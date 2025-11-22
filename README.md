# VProfile Application - CI/CD Pipeline

A complete DevOps CI/CD pipeline implementation for a Java web application using Jenkins, Docker, AWS ECS, and various code quality tools.

## 🚀 Project Overview

This project demonstrates a production-ready CI/CD pipeline that automates the build, test, quality analysis, containerization, and deployment of a Java Maven application to AWS ECS.

![Pipeline Overview](./images/pipeline-overview.png)

## 🏗️ Architecture

The pipeline implements the following workflow:
- **Source Control**: Git repository integration
- **Build Automation**: Maven-based compilation and packaging
- **Quality Assurance**: Unit testing, code analysis, and quality gates
- **Containerization**: Docker image creation and registry management
- **Deployment**: Automated deployment to AWS ECS

![Architecture Diagram](./images/architecture-diagram.png)

## 🛠️ Technologies Used

- **CI/CD**: Jenkins Pipeline
- **Build Tool**: Maven 3.9
- **Runtime**: Java 17 (JDK17)
- **Code Quality**: SonarQube, Checkstyle
- **Containerization**: Docker
- **Container Registry**: AWS ECR
- **Deployment**: AWS ECS
- **Cloud Provider**: AWS

## 📋 Pipeline Stages

### 1. **Fetch Code**
- Pulls source code from GitHub repository
- Branch: `docker`
- Repository: `https://github.com/hkhcoder/vprofile-project.git`

### 2. **Build**
- Compiles the application using Maven
- Skips tests during build phase
- Archives WAR artifacts for deployment

### 3. **Unit Testing**
- Executes comprehensive unit test suite
- Validates code functionality and reliability

### 4. **Code Quality Analysis**
- **Checkstyle**: Enforces coding standards and conventions
- **SonarQube**: Performs static code analysis for bugs, vulnerabilities, and code smells

### 5. **Quality Gate**
- Enforces quality thresholds
- Blocks deployment if quality criteria are not met
- Timeout: 1 hour maximum wait

### 6. **Docker Image Build**
- Creates containerized application image
- Uses multi-stage Dockerfile for optimization
- Tags with build number and 'latest'

### 7. **Image Registry**
- Pushes Docker images to AWS ECR
- Registry: `311141533760.dkr.ecr.us-east-1.amazonaws.com/vprofileappimg`

### 8. **ECS Deployment**
- Deploys to AWS ECS cluster: `vprofileapp`
- Service: `vprofileappsvc`
- Forces new deployment for zero-downtime updates

### 9. **Cleanup**
- Removes local Docker images to free up space

![Pipeline Flow](./images/pipeline-stages.png)

## 🔧 Prerequisites

- Jenkins server with required plugins
- Maven 3.9 configured in Jenkins
- JDK 17 configured in Jenkins
- SonarQube server setup
- AWS CLI configured
- Docker installed on Jenkins agents
- AWS ECR repository created
- AWS ECS cluster and service configured

## 📊 Pipeline Results

![Build Success](./images/build-success.png)

### Quality Metrics
- **Code Coverage**: [Insert coverage percentage]
- **Technical Debt**: [Insert debt ratio]
- **Security Vulnerabilities**: [Insert count]
- **Code Smells**: [Insert count]

![SonarQube Dashboard](./images/sonarqube-dashboard.png)

## 🚀 Deployment

The application is automatically deployed to AWS ECS upon successful pipeline completion.

**Note**: This is a demonstration project - AWS resources are provisioned temporarily for testing and then torn down to avoid ongoing costs.

![Deployed Application](./images/deployed-app.png)

## 📈 Monitoring & Observability

- **Build Status**: Jenkins dashboard
- **Code Quality**: SonarQube reports
- **Application Health**: AWS ECS service monitoring
- **Container Metrics**: CloudWatch integration

![Monitoring Dashboard](./images/monitoring-dashboard.png)

## 🔐 Security Features

- AWS credentials managed through Jenkins credentials store
- ECR authentication via IAM roles
- SonarQube security vulnerability scanning
- Container image security best practices

## 📝 Configuration Files

```
├── Jenkinsfile                 # Pipeline definition
├── Docker-files/
│   └── app/
│       └── multistage/         # Multi-stage Dockerfile
├── src/                        # Application source code
└── pom.xml                     # Maven configuration
```

## 🎯 Key Achievements

- ✅ Fully automated CI/CD pipeline
- ✅ Zero-downtime deployments
- ✅ Comprehensive quality gates
- ✅ Container-based deployment
- ✅ AWS cloud integration
- ✅ Automated testing and code analysis

## 🔄 Pipeline Execution

![Pipeline Execution](./images/pipeline-execution.png)

## 📞 Contact

**Developer**: [Your Name]  
**Email**: [your.email@example.com]  
**LinkedIn**: [Your LinkedIn Profile]  
**GitHub**: [Your GitHub Profile]

---

*This project demonstrates expertise in DevOps practices, CI/CD implementation, containerization, and cloud deployment strategies.*