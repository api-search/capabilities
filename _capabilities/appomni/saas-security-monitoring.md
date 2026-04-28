---
categories:
- compliance
consumed_apis:
- appomni
description: Workflow capability for continuous SaaS security monitoring using AppOmni. Supports security teams investigating threats, managing policies, and generating compliance reports for enterprise SaaS environments.
layout: capability
name: AppOmni SaaS Security Monitoring
operations: []
personas: []
provider_name: AppOmni
provider_slug: appomni
search_terms:
- generates and reviews compliance reports for regulatory frameworks
- generating and managing compliance reports for regulatory needs
- gets full details of a specific security event for investigation
- get compliance reports
- investigates security events and threats in saas applications
- review security policies
- saas security
- zero trust
- casb
- retrieves compliance reports for audit and governance purposes
- appomni
- continuous monitoring and investigation of saas security threats
- lists and filters security events across enterprise saas applications
- detecting and investigating security threats in saas applications
- get event details
- investigate security events
- reviews security policies configured across monitored saas applications
- compliance
- managing security policies for saas application governance
- threat detection
slug: saas-security-monitoring
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: AppOmni SaaS Security Monitoring\n  description: >-\n    Workflow capability for continuous SaaS security monitoring using AppOmni.\n    Supports security teams investigating threats, managing policies, and\n    generating compliance reports for enterprise SaaS environments.\n  tags:\n    - AppOmni\n    - SaaS Security\n    - Threat Detection\n    - Compliance\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APPOMNI_API_TOKEN: APPOMNI_API_TOKEN\n\ncapability:\n  consumes:\n    - import: appomni\n      location: ./shared/appomni-api.yaml\n\n  exposes:\n    - type: mcp\n      port: 9090\n      namespace: saas-security-mcp\n      transport: http\n      description: MCP server for AI-assisted SaaS security monitoring with AppOmni.\n      tools:\n        - name: investigate-security-events\n          description: Lists and filters security events across enterprise SaaS applications\n\
  \          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appomni.list-events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-event-details\n          description: Gets full details of a specific security event for investigation\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appomni.get-event\"\n          with:\n            eventId: \"tools.eventId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: review-security-policies\n          description: Reviews security policies configured across monitored SaaS applications\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appomni.list-policies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-compliance-reports\n          description:\
  \ Retrieves compliance reports for audit and governance purposes\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appomni.list-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
