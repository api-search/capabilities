---
categories: []
consumed_apis:
- salesforce-sales-rest
- salesforce-analytics
description: Unified workflow capability for managing the full sales pipeline in Salesforce Sales Cloud. Combines REST API access to accounts, contacts, leads, opportunities, and activities with analytics for pipeline reporting. Designed for sales operations teams and AI assistants managing deal flow.
layout: capability
name: Salesforce Sales Pipeline Management
operations:
- description: Create a new account record
  method: POST
  name: create-account
  path: /v1/accounts
- description: Get an account record
  method: GET
  name: get-account
  path: /v1/accounts/{id}
- description: Update an account record
  method: PATCH
  name: update-account
  path: /v1/accounts/{id}
- description: Create a new contact record
  method: POST
  name: create-contact
  path: /v1/contacts
- description: Get a contact record
  method: GET
  name: get-contact
  path: /v1/contacts/{id}
- description: Create a new lead record
  method: POST
  name: create-lead
  path: /v1/leads
- description: Get a lead record
  method: GET
  name: get-lead
  path: /v1/leads/{id}
- description: Create a new opportunity
  method: POST
  name: create-opportunity
  path: /v1/opportunities
- description: Get an opportunity record
  method: GET
  name: get-opportunity
  path: /v1/opportunities/{id}
- description: Update an opportunity
  method: PATCH
  name: update-opportunity
  path: /v1/opportunities/{id}
- description: Execute a SOQL query
  method: GET
  name: query
  path: /v1/query
- description: List available sales reports
  method: GET
  name: list-reports
  path: /v1/reports
- description: Execute a sales report
  method: POST
  name: run-report
  path: /v1/reports/{reportId}/run
personas: []
provider_name: Salesforce Sales Cloud
provider_slug: salesforce-sales-cloud
search_terms:
- get lead
- update opportunity
- get current api usage and limits for the salesforce org
- individual contact operations
- soql query for advanced data access
- execute a salesforce report and retrieve results for pipeline analysis
- opportunities
- lead management
- search across salesforce objects using sosl
- account management
- create a new account record
- create opportunity
- get contact
- get a salesforce opportunity record by id
- update an existing account record
- create contact
- update account
- create a new contact record
- salesforce
- sales
- get an opportunity record
- customer management
- enterprise
- opportunity management
- cloud
- get a salesforce lead record by id
- list available sales reports
- individual account operations
- list sales reports
- get org api limits
- execute a soql query
- list dashboards
- get account
- crm
- accounts
- get a lead record
- create a new account record in salesforce
- execute a soql query to retrieve crm records with custom filters
- execute a sales report
- create a new opportunity
- sales reports
- get a salesforce account record by id
- create a new lead record
- list available salesforce dashboards
- create a new contact record in salesforce
- query
- update an existing opportunity (stage, amount, close date)
- create account
- create a new opportunity record in salesforce
- update an opportunity
- individual opportunity operations
- list reports
- sales cloud
- leads
- individual lead operations
- sales pipeline
- get an account record
- list available salesforce reports for sales analytics
- update an account record
- create lead
- contact management
- get opportunity
- run report
- soql query
- get a contact record
- report execution
- sosl search
- get a salesforce contact record by id
- create a new lead record in salesforce
- run sales report
slug: sales-pipeline-management
source_filename: sales-pipeline-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Sales Pipeline Management\"\n  description: >-\n    Unified workflow capability for managing the full sales pipeline in Salesforce\n    Sales Cloud. Combines REST API access to accounts, contacts, leads,\n    opportunities, and activities with analytics for pipeline reporting.\n    Designed for sales operations teams and AI assistants managing deal flow.\n  tags:\n    - Salesforce\n    - Sales Cloud\n    - CRM\n    - Sales Pipeline\n    - Opportunities\n    - Accounts\n    - Leads\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: salesforce-sales-rest\n      location: ./shared/sales-cloud-rest-api.yaml\n    - import: salesforce-analytics\n      location: ./shared/sales-cloud-analytics-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sales-pipeline-api\n\
  \      description: \"Unified REST API for Salesforce sales pipeline management.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n          description: \"Account management\"\n          operations:\n            - method: POST\n              name: create-account\n              description: \"Create a new account record\"\n              call: \"salesforce-sales-rest.create-sobject-record\"\n              with:\n                sObjectName: \"Account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts/{id}\n          name: account\n          description: \"Individual account operations\"\n          operations:\n            - method: GET\n              name: get-account\n              description: \"Get an account record\"\n              call: \"salesforce-sales-rest.get-sobject-record\"\n              with:\n                sObjectName: \"Account\"\n                id: \"rest.id\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-account\n              description: \"Update an account record\"\n              call: \"salesforce-sales-rest.update-sobject-record\"\n              with:\n                sObjectName: \"Account\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contacts\n          name: contacts\n          description: \"Contact management\"\n          operations:\n            - method: POST\n              name: create-contact\n              description: \"Create a new contact record\"\n              call: \"salesforce-sales-rest.create-sobject-record\"\n              with:\n                sObjectName: \"Contact\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contacts/{id}\n\
  \          name: contact\n          description: \"Individual contact operations\"\n          operations:\n            - method: GET\n              name: get-contact\n              description: \"Get a contact record\"\n              call: \"salesforce-sales-rest.get-sobject-record\"\n              with:\n                sObjectName: \"Contact\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/leads\n          name: leads\n          description: \"Lead management\"\n          operations:\n            - method: POST\n              name: create-lead\n              description: \"Create a new lead record\"\n              call: \"salesforce-sales-rest.create-sobject-record\"\n              with:\n                sObjectName: \"Lead\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/leads/{id}\n          name: lead\n\
  \          description: \"Individual lead operations\"\n          operations:\n            - method: GET\n              name: get-lead\n              description: \"Get a lead record\"\n              call: \"salesforce-sales-rest.get-sobject-record\"\n              with:\n                sObjectName: \"Lead\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/opportunities\n          name: opportunities\n          description: \"Opportunity management\"\n          operations:\n            - method: POST\n              name: create-opportunity\n              description: \"Create a new opportunity\"\n              call: \"salesforce-sales-rest.create-sobject-record\"\n              with:\n                sObjectName: \"Opportunity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/opportunities/{id}\n          name:\
  \ opportunity\n          description: \"Individual opportunity operations\"\n          operations:\n            - method: GET\n              name: get-opportunity\n              description: \"Get an opportunity record\"\n              call: \"salesforce-sales-rest.get-sobject-record\"\n              with:\n                sObjectName: \"Opportunity\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-opportunity\n              description: \"Update an opportunity\"\n              call: \"salesforce-sales-rest.update-sobject-record\"\n              with:\n                sObjectName: \"Opportunity\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/query\n          name: soql-query\n          description: \"SOQL query for advanced data access\"\n\
  \          operations:\n            - method: GET\n              name: query\n              description: \"Execute a SOQL query\"\n              call: \"salesforce-sales-rest.soql-query\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n          name: reports\n          description: \"Sales reports\"\n          operations:\n            - method: GET\n              name: list-reports\n              description: \"List available sales reports\"\n              call: \"salesforce-analytics.list-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/{reportId}/run\n          name: report-execution\n          description: \"Report execution\"\n          operations:\n            - method: POST\n              name: run-report\n              description: \"Execute a sales report\"\
  \n              call: \"salesforce-analytics.run-report\"\n              with:\n                reportId: \"rest.reportId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sales-pipeline-mcp\n      transport: http\n      description: \"MCP server for AI-assisted sales pipeline management in Salesforce.\"\n      tools:\n        - name: get-account\n          description: \"Get a Salesforce Account record by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-sales-rest.get-sobject-record\"\n          with:\n            sObjectName: \"Account\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-account\n          description: \"Create a new Account record in Salesforce\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n          call: \"salesforce-sales-rest.create-sobject-record\"\n          with:\n            sObjectName: \"Account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-account\n          description: \"Update an existing Account record\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesforce-sales-rest.update-sobject-record\"\n          with:\n            sObjectName: \"Account\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-contact\n          description: \"Get a Salesforce Contact record by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-sales-rest.get-sobject-record\"\n          with:\n            sObjectName: \"Contact\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: create-contact\n          description: \"Create a new Contact record in Salesforce\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-sales-rest.create-sobject-record\"\n          with:\n            sObjectName: \"Contact\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-lead\n          description: \"Get a Salesforce Lead record by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-sales-rest.get-sobject-record\"\n          with:\n            sObjectName: \"Lead\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-lead\n          description: \"Create a new Lead record in Salesforce\"\n          hints:\n            readOnly: false\n            destructive: false\n      \
  \    call: \"salesforce-sales-rest.create-sobject-record\"\n          with:\n            sObjectName: \"Lead\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-opportunity\n          description: \"Get a Salesforce Opportunity record by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-sales-rest.get-sobject-record\"\n          with:\n            sObjectName: \"Opportunity\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-opportunity\n          description: \"Create a new Opportunity record in Salesforce\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-sales-rest.create-sobject-record\"\n          with:\n            sObjectName: \"Opportunity\"\n          outputParameters:\n            - type: object\n           \
  \   mapping: \"$.\"\n        - name: update-opportunity\n          description: \"Update an existing Opportunity (stage, amount, close date)\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesforce-sales-rest.update-sobject-record\"\n          with:\n            sObjectName: \"Opportunity\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: soql-query\n          description: \"Execute a SOQL query to retrieve CRM records with custom filters\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"salesforce-sales-rest.soql-query\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: sosl-search\n          description: \"Search across Salesforce objects using SOSL\"\n          hints:\n    \
  \        readOnly: true\n            idempotent: true\n          call: \"salesforce-sales-rest.sosl-search\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-org-api-limits\n          description: \"Get current API usage and limits for the Salesforce org\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-sales-rest.get-org-limits\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sales-reports\n          description: \"List available Salesforce reports for sales analytics\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"salesforce-analytics.list-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-sales-report\n          description:\
  \ \"Execute a Salesforce report and retrieve results for pipeline analysis\"\n          hints:\n            readOnly: true\n            idempotent: false\n          call: \"salesforce-analytics.run-report\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dashboards\n          description: \"List available Salesforce dashboards\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-analytics.list-dashboards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-sales-cloud/refs/heads/main/capabilities/sales-pipeline-management.yaml
tags:
- Salesforce
- Sales Cloud
- CRM
- Sales Pipeline
- Opportunities
- Accounts
- Leads
tools:
- description: Get a Salesforce Account record by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-account
- description: Create a new Account record in Salesforce
  hints:
    destructive: false
    readOnly: false
  name: create-account
- description: Update an existing Account record
  hints:
    idempotent: true
    readOnly: false
  name: update-account
- description: Get a Salesforce Contact record by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-contact
- description: Create a new Contact record in Salesforce
  hints:
    destructive: false
    readOnly: false
  name: create-contact
- description: Get a Salesforce Lead record by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-lead
- description: Create a new Lead record in Salesforce
  hints:
    destructive: false
    readOnly: false
  name: create-lead
- description: Get a Salesforce Opportunity record by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-opportunity
- description: Create a new Opportunity record in Salesforce
  hints:
    destructive: false
    readOnly: false
  name: create-opportunity
- description: Update an existing Opportunity (stage, amount, close date)
  hints:
    idempotent: true
    readOnly: false
  name: update-opportunity
- description: Execute a SOQL query to retrieve CRM records with custom filters
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: soql-query
- description: Search across Salesforce objects using SOSL
  hints:
    idempotent: true
    readOnly: true
  name: sosl-search
- description: Get current API usage and limits for the Salesforce org
  hints:
    idempotent: true
    readOnly: true
  name: get-org-api-limits
- description: List available Salesforce reports for sales analytics
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-sales-reports
- description: Execute a Salesforce report and retrieve results for pipeline analysis
  hints:
    idempotent: false
    readOnly: true
  name: run-sales-report
- description: List available Salesforce dashboards
  hints:
    idempotent: true
    readOnly: true
  name: list-dashboards
---
