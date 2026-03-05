# Hi, I'm Brian 👋

Senior Platform Engineer with 11 years building the infrastructure 
and tooling that development teams depend on. Cloud agnostic Kubernetes platforms, 
event-driven CI/CD, GitOps automation, and observability stacks that 
give teams visibility into their systems.

I build things that run without me. Then I document them well enough 
that others can too.

---

## Platform Engineering Portfolio

Three connected projects demonstrating a complete internal developer platform, from event-driven pipelines to infrastructure automation to full-stack observability.

### 🔧 [Argo Events CI/CD Pipeline](https://github.com/SmartBrisco/argo-event-pipeline)
Event-driven CI/CD pipeline built on Kubernetes using Argo Events and Argo Workflows. Webhook triggers flow through a NATS event bus into a multi-step pipeline with Trivy security scanning, Jira-style ticket integration, and an AI-powered failure analysis layer using a locally hosted Ollama model.

`Kubernetes` `Argo Events` `Argo Workflows` `NATS` `Trivy` `Ollama` `Python`

---

### ⚙️ [GitOps Infrastructure Pipeline](https://github.com/SmartBrisco/gitops-infra-pipeline)
GitHub Actions pipeline that provisions AWS infrastructure on every commit to main using Terraform. Features OIDC authentication eliminating all long-lived credentials, multi-stage security gates, and three-channel Slack notifications for deployments, alerts, and audit logging.

`GitHub Actions` `Terraform` `AWS` `OIDC` `Trivy` `TFLint` `Slack`

---

### 📊 [Platform Observability Stack](https://github.com/SmartBrisco/platform-observability)
Full-stack observability platform deployed on Kubernetes. OpenTelemetry Collector receives live telemetry from the Argo pipeline, routing traces to Jaeger and metrics to Prometheus, visualized in Grafana dashboards. Argo workflow execution data flows end to end through the stack.

`OpenTelemetry` `Jaeger` `Prometheus` `Grafana` `Kubernetes` `OTLP`

