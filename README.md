# Terraform template for Azure Virtual Network, ScaleSet, Load Balancer, SSH Jumpbox

DISCLAIMER: All credits goes to Microsoft Docs:

This is the full configuration from https://docs.microsoft.com/en-us/azure/terraform/terraform-create-vm-scaleset-network-disks-hcl adapted to my own personal needs

See above guide for additional information.

## Objectives
The objective of this project is to demostrate how to use Terraform modules with Azure to create:

- Virtual Network
- 2 Subnets
- Azure ScaleSet (2 instances)
- Custom Data to install nginx for LB testing purposes
- Azure LB to access ScaleSet instance
- Jumpbox to SSH instances in ScaleSet

## Requirements

- [Terraform](https://www.terraform.io/)
- [tf-modules](https://github.com/fervartel/tf-modules)
- terraform.tfvars with Azure credentials ([Authenticating Terraform using a Service Principal](https://www.terraform.io/docs/providers/azurerm/auth/service_principal_client_secret.html)):
``` bash
azure_subscription_id = "xxxx"
azure_client_id = "xxxx"
azure_client_secret = "xxxx"
azure_tenant_id = "xxxx"
```

## Advantages
The main advantage of using Terraform as IaC provider is the fact of being Cloud agnostic with support for multiple Cloud (as other services) providers.