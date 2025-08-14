# curriculum-vitae[최경환_이력서_리라이팅_2025_08_14.md](https://github.com/user-attachments/files/21771076/_._._2025_08_14.md)
# 최경환 (DevOps / SRE)

- **전화**: 010-5159-8054
- **이메일**: arpamon2\@gmail.com
- **GitHub**: [https://github.com/dnfwlq8054](https://github.com/dnfwlq8054)
- **Blog**: [https://hwan-shell.tistory.com/](https://hwan-shell.tistory.com/)

---

## 요약 (Summary)

- 인프라 자동화와 관측성(Observability)에 집중해 **개발자가 개발에만 몰입**할 수 있는 환경을 구축하는 DevOps 엔지니어입니다.
- 모노레포 기반 **CI/CD 체계 표준화**와 **Datadog 도입**을 통해 릴리스 속도와 품질을 동시에 개선했습니다.
- 불필요한 수작업을 제거하고 **IaC(Terraform/CloudFormation)** 와 **자동화 스크립트**로 일관성을 확보합니다.
- 복잡한 문제를 단순화하고, **읽기 쉬운 코드/설계**와 재사용 가능한 템플릿으로 팀 생산성을 높입니다.

> 총 경력: **약 4년 5개월**

---

## 기술 스택 (Skills)

**Cloud & Infra**: AWS (ECS/Fargate/EC2/ALB/VPC/CloudTrail/CloudWatch/KMS/S3/Glue/Athena/MWAA, API Gateway, Lambda), Linux\
**IaC & Automation**: Terraform, CloudFormation, GitHub Actions, Jenkins, Shell Scripting\
**Containers & Build**: Docker, Kaniko, 멀티스테이지 빌드, 아티팩트 관리\
**Observability**: Datadog(APM/Logs/Metrics/CI Visibility), Grafana, Prometheus, Loki, Tempo, OpenTelemetry\
**DB & Data**: MySQL (MHA, InnoDB Cluster), ProxySQL, (RDS, S3 기반 DWH 파이프라인)\
**Languages**: Python, JavaScript/TypeScript, Java, Shell, C++

---

## 경력

### 주식회사 에이아이트릭스 (AITrics) · DevOps 엔지니어

**2023.10 – 현재** (정규직)

**1) Vitalcare Observability 구축 (OSS → Datadog 전환)**

- 초기: Grafana + Prometheus + Loki + Promtail + Tempo + OpenTelemetry로 **APM/로그/메트릭 관측** 환경을 구축.
- 전환: 확장성·운영성 한계를 해소하기 위해 **Datadog**(APM·Logs·Infra·CI Visibility)로 일원화.
- **로그 표준화**: `DatadogJsonFormatter`를 구현해 FastAPI/SQLAlchemy 등 **이기종 로거를 JSON 포맷으로 일원화**.
- **Node(Next.js) 트레이싱 문제 해결**: `node --require dd-trace/init` 권장 모드에서도 패키지가 누락되지 않도록
  **멀티스테이지 도커**로 `dd-trace` 번들을 안전하게 주입.
- **효과**: APM으로 서비스 흐름과 병목을 가시화, **단일 화면(Single Pane)** 에서 Infra·APM·Logs 연계 분석,
  배포 후 오류 **즉시 트래킹** 가능.

**2) GitHub Actions 기반 모노레포 CI/CD 표준화**

- 요구사항:
  - Git Tag 기준으로 **백엔드/프론트엔드 등 전 컴포넌트가 동일 이미지 태그**를 사용.
  - 릴리스마다 **버전별 EC2**를 자동 프로비저닝(Terraform Workspace 기반), ALB Target Group으로 **버전 라우팅**.
  - 배포 완료 시 **Slack 알림**(성공/배포 대상 EC2/Tag/커밋 정보).
  - Feature 브랜치 푸시 시 **주기적 CI**(도커 이미지 빌드 포함), 수동 **workflow\_dispatch** 지원.
- 구현:
  - **Terraform**으로 공통 인프라 구성 및 워크스페이스 전략으로 **버전 격리**.
  - **workflow\_call**로 템플릿화하여 **중복/결합도 축소** 및 파이프라인 가시성 확보.
  - GitHub Actions **Matrix**로 Next.js 테스트 분산, **아티팩트**로 커버리지 집계 후 SonarQube 업로드.
  - GitHub Actions 캐시 10GB 한계를 우회하기 위해 **S3 캐시 저장소**를 설계·적용.
  - 워크로드 특성에 맞춘 **전용 러너(셀프호스트)** 를 구성해 병렬 처리 및 자원 효율화.
- **성과**:
  - **빌드/테스트 시간 50%+ 단축** *(약 20분 → 10분 이내)*.
  - Trivy/ SonarQube로 **보안/정적분석 품질 향상**.
  - Git Tag 표준화로 **팀 간 커뮤니케이션 비용 감소** 및 릴리스 가시성 개선.

**3) 기타 운영·자동화**

- AWS 비용 최적화, Datadog 파이프라인 관리, 메가존과의 AWS 계약 실무.
- 온프레미스 MySQL 이중화(MHA + ProxySQL, Master↔Replica), InnoDB Cluster 구축.
- 필요 자동화를 위한 **AWS Lambda 유틸리티** 개발.

---

### (주) 스트리미 · DevOps 엔지니어

**2021.04 – 2023.10** (정규직)

**1) Data Warehouse 인프라 구축 (Terraform · Glue → S3 → Athena · MWAA 배치)**

- 데이터팀 설계를 함께 리뷰·보완하고 **IaC로 인프라 표준화**.
- Glue로 RDS 데이터를 **S3 적재**, Athena로 **애드혹/리포트 쿼리** 환경 제공, 배치는 MWAA로 **주기적 적재**.
- 권한 분리·영역화 대신 **S3 KMS 암호화 + IAM 최소권한**으로 보안 단순화.
- CloudTrail로 퍼블릭 경로 접근 리소스를 식별하고 **VPC Endpoint 우회**로 내부화.
- **효과**: 추측성 데이터 의존을 줄이고 **데이터 품질·신뢰도**를 높여 부서 간 활용 기반 마련.

**2) AWS Fargate 기반 Jenkins CI/CD (동적 에이전트)**

- EC2 Master/Slave의 비효율을 해소하기 위해 **ECS Fargate 에이전트 자동 스케일** 아키텍처로 전환.
- Docker 빌드 제약(DIND) 해결:
  - 이미지 비대화를 막기 위해 **멀티스테이지 빌드**로 에이전트 슬림화.
  - 도커 빌드가 필요한 경우 **Jenkins EC2 Plugin + 전용 AMI**로 안정적으로 수행.
- **성과**: 에이전트 수동 증감 제거, 서버 운영 오버헤드 축소, **동시 빌드 충돌 없이** 작업 단위 명확화.

**3) 거래소 Travel Rule 대응 VerifyVASP 인프라**

- 100만원 이상 거래를 위한 교차 거래소 인증을 **Enclave Server** 기반으로 구현.
- VerifyVASP → (Private) ALB → 내부 HTTP 통신으로 **Gopax API Private 접근**을 중개.
- VPC Peering 환경에서 **NACL로 443 포트 차단 후 내부 ALB**를 통해 프라이빗 경로만 허용.
- **성과**: 적은 인원으로 신속히 네트워크 보안 요건을 충족하고 안정적 운영.

**4) 그 외**

- ISMS 심사 대응, GitLab/ Jira Service Management/ AML 서버 운영.

---

## 학력

- **학점은행제(컴퓨터공학)**, 2020.12 – 2021.08 (졸업)
- **동양미래대학교(정보통신과, 3년)**, 2012.03 – 2017.02 (졸업)

---

## 수상/자격/교육

- 오픈스택을 활용한 클라우드 서비스 구축 (하이미디어아카데미, 2021.01)
  - 클라우드 서비스 관련 교육 수강(취업 후 중도 하차)
- 정보보안전문가 양성교육 (융합보안지원센터, 2017.04)
  - SMB 취약점(이터널블루) 모의해킹, 간단 악성코드 분석

---

## 외국어

- 일본어: 일상 회화
- 영어: 일상 회화

---

## 링크

- AWS Fargate를 이용한 Jenkins 구축: [https://github.com/dnfwlq8054/jenkins-in-fargate](https://github.com/dnfwlq8054/jenkins-in-fargate)
- 기술 블로그: [https://hwan-shell.tistory.com/](https://hwan-shell.tistory.com/)

