# learn-terraform-aks

Relevant commands of this repository:
```shell
az login
az account show
az account list --query "[?user.name=='<microsoft_account_email>'].{Name:name, ID:id, Default:isDefault}" --output Table

printenv | grep '^ARM*'

terraform init -upgrade
terraform plan -out main.tfplan
terraform apply main.tfplan


### helper commands ###
az account list-locations -o table

az vm list-sizes --location koreasouth -o table
az vm list-skus --location koreasouth -o table
```