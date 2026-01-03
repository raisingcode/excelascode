# excelascode v.012
<img width="1600" height="524" alt="excel-as-code" src="https://github.com/user-attachments/assets/6da9af9e-0425-41f0-bacb-ef16932c23e3" />
<br/>

## Backstory
Excel As Code was concieved an a business need  on-prem sysadmins moving some vm to public cloud.  After several rounds or pitches on different was to start cloud native and with devops Excel as Code began as simple worksheet to help teams rapid add new vms and get them deployed .  The main requirement  was to be able to create a list of vms and deploy them for in azure in without having the patience or deep understanding of devops and cloud migration best practices. The tool was hit for the team has been used with other departments as transitionary tool to create vms quick have the terraform need for config managment requirements in some enteprises

## Is this Ideal?
No. But many team still require the need to deploy vms in admin state. This where the capability of excel as code comes . Spreadsheet will allow teams to
 define the vms names and images they want, deploy to an ARM, Terraform, or Bicep implementation allowing them to start leveraging iac to deploy them. 

 ## Capabilities
 - Quota checker
 - Create vms or use an existing
 - Deployment options
   - Deploy directly into azure via api
   - Export as terraform
   - Export as ARM template

 ## Features requested (not yet implemented)
 - Service Principal
 - Use Keyvault or Hashicorp vault to store passwords
 - Multicloud suppport
   - Azure is currently implemented at the time but with interest it could be updated for other cloud providers (AWS, GCP, etc.)

