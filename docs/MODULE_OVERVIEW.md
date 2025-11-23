\# Module Overview – 



\## Networking Modules

\### `vnet.bicep`

\- Creates hub or spoke VNet  

\- Outputs subnet IDs  

\- Supports NSG binding  

\- Supports subnet delegations  



\### `nsg.bicep`

\- Creates NSG with baseline rules  



\### `vnet-peering.bicep`

\- hub ↔ spoke VNet peering  



\## Data Modules

\### `sqlserver-db.bicep`

\- SQL Server + DB  

\- Private-only  

\- Secure TLS/Password  



\### `storage-account.bicep`

\- Storage Account  

\- Private-only networking  



\## Security Modules

\### `keyvault.bicep`

\- Private Key Vault  

\- Network ACLs locked to data subnet  



\### `private-endpoint.bicep`

\- Generic module  

\- Used for SQL, Storage, Key Vault  



\## Compute Modules

\### `appservice-webapi.bicep`

\- App Service Plan  

\- Web App  

\- VNet integration  

\- Key Vault ref support  



\## Monitoring Modules

\### `log-analytics.bicep`

\- LAW creation  

\- For diagnostics  



\### `app-insights.bicep`

\- Workspace-based App Insights  



