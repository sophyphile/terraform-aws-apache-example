# terraform-aws-apache-example

Terraform Module to provision an EC2 instance that runs Apache.

Not intended for production use. Showcase for how to create a public module on Terraform Registry

```hcl
terraform {

}

provider "aws" {
  # Configuration options
  region = "eu-west-2"
}

module "apache" {
  source = ".//terraform-aws-module-apache-example"
  vpc_id = "vpc-0000000000"
  my_ip_with_cidr = "MY_OWN_IP_ADDRESS/32"
  public_key = "ssh-rsa AAAAABBBB..."
  instance_type = "t2.micro"
  server_name = "Apache Example Server"
}

output "public_ip" {
  value = module.apache.public_ip
}
```
