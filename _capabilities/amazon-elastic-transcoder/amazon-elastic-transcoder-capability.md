---
categories: []
consumed_apis:
- elastic_transcoder
description: Unified capability for managing Amazon Elastic Transcoder resources. Combines Amazon Elastic Transcoder APIs for Media Engineer workflows in Media Processing.
layout: capability
name: Amazon Elastic Transcoder Management
operations:
- description: Amazon Elastic Transcoder ReadJob
  method: GET
  name: ReadJob
  path: /v1/ReadJob
- description: Amazon Elastic Transcoder CancelJob
  method: POST
  name: CancelJob
  path: /v1/CancelJob
- description: Amazon Elastic Transcoder CreateJob
  method: POST
  name: CreateJob
  path: /v1/CreateJob
- description: Amazon Elastic Transcoder ListPipelines
  method: GET
  name: ListPipelines
  path: /v1/ListPipelines
- description: Amazon Elastic Transcoder CreatePipeline
  method: POST
  name: CreatePipeline
  path: /v1/CreatePipeline
- description: Amazon Elastic Transcoder ListPresets
  method: GET
  name: ListPresets
  path: /v1/ListPresets
- description: Amazon Elastic Transcoder CreatePreset
  method: POST
  name: CreatePreset
  path: /v1/CreatePreset
- description: Amazon Elastic Transcoder ReadPipeline
  method: GET
  name: ReadPipeline
  path: /v1/ReadPipeline
- description: Amazon Elastic Transcoder UpdatePipeline
  method: POST
  name: UpdatePipeline
  path: /v1/UpdatePipeline
- description: Amazon Elastic Transcoder DeletePipeline
  method: POST
  name: DeletePipeline
  path: /v1/DeletePipeline
- description: Amazon Elastic Transcoder ReadPreset
  method: GET
  name: ReadPreset
  path: /v1/ReadPreset
- description: Amazon Elastic Transcoder DeletePreset
  method: POST
  name: DeletePreset
  path: /v1/DeletePreset
- description: Amazon Elastic Transcoder ListJobsByPipeline
  method: GET
  name: ListJobsByPipeline
  path: /v1/ListJobsByPipeline
- description: Amazon Elastic Transcoder ListJobsByStatus
  method: GET
  name: ListJobsByStatus
  path: /v1/ListJobsByStatus
- description: Amazon Elastic Transcoder TestRole
  method: POST
  name: TestRole
  path: /v1/TestRole
personas: []
provider_name: Amazon Elastic Transcoder
provider_slug: amazon-elastic-transcoder
search_terms:
- video
- UpdatePipelineNotifications
- ReadJob
- ReadPipeline
- CreateJob
- DeletePreset
- amazon elastic transcoder deletepipeline
- amazon elastic transcoder updatepipelinenotifications
- operations teams managing amazon elastic transcoder infrastructure
- media
- ListJobsByPipeline
- amazon elastic transcoder listpresets
- TestRole
- amazon elastic transcoder createpipeline
- UpdatePipeline
- media transcoding service for converting media files to various formats
- ListPresets
- developers building applications using amazon elastic transcoder
- amazon elastic transcoder createjob
- amazon elastic transcoder listjobsbystatus
- transcoding
- amazon elastic transcoder listpipelines
- amazon elastic transcoder readpreset
- amazon elastic transcoder updatepipelinestatus
- amazon web services
- amazon elastic transcoder readjob
- unified capability for managing amazon elastic transcoder resources. combines amazon elastic transcoder apis for media engineer workflows in media processing.
- amazon elastic transcoder createpreset
- UpdatePipelineStatus
- CreatePreset
- aws
- amazon elastic transcoder canceljob
- ListJobsByStatus
- amazon elastic transcoder deletepreset
- ReadPreset
- amazon elastic transcoder listjobsbypipeline
- CreatePipeline
- amazon elastic transcoder updatepipeline
- DeletePipeline
- amazon elastic transcoder testrole
- CancelJob
- amazon elastic transcoder readpipeline
- ListPipelines
slug: amazon-elastic-transcoder-capability
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Elastic Transcoder Management\n  description: Unified capability for managing Amazon Elastic Transcoder resources. Combines Amazon Elastic Transcoder APIs for Media Engineer workflows in Media Processing.\n  tags:\n  - Amazon Web Services\n  - Media\n  - Transcoding\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_API_KEY: AWS_API_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: elastic_transcoder\n    location: ./shared/elastic-transcoder.yaml\n  exposes:\n  - type: rest\n    port: 8184\n    namespace: amazon-elastic-transcoder-workflow-api\n    description: Unified REST API for Amazon Elastic Transcoder management.\n    resources:\n    - path: /v1/ReadJob\n      name: ReadJob\n      description: Amazon Elastic Transcoder ReadJob\n      operations:\n      - method: GET\n        name: ReadJob\n        description: Amazon Elastic Transcoder ReadJob\n        call:\
  \ api.ReadJob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CancelJob\n      name: CancelJob\n      description: Amazon Elastic Transcoder CancelJob\n      operations:\n      - method: POST\n        name: CancelJob\n        description: Amazon Elastic Transcoder CancelJob\n        call: api.CancelJob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateJob\n      name: CreateJob\n      description: Amazon Elastic Transcoder CreateJob\n      operations:\n      - method: POST\n        name: CreateJob\n        description: Amazon Elastic Transcoder CreateJob\n        call: api.CreateJob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListPipelines\n      name: ListPipelines\n      description: Amazon Elastic Transcoder ListPipelines\n      operations:\n      - method: GET\n        name: ListPipelines\n        description: Amazon Elastic Transcoder ListPipelines\n\
  \        call: api.ListPipelines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreatePipeline\n      name: CreatePipeline\n      description: Amazon Elastic Transcoder CreatePipeline\n      operations:\n      - method: POST\n        name: CreatePipeline\n        description: Amazon Elastic Transcoder CreatePipeline\n        call: api.CreatePipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListPresets\n      name: ListPresets\n      description: Amazon Elastic Transcoder ListPresets\n      operations:\n      - method: GET\n        name: ListPresets\n        description: Amazon Elastic Transcoder ListPresets\n        call: api.ListPresets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreatePreset\n      name: CreatePreset\n      description: Amazon Elastic Transcoder CreatePreset\n      operations:\n      - method: POST\n        name: CreatePreset\n\
  \        description: Amazon Elastic Transcoder CreatePreset\n        call: api.CreatePreset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ReadPipeline\n      name: ReadPipeline\n      description: Amazon Elastic Transcoder ReadPipeline\n      operations:\n      - method: GET\n        name: ReadPipeline\n        description: Amazon Elastic Transcoder ReadPipeline\n        call: api.ReadPipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/UpdatePipeline\n      name: UpdatePipeline\n      description: Amazon Elastic Transcoder UpdatePipeline\n      operations:\n      - method: POST\n        name: UpdatePipeline\n        description: Amazon Elastic Transcoder UpdatePipeline\n        call: api.UpdatePipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/DeletePipeline\n      name: DeletePipeline\n      description: Amazon Elastic Transcoder DeletePipeline\n\
  \      operations:\n      - method: POST\n        name: DeletePipeline\n        description: Amazon Elastic Transcoder DeletePipeline\n        call: api.DeletePipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ReadPreset\n      name: ReadPreset\n      description: Amazon Elastic Transcoder ReadPreset\n      operations:\n      - method: GET\n        name: ReadPreset\n        description: Amazon Elastic Transcoder ReadPreset\n        call: api.ReadPreset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/DeletePreset\n      name: DeletePreset\n      description: Amazon Elastic Transcoder DeletePreset\n      operations:\n      - method: POST\n        name: DeletePreset\n        description: Amazon Elastic Transcoder DeletePreset\n        call: api.DeletePreset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListJobsByPipeline\n      name: ListJobsByPipeline\n\
  \      description: Amazon Elastic Transcoder ListJobsByPipeline\n      operations:\n      - method: GET\n        name: ListJobsByPipeline\n        description: Amazon Elastic Transcoder ListJobsByPipeline\n        call: api.ListJobsByPipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListJobsByStatus\n      name: ListJobsByStatus\n      description: Amazon Elastic Transcoder ListJobsByStatus\n      operations:\n      - method: GET\n        name: ListJobsByStatus\n        description: Amazon Elastic Transcoder ListJobsByStatus\n        call: api.ListJobsByStatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/TestRole\n      name: TestRole\n      description: Amazon Elastic Transcoder TestRole\n      operations:\n      - method: POST\n        name: TestRole\n        description: Amazon Elastic Transcoder TestRole\n        call: api.TestRole\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n  - type: mcp\n    port: 9194\n    namespace: amazon-elastic-transcoder-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Elastic Transcoder management.\n    tools:\n    - name: ReadJob\n      description: Amazon Elastic Transcoder ReadJob\n      hints:\n        readOnly: true\n      call: api.ReadJob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: CancelJob\n      description: Amazon Elastic Transcoder CancelJob\n      hints:\n        readOnly: false\n      call: api.CancelJob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: CreateJob\n      description: Amazon Elastic Transcoder CreateJob\n      hints:\n        readOnly: false\n      call: api.CreateJob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListPipelines\n      description: Amazon Elastic Transcoder ListPipelines\n      hints:\n        readOnly: true\n      call: api.ListPipelines\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: CreatePipeline\n      description: Amazon Elastic Transcoder CreatePipeline\n      hints:\n        readOnly: false\n      call: api.CreatePipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListPresets\n      description: Amazon Elastic Transcoder ListPresets\n      hints:\n        readOnly: true\n      call: api.ListPresets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: CreatePreset\n      description: Amazon Elastic Transcoder CreatePreset\n      hints:\n        readOnly: false\n      call: api.CreatePreset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ReadPipeline\n      description: Amazon Elastic Transcoder ReadPipeline\n      hints:\n        readOnly: true\n      call: api.ReadPipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: UpdatePipeline\n      description:\
  \ Amazon Elastic Transcoder UpdatePipeline\n      hints:\n        readOnly: false\n      call: api.UpdatePipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: DeletePipeline\n      description: Amazon Elastic Transcoder DeletePipeline\n      hints:\n        readOnly: false\n      call: api.DeletePipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ReadPreset\n      description: Amazon Elastic Transcoder ReadPreset\n      hints:\n        readOnly: true\n      call: api.ReadPreset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: DeletePreset\n      description: Amazon Elastic Transcoder DeletePreset\n      hints:\n        readOnly: false\n      call: api.DeletePreset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListJobsByPipeline\n      description: Amazon Elastic Transcoder ListJobsByPipeline\n      hints:\n        readOnly: true\n      call: api.ListJobsByPipeline\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListJobsByStatus\n      description: Amazon Elastic Transcoder ListJobsByStatus\n      hints:\n        readOnly: true\n      call: api.ListJobsByStatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: TestRole\n      description: Amazon Elastic Transcoder TestRole\n      hints:\n        readOnly: false\n      call: api.TestRole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: UpdatePipelineNotifications\n      description: Amazon Elastic Transcoder UpdatePipelineNotifications\n      hints:\n        readOnly: false\n      call: api.UpdatePipelineNotifications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: UpdatePipelineStatus\n      description: Amazon Elastic Transcoder UpdatePipelineStatus\n      hints:\n        readOnly: false\n      call: api.UpdatePipelineStatus\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-elastic-transcoder/refs/heads/main/capabilities/amazon-elastic-transcoder-capability.yaml
tags:
- Amazon Web Services
- Media
- Transcoding
tools:
- description: Amazon Elastic Transcoder ReadJob
  hints:
    readOnly: true
  name: ReadJob
- description: Amazon Elastic Transcoder CancelJob
  hints:
    readOnly: false
  name: CancelJob
- description: Amazon Elastic Transcoder CreateJob
  hints:
    readOnly: false
  name: CreateJob
- description: Amazon Elastic Transcoder ListPipelines
  hints:
    readOnly: true
  name: ListPipelines
- description: Amazon Elastic Transcoder CreatePipeline
  hints:
    readOnly: false
  name: CreatePipeline
- description: Amazon Elastic Transcoder ListPresets
  hints:
    readOnly: true
  name: ListPresets
- description: Amazon Elastic Transcoder CreatePreset
  hints:
    readOnly: false
  name: CreatePreset
- description: Amazon Elastic Transcoder ReadPipeline
  hints:
    readOnly: true
  name: ReadPipeline
- description: Amazon Elastic Transcoder UpdatePipeline
  hints:
    readOnly: false
  name: UpdatePipeline
- description: Amazon Elastic Transcoder DeletePipeline
  hints:
    readOnly: false
  name: DeletePipeline
- description: Amazon Elastic Transcoder ReadPreset
  hints:
    readOnly: true
  name: ReadPreset
- description: Amazon Elastic Transcoder DeletePreset
  hints:
    readOnly: false
  name: DeletePreset
- description: Amazon Elastic Transcoder ListJobsByPipeline
  hints:
    readOnly: true
  name: ListJobsByPipeline
- description: Amazon Elastic Transcoder ListJobsByStatus
  hints:
    readOnly: true
  name: ListJobsByStatus
- description: Amazon Elastic Transcoder TestRole
  hints:
    readOnly: false
  name: TestRole
- description: Amazon Elastic Transcoder UpdatePipelineNotifications
  hints:
    readOnly: false
  name: UpdatePipelineNotifications
- description: Amazon Elastic Transcoder UpdatePipelineStatus
  hints:
    readOnly: false
  name: UpdatePipelineStatus
---
