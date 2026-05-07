---
categories: []
consumed_apis: []
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
- associate created artifact
- disassociate discovered resource
- describe migration task
- disassociatecreatedartifact
- describeapplicationstate
- developer building media processing applications
- engineer managing broadcast media workflows
- describemigrationtask
- create progress update stream
- createprogressupdatestream
- Media Developer
- amazon migration hub media processing workflow
- workflow
- disassociatediscoveredresource
- aws media processing and delivery
- list jobs
- deleteprogressupdatestream
- delete progress update stream
- manage media processing jobs
- media
- disassociate created artifact
- media processing
- aws
- broadcasting
- Broadcast Engineer
- associatecreatedartifact
- describe application state
- associate discovered resource
- associatediscoveredresource
slug: amazon-migration-hub-media-workflow
source_filename: amazon-migration-hub-media-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Migration Hub Workflow\n  description: Workflow capability for Amazon Migration Hub media processing operations for broadcast engineers and media\n    developers.\n  tags:\n  - AWS\n  - Media\n  - Broadcasting\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: migration_hub\n    baseUri: http://mgh.{region}.amazonaws.com\n    description: Amazon Migration Hub REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: default\n      path: /\n      description: Amazon Migration Hub resources\n      operations:\n      - name: associate-created-artifact\n        method: POST\n        description: AssociateCreatedArtifact\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: associate-discovered-resource\n        method: POST\n        description: AssociateDiscoveredResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: create-progress-update-stream\n        method: POST\n        description: CreateProgressUpdateStream\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: delete-progress-update-stream\n        method: POST\n        description: DeleteProgressUpdateStream\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: describe-application-state\n        method: POST\n        description: DescribeApplicationState\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n\
  \        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: describe-migration-task\n        method: POST\n        description: DescribeMigrationTask\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: disassociate-created-artifact\n        method: POST\n        description: DisassociateCreatedArtifact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n  \
  \        required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: disassociate-discovered-resource\n        method: POST\n        description: DisassociateDiscoveredResource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: import-migration-task\n        method: POST\n        description: ImportMigrationTask\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n\
  \          type: json\n          data: {}\n      - name: list-application-states\n        method: POST\n        description: ListApplicationStates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: list-created-artifacts\n        method: POST\n        description: ListCreatedArtifacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        inputParameters:\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: list-discovered-resources\n        method: POST\n        description: ListDiscoveredResources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required:\
  \ false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: list-migration-tasks\n        method: POST\n        description: ListMigrationTasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: list-progress-update-streams\n\
  \        method: POST\n        description: ListProgressUpdateStreams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: MaxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: notify-application-state\n        method: POST\n        description: NotifyApplicationState\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n        \
  \  in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: notify-migration-task-state\n        method: POST\n        description: NotifyMigrationTaskState\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: X-Amz-Target\n        body:\n          type: json\n          data: {}\n      - name: put-resource-attributes\n        method: POST\n        description: PutResourceAttributes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description:\
  \ X-Amz-Target\n        body:\n          type: json\n          data: {}\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: migration-hub-workflow-api\n    description: Unified REST API for Amazon Migration Hub workflow management.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n      description: Manage media processing jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs\n        call: migration_hub.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: migration-hub-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Migration Hub workflow management.\n    tools:\n    - name: associate-created-artifact\n      description: AssociateCreatedArtifact\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.associate-created-artifact\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: associate-discovered-resource\n      description: AssociateDiscoveredResource\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.associate-discovered-resource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-progress-update-stream\n      description: CreateProgressUpdateStream\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.create-progress-update-stream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-progress-update-stream\n      description: DeleteProgressUpdateStream\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.delete-progress-update-stream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-application-state\n      description: DescribeApplicationState\n      hints:\n        readOnly: false\n        openWorld:\
  \ true\n      call: migration_hub.describe-application-state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-migration-task\n      description: DescribeMigrationTask\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.describe-migration-task\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disassociate-created-artifact\n      description: DisassociateCreatedArtifact\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.disassociate-created-artifact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disassociate-discovered-resource\n      description: DisassociateDiscoveredResource\n      hints:\n        readOnly: false\n        openWorld: true\n      call: migration_hub.disassociate-discovered-resource\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
