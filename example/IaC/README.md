
## Terraform - High Available Provisioning 
```
cd provisioning
export TF_VAR_ec2_count=4
terraform init
terraform plan -out 'tfplan'
terraform apply 'tfplan'
```