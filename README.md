# project_infrastructure_k8s
This repository contains the infrastructure setup and deployment scripts for the Awesome Cats application, comprising both the frontend and backend components. The deployment leverages Docker, Kubernetes, NGINX Ingress, and various GCP services to ensure a scalable and reliable environment.

## Infrastructure Details

1. **Database**:
   - **Service**: Google Cloud SQL
   - **Type**: PostgreSQL
   - **Setup**: Instance creation, database and table setup

2. **Secrets Management**:
   - **Tool**: Kubernetes Secrets
   - **Contents**: Database hostname, username, password, and database name

3. **Code Repositories**:
   - **Backend**: [awesome_cats_backend](https://github.com/AntTechLabs/awesome_cats_backend.git)
   - **Frontend**: [awesome_cats_frontend](https://github.com/AntTechLabs/awesome_cats_frontend.git)

## Docker

- **Frontend Dockerfile**: Configuration for building the frontend image
- **Backend Dockerfile**: Configuration for building the backend image

## Continuous Integration / Continuous Deployment (CI/CD)

- **Container Registry**: Google Container Registry (GCR)
- **Image Push**: Automated push of Docker images to the private container registry

## Kubernetes Deployment

1. **Deployments**:
   - **Backend**: 2 replicas, environment variables set for database credentials
   - **Frontend**: 2 replicas

2. **Services**:
   - **Type**: ClusterIP
   - **Purpose**: Internal communication between frontend and backend

3. **Ingress Controller**:
   - **Tool**: NGINX Ingress Controller
   - **Load Balancer**: Configuration for external access

## DNS and TLS

1. **DNS**:
   - **Service**: Google Cloud DNS
   - **Tool**: ExternalDNS for automatic DNS record management

2. **TLS Certificates**:
   - **Tool**: cert-manager
   - **Purpose**: Automated issuance and renewal of SSL certificates

## Steps for Deployment

1. **Create and Configure Database**:
   - Set up a CloudSQL instance
   - Connect and create necessary tables

2. **Manage Secrets**:
   - Store database credentials using Kubernetes Secrets

3. **Clone Repositories**:
   - `git clone https://github.com/AntTechLabs/awesome_cats_backend.git`
   - `git clone https://github.com/AntTechLabs/awesome_cats_frontend.git`

4. **Build and Push Docker Images**:
   - Write and use Dockerfiles to build images
   - Push images to GCR

5. **Deploy Applications to Kubernetes**:
   - Write and apply YAML files for backend and frontend deployments
   - Create ClusterIP services

6. **Configure Ingress and DNS**:
   - Install NGINX Ingress Controller
   - Create ingress resources
   - Configure ExternalDNS for automatic DNS management

7. **Set Up TLS Certificates**:
   - Install cert-manager
   - Obtain certificates for your domain

## Conclusion

This setup ensures a robust, scalable, and secure environment for the Awesome Cats application. The use of Kubernetes for orchestration, along with managed services for database and DNS, provides a streamlined deployment process and simplifies ongoing maintenance.