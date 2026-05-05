---
api_specs:
- filename: windstream-voice-openapi.yml
  format: yaml
  label: windstream-voice
  slug: windstream-voice
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/windstream-holdings/refs/heads/main/openapi/windstream-voice-openapi.yml
- filename: windstream-contact-center-openapi.yml
  format: yaml
  label: windstream-ccs
  slug: windstream-ccs
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/windstream-holdings/refs/heads/main/openapi/windstream-contact-center-openapi.yml
categories: []
consumed_apis:
- windstream-voice
- windstream-ccs
description: Unified Communications capability for Windstream Enterprise, combining Voice and Contact Center APIs to enable end-to-end call management, agent operations, auto-attendant configuration, and contact center monitoring. Designed for IT administrators, contact center managers, and UC platform integrators.
layout: capability
name: Windstream Unified Communications
operations:
- description: List active voice calls
  method: GET
  name: list-voice-calls
  path: /v1/calls
- description: Make an outbound voice call
  method: POST
  name: make-call
  path: /v1/calls
- description: Get voice call details
  method: GET
  name: get-voice-call
  path: /v1/calls/{id}
- description: Terminate an active call
  method: DELETE
  name: terminate-call
  path: /v1/calls/{id}
- description: List contact center calls
  method: GET
  name: list-cc-calls
  path: /v1/cc-calls
- description: Search contact center calls by criteria
  method: GET
  name: search-cc-calls
  path: /v1/cc-calls/search
- description: List all extensions
  method: GET
  name: list-extensions
  path: /v1/extensions
- description: Get extension details
  method: GET
  name: get-extension
  path: /v1/extensions/{id}
- description: Update extension configuration
  method: PUT
  name: update-extension
  path: /v1/extensions/{id}
- description: List all auto-attendants
  method: GET
  name: list-auto-attendants
  path: /v1/auto-attendants
- description: Create an auto-attendant
  method: POST
  name: create-auto-attendant
  path: /v1/auto-attendants
- description: Get current agent state
  method: GET
  name: get-agent-state
  path: /v1/agents/{id}/state
- description: Update agent presence state
  method: POST
  name: update-agent-state
  path: /v1/agents/{id}/state
- description: List contact center tenants
  method: GET
  name: list-tenants
  path: /v1/tenants
- description: List ACDs/queues for a tenant
  method: GET
  name: list-queues
  path: /v1/tenants/{id}/queues
- description: List users
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user
  method: POST
  name: create-user
  path: /v1/users
personas: []
provider_name: Windstream Holdings
provider_slug: windstream-holdings
search_terms:
- windstream
- list acd queues for a contact center tenant
- auto-attendant management
- execute a control action (transfer, hold, terminate) on a voice call
- ucaas
- call management
- list users
- tenant management
- update contact center agent presence state
- get current presence state of a contact center agent
- terminate call
- update extension configuration (forwarding, dnd, etc.)
- search contact center calls by number or date range
- create user
- get extension details
- individual extension operations
- terminate voice call
- terminate an active voice call
- broadband
- search cc calls
- list all auto-attendants
- list cc calls
- managed services
- get agent state
- list active voice calls
- list extensions
- create a new auto-attendant with menu options
- update extension
- agent state management
- list windstream system users
- get current agent state
- list all extensions configured in windstream
- list active voice calls in windstream
- individual call operations
- active call management across voice and contact center
- get voice call
- list all extensions
- update agent presence state
- update agent state
- extension management
- list tenants
- list auto attendants
- create a new user
- initiate an outbound voice call from an extension
- make outbound call
- list contact center tenants
- search contact center calls
- contact center
- create an auto-attendant
- unified communications
- create auto attendant
- list queues
- terminate an active call
- get voice call details
- search contact center calls by criteria
- voice
- make call
- acd queue management
- get details of a specific windstream extension
- list auto-attendant (ivr) configurations
- agents
- list voice calls
- user management
- list acds/queues for a tenant
- list contact center calls
- control voice call
- network communications
- contact center call management
- sd-wan
- telecom
- get extension
- update extension configuration
- make an outbound voice call
slug: unified-communications
source_filename: unified-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Windstream Unified Communications\"\n  description: >-\n    Unified Communications capability for Windstream Enterprise, combining Voice\n    and Contact Center APIs to enable end-to-end call management, agent operations,\n    auto-attendant configuration, and contact center monitoring. Designed for IT\n    administrators, contact center managers, and UC platform integrators.\n  tags:\n    - Windstream\n    - Unified Communications\n    - Contact Center\n    - Voice\n    - Telecom\n    - Agents\n    - Call Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WINDSTREAM_VOICE_USERNAME: WINDSTREAM_VOICE_USERNAME\n      WINDSTREAM_VOICE_PASSWORD: WINDSTREAM_VOICE_PASSWORD\n      WINDSTREAM_CCS_TOKEN: WINDSTREAM_CCS_TOKEN\n\ncapability:\n  consumes:\n    - import: windstream-voice\n      location: ./shared/windstream-voice.yaml\n    - import: windstream-ccs\n      location:\
  \ ./shared/windstream-contact-center.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: windstream-uc-api\n      description: \"Unified REST API for Windstream Unified Communications.\"\n      resources:\n        - path: /v1/calls\n          name: calls\n          description: \"Active call management across Voice and Contact Center\"\n          operations:\n            - method: GET\n              name: list-voice-calls\n              description: \"List active voice calls\"\n              call: \"windstream-voice.list-active-calls\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: make-call\n              description: \"Make an outbound voice call\"\n              call: \"windstream-voice.make-outbound-call\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/calls/{id}\n          name: call\n\
  \          description: \"Individual call operations\"\n          operations:\n            - method: GET\n              name: get-voice-call\n              description: \"Get voice call details\"\n              call: \"windstream-voice.get-call\"\n              with:\n                callId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: terminate-call\n              description: \"Terminate an active call\"\n              call: \"windstream-voice.terminate-call\"\n              with:\n                callId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cc-calls\n          name: cc-calls\n          description: \"Contact center call management\"\n          operations:\n            - method: GET\n              name: list-cc-calls\n              description: \"List contact center calls\"\
  \n              call: \"windstream-ccs.list-calls\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cc-calls/search\n          name: cc-calls-search\n          description: \"Search contact center calls\"\n          operations:\n            - method: GET\n              name: search-cc-calls\n              description: \"Search contact center calls by criteria\"\n              call: \"windstream-ccs.search-calls\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/extensions\n          name: extensions\n          description: \"Extension management\"\n          operations:\n            - method: GET\n              name: list-extensions\n              description: \"List all extensions\"\n              call: \"windstream-voice.list-extensions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \n        - path: /v1/extensions/{id}\n          name: extension\n          description: \"Individual extension operations\"\n          operations:\n            - method: GET\n              name: get-extension\n              description: \"Get extension details\"\n              call: \"windstream-voice.get-extension\"\n              with:\n                extensionId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-extension\n              description: \"Update extension configuration\"\n              call: \"windstream-voice.update-extension\"\n              with:\n                extensionId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/auto-attendants\n          name: auto-attendants\n          description: \"Auto-attendant management\"\n          operations:\n            - method:\
  \ GET\n              name: list-auto-attendants\n              description: \"List all auto-attendants\"\n              call: \"windstream-voice.list-auto-attendants\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-auto-attendant\n              description: \"Create an auto-attendant\"\n              call: \"windstream-voice.create-auto-attendant\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/agents/{id}/state\n          name: agent-state\n          description: \"Agent state management\"\n          operations:\n            - method: GET\n              name: get-agent-state\n              description: \"Get current agent state\"\n              call: \"windstream-ccs.get-agent-state\"\n              with:\n                extensionUuid: \"rest.id\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n            - method: POST\n              name: update-agent-state\n              description: \"Update agent presence state\"\n              call: \"windstream-ccs.update-agent-state\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tenants\n          name: tenants\n          description: \"Tenant management\"\n          operations:\n            - method: GET\n              name: list-tenants\n              description: \"List contact center tenants\"\n              call: \"windstream-ccs.list-tenants\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tenants/{id}/queues\n          name: queues\n          description: \"ACD queue management\"\n          operations:\n            - method: GET\n              name: list-queues\n              description: \"List ACDs/queues for a tenant\"\n       \
  \       call: \"windstream-ccs.list-tenant-acds\"\n              with:\n                tenantUuid: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: \"User management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users\"\n              call: \"windstream-voice.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a new user\"\n              call: \"windstream-voice.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: windstream-uc-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Windstream\
  \ Unified Communications management.\"\n      tools:\n        - name: list-voice-calls\n          description: \"List active voice calls in Windstream\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windstream-voice.list-active-calls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: make-outbound-call\n          description: \"Initiate an outbound voice call from an extension\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"windstream-voice.make-outbound-call\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: control-voice-call\n          description: \"Execute a control action (transfer, hold, terminate) on a voice call\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"windstream-voice.control-call\"\n          with:\n    \
  \        callId: \"tools.callId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: terminate-voice-call\n          description: \"Terminate an active voice call\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"windstream-voice.terminate-call\"\n          with:\n            callId: \"tools.callId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-extensions\n          description: \"List all extensions configured in Windstream\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windstream-voice.list-extensions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-extension\n          description: \"Get details of a specific Windstream extension\"\n          hints:\n            readOnly: true\n\
  \            openWorld: false\n          call: \"windstream-voice.get-extension\"\n          with:\n            extensionId: \"tools.extensionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-extension\n          description: \"Update extension configuration (forwarding, DND, etc.)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"windstream-voice.update-extension\"\n          with:\n            extensionId: \"tools.extensionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-auto-attendants\n          description: \"List auto-attendant (IVR) configurations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windstream-voice.list-auto-attendants\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n\n        - name: create-auto-attendant\n          description: \"Create a new auto-attendant with menu options\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"windstream-voice.create-auto-attendant\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-cc-calls\n          description: \"List contact center calls\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windstream-ccs.list-calls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-cc-calls\n          description: \"Search contact center calls by number or date range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windstream-ccs.search-calls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-agent-state\n\
  \          description: \"Get current presence state of a contact center agent\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"windstream-ccs.get-agent-state\"\n          with:\n            extensionUuid: \"tools.extensionUuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-agent-state\n          description: \"Update contact center agent presence state\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"windstream-ccs.update-agent-state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-tenants\n          description: \"List contact center tenants\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windstream-ccs.list-tenants\"\n          outputParameters:\n            - type: object\n  \
  \            mapping: \"$.\"\n\n        - name: list-queues\n          description: \"List ACD queues for a contact center tenant\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windstream-ccs.list-tenant-acds\"\n          with:\n            tenantUuid: \"tools.tenantUuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-users\n          description: \"List Windstream system users\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windstream-voice.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/windstream-holdings/refs/heads/main/capabilities/unified-communications.yaml
tags:
- Windstream
- Unified Communications
- Contact Center
- Voice
- Telecom
- Agents
- Call Management
tools:
- description: List active voice calls in Windstream
  hints:
    openWorld: true
    readOnly: true
  name: list-voice-calls
- description: Initiate an outbound voice call from an extension
  hints:
    destructive: false
    readOnly: false
  name: make-outbound-call
- description: Execute a control action (transfer, hold, terminate) on a voice call
  hints:
    destructive: false
    readOnly: false
  name: control-voice-call
- description: Terminate an active voice call
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: terminate-voice-call
- description: List all extensions configured in Windstream
  hints:
    openWorld: true
    readOnly: true
  name: list-extensions
- description: Get details of a specific Windstream extension
  hints:
    openWorld: false
    readOnly: true
  name: get-extension
- description: Update extension configuration (forwarding, DND, etc.)
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-extension
- description: List auto-attendant (IVR) configurations
  hints:
    openWorld: true
    readOnly: true
  name: list-auto-attendants
- description: Create a new auto-attendant with menu options
  hints:
    destructive: false
    readOnly: false
  name: create-auto-attendant
- description: List contact center calls
  hints:
    openWorld: true
    readOnly: true
  name: list-cc-calls
- description: Search contact center calls by number or date range
  hints:
    openWorld: true
    readOnly: true
  name: search-cc-calls
- description: Get current presence state of a contact center agent
  hints:
    openWorld: false
    readOnly: true
  name: get-agent-state
- description: Update contact center agent presence state
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-agent-state
- description: List contact center tenants
  hints:
    openWorld: true
    readOnly: true
  name: list-tenants
- description: List ACD queues for a contact center tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-queues
- description: List Windstream system users
  hints:
    openWorld: true
    readOnly: true
  name: list-users
---
