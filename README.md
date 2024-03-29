# Automation - Kubernetes setup using Terraform & Ansible
A worked example to provision, Automate and setup Kubernetes cluster(**kubeadm - One Master node and One Worker node**) on AWS ec2 instance(ubuntu) using Terraform and Anisble 

#### Requirements 
1. Terraform v0.12
2. ansible 2.9 
3. ubuntu 18.04 (EC2 instance)
4. Python 2.7.18 or 3.*
5. Docker CE
6. AWS account with default VPC

#### Please follow the below steps
### EC2 Instance setup:
1. Download the Git reopository 
2. Go to terraform_aws_ec2_instance directory and crate SSH key pairs (Private and Public) using ssh-keygen command
3. Run the command to cretate two instances(t2.micro) in your default VPC (#terraform apply -var="ec2_count=2") ---> One for Master and one for worker node
4. The terraform script will display the private IPs after executing the scripts successfully 

### Setup Kubernetes using Ansible:
1. Navigate to Ansible directory
2. Setup the inventory by copy pasting private IPs (#terraform output) 
3. Please do the smoke test by using the ping command (#ansible all -m ping)
4. Run Ansible playbook (#ansible-playbook playbooks/main.yaml)
