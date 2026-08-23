<div align="center">

# 안지산 | BBBIC 💻

### Backend & Cloud Engineer

<img src="https://img.shields.io/badge/Backend-333333?style=for-the-badge" />
<img src="https://img.shields.io/badge/Cloud-527FFF?style=for-the-badge&logo=amazonaws&logoColor=white" />
<img src="https://img.shields.io/badge/DevOps-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Data Engineering-3776AB?style=for-the-badge&logo=python&logoColor=white" />

<br/>
<br/>

**서비스의 기능 구현을 넘어, 안정적으로 배포하고 운영할 수 있는 구조를 고민합니다.**

Java·Spring Boot 기반 백엔드 개발과 AWS 서비스 배포 경험을 바탕으로  
API와 데이터 구조, 클라우드 인프라, CI/CD, Observability에 관심을 두고 있습니다.

백엔드 시스템의 신뢰성과 확장성을 높이는 설계부터  
Cloud Native 환경의 배포·운영, 비용 효율화까지 역량을 확장하고 있습니다.

</div>

---

## 🧭 About Me

- 약 **5,874개 비디오 클립**을 대상으로 이미지·비디오·오디오·텍스트를 연결하는 멀티모달 데이터 파이프라인을 구축했습니다.
- 유해 데이터 비율이 **약 8%인** 클래스 불균형 환경에서 평가 기준을 Accuracy가 아닌 F1-score 중심으로 재정의했습니다.
- Focal Loss, threshold 조정, validation loop 개선을 통해 비디오 모델의 F1-score를 **0.7273에서 0.9878까지 개선**했습니다.
- PDF 논문에서 추출한 이미지를 바탕으로 **500개 이상의 원본 이미지 데이터베이스**와 변형 이미지 데이터셋을 구성했습니다.
- 여행 서비스 프로젝트에서 Spring Boot, EC2, ALB, RDS, S3, CloudFront를 연결한 AWS 배포 구조를 경험했습니다.
- AWS 운영 과정에서 NAT Gateway가 약 **942시간 동안 55달러 이상**의 비용을 발생시킨 사례를 확인하며 인프라 구조와 운영 비용을 함께 고려해야 한다는 점을 배웠습니다.
- 금융 이상거래 대응 플랫폼을 설계하며 거래 접수, 멱등성, 상태 전이, 감사 이력, AI 서비스 연동을 위한 API·데이터 계약을 정의하고 있습니다.
- 구현 결과뿐 아니라 ADR, API 계약, 데이터베이스 명세, 테스트와 GitHub PR 이력을 함께 남기는 개발 방식을 지향합니다.

---

## 🚀 Projects

### 1. FinGuardOps — 금융 이상거래 대응 운영 플랫폼

`2026.07 ~ 진행 중`

`Java 17` `Spring Boot` `Gradle` `JUnit` `PostgreSQL` `FastAPI`  
`Redis` `Docker` `GitHub Actions` `AWS` `Prometheus` `Grafana`

> 금융거래 접수부터 이상 탐지, 사건 조사, 최종 판정, 감사 이력과 AI 분석 리포트까지 연결하는 FraudOps 플랫폼

#### 주요 설계

- 신규 기기 고액 이체, 위험계좌 송금, 단시간 분산 송금, 고액 입금 후 ATM 인출 등 **8개 핵심 이상거래 시나리오 정의**
- 거래, 탐지 결과, 사건, 조사 메모, 감사 이력의 책임과 데이터 관계 설계
- 사건 진행 상태와 최종 조사 결과를 분리한 상태 전이 구조 정의
- Rule·ML 탐지와 생성형 AI 리포트의 책임 분리
- LLM 장애가 금융거래 판단에 영향을 주지 않도록 fallback과 캐시 정책 설계
- AI 호출량, 토큰 사용량, 사건당 비용, 캐시 적중률을 측정하는 운영 지표 정의
- API 시간·금액·식별자·페이지네이션·오류 응답·멱등성 공통 규칙 정의

#### 구현 현황

- Java 17·Spring Boot·Gradle 기반 백엔드 프로젝트 구성
- Controller·Service·DTO 계층을 분리한 Health Check API 구현
- JUnit 기반 Service 단위 테스트와 Controller 통합 테스트 작성
- PostgreSQL·JPA·Flyway·Testcontainers 테스트 환경 구성
- 거래 및 멱등성 레코드 영속화를 위한 테이블·제약조건·인덱스 설계
- Entity와 Repository 계층을 단계적으로 구현 중

#### 확장 방향

```text
거래 접수 API
→ 규칙 기반 탐지
→ AI 서비스 연동
→ 사건 생성·조사·판정
→ Docker 기반 통합 환경
→ CI/CD
→ AWS 배포
→ 로그·메트릭·트레이싱 기반 Observability
```

---

### 2. ㈜무하유 — PDF 논문 이미지 기반 표절 탐지 시스템

`2025.03 ~ 2025.07`

`Python` `OpenCV` `PIL` `PyTorch` `PDF Processing`  
`Cosine Similarity` `SSIM` `pHash`

> PDF 논문의 이미지를 추출하고 변형 여부를 분석하는 표절 탐지 프로젝트

- PDF 파일에서 이미지 자동 추출
- **500개 이상의 원본 이미지 데이터베이스** 구성
- crop, rotation, flip, grayscale, brightness, contrast 등 변형 조건 설계
- 원본·변형 이미지 쌍으로 표절 의심 데이터셋 생성
- Cosine Similarity, SSIM, pHash 기반 탐지 성능 비교
- Siamese Network와 Contrastive Loss 기반 딥러닝 방식 실험
- 데이터 수집, 전처리, 모델 실험, 평가 결과 비교 과정 주도
- 단순 유사도 기반 방식과 딥러닝 방식의 장단점 분석

---

### 3. ㈜무하유 — 멀티모달 유해 콘텐츠 탐지 시스템

`2025.08 ~ 2026.01`

`Python` `PyTorch` `YOLOv8` `CLIP` `KoBERT`  
`YAMNet` `SlowFast` `FFmpeg` `JSONL`

> 이미지·비디오·오디오·텍스트를 결합한 유해 콘텐츠 탐지 프로젝트

- 약 **5,874개 클립**을 대상으로 멀티모달 데이터 파이프라인 구축
- 비디오 분할, 오디오 추출, 텍스트 데이터 생성 과정 자동화
- 학습·검증 데이터 분리와 JSONL manifest 생성
- modality별 데이터 구조와 fallback 처리 설계
- 유해 데이터 비율 약 **8%**의 클래스 불균형 문제 분석
- Accuracy 대신 Precision, Recall, F1-score를 중심으로 평가 기준 개선
- Focal Loss, threshold 조정, validation loop 개선 반복
- 비디오 모델 F1-score를 **0.7273 → 0.9878**로 개선
- GPU·CPU tensor 불일치와 데이터 스키마 오류 해결

---

### 4. TripMate — 여행 동행 및 일정 관리 서비스

`2024.09 ~ 2025.01`

`Java` `Spring Boot` `MySQL` `AWS EC2` `AWS RDS`  
`ALB` `S3` `CloudFront` `Route 53` `ACM` `Docker`

> 여행 일정 공유와 동행자 매칭 기능을 제공하는 웹 서비스

- 백엔드 개발과 AWS 배포 영역 담당
- Spring Boot API 서버를 EC2 환경에 배포
- RDS 기반 MySQL 데이터베이스 구성
- EC2 2대와 Application Load Balancer를 연결한 서버 구조 경험
- React 정적 파일을 S3와 CloudFront를 통해 배포
- Route 53과 ACM을 활용한 도메인·HTTPS 구성
- VPC, 퍼블릭·프라이빗 서브넷, NAT Gateway, 보안 그룹 구성
- 카카오 로그인과 프로필 등록 API 흐름 설계 및 연동
- CORS, HTTPS, RDS 연결, 리다이렉트 흐름 문제 해결
- NAT Gateway의 사용 시간과 비용을 분석하고 개발 환경의 고정 인프라 비용 문제 확인

---



## 🎓 Education & Activities

### Education


- **한국항공대학교 소프트웨어학과**
  - `2020.03 ~ 2026.08 졸업 예정`
  - 백엔드 개발, 데이터 처리, AI·클라우드 프로젝트 수행


### Industry-Academic Projects


- **㈜무하유 산학협력 프로젝트**
  - `2025.03 ~ 2026.01`
  - PDF 이미지 표절 탐지 및 멀티모달 유해 콘텐츠 탐지 프로젝트 수행


### Community / Academic Activities


- **한국항공대학교 알고리즘 학회 'Koala'**
  - `2024.07 ~ 2025.06`
  - 알고리즘 및 자료구조 학습과 문제 풀이 스터디 참여
  - 백준 등 온라인 저지 문제를 활용한 코딩 테스트 대비
  - 풀이 과정과 시간·공간 복잡도를 공유하며 문제 해결 방식 개선
  - 학회원들과 정기적인 코드 리뷰 및 알고리즘 학습 내용 공유


- **LG CNS AM Inspire Camp 6기**
  - `2026.07 ~ 진행 중`
  - Java·Spring Boot 기반 백엔드 개발과 데이터베이스, MSA, Cloud, DevOps 전반의 실무형 교육 과정 참여
  - 현업 시스템의 요구사항 분석부터 설계, 구현, 테스트, 배포, 운영까지 이어지는 전체 개발 흐름 학습
  - 팀 프로젝트를 통해 역할 분담, 일정 관리, Git 기반 협업, 코드 리뷰와 문제 해결 과정 경험
  - 기업 환경을 고려한 API 설계, 데이터 모델링, 서비스 간 통신과 Cloud Native 아키텍처 역량 강화
  - Docker, Kubernetes, CI/CD, 모니터링 기술을 활용한 서비스 배포·운영 환경 구축 학습
  - 현업 문제를 반영한 프로젝트를 수행하며 안정성, 확장성, 유지보수성을 고려하는 개발 역량 강화

---

## 📜 Certifications

### 취득

- `[자격증명]` — `[취득 연월]`

### 준비 중

- ADsP - (8/8 응시 완료, 가채점 합격)
- 정보처리기사 - (필기 8/15 응시 완료, 실기 11월초 응시예정)
- SQLD - (8/22 응시 완료, 결과 대기중)
- OPIc IH 이상 - (현재 IM3 취득, 9월중 재응시 예정)
- SAA (AWS Certified Solutions Architect – Associate) - (10~11월중 응시 예정)
- CKA (Certified Kubernetes Administrator) - (12~1월 응시 예정)

---

## 🛠 Tech Stack

### Backend

<p>
  <img src="https://img.shields.io/badge/Java 17-007396?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Spring Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white" />
  <img src="https://img.shields.io/badge/Gradle-02303A?style=for-the-badge&logo=gradle&logoColor=white" />
  <img src="https://img.shields.io/badge/JPA-59666C?style=for-the-badge" />
  <img src="https://img.shields.io/badge/JUnit5-25A162?style=for-the-badge&logo=junit5&logoColor=white" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" />
</p>

### Database

<p>
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" />
  <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" />
  <img src="https://img.shields.io/badge/Flyway-CC0200?style=for-the-badge&logo=flyway&logoColor=white" />
</p>

### Cloud / Infrastructure

<p>
  <img src="https://img.shields.io/badge/AWS EC2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS RDS-527FFF?style=for-the-badge&logo=amazonrds&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS S3-569A31?style=for-the-badge&logo=amazons3&logoColor=white" />
  <img src="https://img.shields.io/badge/CloudFront-8C4FFF?style=for-the-badge&logo=amazonwebservices&logoColor=white" />
  <img src="https://img.shields.io/badge/Route 53-8C4FFF?style=for-the-badge&logo=amazonroute53&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" />
</p>

### DevOps / Observability — 학습 및 적용 중

<p>
  <img src="https://img.shields.io/badge/GitHub Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" />
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white" />
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white" />
  <img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white" />
</p>

### Data / AI

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white" />
  <img src="https://img.shields.io/badge/FFmpeg-007808?style=for-the-badge&logo=ffmpeg&logoColor=white" />
  <img src="https://img.shields.io/badge/JSONL-000000?style=for-the-badge" />
</p>

### Tools

<p>
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/IntelliJ IDEA-000000?style=for-the-badge&logo=intellijidea&logoColor=white" />
  <img src="https://img.shields.io/badge/VS Code-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white" />
</p>

---

## 📌 Currently Focused On

### Backend Architecture

- Java·Spring Boot 기반 REST API 설계와 구현
- Controller, Service, Repository 계층의 책임 분리
- JPA·PostgreSQL 기반 데이터 모델과 영속성 설계
- 멱등성, 동시성, 상태 전이, 감사 로그를 고려한 백엔드 시스템 설계
- 단위 테스트, 통합 테스트와 Testcontainers 기반 검증 환경 구성

### MSA / Distributed Systems

- 서비스 책임과 데이터 소유권 분리
- 동기 API와 비동기 메시징의 적용 기준
- timeout, retry, circuit breaker를 통한 장애 전파 제어
- Saga, 멱등성, 이벤트 기반 상태 전파 등 분산 시스템 패턴
- Kafka 기반 비동기 이벤트 처리 구조

### Cloud / DevOps

- AWS 네트워크·컴퓨팅·데이터베이스 기반 서비스 배포 구조
- Docker 기반 개발·실행 환경 표준화
- GitHub Actions 기반 CI/CD 파이프라인
- Kubernetes Deployment, Service, ConfigMap, Secret과 리소스 관리
- Cloud Native 환경의 배포·확장·운영 구조

### Observability

- 로그, 메트릭, 트레이싱의 역할과 연결 구조
- Prometheus·Grafana 기반 서비스 상태와 성능 지표 수집
- 지연시간, 오류율, 처리량, 리소스 사용률 기반 문제 분석
- 애플리케이션·인프라·AI 서비스의 통합 운영 지표 설계

### FinOps

- AWS 비용 데이터와 인프라 사용량의 관계 분석
- EC2, RDS, NAT Gateway, Load Balancer, CloudWatch 비용 구조
- 비용 이상 징후와 유휴·과다 할당 리소스 분석
- EKS 환경에서 AWS 비용과 Kubernetes 워크로드의 연결 구조
- 비용 절감 효과와 근거, 신뢰도, 운영 위험을 함께 제시하는 분석 방식

---

## 📫 Contact

<p>
  <a href="mailto:ahnjisan401@gmail.com">
    <img src="https://img.shields.io/badge/Email-ahnjisan401%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
</p>

<p>
  <a href="https://github.com/Ahnjisan">
    <img src="https://img.shields.io/badge/GitHub-Ahnjisan-181717?style=for-the-badge&logo=github&logoColor=white" />
  </a>
</p>
