---
categories:
- data-engineering
consumed_apis:
- appflow
description: Workflow capability for data engineers and integration architects who need to orchestrate, monitor, and manage SaaS-to-AWS data flows using Amazon AppFlow. Combines flow lifecycle management, connector profile administration, and connector entity discovery into a unified integration operations interface.
layout: capability
name: Amazon AppFlow Data Integration
operations:
- description: List all data flows in your account
  method: POST
  name: list-flows
  path: /v1/flows
- description: Get details about a specific flow
  method: GET
  name: describe-flow
  path: /v1/flows/{flowName}
- description: Activate a flow to begin data transfer
  method: POST
  name: start-flow
  path: /v1/flows/{flowName}/start
- description: Deactivate a running flow
  method: POST
  name: stop-flow
  path: /v1/flows/{flowName}/stop
- description: Get execution history and results for a flow
  method: GET
  name: describe-flow-execution-records
  path: /v1/flows/{flowName}/executions
- description: List all connector profiles
  method: GET
  name: describe-connector-profiles
  path: /v1/connector-profiles
- description: List all available AppFlow connectors
  method: GET
  name: describe-connectors
  path: /v1/connectors
- description: List entities available from a connector
  method: GET
  name: list-connector-entities
  path: /v1/connectors/{connectorType}/entities
- description: Get all fields available for a connector entity
  method: GET
  name: describe-connector-entity
  path: /v1/connectors/{connectorType}/entities/{entityName}
personas: []
provider_name: Amazon AppFlow
provider_slug: amazon-appflow
search_terms:
- saas
- workflow for data engineers and integration architects to orchestrate, monitor, and manage saas-to-aws data flows
- get complete details about an appflow data flow including source, destination, trigger, and task configuration.
- configuring and managing connections to saas applications
- update flow
- start a flow
- view the execution history and results of appflow flow runs, including records processed and any errors.
- Data Engineer
- get field definitions for a connector entity
- discover available connectors
- create a new appflow data flow to transfer data between a saas source and an aws destination.
- list connector profiles that store credentials for connecting to saas applications.
- deactivate a running flow
- data integration
- stop flow
- create a connector profile to store authentication credentials for a saas application.
- list connector entities
- cancel flow executions
- activate or trigger an appflow data flow to begin transferring data.
- create flow
- describe connectors
- permanently delete an appflow data flow.
- integration
- list all connector profiles
- Integration Architect
- manage saas connector credentials
- register connector
- unregister connector
- update the credentials or configuration of an existing connector profile.
- activate a flow to begin data transfer
- aws
- update connector profile
- list entities available from a connector
- list all available appflow connectors including salesforce, servicenow, sap, slack, and custom connectors.
- data engineering
- register a new custom lambda-backed connector with your aws account.
- create and list data flows
- list the entities (objects) available from a specific connector, such as salesforce account, contact, or opportunity.
- get the field definitions and capabilities for a specific connector entity to understand what data can be transferred.
- update an existing appflow flow's configuration, schedule, or field mappings.
- delete flow
- describe connector profiles
- amazon appflow
- describe flow
- list all available appflow connectors
- get details about a specific flow
- describe flow execution records
- delete a connector profile and remove its stored credentials.
- describe connector entity
- data flow
- connectors
- list all data flows in your account
- data transfer
- clear cached connector metadata to force appflow to fetch the latest entity and field information from the source system.
- get execution history and results for a flow
- reset connector metadata cache
- etl
- list all amazon appflow data integration flows in your account.
- delete connector profile
- list flows
- stop an active appflow data flow.
- create connector profile
- cancel in-progress runs of an appflow data flow.
- view flow execution history
- get all fields available for a connector entity
- designs integration patterns, manages connector credentials, and establishes data governance for appflow
- browse entities available from a connector
- start flow
- moving data between saas applications and aws services
- builds and maintains data pipelines between saas applications and aws analytics/ml services
- manage a specific data flow
- remove a custom connector registration from your aws account.
- stop a flow
slug: data-integration
source_filename: data-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon AppFlow Data Integration\n  description: Workflow capability for data engineers and integration architects who need to orchestrate, monitor, and manage SaaS-to-AWS data flows using Amazon AppFlow. Combines flow lifecycle management, connector profile administration, and connector entity discovery into a unified integration operations interface.\n  tags:\n    - Amazon AppFlow\n    - Data Integration\n    - ETL\n    - SaaS\n    - AWS\n    - Data Engineering\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: appflow\n      location: ./shared/appflow-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: appflow-integration-api\n      description: Unified REST API for Amazon AppFlow data integration\
  \ workflows.\n      resources:\n        - path: /v1/flows\n          name: flows\n          description: Create and list data flows\n          operations:\n            - method: POST\n              name: list-flows\n              description: List all data flows in your account\n              call: \"appflow.list-flows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flows/{flowName}\n          name: flow\n          description: Manage a specific data flow\n          operations:\n            - method: GET\n              name: describe-flow\n              description: Get details about a specific flow\n              call: \"appflow.describe-flow\"\n              with:\n                flowName: \"rest.flowName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flows/{flowName}/start\n          name: flow-start\n          description: Start\
  \ a flow\n          operations:\n            - method: POST\n              name: start-flow\n              description: Activate a flow to begin data transfer\n              call: \"appflow.start-flow\"\n              with:\n                flowName: \"rest.flowName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flows/{flowName}/stop\n          name: flow-stop\n          description: Stop a flow\n          operations:\n            - method: POST\n              name: stop-flow\n              description: Deactivate a running flow\n              call: \"appflow.stop-flow\"\n              with:\n                flowName: \"rest.flowName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flows/{flowName}/executions\n          name: flow-executions\n          description: View flow execution history\n          operations:\n            - method:\
  \ GET\n              name: describe-flow-execution-records\n              description: Get execution history and results for a flow\n              call: \"appflow.describe-flow-execution-records\"\n              with:\n                flowName: \"rest.flowName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/connector-profiles\n          name: connector-profiles\n          description: Manage SaaS connector credentials\n          operations:\n            - method: GET\n              name: describe-connector-profiles\n              description: List all connector profiles\n              call: \"appflow.describe-connector-profiles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/connectors\n          name: connectors\n          description: Discover available connectors\n          operations:\n            - method: GET\n              name:\
  \ describe-connectors\n              description: List all available AppFlow connectors\n              call: \"appflow.describe-connectors\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/connectors/{connectorType}/entities\n          name: connector-entities\n          description: Browse entities available from a connector\n          operations:\n            - method: GET\n              name: list-connector-entities\n              description: List entities available from a connector\n              call: \"appflow.list-connector-entities\"\n              with:\n                connectorType: \"rest.connectorType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/connectors/{connectorType}/entities/{entityName}\n          name: connector-entity-fields\n          description: Get field definitions for a connector entity\n          operations:\n\
  \            - method: GET\n              name: describe-connector-entity\n              description: Get all fields available for a connector entity\n              call: \"appflow.describe-connector-entity\"\n              with:\n                connectorEntityName: \"rest.entityName\"\n                connectorType: \"rest.connectorType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: appflow-integration-mcp\n      transport: http\n      description: MCP server for AI-assisted Amazon AppFlow data integration workflows.\n      tools:\n        - name: list-flows\n          description: List all Amazon AppFlow data integration flows in your account.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"appflow.list-flows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-flow\n\
  \          description: Get complete details about an AppFlow data flow including source, destination, trigger, and task configuration.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"appflow.describe-flow\"\n          with:\n            flowName: \"tools.flowName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-flow\n          description: Create a new AppFlow data flow to transfer data between a SaaS source and an AWS destination.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"appflow.create-flow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-flow\n          description: Update an existing AppFlow flow's configuration, schedule, or field mappings.\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"appflow.update-flow\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-flow\n          description: Permanently delete an AppFlow data flow.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"appflow.delete-flow\"\n          with:\n            flowName: \"tools.flowName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-flow\n          description: Activate or trigger an AppFlow data flow to begin transferring data.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"appflow.start-flow\"\n          with:\n            flowName: \"tools.flowName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: stop-flow\n          description: Stop an active AppFlow data flow.\n          hints:\n            readOnly: false\n\
  \            idempotent: true\n          call: \"appflow.stop-flow\"\n          with:\n            flowName: \"tools.flowName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-flow-executions\n          description: Cancel in-progress runs of an AppFlow data flow.\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"appflow.cancel-flow-executions\"\n          with:\n            flowName: \"tools.flowName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-flow-execution-records\n          description: View the execution history and results of AppFlow flow runs, including records processed and any errors.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"appflow.describe-flow-execution-records\"\n          with:\n            flowName: \"tools.flowName\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: describe-connector-profiles\n          description: List connector profiles that store credentials for connecting to SaaS applications.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"appflow.describe-connector-profiles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-connector-profile\n          description: Create a connector profile to store authentication credentials for a SaaS application.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"appflow.create-connector-profile\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-connector-profile\n          description: Update the credentials or configuration of an existing connector profile.\n          hints:\n            readOnly: false\n \
  \           idempotent: true\n          call: \"appflow.update-connector-profile\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-connector-profile\n          description: Delete a connector profile and remove its stored credentials.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"appflow.delete-connector-profile\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-connectors\n          description: List all available AppFlow connectors including Salesforce, ServiceNow, SAP, Slack, and custom connectors.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"appflow.describe-connectors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-connector-entities\n          description:\
  \ List the entities (objects) available from a specific connector, such as Salesforce Account, Contact, or Opportunity.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"appflow.list-connector-entities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-connector-entity\n          description: Get the field definitions and capabilities for a specific connector entity to understand what data can be transferred.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"appflow.describe-connector-entity\"\n          with:\n            connectorEntityName: \"tools.connectorEntityName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: register-connector\n          description: Register a new custom Lambda-backed connector with your AWS account.\n          hints:\n            readOnly: false\n\
  \            openWorld: false\n          call: \"appflow.register-connector\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: unregister-connector\n          description: Remove a custom connector registration from your AWS account.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"appflow.unregister-connector\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: reset-connector-metadata-cache\n          description: Clear cached connector metadata to force AppFlow to fetch the latest entity and field information from the source system.\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"appflow.reset-connector-metadata-cache\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-appflow/refs/heads/main/capabilities/data-integration.yaml
tags:
- Amazon AppFlow
- Data Integration
- ETL
- SaaS
- AWS
- Data Engineering
tools:
- description: List all Amazon AppFlow data integration flows in your account.
  hints:
    openWorld: true
    readOnly: true
  name: list-flows
- description: Get complete details about an AppFlow data flow including source, destination, trigger, and task configuration.
  hints:
    openWorld: true
    readOnly: true
  name: describe-flow
- description: Create a new AppFlow data flow to transfer data between a SaaS source and an AWS destination.
  hints:
    openWorld: false
    readOnly: false
  name: create-flow
- description: Update an existing AppFlow flow's configuration, schedule, or field mappings.
  hints:
    idempotent: true
    readOnly: false
  name: update-flow
- description: Permanently delete an AppFlow data flow.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-flow
- description: Activate or trigger an AppFlow data flow to begin transferring data.
  hints:
    openWorld: false
    readOnly: false
  name: start-flow
- description: Stop an active AppFlow data flow.
  hints:
    idempotent: true
    readOnly: false
  name: stop-flow
- description: Cancel in-progress runs of an AppFlow data flow.
  hints:
    destructive: true
    readOnly: false
  name: cancel-flow-executions
- description: View the execution history and results of AppFlow flow runs, including records processed and any errors.
  hints:
    openWorld: true
    readOnly: true
  name: describe-flow-execution-records
- description: List connector profiles that store credentials for connecting to SaaS applications.
  hints:
    openWorld: true
    readOnly: true
  name: describe-connector-profiles
- description: Create a connector profile to store authentication credentials for a SaaS application.
  hints:
    openWorld: false
    readOnly: false
  name: create-connector-profile
- description: Update the credentials or configuration of an existing connector profile.
  hints:
    idempotent: true
    readOnly: false
  name: update-connector-profile
- description: Delete a connector profile and remove its stored credentials.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-connector-profile
- description: List all available AppFlow connectors including Salesforce, ServiceNow, SAP, Slack, and custom connectors.
  hints:
    openWorld: true
    readOnly: true
  name: describe-connectors
- description: List the entities (objects) available from a specific connector, such as Salesforce Account, Contact, or Opportunity.
  hints:
    openWorld: true
    readOnly: true
  name: list-connector-entities
- description: Get the field definitions and capabilities for a specific connector entity to understand what data can be transferred.
  hints:
    openWorld: true
    readOnly: true
  name: describe-connector-entity
- description: Register a new custom Lambda-backed connector with your AWS account.
  hints:
    openWorld: false
    readOnly: false
  name: register-connector
- description: Remove a custom connector registration from your AWS account.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: unregister-connector
- description: Clear cached connector metadata to force AppFlow to fetch the latest entity and field information from the source system.
  hints:
    idempotent: true
    readOnly: false
  name: reset-connector-metadata-cache
---
