<div align="center">

# 안지산 | BBBIC 💻

### Backend & Cloud Engineer

<img src="https://img.shields.io/badge/Backend Developer-333333?style=for-the-badge" />
<img src="https://img.shields.io/badge/Cloud-527FFF?style=for-the-badge&logo=amazonaws&logoColor=white" />
<img src="https://img.shields.io/badge/DevOps-2496ED?style=for-the-badge&logo=docker&logoColor=white" />

<br/>
<br/>

**안정적인 백엔드 시스템과 운영 가능한 클라우드 환경을 설계하는 개발자입니다.**

Spring Boot 기반 API 개발과 AWS EC2·RDS 환경의 서비스 배포 경험을 바탕으로
Docker, CI/CD, Kubernetes와 모니터링 기술을 학습하며
**Backend & Cloud / Data Engineering** 역량을 확장하고 있습니다.

</div>

---

## 🧭 About Me

- **Java와 Spring Boot 기반 백엔드 서버 및 REST API 개발 경험**이 있습니다.
- Controller, Service, Repository 계층을 분리하고 **API와 데이터베이스 구조를 설계하는 과정**에 관심이 있습니다.
- **AWS EC2·RDS 기반 서비스 배포와 운영 환경 구성**을 경험했습니다.
- Docker, GitHub Actions, Kubernetes를 활용한 **일관된 배포 환경과 CI/CD 파이프라인 구축 역량**을 키우고 있습니다.
- 로그, 메트릭, 트레이싱을 기반으로 **장애 원인을 추적하고 개선하는 운영과 Observability 관점의 개발을 지향**합니다.
- 이미지, 비디오, 오디오, 텍스트를 다루는 **멀티모달 데이터 파이프라인**을 구축했습니다.
- 데이터 수집, 전처리, 라벨링, 학습/검증 분리, 모델 실험까지 **데이터 흐름 전체를 설계하고 개선**한 경험이 있습니다.

---

## 🚀 Projects

### 1. TripMate - 여행 동행/일정 관리 서비스 (2024.09 ~ 2025.01)

`Java` `Spring Boot` `MySQL` `AWS EC2` `AWS RDS` `Docker` `GitHub`

> 여행 일정 및 동행 기능을 제공하는 웹 서비스

- **백엔드·클라우드 영역 담당**
- **Spring Boot 서버를 AWS EC2 환경에 배포**
- **MySQL / AWS RDS 기반 데이터베이스 연동 구성**
- 서버 실행 환경, 포트 설정, 배포 과정에서 발생한 **인프라 이슈 해결**
- 로컬 개발 환경과 클라우드 운영 환경의 차이를 고려한 배포 구조 경험

---

### 2. (주)무하유 - PDF 논문 이미지 기반 표절탐지 시스템 (2025.03 ~ 2025.07)

`Python` `OpenCV` `PIL` `PyTorch` `PDF Processing` `Similarity Matching` `GitHub`

> PDF 논문 이미지의 변형 여부를 탐지하는 표절탐지 시스템

- PDF 논문에서 이미지 추출 및 표절 의심 데이터셋 생성
- crop, rotation, flip, grayscale, brightness, contrast 등 **다양한 변형 조건 설계**
- 원본 이미지와 변형 이미지 간 **유사도 기반 탐지 알고리즘 실험**
- 딥러닝 기반 탐지 모델 실험을 통해 기존 방식의 한계와 개선 방향 분석
- **데이터 수집부터 전처리, 실험, 결과 비교까지 전체 흐름 주도**

---

### 3. (주)무하유 - 유해 콘텐츠 탐지 시스템 (2025.08 ~ 2026.01)

`Python` `PyTorch` `YOLOv8` `CLIP` `KoBERT` `YAMNet` `SlowFast` `FFmpeg` `GitHub`

> 이미지·비디오·오디오·텍스트 기반 멀티모달 유해 콘텐츠 탐지 프로젝트

- **약 5,874개 클립 기반 멀티모달 데이터 파이프라인 구축**
- 비디오 클립 분할, 오디오 추출, 텍스트 스텁 생성 자동화
- 학습/검증 데이터 분리 및 **JSONL manifest 생성**
- 클래스 불균형 문제를 분석하고 **Focal Loss, threshold 조정, validation loop 개선** 실험
- 모델 구조 개선을 위해 **데이터 스키마 단순화, modality fallback 처리, GPU/CPU tensor 오류 수정**

---

### 4. AI 기반 금융 이상거래 탐지·운영 플랫폼 (2026.07 ~ 진행 중)

`Java 17` `Spring Boot` `Gradle` `JUnit` `PostgreSQL` `FastAPI` `Docker` `Kubernetes` `AWS` `GitHub Actions`

> 금융거래와 사용자 행동을 분석해 이상거래를 탐지하고, 위험 대응과 FDS 담당자의 사건 처리를 지원하는 운영 플랫폼

* **계좌이체·오픈뱅킹·ATM 인출과 거래 전후 사용자 행동을 결합한 FDS 업무 흐름 설계**
* 신규 기기 고액 이체, 위험계좌 송금, 분산 송금, 입금 후 ATM 인출 등 **8개 핵심 이상거래 시나리오 정의**
* Rule 기반 탐지와 ML 위험 분석을 결합하고, LOW·MEDIUM·HIGH·CRITICAL에 따른 **위험 기반 거래 대응 구조 설계**
* Spring Boot 초기 환경 구축 및 **Controller·Service 계층을 분리한 Health Check API와 테스트 구현**
* 고위험 사건의 탐지 근거와 행동 타임라인을 설명하는 **생성형 AI 분석 리포트 구조 설계**
* LLM 호출 선별, 모델 라우팅, 리포트 캐싱과 토큰 사용량 측정을 통한 **AI 비용 최적화·FinOps 구조 설계**
* 향후 PostgreSQL·FastAPI 연동, Docker·Kubernetes 배포, GitHub Actions CI/CD와 **로그·메트릭·트레이싱 기반 Observability 환경 구축 예정**

---

## 🛠 Tech Stack

### Backend

<p>
  <img src="https://img.shields.io/badge/Java-007396?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Spring Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white" />
</p>

### Cloud / Infra

<p>
  <img src="https://img.shields.io/badge/AWS EC2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS RDS-527FFF?style=for-the-badge&logo=amazonrds&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" />
</p>

### Database

<p>
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" />
</p>

### Data Engineering

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/JSONL-000000?style=for-the-badge" />
  <img src="https://img.shields.io/badge/FFmpeg-007808?style=for-the-badge&logo=ffmpeg&logoColor=white" />
</p>

### AI / ML

<p>
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" />
  <img src="https://img.shields.io/badge/YOLOv8-111111?style=for-the-badge" />
  <img src="https://img.shields.io/badge/CLIP-412991?style=for-the-badge" />
  <img src="https://img.shields.io/badge/KoBERT-4285F4?style=for-the-badge" />
  <img src="https://img.shields.io/badge/SlowFast-FF6F00?style=for-the-badge" />
</p>

### Tools

<p>
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/VS Code-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white" />
  <img src="https://img.shields.io/badge/PyCharm-000000?style=for-the-badge&logo=pycharm&logoColor=white" />
</p>

---

## 📌 Currently Focused On

- Spring Boot 기반 백엔드 API 설계
- AWS EC2 / RDS 기반 서비스 배포
- Docker 기반 실행 환경 구성
- 데이터 수집·전처리·학습 파이프라인 자동화

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

<p>
  <a href="https://creative-nigella-4f4.notion.site/My-Portfolio-1de247251605801e9297c740a8ed688d?source=copy_link">
    <img src="https://img.shields.io/badge/Portfolio-Notion-000000?style=for-the-badge&logo=notion&logoColor=white" />
  </a>
</p>

---

