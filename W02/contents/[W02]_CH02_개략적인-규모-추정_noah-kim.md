# 사고실험을 통한 성능 요구사항 추정

- 다양한 시나리오 설정
- 설정한 시나리오를 바탕으로 시스템의 성능 수치를 계산
- 이를 기반으로 필요한 자원과 설정 추정이 가능

# 규모 추정에 필요한 기본기

## 2의 제곱수

- 데이터 볼륨 단위로 표현된 값을 2의 제곱수로 표현하면 어떻게 되는지 알아야 함

---

- 1KB: 2^10
- 1MB: 2^20
- 1GB: 2^30
- 1TB: 2^40
- 1PB: 2^50

---

- 1 ASCII Character: 1 byte
- 1 UTF-16 Korean Character: 2 byte
- 1 UTF-8 Korean Character: 3 byte

## 응답 지연 값

- 1ms(millisecond): $10^{-3}$ second
    - network packet transmission: different region(150ms)
    - Disk access: HDD(2ms)
    - Keyboard input response
    - HTTP request response
- 1us(microsecond): $10^{-6}$ second
    - network packet transmission: same region(500us)
    - Disk access: SSD(16us)
    - Memory access: Main memory(3us)
    - database query response
- 1ns(nanosecond): $10^{-9}$ second
    - CPU Clock speed: L1 cache(1ns), L2 cache(4ns)

## 가용성 관련 수치

### 고가용성

- 시스템이 오랜 시간 동안 지속적으로 중단 없이 운영될 수 있는 능력

### SLA
- Service Level Agreement
  - Service Provider ↔ Customer 간의 합의
  - 고객이 받게 될 예상 서비스 수준, 평가기준, 서비스 수준을 달성하지 못할 경우 조치 등을 정의
- 종류
  - uptime: 서비스 가용 시간
  - downtime: 서비스 장애 시간

# Case

## 추정: QPS & 저장소

### 가정

- MAU(monthly active users): 3M
- DAU(daily active users): 50% of MAU
- Average daily tweets uploaded per user: 2
- Percentage of Tweets Including media: 10%
- data retention period: 5 years

### 결론

- QPS(query per second)
    - (DAU * Average daily tweets uploaded per user) / 24 hours / 3600 second
    - Max QPS: 2 * QPS
- Average of tweet size
    - tweet_id: 64bytes
    - content(text): 140bytes
    - content(media): 1mb
- Repository for media
    - DAU * Average daily tweets uploaded per user * Percentage of Tweets Including media * Average of Media size(1mb)

# Tip

## Rounding and Approximation

- 논리적인 흐름안에서 도출된 수식 자체를 제시하는 것이 중요
- 수식의 결과는 적절한 근사치로 표현

## Note assumption

## Attach unit

## Frequently occuring issue

- QPS, Max QPS
- Repository, Cache
- Server count
