---
categories: []
consumed_apis: []
description: Workflow capability for Salesforce process automation combining Flow invocation, approval process management, and automation record querying. Serves admins, developers, and integration engineers managing business process automation across Salesforce organizations.
layout: capability
name: Salesforce Process Automation
operations:
- description: Query active and draft Flow definitions.
  method: GET
  name: list-flows
  path: /v1/flows
- description: Get a Flow version record by ID.
  method: GET
  name: get-flow
  path: /v1/flows/{id}
- description: Invoke an autolaunched Flow with input variables.
  method: POST
  name: invoke-flow
  path: /v1/flows/{flowApiName}/invoke
- description: List all approval process configurations.
  method: GET
  name: list-approval-processes
  path: /v1/approvals
- description: Submit, approve, reject, or recall approval requests.
  method: POST
  name: submit-approval
  path: /v1/approvals
- description: Query ProcessInstance, FlowInterview, or WorkflowRule records.
  method: GET
  name: query-automation-records
  path: /v1/automation-records
personas: []
provider_name: Salesforce Automation System
provider_slug: salesforce-automation-system
search_terms:
- list flows
- get the metadata for a specific salesforce flow version by record id.
- automation
- execute a soql query to retrieve processinstance, flowinterview, or workflowrule records from salesforce.
- submit, approve, reject, or recall approval requests.
- submit a record for approval, approve or reject an approval request, or recall an in-progress approval.
- list approval processes
- invoke a salesforce autolaunched flow with input variables. returns output variable values from the flow execution.
- submit approval
- invoke an autolaunched flow with input variables.
- query automation-related salesforce records.
- crm
- list all approval process definitions configured in the salesforce org.
- approval process
- query automation records
- query salesforce flow definitions. returns active and draft flows with their api names, labels, and statuses.
- invoke flow
- workflow
- get a flow version record by id.
- salesforce flow definitions and invocation.
- query processinstance, flowinterview, or workflowrule records.
- query active and draft flow definitions.
- list all approval process configurations.
- get flow version
- approval process management.
- flow
- process builder
- get flow
- salesforce
slug: process-automation
source_filename: process-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce Process Automation\n  description: Workflow capability for Salesforce process automation combining Flow invocation, approval process management,\n    and automation record querying. Serves admins, developers, and integration engineers managing business process automation\n    across Salesforce organizations.\n  tags:\n  - Approval Process\n  - Automation\n  - CRM\n  - Flow\n  - Process Builder\n  - Salesforce\n  - Workflow\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_OAUTH2_TOKEN: SALESFORCE_OAUTH2_TOKEN\n    SALESFORCE_INSTANCE_URL: SALESFORCE_INSTANCE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: sf-flow-automation\n    baseUri: '{{env.SALESFORCE_INSTANCE_URL}}/services/data/v59.0'\n    description: Salesforce Flow and Automation APIs.\n    authentication:\n      type: bearer\n      token: '{{env.SALESFORCE_OAUTH2_TOKEN}}'\n    resources:\n    - name:\
  \ flow-definitions\n      path: /tooling/query\n      description: Query Salesforce Flow definitions via Tooling API.\n      operations:\n      - name: query-flow-definitions\n        method: GET\n        description: Query Flow definitions using SOQL.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: SOQL query for FlowDefinition objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: flows\n          type: object\n          value: $.\n    - name: flow-version\n      path: /tooling/sobjects/Flow/{id}\n      description: Retrieve a specific Flow version.\n      operations:\n      - name: get-flow-version\n        method: GET\n        description: Get a Flow version record by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Salesforce Flow record ID.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: flow\n          type: object\n          value: $.\n    - name: flow-invocation\n      path: /actions/custom/flow/{flowApiName}\n      description: Invoke an autolaunched flow via REST action.\n      operations:\n      - name: invoke-flow\n        method: POST\n        description: Invoke a Salesforce autolaunched Flow with input variables.\n        inputParameters:\n        - name: flowApiName\n          in: path\n          type: string\n          required: true\n          description: API name of the flow to invoke.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: approval-processes\n      path: /process/approvals\n      description: List approval processes and submit approval actions.\n      operations:\n      - name: list-approval-processes\n        method:\
  \ GET\n        description: Retrieve all approval process configurations.\n        outputRawFormat: json\n        outputParameters:\n        - name: approvals\n          type: object\n          value: $.\n      - name: submit-approval-request\n        method: POST\n        description: Submit, approve, or reject an approval process request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n        body:\n          type: json\n          data:\n            requests: '{{tools.requests}}'\n    - name: soql-query\n      path: /query\n      description: Execute SOQL queries against Salesforce objects.\n      operations:\n      - name: query-automation-records\n        method: GET\n        description: Query ProcessInstance, FlowInterview, or WorkflowRule records.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: SOQL query string.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: records\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: salesforce-process-automation-api\n    description: Unified REST API for Salesforce process automation workflows.\n    resources:\n    - path: /v1/flows\n      name: flows\n      description: Salesforce Flow definitions and invocation.\n      operations:\n      - method: GET\n        name: list-flows\n        description: Query active and draft Flow definitions.\n        call: sf-flow-automation.query-flow-definitions\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flows/{id}\n      name: flow-by-id\n      operations:\n      - method: GET\n        name: get-flow\n        description: Get a Flow version record by ID.\n        call: sf-flow-automation.get-flow-version\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/flows/{flowApiName}/invoke\n      name: flow-invocation\n      operations:\n      - method: POST\n        name: invoke-flow\n        description: Invoke an autolaunched Flow with input variables.\n        call: sf-flow-automation.invoke-flow\n        with:\n          flowApiName: rest.flowApiName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/approvals\n      name: approvals\n      description: Approval process management.\n      operations:\n      - method: GET\n        name: list-approval-processes\n        description: List all approval process configurations.\n        call: sf-flow-automation.list-approval-processes\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: submit-approval\n        description: Submit, approve, reject, or recall approval requests.\n        call: sf-flow-automation.submit-approval-request\n \
  \       outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/automation-records\n      name: automation-records\n      description: Query automation-related Salesforce records.\n      operations:\n      - method: GET\n        name: query-automation-records\n        description: Query ProcessInstance, FlowInterview, or WorkflowRule records.\n        call: sf-flow-automation.query-automation-records\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: salesforce-process-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted Salesforce process automation.\n    tools:\n    - name: list-flows\n      description: Query Salesforce Flow definitions. Returns active and draft flows with their API names, labels, and statuses.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sf-flow-automation.query-flow-definitions\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-flow-version\n      description: Get the metadata for a specific Salesforce Flow version by record ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sf-flow-automation.get-flow-version\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: invoke-flow\n      description: Invoke a Salesforce autolaunched Flow with input variables. Returns output variable values from the flow\n        execution.\n      hints:\n        readOnly: false\n        destructive: false\n      call: sf-flow-automation.invoke-flow\n      with:\n        flowApiName: tools.flowApiName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-approval-processes\n      description: List all approval process definitions configured in the Salesforce org.\n      hints:\n        readOnly: true\n        idempotent: true\n\
  \      call: sf-flow-automation.list-approval-processes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-approval\n      description: Submit a record for approval, approve or reject an approval request, or recall an in-progress approval.\n      hints:\n        readOnly: false\n        destructive: false\n      call: sf-flow-automation.submit-approval-request\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: query-automation-records\n      description: Execute a SOQL query to retrieve ProcessInstance, FlowInterview, or WorkflowRule records from Salesforce.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sf-flow-automation.query-automation-records\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-automation-system/refs/heads/main/capabilities/process-automation.yaml
tags:
- Approval Process
- Automation
- CRM
- Flow
- Process Builder
- Salesforce
- Workflow
tools:
- description: Query Salesforce Flow definitions. Returns active and draft flows with their API names, labels, and statuses.
  hints:
    idempotent: true
    readOnly: true
  name: list-flows
- description: Get the metadata for a specific Salesforce Flow version by record ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-flow-version
- description: Invoke a Salesforce autolaunched Flow with input variables. Returns output variable values from the flow execution.
  hints:
    destructive: false
    readOnly: false
  name: invoke-flow
- description: List all approval process definitions configured in the Salesforce org.
  hints:
    idempotent: true
    readOnly: true
  name: list-approval-processes
- description: Submit a record for approval, approve or reject an approval request, or recall an in-progress approval.
  hints:
    destructive: false
    readOnly: false
  name: submit-approval
- description: Execute a SOQL query to retrieve ProcessInstance, FlowInterview, or WorkflowRule records from Salesforce.
  hints:
    idempotent: true
    readOnly: true
  name: query-automation-records
---
