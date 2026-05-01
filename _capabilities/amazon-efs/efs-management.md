---
categories: []
consumed_apis:
- efs
description: Unified capability for managing EFS file systems, mount targets, and access points for storage administrators.
layout: capability
name: Amazon EFS Elastic File System Management
operations:
- description: Amazon EFS Describe File Systems
  method: GET
  name: describeFileSystems
  path: /v1/2015-02-01/file-systems
- description: Amazon EFS Create File System
  method: POST
  name: createFileSystem
  path: /v1/2015-02-01/file-systems
- description: Amazon EFS Delete File System
  method: DELETE
  name: deleteFileSystem
  path: /v1/2015-02-01/file-systems
- description: Amazon EFS Describe Mount Targets
  method: GET
  name: describeMountTargets
  path: /v1/2015-02-01/mount-targets
- description: Amazon EFS Create Mount Target
  method: POST
  name: createMountTarget
  path: /v1/2015-02-01/mount-targets
personas: []
provider_name: Amazon EFS
provider_slug: amazon-efs
search_terms:
- amazon efs delete file system
- create file system
- createFileSystem
- amazon efs create mount target
- delete file system
- createMountTarget
- amazon efs describe file systems
- engineers managing amazon efs resources on aws.
- file storage
- describe file systems
- describeMountTargets
- amazon efs create file system
- deleteFileSystem
- elastic file system
- amazon efs
- create mount target
- amazon efs describe mount targets
- describe mount targets
- amazon web services
- file system management business domain for amazon efs.
- efs
- nfs
- workflow capability for file system management.
- aws
- storage
- describeFileSystems
- file system
- serverless
slug: efs-management
source_filename: efs-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon EFS Elastic File System Management\"\n  description: \"Unified capability for managing EFS file systems, mount targets, and access points for storage administrators.\"\n  tags:\n    - Amazon EFS\n    - AWS\n    - Storage\n    - File System\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: efs\n      location: ./shared/efs.yaml\n\n  exposes:\n    - type: rest\n      port: 8085\n      namespace: efs-api\n      description: \"Unified REST API for Elastic File System Management.\"\n      resources:\n        - path: /v1/2015-02-01/file-systems\n          name: describeFileSystems\n          description: \"Amazon EFS Describe File Systems\"\n          operations:\n            - method: GET\n              name: describeFileSystems\n             \
  \ description: \"Amazon EFS Describe File Systems\"\n              call: \"efs.describeFileSystems\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/2015-02-01/file-systems\n          name: createFileSystem\n          description: \"Amazon EFS Create File System\"\n          operations:\n            - method: POST\n              name: createFileSystem\n              description: \"Amazon EFS Create File System\"\n              call: \"efs.createFileSystem\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/2015-02-01/file-systems\n          name: deleteFileSystem\n          description: \"Amazon EFS Delete File System\"\n          operations:\n            - method: DELETE\n              name: deleteFileSystem\n              description: \"Amazon EFS Delete File System\"\n              call: \"efs.deleteFileSystem\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/2015-02-01/mount-targets\n          name: describeMountTargets\n          description: \"Amazon EFS Describe Mount Targets\"\n          operations:\n            - method: GET\n              name: describeMountTargets\n              description: \"Amazon EFS Describe Mount Targets\"\n              call: \"efs.describeMountTargets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/2015-02-01/mount-targets\n          name: createMountTarget\n          description: \"Amazon EFS Create Mount Target\"\n          operations:\n            - method: POST\n              name: createMountTarget\n              description: \"Amazon EFS Create Mount Target\"\n              call: \"efs.createMountTarget\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9095\n\
  \      namespace: efs-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Elastic File System Management.\"\n      tools:\n        - name: describe-file-systems\n          description: \"Amazon EFS Describe File Systems\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"efs.describeFileSystems\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-file-system\n          description: \"Amazon EFS Create File System\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"efs.createFileSystem\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-file-system\n          description: \"Amazon EFS Delete File System\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"efs.deleteFileSystem\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: describe-mount-targets\n          description: \"Amazon EFS Describe Mount Targets\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"efs.describeMountTargets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-mount-target\n          description: \"Amazon EFS Create Mount Target\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"efs.createMountTarget\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-efs/refs/heads/main/capabilities/efs-management.yaml
tags:
- Amazon EFS
- Storage
- File System
tools:
- description: Amazon EFS Describe File Systems
  hints:
    destructive: false
    readOnly: true
  name: describe-file-systems
- description: Amazon EFS Create File System
  hints:
    destructive: false
    readOnly: false
  name: create-file-system
- description: Amazon EFS Delete File System
  hints:
    destructive: true
    readOnly: false
  name: delete-file-system
- description: Amazon EFS Describe Mount Targets
  hints:
    destructive: false
    readOnly: true
  name: describe-mount-targets
- description: Amazon EFS Create Mount Target
  hints:
    destructive: false
    readOnly: false
  name: create-mount-target
---
