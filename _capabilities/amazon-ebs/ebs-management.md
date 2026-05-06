---
categories: []
consumed_apis: []
description: Unified capability for managing EBS volumes, snapshots, and encryption for cloud storage administrators.
layout: capability
name: Amazon EBS Block Storage Management
operations:
- description: Amazon EBS Describe Volumes
  method: GET
  name: describeVolumes
  path: /v1/resource
- description: Amazon EBS Create Volume
  method: POST
  name: createVolume
  path: /v1/resource
- description: Amazon EBS Delete Volume
  method: POST
  name: deleteVolume
  path: /v1/#DeleteVolume
- description: Amazon EBS Attach Volume
  method: POST
  name: attachVolume
  path: /v1/#AttachVolume
- description: Amazon EBS Detach Volume
  method: POST
  name: detachVolume
  path: /v1/#DetachVolume
- description: Amazon EBS Create Snapshot
  method: POST
  name: createSnapshot
  path: /v1/#CreateSnapshot
- description: Amazon EBS Describe Snapshots
  method: GET
  name: describeSnapshots
  path: /v1/#DescribeSnapshots
personas: []
provider_name: Amazon EBS
provider_slug: amazon-ebs
search_terms:
- amazon ebs create volume
- aws
- describeVolumes
- amazon web services
- ebs
- amazon ebs attach volume
- storage
- volumes
- detachVolume
- amazon ebs describe snapshots
- amazon ebs
- delete volume
- amazon ebs detach volume
- createSnapshot
- create snapshot
- block storage
- amazon ebs describe volumes
- amazon ebs create snapshot
- attach volume
- workflow capability for block storage management.
- ec2
- create volume
- snapshots
- amazon ebs delete volume
- detach volume
- deleteVolume
- describe snapshots
- createVolume
- describeSnapshots
- attachVolume
- engineers managing amazon ebs resources on aws.
- describe volumes
- block storage management business domain for amazon ebs.
slug: ebs-management
source_filename: ebs-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon EBS Block Storage Management\n  description: Unified capability for managing EBS volumes, snapshots, and encryption for cloud storage administrators.\n  tags:\n  - Amazon EBS\n  - AWS\n  - Storage\n  - Block Storage\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: ebs\n    baseUri: https://ec2.amazonaws.com\n    description: Amazon Elastic Block Store persistent block storage for EC2 instances.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: AWS4-HMAC-SHA256 Credential={{env.AWS_ACCESS_KEY_ID}}\n      placement: header\n    resources:\n    - name: root\n      path: /\n      description: Operations for root resources.\n      operations:\n      - name: describeVolumes\n        method: GET\n        description: Amazon\
  \ EBS Describe Volumes\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: The Action parameter\n        - name: Version\n          in: query\n          type: string\n          required: true\n          description: The Version parameter\n        - name: VolumeId\n          in: query\n          type: array\n          required: false\n          description: The volume IDs to describe.\n        - name: MaxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of volumes to return.\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: The token for the next set of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createVolume\n        method: POST\n        description:\
  \ Amazon EBS Create Volume\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: The Action parameter\n        - name: Version\n          in: query\n          type: string\n          required: true\n          description: The Version parameter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#DeleteVolume\n      description: 'Operations for #DeleteVolume resources.'\n      operations:\n      - name: deleteVolume\n        method: POST\n        description: Amazon EBS Delete Volume\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: The Action parameter\n        - name: Version\n          in: query\n          type: string\n          required: true\n          description: The Version parameter\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#AttachVolume\n      description: 'Operations for #AttachVolume resources.'\n      operations:\n      - name: attachVolume\n        method: POST\n        description: Amazon EBS Attach Volume\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: The Action parameter\n        - name: Version\n          in: query\n          type: string\n          required: true\n          description: The Version parameter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#DetachVolume\n      description: 'Operations for #DetachVolume resources.'\n      operations:\n      - name: detachVolume\n        method: POST\n        description: Amazon EBS Detach Volume\n\
  \        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: The Action parameter\n        - name: Version\n          in: query\n          type: string\n          required: true\n          description: The Version parameter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#CreateSnapshot\n      description: 'Operations for #CreateSnapshot resources.'\n      operations:\n      - name: createSnapshot\n        method: POST\n        description: Amazon EBS Create Snapshot\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: The Action parameter\n        - name: Version\n          in: query\n          type: string\n          required: true\n          description: The Version parameter\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#DescribeSnapshots\n      description: 'Operations for #DescribeSnapshots resources.'\n      operations:\n      - name: describeSnapshots\n        method: GET\n        description: Amazon EBS Describe Snapshots\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: The Action parameter\n        - name: Version\n          in: query\n          type: string\n          required: true\n          description: The Version parameter\n        - name: SnapshotId\n          in: query\n          type: array\n          required: false\n          description: The snapshot IDs to describe.\n        - name: MaxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of snapshots to return.\n        - name: NextToken\n\
  \          in: query\n          type: string\n          required: false\n          description: The token for the next set of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: ebs-api\n    description: Unified REST API for Block Storage Management.\n    resources:\n    - path: /v1/resource\n      name: describeVolumes\n      description: Amazon EBS Describe Volumes\n      operations:\n      - method: GET\n        name: describeVolumes\n        description: Amazon EBS Describe Volumes\n        call: ebs.describeVolumes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/resource\n      name: createVolume\n      description: Amazon EBS Create Volume\n      operations:\n      - method: POST\n        name: createVolume\n        description: Amazon EBS Create Volume\n        call: ebs.createVolume\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/#DeleteVolume\n      name: deleteVolume\n      description: Amazon EBS Delete Volume\n      operations:\n      - method: POST\n        name: deleteVolume\n        description: Amazon EBS Delete Volume\n        call: ebs.deleteVolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#AttachVolume\n      name: attachVolume\n      description: Amazon EBS Attach Volume\n      operations:\n      - method: POST\n        name: attachVolume\n        description: Amazon EBS Attach Volume\n        call: ebs.attachVolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#DetachVolume\n      name: detachVolume\n      description: Amazon EBS Detach Volume\n      operations:\n      - method: POST\n        name: detachVolume\n        description: Amazon EBS Detach Volume\n        call: ebs.detachVolume\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /v1/#CreateSnapshot\n      name: createSnapshot\n      description: Amazon EBS Create Snapshot\n      operations:\n      - method: POST\n        name: createSnapshot\n        description: Amazon EBS Create Snapshot\n        call: ebs.createSnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#DescribeSnapshots\n      name: describeSnapshots\n      description: Amazon EBS Describe Snapshots\n      operations:\n      - method: GET\n        name: describeSnapshots\n        description: Amazon EBS Describe Snapshots\n        call: ebs.describeSnapshots\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: ebs-mcp\n    transport: http\n    description: MCP server for AI-assisted Block Storage Management.\n    tools:\n    - name: describe-volumes\n      description: Amazon EBS Describe Volumes\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n      call: ebs.describeVolumes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-volume\n      description: Amazon EBS Create Volume\n      hints:\n        readOnly: false\n        destructive: false\n      call: ebs.createVolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-volume\n      description: Amazon EBS Delete Volume\n      hints:\n        readOnly: false\n        destructive: false\n      call: ebs.deleteVolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: attach-volume\n      description: Amazon EBS Attach Volume\n      hints:\n        readOnly: false\n        destructive: false\n      call: ebs.attachVolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: detach-volume\n      description: Amazon EBS Detach Volume\n      hints:\n        readOnly: false\n        destructive: false\n      call: ebs.detachVolume\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-snapshot\n      description: Amazon EBS Create Snapshot\n      hints:\n        readOnly: false\n        destructive: false\n      call: ebs.createSnapshot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-snapshots\n      description: Amazon EBS Describe Snapshots\n      hints:\n        readOnly: true\n        destructive: false\n      call: ebs.describeSnapshots\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-ebs/refs/heads/main/capabilities/ebs-management.yaml
tags:
- Amazon EBS
- Storage
- Block Storage
tools:
- description: Amazon EBS Describe Volumes
  hints:
    destructive: false
    readOnly: true
  name: describe-volumes
- description: Amazon EBS Create Volume
  hints:
    destructive: false
    readOnly: false
  name: create-volume
- description: Amazon EBS Delete Volume
  hints:
    destructive: false
    readOnly: false
  name: delete-volume
- description: Amazon EBS Attach Volume
  hints:
    destructive: false
    readOnly: false
  name: attach-volume
- description: Amazon EBS Detach Volume
  hints:
    destructive: false
    readOnly: false
  name: detach-volume
- description: Amazon EBS Create Snapshot
  hints:
    destructive: false
    readOnly: false
  name: create-snapshot
- description: Amazon EBS Describe Snapshots
  hints:
    destructive: false
    readOnly: true
  name: describe-snapshots
---
