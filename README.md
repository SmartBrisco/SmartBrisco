# Hi, I'm Brian 👋

Senior Platform Engineer with 11 years building the infrastructure and tooling that development teams depend on. Cloud agnostic Kubernetes platforms, event-driven CI/CD, GitOps automation, and observability stacks that give teams visibility into their systems.

I build things that run without me. Then I document them well enough that others can too.

---

## Why I Built This

These projects are rebuilt from production platform infrastructure for a multi-cloud data warehouse serving enterprise customers across AWS, GCP, and Azure. The patterns here came from real operational pain. LLM-powered error summarization via Ollama and Slack webhook audit logging reduced incident resolution time and accelerated root cause analysis.

---

## Platform Engineering Portfolio

Four connected projects demonstrating a complete internal developer platform, from event-driven pipelines to infrastructure automation to full-stack observability to policy-enforced namespace provisioning.

### 🔧 [Argo Events CI/CD Pipeline](https://github.com/SmartBrisco/argo-event-pipeline)
Event-driven CI/CD pipeline built on Kubernetes using Argo Events and Argo Workflows. Webhook triggers flow through a NATS event bus into a multi-step pipeline with Trivy security scanning, Jira-style ticket integration, and an AI-powered failure analysis layer using a locally hosted Ollama model.

`Kubernetes` `Argo Events` `Argo Workflows` `NATS` `Trivy` `Ollama` `Python`

---

### ⚙️ [GitOps Infrastructure Pipeline](https://github.com/SmartBrisco/gitops-infra-pipeline)
Multi-cloud Terraform pipeline with Kargo progressive delivery across AWS, GCP, and Azure. Features dev-to-prod promotion with OPA and Trivy security gates, manual approval enforcement via GitHub Environments, S3 remote state with DynamoDB locking, scoped IAM with no FullAccess policies, and OIDC authentication eliminating all long-lived credentials.

`GitHub Actions` `Terraform` `Kargo` `AWS` `GCP` `Azure` `OPA` `Trivy` `TFLint` `OIDC` `Slack`

---

### 📊 [Platform Observability Stack](https://github.com/SmartBrisco/platform-observability)
Full-stack observability platform deployed on Kubernetes. OpenTelemetry Collector receives live telemetry from the Argo pipeline, routing traces to Jaeger and metrics to Prometheus, visualized in Grafana dashboards. Argo workflow execution data flows end to end through the stack.

`OpenTelemetry` `Jaeger` `Prometheus` `Grafana` `Kubernetes` `OTLP`

---

### 🛠️ [Namespace Provisioner](https://github.com/SmartBrisco/namespace-provisioner)
Kubernetes operator written in Go using Kubebuilder. Enforces consistent, policy-compliant namespace provisioning across clusters -- every environment gets the correct RBAC, resource quotas, and labels automatically. Drift correction built in: if a RoleBinding is manually deleted, the operator recreates it on the next reconciliation cycle.

`Go` `Kubernetes` `Kubebuilder` `CRD` `RBAC` `Resource Quotas`

---

### 🚀 [Platform](https://github.com/SmartBrisco/Platform)
One command to spin up the full platform locally. Clones all four repos, creates a local kind cluster, installs the namespace operator, deploys the pipeline and observability stack, and fires a test webhook end to end.

`Argo Events` `Argo Workflows` `Go` `Grafana` `Jaeger` `Kargo` `kind` `Kubernetes` `Make` `Ollama` `OpenTelemetry` `Prometheus` `Terraform` `Trivy`