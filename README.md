# Simple CI/CD Pipeline Implementation

A CI/CD pipeline that automates security scanning, building, testing, and deployment of a containerized application.

## Pipeline Overview

![Pipeline Overview](https://github.com/nvicuong/simple-cicd/blob/main/images/pipeline.png)

The pipeline consists of the following stages:

1. **Static Application Security Testing (SAST)**: Scans the source code for security vulnerabilities.
2. **Software Composition Analysis (SCA)**: Checks for vulnerabilities in dependencies.
3. **Build**: Compiles the application and prepares the artifact.
4. **Artifact and Registry**: Stores the built artifact and container image.
5. **Scan Image**: Performs vulnerability scanning on the container image.
6. **Deploy on K8s**: Deploys the containerized application on K8s.
7. **Dynamic Application Security Testing (DAST)**: Conducts runtime security tests.
8. **Performance Testing**: Evaluates system performance under different conditions.
9. **Report to Telegram**: Sends test results to a Telegram chat.

## Technologies Used

- **automating deployment platform**: Kubernetes
- **Git Server**: Gitlab.
- **GitOps**: Argo
- **CI/CD Tool**: GitLab CI/CD, Jenkins.
- **Security Tools**: 
  - SAST: Trivy
  - SCA: Snyk
  - Scan image: Trivy
  - DAST: Arachni
- **Containerization**: Docker
- **Container Registry**: JFrog Artifactory, Docker Hub, Habor Registry.
- **Testing**: Grafana K6 for performance testing.
- **Notification**: Telegram bot API.

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-repo/ci-cd-pipeline.git
cd ci-cd-pipeline
```

### 2. Configure CI/CD Pipeline
- Define the pipeline using .gitlab-ci.yml (for GitLab) or Jenkinsfile (for Jenkins).
- Configure security scanning tools and their integrations.
- Set up the repository in Gitlab, Jenkins
- Set up a Docker container registry.
- Implement Telegram notifications.

### 3. Environment Variables
Configure necessary environment variables in your CI/CD platform.

### 4. Running the Pipeline
- Push your code to the Git repository.
- The pipeline will trigger automatically.
- Monitor logs and test results.

### 5. Monitoring and Reporting
- View testing results on Telegram.