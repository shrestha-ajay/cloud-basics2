## Tutorial on automatically adding servers based on load in AWS

This CloudFormation template creates a multi-az, load balanced and Auto Scaled sample web site running on an Apache Web Serever. The application is configured to span all Availability Zones in the region and is Auto-Scaled based on the CPU utilization of the web servers. Notifications will be sent to the operator email address on scaling events. The instances are load balanced with a simple health check against the default web page. 

**WARNING** This template creates one or more Amazon EC2 instances and an Application Load Balancer. You will be billed for the AWS resources used if you create a stack from this template. 


### Steps:
1. Fork this repository by clicking on "Fork". 
2. Clone this repository to your local computer by running following:

   ```$ git clone git@github.com/YOUR-USERNAME/YOUR-REPOSITORY```
3. Configure AWS CLI in your local machine
4. Run the following command to create the ec2 instance and security group in your AWS account


```
 aws cloudformation deploy \
  --stack-name my-cloudbasic-autoscaling \
  --template-file AutoScalingMultiAZWithNotifications.template \
  --parameter-overrides KeyName="YOUR-EC2-KEYPAIR" OperatorEMail="YOUR-Email-Address"
  ```

  Note: Replace "General-key-1" KeyName with your EC2 KeyPair name


#### Related Resources: 
1. https://s3.amazonaws.com/cloudformation-templates-us-east-1/AutoScalingMultiAZWithNotifications.template
2. https://s3.amazonaws.com/cloudformation-templates-us-east-1/VPC_Single_Instance_In_Subnet.template


