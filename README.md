# VProfile Application - CI/CD Pipeline

A complete DevOps CI/CD pipeline implementation for a Java web application using Jenkins, Docker, AWS ECS, and various code quality tools.

## 🚀 Project Overview

This project demonstrates a production-ready CI/CD pipeline that automates the build, test, quality analysis, containerization, and deployment of a Java Maven application to AWS ECS.


## 🏗️ Architecture

The pipeline implements the following workflow:
- **Source Control**: Git repository integration
- **Build Automation**: Maven-based compilation and packaging
- **Quality Assurance**: Unit testing, code analysis, and quality gates
- **Containerization**: Docker image creation and registry management
- **Deployment**: Automated deployment to AWS ECS

![Architecture Diagram]
<img width="1248" height="626" alt="diagram-export-11-22-2025-2_48_46-PM" src="https://github.com/user-attachments/assets/5e66ab3c-c698-492c-b1cf-7a87009b711e" />


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

![Build Success]
![jenkins](https://github.com/user-attachments/assets/3931e955-dd83-4b4f-8eed-5833643752f9)


### Quality Metrics
- **Code Coverage**: 0.0% (540 lines to cover)
- **Technical Debt**: 8 days 5 hours
- **Security Vulnerabilities**: 0
- **Code Smells**:746

![SonarQube Dashboard]
<img width="775" height="376" alt="image" src="https://github.com/user-attachments/assets/ad18d577-58ba-44e7-a557-bd34377a8509" />


## 🚀 Deployment

The application is automatically deployed to AWS ECS upon successful pipeline completion.

**Note**: This is a demonstration project - AWS resources are provisioned temporarily for testing and then torn down to avoid ongoing costs.

![Deployed Application]
<img width="947" height="473" alt="image" src="https://github.com/user-attachments/assets/9749ddf9-33e2-47c0-8692-8fbac10ccc0f" />


## 📈 Monitoring & Observability

- **Build Status**: Jenkins dashboard
- **Code Quality**: SonarQube reports
- **Application Health**: AWS ECS service monitoring
- **Container Metrics**: CloudWatch integration

![Monitoring Dashboard]
<img width="776" height="350" alt="image" src="https://github.com/user-attachments/assets/a5be39a1-78b5-4655-abf1-a3790f2de455" />


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

**Developer**:Emmanuel Frimpong Kyei-Baffour  
**Email**: baffouremmanuel1997@gmail.com  
**LinkedIn**: www.linkedin.com/in/emmanuelfrimpongkyei-baffour  
**GitHub**: BHAGWAN-KBEF

---

*This project demonstrates expertise in DevOps practices, CI/CD implementation, containerization, and cloud deployment strategies.*
