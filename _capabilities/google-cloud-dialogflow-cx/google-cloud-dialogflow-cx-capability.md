---
categories: []
consumed_apis: []
description: The Dialogflow CX API enables building and managing conversational agents with flows, pages, intents, entity types, and session management for advanced multi-turn conversations.
layout: capability
name: Google Cloud Dialogflow CX API
operations:
- description: Google Cloud Dialogflow CX List agents
  method: GET
  name: listagents
  path: /projects/{projectId}/locations/{location}/agents
- description: Google Cloud Dialogflow CX Create an agent
  method: POST
  name: createagent
  path: /projects/{projectId}/locations/{location}/agents
- description: Google Cloud Dialogflow CX Get an agent
  method: GET
  name: getagent
  path: /projects/{projectId}/locations/{location}/agents/{agentId}
- description: Google Cloud Dialogflow CX Update an agent
  method: PATCH
  name: updateagent
  path: /projects/{projectId}/locations/{location}/agents/{agentId}
- description: Google Cloud Dialogflow CX Delete an agent
  method: DELETE
  name: deleteagent
  path: /projects/{projectId}/locations/{location}/agents/{agentId}
- description: Google Cloud Dialogflow CX List flows
  method: GET
  name: listflows
  path: /projects/{projectId}/locations/{location}/agents/{agentId}/flows
- description: Google Cloud Dialogflow CX Create a flow
  method: POST
  name: createflow
  path: /projects/{projectId}/locations/{location}/agents/{agentId}/flows
- description: Google Cloud Dialogflow CX List intents
  method: GET
  name: listintents
  path: /projects/{projectId}/locations/{location}/agents/{agentId}/intents
- description: Google Cloud Dialogflow CX Create an intent
  method: POST
  name: createintent
  path: /projects/{projectId}/locations/{location}/agents/{agentId}/intents
- description: Google Cloud Dialogflow CX Detect intent
  method: POST
  name: detectintent
  path: /projects/{projectId}/locations/{location}/agents/{agentId}/sessions/{sessionId}:detectIntent
personas: []
provider_name: Google Cloud Dialogflow CX
provider_slug: google-cloud-dialogflow-cx
search_terms:
- google cloud dialogflow cx list agents
- google cloud dialogflow cx list flows
- chatbots
- nlu
- listflows
- deleteagent
- google cloud dialogflow cx detect intent
- createflow
- cx
- getagent
- cloud
- google
- google cloud dialogflow cx get an agent
- detectintent
- virtual agents
- listagents
- google cloud dialogflow cx create an agent
- updateagent
- listintents
- google cloud dialogflow cx delete an agent
- createintent
- api
- google cloud dialogflow cx list intents
- google cloud dialogflow cx create a flow
- createagent
- google cloud dialogflow cx create an intent
- google cloud dialogflow cx update an agent
- dialogflow
- google cloud
- conversational ai
slug: google-cloud-dialogflow-cx-capability
source_filename: google-cloud-dialogflow-cx-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Dialogflow CX API\n  description: The Dialogflow CX API enables building and managing conversational agents with flows, pages, intents, entity\n    types, and session management for advanced multi-turn conversations.\n  tags:\n  - Google\n  - Cloud\n  - Dialogflow\n  - Cx\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-dialogflow-cx\n    baseUri: https://dialogflow.googleapis.com/v3\n    description: Google Cloud Dialogflow CX API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_DIALOGFLOW_CX_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-agents\n      path: /projects/{projectId}/locations/{location}/agents\n      operations:\n      - name: listagents\n        method: GET\n        description: Google Cloud Dialogflow CX List agents\n        inputParameters:\n        - name: projectId\n\
  \          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createagent\n        method: POST\n        description: Google Cloud Dialogflow CX Create an agent\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-agents-age\n      path: /projects/{projectId}/locations/{location}/agents/{agentId}\n      operations:\n      - name: getagent\n        method: GET\n        description: Google Cloud Dialogflow CX\
  \ Get an agent\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateagent\n        method: PATCH\n        description: Google Cloud Dialogflow CX Update an agent\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n      - name: deleteagent\n        method: DELETE\n        description: Google Cloud Dialogflow CX Delete an agent\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-agents-age\n      path: /projects/{projectId}/locations/{location}/agents/{agentId}/flows\n      operations:\n      - name: listflows\n        method: GET\n        description: Google Cloud Dialogflow CX List flows\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in:\
  \ path\n          type: string\n          required: true\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createflow\n        method: POST\n        description: Google Cloud Dialogflow CX Create a flow\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-agents-age\n      path: /projects/{projectId}/locations/{location}/agents/{agentId}/intents\n      operations:\n     \
  \ - name: listintents\n        method: GET\n        description: Google Cloud Dialogflow CX List intents\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createintent\n        method: POST\n        description: Google Cloud Dialogflow CX Create an intent\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-agents-age\n      path: /projects/{projectId}/locations/{location}/agents/{agentId}/sessions/{sessionId}:detectIntent\n      operations:\n      - name: detectintent\n        method: POST\n        description: Google Cloud Dialogflow CX Detect intent\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ google-cloud-dialogflow-cx-rest\n    description: REST adapter for Google Cloud Dialogflow CX API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/agents\n      name: listagents\n      operations:\n      - method: GET\n        name: listagents\n        description: Google Cloud Dialogflow CX List agents\n        call: google-cloud-dialogflow-cx.listagents\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/agents\n      name: createagent\n      operations:\n      - method: POST\n        name: createagent\n        description: Google Cloud Dialogflow CX Create an agent\n        call: google-cloud-dialogflow-cx.createagent\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/agents/{agentId}\n\
  \      name: getagent\n      operations:\n      - method: GET\n        name: getagent\n        description: Google Cloud Dialogflow CX Get an agent\n        call: google-cloud-dialogflow-cx.getagent\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          agentId: rest.agentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/agents/{agentId}\n      name: updateagent\n      operations:\n      - method: PATCH\n        name: updateagent\n        description: Google Cloud Dialogflow CX Update an agent\n        call: google-cloud-dialogflow-cx.updateagent\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          agentId: rest.agentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/agents/{agentId}\n      name: deleteagent\n      operations:\n      - method:\
  \ DELETE\n        name: deleteagent\n        description: Google Cloud Dialogflow CX Delete an agent\n        call: google-cloud-dialogflow-cx.deleteagent\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          agentId: rest.agentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/agents/{agentId}/flows\n      name: listflows\n      operations:\n      - method: GET\n        name: listflows\n        description: Google Cloud Dialogflow CX List flows\n        call: google-cloud-dialogflow-cx.listflows\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          agentId: rest.agentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/agents/{agentId}/flows\n      name: createflow\n      operations:\n      - method: POST\n        name: createflow\n      \
  \  description: Google Cloud Dialogflow CX Create a flow\n        call: google-cloud-dialogflow-cx.createflow\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          agentId: rest.agentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/agents/{agentId}/intents\n      name: listintents\n      operations:\n      - method: GET\n        name: listintents\n        description: Google Cloud Dialogflow CX List intents\n        call: google-cloud-dialogflow-cx.listintents\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          agentId: rest.agentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/agents/{agentId}/intents\n      name: createintent\n      operations:\n      - method: POST\n        name: createintent\n        description: Google Cloud Dialogflow\
  \ CX Create an intent\n        call: google-cloud-dialogflow-cx.createintent\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          agentId: rest.agentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/agents/{agentId}/sessions/{sessionId}:detectIntent\n      name: detectintent\n      operations:\n      - method: POST\n        name: detectintent\n        description: Google Cloud Dialogflow CX Detect intent\n        call: google-cloud-dialogflow-cx.detectintent\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          agentId: rest.agentId\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-dialogflow-cx-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Dialogflow CX API for AI agent use.\n\
  \    tools:\n    - name: listagents\n      description: Google Cloud Dialogflow CX List agents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dialogflow-cx.listagents\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createagent\n      description: Google Cloud Dialogflow CX Create an agent\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dialogflow-cx.createagent\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n\
  \        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getagent\n      description: Google Cloud Dialogflow CX Get an agent\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dialogflow-cx.getagent\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        agentId: tools.agentId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: agentId\n        type: string\n        description: agentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateagent\n      description:\
  \ Google Cloud Dialogflow CX Update an agent\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dialogflow-cx.updateagent\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        agentId: tools.agentId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: agentId\n        type: string\n        description: agentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteagent\n      description: Google Cloud Dialogflow CX Delete an agent\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-dialogflow-cx.deleteagent\n      with:\n        projectId: tools.projectId\n        location:\
  \ tools.location\n        agentId: tools.agentId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: agentId\n        type: string\n        description: agentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listflows\n      description: Google Cloud Dialogflow CX List flows\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dialogflow-cx.listflows\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        agentId: tools.agentId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required:\
  \ true\n      - name: agentId\n        type: string\n        description: agentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createflow\n      description: Google Cloud Dialogflow CX Create a flow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dialogflow-cx.createflow\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        agentId: tools.agentId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: agentId\n        type: string\n        description: agentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listintents\n      description: Google Cloud Dialogflow CX List intents\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dialogflow-cx.listintents\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        agentId: tools.agentId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: agentId\n        type: string\n        description: agentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createintent\n      description: Google Cloud Dialogflow CX Create an intent\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dialogflow-cx.createintent\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        agentId: tools.agentId\n\
  \      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: agentId\n        type: string\n        description: agentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: detectintent\n      description: Google Cloud Dialogflow CX Detect intent\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dialogflow-cx.detectintent\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        agentId: tools.agentId\n        sessionId: tools.sessionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required:\
  \ true\n      - name: agentId\n        type: string\n        description: agentId\n        required: true\n      - name: sessionId\n        type: string\n        description: sessionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_DIALOGFLOW_CX_TOKEN: GOOGLE_CLOUD_DIALOGFLOW_CX_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-dialogflow-cx/refs/heads/main/capabilities/google-cloud-dialogflow-cx-capability.yaml
tags:
- Google
- Cloud
- Dialogflow
- Cx
- API
tools:
- description: Google Cloud Dialogflow CX List agents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listagents
- description: Google Cloud Dialogflow CX Create an agent
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createagent
- description: Google Cloud Dialogflow CX Get an agent
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getagent
- description: Google Cloud Dialogflow CX Update an agent
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateagent
- description: Google Cloud Dialogflow CX Delete an agent
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteagent
- description: Google Cloud Dialogflow CX List flows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listflows
- description: Google Cloud Dialogflow CX Create a flow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createflow
- description: Google Cloud Dialogflow CX List intents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listintents
- description: Google Cloud Dialogflow CX Create an intent
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createintent
- description: Google Cloud Dialogflow CX Detect intent
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: detectintent
---
