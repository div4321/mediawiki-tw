# MEDIAWIKI AUTODEPLOYEMENT USING ANSIBLE

Execution of the playbook **'tw_mediawiki.yaml'** will launch a MediaWiki Frontend in an AWS EC2 RHEL8 instance and a backend MySQL RDS Instance.  

I have used predefined Security Group in my AWS VPC where EC2 is publicly accessible over port 80 in a public subnet and RDS instance is launched in private subnet which is only accessible from EC2 security group. 

This code was created to achieve a basic distributed architecture  but in case of need, code can be expanded to incorporate FT & HA using AWS ASG, AWS ALB & AWS Route 53. 

## Imp Information

I have used **Ansible dynamic inventory** (ec2.ini and ec2.py files located in "inventory" directory) where in "ec2.ini" file is tweaked to limit the scope to just AWS Mumbai region. 

Below are a few important consideration in order to use the code successfully

1. AWS Access and Secret Keys are stored in an ansible-vault protected file.
2. Dynamic Inventory file "ec2.ini" is saved in /etc/ansible/ and this file also has the AWS Access & Secret Keys defined in it.
3. Below requirements are needed on the host that executes this playbook module 
    1. boto
    2. boto3
    3. botocore
    4. python >= 2.6
