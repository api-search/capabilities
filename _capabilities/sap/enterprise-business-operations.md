---
categories:
- machine-learning
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
- s4hana get business partner
- s/4hana cloud business partner master data
- update a business partner in sap business one
- create an invoice in business one
- b1 list invoices
- get a specific business partner from s/4hana cloud
- financial journal entries
- update b1 business partner
- list business partner addresses from s/4hana
- item master data
- list journal entries
- ai execution management
- btp
- create an ai configuration in sap ai core
- list b1 business partners
- list business partners from sap business one
- s4hana list addresses
- create deployment
- b1 create journal entry
- business applications
- list invoices from business one
- ai list artifacts
- b1 create order
- b1 list business partners
- list executions
- ai create artifact
- list ai artifacts (models, datasets) from sap ai core
- ai scenario management
- list ai deployments
- create an ai execution
- trigger an ai training execution in sap ai core
- integration
- b1 update business partner
- enterprise
- s4hana create business partner
- cloud
- ai
- list sales orders from sap business one
- b1 list orders
- create an ai deployment
- list business partner tax numbers from s/4hana cloud
- list addresses
- list business partner bank accounts from s/4hana cloud
- ai create configuration
- get details of a specific ai execution
- business operations
- create a business partner in s/4hana cloud
- register a new ai artifact in sap ai core
- create execution
- create journal entry
- stop a running ai execution
- sap
- list business partner roles from s/4hana cloud
- b1 list items
- list ai configurations from sap ai core
- list ai training executions from sap ai core
- sales order management
- invoice management
- b1 list journal entries
- create b1 business partner
- list items from business one
- ai deployment management
- ai get execution
- create invoice
- b1 get business partner
- list invoices
- s4hana list tax numbers
- list s4hana business partners
- update a business partner in s/4hana cloud
- create s4hana business partner
- create a sales order in business one
- list accounts receivable invoices from sap business one
- ai list executions
- b1 create business partner
- create a sales order in sap business one
- list deployments
- list sales orders from business one
- list item master data from sap business one
- create an accounts receivable invoice in sap business one
- s4hana list roles
- data management
- get b1 business partner
- list ai model deployments from sap ai core
- list orders
- ai list configurations
- list ai executions
- business one business partner detail
- list ai scenarios from ai core
- create a business partner in sap business one
- s/4hana business partner addresses
- ai create deployment
- ai list deployments
- get a specific business partner from sap business one
- business one business partner management
- b1 create invoice
- s4hana list business partners
- ai delete execution
- list business partner master records from s/4hana cloud
- ai create execution
- s4hana update business partner
- s4hana list bank accounts
- list items
- ai list scenarios
- list business partners from s/4hana cloud
- erp
- list financial journal entries from sap business one
- list scenarios
- create an ai model deployment in sap ai core
- list ai scenarios from sap ai core
- create order
- create a financial journal entry in sap business one
- create a journal entry in business one
- list business partner addresses from s/4hana cloud
- list journal entries from business one
slug: enterprise-business-operations
source_filename: enterprise-business-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP Enterprise Business Operations\"\n  description: \"Unified workflow combining SAP Business One, S/4HANA Cloud Business Partner, and AI Core APIs for managing business partners, orders, financials, and AI-driven automation across SAP ERP systems.\"\n  tags:\n    - SAP\n    - Enterprise\n    - ERP\n    - AI\n    - Business Operations\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_AI_CORE_OAUTH_TOKEN: SAP_AI_CORE_OAUTH_TOKEN\n      SAP_B1_USERNAME: SAP_B1_USERNAME\n      SAP_B1_PASSWORD: SAP_B1_PASSWORD\n      SAP_B1_COMPANY_DB: SAP_B1_COMPANY_DB\n      SAP_S4HANA_USERNAME: SAP_S4HANA_USERNAME\n      SAP_S4HANA_PASSWORD: SAP_S4HANA_PASSWORD\n\ncapability:\n  consumes:\n    - import: sap-ai-core\n      location: ./shared/ai-core.yaml\n    - import: sap-business-one\n      location: ./shared/business-one.yaml\n    - import: sap-s4hana-bp\n      location: ./shared/s4hana-business-partner.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sap-enterprise-ops-api\n      description: \"Unified REST API for SAP enterprise business operations spanning ERP, master data, and AI workflows.\"\n      resources:\n        - path: /v1/business-partners\n          name: b1-business-partners\n          description: \"Business One business partner management\"\n          operations:\n            - method: GET\n              name: list-b1-business-partners\n              description: \"List business partners from SAP Business One\"\n              call: \"sap-business-one.list-business-partners\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-b1-business-partner\n              description: \"Create a business partner in SAP Business One\"\n              call: \"sap-business-one.create-business-partner\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/business-partners/{id}\n          name: b1-business-partner-detail\n          description: \"Business One business partner detail\"\n          operations:\n            - method: GET\n              name: get-b1-business-partner\n              description: \"Get a specific business partner from SAP Business One\"\n              call: \"sap-business-one.get-business-partner\"\n              with:\n                CardCode: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-b1-business-partner\n              description: \"Update a business partner in SAP Business One\"\n              call: \"sap-business-one.update-business-partner\"\n              with:\n                CardCode: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/s4hana-business-partners\n\
  \          name: s4hana-business-partners\n          description: \"S/4HANA Cloud business partner master data\"\n          operations:\n            - method: GET\n              name: list-s4hana-business-partners\n              description: \"List business partners from S/4HANA Cloud\"\n              call: \"sap-s4hana-bp.list-business-partners\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-s4hana-business-partner\n              description: \"Create a business partner in S/4HANA Cloud\"\n              call: \"sap-s4hana-bp.create-business-partner\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: \"Sales order management\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List sales orders\
  \ from Business One\"\n              call: \"sap-business-one.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-order\n              description: \"Create a sales order in Business One\"\n              call: \"sap-business-one.create-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/items\n          name: items\n          description: \"Item master data\"\n          operations:\n            - method: GET\n              name: list-items\n              description: \"List items from Business One\"\n              call: \"sap-business-one.list-items\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices\n          name: invoices\n          description: \"Invoice management\"\n          operations:\n            - method:\
  \ GET\n              name: list-invoices\n              description: \"List invoices from Business One\"\n              call: \"sap-business-one.list-invoices\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-invoice\n              description: \"Create an invoice in Business One\"\n              call: \"sap-business-one.create-invoice\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/journal-entries\n          name: journal-entries\n          description: \"Financial journal entries\"\n          operations:\n            - method: GET\n              name: list-journal-entries\n              description: \"List journal entries from Business One\"\n              call: \"sap-business-one.list-journal-entries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \            - method: POST\n              name: create-journal-entry\n              description: \"Create a journal entry in Business One\"\n              call: \"sap-business-one.create-journal-entry\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/addresses\n          name: addresses\n          description: \"S/4HANA business partner addresses\"\n          operations:\n            - method: GET\n              name: list-addresses\n              description: \"List business partner addresses from S/4HANA\"\n              call: \"sap-s4hana-bp.list-addresses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/scenarios\n          name: ai-scenarios\n          description: \"AI scenario management\"\n          operations:\n            - method: GET\n              name: list-scenarios\n              description: \"List AI scenarios from AI Core\"\
  \n              call: \"sap-ai-core.list-scenarios\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/executions\n          name: ai-executions\n          description: \"AI execution management\"\n          operations:\n            - method: GET\n              name: list-executions\n              description: \"List AI executions\"\n              call: \"sap-ai-core.list-executions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-execution\n              description: \"Create an AI execution\"\n              call: \"sap-ai-core.create-execution\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/deployments\n          name: ai-deployments\n          description: \"AI deployment management\"\n          operations:\n            - method: GET\n\
  \              name: list-deployments\n              description: \"List AI deployments\"\n              call: \"sap-ai-core.list-deployments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-deployment\n              description: \"Create an AI deployment\"\n              call: \"sap-ai-core.create-deployment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sap-enterprise-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP enterprise business operations across ERP, master data, and AI workflows.\"\n      tools:\n        - name: b1-list-business-partners\n          description: \"List business partners from SAP Business One\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-business-one.list-business-partners\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: b1-create-business-partner\n          description: \"Create a business partner in SAP Business One\"\n          hints:\n            readOnly: false\n          call: \"sap-business-one.create-business-partner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: b1-get-business-partner\n          description: \"Get a specific business partner from SAP Business One\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-business-one.get-business-partner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: b1-update-business-partner\n          description: \"Update a business partner in SAP Business One\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"sap-business-one.update-business-partner\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: b1-list-orders\n          description: \"List sales orders from SAP Business One\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-business-one.list-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: b1-create-order\n          description: \"Create a sales order in SAP Business One\"\n          hints:\n            readOnly: false\n          call: \"sap-business-one.create-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: b1-list-items\n          description: \"List item master data from SAP Business One\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-business-one.list-items\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: b1-list-journal-entries\n          description: \"List financial journal entries from SAP Business One\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-business-one.list-journal-entries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: b1-create-journal-entry\n          description: \"Create a financial journal entry in SAP Business One\"\n          hints:\n            readOnly: false\n          call: \"sap-business-one.create-journal-entry\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: b1-list-invoices\n          description: \"List accounts receivable invoices from SAP Business One\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-business-one.list-invoices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: b1-create-invoice\n          description: \"Create an accounts receivable invoice in SAP Business One\"\n          hints:\n            readOnly: false\n          call: \"sap-business-one.create-invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: s4hana-list-business-partners\n          description: \"List business partner master records from S/4HANA Cloud\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-s4hana-bp.list-business-partners\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: s4hana-create-business-partner\n          description: \"Create a business partner in S/4HANA Cloud\"\n          hints:\n            readOnly: false\n          call: \"sap-s4hana-bp.create-business-partner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: s4hana-get-business-partner\n\
  \          description: \"Get a specific business partner from S/4HANA Cloud\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-s4hana-bp.get-business-partner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: s4hana-update-business-partner\n          description: \"Update a business partner in S/4HANA Cloud\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"sap-s4hana-bp.update-business-partner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: s4hana-list-addresses\n          description: \"List business partner addresses from S/4HANA Cloud\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-s4hana-bp.list-addresses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: s4hana-list-bank-accounts\n\
  \          description: \"List business partner bank accounts from S/4HANA Cloud\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-s4hana-bp.list-bank-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: s4hana-list-roles\n          description: \"List business partner roles from S/4HANA Cloud\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-s4hana-bp.list-roles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: s4hana-list-tax-numbers\n          description: \"List business partner tax numbers from S/4HANA Cloud\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-s4hana-bp.list-tax-numbers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-list-scenarios\n       \
  \   description: \"List AI scenarios from SAP AI Core\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-ai-core.list-scenarios\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-list-configurations\n          description: \"List AI configurations from SAP AI Core\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-ai-core.list-configurations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-create-configuration\n          description: \"Create an AI configuration in SAP AI Core\"\n          hints:\n            readOnly: false\n          call: \"sap-ai-core.create-configuration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-list-executions\n          description: \"List AI training executions from SAP AI Core\"\n\
  \          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-ai-core.list-executions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-create-execution\n          description: \"Trigger an AI training execution in SAP AI Core\"\n          hints:\n            readOnly: false\n          call: \"sap-ai-core.create-execution\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-get-execution\n          description: \"Get details of a specific AI execution\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-ai-core.get-execution\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-delete-execution\n          description: \"Stop a running AI execution\"\n          hints:\n            readOnly: false\n            destructive: true\n      \
  \      idempotent: true\n          call: \"sap-ai-core.delete-execution\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-list-deployments\n          description: \"List AI model deployments from SAP AI Core\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-ai-core.list-deployments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-create-deployment\n          description: \"Create an AI model deployment in SAP AI Core\"\n          hints:\n            readOnly: false\n          call: \"sap-ai-core.create-deployment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-list-artifacts\n          description: \"List AI artifacts (models, datasets) from SAP AI Core\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-ai-core.list-artifacts\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ai-create-artifact\n          description: \"Register a new AI artifact in SAP AI Core\"\n          hints:\n            readOnly: false\n          call: \"sap-ai-core.create-artifact\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap/refs/heads/main/capabilities/enterprise-business-operations.yaml
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
