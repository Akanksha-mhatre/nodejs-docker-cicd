# Node.js Docker CI/CD Pipeline

## Project Overview

This project demonstrates how to automate the build and deployment process of a Node.js web application using Docker and GitHub Actions.

The application is containerized using Docker, and a GitHub Actions CI/CD pipeline automatically tests the application, builds the Docker image, and pushes the image to GitHub Container Registry.

## Technologies Used

- Node.js
- Express.js
- Docker
- GitHub
- GitHub Actions
- GitHub Container Registry (GHCR)

## Application

The application is a simple Node.js web server.

### Health Check

The application provides a health-check endpoint:

`/health`

which returns:

```json
{
  "status": "healthy"
}
Docker
The application is packaged into a Docker image using the included Dockerfile.
The Docker container runs the Node.js application on port 3000.
To run the application locally:
docker build -t nodejs-demo-app .
docker run -d -p 3000:3000 --name nodejs-container nodejs-demo-app
The application can then be accessed at:
http://localhost:3000
CI/CD Pipeline
The GitHub Actions workflow is located at:
.github/workflows/main.yml
The pipeline is triggered whenever code is pushed to the main branch.
Pipeline Flow
Developer pushes code
        ↓
GitHub Actions
        ↓
Checkout source code
        ↓
Set up Node.js
        ↓
Install dependencies
        ↓
Run tests
        ↓
Build Docker image
        ↓
Login to GitHub Container Registry
        ↓
Push Docker image to GHCR

GitHub Container Registry
The Docker image is automatically published to GitHub Container Registry after a successful workflow run.
Result
This project demonstrates a basic CI/CD automation process where code changes pushed to GitHub automatically trigger testing, Docker image creation, and image publishing.

## Task 2: Jenkins CI/CD Pipeline

### Objective
Created a Jenkins pipeline to automate the build, test, and deployment of a Node.js application using Docker.

### Tools Used
- Jenkins
- Docker
- GitHub
- Node.js
- Git

### Pipeline Stages
1. Checkout SCM
2. Install Dependencies
3. Test
4. Build Docker Image
5. Deploy

### Pipeline Workflow

GitHub Commit
↓
Jenkins SCM Polling
↓
Checkout Source Code
↓
Install Dependencies
↓
Run Tests
↓
Build Docker Image
↓
Deploy Application

### Automatic Trigger
Jenkins was configured with Poll SCM:

H/5 * * * *

This checks the GitHub repository for new commits and automatically starts the pipeline when a change is detected.

### Result
The Jenkins pipeline completed successfully with all stages passing:

- Checkout SCM ✅
- Install Dependencies ✅
- Test ✅
- Build Docker Image ✅
- Deploy ✅

Build #7 was automatically started by an SCM change.

Author
Akanksha Mhatre

