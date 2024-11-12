# Node.js Application with Kubernetes Deployment

This repository contains a simple Node.js application that is containerized with Docker and deployed using Kubernetes. The project is designed to demonstrate the use of Kubernetes Deployments and Services to manage application lifecycle, scaling, and availability.

## Project Structure
- **`server.js`**: The main Node.js server script.
- **`Dockerfile`**: Docker configuration to build the image of the Node.js application.
- **`node-app-deployment.yaml`**: Kubernetes Deployment configuration for managing the Node.js application pods.
- **`node-app-service.yaml`**: Kubernetes Service configuration to expose the application and distribute traffic.

## Features
- **Containerized Node.js App**: A basic Express.js application running in a Docker container.
- **Kubernetes Deployment**: Ensures the application runs in a set of pods, maintains high availability, and automates updates and rollbacks.
- **Scaling**: Supports horizontal scaling to manage high traffic loads.
- **Load Balancing**: The Kubernetes Service balances traffic among pods, enhancing resilience and availability.

## Prerequisites
Ensure you have the following installed and configured on your system:
- **Node.js** and **npm**
- **Docker**
- A running **Kubernetes cluster** (e.g., Minikube, Docker Desktop, or cloud-based)
- **kubectl** configured to access your Kubernetes cluster

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/node-app-k8s.git
cd node-app-k8s
```

### 2. Build the Docker Image
```bash
docker build -t node-app .
```

### 3. Deploy to Kubernetes
Apply the Deployment configuration:
```bash
kubectl apply -f node-app-deployment.yaml
```

### 4. Expose the Application
Apply the Service configuration:
```bash
kubectl apply -f node-app-service.yaml
```

### 5. Verify the Deployment
Check if the pods are running:
```bash
kubectl get pods
```
Verify the service and get the external IP (if applicable):
```bash
kubectl get svc
```

## Usage
Visit `http://<external-ip>` in your web browser to access the running application.

## Scaling the Deployment
To scale the deployment to 5 replicas:
```bash
kubectl scale deployment node-app-deployment --replicas=5
```

## License
This project is licensed under the MIT License. You are free to use, modify, and distribute this project as per the license terms.

## Contributing
Contributions are welcome! Feel free to open issues or submit pull requests.

## Contact
For any questions or suggestions, feel free to reach out or create an issue in this repository.
