---
categories:
- monitoring
consumed_apis: []
description: Unified workflow for SAP HANA Cloud database administration including instance lifecycle management, monitoring alerts, performance metrics, and metering. Used by database administrators and cloud platform engineers.
layout: capability
name: SAP HANA Cloud Administration
operations:
- description: List all SAP HANA Cloud instances.
  method: GET
  name: list-instances
  path: /v1/instances
- description: Provision a new instance.
  method: POST
  name: create-instance
  path: /v1/instances
- description: Get instance details.
  method: GET
  name: get-instance
  path: /v1/instances/{instanceId}
- description: Update an instance.
  method: PATCH
  name: update-instance
  path: /v1/instances/{instanceId}
- description: Delete an instance.
  method: DELETE
  name: delete-instance
  path: /v1/instances/{instanceId}
- description: List alert events.
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: Get database metrics.
  method: GET
  name: get-metrics
  path: /v1/metrics
personas: []
provider_name: SAP HANA
provider_slug: sap-hana
search_terms:
- update instance configuration.
- list triggered alert events for an instance.
- list instance mappings.
- get metrics
- delete an instance.
- list all sap hana cloud instances.
- analytics
- list alert rules for an instance.
- update alert rules
- list all sap hana cloud service instances.
- create a new instance mapping.
- in-memory
- sap hana
- cloud
- update an instance.
- list mappings
- provision a new instance.
- list inventory
- instance lifecycle management.
- monitoring
- enterprise
- performance metrics.
- list all instances in the inventory.
- update instance
- get database metrics.
- get details of a specific instance.
- list instances
- individual instance operations.
- delete mapping
- database
- list alert events.
- create mapping
- delete a service instance permanently.
- update alert rules for an instance.
- provision a new sap hana cloud instance.
- administration
- retrieve database performance metrics.
- get metering
- retrieve consumption metering data.
- alert monitoring.
- get instance details.
- create instance
- list alerts
- get instance
- delete an instance mapping.
- list alert rules
- delete instance
slug: cloud-administration
source_filename: cloud-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP HANA Cloud Administration\n  description: Unified workflow for SAP HANA Cloud database administration including instance lifecycle management, monitoring\n    alerts, performance metrics, and metering. Used by database administrators and cloud platform engineers.\n  tags:\n  - SAP HANA\n  - Cloud\n  - Administration\n  - Monitoring\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_HANA_OAUTH_TOKEN: SAP_HANA_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: hana-cloud-rest\n    baseUri: https://api.cf.eu10.hana.ondemand.com\n    description: SAP HANA Cloud REST API for managing instances, alerts, metrics, and metering.\n    authentication:\n      type: bearer\n      token: '{{SAP_HANA_OAUTH_TOKEN}}'\n    resources:\n    - name: instances\n      path: /v1/service_instances\n      description: Service instance lifecycle management.\n      operations:\n      - name: list-service-instances\n\
  \        method: GET\n        description: List all SAP HANA Cloud service instances.\n        inputParameters:\n        - name: fieldQuery\n          in: query\n          type: string\n          required: false\n          description: Filter query for instance fields.\n        - name: labelQuery\n          in: query\n          type: string\n          required: false\n          description: Filter query for instance labels.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-service-instance\n        method: POST\n        description: Provision a new SAP HANA Cloud service instance.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            service_plan_id: '{{tools.service_plan_id}}'\n            parameters: '{{tools.parameters}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: instance-details\n      path: /v1/service_instances/{instanceId}\n      description: Individual instance operations.\n      operations:\n      - name: get-service-instance\n        method: GET\n        description: Retrieve details of a specific service instance.\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n          description: The service instance ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-service-instance\n        method: PATCH\n        description: Update configuration of a service instance.\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n          description: The service instance ID.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            parameters:\
  \ '{{tools.parameters}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-service-instance\n        method: DELETE\n        description: Delete a service instance and all associated data.\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n          description: The service instance ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventory\n      path: /inventory/v2/serviceInstances\n      description: Inventory listing of all instances.\n      operations:\n      - name: list-inventory-instances\n        method: GET\n        description: List all instances in the inventory.\n        inputParameters:\n        - name: provisioningState\n          in: query\n          type: string\n          required: false\n          description:\
  \ Filter by provisioning state.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts\n      path: /alerts/v1/events\n      description: Alert event operations.\n      operations:\n      - name: list-alert-events\n        method: GET\n        description: List triggered alert events.\n        inputParameters:\n        - name: instanceId\n          in: query\n          type: string\n          required: true\n          description: The instance ID to get alerts for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alert-rules\n      path: /alerts/v1/rules\n      description: Alert rule management.\n      operations:\n      - name: list-alert-rules\n        method: GET\n        description: List alert rules.\n        inputParameters:\n        - name: instanceId\n          in: query\n          type: string\n\
  \          required: true\n          description: The instance ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-alert-rules\n        method: PUT\n        description: Update alert rules for an instance.\n        inputParameters:\n        - name: instanceId\n          in: query\n          type: string\n          required: true\n          description: The instance ID.\n        body:\n          type: json\n          data:\n            rules: '{{tools.rules}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics/v1/values\n      description: Database metrics operations.\n      operations:\n      - name: get-metric-values\n        method: GET\n        description: Retrieve database performance metrics.\n        inputParameters:\n        - name: instanceId\n          in: query\n\
  \          type: string\n          required: true\n          description: The instance ID.\n        - name: metricName\n          in: query\n          type: string\n          required: true\n          description: Name of the metric to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metering\n      path: /metering/v1/values\n      description: Consumption metering data.\n      operations:\n      - name: get-metering-values\n        method: GET\n        description: Retrieve consumption metering data.\n        inputParameters:\n        - name: instanceId\n          in: query\n          type: string\n          required: true\n          description: The instance ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instance-mappings\n      path: /v1/instance_mappings\n      description: Instance mapping\
  \ operations.\n      operations:\n      - name: list-instance-mappings\n        method: GET\n        description: List instance mappings.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-instance-mapping\n        method: POST\n        description: Create a new instance mapping.\n        body:\n          type: json\n          data:\n            sourceInstanceId: '{{tools.sourceInstanceId}}'\n            targetInstanceId: '{{tools.targetInstanceId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-instance-mapping\n        method: DELETE\n        description: Delete an instance mapping.\n        inputParameters:\n        - name: mappingId\n          in: path\n          type: string\n          required: true\n          description: The mapping ID.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hana-cloud-admin-api\n    description: Unified REST API for SAP HANA Cloud administration.\n    resources:\n    - path: /v1/instances\n      name: instances\n      description: Instance lifecycle management.\n      operations:\n      - method: GET\n        name: list-instances\n        description: List all SAP HANA Cloud instances.\n        call: hana-cloud-rest.list-service-instances\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-instance\n        description: Provision a new instance.\n        call: hana-cloud-rest.create-service-instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{instanceId}\n      name: instance-details\n      description: Individual instance operations.\n      operations:\n      - method: GET\n        name: get-instance\n\
  \        description: Get instance details.\n        call: hana-cloud-rest.get-service-instance\n        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-instance\n        description: Update an instance.\n        call: hana-cloud-rest.update-service-instance\n        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-instance\n        description: Delete an instance.\n        call: hana-cloud-rest.delete-service-instance\n        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts\n      name: alerts\n      description: Alert monitoring.\n      operations:\n      - method: GET\n        name: list-alerts\n        description: List alert events.\n        call: hana-cloud-rest.list-alert-events\n\
  \        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Performance metrics.\n      operations:\n      - method: GET\n        name: get-metrics\n        description: Get database metrics.\n        call: hana-cloud-rest.get-metric-values\n        with:\n          instanceId: rest.instanceId\n          metricName: rest.metricName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hana-cloud-admin-mcp\n    transport: http\n    description: MCP server for AI-assisted SAP HANA Cloud database administration.\n    tools:\n    - name: list-instances\n      description: List all SAP HANA Cloud service instances.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hana-cloud-rest.list-service-instances\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: create-instance\n      description: Provision a new SAP HANA Cloud instance.\n      hints:\n        readOnly: false\n      call: hana-cloud-rest.create-service-instance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-instance\n      description: Get details of a specific instance.\n      hints:\n        readOnly: true\n      call: hana-cloud-rest.get-service-instance\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-instance\n      description: Update instance configuration.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: hana-cloud-rest.update-service-instance\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-instance\n      description: Delete a service instance permanently.\n      hints:\n        destructive: true\n        idempotent:\
  \ true\n      call: hana-cloud-rest.delete-service-instance\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-inventory\n      description: List all instances in the inventory.\n      hints:\n        readOnly: true\n      call: hana-cloud-rest.list-inventory-instances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-alerts\n      description: List triggered alert events for an instance.\n      hints:\n        readOnly: true\n      call: hana-cloud-rest.list-alert-events\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-alert-rules\n      description: List alert rules for an instance.\n      hints:\n        readOnly: true\n      call: hana-cloud-rest.list-alert-rules\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: update-alert-rules\n      description: Update alert rules for an instance.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: hana-cloud-rest.update-alert-rules\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-metrics\n      description: Retrieve database performance metrics.\n      hints:\n        readOnly: true\n      call: hana-cloud-rest.get-metric-values\n      with:\n        instanceId: tools.instanceId\n        metricName: tools.metricName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-metering\n      description: Retrieve consumption metering data.\n      hints:\n        readOnly: true\n      call: hana-cloud-rest.get-metering-values\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-mappings\n      description: List instance\
  \ mappings.\n      hints:\n        readOnly: true\n      call: hana-cloud-rest.list-instance-mappings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-mapping\n      description: Create a new instance mapping.\n      hints:\n        readOnly: false\n      call: hana-cloud-rest.create-instance-mapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-mapping\n      description: Delete an instance mapping.\n      hints:\n        destructive: true\n        idempotent: true\n      call: hana-cloud-rest.delete-instance-mapping\n      with:\n        mappingId: tools.mappingId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-hana/refs/heads/main/capabilities/cloud-administration.yaml
tags:
- SAP HANA
- Cloud
- Administration
- Monitoring
tools:
- description: List all SAP HANA Cloud service instances.
  hints:
    openWorld: true
    readOnly: true
  name: list-instances
- description: Provision a new SAP HANA Cloud instance.
  hints:
    readOnly: false
  name: create-instance
- description: Get details of a specific instance.
  hints:
    readOnly: true
  name: get-instance
- description: Update instance configuration.
  hints:
    idempotent: true
    readOnly: false
  name: update-instance
- description: Delete a service instance permanently.
  hints:
    destructive: true
    idempotent: true
  name: delete-instance
- description: List all instances in the inventory.
  hints:
    readOnly: true
  name: list-inventory
- description: List triggered alert events for an instance.
  hints:
    readOnly: true
  name: list-alerts
- description: List alert rules for an instance.
  hints:
    readOnly: true
  name: list-alert-rules
- description: Update alert rules for an instance.
  hints:
    idempotent: true
    readOnly: false
  name: update-alert-rules
- description: Retrieve database performance metrics.
  hints:
    readOnly: true
  name: get-metrics
- description: Retrieve consumption metering data.
  hints:
    readOnly: true
  name: get-metering
- description: List instance mappings.
  hints:
    readOnly: true
  name: list-mappings
- description: Create a new instance mapping.
  hints:
    readOnly: false
  name: create-mapping
- description: Delete an instance mapping.
  hints:
    destructive: true
    idempotent: true
  name: delete-mapping
---
