# 🎮 Gaming Leaderboard on AWS

A serverless API project that tracks and displays player high scores. This project leverages AWS Lambda for compute, Amazon DynamoDB for data storage, API Gateway for routing, and CloudWatch for logging/monitoring. It integrates with Jenkins for CI/CD automation and Ansible for additional configuration management. The entire infrastructure can be provisioned with Terraform for a reproducible, version-controlled setup.

## 📑 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
  - [Terraform Setup](#terraform-setup)
  - [Jenkins CI/CD Pipeline](#jenkins-cicd-pipeline)
  - [Ansible Integration](#ansible-integration)
- [Usage](#usage)
- [Benefits](#benefits)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This project implements a Gaming Leaderboard API on AWS using a serverless architecture. The API tracks player high scores, storing the data in DynamoDB and exposing endpoints via API Gateway. CloudWatch handles logging and monitoring, while Jenkins automates testing and deployment through a CI/CD pipeline. Ansible playbooks provide additional configuration, and Terraform is used to provision the complete AWS infrastructure.

## ⭐ Features

- **🚀 Serverless Architecture:** Utilizes AWS Lambda to handle API requests without managing servers
- **💾 Scalable Data Storage:** Leverages Amazon DynamoDB (free tier eligible) for storing player scores
- **🔄 API Routing:** Configured using AWS API Gateway for seamless HTTP request routing
- **📊 Logging & Monitoring:** Integrated with CloudWatch to capture logs and performance metrics
- **⚡ CI/CD Automation:** Jenkins pipeline for continuous integration, running tests, and deploying Lambda code
- **🔧 Infrastructure Automation:** Terraform provisions the AWS resources, with Ansible managing post-deployment configurations
- **🔄 Reproducible Environments:** Infrastructure as Code (IaC) ensures that your setup can be version-controlled and easily replicated

## 🏗 Architecture

The core AWS components for this project include:

- **⚡ AWS Lambda:** Executes the API logic in a serverless manner
- **💾 Amazon DynamoDB:** Stores the high score data
- **🔀 API Gateway:** Routes API calls to the appropriate Lambda functions
- **📈 CloudWatch:** Monitors application logs and performance
- **🔄 CI/CD Pipeline (Jenkins):** Automates testing and deployment workflows
- **⚙️ Configuration Management (Ansible):** Automates infrastructure configuration tasks
- **🏗 Infrastructure Provisioning (Terraform):** Defines and manages the AWS environment in a version-controlled manner

## 📋 Prerequisites

Before you begin, ensure you have the following:

- An active **AWS Account** with appropriate permissions
- **Terraform** installed and configured with your AWS credentials
- **Jenkins** set up for CI/CD operations
- **Ansible** installed for running playbooks
- **AWS CLI** installed and configured
- **Git** to clone the repository
- A suitable runtime environment for your Lambda functions (e.g., Node.js, Python)

## 🚀 Getting Started

### 🏗 Terraform Setup

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/gaming-leaderboard-aws.git
   cd gaming-leaderboard-aws
   ```

2. **Initialize Terraform:**
   ```bash
   terraform init
   ```

3. **Plan and Apply the Configuration:**
   ```bash
   terraform plan
   terraform apply
   ```
   This will provision your AWS Lambda, DynamoDB, API Gateway, and CloudWatch configurations as defined in the Terraform files.

### 🔄 Jenkins CI/CD Pipeline

1. **Configure Jenkins:**
   - Set up a Jenkins job that triggers on repository changes
   - In your Jenkinsfile (or pipeline configuration), define stages such as:
     - **Stage 1:** Code linting and unit tests
     - **Stage 2:** Package the Lambda function and deploy using AWS CLI commands
   
2. **Pipeline Example Overview:**
   - **Stage 1:** Run tests to ensure code quality
   - **Stage 2:** Automatically package and deploy the updated Lambda function

3. **Integrate AWS Credentials:**
   - Ensure that Jenkins has the necessary AWS credentials, either through environment variables or a credentials plugin

### ⚙️ Ansible Integration

1. **Run Ansible Playbooks:**
   - Use Ansible to further configure your API Gateway settings and DynamoDB tables after Terraform provisions the base infrastructure
   - Execute the playbook with:
     ```bash
     ansible-playbook -i inventory/hosts configure-infra.yml
     ```

2. **Purpose of Ansible:**
   - Automates additional configuration tasks
   - Ensures that infrastructure settings remain consistent and reproducible

## 🎮 Usage

- **API Endpoints:**
  - After deployment, the API Gateway will provide endpoints for retrieving and updating high scores
  
- **Monitoring:**
  - View logs and performance metrics in CloudWatch
  
- **CI/CD:**
  - Changes pushed to the repository trigger the Jenkins pipeline, which runs tests and deploys updates automatically

## 💫 Benefits

- **📝 Reproducibility:** Terraform ensures that your infrastructure can be version-controlled and replicated
- **🤖 Automation:** Jenkins and Ansible automate testing, deployment, and configuration, minimizing manual tasks
- **💰 Cost-Effectiveness:** Leverages AWS free-tier resources where possible
- **📈 Scalability:** A serverless design that scales automatically with demand
- **⏪ Quick Rollbacks:** Versioned infrastructure and automated deployment pipelines facilitate rapid recovery from issues

## 🤝 Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. For major updates or changes, please open an issue first to discuss your ideas.

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Happy coding! 🚀✨
