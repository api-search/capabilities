---
categories: []
consumed_apis: []
description: The LlamaCloud API is the central REST API for LlamaIndex's cloud platform, providing programmatic access to managed document processing, indexing, and retrieval services. It enables developers to build production-grade LLM applications by leveraging cloud-hosted infrastructure for document ingestion, knowledge management, and agent orchestration. The API supports authentication via API keys and is available in both US and EU regions.
layout: capability
name: LlamaIndex LlamaCloud API
operations:
- description: List projects
  method: GET
  name: listprojects
  path: /projects
- description: Create a project
  method: POST
  name: createproject
  path: /projects
- description: Get a project
  method: GET
  name: getproject
  path: /projects/{projectId}
- description: Upload a file
  method: POST
  name: uploadfile
  path: /files
- description: List pipelines
  method: GET
  name: listpipelines
  path: /pipelines
- description: Create a pipeline
  method: POST
  name: createpipeline
  path: /pipelines
- description: Get a pipeline
  method: GET
  name: getpipeline
  path: /pipelines/{pipelineId}
- description: Delete a pipeline
  method: DELETE
  name: deletepipeline
  path: /pipelines/{pipelineId}
- description: Sync a pipeline
  method: POST
  name: syncpipeline
  path: /pipelines/{pipelineId}/sync
- description: Run search
  method: POST
  name: runsearch
  path: /pipelines/{pipelineId}/retrieve
- description: List pipeline files
  method: GET
  name: listpipelinefiles
  path: /pipelines/{pipelineId}/files
- description: Add files to a pipeline
  method: PUT
  name: addfilestopipeline
  path: /pipelines/{pipelineId}/files
- description: List pipeline data sources
  method: GET
  name: listpipelinedatasources
  path: /pipelines/{pipelineId}/data-sources
- description: Add data sources to a pipeline
  method: PUT
  name: adddatasourcestopipeline
  path: /pipelines/{pipelineId}/data-sources
- description: List pipeline data sinks
  method: GET
  name: listpipelinedatasinks
  path: /pipelines/{pipelineId}/data-sinks
- description: List pipeline jobs
  method: GET
  name: listpipelinejobs
  path: /pipelines/{pipelineId}/jobs
- description: List data sources
  method: GET
  name: listdatasources
  path: /data-sources
- description: Create a data source
  method: POST
  name: createdatasource
  path: /data-sources
personas: []
provider_name: llamaindex
provider_slug: llamaindex
search_terms:
- list pipeline data sources
- createdatasource
- add files to a pipeline
- list data sources
- listpipelinedatasinks
- sync a pipeline
- list pipelines
- create a project
- syncpipeline
- runsearch
- getproject
- run search
- listdatasources
- uploadfile
- deletepipeline
- listpipelinejobs
- createpipeline
- api
- listpipelinefiles
- list pipeline jobs
- listpipelinedatasources
- create a data source
- listpipelines
- listprojects
- list projects
- delete a pipeline
- getpipeline
- list pipeline data sinks
- create a pipeline
- add data sources to a pipeline
- llamaindex
- upload a file
- get a pipeline
- addfilestopipeline
- createproject
- list pipeline files
- get a project
- adddatasourcestopipeline
slug: llamaindex-capability
source_filename: llamaindex-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LlamaIndex LlamaCloud API\n  description: The LlamaCloud API is the central REST API for LlamaIndex's cloud platform, providing programmatic access to\n    managed document processing, indexing, and retrieval services. It enables developers to build production-grade LLM applications\n    by leveraging cloud-hosted infrastructure for document ingestion, knowledge management, and agent orchestration. The API\n    supports authentication via API keys and is available in both US and EU regions.\n  tags:\n  - Llamaindex\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: llamaindex\n    baseUri: https://api.cloud.llamaindex.ai/api/v1\n    description: LlamaIndex LlamaCloud API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LLAMAINDEX_TOKEN}}'\n    resources:\n    - name: projects\n      path: /projects\n      operations:\n      - name: listprojects\n    \
  \    method: GET\n        description: List projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Create a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid\n      path: /projects/{projectId}\n      operations:\n      - name: getproject\n        method: GET\n        description: Get a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files\n      path: /files\n      operations:\n      - name: uploadfile\n        method: POST\n        description: Upload a file\n        inputParameters:\n        - name: project_id\n          in: query\n          type: string\n          required: true\n          description: The project to associate\
  \ the file with.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines\n      path: /pipelines\n      operations:\n      - name: listpipelines\n        method: GET\n        description: List pipelines\n        inputParameters:\n        - name: project_id\n          in: query\n          type: string\n          required: true\n          description: Filter pipelines by project identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpipeline\n        method: POST\n        description: Create a pipeline\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines-pipelineid\n      path: /pipelines/{pipelineId}\n      operations:\n      - name: getpipeline\n        method: GET\n        description: Get a pipeline\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepipeline\n        method: DELETE\n        description: Delete a pipeline\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines-pipelineid-sync\n      path: /pipelines/{pipelineId}/sync\n      operations:\n      - name: syncpipeline\n        method: POST\n        description: Sync a pipeline\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines-pipelineid-retrieve\n      path: /pipelines/{pipelineId}/retrieve\n      operations:\n      - name: runsearch\n        method: POST\n        description: Run search\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines-pipelineid-files\n\
  \      path: /pipelines/{pipelineId}/files\n      operations:\n      - name: listpipelinefiles\n        method: GET\n        description: List pipeline files\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addfilestopipeline\n        method: PUT\n        description: Add files to a pipeline\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines-pipelineid-data-sources\n      path: /pipelines/{pipelineId}/data-sources\n      operations:\n      - name: listpipelinedatasources\n        method: GET\n        description: List pipeline data sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: adddatasourcestopipeline\n        method: PUT\n        description: Add data sources to a pipeline\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines-pipelineid-data-sinks\n      path: /pipelines/{pipelineId}/data-sinks\n      operations:\n      - name: listpipelinedatasinks\n        method: GET\n        description: List pipeline data sinks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines-pipelineid-jobs\n      path: /pipelines/{pipelineId}/jobs\n      operations:\n      - name: listpipelinejobs\n        method: GET\n        description: List pipeline jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-sources\n      path: /data-sources\n      operations:\n      - name: listdatasources\n        method: GET\n        description: List data sources\n        inputParameters:\n        - name: project_id\n          in:\
  \ query\n          type: string\n          required: true\n          description: Filter data sources by project identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdatasource\n        method: POST\n        description: Create a data source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: llamaindex-rest\n    description: REST adapter for LlamaIndex LlamaCloud API.\n    resources:\n    - path: /projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: List projects\n        call: llamaindex.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects\n      name: createproject\n      operations:\n      - method: POST\n        name:\
  \ createproject\n        description: Create a project\n        call: llamaindex.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Get a project\n        call: llamaindex.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files\n      name: uploadfile\n      operations:\n      - method: POST\n        name: uploadfile\n        description: Upload a file\n        call: llamaindex.uploadfile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines\n      name: listpipelines\n      operations:\n      - method: GET\n        name: listpipelines\n        description: List pipelines\n        call: llamaindex.listpipelines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines\n    \
  \  name: createpipeline\n      operations:\n      - method: POST\n        name: createpipeline\n        description: Create a pipeline\n        call: llamaindex.createpipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines/{pipelineId}\n      name: getpipeline\n      operations:\n      - method: GET\n        name: getpipeline\n        description: Get a pipeline\n        call: llamaindex.getpipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines/{pipelineId}\n      name: deletepipeline\n      operations:\n      - method: DELETE\n        name: deletepipeline\n        description: Delete a pipeline\n        call: llamaindex.deletepipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines/{pipelineId}/sync\n      name: syncpipeline\n      operations:\n      - method: POST\n        name: syncpipeline\n        description: Sync a pipeline\n  \
  \      call: llamaindex.syncpipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines/{pipelineId}/retrieve\n      name: runsearch\n      operations:\n      - method: POST\n        name: runsearch\n        description: Run search\n        call: llamaindex.runsearch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines/{pipelineId}/files\n      name: listpipelinefiles\n      operations:\n      - method: GET\n        name: listpipelinefiles\n        description: List pipeline files\n        call: llamaindex.listpipelinefiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines/{pipelineId}/files\n      name: addfilestopipeline\n      operations:\n      - method: PUT\n        name: addfilestopipeline\n        description: Add files to a pipeline\n        call: llamaindex.addfilestopipeline\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /pipelines/{pipelineId}/data-sources\n      name: listpipelinedatasources\n      operations:\n      - method: GET\n        name: listpipelinedatasources\n        description: List pipeline data sources\n        call: llamaindex.listpipelinedatasources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines/{pipelineId}/data-sources\n      name: adddatasourcestopipeline\n      operations:\n      - method: PUT\n        name: adddatasourcestopipeline\n        description: Add data sources to a pipeline\n        call: llamaindex.adddatasourcestopipeline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines/{pipelineId}/data-sinks\n      name: listpipelinedatasinks\n      operations:\n      - method: GET\n        name: listpipelinedatasinks\n        description: List pipeline data sinks\n        call: llamaindex.listpipelinedatasinks\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /pipelines/{pipelineId}/jobs\n      name: listpipelinejobs\n      operations:\n      - method: GET\n        name: listpipelinejobs\n        description: List pipeline jobs\n        call: llamaindex.listpipelinejobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /data-sources\n      name: listdatasources\n      operations:\n      - method: GET\n        name: listdatasources\n        description: List data sources\n        call: llamaindex.listdatasources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /data-sources\n      name: createdatasource\n      operations:\n      - method: POST\n        name: createdatasource\n        description: Create a data source\n        call: llamaindex.createdatasource\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: llamaindex-mcp\n    transport: http\n    description: MCP\
  \ adapter for LlamaIndex LlamaCloud API for AI agent use.\n    tools:\n    - name: listprojects\n      description: List projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: llamaindex.listprojects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproject\n      description: Create a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: llamaindex.createproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Get a project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: llamaindex.getproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadfile\n      description: Upload a file\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n  \
  \    call: llamaindex.uploadfile\n      with:\n        project_id: tools.project_id\n      inputParameters:\n      - name: project_id\n        type: string\n        description: The project to associate the file with.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpipelines\n      description: List pipelines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: llamaindex.listpipelines\n      with:\n        project_id: tools.project_id\n      inputParameters:\n      - name: project_id\n        type: string\n        description: Filter pipelines by project identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpipeline\n      description: Create a pipeline\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: llamaindex.createpipeline\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getpipeline\n      description: Get a pipeline\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: llamaindex.getpipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletepipeline\n      description: Delete a pipeline\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: llamaindex.deletepipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: syncpipeline\n      description: Sync a pipeline\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: llamaindex.syncpipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runsearch\n      description: Run search\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: llamaindex.runsearch\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpipelinefiles\n      description: List pipeline files\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: llamaindex.listpipelinefiles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addfilestopipeline\n      description: Add files to a pipeline\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: llamaindex.addfilestopipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpipelinedatasources\n      description: List pipeline data sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: llamaindex.listpipelinedatasources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adddatasourcestopipeline\n      description: Add data sources to a pipeline\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: llamaindex.adddatasourcestopipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpipelinedatasinks\n      description: List pipeline data sinks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: llamaindex.listpipelinedatasinks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpipelinejobs\n      description: List pipeline jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: llamaindex.listpipelinejobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatasources\n      description: List data sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: llamaindex.listdatasources\n      with:\n        project_id: tools.project_id\n\
  \      inputParameters:\n      - name: project_id\n        type: string\n        description: Filter data sources by project identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdatasource\n      description: Create a data source\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: llamaindex.createdatasource\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LLAMAINDEX_TOKEN: LLAMAINDEX_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/llamaindex/refs/heads/main/capabilities/llamaindex-capability.yaml
tags:
- Llamaindex
- API
tools:
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Create a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Get a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Upload a file
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadfile
- description: List pipelines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpipelines
- description: Create a pipeline
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpipeline
- description: Get a pipeline
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpipeline
- description: Delete a pipeline
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepipeline
- description: Sync a pipeline
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: syncpipeline
- description: Run search
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runsearch
- description: List pipeline files
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpipelinefiles
- description: Add files to a pipeline
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: addfilestopipeline
- description: List pipeline data sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpipelinedatasources
- description: Add data sources to a pipeline
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: adddatasourcestopipeline
- description: List pipeline data sinks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpipelinedatasinks
- description: List pipeline jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpipelinejobs
- description: List data sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatasources
- description: Create a data source
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatasource
---
