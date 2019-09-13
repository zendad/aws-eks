# Kubernetes setup on Amazon AWS EKS with eksctl
This repository contains tooling for deploying a HA Kubernetes cluster on Amazon AWS EKS in an existing VPC with subnets.

## Prerequisites
The cluster will be deployed from a linux jumpbox/bastion host with the following:
 - [eksctl](https://eksctl.io/), to [install follow this guide](https://eksctl.io/introduction/installation/)
 - kubectl 
 - aws tools
 
Configure the AWS credentials to be be used to authenticate with Amazon AWS, with the correct roles attached to it.
   
## Configurations
The main configuration of the cluster is in the file `cluster.yml`.
 
## Installing the EKS cluster
Create the eks cluster using `eksctl`:
```
eksctl create cluster -f cluster.yaml
```

## Kube Config 
aws eks --region eu-west-1  update-kubeconfig --name `[clustername]`