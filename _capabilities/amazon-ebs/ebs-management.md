---
categories: []
consumed_apis:
- ebs
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
- block storage management business domain for amazon ebs.
- storage
- describe volumes
- ec2
- detachVolume
- snapshots
- amazon ebs describe volumes
- amazon ebs describe snapshots
- describeVolumes
- createSnapshot
- deleteVolume
- amazon ebs delete volume
- amazon ebs create volume
- create volume
- volumes
- aws
- delete volume
- engineers managing amazon ebs resources on aws.
- attachVolume
- amazon ebs detach volume
- attach volume
- describeSnapshots
- detach volume
- createVolume
- create snapshot
- amazon ebs attach volume
- amazon web services
- amazon ebs
- ebs
- workflow capability for block storage management.
- describe snapshots
- block storage
- amazon ebs create snapshot
slug: ebs-management
source_filename: ebs-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon EBS Block Storage Management\"\n  description: \"Unified capability for managing EBS volumes, snapshots, and encryption for cloud storage administrators.\"\n  tags:\n    - Amazon EBS\n    - AWS\n    - Storage\n    - Block Storage\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: ebs\n      location: ./shared/ebs.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: ebs-api\n      description: \"Unified REST API for Block Storage Management.\"\n      resources:\n        - path: /v1/resource\n          name: describeVolumes\n          description: \"Amazon EBS Describe Volumes\"\n          operations:\n            - method: GET\n              name: describeVolumes\n              description: \"Amazon EBS Describe Volumes\"\
  \n              call: \"ebs.describeVolumes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resource\n          name: createVolume\n          description: \"Amazon EBS Create Volume\"\n          operations:\n            - method: POST\n              name: createVolume\n              description: \"Amazon EBS Create Volume\"\n              call: \"ebs.createVolume\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#DeleteVolume\n          name: deleteVolume\n          description: \"Amazon EBS Delete Volume\"\n          operations:\n            - method: POST\n              name: deleteVolume\n              description: \"Amazon EBS Delete Volume\"\n              call: \"ebs.deleteVolume\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#AttachVolume\n          name: attachVolume\n\
  \          description: \"Amazon EBS Attach Volume\"\n          operations:\n            - method: POST\n              name: attachVolume\n              description: \"Amazon EBS Attach Volume\"\n              call: \"ebs.attachVolume\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#DetachVolume\n          name: detachVolume\n          description: \"Amazon EBS Detach Volume\"\n          operations:\n            - method: POST\n              name: detachVolume\n              description: \"Amazon EBS Detach Volume\"\n              call: \"ebs.detachVolume\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#CreateSnapshot\n          name: createSnapshot\n          description: \"Amazon EBS Create Snapshot\"\n          operations:\n            - method: POST\n              name: createSnapshot\n              description: \"Amazon EBS Create Snapshot\"\
  \n              call: \"ebs.createSnapshot\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#DescribeSnapshots\n          name: describeSnapshots\n          description: \"Amazon EBS Describe Snapshots\"\n          operations:\n            - method: GET\n              name: describeSnapshots\n              description: \"Amazon EBS Describe Snapshots\"\n              call: \"ebs.describeSnapshots\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: ebs-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Block Storage Management.\"\n      tools:\n        - name: describe-volumes\n          description: \"Amazon EBS Describe Volumes\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ebs.describeVolumes\"\n          outputParameters:\n       \
  \     - type: object\n              mapping: \"$.\"\n        - name: create-volume\n          description: \"Amazon EBS Create Volume\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ebs.createVolume\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-volume\n          description: \"Amazon EBS Delete Volume\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ebs.deleteVolume\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: attach-volume\n          description: \"Amazon EBS Attach Volume\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ebs.attachVolume\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: detach-volume\n          description: \"Amazon EBS Detach Volume\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ebs.detachVolume\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-snapshot\n          description: \"Amazon EBS Create Snapshot\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ebs.createSnapshot\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-snapshots\n          description: \"Amazon EBS Describe Snapshots\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ebs.describeSnapshots\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
