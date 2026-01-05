This project demonstrates a fully automated CI/CD pipeline that provisions AWS infrastructure using Terraform, configures a Jenkins server, and builds & deploys a Java 17 application inside Docker containers.

├── terraform/          # Terraform infrastructure files (.tf)
├── src/                # Java 17 application source code
├── Dockerfile          # Docker image configuration
├── Jenkinsfile         # Jenkins CI/CD pipeline script
└── README.md           # Project documentation



Architecture Overview
1️⃣ Infrastructure as Code (IaC)
AWS resources are provisioned using Terraform
Creates:
EC2 instance for Jenkins
Security Groups
Opened ports:
22 – SSH
8080 – Jenkins
80 – Application access

2️⃣ CI/CD Orchestration (Jenkins)

Jenkins is installed on an EC2 instance
Integrated with GitHub using Webhooks
Pipeline stages include:
Source code checkout
Build
Docker image creation
Deployment

3️⃣ Containerization (Docker)

Java 17 application is packaged into a Docker image
Image is:
Built during pipeline execution
Pushed to Docker Hub or a local registry
Deployed automatically
