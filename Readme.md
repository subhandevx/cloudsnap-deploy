# CloudSnap Deployment Repository

This repository manages the infrastructure and Kubernetes deployment configuration for the CloudSnap application.

## Repository structure

- `terraform/` — AWS infrastructure such as VPC, EKS, IAM and node groups
- `kubernetes/` — CloudSnap application and monitoring manifests
- `argocd/` — Argo CD application definitions

## Planned workflow

1. Terraform creates the AWS infrastructure
2. GitHub Actions builds CloudSnap images and pushes them to ECR
3. Argo CD reads this repository
4. Argo CD deploys CloudSnap into EKS
5. Prometheus, Grafana and Loki provide observability