---
consumed_apis:
- sap-ai-core
- sap-business-one
- sap-s4hana-bp
description: Unified workflow combining SAP Business One, S/4HANA Cloud Business Partner, and AI Core APIs for managing business partners, orders, financials, and AI-driven automation across SAP ERP systems.
layout: capability
name: SAP Enterprise Business Operations
operations:
- description: List business partners from SAP Business One
  method: GET
  name: list-b1-business-partners
  path: /v1/business-partners
- description: Create a business partner in SAP Business One
  method: POST
  name: create-b1-business-partner
  path: /v1/business-partners
- description: Get a specific business partner from SAP Business One
  method: GET
  name: get-b1-business-partner
  path: /v1/business-partners/{id}
- description: Update a business partner in SAP Business One
  method: PATCH
  name: update-b1-business-partner
  path: /v1/business-partners/{id}
- description: List business partners from S/4HANA Cloud
  method: GET
  name: list-s4hana-business-partners
  path: /v1/s4hana-business-partners
- description: Create a business partner in S/4HANA Cloud
  method: POST
  name: create-s4hana-business-partner
  path: /v1/s4hana-business-partners
- description: List sales orders from Business One
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a sales order in Business One
  method: POST
  name: create-order
  path: /v1/orders
- description: List items from Business One
  method: GET
  name: list-items
  path: /v1/items
- description: List invoices from Business One
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Create an invoice in Business One
  method: POST
  name: create-invoice
  path: /v1/invoices
- description: List journal entries from Business One
  method: GET
  name: list-journal-entries
  path: /v1/journal-entries
- description: Create a journal entry in Business One
  method: POST
  name: create-journal-entry
  path: /v1/journal-entries
- description: List business partner addresses from S/4HANA
  method: GET
  name: list-addresses
  path: /v1/addresses
- description: List AI scenarios from AI Core
  method: GET
  name: list-scenarios
  path: /v1/scenarios
- description: List AI executions
  method: GET
  name: list-executions
  path: /v1/executions
- description: Create an AI execution
  method: POST
  name: create-execution
  path: /v1/executions
- description: List AI deployments
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: Create an AI deployment
  method: POST
  name: create-deployment
  path: /v1/deployments
personas: []
provider_name: SAP
provider_slug: sap
search_terms:
- list journal entries from business one
- list ai scenarios from ai core
- ai create artifact
- item master data
- ai list deployments
- s/4hana cloud business partner master data
- register a new ai artifact in sap ai core
- list items
- ai execution management
- list item master data from sap business one
- list b1 business partners
- list ai training executions from sap ai core
- s4hana list roles
- financial journal entries
- list deployments
- list invoices from business one
- s/4hana business partner addresses
- create invoice
- list ai deployments
- create s4hana business partner
- list ai configurations from sap ai core
- list ai model deployments from sap ai core
- ai delete execution
- b1 create business partner
- sales order management
- list executions
- list scenarios
- create a business partner in s/4hana cloud
- list business partner roles from s/4hana cloud
- list business partner addresses from s/4hana
- list sales orders from sap business one
- ai list scenarios
- b1 list items
- ai
- s4hana list bank accounts
- get b1 business partner
- list s4hana business partners
- integration
- enterprise
- list sales orders from business one
- b1 list business partners
- create a financial journal entry in sap business one
- create an accounts receivable invoice in sap business one
- ai create deployment
- cloud
- create an ai execution
- ai list configurations
- create deployment
- s4hana update business partner
- get details of a specific ai execution
- create journal entry
- create a sales order in sap business one
- business one business partner management
- s4hana list tax numbers
- data management
- ai list executions
- b1 get business partner
- create an ai configuration in sap ai core
- ai create configuration
- list financial journal entries from sap business one
- list ai scenarios from sap ai core
- stop a running ai execution
- list ai artifacts (models, datasets) from sap ai core
- b1 create journal entry
- b1 list invoices
- update b1 business partner
- update a business partner in s/4hana cloud
- b1 update business partner
- create a sales order in business one
- b1 create order
- sap
- create order
- get a specific business partner from s/4hana cloud
- update a business partner in sap business one
- list ai executions
- list invoices
- s4hana get business partner
- ai get execution
- invoice management
- b1 list orders
- business applications
- list business partners from s/4hana cloud
- business operations
- create a journal entry in business one
- erp
- create an ai deployment
- list business partner master records from s/4hana cloud
- create an invoice in business one
- s4hana create business partner
- ai scenario management
- list journal entries
- create execution
- create an ai model deployment in sap ai core
- s4hana list business partners
- create a business partner in sap business one
- get a specific business partner from sap business one
- list business partner bank accounts from s/4hana cloud
- trigger an ai training execution in sap ai core
- ai deployment management
- btp
- list business partner tax numbers from s/4hana cloud
- b1 list journal entries
- list business partners from sap business one
- ai list artifacts
- s4hana list addresses
- list accounts receivable invoices from sap business one
- business one business partner detail
- ai create execution
- list business partner addresses from s/4hana cloud
- list orders
- create b1 business partner
- b1 create invoice
- list items from business one
- list addresses
slug: enterprise-business-operations
tags:
- SAP
- Enterprise
- ERP
- AI
- Business Operations
tools:
- description: List business partners from SAP Business One
  hints:
    openWorld: true
    readOnly: true
  name: b1-list-business-partners
- description: Create a business partner in SAP Business One
  hints:
    readOnly: false
  name: b1-create-business-partner
- description: Get a specific business partner from SAP Business One
  hints:
    openWorld: true
    readOnly: true
  name: b1-get-business-partner
- description: Update a business partner in SAP Business One
  hints:
    idempotent: true
    readOnly: false
  name: b1-update-business-partner
- description: List sales orders from SAP Business One
  hints:
    openWorld: true
    readOnly: true
  name: b1-list-orders
- description: Create a sales order in SAP Business One
  hints:
    readOnly: false
  name: b1-create-order
- description: List item master data from SAP Business One
  hints:
    openWorld: true
    readOnly: true
  name: b1-list-items
- description: List financial journal entries from SAP Business One
  hints:
    openWorld: true
    readOnly: true
  name: b1-list-journal-entries
- description: Create a financial journal entry in SAP Business One
  hints:
    readOnly: false
  name: b1-create-journal-entry
- description: List accounts receivable invoices from SAP Business One
  hints:
    openWorld: true
    readOnly: true
  name: b1-list-invoices
- description: Create an accounts receivable invoice in SAP Business One
  hints:
    readOnly: false
  name: b1-create-invoice
- description: List business partner master records from S/4HANA Cloud
  hints:
    openWorld: true
    readOnly: true
  name: s4hana-list-business-partners
- description: Create a business partner in S/4HANA Cloud
  hints:
    readOnly: false
  name: s4hana-create-business-partner
- description: Get a specific business partner from S/4HANA Cloud
  hints:
    openWorld: true
    readOnly: true
  name: s4hana-get-business-partner
- description: Update a business partner in S/4HANA Cloud
  hints:
    idempotent: true
    readOnly: false
  name: s4hana-update-business-partner
- description: List business partner addresses from S/4HANA Cloud
  hints:
    openWorld: true
    readOnly: true
  name: s4hana-list-addresses
- description: List business partner bank accounts from S/4HANA Cloud
  hints:
    openWorld: true
    readOnly: true
  name: s4hana-list-bank-accounts
- description: List business partner roles from S/4HANA Cloud
  hints:
    openWorld: true
    readOnly: true
  name: s4hana-list-roles
- description: List business partner tax numbers from S/4HANA Cloud
  hints:
    openWorld: true
    readOnly: true
  name: s4hana-list-tax-numbers
- description: List AI scenarios from SAP AI Core
  hints:
    openWorld: true
    readOnly: true
  name: ai-list-scenarios
- description: List AI configurations from SAP AI Core
  hints:
    openWorld: true
    readOnly: true
  name: ai-list-configurations
- description: Create an AI configuration in SAP AI Core
  hints:
    readOnly: false
  name: ai-create-configuration
- description: List AI training executions from SAP AI Core
  hints:
    openWorld: true
    readOnly: true
  name: ai-list-executions
- description: Trigger an AI training execution in SAP AI Core
  hints:
    readOnly: false
  name: ai-create-execution
- description: Get details of a specific AI execution
  hints:
    openWorld: true
    readOnly: true
  name: ai-get-execution
- description: Stop a running AI execution
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: ai-delete-execution
- description: List AI model deployments from SAP AI Core
  hints:
    openWorld: true
    readOnly: true
  name: ai-list-deployments
- description: Create an AI model deployment in SAP AI Core
  hints:
    readOnly: false
  name: ai-create-deployment
- description: List AI artifacts (models, datasets) from SAP AI Core
  hints:
    openWorld: true
    readOnly: true
  name: ai-list-artifacts
- description: Register a new AI artifact in SAP AI Core
  hints:
    readOnly: false
  name: ai-create-artifact
---
