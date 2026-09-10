## Deployment Verification

### 1. Frontend Application

The frontend application is running on the EKS LoadBalancer.

![Frontend Application](screenshots/01-frontend-browser.png)

### 2. Kubernetes Resources

The frontend and backend pods and LoadBalancer services are running successfully.

![kubectl get all](screenshots/02-kubectl-get-all.png)

### 3. Frontend Deployment

The frontend deployment is running one available replica using the SHA-tagged ECR image.

![Frontend Deployment](screenshots/03-kubectl-describe-frontend.png)

### 4. Frontend ECR Image

The frontend Docker image is available in Amazon ECR.

![Frontend ECR Image](screenshots/04-frontend-ecr.png)
