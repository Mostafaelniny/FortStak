# Todo List Application with CI/CD Pipeline

![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-000000?style=for-the-badge&logo=ansible&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)

A complete implementation of a Todo List application with CI/CD pipeline, containerization, automated deployment, and continuous updates.


## Project Overview

This project implements a Todo List application with the following components:
1. Dockerized Node.js application with MongoDB
2. GitHub Actions CI pipeline building and pushing Docker images
3. Ansible configuration for VM setup
4. Automated deployment with Docker Compose
5. Continuous image update mechanism
6. (Bonus) Kubernetes deployment with ArgoCD


## Technologies

- Database
  - MongoDB
- Backend
  - Node.js
  - Express
- Frontend
  - EJS
  - JS
  - CSS
- DevOps
  - Docker
  - Docker Compose
  - Ansible (VM Configuration)  
  - Kubernetes (Bonus: Container Orchestration)
 

## Features

- **Todo Management**: Create, read, update, and delete todo items
- **Containerized**: Fully dockerized application with proper health checks
- **CI Pipeline**: Automated build and push to private Docker registry
- **Infrastructure as Code**: VM provisioning with Ansible
- **Auto-Updating**: System detects and deploys new image versions
- **Health Monitoring**: Container health checks for reliability



## System Architecture

#Part (1) :
-----------
-Step 1: Clone the Node.js App: <img width="887" height="262" alt="(1) Show successful clone" src="https://github.com/user-attachments/assets/18109df8-9f72-4a3e-9928-3dab945b207c" />


-Step 2: MongoDB Setup in docker : <img width="1917" height="492" alt="(2) Container was successfully creadted and started and it is  running" src="https://github.com/user-attachments/assets/e351c5f5-baaa-4fea-ab0c-614cef1f46e4" />
                           <img width="1911" height="440" alt="(3) Successfully connected to MongoDB" src="https://github.com/user-attachments/assets/a33ca31d-ddf4-405c-89e9-0f7580672f8b" />



-Step 3: Dockerize the App 
---------------------------

1. Create a Dockerfile  :
 
   <img width="1912" height="490" alt="(4) Create a Dockerfile" src="https://github.com/user-attachments/assets/a622cffe-0710-48db-801b-ee19d244001e" />


 
 2.Add .dockerignore     : 
 
 <img width="1916" height="92" alt="4 2" src="https://github.com/user-attachments/assets/f7fccc4a-3390-4004-930f-cd2d930284c6" />


 
 3. Build the Docker Image  :
 
 <img width="1918" height="823" alt="(5) Create the Image" src="https://github.com/user-attachments/assets/9620037c-9cf4-4a75-8aac-a538a2cf098e" />



 Dockarizing done : 
 
 <img width="1065" height="257" alt="(5 1) Dockarizing done" src="https://github.com/user-attachments/assets/0cfdc3e4-2175-4dc6-b826-2a973772c5cf" />
                        




-Step 4: Run the Docker Container  :

<img width="1917" height="222" alt="(6) run the docker container" src="https://github.com/user-attachments/assets/51665b6b-1f88-4faa-98e5-bbaaddccfa65" />
                                       

-Step 5 : Test the App : 

<img width="1917" height="846" alt="(6 1) test the app" src="https://github.com/user-attachments/assets/e39fda6a-b16b-4bbb-b868-a999b1dae6f2" />



-Step 6 : GitHub Actions Workflow to Build & Push :   

<img width="1918" height="838" alt="7 1" src="https://github.com/user-attachments/assets/e538bd9b-b0c8-45fe-a20f-94caed74a0e4" />

<img width="1577" height="376" alt="(7) GitHub Actions Workflow" src="https://github.com/user-attachments/assets/9bc6e932-c63a-40bd-9830-6f1f6ab29a84" />


Step 7  : Automated Docker Deployment :
---------------------------------------
1.Build Configuration : 

<img width="1918" height="671" alt="7 99" src="https://github.com/user-attachments/assets/3828ef5c-e135-4885-8fdc-f05f9ae7624a" />

2. Execution Results  :

<img width="1577" height="337" alt="8" src="https://github.com/user-attachments/assets/3b8e7dd2-c788-40f9-8f5d-07c925adbd44" />

<img width="1427" height="336" alt="8 2" src="https://github.com/user-attachments/assets/2d6602b1-3000-46e0-bbee-25590bb4138b" />




Now we have:
1. A todo-app image pushed to Docker Hub ✅
2. A MongoDB container running ✅


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------




#Part (2) :
-----------
Goal: From my local machine, use Ansible to prepare a remote VM with Docker and Docker Compose.


1. VM Setup & Ansible Configuration
Inventory File: inventory.ini configured with my VM's IP

Ansible Playbook: docker-setup.yml created with installation tasks

<img width="1918" height="841" alt="1" src="https://github.com/user-attachments/assets/1d01c8ab-571c-47bd-96ea-67c4febc7f7b" />

<img width="731" height="63" alt="image" src="https://github.com/user-attachments/assets/3679f9e0-388f-4664-a229-c563b28382da" />


Output from running the Ansible playbook to install Docker/Docker Compose on the remote VM:

1.Installs system packages

2.Configures Docker repositories

3.Sets up user permissions




    ------------------------------------------------------------------------


2. Verification on VM

<img width="756" height="605" alt="2" src="https://github.com/user-attachments/assets/a0bd3d36-c586-42ea-8481-a53b63ee0a83" />

Post-installation verification:

Confirms Docker (20.10.24) and Docker Compose (v2.24.5) versions

Validates setup with hello-world container

    ------------------------------------------------------------------------

3. Application Deployment

<img width="1430" height="451" alt="3" src="https://github.com/user-attachments/assets/99d78710-d467-4c5e-b4fa-cd13ed299ef7" />

Running docker compose up -d:

Pulls base images (Node.js, MongoDB, Watchtower)

Ignores obsolete version field (warning)

    ------------------------------------------------------------------------


4. Running Services

<img width="1638" height="667" alt="4" src="https://github.com/user-attachments/assets/b31e7a7a-65ab-418a-8ac9-557b380710ce" />

Final deployment results:

Running Containers:

todo-app (port 4000, health check)

watchtower (auto-updater)

Network: todo-app_default created

    ------------------------------------------------------------------------



-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

##Part (3) :    Docker Compose Deployment & Auto-Updating
------------

 

 1. Docker Compose Configuration
    
<img width="1840" height="733" alt="1" src="https://github.com/user-attachments/assets/dfeab72f-75ea-4c27-9bfc-c037438b68f1" />

 
*Key components in `docker-compose.yml`:*
```yaml
services: 
  todo-app:
    image: mostafaelniny/todo-app:latest
    ports: ["3000:3000"]
    healthcheck:  # Container health monitoring
      test: ["CMD", "curl", "-f", "http://localhost:3000"]
      interval: 30s
      
  watchtower:  # Auto-updater
    image: containrrr/watchtower
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
    command: --interval 30 --cleanup
```
    ---------------------------------------------------

2. Deployment Process

<img width="2610" height="1722" alt="deepseek_mermaid_20250731_fbc413" src="https://github.com/user-attachments/assets/473e1662-2667-4cc8-8290-f3ad1bb17c2a" />

    --------------------------------------------------

3. System Architecture

[ Docker Host (VM) ]
├── todo-app (Node.js)
│   ├── Port: 4000
│   └── Health Check: HTTP 4000/
└── watchtower
    ├── Monitors: todo-app
    └── Updates: Every 30s    
    
    --------------------------------------------------
#Key Features Implemented:
✅ Health Checks - Ensures app responsiveness
✅ Auto-Updating - Watchtower monitors Docker Hub
✅ Port Mapping - Exposes app on port 4000
✅ Cleanup - Removes old images to save space    

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------





      

