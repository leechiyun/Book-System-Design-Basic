# Summary

## 2장: 시스템 규모 추정

- 치윤
  - 2의 제곱수: 컴퓨터는 이진수. 비트값으로 여러 단위들을 변환하여 파악하기
  - 가용성 수치: 99%는 생각보다 오류가 높은 수치
  - 설계에 대한 추정(사용자, 레포지토리)
  - 디스크 seek: 성능 느림
  - 가정 적어두기

## 3장: 시스템 설계 면접 공략법

# Insight

## 2장: 시스템 규모 추정

- 치윤
  - 큰 틀 짜기
    - 요구사항으로 규모를 고려
    - 제약사항 만족하는지 대략적으로 계산
  - 상세 설계
    - 기업에 따라 우선적으로 생각하는 것이 다름
  - 마무리
    - 완벽한 설계는 없음.
    - 문제점을 찾아보고 어떻게 해결할 것인지 생각하기

## 3장: 시스템 설계 면접 공략법

- 치윤
  - 면접 뿐만 아니라 알고리즘 설계에도 적용하는데 유용하다 느낌!
  - 바로바로 답을 내는 것 X. 왜 이런 결정을 했는지 집중
  - 면접은 대화하는 자리. 질문하는 것 두려워하지 말기. 자신이 생각하는 것 말하기

# Debate

### 디스크 IO 접근을 줄이기 위한 노력 by 진서

- 캐시 : Redis, Memcached
- 데이터베이스 단에서 인덱스 최적화
- 배치 처리
- Lazy Loading
- Disk I/O Scheduling
  - [https://seungjuitmemo.tistory.com/344](https://seungjuitmemo.tistory.com/344)
- 데이터 압축(Spring Data JPA와 GZIP사용)

### Disk IO 성능 측정

- 치윤
  - Kernal 단에서 모니터링
  - ElasticSearch에서 접근 (https://app.netdata.cloud/spaces/netdata-demo/rooms/all-nodes/overview?_gl=1*10muwp2*_ga*MTMxMDc2MDI1My4xNzE3Njg1NDY4*_ga_J69Z2JCTFB*MTcxNzY4NTQ2OC4xLjEuMTcxNzY4NTQ3Mi41Ni4wLjA.#metrics_correlation=false&after=-900&before=0&utc=Asia%2FSeoul&offset=%2B9&timezoneName=Seoul&modal=&modalTab=&modalParams=&selectedIntegrationCategory=deploy.operating-systems&force_play=false&d8a4e0c5-7c79-4145-900e-83a9f06fcb6a--chartName-val=menu_system)
- 노아
  - Shell 명령어 사용: iostat, dd, hdparam 
- 진서
  - prometheus + grafana
  - 시스템 오류 시, 알람 전달 기능

### 성능 테스트

- 진서
  - [https://velog.io/@sontulip/performance-test](https://velog.io/@sontulip/performance-test) 
  - https://loosie.tistory.com/821#%EC%8A%A4%ED%8A%B8%EB%A0%88%EC%8A%A4_%ED%85%8C%EC%8A%A4%ED%8A%B8_(Stress_Test)\
