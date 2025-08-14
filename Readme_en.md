# Hi, I'm **Kyeonghwan Choi** (DevOps / SRE) 👋

<sub>Updated: 2025-08-14</sub>

I build **reliable, observable, and automated** infrastructure so developers can focus on shipping.
I standardized **mono-repo CI/CD** and rolled out **Datadog** (APM/Logs/Metrics/CI Visibility), improving both release velocity and quality.

- 🔭 **Experience**: ~4 years 5 months (DevOps/SRE)
- 📍 Seoul, Korea (KST / UTC+9)
- ✉️ **Email**: arpamon2@gmail.com
- 🧑‍💻 **GitHub**: https://github.com/dnfwlq8054
- 📝 **Blog**: https://hwan-shell.tistory.com/

---

## 🚀 Highlights
- Unified observability on **Datadog**; standardized JSON logging (`DatadogJsonFormatter`) across FastAPI/SQLAlchemy and services.
- Solved Next.js tracing pitfalls by safely bundling **dd-trace** via multi-stage Docker; reliable `node --require dd-trace/init`.
- Built **reusable GitHub Actions pipelines** (workflow_call, matrices, artifacts); S3-backed cache to bypass 10GB limit.
- Cut **build/test time by 50%+** (~20 → ≤10 min); improved security/quality with **Trivy** + **SonarQube**.
- Automated **versioned EC2** provisioning via Terraform Workspaces; routed with **ALB Target Groups**.

---

## 🧰 Tech Stack
- **Cloud/Infra**: AWS (ECS/Fargate/EC2/ALB/VPC/CloudTrail/CloudWatch/KMS/S3/Glue/Athena/MWAA, API Gateway, Lambda), Linux  
- **IaC/Automation**: Terraform, CloudFormation, GitHub Actions, Jenkins, Shell  
- **Containers/Build**: Docker, Kaniko, multi-stage builds, artifact mgmt  
- **Observability**: Datadog (APM/Logs/Metrics/CI Visibility), Grafana, Prometheus, Loki, Tempo, OpenTelemetry  
- **DB/Data**: MySQL (MHA, InnoDB Cluster), ProxySQL; RDS, S3-based DWH  
- **Languages**: Python, JavaScript/TypeScript, Java, Shell, C++

---

## 🏢 Experience (condensed)

**AITrics — DevOps Engineer** (Oct 2023 – Present)  
- Built APM/log/metric stack (Grafana/Prometheus/Loki/Tempo/Otel) → unified on **Datadog**.  
- Standardized logging & tracing; single-pane correlation (Infra/APM/Logs) → **faster post-deploy triage**.  
- **Mono-repo CI/CD**: reusable workflows, matrices, S3 cache; **self-hosted runners** tuned for workloads.  
- **Impact**: 50%+ faster pipelines; higher SRE signal via Trivy/SonarQube; cleaner communication with tag standards.

**Streami — DevOps Engineer** (Apr 2021 – Oct 2023)  
- **DWH** pipeline: Glue → S3 → Athena; scheduled with **MWAA**; hardened via **KMS + least-privilege IAM**.  
- **Jenkins on Fargate** (dynamic agents); slim multi-stage images; Docker builds via EC2 agents as needed.  
- **VerifyVASP** infra: enclave-based, private ALB, VPC Endpoints; NACL hardening in VPC-peering env.

---

## 🔗 Selected Work & Links
- Jenkins on AWS Fargate: https://github.com/dnfwlq8054/jenkins-in-fargate  
- Tech blog: https://hwan-shell.tistory.com/

---

## 💡 Interests / Now
- **Kubernetes** (networking, CNI, Istio), **GitOps** (Argo CD/Rollouts), and **MLOps** foundations.
- Reducing toil with **clear designs**, **automation**, and **observability-first** practices.

---
