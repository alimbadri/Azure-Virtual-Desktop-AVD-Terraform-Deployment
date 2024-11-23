# Azure-Virtual-Desktop-AVD-Terraform-Deployment
This repository contains Terraform scripts used to deploy and manage Azure Virtual Desktop (AVD) resources. The configuration includes important elements such as Resource Groups, Workspaces, Host Pools, Application Groups, and more.

Features
Automated creation of AVD resources:
Resource Group
Virtual Desktop Workspace
Host Pool
Application Group (DAG)
Workspace and DAG association

Dynamic expiration for Host Pool Registration Token.

Outputs for deployed resources:
    Resource Group name
    Host Pool name
    Workspace name
    Application Group name
    Deployment location

## Prerequisites

Before running the Terraform scripts, ensure you have the following:

1. **Azure Subscription**: An active Azure account.
2. **Terraform Installed**: [Download Terraform](https://www.terraform.io/downloads.html).
3. **Azure CLI Installed**: [Install Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli).
4. **Permissions**:
   - Contributor or Owner role for the Azure subscription.
   - Directory Reader role for associating Active Directory groups (optional).

---

Set Up Azure Authentication: Export the following environment variables:

export ARM_CLIENT_ID=<your-client-id>
export ARM_CLIENT_SECRET=<your-client-secret>
export ARM_SUBSCRIPTION_ID=<your-subscription-id>
export ARM_TENANT_ID=<your-tenant-id>

Initialize Terraform: Run the following command to download the required provider plugins:

terraform init


Plan the Deployment: Generate and review an execution plan:

terraform plan

Apply the Configuration: Deploy the resources to Azure:

terraform apply

Outputs: After deployment, Terraform will display the following outputs:

Resource Group name
Host Pool name
Workspace name
Application Group name
Location
Outputs Example

    Outputs Example :

    azure_virtual_desktop_compute_resource_group = "rg-avd-resources"
            azure_virtual_desktop_host_pool = "AVD-TF-HP"
            azurerm_virtual_desktop_application_group = "avdtf-dag"
            azurerm_virtual_desktop_workspace = "valid_workspace-name_123"
            location = "eastus"

Directory Structure :-

.
├── main.tf                # Main Terraform configuration
├── variables.tf           # Input variables
├── outputs.tf             # Outputs for Terraform deployment
├── README.md              # Project documentation
└── .gitignore             # Ignored files

Notes
Ensure sensitive data (e.g., credentials) are stored securely and not committed to the repository.
Use .gitignore to exclude .terraform/, .tfstate, and other sensitive files.

Upcoming Improvements

Automate Terraform deployment with (GitHub Actions / Azure DevOps ).
Add more granular role-based access controls (RBAC) for AVD users.

Cleaning Up Resources 

To destroy the resources created by this configuration, run:

terraform destroy
