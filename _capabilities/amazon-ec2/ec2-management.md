---
categories: []
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
- startInstances
- amazon ec2 deregister an ami
- compute
- workflow capability for cloud compute management.
- describe instance status
- amazon ec2 reboot instances
- stopInstances
- terminate instances
- createImage
- reboot instances
- amazon ec2 describe instance status
- deregister image
- deregisterImage
- virtual machines
- infrastructure
- aws
- amazon ec2 terminate instances
- create image
- describeImages
- amazon ec2 create an ami from an instance
- stop instances
- amazon ec2 stop running instances
- cloud computing
- runInstances
- engineers managing amazon ec2 resources on aws.
- cloud compute management business domain for amazon ec2.
- amazon ec2 describe amis
- iaas
- describeInstanceStatus
- rebootInstances
- amazon ec2 describe ec2 instances
- describe instances
- describeInstances
- amazon ec2 start stopped instances
- amazon ec2
- amazon ec2 launch ec2 instances
- run instances
- terminateInstances
- describe images
- start instances
slug: ec2-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon EC2 Cloud Compute Management\"\n  description: \"Unified capability for managing EC2 instances, AMIs, security groups, and networking for cloud infrastructure engineers.\"\n  tags:\n    - Amazon EC2\n    - AWS\n    - Compute\n    - Cloud Computing\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: ec2\n      location: ./shared/ec2.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: ec2-api\n      description: \"Unified REST API for Cloud Compute Management.\"\n      resources:\n        - path: /v1/?Action=RunInstances\n          name: runInstances\n          description: \"Amazon EC2 Launch EC2 Instances\"\n          operations:\n            - method: GET\n              name: runInstances\n              description: \"\
  Amazon EC2 Launch EC2 Instances\"\n              call: \"ec2.runInstances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/?Action=DescribeInstances\n          name: describeInstances\n          description: \"Amazon EC2 Describe EC2 Instances\"\n          operations:\n            - method: GET\n              name: describeInstances\n              description: \"Amazon EC2 Describe EC2 Instances\"\n              call: \"ec2.describeInstances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/?Action=StartInstances\n          name: startInstances\n          description: \"Amazon EC2 Start Stopped Instances\"\n          operations:\n            - method: GET\n              name: startInstances\n              description: \"Amazon EC2 Start Stopped Instances\"\n              call: \"ec2.startInstances\"\n              outputParameters:\n       \
  \         - type: object\n                  mapping: \"$.\"\n        - path: /v1/?Action=StopInstances\n          name: stopInstances\n          description: \"Amazon EC2 Stop Running Instances\"\n          operations:\n            - method: GET\n              name: stopInstances\n              description: \"Amazon EC2 Stop Running Instances\"\n              call: \"ec2.stopInstances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/?Action=TerminateInstances\n          name: terminateInstances\n          description: \"Amazon EC2 Terminate Instances\"\n          operations:\n            - method: GET\n              name: terminateInstances\n              description: \"Amazon EC2 Terminate Instances\"\n              call: \"ec2.terminateInstances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/?Action=RebootInstances\n          name: rebootInstances\n\
  \          description: \"Amazon EC2 Reboot Instances\"\n          operations:\n            - method: GET\n              name: rebootInstances\n              description: \"Amazon EC2 Reboot Instances\"\n              call: \"ec2.rebootInstances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/?Action=DescribeInstanceStatus\n          name: describeInstanceStatus\n          description: \"Amazon EC2 Describe Instance Status\"\n          operations:\n            - method: GET\n              name: describeInstanceStatus\n              description: \"Amazon EC2 Describe Instance Status\"\n              call: \"ec2.describeInstanceStatus\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/?Action=CreateImage\n          name: createImage\n          description: \"Amazon EC2 Create an AMI from an Instance\"\n          operations:\n            - method:\
  \ GET\n              name: createImage\n              description: \"Amazon EC2 Create an AMI from an Instance\"\n              call: \"ec2.createImage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/?Action=DescribeImages\n          name: describeImages\n          description: \"Amazon EC2 Describe AMIs\"\n          operations:\n            - method: GET\n              name: describeImages\n              description: \"Amazon EC2 Describe AMIs\"\n              call: \"ec2.describeImages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/?Action=DeregisterImage\n          name: deregisterImage\n          description: \"Amazon EC2 Deregister an AMI\"\n          operations:\n            - method: GET\n              name: deregisterImage\n              description: \"Amazon EC2 Deregister an AMI\"\n              call: \"ec2.deregisterImage\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: ec2-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Cloud Compute Management.\"\n      tools:\n        - name: run-instances\n          description: \"Amazon EC2 Launch EC2 Instances\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2.runInstances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-instances\n          description: \"Amazon EC2 Describe EC2 Instances\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2.describeInstances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-instances\n          description: \"Amazon EC2 Start Stopped Instances\"\n          hints:\n     \
  \       readOnly: true\n            destructive: false\n          call: \"ec2.startInstances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-instances\n          description: \"Amazon EC2 Stop Running Instances\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2.stopInstances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: terminate-instances\n          description: \"Amazon EC2 Terminate Instances\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2.terminateInstances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reboot-instances\n          description: \"Amazon EC2 Reboot Instances\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2.rebootInstances\"\n \
  \         outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-instance-status\n          description: \"Amazon EC2 Describe Instance Status\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2.describeInstanceStatus\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-image\n          description: \"Amazon EC2 Create an AMI from an Instance\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2.createImage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-images\n          description: \"Amazon EC2 Describe AMIs\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2.describeImages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: deregister-image\n          description: \"Amazon EC2 Deregister an AMI\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2.deregisterImage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-ec2/refs/heads/main/capabilities/ec2-management.yaml
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
