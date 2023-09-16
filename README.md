# Infrasity Deployment

## Overview

This repository contains the Terraform configuration script for deploying the Infrasity application on Azure Kubernetes Service (AKS) using Terraform and Azure resources. Terraform offers a robust infrastructure-as-code solution, while AKS provides a managed Kubernetes cluster, ensuring scalability and reliability. This README will guide you through the deployment process.

## Prerequisites

Before you begin, make sure you have the following prerequisites:

- [Terraform](https://www.terraform.io/downloads.html) installed.
- Azure CLI and an Azure account.
- Basic knowledge of Terraform and Kubernetes.

## Deployment

# Clone this repository to your local machine:

```
git clone https://github.com/ScaleupInfra/terrateam-azure.git
```

# Initialize Terraform and download the required providers:

```
terraform init

```

# Modify the main.tf file to configure your deployment according to your requirements. You may need to adjust variables, resources, and settings.

# Create a Terraform execution plan:

```
terraform plan

```

Apply the Terraform configuration to create the AKS cluster and associated resources:

```
terraform apply

```

After the deployment is complete, Terraform will output the kubeconfig information. Save this information securely, as it will be needed to interact with your AKS cluster.

## Accessing the AKS Cluster

To access the AKS cluster using kubectl, use the kubeconfig provided during the Terraform apply step:

```
kubectl --kubeconfig=<path-to-kubeconfig> get pods

```

Replace `<path-to-kubeconfig>` with the actual path to your kubeconfig file.

## Cleanup

# To destroy the AKS cluster and associated resources when you no longer need them, run:

```
terraform destroy

```

## Troubleshooting

# If you encounter any issues or have questions, please refer to the Terraform documentation and Azure Kubernetes Service documentation, or feel free to open an issue in this repository.

Happy deploying!
