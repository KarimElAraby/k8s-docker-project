# k8s-docker-small-project-using-Nginx
This project involves setting up a KinD (Kubernetes in Docker) cluster, creating Docker containers, deploying applications to the cluster using Kubernetes manifests, and exposing services externally using NGINX Ingress.

## Project Steps
  Follow the steps below to complete the project:

### 1. Set Up KinD Cluster

 1- Create a KinD cluster using the kind create cluster --config cluster-config.yaml command.
 
 2- Verify that the cluster is running successfully.

### 2. Docker
#### Dockerfile

 1- Create a Dockerfile for a simple web application that displays "Hello from <your-name>" (e.g., an Nginx server).
 
 2- Build the Docker image using the docker build command.
 
 ![Screenshot from 2024-04-26 17-02-12](https://github.com/KarimElAraby/k8s-docker-small-project/assets/137705973/921851ed-c2c3-4cf5-b367-507bb62f3f40)

 3- Push the Docker image to a container registry.

![Screenshot from 2024-04-26 17-02-25](https://github.com/KarimElAraby/k8s-docker-small-project/assets/137705973/104b547f-d021-4c77-8429-13d887417a6a)

#### Docker Containers

 1- Run a Docker container using the built image using the docker run command.

![Screenshot from 2024-04-26 17-13-36](https://github.com/KarimElAraby/k8s-docker-small-project/assets/137705973/e4559f16-62c2-427e-99e5-c33e91eb4b79)
 
 2- Verify that the container is running and accessible.
 
 ![Screenshot from 2024-04-26 17-14-39](https://github.com/KarimElAraby/k8s-docker-small-project/assets/137705973/6d9174aa-3048-4e23-a263-33da627242e0)

### 3. Kubernetes

#### ConfigMap and Secret

 1- Create ConfigMap and Secret YAML files with sample data, specifying the key-value pairs or secrets.
 
 2- Apply the ConfigMap and Secret to the KinD cluster using the kubectl apply -f configmap.yaml and kubectl apply -f secret.yaml commands.
 
 3-Use the ConfigMap and Secret in a Deployment YAML file by referencing them in the environment variables or volume mounts.

 ![Screenshot from 2024-05-04 04-01-00](https://github.com/KarimElAraby/k8s-docker-small-project/assets/137705973/f3508dcc-3c45-4791-98b8-1e7fdccc803e)
 ![Screenshot from 2024-05-04 04-01-11](https://github.com/KarimElAraby/k8s-docker-small-project/assets/137705973/1c76bd24-d520-4575-8b42-6600ed1fa3c8)

 #### PersistentVolume and PersistentVolumeClaim

 1- Create PersistentVolume and PersistentVolumeClaim YAML files with sample configurations, specifying the storage class, access mode, and capacity.
 
 2- Apply the PersistentVolume and PersistentVolumeClaim to the KinD cluster using the kubectl apply -f pv.yaml and kubectl apply -f pvc.yaml commands.
 
 3- Mount the PersistentVolumeClaim to a Deployment by referencing it in the volume mounts section of the deployment YAML file.

![Screenshot from 2024-05-04 04-02-21](https://github.com/KarimElAraby/k8s-docker-small-project/assets/137705973/e7ab07fb-bc31-46cc-8f4c-5f204e8c7bf8)


#### Deployment

 1- Create a Deployment YAML file for the web application, specifying the desired replicas, image, and other configurations.
 
 2- Apply the Deployment to the KinD cluster using the kubectl apply -f deployment.yaml command.
 
 3- Verify the Deployment and its Pods by checking their status using the kubectl get deployment and kubectl get pods commands.

 ![Screenshot from 2024-05-04 04-02-42](https://github.com/KarimElAraby/k8s-docker-small-project/assets/137705973/e8ce8143-276e-4e50-8819-f799e899aa36)


#### Service

 1- Create a Service YAML file to expose the Deployment internally within the cluster, specifying the target port and selector.
 
 2- Apply the Service to the KinD cluster using the kubectl apply -f service.yaml command.
 
 3- Access the service within the cluster using the cluster IP and the specified target port.
 
![Screenshot from 2024-05-04 04-03-11](https://github.com/KarimElAraby/k8s-docker-small-project/assets/137705973/6a7daad7-c6fc-4657-a911-85dc4a71ca03)


#### Ingress

 1- Install the NGINX Ingress Controller on the KinD cluster using the following command:  
     kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml

 2- Create an Ingress YAML file to expose the service externally, specifying the host, paths, and service backend.
 
 3- Apply the Ingress to the KinD cluster using the kubectl apply -f ingress.yaml command.
 
 4- Access the service externally using the Ingress endpoint and the specified host.

![Screenshot from 2024-05-02 16-58-21](https://github.com/KarimElAraby/k8s-docker-small-project/assets/137705973/d89100cf-2270-4d20-9387-e2846e3a783c)

![Screenshot from 2024-05-02 17-02-31](https://github.com/KarimElAraby/k8s-docker-small-project/assets/137705973/acc6a37b-4922-4d99-84b7-b38ae9adaf56)

