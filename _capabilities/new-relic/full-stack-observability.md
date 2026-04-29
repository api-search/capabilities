---
categories:
- incident-management
consumed_apis:
- rest-api
description: Alert policy and condition management workflow for platform admins configuring and maintaining New Relic alerting rules, notification channels, and policy structures.
layout: capability
name: New Relic Alerting Configuration
operations:
- description: List alert policies
  method: GET
  name: get-alerts-policies
  path: /v1/policies
- description: Create a new alert policy
  method: POST
  name: create-alerts-policy
  path: /v1/policies
- description: Update an alert policy
  method: PUT
  name: update-alerts-policy
  path: /v1/policies/{policyId}
- description: Delete an alert policy
  method: DELETE
  name: delete-alerts-policy
  path: /v1/policies/{policyId}
- description: List conditions for a policy
  method: GET
  name: get-alerts-conditions
  path: /v1/conditions
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
personas: []
provider_name: New Relic
provider_slug: new-relic
search_terms:
- monitoring
- list conditions for a policy
- list alert violations
- update or delete an alert policy
- get alerts incidents
- delete alerts policy
- analytics
- get alerts policies
- platform administration
- get alerts conditions
- update an alert policy
- delete an alert policy
- apm
- observability
- get alerts events
- list alert conditions
- new relic
- platform
- performance
- update alerts policy
- get alerts violations
- configuration
- list alert conditions for a specific policy
- devops
- infrastructure
- list alert events
- list alert incidents
- alerting
- list all alert policies
- manage alert policies
- list alert events filtered by product or entity type
- create a new alert policy
- create alerts policy
- policies
- list alert policies
- analysis
slug: full-stack-observability
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"New Relic Alerting Configuration\"\n  description: \"Alert policy and condition management workflow for platform admins configuring and maintaining New Relic alerting rules, notification channels, and policy structures.\"\n  tags:\n    - New Relic\n    - Alerting\n    - Configuration\n    - Platform Administration\n    - Policies\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      NEW_RELIC_API_KEY: NEW_RELIC_API_KEY\n\ncapability:\n  consumes:\n    - import: rest-api\n      location: ./shared/rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: alerting-config-api\n      description: \"Unified REST API for New Relic alert policy and condition management.\"\n      resources:\n        - path: /v1/policies\n          name: policies\n          description: \"Manage alert policies\"\n          operations:\n            - method: GET\n              name:\
  \ get-alerts-policies\n              description: \"List alert policies\"\n              call: \"rest-api.get-alerts-policies\"\n              with:\n                filter[name]: \"rest.filter_name\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-alerts-policy\n              description: \"Create a new alert policy\"\n              call: \"rest-api.create-alerts-policy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/policies/{policyId}\n          name: policy-detail\n          description: \"Update or delete an alert policy\"\n          operations:\n            - method: PUT\n              name: update-alerts-policy\n              description: \"Update an alert policy\"\n              call: \"rest-api.update-alerts-policy\"\n              with:\n                policy_id:\
  \ \"rest.policyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-alerts-policy\n              description: \"Delete an alert policy\"\n              call: \"rest-api.delete-alerts-policy\"\n              with:\n                policy_id: \"rest.policyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/conditions\n          name: conditions\n          description: \"List alert conditions\"\n          operations:\n            - method: GET\n              name: get-alerts-conditions\n              description: \"List conditions for a policy\"\n              call: \"rest-api.get-alerts-conditions\"\n              with:\n                policy_id: \"rest.policy_id\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    \
  \    - path: /v1/incidents\n          name: incidents\n          description: \"List alert incidents\"\n          operations:\n            - method: GET\n              name: get-alerts-incidents\n              description: \"List alert incidents\"\n              call: \"rest-api.get-alerts-incidents\"\n              with:\n                only_open: \"rest.only_open\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/violations\n          name: violations\n          description: \"List alert violations\"\n          operations:\n            - method: GET\n              name: get-alerts-violations\n              description: \"List alert violations\"\n              call: \"rest-api.get-alerts-violations\"\n              with:\n                only_open: \"rest.only_open\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n       \
  \           mapping: \"$.\"\n        - path: /v1/alert-events\n          name: alert-events\n          description: \"List alert events\"\n          operations:\n            - method: GET\n              name: get-alerts-events\n              description: \"List alert events\"\n              call: \"rest-api.get-alerts-events\"\n              with:\n                filter[product]: \"rest.filter_product\"\n                filter[entity_type]: \"rest.filter_entity_type\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: alerting-config-mcp\n      transport: http\n      description: \"MCP server for AI-assisted New Relic alert policy and condition management.\"\n      tools:\n        - name: get-alerts-policies\n          description: \"List all alert policies\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"rest-api.get-alerts-policies\"\n          with:\n            filter[name]: \"tools.filter_name\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-alerts-policy\n          description: \"Create a new alert policy\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"rest-api.create-alerts-policy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-alerts-policy\n          description: \"Update an alert policy\"\n          hints:\n            readOnly: false\n            idempotent: true\n            openWorld: true\n          call: \"rest-api.update-alerts-policy\"\n          with:\n            policy_id: \"tools.policy_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-alerts-policy\n          description: \"Delete an alert\
  \ policy\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          call: \"rest-api.delete-alerts-policy\"\n          with:\n            policy_id: \"tools.policy_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-alerts-conditions\n          description: \"List alert conditions for a specific policy\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-alerts-conditions\"\n          with:\n            policy_id: \"tools.policy_id\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-alerts-incidents\n          description: \"List alert incidents\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-alerts-incidents\"\n          with:\n\
  \            only_open: \"tools.only_open\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-alerts-violations\n          description: \"List alert violations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-alerts-violations\"\n          with:\n            only_open: \"tools.only_open\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-alerts-events\n          description: \"List alert events filtered by product or entity type\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-alerts-events\"\n          with:\n            filter[product]: \"tools.filter_product\"\n            filter[entity_type]: \"tools.filter_entity_type\"\n            page: \"tools.page\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/new-relic/refs/heads/main/capabilities/full-stack-observability.yaml
tags:
- New Relic
- Alerting
- Configuration
- Platform Administration
- Policies
tools:
- description: List all alert policies
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-policies
- description: Create a new alert policy
  hints:
    openWorld: true
    readOnly: false
  name: create-alerts-policy
- description: Update an alert policy
  hints:
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-alerts-policy
- description: Delete an alert policy
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-alerts-policy
- description: List alert conditions for a specific policy
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-conditions
- description: List alert incidents
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-incidents
- description: List alert violations
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-violations
- description: List alert events filtered by product or entity type
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-events
---
