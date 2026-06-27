# Hi, I'm Brian 👋

Senior platform engineer and SRE with 12 years building and owning cloud infrastructure across AWS, GCP, and Azure. Most recently at Actian, designed the Terraform modules and CI/CD pipelines that 4 engineering teams built on, cutting cluster provisioning from 6 hours to 30 minutes and eliminating $180k in annual cloud waste.

Before that, spent 4 years as the sole North American SRE at base2Services, owning production across 64 enterprise clients in Healthcare, Finance, Legal, and Retail under HIPAA, SOC2, and ISO 27001. Defended a 99.5% SLO solo across time zones.


---

## Platform Engineering Portfolio

Six connected projects demonstrating a complete internal developer platform — event-driven pipelines, infrastructure automation, full-stack observability, Kubernetes operators, ML workload delivery, and a single-command bootstrap that ties it all together.

![Platform Architecture](screenshots/platform-architecture.svg)

---

### 🚀 [Internal Developer Platform](https://github.com/SmartBrisco/Internal-Developer-Platform) — Start Here

One command spins up the entire platform locally in under 5 minutes.
![Platform up in 299s](screenshots/platform-up.png)

```
make platform-up
```

Orchestrates all five projects below: creates the kind cluster, installs Argo Workflows and Argo Events, deploys the observability stack, installs the namespace operator, fires a test webhook, and confirms the pipeline runs end to end. The platform is designed to boot and operate without manual intervention.

`Kubernetes` `kind` `Argo Workflows` `Argo Events` `Makefile` `Kargo`

---

### 🔧 [Argo Events CI/CD Pipeline](https://github.com/SmartBrisco/argo-event-pipeline)

Event-driven CI/CD pipeline built on Kubernetes using Argo Events and Argo Workflows. Webhook triggers flow through a NATS event bus into a multi-step pipeline with Trivy security scanning, Jira-style ticket integration, and an AI-powered failure analysis layer using a locally hosted Ollama model — no external API keys, no egress cost.

`Kubernetes` `Argo Events` `Argo Workflows` `NATS` `Trivy` `Ollama` `Python`

---

### ⚙️ [GitOps Infrastructure Pipeline](https://github.com/SmartBrisco/gitops-infra-pipeline)

GitHub Actions pipeline that provisions AWS infrastructure on every commit to main using Terraform. OIDC authentication eliminates all long-lived credentials. Multi-stage security gates run Terraform fmt, validate, TFLint, and Trivy IaC scanning before any apply. Three-channel Slack notifications for deployments, alerts, and a complete audit trail.

`GitHub Actions` `Terraform` `AWS` `OIDC` `Trivy` `TFLint` `OPA` `Slack`

---

### 📊 [Platform Observability Stack](https://github.com/SmartBrisco/platform-observability)

Full-stack observability platform deployed on Kubernetes. OpenTelemetry Collector receives live telemetry from the Argo pipeline via OTLP gRPC, routing traces to Jaeger and metrics to Prometheus, visualized in Grafana dashboards. All components run in an isolated monitoring namespace with cross-namespace RBAC. Argo workflow execution data flows end to end through the stack.

`OpenTelemetry` `Jaeger` `Prometheus` `Grafana` `Kubernetes` `OTLP`

---

### 🏗️ [Namespace Provisioner](https://github.com/SmartBrisco/namespace-provisioner)

Kubernetes operator built in Go using kubebuilder. Watches for `ManagedNamespace` custom resources and reconciles namespaces with RBAC, resource quotas, and network policies automatically. Self-healing — if configuration drifts from spec, the operator corrects it without intervention. Deployed and managed as part of the IDP bootstrap.

`Go` `kubebuilder` `Kubernetes Operators` `CRD` `RBAC`

---

### 🤖 [ML Platform IDP](https://github.com/SmartBrisco/ml-platform-idp)

CI/CD pipeline for containerized ML workloads. Builds and pushes images to AWS ECR with immutable tags, scans with Trivy (warn in dev, hard fail in prod), signs with Cosign via Sigstore for cryptographic integrity, writes tamper-evident audit records to S3 with object lock, and triggers downstream deployment via Argo Events. Designed with GxP-regulated environments in mind.

`GitHub Actions` `AWS ECR` `Cosign` `Sigstore` `Helm` `Helmfile` `Django` `OIDC` `GxP`
