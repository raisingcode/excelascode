# excelascode v.1.3
<img width="1600" height="524" alt="excel-as-code" src="https://github.com/user-attachments/assets/6da9af9e-0425-41f0-bacb-ef16932c23e3" />
<br/>

## Backstory
Excel As Code was concieved workign with on-prem sysadmins moving some vm to public cloud.  After several rounds or pitches on different was to start cloud native and with devops Excel as Code began as simple worksheet to help teams rapid add new vms and get them deployed .  The main requirement  was to be able to create a list of vms and deploy them for in azure in without having the patience or deep understanding of devops and cloud migration best practices. The tool was hit for the team has been used with other departments as transitionary tool to create vms quick have the terraform need for config managment requirements in some enteprises

# The why and the how...
Many teams still require a way to deploy vms in bulk fashion. This is where the capability of excel as code comes . Spreadsheet will allow teams to
 define the vms names, skus, images and images they want in spreedsheet form then  deploy directly into Azure or export to Terraform, or Bicep implementation allowing them to start leveraging iac to deploy them and keeping DevOps compliance with infra as code principals

 # Tested Environments
✅ Office 2019
✅ Office 365 Desktop

 ## Capabilities
 - Quota checker for available vcpu capability before deploying
 - Region specific skus
 - Support for Azure Public (AWS or GCP could available in future releases)
 - Deployment options
   - Deploy directly into azure via api
   - Export as terraform
   - Export as ARM template

 ## Features requested (not yet implemented)
 - Service Principal integration
 - Multi-az configuration
 - Use Keyvault or Hashicorp vault to store passwords
 - Multicloud suppport
   - Azure is currently implemented at the time but with interest it could be updated for other cloud providers (AWS, GCP, etc.)

