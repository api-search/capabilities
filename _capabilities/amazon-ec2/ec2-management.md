---
categories: []
consumed_apis: []
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
- amazon ec2 terminate instances
- amazon ec2 stop running instances
- aws
- run instances
- compute
- amazon ec2 describe ec2 instances
- startInstances
- amazon ec2 start stopped instances
- infrastructure
- rebootInstances
- cloud compute management business domain for amazon ec2.
- runInstances
- iaas
- virtual machines
- deregister image
- amazon ec2
- amazon ec2 deregister an ami
- amazon ec2 launch ec2 instances
- deregisterImage
- stopInstances
- stop instances
- workflow capability for cloud compute management.
- cloud computing
- reboot instances
- amazon ec2 describe instance status
- describeImages
- describe images
- describeInstances
- createImage
- amazon ec2 reboot instances
- describe instance status
- create image
- terminate instances
- start instances
- engineers managing amazon ec2 resources on aws.
- terminateInstances
- describeInstanceStatus
- amazon ec2 create an ami from an instance
- describe instances
- amazon ec2 describe amis
slug: ec2-management
source_filename: ec2-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon EC2 Cloud Compute Management\n  description: Unified capability for managing EC2 instances, AMIs, security groups, and networking for cloud infrastructure\n    engineers.\n  tags:\n  - Amazon EC2\n  - AWS\n  - Compute\n  - Cloud Computing\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: ec2\n    baseUri: https://ec2.amazonaws.com\n    description: Amazon EC2 resizable compute capacity in the cloud.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: AWS4-HMAC-SHA256 Credential={{env.AWS_ACCESS_KEY_ID}}\n      placement: header\n    resources:\n    - name: ?Action=RunInstances\n      path: /?Action=RunInstances\n      description: Operations for ?Action=RunInstances resources.\n      operations:\n      - name: runInstances\n\
  \        method: GET\n        description: Amazon EC2 Launch EC2 Instances\n        inputParameters:\n        - name: MinCount\n          in: query\n          type: integer\n          required: true\n          description: The minimum number of instances to launch\n        - name: MaxCount\n          in: query\n          type: integer\n          required: true\n          description: The maximum number of instances to launch\n        - name: KeyName\n          in: query\n          type: string\n          required: false\n          description: The name of the key pair to use for SSH access\n        - name: SecurityGroupId\n          in: query\n          type: array\n          required: false\n          description: The IDs of the security groups\n        - name: SubnetId\n          in: query\n          type: string\n          required: false\n          description: The ID of the subnet to launch the instance into\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: ?Action=DescribeInstances\n      path: /?Action=DescribeInstances\n      description: Operations for ?Action=DescribeInstances resources.\n      operations:\n      - name: describeInstances\n        method: GET\n        description: Amazon EC2 Describe EC2 Instances\n        inputParameters:\n        - name: InstanceId\n          in: query\n          type: array\n          required: false\n          description: The instance IDs to describe\n        - name: Filter\n          in: query\n          type: array\n          required: false\n          description: Filters to apply to the results\n        - name: MaxResults\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Token for the next page of results\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=StartInstances\n      path: /?Action=StartInstances\n      description: Operations for ?Action=StartInstances resources.\n      operations:\n      - name: startInstances\n        method: GET\n        description: Amazon EC2 Start Stopped Instances\n        inputParameters:\n        - name: InstanceId\n          in: query\n          type: array\n          required: true\n          description: The IDs of the instances to start\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=StopInstances\n      path: /?Action=StopInstances\n      description: Operations for ?Action=StopInstances resources.\n      operations:\n      - name: stopInstances\n        method: GET\n        description: Amazon EC2 Stop Running Instances\n        inputParameters:\n        - name: InstanceId\n\
  \          in: query\n          type: array\n          required: true\n          description: The IDs of the instances to stop\n        - name: Force\n          in: query\n          type: boolean\n          required: false\n          description: Forces the instances to stop without graceful shutdown\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=TerminateInstances\n      path: /?Action=TerminateInstances\n      description: Operations for ?Action=TerminateInstances resources.\n      operations:\n      - name: terminateInstances\n        method: GET\n        description: Amazon EC2 Terminate Instances\n        inputParameters:\n        - name: InstanceId\n          in: query\n          type: array\n          required: true\n          description: The IDs of the instances to terminate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: ?Action=RebootInstances\n      path: /?Action=RebootInstances\n      description: Operations for ?Action=RebootInstances resources.\n      operations:\n      - name: rebootInstances\n        method: GET\n        description: Amazon EC2 Reboot Instances\n        inputParameters:\n        - name: InstanceId\n          in: query\n          type: array\n          required: true\n          description: The IDs of the instances to reboot\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DescribeInstanceStatus\n      path: /?Action=DescribeInstanceStatus\n      description: Operations for ?Action=DescribeInstanceStatus resources.\n      operations:\n      - name: describeInstanceStatus\n        method: GET\n        description: Amazon EC2 Describe Instance Status\n        inputParameters:\n        - name: InstanceId\n          in: query\n          type: array\n \
  \         required: false\n          description: The instance IDs to describe\n        - name: IncludeAllInstances\n          in: query\n          type: boolean\n          required: false\n          description: Include all instances regardless of running state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=CreateImage\n      path: /?Action=CreateImage\n      description: Operations for ?Action=CreateImage resources.\n      operations:\n      - name: createImage\n        method: GET\n        description: Amazon EC2 Create an AMI from an Instance\n        inputParameters:\n        - name: InstanceId\n          in: query\n          type: string\n          required: true\n          description: The ID of the instance to create the image from\n        - name: Name\n          in: query\n          type: string\n          required: true\n          description: A name for the new image\n     \
  \   - name: Description\n          in: query\n          type: string\n          required: false\n          description: A description for the new image\n        - name: NoReboot\n          in: query\n          type: boolean\n          required: false\n          description: If true, Amazon EC2 does not shut down the instance before creating the image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DescribeImages\n      path: /?Action=DescribeImages\n      description: Operations for ?Action=DescribeImages resources.\n      operations:\n      - name: describeImages\n        method: GET\n        description: Amazon EC2 Describe AMIs\n        inputParameters:\n        - name: ImageId\n          in: query\n          type: array\n          required: false\n          description: The image IDs to describe\n        - name: Owner\n          in: query\n          type: array\n          required: false\n\
  \          description: Scopes the results to images with the specified owners\n        - name: Filter\n          in: query\n          type: array\n          required: false\n          description: Filters to apply to the results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DeregisterImage\n      path: /?Action=DeregisterImage\n      description: Operations for ?Action=DeregisterImage resources.\n      operations:\n      - name: deregisterImage\n        method: GET\n        description: Amazon EC2 Deregister an AMI\n        inputParameters:\n        - name: ImageId\n          in: query\n          type: string\n          required: true\n          description: The ID of the AMI to deregister\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=CreateSecurityGroup\n      path: /?Action=CreateSecurityGroup\n\
  \      description: Operations for ?Action=CreateSecurityGroup resources.\n      operations:\n      - name: createSecurityGroup\n        method: GET\n        description: Amazon EC2 Create a Security Group\n        inputParameters:\n        - name: GroupName\n          in: query\n          type: string\n          required: true\n          description: The name of the security group\n        - name: GroupDescription\n          in: query\n          type: string\n          required: true\n          description: A description for the security group\n        - name: VpcId\n          in: query\n          type: string\n          required: false\n          description: The ID of the VPC for the security group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DescribeSecurityGroups\n      path: /?Action=DescribeSecurityGroups\n      description: Operations for ?Action=DescribeSecurityGroups resources.\n\
  \      operations:\n      - name: describeSecurityGroups\n        method: GET\n        description: Amazon EC2 Describe Security Groups\n        inputParameters:\n        - name: GroupId\n          in: query\n          type: array\n          required: false\n          description: The IDs of the security groups to describe\n        - name: GroupName\n          in: query\n          type: array\n          required: false\n          description: The names of the security groups to describe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=AuthorizeSecurityGroupIngress\n      path: /?Action=AuthorizeSecurityGroupIngress\n      description: Operations for ?Action=AuthorizeSecurityGroupIngress resources.\n      operations:\n      - name: authorizeSecurityGroupIngress\n        method: GET\n        description: Amazon EC2 Add Inbound Security Group Rules\n        inputParameters:\n        - name:\
  \ GroupId\n          in: query\n          type: string\n          required: true\n          description: The ID of the security group\n        - name: IpProtocol\n          in: query\n          type: string\n          required: false\n          description: The IP protocol name (tcp, udp, icmp) or number\n        - name: FromPort\n          in: query\n          type: integer\n          required: false\n          description: The start of port range for TCP and UDP protocols\n        - name: ToPort\n          in: query\n          type: integer\n          required: false\n          description: The end of port range for TCP and UDP protocols\n        - name: CidrIp\n          in: query\n          type: string\n          required: false\n          description: The IPv4 CIDR range\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DeleteSecurityGroup\n      path: /?Action=DeleteSecurityGroup\n\
  \      description: Operations for ?Action=DeleteSecurityGroup resources.\n      operations:\n      - name: deleteSecurityGroup\n        method: GET\n        description: Amazon EC2 Delete a Security Group\n        inputParameters:\n        - name: GroupId\n          in: query\n          type: string\n          required: false\n          description: The ID of the security group to delete\n        - name: GroupName\n          in: query\n          type: string\n          required: false\n          description: The name of the security group to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=CreateKeyPair\n      path: /?Action=CreateKeyPair\n      description: Operations for ?Action=CreateKeyPair resources.\n      operations:\n      - name: createKeyPair\n        method: GET\n        description: Amazon EC2 Create a Key Pair\n        inputParameters:\n        - name: KeyName\n     \
  \     in: query\n          type: string\n          required: true\n          description: A unique name for the key pair\n        - name: KeyType\n          in: query\n          type: string\n          required: false\n          description: The type of key pair (rsa or ed25519)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DescribeKeyPairs\n      path: /?Action=DescribeKeyPairs\n      description: Operations for ?Action=DescribeKeyPairs resources.\n      operations:\n      - name: describeKeyPairs\n        method: GET\n        description: Amazon EC2 Describe Key Pairs\n        inputParameters:\n        - name: KeyName\n          in: query\n          type: array\n          required: false\n          description: The key pair names to describe\n        - name: KeyPairId\n          in: query\n          type: array\n          required: false\n          description: The IDs of the key pairs\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DeleteKeyPair\n      path: /?Action=DeleteKeyPair\n      description: Operations for ?Action=DeleteKeyPair resources.\n      operations:\n      - name: deleteKeyPair\n        method: GET\n        description: Amazon EC2 Delete a Key Pair\n        inputParameters:\n        - name: KeyName\n          in: query\n          type: string\n          required: false\n          description: The name of the key pair to delete\n        - name: KeyPairId\n          in: query\n          type: string\n          required: false\n          description: The ID of the key pair to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=AllocateAddress\n      path: /?Action=AllocateAddress\n      description: Operations for ?Action=AllocateAddress resources.\n  \
  \    operations:\n      - name: allocateAddress\n        method: GET\n        description: Amazon EC2 Allocate an Elastic IP Address\n        inputParameters:\n        - name: Domain\n          in: query\n          type: string\n          required: false\n          description: Set to vpc to allocate the address for use with instances in a VPC\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=AssociateAddress\n      path: /?Action=AssociateAddress\n      description: Operations for ?Action=AssociateAddress resources.\n      operations:\n      - name: associateAddress\n        method: GET\n        description: Amazon EC2 Associate an Elastic IP Address\n        inputParameters:\n        - name: AllocationId\n          in: query\n          type: string\n          required: false\n          description: The allocation ID for the Elastic IP address\n        - name: InstanceId\n          in: query\n\
  \          type: string\n          required: false\n          description: The ID of the instance to associate with\n        - name: NetworkInterfaceId\n          in: query\n          type: string\n          required: false\n          description: The ID of the network interface\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=ReleaseAddress\n      path: /?Action=ReleaseAddress\n      description: Operations for ?Action=ReleaseAddress resources.\n      operations:\n      - name: releaseAddress\n        method: GET\n        description: Amazon EC2 Release an Elastic IP Address\n        inputParameters:\n        - name: AllocationId\n          in: query\n          type: string\n          required: false\n          description: The allocation ID of the Elastic IP address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: ?Action=CreateLaunchTemplate\n      path: /?Action=CreateLaunchTemplate\n      description: Operations for ?Action=CreateLaunchTemplate resources.\n      operations:\n      - name: createLaunchTemplate\n        method: GET\n        description: Amazon EC2 Create a Launch Template\n        inputParameters:\n        - name: LaunchTemplateName\n          in: query\n          type: string\n          required: true\n          description: A name for the launch template\n        - name: VersionDescription\n          in: query\n          type: string\n          required: false\n          description: A description for the first version of the launch template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DescribeLaunchTemplates\n      path: /?Action=DescribeLaunchTemplates\n      description: Operations for ?Action=DescribeLaunchTemplates resources.\n      operations:\n     \
  \ - name: describeLaunchTemplates\n        method: GET\n        description: Amazon EC2 Describe Launch Templates\n        inputParameters:\n        - name: LaunchTemplateId\n          in: query\n          type: array\n          required: false\n          description: The IDs of the launch templates\n        - name: LaunchTemplateName\n          in: query\n          type: array\n          required: false\n          description: The names of the launch templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=RequestSpotInstances\n      path: /?Action=RequestSpotInstances\n      description: Operations for ?Action=RequestSpotInstances resources.\n      operations:\n      - name: requestSpotInstances\n        method: GET\n        description: Amazon EC2 Request Spot Instances\n        inputParameters:\n        - name: SpotPrice\n          in: query\n          type: string\n          required:\
  \ false\n          description: The maximum price per unit hour for a Spot Instance\n        - name: InstanceCount\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of Spot Instances to launch\n        - name: Type\n          in: query\n          type: string\n          required: false\n          description: The Spot Instance request type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DescribeSpotInstanceRequests\n      path: /?Action=DescribeSpotInstanceRequests\n      description: Operations for ?Action=DescribeSpotInstanceRequests resources.\n      operations:\n      - name: describeSpotInstanceRequests\n        method: GET\n        description: Amazon EC2 Describe Spot Instance Requests\n        inputParameters:\n        - name: SpotInstanceRequestId\n          in: query\n          type: array\n          required: false\n\
  \          description: The IDs of the Spot Instance requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DescribeRegions\n      path: /?Action=DescribeRegions\n      description: Operations for ?Action=DescribeRegions resources.\n      operations:\n      - name: describeRegions\n        method: GET\n        description: Amazon EC2 Describe AWS Regions\n        inputParameters:\n        - name: RegionName\n          in: query\n          type: array\n          required: false\n          description: The names of the Regions\n        - name: AllRegions\n          in: query\n          type: boolean\n          required: false\n          description: Indicates whether to display all Regions including disabled\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ?Action=DescribeAvailabilityZones\n      path:\
  \ /?Action=DescribeAvailabilityZones\n      description: Operations for ?Action=DescribeAvailabilityZones resources.\n      operations:\n      - name: describeAvailabilityZones\n        method: GET\n        description: Amazon EC2 Describe Availability Zones\n        inputParameters:\n        - name: ZoneName\n          in: query\n          type: array\n          required: false\n          description: The names of the Availability Zones\n        - name: ZoneId\n          in: query\n          type: array\n          required: false\n          description: The IDs of the Availability Zones\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: ec2-api\n    description: Unified REST API for Cloud Compute Management.\n    resources:\n    - path: /v1/?Action=RunInstances\n      name: runInstances\n      description: Amazon EC2 Launch EC2 Instances\n      operations:\n\
  \      - method: GET\n        name: runInstances\n        description: Amazon EC2 Launch EC2 Instances\n        call: ec2.runInstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/?Action=DescribeInstances\n      name: describeInstances\n      description: Amazon EC2 Describe EC2 Instances\n      operations:\n      - method: GET\n        name: describeInstances\n        description: Amazon EC2 Describe EC2 Instances\n        call: ec2.describeInstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/?Action=StartInstances\n      name: startInstances\n      description: Amazon EC2 Start Stopped Instances\n      operations:\n      - method: GET\n        name: startInstances\n        description: Amazon EC2 Start Stopped Instances\n        call: ec2.startInstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/?Action=StopInstances\n      name: stopInstances\n\
  \      description: Amazon EC2 Stop Running Instances\n      operations:\n      - method: GET\n        name: stopInstances\n        description: Amazon EC2 Stop Running Instances\n        call: ec2.stopInstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/?Action=TerminateInstances\n      name: terminateInstances\n      description: Amazon EC2 Terminate Instances\n      operations:\n      - method: GET\n        name: terminateInstances\n        description: Amazon EC2 Terminate Instances\n        call: ec2.terminateInstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/?Action=RebootInstances\n      name: rebootInstances\n      description: Amazon EC2 Reboot Instances\n      operations:\n      - method: GET\n        name: rebootInstances\n        description: Amazon EC2 Reboot Instances\n        call: ec2.rebootInstances\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/?Action=DescribeInstanceStatus\n      name: describeInstanceStatus\n      description: Amazon EC2 Describe Instance Status\n      operations:\n      - method: GET\n        name: describeInstanceStatus\n        description: Amazon EC2 Describe Instance Status\n        call: ec2.describeInstanceStatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/?Action=CreateImage\n      name: createImage\n      description: Amazon EC2 Create an AMI from an Instance\n      operations:\n      - method: GET\n        name: createImage\n        description: Amazon EC2 Create an AMI from an Instance\n        call: ec2.createImage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/?Action=DescribeImages\n      name: describeImages\n      description: Amazon EC2 Describe AMIs\n      operations:\n      - method: GET\n        name: describeImages\n        description: Amazon EC2 Describe AMIs\n        call: ec2.describeImages\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/?Action=DeregisterImage\n      name: deregisterImage\n      description: Amazon EC2 Deregister an AMI\n      operations:\n      - method: GET\n        name: deregisterImage\n        description: Amazon EC2 Deregister an AMI\n        call: ec2.deregisterImage\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: ec2-mcp\n    transport: http\n    description: MCP server for AI-assisted Cloud Compute Management.\n    tools:\n    - name: run-instances\n      description: Amazon EC2 Launch EC2 Instances\n      hints:\n        readOnly: true\n        destructive: false\n      call: ec2.runInstances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-instances\n      description: Amazon EC2 Describe EC2 Instances\n      hints:\n        readOnly: true\n        destructive: false\n      call: ec2.describeInstances\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-instances\n      description: Amazon EC2 Start Stopped Instances\n      hints:\n        readOnly: true\n        destructive: false\n      call: ec2.startInstances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-instances\n      description: Amazon EC2 Stop Running Instances\n      hints:\n        readOnly: true\n        destructive: false\n      call: ec2.stopInstances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: terminate-instances\n      description: Amazon EC2 Terminate Instances\n      hints:\n        readOnly: true\n        destructive: false\n      call: ec2.terminateInstances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reboot-instances\n      description: Amazon EC2 Reboot Instances\n      hints:\n        readOnly: true\n        destructive: false\n      call: ec2.rebootInstances\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-instance-status\n      description: Amazon EC2 Describe Instance Status\n      hints:\n        readOnly: true\n        destructive: false\n      call: ec2.describeInstanceStatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-image\n      description: Amazon EC2 Create an AMI from an Instance\n      hints:\n        readOnly: true\n        destructive: false\n      call: ec2.createImage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-images\n      description: Amazon EC2 Describe AMIs\n      hints:\n        readOnly: true\n        destructive: false\n      call: ec2.describeImages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deregister-image\n      description: Amazon EC2 Deregister an AMI\n      hints:\n        readOnly: true\n        destructive: false\n      call: ec2.deregisterImage\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-ec2/refs/heads/main/capabilities/ec2-management.yaml
tags:
- Amazon EC2
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
