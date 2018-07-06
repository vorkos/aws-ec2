# aws-ec2

Prepare ec2 instances for swarm cluster

aws:
  region: "eu-central-1"

vpc:
  #Name of VPC
  aws_vpc_name: "example-vpc"
  #Name of security group
  sg: "prod"
  #AWS region for example
  aws_vpc_region: "{{ aws.region }}"
  #AWS availability zones in region for example
  aws_vpc_az_a: "{{ aws.region }}a"
  aws_vpc_az_b: "{{ aws.region }}b"
  aws_vpc_az_c: "{{ aws.region }}c"
  #AWS VPC cidr block for example
  aws_vpc_cidrblock: "10.0.0.0/16"
  #AWS VPC subnets in availability zone from vpc cidr block
  aws_vpc_subnet_az_a: "10.0.0.0/24"
  aws_vpc_subnet_az_b: "10.0.1.0/24"
  aws_vpc_subnet_az_c: "10.0.2.0/24"

ec2:
  aws_ec2_region: "{{ aws.region }}"
  #Tag for all nodes
  tag_Role: "swarm"
  #image ami
  image: "ami-3c635cd7"
  count_worker: 1
  count_manager: 3
  type: "t2.micro"
  #Name of ssh creds in AWS
  ssh_key: "vorkos"

