---
categories:
- incident-management
consumed_apis: []
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
- get alerts incidents
- apm
- get alerts conditions
- list alert policies
- list alert violations
- infrastructure
- analytics
- update an alert policy
- devops
- configuration
- alerting
- get alerts policies
- monitoring
- manage alert policies
- list conditions for a policy
- list alert conditions
- new relic
- delete alerts policy
- list alert incidents
- list alert events filtered by product or entity type
- observability
- delete an alert policy
- platform administration
- create alerts policy
- get alerts events
- performance
- platform
- get alerts violations
- update or delete an alert policy
- update alerts policy
- analysis
- policies
- list alert events
- create a new alert policy
- list alert conditions for a specific policy
- list all alert policies
slug: full-stack-observability
source_filename: full-stack-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: New Relic Alerting Configuration\n  description: Alert policy and condition management workflow for platform admins configuring and maintaining New Relic alerting\n    rules, notification channels, and policy structures.\n  tags:\n  - New Relic\n  - Alerting\n  - Configuration\n  - Platform Administration\n  - Policies\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    NEW_RELIC_API_KEY: NEW_RELIC_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: rest-api\n    baseUri: https://api.newrelic.com/v2\n    description: New Relic REST API v2 for managing applications, alerts, and retrieving monitoring data.\n    authentication:\n      type: apikey\n      key: Api-Key\n      value: '{{NEW_RELIC_API_KEY}}'\n      placement: header\n    resources:\n    - name: applications\n      path: /applications.json\n      description: Manage monitored applications\n      operations:\n      - name: get-applications\n\
  \        method: GET\n        description: Retrieves a paginated list of all applications.\n        inputParameters:\n        - name: filter[name]\n          in: query\n          type: string\n          required: false\n          description: Filter by application name.\n        - name: filter[host]\n          in: query\n          type: string\n          required: false\n          description: Filter by application host.\n        - name: filter[ids]\n          in: query\n          type: array\n          required: false\n          description: Filter by application IDs.\n        - name: filter[language]\n          in: query\n          type: string\n          required: false\n          description: Filter by application language.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: application-detail\n      path: /applications/{id}.json\n      description: Get, update, or delete a specific application\n      operations:\n      - name: get-application\n        method: GET\n        description: Retrieves a specific application by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-application\n        method: PUT\n        description: Updates an application's settings.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            application: '{{tools.application}}'\n      - name: delete-application\n        method: DELETE\n        description: Removes an application from New Relic.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application-deployments\n      path: /applications/{application_id}/deployments.json\n      description: Manage application deployments\n      operations:\n      - name: get-deployments\n        method: GET\n        description: Retrieves deployment records for an application.\n        inputParameters:\n        - name: application_id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        - name: page\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment\n        method: POST\n        description: Records a new deployment for an application.\n        inputParameters:\n        - name: application_id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            deployment: '{{tools.deployment}}'\n    - name: application-hosts\n      path: /applications/{application_id}/hosts.json\n      description: List application hosts\n      operations:\n      - name: get-application-hosts\n        method: GET\n        description: Retrieves a list of hosts for an application.\n        inputParameters:\n \
  \       - name: application_id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application-metrics\n      path: /applications/{application_id}/metrics.json\n      description: List application metrics\n      operations:\n      - name: get-application-metrics\n        method: GET\n        description: Retrieves available metric names for an application.\n        inputParameters:\n        - name: application_id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter by metric name.\n\
  \        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application-metrics-data\n      path: /applications/{application_id}/metrics/data.json\n      description: Query application metric data\n      operations:\n      - name: get-application-metrics-data\n        method: GET\n        description: Retrieves metric data for an application.\n        inputParameters:\n        - name: application_id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        - name: names[]\n          in: query\n          type: array\n          required: true\n          description: Metric names to retrieve.\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start\
  \ of the time range.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the time range.\n        - name: period\n          in: query\n          type: integer\n          required: false\n          description: Period in seconds for data point aggregation.\n        - name: summarize\n          in: query\n          type: boolean\n          required: false\n          description: Whether to return a single summarized data point.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: key-transactions\n      path: /key_transactions.json\n      description: List key transactions\n      operations:\n      - name: get-key-transactions\n        method: GET\n        description: Retrieves a list of key transactions.\n        inputParameters:\n        - name: filter[name]\n          in: query\n          type: string\n          required: false\n\
  \          description: Filter by key transaction name.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts-policies\n      path: /alerts_policies.json\n      description: Manage alert policies\n      operations:\n      - name: get-alerts-policies\n        method: GET\n        description: Retrieves a list of alert policies.\n        inputParameters:\n        - name: filter[name]\n          in: query\n          type: string\n          required: false\n          description: Filter by policy name.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: create-alerts-policy\n        method: POST\n        description: Creates a new alert policy.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            policy: '{{tools.policy}}'\n    - name: alerts-policy-detail\n      path: /alerts_policies/{policy_id}.json\n      description: Update or delete an alert policy\n      operations:\n      - name: update-alerts-policy\n        method: PUT\n        description: Updates an alert policy.\n        inputParameters:\n        - name: policy_id\n          in: path\n          type: integer\n          required: true\n          description: Policy ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            policy: '{{tools.policy}}'\n   \
  \   - name: delete-alerts-policy\n        method: DELETE\n        description: Deletes an alert policy.\n        inputParameters:\n        - name: policy_id\n          in: path\n          type: integer\n          required: true\n          description: Policy ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts-conditions\n      path: /alerts_conditions.json\n      description: List alert conditions\n      operations:\n      - name: get-alerts-conditions\n        method: GET\n        description: Retrieves a list of alert conditions.\n        inputParameters:\n        - name: policy_id\n          in: query\n          type: integer\n          required: true\n          description: Policy ID to filter conditions.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: alerts-incidents\n      path: /alerts_incidents.json\n      description: List alert incidents\n      operations:\n      - name: get-alerts-incidents\n        method: GET\n        description: Retrieves a list of alert incidents.\n        inputParameters:\n        - name: only_open\n          in: query\n          type: boolean\n          required: false\n          description: Filter for only open incidents.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts-violations\n      path: /alerts_violations.json\n      description: List alert violations\n      operations:\n      - name: get-alerts-violations\n        method: GET\n        description: Retrieves a list of alert violations.\n\
  \        inputParameters:\n        - name: only_open\n          in: query\n          type: boolean\n          required: false\n          description: Filter for only open violations.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts-events\n      path: /alerts_events.json\n      description: List alert events\n      operations:\n      - name: get-alerts-events\n        method: GET\n        description: Retrieves a list of alert events.\n        inputParameters:\n        - name: filter[product]\n          in: query\n          type: string\n          required: false\n          description: Filter by product type.\n        - name: filter[entity_type]\n          in: query\n          type: string\n          required: false\n          description: Filter by entity\
  \ type.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: alerting-config-api\n    description: Unified REST API for New Relic alert policy and condition management.\n    resources:\n    - path: /v1/policies\n      name: policies\n      description: Manage alert policies\n      operations:\n      - method: GET\n        name: get-alerts-policies\n        description: List alert policies\n        call: rest-api.get-alerts-policies\n        with:\n          filter[name]: rest.filter_name\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-alerts-policy\n        description: Create a new alert policy\n        call: rest-api.create-alerts-policy\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies/{policyId}\n      name: policy-detail\n      description: Update or delete an alert policy\n      operations:\n      - method: PUT\n        name: update-alerts-policy\n        description: Update an alert policy\n        call: rest-api.update-alerts-policy\n        with:\n          policy_id: rest.policyId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-alerts-policy\n        description: Delete an alert policy\n        call: rest-api.delete-alerts-policy\n        with:\n          policy_id: rest.policyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/conditions\n      name: conditions\n      description: List alert conditions\n      operations:\n      - method: GET\n        name: get-alerts-conditions\n        description: List conditions for a policy\n        call: rest-api.get-alerts-conditions\n\
  \        with:\n          policy_id: rest.policy_id\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/incidents\n      name: incidents\n      description: List alert incidents\n      operations:\n      - method: GET\n        name: get-alerts-incidents\n        description: List alert incidents\n        call: rest-api.get-alerts-incidents\n        with:\n          only_open: rest.only_open\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/violations\n      name: violations\n      description: List alert violations\n      operations:\n      - method: GET\n        name: get-alerts-violations\n        description: List alert violations\n        call: rest-api.get-alerts-violations\n        with:\n          only_open: rest.only_open\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alert-events\n\
  \      name: alert-events\n      description: List alert events\n      operations:\n      - method: GET\n        name: get-alerts-events\n        description: List alert events\n        call: rest-api.get-alerts-events\n        with:\n          filter[product]: rest.filter_product\n          filter[entity_type]: rest.filter_entity_type\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: alerting-config-mcp\n    transport: http\n    description: MCP server for AI-assisted New Relic alert policy and condition management.\n    tools:\n    - name: get-alerts-policies\n      description: List all alert policies\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.get-alerts-policies\n      with:\n        filter[name]: tools.filter_name\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-alerts-policy\n \
  \     description: Create a new alert policy\n      hints:\n        readOnly: false\n        openWorld: true\n      call: rest-api.create-alerts-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-alerts-policy\n      description: Update an alert policy\n      hints:\n        readOnly: false\n        idempotent: true\n        openWorld: true\n      call: rest-api.update-alerts-policy\n      with:\n        policy_id: tools.policy_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-alerts-policy\n      description: Delete an alert policy\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n        openWorld: true\n      call: rest-api.delete-alerts-policy\n      with:\n        policy_id: tools.policy_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-alerts-conditions\n      description: List alert conditions for a specific policy\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.get-alerts-conditions\n      with:\n        policy_id: tools.policy_id\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-alerts-incidents\n      description: List alert incidents\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.get-alerts-incidents\n      with:\n        only_open: tools.only_open\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-alerts-violations\n      description: List alert violations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.get-alerts-violations\n      with:\n        only_open: tools.only_open\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-alerts-events\n      description: List alert events filtered by product or entity\
  \ type\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.get-alerts-events\n      with:\n        filter[product]: tools.filter_product\n        filter[entity_type]: tools.filter_entity_type\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
