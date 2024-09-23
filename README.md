# ABOUT K8s
Kubernetes, often abbreviated as K8s, is an open-source platform for automating the deployment, scaling, and management of containerized applications. But Kubernetes is more than just a container orchestrator. It could be thought of as the operating system for cloud-native applications in the sense that it’s the platform that applications run on, just as desktop applications run on MacOS, Windows, or Linux. It aims to reduce the burden of orchestrating underlying compute, network, and storage infrastructure, and enable application operators and developers to focus entirely on container-centric workflows for self-service operation.

**Main Function/Usage:-** Kubernetes manages containers, which package an application and its dependencies together to ensure it runs consistently across different environments. Containers are isolated units but lightweight compared to virtual machines.

# NODE 
A Node is the fundamental worker machine in a Kubernetes cluster. It can be either a physical machine or a virtual machine in a cloud environment. Each node runs the necessary services to support the containers it hosts, such as the container runtime (e.g., Docker), the Kubelet (which communicates with the Kubernetes control plane), and Kube-proxy (which manages networking for the pods).

**TYPES OF NODES**

1. Master Node- The master node is the brain of the Kubernetes cluster and handles scheduling, maintaining the desired state, and managing resources. It contains components like API Server,Scheduler,Controller Manager

2. Worker  Node- Worker nodes are the machines where application workloads run. These nodes run the containers and host the pods that make up an application. They handle the execution of the actual tasks, networking, and storage management.

# PODS
A Pod is the smallest and most basic deployable unit in Kubernetes (K8s). It represents a single instance of a running process in your cluster and can contain one or more containers that share the same network and storage resources. Typically, pods are used to run a single container, but there are cases where multiple containers need to work together closely, and in these cases, a pod will contain multiple tightly coupled containers.


# Kubernetes Architecture 
A Kubernetes environment consists of a control plane (master), a distributed storage system for keeping the cluster state consistent (etcd), and a number of cluster nodes (Kubelets). 


![image alt](https://platform9.com/wp-content/uploads/2019/05/kubernetes-constructs-concepts-architecture.jpg)

# About Minikube 
Minikube is a lightweight tool that allows you to run a Kubernetes (K8s) cluster locally on your machine. It is designed for development and testing purposes. Minikube runs a single-node Kubernetes cluster inside a virtual machine (VM) on your local machine or directly in containers (on systems with containerization support). It provides the full Kubernetes functionality, allowing you to test and develop containerized applications without requiring a remote or cloud infrastructure.


**SINGLE NODE CLUSTER**

A single-node cluster in Kubernetes refers to a cluster where both the control plane (which manages the cluster) and the worker node (which runs applications) are on the same machine. It runs all the components of Kubernetes, including the API server, scheduler, and Kubelet, but on just one physical or virtual node.

# How to install Minikube with Ubuntu
1. **STEP 1:** Connect to the Server via PuTTY
   * Open PuTTY
   * Enter the Hostname or IP Address
   * Click Open
   * Login to the server by writing ubuntu
     
2. **STEP 2:** Install docker using the following command
   
           curl -sL https://github.com/ShubhamTatvamasi/docker-install/raw/master/docker-install.sh | bash

![WhatsApp Image 2024-09-23 at 15 13 50_890bcc7a](https://github.com/user-attachments/assets/6a62086d-595f-4ea4-abae-109fdb571018)


4. **STEP 3:**  Add your local user to docker group so that your local user run docker commands without sudo.

               sudo usermod -aG docker $USER

5. **STEP 4:** Now enter the following command

              $ newgrp docker

6. **STEP 5:** Install the Kubernetes command-line tool, kubectl, via the Snap package management system

               sudo snap install kubectl --classic

               kubectl version --client

7. **STEP 6:** Download and Install Minikube Binary

                curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

                sudo install minikube-linux-amd64 /usr/local/bin/minikube

8. **STEP 7:** Verify minikube version by following command

                minikube version

![WhatsApp Image 2024-09-23 at 15 13 52_d790956c](https://github.com/user-attachments/assets/5da6aaac-b513-44c0-b895-9fffe50c0fb8)

9. **STEP 8:** Install Kubectl tool

                curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
   
10. **STEP 9:** Start Minikube Cluster
    
                minikube start --driver=docker

11. **STEP 10:** Verify the status of your cluster

                minikube status

![WhatsApp Image 2024-09-24 at 00 39 14_7cfa6cbf](https://github.com/user-attachments/assets/104cb600-c576-42b9-812a-60a979c43e71)

12. **STEP 11** Grant permissions

                kubectl cluster-info

                Kubectl config view

                kubectl get nodes

                kubectl get pods

13. **STEP 12** start the Kubernetes dashboard run below command

                minikube dashboard

    ![image alt](https://www.linuxbuzz.com/wp-content/uploads/2023/11/Starting-Kubernetes-Dashboard-Minikube-1024x93.png)

                kubectl proxy --address='0.0.0.0' --disable-filter=true &
    
15. **STEP 13** Use the following url on browser and use your public ip 

               http://public_ip:8001/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/

![image alt](https://www.linuxbuzz.com/wp-content/uploads/2023/11/Kubernetes-Dashboard-GUI-Minikube-Ubuntu-1024x640.png)
