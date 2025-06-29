CLO835 – Assignment 2
This repository contains Kubernetes manifests used to deploy a containerized MySQL database and a web application on a single-node kind cluster running inside an EC2 instance.

📁 Files
File	Description
namespace.yaml	Creates the web and mysql namespaces
mysql-deployment.yaml	MySQL Deployment with ClusterIP service
web-deployment.yaml	Web app Deployment with NodePort service (port 30000)
mysql-rs.yaml	MySQL ReplicaSet (used for testing)
web-rs.yaml	Web app ReplicaSet (used for testing)
🚀 Deployment Steps
Run the following commands inside your EC2 instance:

Create namespaces:
kubectl apply -f namespace.yaml

Deploy MySQL:
kubectl apply -f mysql-deployment.yaml

Deploy web app:
kubectl apply -f web-deployment.yaml

Access your app from:
curl http://localhost:30000
or from browser: http://<EC2_PUBLIC_IP>:30000

🌐 Service Types Explained
MySQL uses ClusterIP because it's accessed only within the cluster.

Web App uses NodePort to allow access from outside the cluster via EC2's public IP.

📦 Tools Used
Docker & Amazon ECR (for building and storing images)

kind (to run Kubernetes cluster inside Docker)

kubectl (to deploy and manage K8s resources)

Git & GitHub (for version control)
