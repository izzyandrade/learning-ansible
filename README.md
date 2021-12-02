# learning-ansible

A repository I created to learn about Ansible, a powerful Configuration Management Tool for Continuous Deployment (CD)

### Command to populate inventory.txt

You can use the following command to get the list of public IP addresses from EC2 instances,
and printing them into the inventory.txt file:

`aws ec2 describe-instances --query 'Reservations[*].Instances[*].PublicIpAddress' --region us-east-1 --output text >> inventory`

### Command to run the playbook

By running this command, the playbook gets called, accesses all of the EC2 instances inside the inventory, and run all the tasks you defined,
don't forget to change {YOUR_SSH_KEY} with the SSH key you defined for the instances.

`ansible-playbook main.yml -i inventory --private-key ../{YOUR_SSH_KEY}.pem`
