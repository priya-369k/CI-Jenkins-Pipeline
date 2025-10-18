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


## Pipeline Stages

### Stage 1: Code Checkout
- Fetches latest code from GitHub repository
- Validates webhook signature

### Stage 2: Build & Unit Test
- Maven compiles source code
- Executes unit tests
- Generates test reports

### Stage 3: Code Quality Analysis
- **Checkstyle**: Validates coding standards
- **SonarQube**: Deep security and quality analysis
- Publishes results to SonarQube dashboard

### Stage 4: Quality Gate Evaluation
- Checks if code meets quality thresholds
- Pipeline fails if quality gate criteria not met

### Stage 5: Artifact Packaging
- Maven packages application (JAR/WAR)
- Generates version identifier with build number

### Stage 6: Nexus Upload
- Uploads artifact to Nexus repository
- Stores metadata (commit hash, timestamp, version)

### Stage 7: Notification
- Sends Slack notification with build status
- Includes links to logs and reports
## Key Skills Demonstrated

### DevOps Engineering
- CI/CD pipeline development and optimization
- Infrastructure automation with Terraform
- Configuration management and orchestration
- Artifact lifecycle management

### Quality Assurance
- Automated testing integration
- Code quality gate implementation
- Security vulnerability scanning
- Technical debt monitoring

### Cloud Infrastructure
- AWS EC2 instance provisioning
- Security group configuration
- IAM role management
- Cost-optimized infrastructure design

### Tools & Technologies
- Jenkins pipeline scripting (Declarative/Scripted)
- Maven build lifecycle management
- SonarQube quality profile customization
- Nexus repository administration
- Git workflow automation
- Slack API integration

## Performance Metrics

- **Build Time**: ~3-5 minutes per build
- **Mean Time to Repair (MTTR)**: Reduced from hours to minutes
- **Deployment Frequency**: Multiple deployments per day
- **Quality Gate Pass Rate**: >90%
- **Code Coverage**: >80% maintained


## Troubleshooting

### Common Issues

**Issue**: Webhook not triggering builds
- **Solution**: Verify Jenkins URL is publicly accessible; check security group rules

**Issue**: Quality gate timeout
- **Solution**: Increase timeout in Jenkinsfile; verify SonarQube webhook configuration

**Issue**: Nexus upload authentication failure
- **Solution**: Regenerate credentials; verify deployment user permissions


## Best Practices Implemented

- **Fail Fast**: Early detection of issues at commit stage
- **Automated Testing**: Zero manual testing intervention
- **Quality Gates**: Enforced quality standards
- **Versioned Artifacts**: Traceable deployments
- **Immediate Feedback**: Real-time notifications
- **Security Scanning**: Vulnerability detection before production

## Future Enhancements

- [ ] Kubernetes deployment integration
- [ ] Container image building with Docker
- [ ] Automated security scanning with OWASP Dependency-Check
- [ ] Performance testing with JMeter
- [ ] Multi-branch pipeline support
- [ ] Blue-green deployment strategy



