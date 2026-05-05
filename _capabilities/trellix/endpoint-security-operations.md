---
api_specs:
- filename: trellix-edr-openapi.yml
  format: yaml
  label: trellix-edr
  slug: trellix-edr
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/trellix/refs/heads/main/openapi/trellix-edr-openapi.yml
- filename: trellix-epo-saas-openapi.yml
  format: yaml
  label: trellix-epo
  slug: trellix-epo
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/trellix/refs/heads/main/openapi/trellix-epo-saas-openapi.yml
categories: []
consumed_apis:
- trellix-edr
- trellix-epo
description: Unified capability for SOC analysts and endpoint security engineers to detect, investigate, hunt, and respond to endpoint threats using Trellix EDR and ePO SaaS. Combines threat detection, alert investigation, real-time search, device management, and automated response actions for comprehensive endpoint security operations.
layout: capability
name: Trellix Endpoint Security Operations
operations:
- description: List detected threats
  method: GET
  name: list-threats
  path: /v1/threats
- description: List detections
  method: GET
  name: list-detections
  path: /v1/detections
- description: List alerts
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: List managed devices
  method: GET
  name: list-devices
  path: /v1/devices
- description: List threat events
  method: GET
  name: list-events
  path: /v1/events
- description: List active searches
  method: GET
  name: list-searches
  path: /v1/searches
- description: Create real-time search
  method: POST
  name: create-search
  path: /v1/searches
- description: Execute response reaction
  method: POST
  name: create-reaction
  path: /v1/reactions
- description: Create response action
  method: POST
  name: create-response-action
  path: /v1/response-actions
personas: []
provider_name: Trellix
provider_slug: trellix
search_terms:
- endpoint detections
- incident response
- managed endpoint devices from epo
- epo response actions
- list managed endpoint devices from epo saas for asset inventory and status checks.
- list threat events
- edr list detections
- threat intelligence
- edr list alerts
- cloud security
- list events
- xdr
- create reaction
- cybersecurity
- list detections
- epo list events
- list security alerts from edr for soc triage and prioritization.
- list threats detected by trellix edr for incident investigation and triage.
- create a real-time search across endpoints to hunt for indicators of compromise.
- threat detection
- list devices
- list searches
- edr response reactions
- list threats
- detected threats from edr
- list detected threats
- list alerts
- list managed devices
- endpoint security
- epo list devices
- security operations
- create response action
- edr list threats
- epo create response action
- edr create search
- create search
- execute an edr response reaction on an endpoint (isolate, collect artifacts, terminate process).
- list active searches
- execute response reaction
- edr create reaction
- threat hunting
- list endpoint detections from edr for threat hunting and analysis.
- real-time endpoint searches
- create real-time search
- create an epo response action on a managed device (quarantine, run scan, apply policy).
- threat events from epo
- list threat events from epo saas for incident correlation and reporting.
- epo execute query
- execute a saved epo query for security reporting and compliance checks.
- security alerts
slug: endpoint-security-operations
source_filename: endpoint-security-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Trellix Endpoint Security Operations\"\n  description: >-\n    Unified capability for SOC analysts and endpoint security engineers to\n    detect, investigate, hunt, and respond to endpoint threats using Trellix\n    EDR and ePO SaaS. Combines threat detection, alert investigation,\n    real-time search, device management, and automated response actions\n    for comprehensive endpoint security operations.\n  tags:\n    - Endpoint Security\n    - Incident Response\n    - Security Operations\n    - Threat Detection\n    - Threat Hunting\n    - XDR\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRELLIX_EDR_API_KEY: TRELLIX_EDR_API_KEY\n      TRELLIX_EPO_API_KEY: TRELLIX_EPO_API_KEY\n\ncapability:\n  consumes:\n    - import: trellix-edr\n      location: ./shared/trellix-edr.yaml\n    - import: trellix-epo\n      location: ./shared/trellix-epo-saas.yaml\n\n  exposes:\n    - type:\
  \ rest\n      port: 8080\n      namespace: trellix-endpoint-ops-api\n      description: \"Unified REST API for Trellix endpoint security operations.\"\n      resources:\n        - path: /v1/threats\n          name: threats\n          description: \"Detected threats from EDR\"\n          operations:\n            - method: GET\n              name: list-threats\n              description: \"List detected threats\"\n              call: \"trellix-edr.list-threats\"\n              with:\n                limit: \"rest.limit\"\n                since: \"rest.since\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/detections\n          name: detections\n          description: \"Endpoint detections\"\n          operations:\n            - method: GET\n              name: list-detections\n              description: \"List detections\"\n              call: \"trellix-edr.list-detections\"\n              with:\n                limit:\
  \ \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/alerts\n          name: alerts\n          description: \"Security alerts\"\n          operations:\n            - method: GET\n              name: list-alerts\n              description: \"List alerts\"\n              call: \"trellix-edr.list-alerts\"\n              with:\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/devices\n          name: devices\n          description: \"Managed endpoint devices from ePO\"\n          operations:\n            - method: GET\n              name: list-devices\n              description: \"List managed devices\"\n              call: \"trellix-epo.list-devices\"\n              with:\n                limit: \"rest.limit\"\n                filter: \"rest.filter\"\n              outputParameters:\n            \
  \    - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: \"Threat events from ePO\"\n          operations:\n            - method: GET\n              name: list-events\n              description: \"List threat events\"\n              call: \"trellix-epo.list-events\"\n              with:\n                limit: \"rest.limit\"\n                since: \"rest.since\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/searches\n          name: searches\n          description: \"Real-time endpoint searches\"\n          operations:\n            - method: GET\n              name: list-searches\n              description: \"List active searches\"\n              call: \"trellix-edr.list-searches\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-search\n\
  \              description: \"Create real-time search\"\n              call: \"trellix-edr.create-search\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reactions\n          name: reactions\n          description: \"EDR response reactions\"\n          operations:\n            - method: POST\n              name: create-reaction\n              description: \"Execute response reaction\"\n              call: \"trellix-edr.create-reaction\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/response-actions\n          name: response-actions\n          description: \"ePO response actions\"\n          operations:\n            - method: POST\n              name: create-response-action\n              description: \"Create response action\"\n              call: \"trellix-epo.create-response-action\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: trellix-endpoint-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted endpoint security operations, threat hunting, and incident response.\"\n      tools:\n        - name: edr-list-threats\n          description: \"List threats detected by Trellix EDR for incident investigation and triage.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trellix-edr.list-threats\"\n          with:\n            limit: \"tools.limit\"\n            since: \"tools.since\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edr-list-detections\n          description: \"List endpoint detections from EDR for threat hunting and analysis.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trellix-edr.list-detections\"\n          with:\n        \
  \    limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edr-list-alerts\n          description: \"List security alerts from EDR for SOC triage and prioritization.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trellix-edr.list-alerts\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edr-create-search\n          description: \"Create a real-time search across endpoints to hunt for indicators of compromise.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"trellix-edr.create-search\"\n          with:\n            query: \"tools.query\"\n            hosts: \"tools.hosts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edr-create-reaction\n\
  \          description: \"Execute an EDR response reaction on an endpoint (isolate, collect artifacts, terminate process).\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"trellix-edr.create-reaction\"\n          with:\n            type: \"tools.type\"\n            hostId: \"tools.hostId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: epo-list-devices\n          description: \"List managed endpoint devices from ePO SaaS for asset inventory and status checks.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trellix-epo.list-devices\"\n          with:\n            limit: \"tools.limit\"\n            filter: \"tools.filter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: epo-list-events\n          description: \"List threat events from ePO SaaS for\
  \ incident correlation and reporting.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trellix-epo.list-events\"\n          with:\n            limit: \"tools.limit\"\n            since: \"tools.since\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: epo-execute-query\n          description: \"Execute a saved ePO query for security reporting and compliance checks.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trellix-epo.execute-query\"\n          with:\n            queryId: \"tools.queryId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: epo-create-response-action\n          description: \"Create an ePO response action on a managed device (quarantine, run scan, apply policy).\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent:\
  \ false\n          call: \"trellix-epo.create-response-action\"\n          with:\n            type: \"tools.type\"\n            deviceId: \"tools.deviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trellix/refs/heads/main/capabilities/endpoint-security-operations.yaml
tags:
- Endpoint Security
- Incident Response
- Security Operations
- Threat Detection
- Threat Hunting
- XDR
tools:
- description: List threats detected by Trellix EDR for incident investigation and triage.
  hints:
    openWorld: true
    readOnly: true
  name: edr-list-threats
- description: List endpoint detections from EDR for threat hunting and analysis.
  hints:
    openWorld: true
    readOnly: true
  name: edr-list-detections
- description: List security alerts from EDR for SOC triage and prioritization.
  hints:
    openWorld: true
    readOnly: true
  name: edr-list-alerts
- description: Create a real-time search across endpoints to hunt for indicators of compromise.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: edr-create-search
- description: Execute an EDR response reaction on an endpoint (isolate, collect artifacts, terminate process).
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: edr-create-reaction
- description: List managed endpoint devices from ePO SaaS for asset inventory and status checks.
  hints:
    openWorld: true
    readOnly: true
  name: epo-list-devices
- description: List threat events from ePO SaaS for incident correlation and reporting.
  hints:
    openWorld: true
    readOnly: true
  name: epo-list-events
- description: Execute a saved ePO query for security reporting and compliance checks.
  hints:
    openWorld: false
    readOnly: true
  name: epo-execute-query
- description: Create an ePO response action on a managed device (quarantine, run scan, apply policy).
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: epo-create-response-action
---
