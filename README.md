# React CI/CD Pipeline using Jenkins and Docker

This project demonstrates a complete CI/CD pipeline for a React application using Jenkins, Docker, and Docker Hub. The pipeline automatically builds the application, creates a Docker image, pushes it to Docker Hub, and deploys it on a Jenkins-hosted EC2 instance.

## 🛠️ Tech Stack

- **React.js** (Frontend)
- **Docker** (Containerization)
- **Jenkins** (CI/CD pipeline)
- **Docker Hub** (Image Registry)
- **AWS EC2** (Deployment server)
- **GitHub** (Source Code Management)
---
## 📁 Repository Structure

.
├── Jenkinsfile # Jenkins pipeline definition
├── README.md # Project documentation
├── build.sh # Shell script to build, run, and push Docker image
├── dockerfile # Dockerfile to build the application image
├── package.json # Project metadata and dependencies
├── package-lock.json # Dependency tree lock file
└── <React app source files>

---

## 🚀 What the Pipeline Does

1. **Triggers on Git Push** – The pipeline is triggered automatically when changes are pushed to the GitHub repository.
2. **Jenkins Pipeline Execution**
   - Grants execute permission to `build.sh`
   - Executes the `build.sh` script to:
     - Log in to Docker Hub
     - Build the React app
     - Create and run the Docker container
     - Push the image to Docker Hub
3. **Deployment** – The app is served using an Nginx container on the EC2 instance and is accessible via its public IP.

--- 

🌐 Accessing the Application
Once the Jenkins job runs successfully, the application is deployed and accessible via the public IP of your EC2 instance on port 80:

http://<EC2-Public-IP>

🔄 CI/CD Automation Summary
Auto Trigger: Push to GitHub triggers Jenkins job
Jenkins: Clones repo → Runs pipeline → Executes Docker build and deployment
Docker Hub: Stores latest image with tag ci-cd
EC2: Hosts running container accessible via browser

✅ Prerequisites
Docker installed on Jenkins EC2 instance
Jenkins with Git and Docker plugins installed
GitHub repo connected to Jenkins job
Docker Hub credentials set in Jenkins (environment variables or credentials plugin)

![image pushed to dockerhub](https://github.com/user-attachments/assets/d88028bc-4cb2-4fc4-b58b-a4ee4fb40485)

![Jenkin pipeline automation](https://github.com/user-attachments/assets/509bffc6-c26c-4947-9993-b8f7d780f576)


