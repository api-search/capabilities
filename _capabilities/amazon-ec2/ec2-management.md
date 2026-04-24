---
consumed_apis:
- ec2
description: Unified capability for managing EC2 instances, AMIs, security groups, and networking for cloud infrastructure engineers.
layout: capability
name: Amazon EC2 Cloud Compute Management
operations:
- description: Amazon EC2 Launch EC2 Instances
  method: GET
  name: runInstances
  path: /v1/?Action=RunInstances
- description: Amazon EC2 Describe EC2 Instances
  method: GET
  name: describeInstances
  path: /v1/?Action=DescribeInstances
- description: Amazon EC2 Start Stopped Instances
  method: GET
  name: startInstances
  path: /v1/?Action=StartInstances
- description: Amazon EC2 Stop Running Instances
  method: GET
  name: stopInstances
  path: /v1/?Action=StopInstances
- description: Amazon EC2 Terminate Instances
  method: GET
  name: terminateInstances
  path: /v1/?Action=TerminateInstances
- description: Amazon EC2 Reboot Instances
  method: GET
  name: rebootInstances
  path: /v1/?Action=RebootInstances
- description: Amazon EC2 Describe Instance Status
  method: GET
  name: describeInstanceStatus
  path: /v1/?Action=DescribeInstanceStatus
- description: Amazon EC2 Create an AMI from an Instance
  method: GET
  name: createImage
  path: /v1/?Action=CreateImage
- description: Amazon EC2 Describe AMIs
  method: GET
  name: describeImages
  path: /v1/?Action=DescribeImages
- description: Amazon EC2 Deregister an AMI
  method: GET
  name: deregisterImage
  path: /v1/?Action=DeregisterImage
personas: []
provider_name: Amazon EC2
provider_slug: amazon-ec2
search_terms:
- createImage
- workflow capability for cloud compute management.
- runInstances
- amazon ec2 describe amis
- startInstances
- stop instances
- cloud compute management business domain for amazon ec2.
- amazon ec2 describe instance status
- amazon ec2 launch ec2 instances
- stopInstances
- compute
- describeInstanceStatus
- terminate instances
- deregister image
- amazon ec2 terminate instances
- describeInstances
- amazon ec2 start stopped instances
- reboot instances
- create image
- amazon ec2 describe ec2 instances
- amazon ec2 reboot instances
- amazon ec2 create an ami from an instance
- engineers managing amazon ec2 resources on aws.
- terminateInstances
- virtual machines
- describe instances
- describe images
- run instances
- amazon ec2
- amazon ec2 deregister an ami
- rebootInstances
- aws
- deregisterImage
- start instances
- cloud computing
- amazon ec2 stop running instances
- describeImages
- iaas
- infrastructure
- describe instance status
slug: ec2-management
tags:
- Amazon EC2
- AWS
- Compute
- Cloud Computing
tools:
- description: Amazon EC2 Launch EC2 Instances
  hints:
    destructive: false
    readOnly: true
  name: run-instances
- description: Amazon EC2 Describe EC2 Instances
  hints:
    destructive: false
    readOnly: true
  name: describe-instances
- description: Amazon EC2 Start Stopped Instances
  hints:
    destructive: false
    readOnly: true
  name: start-instances
- description: Amazon EC2 Stop Running Instances
  hints:
    destructive: false
    readOnly: true
  name: stop-instances
- description: Amazon EC2 Terminate Instances
  hints:
    destructive: false
    readOnly: true
  name: terminate-instances
- description: Amazon EC2 Reboot Instances
  hints:
    destructive: false
    readOnly: true
  name: reboot-instances
- description: Amazon EC2 Describe Instance Status
  hints:
    destructive: false
    readOnly: true
  name: describe-instance-status
- description: Amazon EC2 Create an AMI from an Instance
  hints:
    destructive: false
    readOnly: true
  name: create-image
- description: Amazon EC2 Describe AMIs
  hints:
    destructive: false
    readOnly: true
  name: describe-images
- description: Amazon EC2 Deregister an AMI
  hints:
    destructive: false
    readOnly: true
  name: deregister-image
---
