# Snowflake Terraform Infrastructure
Repository for learning how to structure Terraform for a Snowflake account

## Installing Terraform
First step is make sure we have Hashicorp Terraform installed:
```bash
wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
```
```bash
terraform --version
```

The traditional Terraform workflow follows these commands:
```bash
terraform init
terraform plan
terraform apply
terraform destroy
```
Other Terraform commands can be used to provide information for the current state of the repository and infrastructure:


## Creating a Snowflake Service User for Terraform
You may create a new Git repository for this project, or use an already created one.
The next step is creating a RSA key for Terraform authentication.
```bash
cd ~/.ssh
openssl genrsa 2048 | openssl pkcs8 -topk8 -inform PEM -out snowflake_tf_snow_key.p8 -nocrypt
openssl rsa -in snowflake_tf_snow_key.p8 -pubout -out snowflake_tf_snow_key.pub
```



## References
- [Terraforming Snowflake](https://quickstarts.snowflake.com/guide/terraforming_snowflake/)
- [Install Terraform (Hashicorp)](https://developer.hashicorp.com/terraform/install)
