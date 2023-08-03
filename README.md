Udacity. Cloud DevOps Engineer Nanodegree Program. 
Project 2.

## Project 2 - Deploy a high-availability web app using CloudFormation

##### Project Overview
The creation of this project is to practice and get experience in infrastructure as code. Let's imagine a business develops an app that is similar to Instagram. The programmers uploaded the most recent version of their code as a zip file to the open S3 bucket. Deploying the application into the appropriate infrastructure together with the required auxiliary applications is the current task. Automating this will enable the infrastructure to be taken down as soon as the testing team has finished the test and gathered its findings. The scenario is a realistic app where a sample dummy HTML file has been deployed on the Apache web server running on an EC2 instance.

##### 1. Infrastructure Diagram: 
To visualize and understand the CloudFormation script.


![udagram-infrastructure-diagram](https://github.com/nafnu/Deploy-a-high-availability-web-app-using-CloudFormation/assets/65398774/f3565662-b45b-4ea7-b9ce-4114433485bb)



##### 2.Scripts: 
Templates and parameters. Will be added documents in folders to interpret the instructions and scripts. The files included are: 
 - `create.sh:` cloudformation create stack script.
 - `update.sh:` cloudformation update stack script.
 - `delete.sh:` cloudformation delete stack script.
 - `network.yml:` parameters file for network cloudformation stack.
 - `network-parameters.json:` cloudformation parameters file for creating networking resources for this project.
 - `servers.yml:` parameters file for server cloudformation stack. Also, include the role
 - `servers-parameters.json:` cloudformation parameters file for create a server for this project.

### How to run the supporting material?
You can run the supporting material in two easy steps:
```bash
## Create the network infrastructure
./create.sh UdagramApp network.yml network-parameters.json
# After exceuting it these are the resources created:
# VPC
# Subnets
# Route Tables
# Routes
# Internet Gateway
# NAT Gateways

## Create server
./create.sh webserver-stack servers.yml server-parameters.json
# After exceuting it these are the resources created:
# Security Groups
# IAM Role, Policy, Instance Profile
# Launch configuration
# Auto Scaling Group
# Load Balancer
# Target Group