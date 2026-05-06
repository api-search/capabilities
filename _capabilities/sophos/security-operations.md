---
categories: []
consumed_apis: []
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
- retrieve security alerts from sophos central. use for threat detection, incident triage, and monitoring active security events. supports cursor pagination and date filtering.
- list events
- list security events from sophos central within the last 24 hours
- sophos
- siem
- list security alerts from sophos central within the last 24 hours
- security events from sophos central
- retrieve security events from sophos central. use for siem integration, log analysis, and security monitoring. supports filtering by event type exclusions and date ranges.
- cybersecurity
- endpoint protection
- list alerts
- incident response
- security operations
- list security events
- security
- list security alerts
- threat detection
- security alerts from sophos central
slug: security-operations
source_filename: security-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sophos Security Operations\n  description: Unified capability for security operations using the Sophos Central SIEM API. Combines alert retrieval and\n    event monitoring to support SOC analysts performing threat detection, incident triage, and security event analysis workflows.\n  tags:\n  - Sophos\n  - Security Operations\n  - SIEM\n  - Threat Detection\n  - Incident Response\n  - Cybersecurity\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SOPHOS_API_KEY: SOPHOS_API_KEY\n    SOPHOS_BEARER_TOKEN: SOPHOS_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sophos-siem\n    baseUri: https://api1.central.sophos.com/gateway\n    description: Sophos Central SIEM API for retrieving security alerts and events\n    authentication:\n      type: apikey\n      key: x-api-key\n      value: '{{SOPHOS_API_KEY}}'\n      placement: header\n    resources:\n    - name: alerts\n      path:\
  \ /siem/v1/alerts\n      description: Security alerts from Sophos Central\n      operations:\n      - name: list-alerts\n        method: GET\n        description: Retrieve security alerts for the customer within the last 24 hours\n        inputParameters:\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor for next page of results\n        - name: from_date\n          in: query\n          type: integer\n          required: false\n          description: Unix timestamp UTC specifying start date (within last 24 hours)\n        - name: from_date_offset_minutes\n          in: query\n          type: integer\n          required: false\n          description: Delay data collection by X minutes\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum alerts to return (default 200, max 1000)\n        - name: Authorization\n          in: header\n\
  \          type: string\n          required: true\n          description: Bearer token for authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /siem/v1/events\n      description: Security events from Sophos Central\n      operations:\n      - name: list-events\n        method: GET\n        description: Retrieve security events for the customer within the last 24 hours\n        inputParameters:\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor for next page of results\n        - name: from_date\n          in: query\n          type: integer\n          required: false\n          description: Unix timestamp UTC specifying start date\n        - name: from_date_offset_minutes\n          in: query\n          type: integer\n          required: false\n          description: Delay data collection\
  \ by X minutes\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum events to return (default 200, max 1000)\n        - name: exclude_types\n          in: query\n          type: string\n          required: false\n          description: Comma-separated event types to exclude\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer token for authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sophos-security-ops-api\n    description: Unified REST API for Sophos security operations including alerts and event monitoring.\n    resources:\n    - path: /v1/alerts\n      name: alerts\n      description: Security alerts from Sophos Central\n      operations:\n      - method: GET\n        name: list-alerts\n\
  \        description: List security alerts from Sophos Central within the last 24 hours\n        call: sophos-siem.list-alerts\n        with:\n          cursor: rest.cursor\n          from_date: rest.from_date\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Security events from Sophos Central\n      operations:\n      - method: GET\n        name: list-events\n        description: List security events from Sophos Central within the last 24 hours\n        call: sophos-siem.list-events\n        with:\n          cursor: rest.cursor\n          from_date: rest.from_date\n          exclude_types: rest.exclude_types\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sophos-security-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted security operations using\
  \ Sophos Central SIEM.\n    tools:\n    - name: list-security-alerts\n      description: Retrieve security alerts from Sophos Central. Use for threat detection, incident triage, and monitoring\n        active security events. Supports cursor pagination and date filtering.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sophos-siem.list-alerts\n      with:\n        cursor: tools.cursor\n        from_date: tools.from_date\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-security-events\n      description: Retrieve security events from Sophos Central. Use for SIEM integration, log analysis, and security monitoring.\n        Supports filtering by event type exclusions and date ranges.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sophos-siem.list-events\n      with:\n        cursor: tools.cursor\n        from_date: tools.from_date\n        exclude_types: tools.exclude_types\n\
  \        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
