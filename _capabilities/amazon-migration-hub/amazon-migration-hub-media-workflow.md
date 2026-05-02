---
categories: []
consumed_apis:
- migration_hub
description: Workflow capability for Amazon Migration Hub media processing operations for broadcast engineers and media developers.
layout: capability
name: Amazon Migration Hub Workflow
operations:
- description: List jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon Migration Hub
provider_slug: amazon-migration-hub
search_terms:
- media
- disassociate discovered resource
- associatediscoveredresource
- associate created artifact
- createprogressupdatestream
- describe migration task
- disassociatecreatedartifact
- Media Developer
- deleteprogressupdatestream
- Broadcast Engineer
- describe application state
- create progress update stream
- describeapplicationstate
- media processing
- broadcasting
- disassociatediscoveredresource
- delete progress update stream
- aws media processing and delivery
- amazon migration hub media processing workflow
- disassociate created artifact
- manage media processing jobs
- describemigrationtask
- workflow
- engineer managing broadcast media workflows
- list jobs
- associate discovered resource
- developer building media processing applications
- aws
- associatecreatedartifact
slug: amazon-migration-hub-media-workflow
source_filename: amazon-migration-hub-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Migration Hub Workflow\n  description: Workflow capability for Amazon Migration Hub media processing operations for broadcast engineers and media developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: migration_hub\n    location: ./shared/migration-hub.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: migration-hub-workflow-api\n    description: Unified REST API for Amazon Migration Hub workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: migration_hub.list-jobs\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: migration-hub-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Migration Hub workflow management.\n    tools:\n    - name: associate-created-artifact\n      description: AssociateCreatedArtifact\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.associate-created-artifact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: associate-discovered-resource\n      description: AssociateDiscoveredResource\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.associate-discovered-resource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-progress-update-stream\n      description: CreateProgressUpdateStream\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.create-progress-update-stream\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-progress-update-stream\n      description: DeleteProgressUpdateStream\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.delete-progress-update-stream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-application-state\n      description: DescribeApplicationState\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.describe-application-state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-migration-task\n      description: DescribeMigrationTask\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.describe-migration-task\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disassociate-created-artifact\n      description: DisassociateCreatedArtifact\n      hints:\n        readOnly:\
  \ false\n        openWorld: true\n      call: migration_hub.disassociate-created-artifact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disassociate-discovered-resource\n      description: DisassociateDiscoveredResource\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.disassociate-discovered-resource\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-migration-hub/refs/heads/main/capabilities/amazon-migration-hub-media-workflow.yaml
tags:
- Media
- Broadcasting
- Workflow
tools:
- description: AssociateCreatedArtifact
  hints:
    openWorld: true
    readOnly: false
  name: associate-created-artifact
- description: AssociateDiscoveredResource
  hints:
    openWorld: true
    readOnly: false
  name: associate-discovered-resource
- description: CreateProgressUpdateStream
  hints:
    openWorld: true
    readOnly: false
  name: create-progress-update-stream
- description: DeleteProgressUpdateStream
  hints:
    openWorld: true
    readOnly: false
  name: delete-progress-update-stream
- description: DescribeApplicationState
  hints:
    openWorld: true
    readOnly: false
  name: describe-application-state
- description: DescribeMigrationTask
  hints:
    openWorld: true
    readOnly: false
  name: describe-migration-task
- description: DisassociateCreatedArtifact
  hints:
    openWorld: true
    readOnly: false
  name: disassociate-created-artifact
- description: DisassociateDiscoveredResource
  hints:
    openWorld: true
    readOnly: false
  name: disassociate-discovered-resource
---
