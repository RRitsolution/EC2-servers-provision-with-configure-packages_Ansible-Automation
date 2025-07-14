# EC2 servers provision with configure packages_Ansible-Automation
This repository is automate(except existing ssh key and security group and subnet id ) to provision EC2 servers along with packages setup and get confirm if packages are installed or not 

Project Overview:-
1: We will launch 3 EC2 vms on AWS with automation Ansible
2: Then We will fetch dynamically Public IPS of earlier launched VMs to connect purpose
3: Finally We will setup all 3 servers like webserver(deploy apache2 package) 1st server and 2nd for data base server(deploy mysql_server) and last 3rd one for application server (deploy python package)
4: We will also confirm if required packages are succesfully installed or not 

Below are the files structure used to deploy this project .

ansible.pem(ssh key)  ec2launch.yaml(Playbook)  inventory.ini(Inventory file)  secrets.yaml(secrets file )

Note-I have made empty file ansible.pem(since sharing publically) in your case it will contain private key data


To execute this playbook:-

ansible-playbook  -i inventory.ini ec2launch.yaml --ask-vault-pass

Pre requsite:-
1 EC2 already provisioned with Ansible setup and python3-pip, boto, boto3,boto-core packages installed to intract with AWS

Private ssh key file is availbile on my EC2 server root directory(where ansbile is running you need to copy to it by scp command-
##scp -i private ssh key user@public ip:root directory path) 

aws_access key & aws_secret key already configured on my Ansible control server to authenticate with AWS account(I have used my aws root user aws access key & aws secret key)

secrets.yaml need to create and encrypted to use with playbook//for creation command
##ansible-vault create secrets.yaml ==>further you can set password and defined your secrets like key,etc.

for this project i have set below secrets in secrets.yaml:-




key_name: ##put your ssh key name(only key name not with pem extension)

security_group: ## put your security group name ensure port all traffic is open now for .. it is for testing only not production

ansible_ssh_private_key_file: ##key name with ssh path like ./xyz.pem of your ansible server






