---
api_specs:
- filename: utilityapi-openapi.yml
  format: yaml
  label: utilityapi
  slug: utilityapi
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/utilityapi/refs/heads/main/openapi/utilityapi-openapi.yml
categories: []
consumed_apis:
- utilityapi
description: Unified workflow capability for accessing utility energy data including meters, billing history, interval usage, and authorization management. Designed for cleantech developers, energy analytics platforms, and EV charging optimization tools.
layout: capability
name: UtilityAPI Energy Data Access
operations:
- description: List all utility meters for authorized customers
  method: GET
  name: list-meters
  path: /v1/meters
- description: Get a specific utility meter
  method: GET
  name: get-meter
  path: /v1/meters/{uid}
- description: Trigger data collection for a meter
  method: POST
  name: collect-meter-data
  path: /v1/meters/{uid}/collect
- description: Enable ongoing monitoring for a meter
  method: POST
  name: monitor-meter-data
  path: /v1/meters/{uid}/monitor
- description: List utility bills for authorized meters
  method: GET
  name: list-bills
  path: /v1/bills
- description: List meter usage intervals
  method: GET
  name: list-intervals
  path: /v1/intervals
- description: List all customer authorizations
  method: GET
  name: list-authorizations
  path: /v1/authorizations
- description: Revoke a customer's utility data authorization
  method: POST
  name: revoke-authorization
  path: /v1/authorizations/{uid}/revoke
- description: List webhook events
  method: GET
  name: list-events
  path: /v1/events
- description: List customer billing accounts
  method: GET
  name: list-billing-accounts
  path: /v1/billing-accounts
- description: List billing summaries
  method: GET
  name: list-billing-summaries
  path: /v1/billing-summaries
personas: []
provider_name: UtilityAPI
provider_slug: utilityapi
search_terms:
- list all utility meters for authorized customers
- list authorizations
- revoke a customer's utility data authorization
- list meter usage intervals
- trigger data collection for a utility meter
- list bills
- customer authorizations
- get meter
- green button
- billing
- list webhook events for monitoring data updates
- clean energy
- revoke a customer authorization
- revoke authorization
- list utility billing history for a meter
- list events
- list customer billing accounts
- trigger data collection for a meter
- list webhook events
- list meter usage interval data for energy analysis
- meter data
- list intervals
- enable ongoing data monitoring for a utility meter
- webhook events
- meter usage interval data
- list billing accounts
- list all customer authorizations
- get details for a specific utility meter
- billing summaries
- trigger meter data collection
- list customer utility data authorizations
- list billing summaries
- list utility meters for authorized customers
- billing data
- enable ongoing monitoring for a meter
- enable meter monitoring
- list utility bills for authorized meters
- utility billing data
- ev charging
- collect meter data
- get a specific utility meter
- utilities
- energy
- list meters
- monitor meter data
- individual meter details
- list billing summaries for energy cost analysis
- utility meter access for authorized customers
- customer billing accounts
slug: energy-data-access
source_filename: energy-data-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: UtilityAPI Energy Data Access\n  description: >-\n    Unified workflow capability for accessing utility energy data including meters,\n    billing history, interval usage, and authorization management. Designed for\n    cleantech developers, energy analytics platforms, and EV charging optimization tools.\n  tags:\n    - Energy\n    - Utilities\n    - Billing\n    - Meter Data\n    - Green Button\n    - Clean Energy\n    - EV Charging\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UTILITYAPI_TOKEN: UTILITYAPI_TOKEN\n\ncapability:\n  consumes:\n    - import: utilityapi\n      location: ./shared/utilityapi.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: energy-data-api\n      description: Unified REST API for energy data access and utility management.\n      resources:\n        - path: /v1/meters\n          name: meters\n          description: Utility meter\
  \ access for authorized customers\n          operations:\n            - method: GET\n              name: list-meters\n              description: List all utility meters for authorized customers\n              call: \"utilityapi.list-meters\"\n              with:\n                authorization_uid: \"rest.authorization_uid\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meters/{uid}\n          name: meter\n          description: Individual meter details\n          operations:\n            - method: GET\n              name: get-meter\n              description: Get a specific utility meter\n              call: \"utilityapi.get-meter\"\n              with:\n                uid: \"rest.uid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meters/{uid}/collect\n          name: meter-collect\n          description:\
  \ Trigger meter data collection\n          operations:\n            - method: POST\n              name: collect-meter-data\n              description: Trigger data collection for a meter\n              call: \"utilityapi.collect-meter-data\"\n              with:\n                uid: \"rest.uid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meters/{uid}/monitor\n          name: meter-monitor\n          description: Enable meter monitoring\n          operations:\n            - method: POST\n              name: monitor-meter-data\n              description: Enable ongoing monitoring for a meter\n              call: \"utilityapi.monitor-meter-data\"\n              with:\n                uid: \"rest.uid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bills\n          name: bills\n          description: Utility billing data\n          operations:\n\
  \            - method: GET\n              name: list-bills\n              description: List utility bills for authorized meters\n              call: \"utilityapi.list-bills\"\n              with:\n                meter_uid: \"rest.meter_uid\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/intervals\n          name: intervals\n          description: Meter usage interval data\n          operations:\n            - method: GET\n              name: list-intervals\n              description: List meter usage intervals\n              call: \"utilityapi.list-intervals\"\n              with:\n                meter_uid: \"rest.meter_uid\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/authorizations\n   \
  \       name: authorizations\n          description: Customer authorizations\n          operations:\n            - method: GET\n              name: list-authorizations\n              description: List all customer authorizations\n              call: \"utilityapi.list-authorizations\"\n              with:\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/authorizations/{uid}/revoke\n          name: authorization-revoke\n          description: Revoke a customer authorization\n          operations:\n            - method: POST\n              name: revoke-authorization\n              description: Revoke a customer's utility data authorization\n              call: \"utilityapi.revoke-authorization\"\n              with:\n                uid: \"rest.uid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n\
  \          name: events\n          description: Webhook events\n          operations:\n            - method: GET\n              name: list-events\n              description: List webhook events\n              call: \"utilityapi.list-events\"\n              with:\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/billing-accounts\n          name: billing-accounts\n          description: Customer billing accounts\n          operations:\n            - method: GET\n              name: list-billing-accounts\n              description: List customer billing accounts\n              call: \"utilityapi.list-billing-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/billing-summaries\n          name: billing-summaries\n          description: Billing summaries\n          operations:\n            - method: GET\n\
  \              name: list-billing-summaries\n              description: List billing summaries\n              call: \"utilityapi.list-billing-summaries\"\n              with:\n                billing_account_uid: \"rest.billing_account_uid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: energy-data-mcp\n      transport: http\n      description: MCP server for AI-assisted energy data analysis and utility management.\n      tools:\n        - name: list-meters\n          description: List utility meters for authorized customers\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"utilityapi.list-meters\"\n          with:\n            authorization_uid: \"tools.authorization_uid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-meter\n          description: Get details for a specific\
  \ utility meter\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"utilityapi.get-meter\"\n          with:\n            uid: \"tools.uid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: collect-meter-data\n          description: Trigger data collection for a utility meter\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"utilityapi.collect-meter-data\"\n          with:\n            uid: \"tools.uid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: monitor-meter-data\n          description: Enable ongoing data monitoring for a utility meter\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"utilityapi.monitor-meter-data\"\n          with:\n            uid: \"tools.uid\"\n          outputParameters:\n            - type: object\n           \
  \   mapping: \"$.\"\n        - name: list-bills\n          description: List utility billing history for a meter\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"utilityapi.list-bills\"\n          with:\n            meter_uid: \"tools.meter_uid\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-intervals\n          description: List meter usage interval data for energy analysis\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"utilityapi.list-intervals\"\n          with:\n            meter_uid: \"tools.meter_uid\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-authorizations\n          description: List customer utility data authorizations\n \
  \         hints:\n            readOnly: true\n            openWorld: true\n          call: \"utilityapi.list-authorizations\"\n          with:\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: revoke-authorization\n          description: Revoke a customer's utility data authorization\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"utilityapi.revoke-authorization\"\n          with:\n            uid: \"tools.uid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-events\n          description: List webhook events for monitoring data updates\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"utilityapi.list-events\"\n          with:\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-billing-accounts\n          description: List customer billing accounts\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"utilityapi.list-billing-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-billing-summaries\n          description: List billing summaries for energy cost analysis\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"utilityapi.list-billing-summaries\"\n          with:\n            billing_account_uid: \"tools.billing_account_uid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/utilityapi/refs/heads/main/capabilities/energy-data-access.yaml
tags:
- Energy
- Utilities
- Billing
- Meter Data
- Green Button
- Clean Energy
- EV Charging
tools:
- description: List utility meters for authorized customers
  hints:
    openWorld: true
    readOnly: true
  name: list-meters
- description: Get details for a specific utility meter
  hints:
    idempotent: true
    readOnly: true
  name: get-meter
- description: Trigger data collection for a utility meter
  hints:
    destructive: false
    readOnly: false
  name: collect-meter-data
- description: Enable ongoing data monitoring for a utility meter
  hints:
    idempotent: true
    readOnly: false
  name: monitor-meter-data
- description: List utility billing history for a meter
  hints:
    openWorld: true
    readOnly: true
  name: list-bills
- description: List meter usage interval data for energy analysis
  hints:
    openWorld: true
    readOnly: true
  name: list-intervals
- description: List customer utility data authorizations
  hints:
    openWorld: true
    readOnly: true
  name: list-authorizations
- description: Revoke a customer's utility data authorization
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoke-authorization
- description: List webhook events for monitoring data updates
  hints:
    openWorld: true
    readOnly: true
  name: list-events
- description: List customer billing accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-billing-accounts
- description: List billing summaries for energy cost analysis
  hints:
    openWorld: true
    readOnly: true
  name: list-billing-summaries
---
