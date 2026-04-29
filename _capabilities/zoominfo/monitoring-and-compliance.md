---
api_specs:
- filename: zoominfo-openapi.yml
  format: yaml
  label: zoominfo
  slug: zoominfo
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/zoominfo/refs/heads/main/openapi/zoominfo-openapi.yml
categories:
- compliance
consumed_apis:
- zoominfo
description: Unified capability for monitoring and compliance workflows combining webhook management, API usage tracking, and compliance operations. Used by platform admins and data governance teams to manage data monitoring, ensure compliance, and track API consumption.
layout: capability
name: ZoomInfo Monitoring And Compliance
operations:
- description: Create a new webhook subscription.
  method: POST
  name: create-webhook
  path: /v1/webhooks
- description: List all webhook subscriptions.
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Update an existing webhook subscription.
  method: PUT
  name: update-webhook
  path: /v1/webhooks/{webhookId}
- description: Delete a webhook subscription.
  method: DELETE
  name: delete-webhook
  path: /v1/webhooks/{webhookId}
- description: Validate a webhook target URL.
  method: POST
  name: validate-target-url
  path: /v1/webhooks/validate
- description: Get available webhook subscription types.
  method: GET
  name: get-subscription-types
  path: /v1/webhooks/subscription-types
- description: Check compliance status for specified contacts.
  method: POST
  name: check-compliance
  path: /v1/compliance
- description: Get API usage data.
  method: GET
  name: get-usage
  path: /v1/usage
personas: []
provider_name: ZoomInfo
provider_slug: zoominfo
search_terms:
- webhook subscription management.
- get api usage data and consumption metrics.
- get subscription types
- get api usage data.
- monitoring
- available webhook subscription types.
- validate target url
- api usage tracking.
- get usage
- get available webhook subscription types.
- compliance
- individual webhook management.
- webhook target url validation.
- contacts
- validate a webhook target url.
- lead generation
- delete webhook
- api usage
- delete a webhook subscription.
- check data compliance status for specified contacts.
- update an existing webhook subscription.
- b2b
- b2b data
- create webhook
- data
- contact database
- marketing intelligence
- create a new webhook subscription.
- list all webhook subscriptions.
- company data
- create a new webhook subscription for data change notifications.
- update webhook
- data compliance operations.
- check compliance
- list all configured webhook subscriptions.
- webhooks
- zoominfo
- list webhooks
- validate a webhook target url is reachable.
- check compliance status for specified contacts.
- sales intelligence
slug: monitoring-and-compliance
source_filename: monitoring-and-compliance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"ZoomInfo Monitoring And Compliance\"\n  description: \"Unified capability for monitoring and compliance workflows combining webhook management, API usage tracking, and compliance operations. Used by platform admins and data governance teams to manage data monitoring, ensure compliance, and track API consumption.\"\n  tags:\n    - ZoomInfo\n    - Monitoring\n    - Compliance\n    - Webhooks\n    - API Usage\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ZOOMINFO_USERNAME: ZOOMINFO_USERNAME\n      ZOOMINFO_PASSWORD: ZOOMINFO_PASSWORD\n\ncapability:\n  consumes:\n    - import: zoominfo\n      location: ./shared/zoominfo.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: monitoring-and-compliance-api\n      description: \"Unified REST API for monitoring and compliance workflows.\"\n      resources:\n        - path: /v1/webhooks\n          name: webhooks\n\
  \          description: \"Webhook subscription management.\"\n          operations:\n            - method: POST\n              name: create-webhook\n              description: \"Create a new webhook subscription.\"\n              call: \"zoominfo.create-webhook\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-webhooks\n              description: \"List all webhook subscriptions.\"\n              call: \"zoominfo.list-webhooks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks/{webhookId}\n          name: webhook-management\n          description: \"Individual webhook management.\"\n          operations:\n            - method: PUT\n              name: update-webhook\n              description: \"Update an existing webhook subscription.\"\n              call: \"zoominfo.update-webhook\"\n              with:\n\
  \                webhookId: \"rest.webhookId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-webhook\n              description: \"Delete a webhook subscription.\"\n              call: \"zoominfo.delete-webhook\"\n              with:\n                webhookId: \"rest.webhookId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks/validate\n          name: webhook-validation\n          description: \"Webhook target URL validation.\"\n          operations:\n            - method: POST\n              name: validate-target-url\n              description: \"Validate a webhook target URL.\"\n              call: \"zoominfo.validate-target-url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks/subscription-types\n          name:\
  \ subscription-types\n          description: \"Available webhook subscription types.\"\n          operations:\n            - method: GET\n              name: get-subscription-types\n              description: \"Get available webhook subscription types.\"\n              call: \"zoominfo.get-subscription-types\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compliance\n          name: compliance\n          description: \"Data compliance operations.\"\n          operations:\n            - method: POST\n              name: check-compliance\n              description: \"Check compliance status for specified contacts.\"\n              call: \"zoominfo.check-compliance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/usage\n          name: usage\n          description: \"API usage tracking.\"\n          operations:\n            - method: GET\n  \
  \            name: get-usage\n              description: \"Get API usage data.\"\n              call: \"zoominfo.lookup-usage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: monitoring-and-compliance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted monitoring and compliance management.\"\n      tools:\n        - name: create-webhook\n          description: \"Create a new webhook subscription for data change notifications.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"zoominfo.create-webhook\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-webhooks\n          description: \"List all configured webhook subscriptions.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zoominfo.list-webhooks\"\n \
  \         outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-webhook\n          description: \"Update an existing webhook subscription.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"zoominfo.update-webhook\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-webhook\n          description: \"Delete a webhook subscription.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"zoominfo.delete-webhook\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-target-url\n          description: \"Validate a webhook target URL is reachable.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zoominfo.validate-target-url\"\n          outputParameters:\n    \
  \        - type: object\n              mapping: \"$.\"\n        - name: get-subscription-types\n          description: \"Get available webhook subscription types.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zoominfo.get-subscription-types\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-compliance\n          description: \"Check data compliance status for specified contacts.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"zoominfo.check-compliance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-usage\n          description: \"Get API usage data and consumption metrics.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"zoominfo.lookup-usage\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zoominfo/refs/heads/main/capabilities/monitoring-and-compliance.yaml
tags:
- ZoomInfo
- Monitoring
- Compliance
- Webhooks
- API Usage
tools:
- description: Create a new webhook subscription for data change notifications.
  hints:
    idempotent: false
    readOnly: false
  name: create-webhook
- description: List all configured webhook subscriptions.
  hints:
    idempotent: true
    readOnly: true
  name: list-webhooks
- description: Update an existing webhook subscription.
  hints:
    idempotent: true
    readOnly: false
  name: update-webhook
- description: Delete a webhook subscription.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-webhook
- description: Validate a webhook target URL is reachable.
  hints:
    idempotent: true
    readOnly: true
  name: validate-target-url
- description: Get available webhook subscription types.
  hints:
    idempotent: true
    readOnly: true
  name: get-subscription-types
- description: Check data compliance status for specified contacts.
  hints:
    openWorld: true
    readOnly: true
  name: check-compliance
- description: Get API usage data and consumption metrics.
  hints:
    idempotent: true
    readOnly: true
  name: get-usage
---
