---
categories: []
consumed_apis:
- salesforce-service-rest
- salesforce-live-agent
description: Unified workflow capability for customer service case management in Salesforce Service Cloud. Combines REST API case CRUD with Live Agent chat initiation for complete customer service resolution workflows. Designed for service agents and customer service AI assistants.
layout: capability
name: Salesforce Service Cloud Case Management
operations:
- description: Create a new customer service case
  method: POST
  name: create-case
  path: /v1/cases
- description: Get case details
  method: GET
  name: get-case
  path: /v1/cases/{caseId}
- description: Update case status or details
  method: PATCH
  name: update-case
  path: /v1/cases/{caseId}
- description: Delete a case
  method: DELETE
  name: delete-case
  path: /v1/cases/{caseId}
- description: Create a contact
  method: POST
  name: create-contact
  path: /v1/contacts
- description: Get a contact
  method: GET
  name: get-contact
  path: /v1/contacts/{contactId}
- description: Get account details
  method: GET
  name: get-account
  path: /v1/accounts/{accountId}
- description: Query service data
  method: GET
  name: query
  path: /v1/query
- description: Initiate a live chat session
  method: POST
  name: initiate-live-chat
  path: /v1/chat/initiate
personas: []
provider_name: Salesforce Service Cloud
provider_slug: salesforce-service-cloud
search_terms:
- get account information for service context
- create a contact
- close a customer service case by updating status to closed
- update case status
- delete a case record
- get case details
- initiate a live chat session
- get account
- get account details
- get contact details for a customer
- create contact
- help desk
- query cases
- individual contact
- live chat initiation
- get case
- query
- delete a case
- query service data
- update case
- get a contact
- end chat session
- create a new customer service case
- case lifecycle management
- delete case
- case management
- individual case operations
- salesforce
- service cloud
- support
- send a message in an active live chat session
- end an active live chat session
- account for service context
- query cases using soql for filtering by status, priority, account, or agent
- update case status, priority, or description
- crm
- send chat message
- get contact
- create a new customer service case with subject, description, priority, and contact
- ticketing
- create case
- update case status or details
- initiate a live chat session with a service agent
- contact management for service
- soql query
- get customer service case details by id
- initiate live chat
- close case
- customer service
- create a new contact record for a customer
slug: case-management
source_filename: case-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Service Cloud Case Management\"\n  description: >-\n    Unified workflow capability for customer service case management in\n    Salesforce Service Cloud. Combines REST API case CRUD with Live Agent\n    chat initiation for complete customer service resolution workflows.\n    Designed for service agents and customer service AI assistants.\n  tags:\n    - Salesforce\n    - Service Cloud\n    - Case Management\n    - Customer Service\n    - Help Desk\n    - Support\n    - CRM\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n      SALESFORCE_LIVE_AGENT_TOKEN: SALESFORCE_LIVE_AGENT_TOKEN\n\ncapability:\n  consumes:\n    - import: salesforce-service-rest\n      location: ./shared/service-cloud-rest-api.yaml\n    - import: salesforce-live-agent\n      location: ./shared/live-agent-api.yaml\n\n  exposes:\n    - type: rest\n\
  \      port: 8080\n      namespace: case-management-api\n      description: \"Unified REST API for Salesforce Service Cloud case management.\"\n      resources:\n        - path: /v1/cases\n          name: cases\n          description: \"Case lifecycle management\"\n          operations:\n            - method: POST\n              name: create-case\n              description: \"Create a new customer service case\"\n              call: \"salesforce-service-rest.create-case\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cases/{caseId}\n          name: case\n          description: \"Individual case operations\"\n          operations:\n            - method: GET\n              name: get-case\n              description: \"Get case details\"\n              call: \"salesforce-service-rest.get-case\"\n              with:\n                caseId: \"rest.caseId\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n            - method: PATCH\n              name: update-case\n              description: \"Update case status or details\"\n              call: \"salesforce-service-rest.update-case\"\n              with:\n                caseId: \"rest.caseId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-case\n              description: \"Delete a case\"\n              call: \"salesforce-service-rest.delete-case\"\n              with:\n                caseId: \"rest.caseId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contacts\n          name: contacts\n          description: \"Contact management for service\"\n          operations:\n            - method: POST\n              name: create-contact\n              description: \"Create a contact\"\n              call: \"salesforce-service-rest.create-contact\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contacts/{contactId}\n          name: contact\n          description: \"Individual contact\"\n          operations:\n            - method: GET\n              name: get-contact\n              description: \"Get a contact\"\n              call: \"salesforce-service-rest.get-contact\"\n              with:\n                contactId: \"rest.contactId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts/{accountId}\n          name: account\n          description: \"Account for service context\"\n          operations:\n            - method: GET\n              name: get-account\n              description: \"Get account details\"\n              call: \"salesforce-service-rest.get-account\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n        - path: /v1/query\n          name: query\n          description: \"SOQL query\"\n          operations:\n            - method: GET\n              name: query\n              description: \"Query service data\"\n              call: \"salesforce-service-rest.query-service-data\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/chat/initiate\n          name: live-chat\n          description: \"Live chat initiation\"\n          operations:\n            - method: POST\n              name: initiate-live-chat\n              description: \"Initiate a live chat session\"\n              call: \"salesforce-live-agent.initiate-chat\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: case-management-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted Salesforce Service Cloud case management.\"\n      tools:\n        - name: get-case\n          description: \"Get customer service case details by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-service-rest.get-case\"\n          with:\n            caseId: \"tools.caseId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-case\n          description: \"Create a new customer service case with subject, description, priority, and contact\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-service-rest.create-case\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-case-status\n          description: \"Update case status, priority, or description\"\n          hints:\n         \
  \   readOnly: false\n            idempotent: true\n          call: \"salesforce-service-rest.update-case\"\n          with:\n            caseId: \"tools.caseId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: close-case\n          description: \"Close a customer service case by updating status to Closed\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesforce-service-rest.update-case\"\n          with:\n            caseId: \"tools.caseId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-case\n          description: \"Delete a case record\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"salesforce-service-rest.delete-case\"\n          with:\n            caseId: \"tools.caseId\"\n          outputParameters:\n            - type: object\n \
  \             mapping: \"$.\"\n        - name: get-contact\n          description: \"Get contact details for a customer\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-service-rest.get-contact\"\n          with:\n            contactId: \"tools.contactId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-contact\n          description: \"Create a new contact record for a customer\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-service-rest.create-contact\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account\n          description: \"Get account information for service context\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-service-rest.get-account\"\n          with:\n            accountId:\
  \ \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-cases\n          description: \"Query cases using SOQL for filtering by status, priority, account, or agent\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"salesforce-service-rest.query-service-data\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: initiate-live-chat\n          description: \"Initiate a live chat session with a service agent\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-live-agent.initiate-chat\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-chat-message\n          description: \"Send a message in an active live chat session\"\n      \
  \    hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-live-agent.send-chat-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: end-chat-session\n          description: \"End an active live chat session\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-live-agent.end-chat-session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-service-cloud/refs/heads/main/capabilities/case-management.yaml
tags:
- Salesforce
- Service Cloud
- Case Management
- Customer Service
- Help Desk
- Support
- CRM
tools:
- description: Get customer service case details by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-case
- description: Create a new customer service case with subject, description, priority, and contact
  hints:
    destructive: false
    readOnly: false
  name: create-case
- description: Update case status, priority, or description
  hints:
    idempotent: true
    readOnly: false
  name: update-case-status
- description: Close a customer service case by updating status to Closed
  hints:
    idempotent: true
    readOnly: false
  name: close-case
- description: Delete a case record
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-case
- description: Get contact details for a customer
  hints:
    idempotent: true
    readOnly: true
  name: get-contact
- description: Create a new contact record for a customer
  hints:
    destructive: false
    readOnly: false
  name: create-contact
- description: Get account information for service context
  hints:
    idempotent: true
    readOnly: true
  name: get-account
- description: Query cases using SOQL for filtering by status, priority, account, or agent
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-cases
- description: Initiate a live chat session with a service agent
  hints:
    destructive: false
    readOnly: false
  name: initiate-live-chat
- description: Send a message in an active live chat session
  hints:
    destructive: false
    readOnly: false
  name: send-chat-message
- description: End an active live chat session
  hints:
    destructive: false
    readOnly: false
  name: end-chat-session
---
