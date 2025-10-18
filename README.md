# CI-Jenkins-Pipeline
Enterprise CI/CD Pipeline using Jenkins, Maven, SonarQube, Nexus, and Slack for automated build, test, quality analysis, and artifact management

## Project Overview

Enterprise-grade Continuous Integration and Continuous Delivery (CI/CD) pipeline implementing automated build, test, code quality analysis, and artifact management using industry-standard DevOps tools. This project demonstrates best practices for reducing Mean Time to Repair (MTTR), eliminating manual bottlenecks, and enabling rapid iteration cycles in Agile environments.

### Key Features

- **Automated Build & Test**: Maven-based build automation with integrated unit testing
- **Code Quality Analysis**: Dual-layer quality scanning using Checkstyle and SonarQube
- **Quality Gates**: Configurable quality thresholds preventing substandard code deployment
- **Artifact Management**: Versioned artifact storage in Nexus Sonatype repository
- **Real-time Notifications**: Slack integration for immediate pipeline status updates
- **Infrastructure as Code**: Terraform scripts for AWS EC2 provisioning
- **Webhook Integration**: GitHub webhook-triggered automated builds
- **Security Scanning**: SonarQube security vulnerability detection

## Architecture

The CI/CD pipeline follows this workflow:

Developer Commit → GitHub → Jenkins (Build & Test) → Checkstyle Analysis →
SonarQube Scan → Quality Gate → Maven Package → Nexus Upload → Slack Notification


### Core Components

| Component | Purpose | Port |
|-----------|---------|------|
| **Jenkins** | CI/CD orchestration server | 8080 |
| **Maven** | Build automation and dependency management | N/A |
| **Git/GitHub** | Version control system | N/A |
| **Checkstyle** | Code style validation | N/A |
| **SonarQube** | Code quality and security analysis | 9000 |
| **Nexus Sonatype** | Artifact repository manager | 8081 |
| **Slack** | Real-time notification system | N/A |
| **AWS EC2** | Infrastructure hosting platform | N/A |

## Technologies

### DevOps Tools
- Jenkins 2.x - Automation server
- Maven 3.8+ - Build tool
- Git 2.x - Version control
- SonarQube 9.x - Code quality platform
- Nexus OSS 3.x - Repository manager
- Checkstyle 10.x - Code analyzer

## Prerequisites

### Required Accounts
- AWS Account with EC2 access
- GitHub Account
- Slack Workspace (optional but recommended)

### Required Knowledge
- Basic Linux command line
- Git fundamentals
- Java application structure
- AWS EC2 basics

### Local Development Tools
- Git installed locally
- SSH client
- Text editor (VS Code recommended)
- AWS CLI (optional)

