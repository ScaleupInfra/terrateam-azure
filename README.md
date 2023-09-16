# Infrasity Deployment

# Overview

This repository contains the Terraform configuration script for deploying the Infrasity application on Azure Kubernetes Service (AKS) using Terraform and Azure resources. Terraform offers a robust infrastructure-as-code solution, while AKS provides a managed Kubernetes cluster, ensuring scalability and reliability. This README will guide you through the deployment process.

# Prerequisites

## Before you begin, make sure you have the following prerequisites:

- [Terraform](https://www.terraform.io/downloads.html) installed.
- Azure CLI and an Azure account.
- Basic knowledge of Terraform and Kubernetes.
- [Terrateam](https://github.com/apps/terrateam-action) installed.

## Deployment on local

## Clone this repository to your local machine:

```
git clone https://github.com/ScaleupInfra/terrateam-azure.git
```

# Initialize Terraform and download the required providers:

```
terraform init

```

## Modify the main.tf file to configure your deployment according to your requirements. You may need to adjust your backend settings.

## Create a Terraform execution plan:

```
terraform plan

```

## Apply the Terraform configuration to create the AKS cluster and associated resources:

```
terraform apply

```

After the deployment is complete, Terraform will output the kubeconfig information. Save this information securely, as it will be needed to interact with your AKS cluster.

# Working with Terrateam on GitHub

## Commit your changes into your github
```
git add .
git commit -m "all files"
git push origin main
```
You can change repo and it's branch according to your configurations.

## Create a branch
```
git checkout -b terrateam-setups
```
Do some changes to your branch and push it to the GitHub
```
git add .
git commit -m "changes made"
git push origin terrateam-setups
```
## Raise a pull request
You can raise a pull request from you GitHub UI or install [GitHub CLI](https://cli.github.com/) to your local and run the following command to raise a pull request
```
gh pr create --fill
```

# Checkout PR
Checkout your PR request, on successful plan, comment ``` terrateam apply ``` on PR to apply changes in your Azure account.

# Accessing the AKS Cluster

To access the AKS cluster using kubectl, use the kubeconfig provided during the Terraform apply step:

```
kubectl --kubeconfig=<path-to-kubeconfig> get pods

```

Replace `<path-to-kubeconfig>` with the actual path to your kubeconfig file.

# Cleanup

## To destroy the AKS cluster and associated resources when you no longer need them, run:

```
terraform destroy

```

# Troubleshooting

## If you encounter any issues or have questions, please refer to the Terraform documentation and Azure Kubernetes Service documentation, or feel free to open an issue in this repository.

Happy deploying!
