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
- get complete details about an appflow data flow including source, destination, trigger, and task configuration.
- delete a connector profile and remove its stored credentials.
- moving data between saas applications and aws services
- manage a specific data flow
- describe connector entity
- list all available appflow connectors including salesforce, servicenow, sap, slack, and custom connectors.
- get details about a specific flow
- reset connector metadata cache
- manage saas connector credentials
- get execution history and results for a flow
- list connector entities
- list all connector profiles
- amazon appflow
- list the entities (objects) available from a specific connector, such as salesforce account, contact, or opportunity.
- designs integration patterns, manages connector credentials, and establishes data governance for appflow
- view the execution history and results of appflow flow runs, including records processed and any errors.
- describe connector profiles
- etl
- create flow
- update flow
- start a flow
- cancel flow executions
- update the credentials or configuration of an existing connector profile.
- register a new custom lambda-backed connector with your aws account.
- workflow for data engineers and integration architects to orchestrate, monitor, and manage saas-to-aws data flows
- create and list data flows
- browse entities available from a connector
- create connector profile
- aws
- Data Engineer
- get field definitions for a connector entity
- configuring and managing connections to saas applications
- clear cached connector metadata to force appflow to fetch the latest entity and field information from the source system.
- permanently delete an appflow data flow.
- update an existing appflow flow's configuration, schedule, or field mappings.
- data integration
- activate a flow to begin data transfer
- create a new appflow data flow to transfer data between a saas source and an aws destination.
- stop flow
- list entities available from a connector
- list flows
- delete connector profile
- delete flow
- discover available connectors
- integration
- list all data flows in your account
- get all fields available for a connector entity
- start flow
- list all amazon appflow data integration flows in your account.
- get the field definitions and capabilities for a specific connector entity to understand what data can be transferred.
- builds and maintains data pipelines between saas applications and aws analytics/ml services
- Integration Architect
- list all available appflow connectors
- cancel in-progress runs of an appflow data flow.
- view flow execution history
- saas
- update connector profile
- create a connector profile to store authentication credentials for a saas application.
- describe flow
- data flow
- unregister connector
- remove a custom connector registration from your aws account.
- activate or trigger an appflow data flow to begin transferring data.
- stop an active appflow data flow.
- data transfer
- describe flow execution records
- stop a flow
- register connector
- connectors
- data engineering
- describe connectors
- deactivate a running flow
- list connector profiles that store credentials for connecting to saas applications.
slug: data-integration
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
