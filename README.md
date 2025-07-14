# EC2 servers provision with configure packages_Ansible-Automation
This repository is fully automate to provision EC2 servers along with packages setup and get confirm if packages are installed or not 

Pre requsite:-
1 EC2 already provisioned with Ansible setup and python3-pip, boto, boto3,boto-core packages installed to intract with AWS services
Private ssh key file is availbile on my EC2 server root(where ansbile is running) 
aws_access key & aws_secret key already configured on my Ansible control server to authenticate with AWS account(I have used my aws root user aws access key & aws secret key)
secrets.yaml created and encrypted to use with playbook//for creation command- ansible-vault create secrets.yaml further you can set password and defined your secrets like key,etc.
for this project i have set below secrets in secrets.yaml:-
key_name: ##put your ssh key name(only key name not with pem extension)
security_group: ## put your security group name ensure port all traffic is open now for .. it is for testing only not production
ansible_ssh_private_key_file: ##key name with ssh path like ./xyz.pem of your ansible server

