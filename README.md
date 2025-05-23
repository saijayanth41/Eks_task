# EKS Task

## Overview
This repository contains a series of tasks designed to help users get hands-on experience with **Amazon Elastic Kubernetes Service (EKS)**. The project aims to simplify the deployment and management of containerized applications in Kubernetes clusters running on AWS.

## Prerequisites
To run this project successfully, you will need the following:
- **AWS Account**: For accessing Amazon Web Services.
- **AWS CLI**: Installed and configured with access to your AWS account.
- **kubectl**: Kubernetes CLI for interacting with your Kubernetes cluster.
- **eksctl**: A command-line tool to create and manage EKS clusters.
- **Docker**: To build and manage containerized applications.

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/saijayanth41/Eks_task.git
    cd Eks_task
    ```

2. Set up AWS CLI and eksctl:
    Follow the official guide to install and configure the AWS CLI and eksctl:
    - [AWS CLI Installation](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
    - [eksctl Installation](https://eksctl.io/)

3. Configure the AWS CLI with your AWS credentials:
    ```bash
    aws configure
    ```

4. Set up kubectl:
    Follow the guide here to install kubectl: [Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

## Project Structure

```
├── eks-cluster.yaml          # CloudFormation template to create the EKS cluster
├── deployment.yaml           # Kubernetes deployment configuration for your app
├── service.yaml              # Service definition for your app
├── README.md                 # Project documentation
└── scripts/                   # Helper scripts for deployment
    ├── create-cluster.sh      # Script to create the EKS cluster
    ├── deploy-app.sh          # Script to deploy the app on EKS
```

## How to Use

### 1. Create an EKS Cluster

Run the `create-cluster.sh` script to create the EKS cluster:
```bash
bash scripts/create-cluster.sh
```
This will initiate the creation of an EKS cluster in your AWS account.

### 2. Configure kubectl

Once the cluster is created, configure `kubectl` to connect to the EKS cluster:
```bash
aws eks --region <region> update-kubeconfig --name <cluster-name>
```

### 3. Deploy Your Application

Use the provided `deployment.yaml` and `service.yaml` files to deploy your application to EKS:
```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### 4. Verify the Deployment

Check if your app is successfully deployed:
```bash
kubectl get pods
kubectl get services
```

## Features
- **Cluster Management**: Automate the creation of an EKS cluster.
- **Application Deployment**: Simplify the deployment of your containerized applications on EKS.
- **Scalability**: Easily scale your applications with Kubernetes and EKS.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
