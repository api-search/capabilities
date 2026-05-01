---
categories:
- monitoring
consumed_apis:
- hana-cloud-rest
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
- individual instance operations.
- delete instance
- list instances
- list all sap hana cloud instances.
- create a new instance mapping.
- create instance
- list alert rules
- list mappings
- retrieve consumption metering data.
- get details of a specific instance.
- create mapping
- alert monitoring.
- list triggered alert events for an instance.
- analytics
- in-memory
- provision a new sap hana cloud instance.
- sap hana
- delete an instance mapping.
- provision a new instance.
- update instance
- administration
- list alert events.
- update alert rules for an instance.
- database
- retrieve database performance metrics.
- list all sap hana cloud service instances.
- enterprise
- list all instances in the inventory.
- delete mapping
- update an instance.
- list instance mappings.
- get database metrics.
- monitoring
- performance metrics.
- get metrics
- update alert rules
- delete an instance.
- cloud
- instance lifecycle management.
- delete a service instance permanently.
- get instance
- list alerts
- update instance configuration.
- list inventory
- get instance details.
- list alert rules for an instance.
- get metering
slug: cloud-administration
source_filename: cloud-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP HANA Cloud Administration\"\n  description: \"Unified workflow for SAP HANA Cloud database administration including instance lifecycle management, monitoring alerts, performance metrics, and metering. Used by database administrators and cloud platform engineers.\"\n  tags:\n    - SAP HANA\n    - Cloud\n    - Administration\n    - Monitoring\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_HANA_OAUTH_TOKEN: SAP_HANA_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: hana-cloud-rest\n      location: ./shared/hana-cloud-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: hana-cloud-admin-api\n      description: \"Unified REST API for SAP HANA Cloud administration.\"\n      resources:\n        - path: /v1/instances\n          name: instances\n          description: \"Instance lifecycle management.\"\n          operations:\n            - method:\
  \ GET\n              name: list-instances\n              description: \"List all SAP HANA Cloud instances.\"\n              call: \"hana-cloud-rest.list-service-instances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-instance\n              description: \"Provision a new instance.\"\n              call: \"hana-cloud-rest.create-service-instance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/instances/{instanceId}\n          name: instance-details\n          description: \"Individual instance operations.\"\n          operations:\n            - method: GET\n              name: get-instance\n              description: \"Get instance details.\"\n              call: \"hana-cloud-rest.get-service-instance\"\n              with:\n                instanceId: \"rest.instanceId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-instance\n              description: \"Update an instance.\"\n              call: \"hana-cloud-rest.update-service-instance\"\n              with:\n                instanceId: \"rest.instanceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-instance\n              description: \"Delete an instance.\"\n              call: \"hana-cloud-rest.delete-service-instance\"\n              with:\n                instanceId: \"rest.instanceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/alerts\n          name: alerts\n          description: \"Alert monitoring.\"\n          operations:\n            - method: GET\n              name: list-alerts\n              description: \"List alert events.\"\
  \n              call: \"hana-cloud-rest.list-alert-events\"\n              with:\n                instanceId: \"rest.instanceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics\n          name: metrics\n          description: \"Performance metrics.\"\n          operations:\n            - method: GET\n              name: get-metrics\n              description: \"Get database metrics.\"\n              call: \"hana-cloud-rest.get-metric-values\"\n              with:\n                instanceId: \"rest.instanceId\"\n                metricName: \"rest.metricName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: hana-cloud-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP HANA Cloud database administration.\"\n      tools:\n        - name: list-instances\n          description:\
  \ \"List all SAP HANA Cloud service instances.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hana-cloud-rest.list-service-instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-instance\n          description: \"Provision a new SAP HANA Cloud instance.\"\n          hints:\n            readOnly: false\n          call: \"hana-cloud-rest.create-service-instance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-instance\n          description: \"Get details of a specific instance.\"\n          hints:\n            readOnly: true\n          call: \"hana-cloud-rest.get-service-instance\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-instance\n          description: \"Update instance configuration.\"\
  \n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"hana-cloud-rest.update-service-instance\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-instance\n          description: \"Delete a service instance permanently.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"hana-cloud-rest.delete-service-instance\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-inventory\n          description: \"List all instances in the inventory.\"\n          hints:\n            readOnly: true\n          call: \"hana-cloud-rest.list-inventory-instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-alerts\n\
  \          description: \"List triggered alert events for an instance.\"\n          hints:\n            readOnly: true\n          call: \"hana-cloud-rest.list-alert-events\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-alert-rules\n          description: \"List alert rules for an instance.\"\n          hints:\n            readOnly: true\n          call: \"hana-cloud-rest.list-alert-rules\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-alert-rules\n          description: \"Update alert rules for an instance.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"hana-cloud-rest.update-alert-rules\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n \
  \           - type: object\n              mapping: \"$.\"\n        - name: get-metrics\n          description: \"Retrieve database performance metrics.\"\n          hints:\n            readOnly: true\n          call: \"hana-cloud-rest.get-metric-values\"\n          with:\n            instanceId: \"tools.instanceId\"\n            metricName: \"tools.metricName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-metering\n          description: \"Retrieve consumption metering data.\"\n          hints:\n            readOnly: true\n          call: \"hana-cloud-rest.get-metering-values\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-mappings\n          description: \"List instance mappings.\"\n          hints:\n            readOnly: true\n          call: \"hana-cloud-rest.list-instance-mappings\"\n         \
  \ outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-mapping\n          description: \"Create a new instance mapping.\"\n          hints:\n            readOnly: false\n          call: \"hana-cloud-rest.create-instance-mapping\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-mapping\n          description: \"Delete an instance mapping.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"hana-cloud-rest.delete-instance-mapping\"\n          with:\n            mappingId: \"tools.mappingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
