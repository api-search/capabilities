---
categories: []
consumed_apis:
- entity_resolution
description: Unified capability for managing Amazon Entity Resolution resources. Combines Amazon Entity Resolution APIs for Data Analyst workflows in Data Quality.
layout: capability
name: Amazon Entity Resolution Management
operations:
- description: Amazon Entity Resolution ListMatchingWorkflows
  method: GET
  name: ListMatchingWorkflows
  path: /v1/ListMatchingWorkflows
- description: Amazon Entity Resolution CreateMatchingWorkflow
  method: POST
  name: CreateMatchingWorkflow
  path: /v1/CreateMatchingWorkflow
- description: Amazon Entity Resolution ListSchemaMappings
  method: GET
  name: ListSchemaMappings
  path: /v1/ListSchemaMappings
- description: Amazon Entity Resolution CreateSchemaMapping
  method: POST
  name: CreateSchemaMapping
  path: /v1/CreateSchemaMapping
- description: Amazon Entity Resolution GetMatchingWorkflow
  method: GET
  name: GetMatchingWorkflow
  path: /v1/GetMatchingWorkflow
- description: Amazon Entity Resolution UpdateMatchingWorkflow
  method: POST
  name: UpdateMatchingWorkflow
  path: /v1/UpdateMatchingWorkflow
- description: Amazon Entity Resolution DeleteMatchingWorkflow
  method: POST
  name: DeleteMatchingWorkflow
  path: /v1/DeleteMatchingWorkflow
- description: Amazon Entity Resolution GetSchemaMapping
  method: GET
  name: GetSchemaMapping
  path: /v1/GetSchemaMapping
- description: Amazon Entity Resolution DeleteSchemaMapping
  method: POST
  name: DeleteSchemaMapping
  path: /v1/DeleteSchemaMapping
- description: Amazon Entity Resolution GetMatchId
  method: POST
  name: GetMatchId
  path: /v1/GetMatchId
- description: Amazon Entity Resolution GetMatchingJob
  method: GET
  name: GetMatchingJob
  path: /v1/GetMatchingJob
- description: Amazon Entity Resolution ListMatchingJobs
  method: GET
  name: ListMatchingJobs
  path: /v1/ListMatchingJobs
- description: Amazon Entity Resolution StartMatchingJob
  method: POST
  name: StartMatchingJob
  path: /v1/StartMatchingJob
- description: Amazon Entity Resolution ListTagsForResource
  method: GET
  name: ListTagsForResource
  path: /v1/ListTagsForResource
- description: Amazon Entity Resolution TagResource
  method: POST
  name: TagResource
  path: /v1/TagResource
personas: []
provider_name: Amazon Entity Resolution
provider_slug: amazon-entity-resolution
search_terms:
- StartMatchingJob
- developers building applications using amazon entity resolution
- amazon entity resolution getmatchingworkflow
- amazon entity resolution deleteschemamapping
- GetSchemaMapping
- operations teams managing amazon entity resolution infrastructure
- amazon entity resolution createschemamapping
- amazon entity resolution startmatchingjob
- data matching
- amazon entity resolution getmatchid
- GetMatchingWorkflow
- machine learning
- amazon entity resolution deletematchingworkflow
- amazon entity resolution getschemamapping
- GetMatchId
- amazon entity resolution listmatchingworkflows
- amazon entity resolution getmatchingjob
- unified capability for managing amazon entity resolution resources. combines amazon entity resolution apis for data analyst workflows in data quality.
- UntagResource
- machine learning service for matching and linking related records
- ListMatchingWorkflows
- DeleteSchemaMapping
- amazon entity resolution tagresource
- amazon web services
- amazon entity resolution updatematchingworkflow
- amazon entity resolution creatematchingworkflow
- UpdateMatchingWorkflow
- data integration
- amazon entity resolution listtagsforresource
- ListTagsForResource
- amazon entity resolution listmatchingjobs
- TagResource
- DeleteMatchingWorkflow
- amazon entity resolution listschemamappings
- ListSchemaMappings
- ListMatchingJobs
- CreateSchemaMapping
- amazon entity resolution untagresource
- GetMatchingJob
- CreateMatchingWorkflow
- entity resolution
slug: amazon-entity-resolution-capability
source_filename: amazon-entity-resolution-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Entity Resolution Management\n  description: Unified capability for managing Amazon Entity Resolution resources. Combines Amazon Entity Resolution APIs for Data Analyst workflows in Data Quality.\n  tags:\n  - Amazon Web Services\n  - Data Integration\n  - Machine Learning\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_API_KEY: AWS_API_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: entity_resolution\n    location: ./shared/entity-resolution.yaml\n  exposes:\n  - type: rest\n    port: 8190\n    namespace: amazon-entity-resolution-workflow-api\n    description: Unified REST API for Amazon Entity Resolution management.\n    resources:\n    - path: /v1/ListMatchingWorkflows\n      name: ListMatchingWorkflows\n      description: Amazon Entity Resolution ListMatchingWorkflows\n      operations:\n      - method: GET\n        name: ListMatchingWorkflows\n        description:\
  \ Amazon Entity Resolution ListMatchingWorkflows\n        call: api.ListMatchingWorkflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateMatchingWorkflow\n      name: CreateMatchingWorkflow\n      description: Amazon Entity Resolution CreateMatchingWorkflow\n      operations:\n      - method: POST\n        name: CreateMatchingWorkflow\n        description: Amazon Entity Resolution CreateMatchingWorkflow\n        call: api.CreateMatchingWorkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListSchemaMappings\n      name: ListSchemaMappings\n      description: Amazon Entity Resolution ListSchemaMappings\n      operations:\n      - method: GET\n        name: ListSchemaMappings\n        description: Amazon Entity Resolution ListSchemaMappings\n        call: api.ListSchemaMappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/CreateSchemaMapping\n    \
  \  name: CreateSchemaMapping\n      description: Amazon Entity Resolution CreateSchemaMapping\n      operations:\n      - method: POST\n        name: CreateSchemaMapping\n        description: Amazon Entity Resolution CreateSchemaMapping\n        call: api.CreateSchemaMapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/GetMatchingWorkflow\n      name: GetMatchingWorkflow\n      description: Amazon Entity Resolution GetMatchingWorkflow\n      operations:\n      - method: GET\n        name: GetMatchingWorkflow\n        description: Amazon Entity Resolution GetMatchingWorkflow\n        call: api.GetMatchingWorkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/UpdateMatchingWorkflow\n      name: UpdateMatchingWorkflow\n      description: Amazon Entity Resolution UpdateMatchingWorkflow\n      operations:\n      - method: POST\n        name: UpdateMatchingWorkflow\n        description: Amazon Entity Resolution\
  \ UpdateMatchingWorkflow\n        call: api.UpdateMatchingWorkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/DeleteMatchingWorkflow\n      name: DeleteMatchingWorkflow\n      description: Amazon Entity Resolution DeleteMatchingWorkflow\n      operations:\n      - method: POST\n        name: DeleteMatchingWorkflow\n        description: Amazon Entity Resolution DeleteMatchingWorkflow\n        call: api.DeleteMatchingWorkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/GetSchemaMapping\n      name: GetSchemaMapping\n      description: Amazon Entity Resolution GetSchemaMapping\n      operations:\n      - method: GET\n        name: GetSchemaMapping\n        description: Amazon Entity Resolution GetSchemaMapping\n        call: api.GetSchemaMapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/DeleteSchemaMapping\n      name: DeleteSchemaMapping\n      description:\
  \ Amazon Entity Resolution DeleteSchemaMapping\n      operations:\n      - method: POST\n        name: DeleteSchemaMapping\n        description: Amazon Entity Resolution DeleteSchemaMapping\n        call: api.DeleteSchemaMapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/GetMatchId\n      name: GetMatchId\n      description: Amazon Entity Resolution GetMatchId\n      operations:\n      - method: POST\n        name: GetMatchId\n        description: Amazon Entity Resolution GetMatchId\n        call: api.GetMatchId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/GetMatchingJob\n      name: GetMatchingJob\n      description: Amazon Entity Resolution GetMatchingJob\n      operations:\n      - method: GET\n        name: GetMatchingJob\n        description: Amazon Entity Resolution GetMatchingJob\n        call: api.GetMatchingJob\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/ListMatchingJobs\n      name: ListMatchingJobs\n      description: Amazon Entity Resolution ListMatchingJobs\n      operations:\n      - method: GET\n        name: ListMatchingJobs\n        description: Amazon Entity Resolution ListMatchingJobs\n        call: api.ListMatchingJobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/StartMatchingJob\n      name: StartMatchingJob\n      description: Amazon Entity Resolution StartMatchingJob\n      operations:\n      - method: POST\n        name: StartMatchingJob\n        description: Amazon Entity Resolution StartMatchingJob\n        call: api.StartMatchingJob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ListTagsForResource\n      name: ListTagsForResource\n      description: Amazon Entity Resolution ListTagsForResource\n      operations:\n      - method: GET\n        name: ListTagsForResource\n        description: Amazon Entity Resolution\
  \ ListTagsForResource\n        call: api.ListTagsForResource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/TagResource\n      name: TagResource\n      description: Amazon Entity Resolution TagResource\n      operations:\n      - method: POST\n        name: TagResource\n        description: Amazon Entity Resolution TagResource\n        call: api.TagResource\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9200\n    namespace: amazon-entity-resolution-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Entity Resolution management.\n    tools:\n    - name: ListMatchingWorkflows\n      description: Amazon Entity Resolution ListMatchingWorkflows\n      hints:\n        readOnly: true\n      call: api.ListMatchingWorkflows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: CreateMatchingWorkflow\n      description: Amazon Entity Resolution CreateMatchingWorkflow\n\
  \      hints:\n        readOnly: false\n      call: api.CreateMatchingWorkflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListSchemaMappings\n      description: Amazon Entity Resolution ListSchemaMappings\n      hints:\n        readOnly: true\n      call: api.ListSchemaMappings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: CreateSchemaMapping\n      description: Amazon Entity Resolution CreateSchemaMapping\n      hints:\n        readOnly: false\n      call: api.CreateSchemaMapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: GetMatchingWorkflow\n      description: Amazon Entity Resolution GetMatchingWorkflow\n      hints:\n        readOnly: true\n      call: api.GetMatchingWorkflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: UpdateMatchingWorkflow\n      description: Amazon Entity Resolution UpdateMatchingWorkflow\n      hints:\n        readOnly:\
  \ false\n      call: api.UpdateMatchingWorkflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: DeleteMatchingWorkflow\n      description: Amazon Entity Resolution DeleteMatchingWorkflow\n      hints:\n        readOnly: false\n      call: api.DeleteMatchingWorkflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: GetSchemaMapping\n      description: Amazon Entity Resolution GetSchemaMapping\n      hints:\n        readOnly: true\n      call: api.GetSchemaMapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: DeleteSchemaMapping\n      description: Amazon Entity Resolution DeleteSchemaMapping\n      hints:\n        readOnly: false\n      call: api.DeleteSchemaMapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: GetMatchId\n      description: Amazon Entity Resolution GetMatchId\n      hints:\n        readOnly: false\n      call: api.GetMatchId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: GetMatchingJob\n      description: Amazon Entity Resolution GetMatchingJob\n      hints:\n        readOnly: true\n      call: api.GetMatchingJob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListMatchingJobs\n      description: Amazon Entity Resolution ListMatchingJobs\n      hints:\n        readOnly: true\n      call: api.ListMatchingJobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: StartMatchingJob\n      description: Amazon Entity Resolution StartMatchingJob\n      hints:\n        readOnly: false\n      call: api.StartMatchingJob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ListTagsForResource\n      description: Amazon Entity Resolution ListTagsForResource\n      hints:\n        readOnly: true\n      call: api.ListTagsForResource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: TagResource\n\
  \      description: Amazon Entity Resolution TagResource\n      hints:\n        readOnly: false\n      call: api.TagResource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: UntagResource\n      description: Amazon Entity Resolution UntagResource\n      hints:\n        readOnly: false\n      call: api.UntagResource\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-entity-resolution/refs/heads/main/capabilities/amazon-entity-resolution-capability.yaml
tags:
- Amazon Web Services
- Data Integration
- Machine Learning
tools:
- description: Amazon Entity Resolution ListMatchingWorkflows
  hints:
    readOnly: true
  name: ListMatchingWorkflows
- description: Amazon Entity Resolution CreateMatchingWorkflow
  hints:
    readOnly: false
  name: CreateMatchingWorkflow
- description: Amazon Entity Resolution ListSchemaMappings
  hints:
    readOnly: true
  name: ListSchemaMappings
- description: Amazon Entity Resolution CreateSchemaMapping
  hints:
    readOnly: false
  name: CreateSchemaMapping
- description: Amazon Entity Resolution GetMatchingWorkflow
  hints:
    readOnly: true
  name: GetMatchingWorkflow
- description: Amazon Entity Resolution UpdateMatchingWorkflow
  hints:
    readOnly: false
  name: UpdateMatchingWorkflow
- description: Amazon Entity Resolution DeleteMatchingWorkflow
  hints:
    readOnly: false
  name: DeleteMatchingWorkflow
- description: Amazon Entity Resolution GetSchemaMapping
  hints:
    readOnly: true
  name: GetSchemaMapping
- description: Amazon Entity Resolution DeleteSchemaMapping
  hints:
    readOnly: false
  name: DeleteSchemaMapping
- description: Amazon Entity Resolution GetMatchId
  hints:
    readOnly: false
  name: GetMatchId
- description: Amazon Entity Resolution GetMatchingJob
  hints:
    readOnly: true
  name: GetMatchingJob
- description: Amazon Entity Resolution ListMatchingJobs
  hints:
    readOnly: true
  name: ListMatchingJobs
- description: Amazon Entity Resolution StartMatchingJob
  hints:
    readOnly: false
  name: StartMatchingJob
- description: Amazon Entity Resolution ListTagsForResource
  hints:
    readOnly: true
  name: ListTagsForResource
- description: Amazon Entity Resolution TagResource
  hints:
    readOnly: false
  name: TagResource
- description: Amazon Entity Resolution UntagResource
  hints:
    readOnly: false
  name: UntagResource
---
