\# Enterprise-Grade Azure Landing Zone  

\### \*\*Hub–Spoke Architecture • Private Endpoints • Zero-Trust Networking • Secure App Platform\*\*



This repository contains a fully modular \*\*Azure Landing Zone\*\*, engineered using \*\*Bicep IaC\*\* following enterprise cloud architecture patterns.



---



\## \*\*Architecture Overview\*\*



Your Azure environment implements:



\### \*\*Hub–Spoke Network Topology\*\*

\- \*\*Hub VNet\*\* (`10.0.0.0/16`)

&nbsp; - Centralized routing

&nbsp; - Gateway transit enabled

\- \*\*Spoke VNet\*\* (`10.10.0.0/16`)

&nbsp; - App, Data, and Monitoring subnets

&nbsp; - NSG applied to App subnet



\### \*\*Private Endpoints (Zero Public Exposure)\*\*

Private Endpoints deployed for:

\- \*\*Storage Account (Blob)\*\*

\- \*\*SQL Server\*\*

\- \*\*Key Vault\*\*



All resources are:

\- Public network access \*\*disabled\*\*

\- Private DNS Zones automatically configured via NIC attachments



\### \*\*Application Layer\*\*

\- \*\*App Service (Web/API workload)\*\*

&nbsp; - VNet Integration with App Subnet

&nbsp; - Key Vault secret references enabled

\- \*\*Application Insights\*\* (Workspace-based)

\- \*\*Log Analytics Workspace\*\* for unified monitoring



\### \*\*Security Controls\*\*

\- NSG to restrict inbound/outbound traffic

\- Key Vault firewall + VNet rule

\- TLS 1.2 enforcement

\- Managed Identity enabled for secure secret retrieval



---



\## \*\*Repository Structure\*\*



```

/infra

&nbsp; main.bicep               # Master subscription-level deployment

/infra-lib

&nbsp; /networking

&nbsp;   vnet.bicep

&nbsp;   vnet-peering.bicep

&nbsp;   nsg.bicep

&nbsp; /security

&nbsp;   keyvault.bicep

&nbsp;   private-endpoint.bicep

&nbsp; /data

&nbsp;   storage-account.bicep

&nbsp;   sqlserver-db.bicep

&nbsp; /compute

&nbsp;   appservice-webapi.bicep

&nbsp; /monitoring

&nbsp;   log-analytics.bicep

&nbsp;   app-insights.bicep

/docs

&nbsp; ARCHITECTURE.md 

&nbsp; DEPLOYMENT\_GUIDE.md

&nbsp; MODULE\_OVERVIEW.md

&nbsp; SECURITY\_MODEL.md

&nbsp; CHANGELOG.md 

&nbsp; architecture-diagram.png  # Enterprise architecture diagram

```



---



\## \*\*Deployment\*\*



\### Prerequisites

\- Azure CLI  

\- Bicep CLI  

\- Contributor access on the subscription  



\### Deploy

```bash

az deployment sub create   --name projectA-dev   --location eastus2   --template-file infra/main.bicep   --parameters environment=dev sqlAdminPassword="YourPassword123!"

```



---



\## Outputs

Deployment returns:

\- App Service URL

\- Key Vault URI

\- Storage Blob Endpoint

\- Hub + Spoke VNet IDs

\- Log Analytics Workspace ID



---



\## Purpose

This project demonstrates:

\- Enterprise Azure cloud engineering

\- Infrastructure-as-Code mastery

\- Private networking \& zero-trust design

\- Modular Bicep architecture

\- Real-world DevOps + Cloud Security patterns



Perfect for:

\- LinkedIn showcase  

\- Portfolio projects  

\- Interview discussions  

\- Cloud engineering demonstrations  



---



\## Architecture Diagram

Included at `/docs/architecture.png`  

(You can replace it with the regenerated version.)



---



\## Author

\*\*Malcolm Warren\*\*  

Future Cloud Architect | Azure \& DevOps | Cloud Advocate ☁

Built with: Azure, Bicep, Azure CLI, GitHub Actions (CI/CD)



---





