# ABOUT K8s
Kubernetes, often abbreviated as K8s, is an open-source platform for automating the deployment, scaling, and management of containerized applications. 
**Main Function/Usage:-** Kubernetes manages containers, which package an application and its dependencies together to ensure it runs consistently across different environments. Containers are isolated units but lightweight compared to virtual machines.

# NODE 
A Node is the fundamental worker machine in a Kubernetes cluster. It can be either a physical machine or a virtual machine in a cloud environment. Each node runs the necessary services to support the containers it hosts, such as the container runtime (e.g., Docker), the Kubelet (which communicates with the Kubernetes control plane), and Kube-proxy (which manages networking for the pods).

**TYPES OF NODES**

1. Master Node- The master node is the brain of the Kubernetes cluster and handles scheduling, maintaining the desired state, and managing resources. It contains components like API Server,Scheduler,Controller Manager

2. Worker  Node- Worker nodes are the machines where application workloads run. These nodes run the containers and host the pods that make up an application. They handle the execution of the actual tasks, networking, and storage management.

# PODS
A Pod is the smallest and most basic deployable unit in Kubernetes (K8s). It represents a single instance of a running process in your cluster and can contain one or more containers that share the same network and storage resources. Typically, pods are used to run a single container, but there are cases where multiple containers need to work together closely, and in these cases, a pod will contain multiple tightly coupled containers.
