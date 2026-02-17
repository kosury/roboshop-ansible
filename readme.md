 https://docs.ansible.com/projects/ansible/latest/collections/amazon/aws/ec2_instance_module.html#ansible-collections-amazon-aws-ec2-instance-module

 we have have to search for EC2 instance creation in Ansible.
 since ansible has no inbuilt modules for this, amazon has provided amazon.aws.ec2-instance

 EC2 instance creation- required parameters, below list is including optional parameters also

 name: start an instance with a public IP address
  amazon.aws.ec2_instance:
    name: "public-compute-instance"
    key_name: "prod-ssh-key"
    vpc_subnet_id: subnet-5ca1ab1e
    instance_type: c5.large
    security_group: default
    network_interfaces:
      - assign_public_ip: true
    image_id: ami-123456
    tags:
      Environment: Testing


AMI ID : ami-0220d79f3f480ecf5
Instance type : t3.micro
security_group: sg-03371e37c82c1a968
name: 
tags:
        Project: roboshop
        Component: "{{ item }}"
        Environment: "{{ env }}"
        Name: 