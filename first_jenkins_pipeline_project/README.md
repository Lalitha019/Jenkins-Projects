# Jenkins Docker Pipeline Project

## Overview

This project demonstrates a basic Continuous Integration (CI) pipeline using Jenkins, Docker, and GitHub. The objective is to understand how Jenkins can automatically fetch source code from a GitHub repository, execute pipeline stages, interact with Docker containers, and perform build validation.

As part of this project, Jenkins is configured to pull the source code from GitHub, execute a pipeline defined in a Jenkinsfile, launch a Docker container using the Node.js image, and verify the installation by printing the Node.js version.

This project serves as a foundation for learning CI/CD concepts and understanding how modern DevOps pipelines automate software build and deployment processes.

---

## Technologies Used

* Jenkins
* Docker
* Git & GitHub
* AWS EC2 (Ubuntu)
* Node.js Docker Image

---

## Project Architecture

GitHub Repository
↓
Jenkins Pipeline
↓
Docker Container
↓
Execute Commands
↓
Display Node.js Version

---

## Pipeline Workflow

1. Source code is stored in a GitHub repository.
2. Jenkins is configured to connect to the repository.
3. Jenkins reads the Jenkinsfile.
4. A Docker container is created using the Node.js image.
5. The pipeline executes commands inside the container.
6. Node.js version is displayed in the Jenkins console output.
7. Build status is generated as Success or Failure.

---

## Jenkinsfile

The Jenkinsfile contains the pipeline definition and stages required to execute the build process inside a Docker container.

Example objective:

* Pull Node.js Docker image
* Create Docker container
* Execute Node version command
* Display output in Jenkins console

---

## Learning Outcomes

Through this project, I gained hands-on experience in:

* Setting up Jenkins on AWS EC2
* Installing and configuring Docker
* Integrating GitHub with Jenkins
* Creating and managing Jenkins Pipelines
* Writing Declarative Pipeline scripts
* Executing commands inside Docker containers
* Understanding CI/CD fundamentals
* Troubleshooting Jenkins, Docker, and permission-related issues

---

## Future Enhancements

* Integrate automated testing stages
* Build and push Docker images to Docker Hub
* Implement webhook-based triggers
* Add deployment stages
* Integrate with Kubernetes for container orchestration

---

## Author

Lalitha Mahalakshmi

DevOps Learning Project – Jenkins Zero to Hero Journey
