# azFunc-github-actions

```bash
cd bash
./000.step-one-setup-terraform.sh
```
This will setup a resource group simply to do terraform state management for the project

```bash
cd terraform
export ARM_ACCESS_KEY=$(az keyvault secret show --name terraform-backend-key --vault-name kv-tf-githubaction --query value -o tsv)  
terraform init
terraform plan -out=tf.plan
terraform apply tf.plan
```
