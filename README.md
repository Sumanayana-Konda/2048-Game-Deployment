# Amazon EKS (Elastic Kubernetes Service) 2048 Game Deployment

### The app is running on
<pre>
  http://k8s-game2048-ingress2-c229b36659-742404546.us-east-1.elb.amazonaws.com/
</pre>

## Project Overview
This project demonstrates the deployment of a 2048 game on Amazon EKS, Amazon's managed Kubernetes service. The game is deployed using Kubernetes resources such as Deployments, Pods, Services, and a Horizontal Pod Autoscaler (HPA). Additionally, OIDC (OpenID Connect) authentication is integrated into the cluster for secure access control.


### User Interface

<img width="1149" alt="Screen Shot 2023-10-12 at 3 22 19 AM" src="https://github.com/Sumanayana-Konda/Kubernetes-Project/assets/114708712/c72cf427-299c-4172-80ac-27e4f0a59195">

### Architecture
![microservices_application_on_amazon_eks](https://github.com/Sumanayana-Konda/Kubernetes-Project/assets/114708712/8ef8628f-d5d9-4380-8371-5d89c350651b)

### Kubernetes Resources
#### Pods:
Five Pods are running the 2048 game.
#### ReplicaSet:
A ReplicaSet ensures that the desired number of game Pods (in this case, five) are running at all times.
#### Deployment:
The Deployment manages the lifecycle of the game application.
It allows for declarative updates and rollbacks of the game.
#### Horizontal Pod Autoscaler (HPA):
The HPA monitors resource utilization (e.g., CPU) and automatically adjusts the number of game Pods to handle varying workloads.
#### Load Balancing
An AWS Elastic Load Balancer (ELB) or Application Load Balancer (ALB) is used to distribute incoming user traffic to the game Pods running in the EKS cluster.
#### OIDC Authentication
OIDC authentication is integrated into the EKS cluster to provide secure access control.
Users and applications can authenticate using OIDC tokens issued by the OIDC identity provider.
Kubernetes RBAC (Role-Based Access Control) roles and role bindings are configured to control access to cluster resources for OIDC-authenticated users.


## Prerequisites

### Install kubectl
[Link to install kubectl](https://kubernetes.io/docs/tasks/tools/)

### Install eksctl
[Link to install eksctl](https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html)

### Install aws-cli
[Link to install aws cli](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

### Install Helm
[Link to install helm](https://helm.sh/docs/intro/install/)





