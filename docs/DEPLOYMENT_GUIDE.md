\# Deployment Guide -



\## Prerequisites

\- Azure CLI  

\- Bicep CLI  

\- Contributor rights on target subscription  



\## Login

```sh

az login

az account set --subscription "<SUBSCRIPTION\_ID>"

```



\## What-If Deployment

```sh

az deployment sub what-if   --location eastus2   --template-file infra/main.bicep   --parameters environment=dev sqlAdminPassword="MyStrongP@ss!"

```



\## Actual Deployment

```sh

az deployment sub create   --location eastus2   --template-file infra/main.bicep   --parameters environment=dev sqlAdminPassword="MyStrongP@ss!"

```



\## Outputs

The deployment returns:

\- App Service name  

\- Key Vault URI  

\- VNet IDs  

\- Storage endpoint  

\- Log Analytics workspace ID  



\## Troubleshooting

\- Check NSG associations on app subnet  

\- Ensure SQL and Storage private endpoints have correct subnet  

\- Ensure VNet peering is fully in sync  



