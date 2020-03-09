# azFunc-github-actions

```bash
cd bash
./000.step-one-setup-terraform.sh
```
This will setup a resource group simply to do terraform state management for the project


```bash
cd az-setup/terraform/002.main-infrastructure/
terraform init
terraform plan -target=azurerm_function_app.main -out=tf.plan
terraform apply tf.plan 
```
The azure function needs to be created first so that its id is known before we can assign roles via managed identity.
So its a 2 step terraform process.

```bash
cd terraform
terraform init
terraform plan -out=tf.plan    
terraform apply tf.plan 
```
