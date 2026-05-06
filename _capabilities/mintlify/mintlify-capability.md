---
categories: []
consumed_apis: []
description: Mintlify provides a suite of APIs for managing documentation deployments, automating documentation editing through agents, embedding AI assistants, and exporting analytics. Endpoints span the Update, Agent, Assistant, and Analytics APIs.
layout: capability
name: Mintlify API
operations:
- description: Trigger documentation update
  method: POST
  name: triggerupdate
  path: /v1/project/update/{projectId}
- description: Get update status
  method: GET
  name: getupdatestatus
  path: /v1/project/update-status/{statusId}
- description: Create agent job
  method: POST
  name: createagentjob
  path: /v1/agent/{projectId}/job
- description: Get agent job
  method: GET
  name: getagentjob
  path: /v1/agent/{projectId}/job/{id}
- description: Create assistant message
  method: POST
  name: createassistantmessage
  path: /discovery/v2/assistant/{domain}/message
- description: Search documentation
  method: POST
  name: searchdocs
  path: /discovery/v1/search/{domain}
- description: Get user feedback
  method: GET
  name: getfeedback
  path: /v1/analytics/feedback
- description: Get assistant conversations
  method: GET
  name: getconversations
  path: /v1/analytics/conversations
personas: []
provider_name: Mintlify
provider_slug: mintlify
search_terms:
- getconversations
- getagentjob
- createassistantmessage
- searchdocs
- triggerupdate
- mintlify
- create assistant message
- documentation
- get update status
- trigger documentation update
- api
- create agent job
- getupdatestatus
- search documentation
- get user feedback
- getfeedback
- get assistant conversations
- createagentjob
- get agent job
slug: mintlify-capability
source_filename: mintlify-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mintlify API\n  description: Mintlify provides a suite of APIs for managing documentation deployments, automating documentation editing\n    through agents, embedding AI assistants, and exporting analytics. Endpoints span the Update, Agent, Assistant, and Analytics\n    APIs.\n  tags:\n  - Mintlify\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: mintlify\n    baseUri: https://api.mintlify.com\n    description: Mintlify API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MINTLIFY_TOKEN}}'\n    resources:\n    - name: v1-project-update-projectid\n      path: /v1/project/update/{projectId}\n      operations:\n      - name: triggerupdate\n        method: POST\n        description: Trigger documentation update\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-project-update-status-statusid\n      path: /v1/project/update-status/{statusId}\n      operations:\n      - name: getupdatestatus\n        method: GET\n        description: Get update status\n        inputParameters:\n        - name: statusId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-agent-projectid-job\n      path: /v1/agent/{projectId}/job\n      operations:\n      - name: createagentjob\n        method: POST\n        description: Create agent job\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: v1-agent-projectid-job-id\n      path: /v1/agent/{projectId}/job/{id}\n      operations:\n      - name: getagentjob\n        method: GET\n        description: Get agent job\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: discovery-v2-assistant-domain-message\n      path: /discovery/v2/assistant/{domain}/message\n      operations:\n      - name: createassistantmessage\n        method: POST\n        description: Create assistant message\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: discovery-v1-search-domain\n      path: /discovery/v1/search/{domain}\n      operations:\n      - name: searchdocs\n        method: POST\n        description: Search documentation\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-analytics-feedback\n      path: /v1/analytics/feedback\n      operations:\n      - name: getfeedback\n        method: GET\n        description: Get user feedback\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-analytics-conversations\n      path: /v1/analytics/conversations\n      operations:\n      - name: getconversations\n        method: GET\n        description: Get assistant conversations\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mintlify-rest\n    description: REST adapter for Mintlify API.\n    resources:\n    - path: /v1/project/update/{projectId}\n      name: triggerupdate\n      operations:\n      - method: POST\n        name: triggerupdate\n        description: Trigger documentation update\n        call: mintlify.triggerupdate\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/project/update-status/{statusId}\n      name: getupdatestatus\n      operations:\n      - method: GET\n        name: getupdatestatus\n        description: Get update status\n        call: mintlify.getupdatestatus\n        with:\n          statusId: rest.statusId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/agent/{projectId}/job\n      name: createagentjob\n      operations:\n\
  \      - method: POST\n        name: createagentjob\n        description: Create agent job\n        call: mintlify.createagentjob\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/agent/{projectId}/job/{id}\n      name: getagentjob\n      operations:\n      - method: GET\n        name: getagentjob\n        description: Get agent job\n        call: mintlify.getagentjob\n        with:\n          projectId: rest.projectId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /discovery/v2/assistant/{domain}/message\n      name: createassistantmessage\n      operations:\n      - method: POST\n        name: createassistantmessage\n        description: Create assistant message\n        call: mintlify.createassistantmessage\n        with:\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /discovery/v1/search/{domain}\n      name: searchdocs\n      operations:\n      - method: POST\n        name: searchdocs\n        description: Search documentation\n        call: mintlify.searchdocs\n        with:\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/feedback\n      name: getfeedback\n      operations:\n      - method: GET\n        name: getfeedback\n        description: Get user feedback\n        call: mintlify.getfeedback\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/conversations\n      name: getconversations\n      operations:\n      - method: GET\n        name: getconversations\n        description: Get assistant conversations\n        call: mintlify.getconversations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mintlify-mcp\n    transport: http\n \
  \   description: MCP adapter for Mintlify API for AI agent use.\n    tools:\n    - name: triggerupdate\n      description: Trigger documentation update\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mintlify.triggerupdate\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getupdatestatus\n      description: Get update status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mintlify.getupdatestatus\n      with:\n        statusId: tools.statusId\n      inputParameters:\n      - name: statusId\n        type: string\n        description: statusId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createagentjob\n      description:\
  \ Create agent job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mintlify.createagentjob\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getagentjob\n      description: Get agent job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mintlify.getagentjob\n      with:\n        projectId: tools.projectId\n        id: tools.id\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createassistantmessage\n      description: Create assistant\
  \ message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mintlify.createassistantmessage\n      with:\n        domain: tools.domain\n      inputParameters:\n      - name: domain\n        type: string\n        description: domain\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchdocs\n      description: Search documentation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mintlify.searchdocs\n      with:\n        domain: tools.domain\n      inputParameters:\n      - name: domain\n        type: string\n        description: domain\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfeedback\n      description: Get user feedback\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mintlify.getfeedback\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconversations\n      description: Get assistant conversations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mintlify.getconversations\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MINTLIFY_TOKEN: MINTLIFY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mintlify/refs/heads/main/capabilities/mintlify-capability.yaml
tags:
- Mintlify
- API
tools:
- description: Trigger documentation update
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: triggerupdate
- description: Get update status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getupdatestatus
- description: Create agent job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createagentjob
- description: Get agent job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getagentjob
- description: Create assistant message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createassistantmessage
- description: Search documentation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchdocs
- description: Get user feedback
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfeedback
- description: Get assistant conversations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconversations
---
