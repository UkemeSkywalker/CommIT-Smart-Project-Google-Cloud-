<img width="3000" height="1720" alt="image-1794935261299" src="https://github.com/user-attachments/assets/b7b5c8ca-b538-4fa6-af90-420fdab0cc29" />

# GCP GKE Infrastructure Deployment with Terraform

A hands-on DevOps assignment demonstrating infrastructure provisioning on Google Cloud Platform using Terraform, Google Kubernetes Engine (GKE), Docker and Kubernetes.

The project provisions a Kubernetes environment on GCP and packages a static web application using Nginx.

## Project Overview

The implementation covers:

- GKE cluster provisioning using Terraform.
- Kubernetes node pool configuration.
- GCP firewall configuration.
- Docker image creation using Nginx.
- Terraform automation for infrastructure deployment.

## Architecture

### Google Kubernetes Engine

The Terraform configuration provisions:

- A GKE cluster named `commit-smart`.
- A node pool named `commit-smart-node-pool`.
- Three nodes using the `e2-standard-2` machine type.
- 100 GB disk configuration for the node pool.

### Firewall

A GCP firewall rule allows TCP traffic on:

- Port 80 — HTTP.
- Port 443 — HTTPS.

### Application Container

The Dockerfile uses the `nginx:alpine` image and copies the static application page into the Nginx web root.

## Technology Stack

- Google Cloud Platform
- Google Kubernetes Engine
- Terraform
- Docker
- Nginx
- Kubernetes

## Repository Structure

```text
.
├── App/
│   └── index.html
├── Terraform/
│   └── modules/
│       ├── gke_cluster/
│       └── gke_firewall/
├── kubernetes/
├── Dockerfile
├── apply-terraform.sh
└── Readme.md
```

## Prerequisites

- Google Cloud account and project.
- Google Cloud CLI.
- Terraform.
- Docker.
- kubectl.
- Appropriate GCP IAM permissions.

## Deployment

Authenticate with Google Cloud:

```bash
gcloud auth application-default login
```

Set the active project:

```bash
gcloud config set project YOUR_PROJECT_ID
```

Review the Terraform configuration and configure the required project variables before deployment.

Initialise Terraform:

```bash
cd Terraform
terraform init
terraform fmt -recursive
terraform validate
terraform plan
```

After reviewing the plan:

```bash
terraform apply
```

## Future Improvements

- Complete application deployment and service configuration.
- Add persistent storage and database infrastructure.
- Introduce a CI/CD pipeline.
- Add workload identity and least-privilege IAM.
- Add Terraform state management.
- Add monitoring and logging.
- Add automated infrastructure validation and security scanning.

## License

See the repository for licensing information.
