# Automated AWS Container Registry Infrastructure (CI/CD)

An enterprise-grade DevOps and Cloud Architecture portfolio project demonstrating Infrastructure as Code (IaC), containerization, and secure continuous integration (CI/CD) workflows within the AWS cloud environment.

## 🏗️ Architecture Blueprint
1. **Local Development:** Application containerized locally using a lightweight **Nginx** base web server configuration.
2. **Infrastructure as Code:** Production-grade storage architecture provisioned programmatically using **HashiCorp Terraform**.
3. **Storage Tier:** Secure, scalable **Amazon Elastic Container Registry (ECR)** registry deployed to host immutable build blueprints.
4. **GitOps & Automation:** Secure automation pipeline configured via **GitHub Actions** to build, tag, and publish application containers instantly upon code changes.

## 🛠️ Technology Stack
* **Cloud Platform:** Amazon Web Services (AWS)
* **Infrastructure Configuration:** HashiCorp Terraform (IaC)
* **Container Orchestration:** Docker & Nginx
* **Automation Automation:** GitHub Actions (CI/CD)
* **Version Control:** Git & GitHub

## 🚀 Key Deployment Phases
### Phase 1: Container Packaging
A lightweight custom web environment was created and isolated using custom local parameters:
```bash
docker build -t my-first-web-app .
docker run -d -p 9000:80 --name wgu-portfolio-container my-first-web-app
```

### Phase 2: Cloud Infrastructure Setup
Automated the creation of the cloud architecture backend directly through Terraform scripts:
```hcl
resource "aws_ecr_repository" "app_repo" {
  name                 = "wgu-portfolio-app"
  image_tag_mutability = "MUTABLE"
  image_scanning_configuration { scan_on_push = true }
}
```

### Phase 3: Automated Pipeline Execution
Configured secure encrypted repository keys (`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`) inside GitHub settings to seamlessly link the automated runner to the cloud repository with zero manual file transfers.
