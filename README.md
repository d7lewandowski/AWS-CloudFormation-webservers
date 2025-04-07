# AWS SimuLearn - Cloud First Steps

This CloudFormation template creates a basic VPC, subnets, an internet gateway, a route table with routes, and launches two EC2 instances with associated security groups.
*UserData is encode base64
## Overview

The template provisions:
- **VPC (LabVpc):** With CIDR block `10.0.0.0/16`
- **Subnets:** Two public subnets in different Availability Zones:
  - `PublicSubnetSubnet1` in `us-east-1a` with CIDR block `10.0.0.0/24`
  - `PublicSubnetSubnet2` in `us-east-1b` with CIDR block `10.0.1.0/24`
- **Security Group:** (`InstanceSecurityGroup`) that allows HTTP (port 80) inbound and outbound
- **EC2 Instances:** Two web servers (`WebServer01` and `WebServer02`)
- **Internet Gateway:** and its attachment to the VPC
- **Route Table and Routes:** To enable outbound traffic to the internet
- **Subnet Associations:** To link subnets with the route table

## Deployment

1. **Upload the Template:**  
   Log into AWS CloudFormation and create a new stack by uploading the `AWSSimuLearnCloudFirstSteps.yaml` template.

2. **Specify Stack Parameters (if any):**  
   This template does not require parameter input.

3. **Review and Create:**  
   Review your settings and launch the stack.

4. **Verify:**  
   On successful deployment, the VPC ID will be output.

## Cleanup

To avoid unwanted charges, remember to delete the CloudFormation stack when it is no longer needed.

## Note

The EC2 instances are launched with user data that configures a basic web server setup.  
For further customization, you can modify the template or the user data scripts within the resource definitions.

Happy learning with AWS!
