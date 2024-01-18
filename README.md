# learn-terraform-aks

Practices of this guide: [Quickstart - Deploy an AKS using Terraform](https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-terraform?tabs=bash). The sample repository is [here](https://github.com/Azure-Samples/aks-store-demo).

Relevant commands of this repository:
```shell
az login
az account show
az account list --query "[?user.name=='<microsoft_account_email>'].{Name:name, ID:id, Default:isDefault}" --output Table

printenv | grep '^ARM*'

terraform init -upgrade
terraform plan -out main.tfplan
terraform apply main.tfplan

resource_group_name=$(terraform output -raw resource_group_name)
az aks list --resource-group $resource_group_name --query "[].{\"K8s cluster name\":name}" --output table
echo "$(terraform output kube_config)" > ./azurek8s
export KUBECONFIG=./azurek8s
kubectl get nodes

### helper commands ###
az account list-locations -o table

az vm list-sizes --location koreasouth -o table
az vm list-skus --location koreasouth -o table
```