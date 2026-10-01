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

Author
Akanksha Mhatre
