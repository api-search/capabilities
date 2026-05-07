---
categories: []
consumed_apis: []
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
- list customer billing accounts
- list webhook events for monitoring data updates
- revoke a customer's utility data authorization
- list meter usage intervals
- list events
- list billing accounts
- individual meter details
- customer authorizations
- monitor meter data
- billing
- list meters
- collect meter data
- trigger data collection for a utility meter
- get details for a specific utility meter
- ev charging
- list customer utility data authorizations
- trigger meter data collection
- utilities
- revoke a customer authorization
- list meter usage interval data for energy analysis
- list all customer authorizations
- list utility meters for authorized customers
- utility billing data
- meter usage interval data
- revoke authorization
- meter data
- list webhook events
- clean energy
- get meter
- energy
- list utility bills for authorized meters
- list bills
- get a specific utility meter
- customer billing accounts
- list billing summaries
- webhook events
- billing data
- utility meter access for authorized customers
- list billing summaries for energy cost analysis
- list authorizations
- enable meter monitoring
- list utility billing history for a meter
- green button
- enable ongoing data monitoring for a utility meter
- list all utility meters for authorized customers
- enable ongoing monitoring for a meter
- list intervals
- trigger data collection for a meter
- billing summaries
slug: energy-data-access
source_filename: energy-data-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: UtilityAPI Energy Data Access\n  description: Unified workflow capability for accessing utility energy data including meters, billing history, interval usage,\n    and authorization management. Designed for cleantech developers, energy analytics platforms, and EV charging optimization\n    tools.\n  tags:\n  - Energy\n  - Utilities\n  - Billing\n  - Meter Data\n  - Green Button\n  - Clean Energy\n  - EV Charging\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UTILITYAPI_TOKEN: UTILITYAPI_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: utilityapi\n    baseUri: https://utilityapi.com/api/v2\n    description: UtilityAPI REST API for utility data access\n    authentication:\n      type: bearer\n      token: '{{UTILITYAPI_TOKEN}}'\n    resources:\n    - name: meters\n      path: /meters\n      description: Utility service meters for authorized customers\n      operations:\n      - name:\
  \ list-meters\n        method: GET\n        description: List all utility meters for authorized customers\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of meters to return\n        - name: authorization_uid\n          in: query\n          type: string\n          required: false\n          description: Filter meters by authorization UID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-meter\n        method: GET\n        description: Retrieve a specific utility meter\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n          description: Meter unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: collect-meter-data\n\
  \        method: POST\n        description: Trigger data collection for a utility meter\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n          description: Meter unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: monitor-meter-data\n        method: POST\n        description: Enable ongoing monitoring for a utility meter\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n          description: Meter unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bills\n      path: /bills\n      description: Utility billing information\n      operations:\n      - name: list-bills\n        method: GET\n        description: List all utility bills for authorized\
  \ meters\n        inputParameters:\n        - name: meter_uid\n          in: query\n          type: string\n          required: false\n          description: Filter bills by meter UID\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start date filter (ISO 8601)\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End date filter (ISO 8601)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of bills to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: intervals\n      path: /intervals\n      description: Meter usage intervals\n      operations:\n      - name: list-intervals\n        method: GET\n        description: List meter usage intervals for authorized meters\n        inputParameters:\n\
  \        - name: meter_uid\n          in: query\n          type: string\n          required: false\n          description: Filter intervals by meter UID\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start datetime filter (ISO 8601)\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End datetime filter (ISO 8601)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of intervals to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authorizations\n      path: /authorizations\n      description: Customer authorizations for utility data access\n      operations:\n      - name: list-authorizations\n        method: GET\n        description: List all submitted authorizations\n    \
  \    inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by authorization status\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of authorizations to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-authorization\n        method: GET\n        description: Retrieve a specific authorization\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n          description: Authorization unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revoke-authorization\n        method: POST\n        description: Revoke a customer authorization\n        inputParameters:\n\
  \        - name: uid\n          in: path\n          type: string\n          required: true\n          description: Authorization unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      description: Webhook events and notifications\n      operations:\n      - name: list-events\n        method: GET\n        description: List webhook events for the authenticated account\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by event type\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of events to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-event\n        method: GET\n\
  \        description: Retrieve a specific webhook event\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n          description: Event unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-accounts\n      path: /accounting/billing-accounts\n      description: Customer billing accounts\n      operations:\n      - name: list-billing-accounts\n        method: GET\n        description: List all customer billing accounts\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of accounts to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-billing-account\n        method: GET\n        description: Retrieve a specific\
  \ billing account\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n          description: Billing account unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-summaries\n      path: /accounting/billing-summaries\n      description: Billing summaries for customer accounts\n      operations:\n      - name: list-billing-summaries\n        method: GET\n        description: List billing summaries for customer accounts\n        inputParameters:\n        - name: billing_account_uid\n          in: query\n          type: string\n          required: false\n          description: Filter by billing account UID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of summaries to return\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-billing-summary\n        method: GET\n        description: Retrieve a specific billing summary\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n          description: Billing summary unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: energy-data-api\n    description: Unified REST API for energy data access and utility management.\n    resources:\n    - path: /v1/meters\n      name: meters\n      description: Utility meter access for authorized customers\n      operations:\n      - method: GET\n        name: list-meters\n        description: List all utility meters for authorized customers\n        call: utilityapi.list-meters\n        with:\n          authorization_uid: rest.authorization_uid\n\
  \          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/meters/{uid}\n      name: meter\n      description: Individual meter details\n      operations:\n      - method: GET\n        name: get-meter\n        description: Get a specific utility meter\n        call: utilityapi.get-meter\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/meters/{uid}/collect\n      name: meter-collect\n      description: Trigger meter data collection\n      operations:\n      - method: POST\n        name: collect-meter-data\n        description: Trigger data collection for a meter\n        call: utilityapi.collect-meter-data\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/meters/{uid}/monitor\n      name: meter-monitor\n      description: Enable meter monitoring\n      operations:\n\
  \      - method: POST\n        name: monitor-meter-data\n        description: Enable ongoing monitoring for a meter\n        call: utilityapi.monitor-meter-data\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bills\n      name: bills\n      description: Utility billing data\n      operations:\n      - method: GET\n        name: list-bills\n        description: List utility bills for authorized meters\n        call: utilityapi.list-bills\n        with:\n          meter_uid: rest.meter_uid\n          start: rest.start\n          end: rest.end\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/intervals\n      name: intervals\n      description: Meter usage interval data\n      operations:\n      - method: GET\n        name: list-intervals\n        description: List meter usage intervals\n        call: utilityapi.list-intervals\n        with:\n          meter_uid: rest.meter_uid\n\
  \          start: rest.start\n          end: rest.end\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/authorizations\n      name: authorizations\n      description: Customer authorizations\n      operations:\n      - method: GET\n        name: list-authorizations\n        description: List all customer authorizations\n        call: utilityapi.list-authorizations\n        with:\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/authorizations/{uid}/revoke\n      name: authorization-revoke\n      description: Revoke a customer authorization\n      operations:\n      - method: POST\n        name: revoke-authorization\n        description: Revoke a customer's utility data authorization\n        call: utilityapi.revoke-authorization\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name:\
  \ events\n      description: Webhook events\n      operations:\n      - method: GET\n        name: list-events\n        description: List webhook events\n        call: utilityapi.list-events\n        with:\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing-accounts\n      name: billing-accounts\n      description: Customer billing accounts\n      operations:\n      - method: GET\n        name: list-billing-accounts\n        description: List customer billing accounts\n        call: utilityapi.list-billing-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing-summaries\n      name: billing-summaries\n      description: Billing summaries\n      operations:\n      - method: GET\n        name: list-billing-summaries\n        description: List billing summaries\n        call: utilityapi.list-billing-summaries\n        with:\n          billing_account_uid: rest.billing_account_uid\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: energy-data-mcp\n    transport: http\n    description: MCP server for AI-assisted energy data analysis and utility management.\n    tools:\n    - name: list-meters\n      description: List utility meters for authorized customers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: utilityapi.list-meters\n      with:\n        authorization_uid: tools.authorization_uid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-meter\n      description: Get details for a specific utility meter\n      hints:\n        readOnly: true\n        idempotent: true\n      call: utilityapi.get-meter\n      with:\n        uid: tools.uid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: collect-meter-data\n      description: Trigger data collection for a utility meter\n      hints:\n        readOnly: false\n\
  \        destructive: false\n      call: utilityapi.collect-meter-data\n      with:\n        uid: tools.uid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: monitor-meter-data\n      description: Enable ongoing data monitoring for a utility meter\n      hints:\n        readOnly: false\n        idempotent: true\n      call: utilityapi.monitor-meter-data\n      with:\n        uid: tools.uid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bills\n      description: List utility billing history for a meter\n      hints:\n        readOnly: true\n        openWorld: true\n      call: utilityapi.list-bills\n      with:\n        meter_uid: tools.meter_uid\n        start: tools.start\n        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-intervals\n      description: List meter usage interval data for energy analysis\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: utilityapi.list-intervals\n      with:\n        meter_uid: tools.meter_uid\n        start: tools.start\n        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-authorizations\n      description: List customer utility data authorizations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: utilityapi.list-authorizations\n      with:\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revoke-authorization\n      description: Revoke a customer's utility data authorization\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: utilityapi.revoke-authorization\n      with:\n        uid: tools.uid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-events\n      description: List webhook events for monitoring data updates\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: utilityapi.list-events\n      with:\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-billing-accounts\n      description: List customer billing accounts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: utilityapi.list-billing-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-billing-summaries\n      description: List billing summaries for energy cost analysis\n      hints:\n        readOnly: true\n        openWorld: true\n      call: utilityapi.list-billing-summaries\n      with:\n        billing_account_uid: tools.billing_account_uid\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
