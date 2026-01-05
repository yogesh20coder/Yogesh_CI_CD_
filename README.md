**AWS CI/CD Pipeline with Jenkins, Docker, and Terraform
This project demonstrates a fully automated CI/CD pipeline. It provisions AWS infrastructure using Terraform, configures a Jenkins server, and automates the deployment of a Java 17 application inside Docker containers.**

├── terraform/          # Infrastructure files (.tf)
├── src/                # Java Application source code
├── Dockerfile          # Container configuration
├── Jenkinsfile         # CI/CD Pipeline script
└── README.md

Architecture
Infrastructure as Code: Terraform scripts to deploy an EC2 instance and configure Security Groups.

CI/CD Orchestration: Jenkins installed on EC2, integrated with GitHub via Webhooks.
Containerization: A Java application packaged using Docker.
Deployment: Automated build and push to Docker Hub/Local Registry and deployment to a production-ready environment.

🛠 Prerequisites
AWS Account & CLI configured.
Terraform installed.
GitHub Repository for your source code.

1. Infrastructure Provisioning
Navigate to the terraform/ directory and run:

Note: This creates an EC2 instance and opens ports 22 (SSH), 8080 (Jenkins), and 80 (App).
2. Jenkins Setup & Troubleshooting
Once the instance is live, access Jenkins at http://<EC2-IP>:8080.
Crucial Step: Docker Permissions To allow Jenkins to run Docker commands without sudo, run the following on your EC2:
sudo usermod -aG docker jenkins
sudo systemctl restart jenkins

3. Pipeline Configuration
Create a Pipeline Project in Jenkins.
Link your GitHub Repository.
Add your Docker Hub credentials to the Jenkins Credentials Store.
Use the provided Jenkinsfile in this repo.
