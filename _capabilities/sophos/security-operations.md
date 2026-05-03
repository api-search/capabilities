---
api_specs:
- filename: sophos-central-siem-openapi.yml
  format: yaml
  label: sophos-siem
  slug: sophos-siem
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sophos/refs/heads/main/openapi/sophos-central-siem-openapi.yml
categories: []
consumed_apis:
- sophos-siem
description: Unified capability for security operations using the Sophos Central SIEM API. Combines alert retrieval and event monitoring to support SOC analysts performing threat detection, incident triage, and security event analysis workflows.
layout: capability
name: Sophos Security Operations
operations:
- description: List security alerts from Sophos Central within the last 24 hours
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: List security events from Sophos Central within the last 24 hours
  method: GET
  name: list-events
  path: /v1/events
personas: []
provider_name: Sophos
provider_slug: sophos
search_terms:
- security events from sophos central
- retrieve security alerts from sophos central. use for threat detection, incident triage, and monitoring active security events. supports cursor pagination and date filtering.
- endpoint protection
- security alerts from sophos central
- security
- list security events
- incident response
- sophos
- list events
- threat detection
- cybersecurity
- security operations
- list alerts
- list security events from sophos central within the last 24 hours
- retrieve security events from sophos central. use for siem integration, log analysis, and security monitoring. supports filtering by event type exclusions and date ranges.
- list security alerts
- list security alerts from sophos central within the last 24 hours
- siem
slug: security-operations
source_filename: security-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sophos Security Operations\"\n  description: >-\n    Unified capability for security operations using the Sophos Central SIEM API.\n    Combines alert retrieval and event monitoring to support SOC analysts performing\n    threat detection, incident triage, and security event analysis workflows.\n  tags:\n    - Sophos\n    - Security Operations\n    - SIEM\n    - Threat Detection\n    - Incident Response\n    - Cybersecurity\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SOPHOS_API_KEY: SOPHOS_API_KEY\n      SOPHOS_BEARER_TOKEN: SOPHOS_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: sophos-siem\n      location: ./shared/sophos-central-siem.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sophos-security-ops-api\n      description: \"Unified REST API for Sophos security operations including alerts and event monitoring.\"\n      resources:\n  \
  \      - path: /v1/alerts\n          name: alerts\n          description: Security alerts from Sophos Central\n          operations:\n            - method: GET\n              name: list-alerts\n              description: List security alerts from Sophos Central within the last 24 hours\n              call: \"sophos-siem.list-alerts\"\n              with:\n                cursor: \"rest.cursor\"\n                from_date: \"rest.from_date\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events\n          name: events\n          description: Security events from Sophos Central\n          operations:\n            - method: GET\n              name: list-events\n              description: List security events from Sophos Central within the last 24 hours\n              call: \"sophos-siem.list-events\"\n              with:\n                cursor: \"rest.cursor\"\n            \
  \    from_date: \"rest.from_date\"\n                exclude_types: \"rest.exclude_types\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sophos-security-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted security operations using Sophos Central SIEM.\"\n      tools:\n        - name: list-security-alerts\n          description: >-\n            Retrieve security alerts from Sophos Central. Use for threat detection,\n            incident triage, and monitoring active security events. Supports cursor\n            pagination and date filtering.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sophos-siem.list-alerts\"\n          with:\n            cursor: \"tools.cursor\"\n            from_date: \"tools.from_date\"\n            limit: \"tools.limit\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-security-events\n          description: >-\n            Retrieve security events from Sophos Central. Use for SIEM integration,\n            log analysis, and security monitoring. Supports filtering by event type\n            exclusions and date ranges.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sophos-siem.list-events\"\n          with:\n            cursor: \"tools.cursor\"\n            from_date: \"tools.from_date\"\n            exclude_types: \"tools.exclude_types\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sophos/refs/heads/main/capabilities/security-operations.yaml
tags:
- Sophos
- Security Operations
- SIEM
- Threat Detection
- Incident Response
- Cybersecurity
tools:
- description: Retrieve security alerts from Sophos Central. Use for threat detection, incident triage, and monitoring active security events. Supports cursor pagination and date filtering.
  hints:
    openWorld: true
    readOnly: true
  name: list-security-alerts
- description: Retrieve security events from Sophos Central. Use for SIEM integration, log analysis, and security monitoring. Supports filtering by event type exclusions and date ranges.
  hints:
    openWorld: true
    readOnly: true
  name: list-security-events
---
