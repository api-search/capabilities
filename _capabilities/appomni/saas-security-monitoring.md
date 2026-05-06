---
categories:
- compliance
consumed_apis: []
description: Workflow capability for continuous SaaS security monitoring using AppOmni. Supports security teams investigating threats, managing policies, and generating compliance reports for enterprise SaaS environments.
layout: capability
name: AppOmni SaaS Security Monitoring
operations: []
personas: []
provider_name: AppOmni
provider_slug: appomni
search_terms:
- managing security policies for saas application governance
- reviews security policies configured across monitored saas applications
- gets full details of a specific security event for investigation
- review security policies
- generates and reviews compliance reports for regulatory frameworks
- appomni
- investigate security events
- compliance
- get compliance reports
- zero trust
- saas security
- casb
- continuous monitoring and investigation of saas security threats
- threat detection
- generating and managing compliance reports for regulatory needs
- get event details
- investigates security events and threats in saas applications
- detecting and investigating security threats in saas applications
- lists and filters security events across enterprise saas applications
- retrieves compliance reports for audit and governance purposes
slug: saas-security-monitoring
source_filename: saas-security-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AppOmni SaaS Security Monitoring\n  description: Workflow capability for continuous SaaS security monitoring using AppOmni. Supports security teams investigating\n    threats, managing policies, and generating compliance reports for enterprise SaaS environments.\n  tags:\n  - AppOmni\n  - SaaS Security\n  - Threat Detection\n  - Compliance\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APPOMNI_API_TOKEN: APPOMNI_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: appomni\n    baseUri: https://api.appomni.com/v1\n    description: AppOmni SaaS security API\n    authentication:\n      type: bearer\n      token: '{{APPOMNI_API_TOKEN}}'\n    resources:\n    - name: events\n      path: /events\n      description: Security events detected across SaaS applications\n      operations:\n      - name: list-events\n        method: GET\n        description: Returns security events\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-event\n        method: GET\n        description: Returns a specific security event\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: Event identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies\n      path: /policies\n      description: Security policy management\n      operations:\n      - name: list-policies\n        method: GET\n        description: Returns security policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-reports\n      path: /compliance/reports\n      description: Compliance reporting\n      operations:\n      - name: list-reports\n\
  \        method: GET\n        description: Returns compliance reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9090\n    namespace: saas-security-mcp\n    transport: http\n    description: MCP server for AI-assisted SaaS security monitoring with AppOmni.\n    tools:\n    - name: investigate-security-events\n      description: Lists and filters security events across enterprise SaaS applications\n      hints:\n        readOnly: true\n        idempotent: true\n      call: appomni.list-events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event-details\n      description: Gets full details of a specific security event for investigation\n      hints:\n        readOnly: true\n        idempotent: true\n      call: appomni.get-event\n      with:\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: review-security-policies\n      description: Reviews security policies configured across monitored SaaS applications\n      hints:\n        readOnly: true\n        idempotent: true\n      call: appomni.list-policies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-compliance-reports\n      description: Retrieves compliance reports for audit and governance purposes\n      hints:\n        readOnly: true\n        idempotent: true\n      call: appomni.list-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/appomni/refs/heads/main/capabilities/saas-security-monitoring.yaml
tags:
- AppOmni
- SaaS Security
- Threat Detection
- Compliance
tools:
- description: Lists and filters security events across enterprise SaaS applications
  hints:
    idempotent: true
    readOnly: true
  name: investigate-security-events
- description: Gets full details of a specific security event for investigation
  hints:
    idempotent: true
    readOnly: true
  name: get-event-details
- description: Reviews security policies configured across monitored SaaS applications
  hints:
    idempotent: true
    readOnly: true
  name: review-security-policies
- description: Retrieves compliance reports for audit and governance purposes
  hints:
    idempotent: true
    readOnly: true
  name: get-compliance-reports
---
