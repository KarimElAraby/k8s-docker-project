# k8s-docker-small-project

This project involves setting up a KinD (Kubernetes in Docker) cluster, creating Docker containers, deploying applications to the cluster using Kubernetes manifests, and exposing services externally using NGINX Ingress.
## Project Steps

Follow the steps below to complete the project:
### 1. Set Up KinD Cluster

 Create a KinD cluster using the kind create cluster --config cluster-config.yaml command.
 Verify that the cluster is running successfully.

### 2. Docker
#### Dockerfile

 Create a Dockerfile for a simple web application that displays "Hello from <your-name>" (e.g., an Nginx server).
 Build the Docker image using the docker build command.
 Push the Docker image to a container registry.

#### Docker Containers

 Run a Docker container using the built image using the docker run command.
 Verify that the container is running and accessible.

### 3. Kubernetes
#### Deployment

 Create a Deployment YAML file for the web application, specifying the desired replicas, image, and other configurations.
 Apply the Deployment to the KinD cluster using the kubectl apply -f deployment.yaml command.
 Verify the Deployment and its Pods by checking their status using the kubectl get deployment and kubectl get pods commands.

#### Service

 Create a Service YAML file to expose the Deployment internally within the cluster, specifying the target port and selector.
 Apply the Service to the KinD cluster using the kubectl apply -f service.yaml command.
 Access the service within the cluster using the cluster IP and the specified target port.

#### Ingress

 Install the NGINX Ingress Controller on the KinD cluster using the following command:
    
 kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml

 Create an Ingress YAML file to expose the service externally, specifying the host, paths, and service backend.
 Apply the Ingress to the KinD cluster using the kubectl apply -f ingress.yaml command.
 Access the service externally using the Ingress endpoint and the specified host.

#### ConfigMap and Secret

 Create ConfigMap and Secret YAML files with sample data, specifying the key-value pairs or secrets.
 Apply the ConfigMap and Secret to the KinD cluster using the kubectl apply -f configmap.yaml and kubectl apply -f secret.yaml commands.
 Use the ConfigMap and Secret in a Deployment YAML file by referencing them in the environment variables or volume mounts.
 Deploy the Deployment to the cluster using the kubectl apply -f deployment.yaml command.

#### PersistentVolume and PersistentVolumeClaim

 Create PersistentVolume and PersistentVolumeClaim YAML files with sample configurations, specifying the storage class, access mode, and capacity.
 Apply the PersistentVolume and PersistentVolumeClaim to the KinD cluster using the kubectl apply -f pv.yaml and kubectl apply -f pvc.yaml commands.
 Mount the PersistentVolumeClaim to a Deployment by referencing it in the volume mounts section of the deployment YAML file.
 Deploy the Deployment to the cluster using the kubectl apply -f deployment.yaml command and verify the volume is correctly mounted.

