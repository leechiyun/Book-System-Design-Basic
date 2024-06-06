# 가용성
- 시스템이 정상적으로 사용 가능한 정도
- 시스템의 연속성, 신뢰성을 강조
- availability  = uptime / (uptime + downtime)

## 주요 매트릭
- uptime: 시스템이 정상적으로 운영되는 시간의 비율
- downtime: 시스템이 비정상적으로 운영되는 시간의 비율
- TPS(Transactions Per Second): 초당 처리할 수 있는 트랜잭션 수
- RPS(Requests Per Second): 초당 처리할 수 있는 요청 수
- MTTF(Mean Time To Failure): 시스템이 고장나기까지 평균적으로 소요되는 시간
- MTTR(Mean Time To Repair): 고장이 발생한 후 복구까지 걸리는 평균 시간 
- MTBF(Mean Time To Between Failures): 두 번의 고장 사이에 평균적으로 소요되는 시간 

## vs 확장성
- 시스템이 증가하는 부하를 효율적으로 처리할 수 있는 능력
- 비용 효율성, 유연성(변화하는 부하에 대한 대응 능력)을 강조

### 주요 매트릭
- Throughput: 단위 시간당 처리할 수 있는 작업의 양

## 고가용성
- 시스템이 상당히 오랜 기간동안 지속적으로 정상 운영이 가능한 성질
- 예기치 못한 상황에서도 시승템이 계속 정상 운영될 수 있어야 함
- SOAP를 감지해 제거하는데 좌우됨

### 장애
- hardware
- software: OS, Application
- service: fail to access network, latency, cloud, performance
- external: blackout

### 고가용성 클러스터
- 중복성
  - 클러스터: 하나의 논리 엔티티로 함께 작동하는 인스턴스 모임 
- 페일오버
  - 클러스터 내 서버 인스턴스에 대한 페일오버 보호 허용
  - 클러스터의 요청 처리에 실패한 노드의 서버에서 클러스터의 다른 노드가 요청을 자동으로 넘겨받음

### 주요 매트릭
- five nines: 99.999%(1년간 5분 15초 이하의 장애시간 허용)
