---
categories: []
consumed_apis: []
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
- get account
- close a customer service case by updating status to closed
- get contact
- create case
- query cases
- get case details
- case management
- query cases using soql for filtering by status, priority, account, or agent
- update case status, priority, or description
- get account details
- close case
- delete a case record
- support
- create contact
- contact management for service
- account for service context
- get account information for service context
- send a message in an active live chat session
- create a contact
- query
- initiate live chat
- create a new customer service case
- get customer service case details by id
- crm
- individual case operations
- update case status or details
- live chat initiation
- service cloud
- help desk
- send chat message
- delete case
- get contact details for a customer
- get case
- end an active live chat session
- individual contact
- update case status
- initiate a live chat session with a service agent
- case lifecycle management
- query service data
- delete a case
- get a contact
- initiate a live chat session
- customer service
- create a new contact record for a customer
- end chat session
- ticketing
- soql query
- salesforce
- create a new customer service case with subject, description, priority, and contact
- update case
slug: case-management
source_filename: case-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce Service Cloud Case Management\n  description: Unified workflow capability for customer service case management in Salesforce Service Cloud. Combines REST\n    API case CRUD with Live Agent chat initiation for complete customer service resolution workflows. Designed for service\n    agents and customer service AI assistants.\n  tags:\n  - Salesforce\n  - Service Cloud\n  - Case Management\n  - Customer Service\n  - Help Desk\n  - Support\n  - CRM\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n    SALESFORCE_LIVE_AGENT_TOKEN: SALESFORCE_LIVE_AGENT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: salesforce-service-rest\n    baseUri: https://{instance}.salesforce.com/services/data/v59.0\n    description: Salesforce Service Cloud REST API\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n\
  \    resources:\n    - name: cases\n      path: /sobjects/Case\n      description: Case management\n      operations:\n      - name: get-case-info\n        method: GET\n        description: Get Case object metadata and recent cases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-case\n        method: POST\n        description: Create a new customer service case\n        body:\n          type: json\n          data:\n            Subject: '{{tools.subject}}'\n            Description: '{{tools.description}}'\n            Status: '{{tools.status}}'\n            Priority: '{{tools.priority}}'\n            AccountId: '{{tools.accountId}}'\n            ContactId: '{{tools.contactId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: case\n      path: /sobjects/Case/{caseId}\n      description: Individual\
  \ case operations\n      operations:\n      - name: get-case\n        method: GET\n        description: Get a case by ID\n        inputParameters:\n        - name: caseId\n          in: path\n          type: string\n          required: true\n          description: Salesforce ID of the Case\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-case\n        method: PATCH\n        description: Update a case\n        inputParameters:\n        - name: caseId\n          in: path\n          type: string\n          required: true\n          description: Salesforce ID of the Case\n        body:\n          type: json\n          data:\n            Status: '{{tools.status}}'\n            Priority: '{{tools.priority}}'\n            Description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ delete-case\n        method: DELETE\n        description: Delete a case\n        inputParameters:\n        - name: caseId\n          in: path\n          type: string\n          required: true\n          description: Salesforce ID of the Case\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /sobjects/Contact\n      description: Contact management\n      operations:\n      - name: create-contact\n        method: POST\n        description: Create a new contact\n        body:\n          type: json\n          data:\n            FirstName: '{{tools.firstName}}'\n            LastName: '{{tools.lastName}}'\n            Email: '{{tools.email}}'\n            AccountId: '{{tools.accountId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contact\n      path: /sobjects/Contact/{contactId}\n  \
  \    description: Individual contact operations\n      operations:\n      - name: get-contact\n        method: GET\n        description: Get a contact by ID\n        inputParameters:\n        - name: contactId\n          in: path\n          type: string\n          required: true\n          description: Salesforce ID of the Contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /sobjects/Account/{accountId}\n      description: Account operations\n      operations:\n      - name: get-account\n        method: GET\n        description: Get an account by ID\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Salesforce ID of the Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-query\n\
  \      path: /query\n      description: SOQL query for service data\n      operations:\n      - name: query-service-data\n        method: GET\n        description: Query service cloud data with SOQL\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: SOQL query string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: salesforce-live-agent\n    baseUri: https://{instance}.salesforce.com/chat/rest\n    description: Salesforce Live Agent REST API\n    authentication:\n      type: apikey\n      key: X-LIVEAGENT-API-VERSION\n      value: '{{SALESFORCE_LIVE_AGENT_TOKEN}}'\n      placement: header\n    resources:\n    - name: visitor-session\n      path: /System/SessionId\n      description: Initialize visitor session\n      operations:\n      - name: create-visitor-session\n        method: GET\n  \
  \      description: Initialize a new visitor session for live chat\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chat-request\n      path: /Chasitor/ChasitorInit\n      description: Initiate chat request\n      operations:\n      - name: initiate-chat\n        method: POST\n        description: Initiate a live chat request with an agent\n        body:\n          type: json\n          data:\n            organizationId: '{{tools.organizationId}}'\n            deploymentId: '{{tools.deploymentId}}'\n            buttonId: '{{tools.buttonId}}'\n            sessionId: '{{tools.sessionId}}'\n            visitorName: '{{tools.visitorName}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chat-messages\n      path: /Chasitor/ChatMessage\n      description: Chat message management\n      operations:\n      - name:\
  \ send-chat-message\n        method: POST\n        description: Send a message in the live chat session\n        body:\n          type: json\n          data:\n            text: '{{tools.text}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chat-end\n      path: /Chasitor/ChatEnd\n      description: End chat session\n      operations:\n      - name: end-chat-session\n        method: POST\n        description: End the live chat session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: case-management-api\n    description: Unified REST API for Salesforce Service Cloud case management.\n    resources:\n    - path: /v1/cases\n      name: cases\n      description: Case lifecycle management\n      operations:\n      - method: POST\n        name: create-case\n      \
  \  description: Create a new customer service case\n        call: salesforce-service-rest.create-case\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cases/{caseId}\n      name: case\n      description: Individual case operations\n      operations:\n      - method: GET\n        name: get-case\n        description: Get case details\n        call: salesforce-service-rest.get-case\n        with:\n          caseId: rest.caseId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-case\n        description: Update case status or details\n        call: salesforce-service-rest.update-case\n        with:\n          caseId: rest.caseId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-case\n        description: Delete a case\n        call: salesforce-service-rest.delete-case\n        with:\n          caseId: rest.caseId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts\n      name: contacts\n      description: Contact management for service\n      operations:\n      - method: POST\n        name: create-contact\n        description: Create a contact\n        call: salesforce-service-rest.create-contact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts/{contactId}\n      name: contact\n      description: Individual contact\n      operations:\n      - method: GET\n        name: get-contact\n        description: Get a contact\n        call: salesforce-service-rest.get-contact\n        with:\n          contactId: rest.contactId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}\n      name: account\n      description: Account for service context\n      operations:\n      - method: GET\n        name: get-account\n        description: Get account details\n\
  \        call: salesforce-service-rest.get-account\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/query\n      name: query\n      description: SOQL query\n      operations:\n      - method: GET\n        name: query\n        description: Query service data\n        call: salesforce-service-rest.query-service-data\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/chat/initiate\n      name: live-chat\n      description: Live chat initiation\n      operations:\n      - method: POST\n        name: initiate-live-chat\n        description: Initiate a live chat session\n        call: salesforce-live-agent.initiate-chat\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: case-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Salesforce\
  \ Service Cloud case management.\n    tools:\n    - name: get-case\n      description: Get customer service case details by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-service-rest.get-case\n      with:\n        caseId: tools.caseId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-case\n      description: Create a new customer service case with subject, description, priority, and contact\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-service-rest.create-case\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-case-status\n      description: Update case status, priority, or description\n      hints:\n        readOnly: false\n        idempotent: true\n      call: salesforce-service-rest.update-case\n      with:\n        caseId: tools.caseId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: close-case\n\
  \      description: Close a customer service case by updating status to Closed\n      hints:\n        readOnly: false\n        idempotent: true\n      call: salesforce-service-rest.update-case\n      with:\n        caseId: tools.caseId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-case\n      description: Delete a case record\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: salesforce-service-rest.delete-case\n      with:\n        caseId: tools.caseId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contact\n      description: Get contact details for a customer\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-service-rest.get-contact\n      with:\n        contactId: tools.contactId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-contact\n      description: Create a new contact\
  \ record for a customer\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-service-rest.create-contact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Get account information for service context\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-service-rest.get-account\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-cases\n      description: Query cases using SOQL for filtering by status, priority, account, or agent\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: salesforce-service-rest.query-service-data\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiate-live-chat\n      description: Initiate a live chat session with a service agent\n\
  \      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-live-agent.initiate-chat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-chat-message\n      description: Send a message in an active live chat session\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-live-agent.send-chat-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: end-chat-session\n      description: End an active live chat session\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-live-agent.end-chat-session\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
