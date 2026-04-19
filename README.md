# Oracle 19c Data Guard 구성

Oracle 19c Data Guard 환경 구축 가이드입니다.

---

#### 사용 소프트웨어

| 소프트웨어 | 버전 |
|-----------|------|
| VirtualBox | 7.0.18 |
| Oracle Linux | release 7.9 |

---

#### 서버 구성

| VM 이름 | 호스트 이름 | 메모리 | CPU | 어댑터1 | 구성 방법 |
|---------|-----------|--------|-----|--------|---------|
| oracle19c_class1 | orcl | 8GB | 4Core | 어댑터에 브리지 | 리눅스 설치 |

---

#### 스토리지

| 파일 이름 | 용량 | 타입 | 용도 |
|----------|------|------|------|
| oracle19c_class1 | 100GB | Dynamic | 서버의 시스템 영역 |

---

#### 네트워크

| VM | Public IP | 넷마스크 | 게이트웨이 | DNS 서버 |
|----|----------|---------|----------|---------|
| Primary (PROD) | 192.168.23.217 | 255.255.0.0 | 192.168.0.1 | 8.8.8.8 |
| Standby (SBDB) | 192.168.43.217 | 255.255.0.0 | 192.168.0.1 | 8.8.8.8 |

---

#### 설치 순서

| 순서 | 문서 |
|------|------|
| 1 | [Primary DB 생성](./1.%20Primary%20DB%20%EC%83%9D%EC%84%B1.md) |
| 2 | [Standby DB 생성](./2.%20Standby%20DB%20%EC%83%9D%EC%84%B1.md) |
| 3 | [DML 동기화 테스트](./3.%20DML%20%EB%8F%99%EA%B8%B0%ED%99%94%20%ED%85%8C%EC%8A%A4%ED%8A%B8.md) |
| 4 | [Switchover 테스트](./4.%20Switchover%20%ED%85%8C%EC%8A%A4%ED%8A%B8.md) |
| 5 | [Failover 테스트](./5.%20Failover%20%ED%85%8C%EC%8A%A4%ED%8A%B8.md) |

---

#### 주요 특징

- Primary/Standby 2노드 Data Guard 환경 구성
- Redo 로그 기반 실시간 동기화 구성
- Switchover/Failover 역할 전환 테스트 포함
- DGMGRL Broker를 활용한 Failover 구성
- 실제 설치 중 발생한 오류 및 해결 방법 포함

