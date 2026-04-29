---
categories:
- incident-management
consumed_apis:
- rest-api
description: Incident response workflow combining alerts, incidents, violations, and events for SREs investigating and resolving production issues detected by New Relic.
layout: capability
name: New Relic Incident Response
operations:
- description: List alert incidents
  method: GET
  name: get-alerts-incidents
  path: /v1/incidents
- description: List alert violations
  method: GET
  name: get-alerts-violations
  path: /v1/violations
- description: List alert events
  method: GET
  name: get-alerts-events
  path: /v1/alert-events
- description: List alert conditions for a policy
  method: GET
  name: get-alerts-conditions
  path: /v1/alert-conditions
- description: List applications
  method: GET
  name: get-applications
  path: /v1/applications
- description: Get application details
  method: GET
  name: get-application
  path: /v1/applications/{id}
personas: []
provider_name: New Relic
provider_slug: new-relic
search_terms:
- get alerts conditions
- list alert conditions for a specific policy
- list alert violations, optionally filtered to only open ones
- platform
- devops
- list alert incidents, optionally filtered to only open ones
- sre
- list alert events filtered by product or entity type
- apm
- analysis
- list alert violations
- incident response
- get application details
- list applications for context
- list alert conditions
- monitoring
- list applications for incident context
- get applications
- get application details for incident investigation
- observability
- list alert events
- alerts
- get alerts events
- analytics
- list alert conditions for a policy
- new relic
- incidents
- get alerts violations
- infrastructure
- list applications
- get alerts incidents
- get application details for incident context
- list alert incidents
- get application
- performance
slug: incident-response
source_filename: incident-response.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"New Relic Incident Response\"\n  description: \"Incident response workflow combining alerts, incidents, violations, and events for SREs investigating and resolving production issues detected by New Relic.\"\n  tags:\n    - New Relic\n    - Incident Response\n    - SRE\n    - Alerts\n    - Incidents\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      NEW_RELIC_API_KEY: NEW_RELIC_API_KEY\n\ncapability:\n  consumes:\n    - import: rest-api\n      location: ./shared/rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: incident-response-api\n      description: \"Unified REST API for New Relic incident response workflows.\"\n      resources:\n        - path: /v1/incidents\n          name: incidents\n          description: \"List alert incidents\"\n          operations:\n            - method: GET\n              name: get-alerts-incidents\n              description:\
  \ \"List alert incidents\"\n              call: \"rest-api.get-alerts-incidents\"\n              with:\n                only_open: \"rest.only_open\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/violations\n          name: violations\n          description: \"List alert violations\"\n          operations:\n            - method: GET\n              name: get-alerts-violations\n              description: \"List alert violations\"\n              call: \"rest-api.get-alerts-violations\"\n              with:\n                only_open: \"rest.only_open\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/alert-events\n          name: alert-events\n          description: \"List alert events\"\n          operations:\n            - method: GET\n              name: get-alerts-events\n\
  \              description: \"List alert events\"\n              call: \"rest-api.get-alerts-events\"\n              with:\n                filter[product]: \"rest.filter_product\"\n                filter[entity_type]: \"rest.filter_entity_type\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/alert-conditions\n          name: alert-conditions\n          description: \"List alert conditions\"\n          operations:\n            - method: GET\n              name: get-alerts-conditions\n              description: \"List alert conditions for a policy\"\n              call: \"rest-api.get-alerts-conditions\"\n              with:\n                policy_id: \"rest.policy_id\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications\n          name: applications\n       \
  \   description: \"List applications for context\"\n          operations:\n            - method: GET\n              name: get-applications\n              description: \"List applications\"\n              call: \"rest-api.get-applications\"\n              with:\n                filter[name]: \"rest.filter_name\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{id}\n          name: application-detail\n          description: \"Get application details for incident context\"\n          operations:\n            - method: GET\n              name: get-application\n              description: \"Get application details\"\n              call: \"rest-api.get-application\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace:\
  \ incident-response-mcp\n      transport: http\n      description: \"MCP server for AI-assisted New Relic incident response.\"\n      tools:\n        - name: get-alerts-incidents\n          description: \"List alert incidents, optionally filtered to only open ones\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-alerts-incidents\"\n          with:\n            only_open: \"tools.only_open\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-alerts-violations\n          description: \"List alert violations, optionally filtered to only open ones\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-alerts-violations\"\n          with:\n            only_open: \"tools.only_open\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: get-alerts-events\n          description: \"List alert events filtered by product or entity type\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-alerts-events\"\n          with:\n            filter[product]: \"tools.filter_product\"\n            filter[entity_type]: \"tools.filter_entity_type\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-alerts-conditions\n          description: \"List alert conditions for a specific policy\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-alerts-conditions\"\n          with:\n            policy_id: \"tools.policy_id\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-applications\n          description: \"List applications\
  \ for incident context\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-applications\"\n          with:\n            filter[name]: \"tools.filter_name\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application\n          description: \"Get application details for incident investigation\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-application\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/new-relic/refs/heads/main/capabilities/incident-response.yaml
tags:
- New Relic
- Incident Response
- SRE
- Alerts
- Incidents
tools:
- description: List alert incidents, optionally filtered to only open ones
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-incidents
- description: List alert violations, optionally filtered to only open ones
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-violations
- description: List alert events filtered by product or entity type
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-events
- description: List alert conditions for a specific policy
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-conditions
- description: List applications for incident context
  hints:
    openWorld: true
    readOnly: true
  name: get-applications
- description: Get application details for incident investigation
  hints:
    openWorld: true
    readOnly: true
  name: get-application
---
