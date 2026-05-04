# EKS-Cluster-Creation
EKS Cluster creation using Terraform

This project provisions a production-ready Amazon EKS cluster using Terraform.
We build the cluster step by step, covering IAM roles, networking, node groups, and outputs.

# Step 1 - 

File structure - terraform

| File  | Description |
| ------------- | ------------- |
| c1_versions.tf  | Required Terraform + AWS provider versions  |
| c2_variables.tf	  | Input variables (region, cluster name, etc.)  |
| c3_remote-state.tf | Remote backend for Terraform state (S3 + DynamoDB)|
|c4_datasources_and_locals.tf|AWS data sources and local values|
|c5_eks_tags.tf|Common tags for resources|
|c6_eks_cluster_iamrole.tf| IAM role for EKS control plane|
|c7_eks_cluster.tf| EKS cluster resource definition|
|c8_eks_nodegroup_iamrole.tf| IAM role for EKS worker node groups|
|c9_eks_nodegroup_private.tf| Private node group configuration|
|c10_eks_outputs.tf	| Useful Terraform outputs (kubeconfig, cluster details)

# Step 2 - Steps to Provision 

 Terraform Initialize
terraform init

 Terraform Validate
terraform validate

 Terraform Plan
terraform plan

 Terraform Apply
terraform apply -auto-approve

# Step-03: Configure kubectl cli to access EKS cluster
 EKS kubeconfig
aws eks update-kubeconfig --name <cluster_name> --region <aws_region>

 List Kubernetes Nodes
kubectl get nodes

 List Kubernetes Pods 
kubectl get pods -n kube-system

# Step-04: Browse EKS Cluster features on AWS Console
Go to AWS Console -> EKS
Review Tabs
Overview
Resources
Compute
Networking
Add-ons
Access
Observability
Update history
Tags


<img width="1916" height="383" alt="image" src="https://github.com/user-attachments/assets/18147b77-618e-4736-9b59-a91b97c3892c" />
