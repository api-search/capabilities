---
categories: []
consumed_apis: []
description: The Grapes API allows you to automate recurring operations on the Grapes knowledge management platform, including project administration, agent configuration, and dataset import/export. The API follows HATEOAS principles for link management between resources.
layout: capability
name: Grapes Knowledge Base API
operations:
- description: List projects
  method: GET
  name: get-projects
  path: /projects
- description: Create project
  method: POST
  name: post-projects
  path: /projects
- description: Get project
  method: GET
  name: get-projects-projectid
  path: /projects/{projectId}
- description: List agents
  method: GET
  name: get-agents
  path: /agents
- description: Create agent
  method: POST
  name: post-agents
  path: /agents
- description: List datasets
  method: GET
  name: get-datasets
  path: /datasets
- description: Export dataset
  method: GET
  name: get-datasets-datasetid-export
  path: /datasets/{datasetId}/export
- description: Import dataset
  method: POST
  name: post-datasets-import
  path: /datasets/import
personas: []
provider_name: Grapes Knowledge Base
provider_slug: grapes-knowledge-base
search_terms:
- export dataset
- post agents
- get datasets
- list datasets
- list agents
- knowledge management
- post projects
- get datasets datasetid export
- get projects projectid
- hateoas
- import dataset
- create project
- knowledge
- get projects
- base
- data management
- api
- grapes
- knowledge base
- get project
- list projects
- post datasets import
- get agents
- create agent
- automation
slug: grapes-knowledge-base-capability
source_filename: grapes-knowledge-base-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Grapes Knowledge Base API\n  description: The Grapes API allows you to automate recurring operations on the Grapes knowledge management platform, including\n    project administration, agent configuration, and dataset import/export. The API follows HATEOAS principles for link management\n    between resources.\n  tags:\n  - Grapes\n  - Knowledge\n  - Base\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: grapes-knowledge-base\n    baseUri: https://api.data-grapes.com\n    description: Grapes Knowledge Base API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GRAPES_KNOWLEDGE_BASE_TOKEN}}'\n    resources:\n    - name: projects\n      path: /projects\n      operations:\n      - name: get-projects\n        method: GET\n        description: List projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: post-projects\n        method: POST\n        description: Create project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid\n      path: /projects/{projectId}\n      operations:\n      - name: get-projects-projectid\n        method: GET\n        description: Get project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents\n      path: /agents\n      operations:\n      - name: get-agents\n        method: GET\n        description: List agents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-agents\n        method: POST\n        description:\
  \ Create agent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasets\n      path: /datasets\n      operations:\n      - name: get-datasets\n        method: GET\n        description: List datasets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasets-datasetid-export\n      path: /datasets/{datasetId}/export\n      operations:\n      - name: get-datasets-datasetid-export\n        method: GET\n        description: Export dataset\n        inputParameters:\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasets-import\n      path: /datasets/import\n      operations:\n      - name: post-datasets-import\n        method:\
  \ POST\n        description: Import dataset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: grapes-knowledge-base-rest\n    description: REST adapter for Grapes Knowledge Base API.\n    resources:\n    - path: /projects\n      name: get-projects\n      operations:\n      - method: GET\n        name: get-projects\n        description: List projects\n        call: grapes-knowledge-base.get-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects\n      name: post-projects\n      operations:\n      - method: POST\n        name: post-projects\n        description: Create project\n        call: grapes-knowledge-base.post-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}\n      name: get-projects-projectid\n      operations:\n      - method:\
  \ GET\n        name: get-projects-projectid\n        description: Get project\n        call: grapes-knowledge-base.get-projects-projectid\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agents\n      name: get-agents\n      operations:\n      - method: GET\n        name: get-agents\n        description: List agents\n        call: grapes-knowledge-base.get-agents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agents\n      name: post-agents\n      operations:\n      - method: POST\n        name: post-agents\n        description: Create agent\n        call: grapes-knowledge-base.post-agents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasets\n      name: get-datasets\n      operations:\n      - method: GET\n        name: get-datasets\n        description: List datasets\n        call: grapes-knowledge-base.get-datasets\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasets/{datasetId}/export\n      name: get-datasets-datasetid-export\n      operations:\n      - method: GET\n        name: get-datasets-datasetid-export\n        description: Export dataset\n        call: grapes-knowledge-base.get-datasets-datasetid-export\n        with:\n          datasetId: rest.datasetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasets/import\n      name: post-datasets-import\n      operations:\n      - method: POST\n        name: post-datasets-import\n        description: Import dataset\n        call: grapes-knowledge-base.post-datasets-import\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: grapes-knowledge-base-mcp\n    transport: http\n    description: MCP adapter for Grapes Knowledge Base API for AI agent use.\n    tools:\n    - name: get-projects\n    \
  \  description: List projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grapes-knowledge-base.get-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-projects\n      description: Create project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grapes-knowledge-base.post-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-projects-projectid\n      description: Get project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grapes-knowledge-base.get-projects-projectid\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-agents\n \
  \     description: List agents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grapes-knowledge-base.get-agents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-agents\n      description: Create agent\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grapes-knowledge-base.post-agents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-datasets\n      description: List datasets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grapes-knowledge-base.get-datasets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-datasets-datasetid-export\n      description: Export dataset\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grapes-knowledge-base.get-datasets-datasetid-export\n\
  \      with:\n        datasetId: tools.datasetId\n      inputParameters:\n      - name: datasetId\n        type: string\n        description: datasetId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-datasets-import\n      description: Import dataset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grapes-knowledge-base.post-datasets-import\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GRAPES_KNOWLEDGE_BASE_TOKEN: GRAPES_KNOWLEDGE_BASE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/grapes-knowledge-base/refs/heads/main/capabilities/grapes-knowledge-base-capability.yaml
tags:
- Grapes
- Knowledge
- Base
- API
tools:
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-projects
- description: Create project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-projects
- description: Get project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-projects-projectid
- description: List agents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agents
- description: Create agent
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agents
- description: List datasets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-datasets
- description: Export dataset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-datasets-datasetid-export
- description: Import dataset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-datasets-import
---
