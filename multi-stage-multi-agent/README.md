# Multi-Stage Multi-Agent Jenkins Pipeline

## Overview

This project demonstrates how Jenkins can execute multiple stages using different Docker agents within a single pipeline.

The pipeline is configured with `agent none`, allowing each stage to define its own execution environment. Jenkins dynamically pulls and launches the required Docker image for every stage and executes the specified commands inside the corresponding container.

This approach enables different technology stacks to be tested and validated within the same CI/CD pipeline without installing all dependencies directly on the Jenkins server.

---

## Technologies Used

* Jenkins
* Docker
* GitHub
* AWS EC2 (Ubuntu)
* Maven
* Node.js

---

## Project Architecture

GitHub Repository

↓

Jenkins Pipeline

↓

Stage 1 (Backend)

Docker Agent: Maven

↓

Execute Maven Commands

↓

Stage 2 (Frontend)

Docker Agent: Node.js

↓

Execute Node.js Commands

↓

Pipeline Completion

---

## Pipeline Configuration

### Global Agent

```groovy
agent none
```

No default execution environment is assigned to the entire pipeline.

Each stage defines its own Docker container.

### Backend Stage

```groovy
stage('Back-end') {
    agent {
        docker {
            image 'maven:3.8.1-adoptopenjdk-11'
        }
    }

    steps {
        sh 'mvn --version'
    }
}
```

This stage:

* Pulls Maven Docker image
* Creates a temporary container
* Executes Maven version command
* Removes container after execution

---

### Frontend Stage

```groovy
stage('Front-end') {
    agent {
        docker {
            image 'node:16-alpine'
        }
    }

    steps {
        sh 'node --version'
    }
}
```

This stage:

* Pulls Node.js Docker image
* Creates a temporary container
* Executes Node version command
* Removes container after execution

---

## Execution Flow

The stages execute sequentially:

1. Jenkins starts the pipeline.
2. Backend stage launches Maven container.
3. Maven commands are executed.
4. Maven container is stopped.
5. Frontend stage launches Node.js container.
6. Node.js commands are executed.
7. Pipeline completes successfully.

### Important Note

Even though multiple Docker images are used, Jenkins executes the stages one by one by default.

The Maven and Node.js containers do not run simultaneously unless the pipeline is explicitly configured with parallel stages.

---

## Learning Outcomes

Through this project, I learned:

* Multi-stage Jenkins pipelines
* Stage-level Docker agents
* Dynamic Docker container creation
* Running different technology stacks in a single pipeline
* Jenkins Declarative Pipeline syntax
* Containerized build environments
* CI/CD pipeline design principles
* Docker and Jenkins integration

---

## Author

Lalitha Mahalakshmi

DevOps Learning Project – Jenkins Multi-Stage Multi-Agent Pipeline
