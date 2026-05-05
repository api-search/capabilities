---
categories: []
consumed_apis:
- salesforce-rest
description: CRM data management workflow combining Salesforce REST API record operations, SOQL querying, and SOSL search for managing accounts, contacts, leads, opportunities, and cases. Used by sales ops teams, integration engineers, and data pipelines to synchronize and manage CRM records programmatically.
layout: capability
name: Salesforce CRM Data Management
operations:
- description: Create a new Salesforce record
  method: POST
  name: create-record
  path: /v1/records/{sObjectName}
- description: Get a Salesforce record by sObject type and ID
  method: GET
  name: get-record
  path: /v1/records/{sObjectName}/{id}
- description: Update fields on a Salesforce record
  method: PATCH
  name: update-record
  path: /v1/records/{sObjectName}/{id}
- description: Delete a Salesforce record
  method: DELETE
  name: delete-record
  path: /v1/records/{sObjectName}/{id}
- description: Execute a SOQL query
  method: GET
  name: execute-query
  path: /v1/query
- description: Execute a SOSL search across multiple object types
  method: GET
  name: execute-search
  path: /v1/search
- description: Get field definitions for a Salesforce object type
  method: GET
  name: describe-sobject
  path: /v1/metadata/{sObjectName}
- description: Get current Salesforce org limits and API usage
  method: GET
  name: get-org-limits
  path: /v1/limits
personas: []
provider_name: Salesforce
provider_slug: salesforcecom
search_terms:
- create new records by sobject type
- sobject field metadata
- get a salesforce record by sobject type and id
- delete a salesforce record
- get field metadata
- query records
- read, update, and delete individual records
- create a new salesforce record
- records
- execute search
- execute a soql query
- cloud
- marketing
- ai
- delete a salesforce crm record (moves to recycle bin, recoverable)
- update fields on a salesforce record
- check current salesforce org api call limits and remaining usage
- query
- create a new salesforce crm record (account, contact, lead, opportunity, case)
- execute query
- search records
- org api usage limits
- execute a sosl search across multiple object types
- update record
- query salesforce records using soql (e.g., select id, name from account where industry = 'technology')
- update fields on an existing salesforce crm record
- describe sobject
- salesforce
- get field definitions for a salesforce object type
- data management
- delete record
- create record
- get org limits
- crm
- soql query execution
- sales
- search across multiple salesforce object types using sosl full-text search
- get current salesforce org limits and api usage
- get field definitions and schema metadata for a salesforce object type
- get record
- automation
- check api limits
- sosl cross-object search
- retrieve a specific salesforce crm record by object type and id
slug: crm-data-management
source_filename: crm-data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce CRM Data Management\"\n  description: >-\n    CRM data management workflow combining Salesforce REST API record operations,\n    SOQL querying, and SOSL search for managing accounts, contacts, leads,\n    opportunities, and cases. Used by sales ops teams, integration engineers,\n    and data pipelines to synchronize and manage CRM records programmatically.\n  tags:\n    - CRM\n    - Salesforce\n    - Data Management\n    - Records\n    - Query\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n      SALESFORCE_INSTANCE: SALESFORCE_INSTANCE\n\ncapability:\n  consumes:\n    - import: salesforce-rest\n      location: ./shared/salesforce-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: crm-data-management-api\n      description: \"Unified REST API for Salesforce CRM data management workflows.\"\
  \n      resources:\n        - path: /v1/records/{sObjectName}\n          name: records-by-type\n          description: \"Create new records by sObject type\"\n          operations:\n            - method: POST\n              name: create-record\n              description: \"Create a new Salesforce record\"\n              call: \"salesforce-rest.create-record\"\n              with:\n                sObjectName: \"rest.sObjectName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/records/{sObjectName}/{id}\n          name: record-by-id\n          description: \"Read, update, and delete individual records\"\n          operations:\n            - method: GET\n              name: get-record\n              description: \"Get a Salesforce record by sObject type and ID\"\n              call: \"salesforce-rest.get-record\"\n              with:\n                sObjectName: \"rest.sObjectName\"\n                id: \"rest.id\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-record\n              description: \"Update fields on a Salesforce record\"\n              call: \"salesforce-rest.update-record\"\n              with:\n                sObjectName: \"rest.sObjectName\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-record\n              description: \"Delete a Salesforce record\"\n              call: \"salesforce-rest.delete-record\"\n              with:\n                sObjectName: \"rest.sObjectName\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/query\n          name: soql-query\n          description: \"SOQL query execution\"\n          operations:\n\
  \            - method: GET\n              name: execute-query\n              description: \"Execute a SOQL query\"\n              call: \"salesforce-rest.execute-query\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search\n          name: sosl-search\n          description: \"SOSL cross-object search\"\n          operations:\n            - method: GET\n              name: execute-search\n              description: \"Execute a SOSL search across multiple object types\"\n              call: \"salesforce-rest.execute-search\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/metadata/{sObjectName}\n          name: object-metadata\n          description: \"sObject field metadata\"\n          operations:\n            - method: GET\n       \
  \       name: describe-sobject\n              description: \"Get field definitions for a Salesforce object type\"\n              call: \"salesforce-rest.describe-sobject\"\n              with:\n                sObjectName: \"rest.sObjectName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/limits\n          name: org-limits\n          description: \"Org API usage limits\"\n          operations:\n            - method: GET\n              name: get-org-limits\n              description: \"Get current Salesforce org limits and API usage\"\n              call: \"salesforce-rest.get-org-limits\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: crm-data-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Salesforce CRM data management.\"\n      tools:\n        - name: query-records\n\
  \          description: \"Query Salesforce records using SOQL (e.g., SELECT Id, Name FROM Account WHERE Industry = 'Technology')\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"salesforce-rest.execute-query\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-records\n          description: \"Search across multiple Salesforce object types using SOSL full-text search\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"salesforce-rest.execute-search\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-record\n          description: \"Retrieve a specific Salesforce CRM record by object type and ID\"\n          hints:\n           \
  \ readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.get-record\"\n          with:\n            sObjectName: \"tools.sObjectName\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-record\n          description: \"Create a new Salesforce CRM record (Account, Contact, Lead, Opportunity, Case)\"\n          hints:\n            readOnly: false\n          call: \"salesforce-rest.create-record\"\n          with:\n            sObjectName: \"tools.sObjectName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-record\n          description: \"Update fields on an existing Salesforce CRM record\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesforce-rest.update-record\"\n          with:\n            sObjectName: \"tools.sObjectName\"\n            id: \"tools.id\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-record\n          description: \"Delete a Salesforce CRM record (moves to recycle bin, recoverable)\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"salesforce-rest.delete-record\"\n          with:\n            sObjectName: \"tools.sObjectName\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-field-metadata\n          description: \"Get field definitions and schema metadata for a Salesforce object type\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.describe-sobject\"\n          with:\n            sObjectName: \"tools.sObjectName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-api-limits\n\
  \          description: \"Check current Salesforce org API call limits and remaining usage\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.get-org-limits\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforcecom/refs/heads/main/capabilities/crm-data-management.yaml
tags:
- CRM
- Salesforce
- Data Management
- Records
- Query
tools:
- description: Query Salesforce records using SOQL (e.g., SELECT Id, Name FROM Account WHERE Industry = 'Technology')
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-records
- description: Search across multiple Salesforce object types using SOSL full-text search
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-records
- description: Retrieve a specific Salesforce CRM record by object type and ID
  hints:
    idempotent: true
    readOnly: true
  name: get-record
- description: Create a new Salesforce CRM record (Account, Contact, Lead, Opportunity, Case)
  hints:
    readOnly: false
  name: create-record
- description: Update fields on an existing Salesforce CRM record
  hints:
    idempotent: true
    readOnly: false
  name: update-record
- description: Delete a Salesforce CRM record (moves to recycle bin, recoverable)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-record
- description: Get field definitions and schema metadata for a Salesforce object type
  hints:
    idempotent: true
    readOnly: true
  name: get-field-metadata
- description: Check current Salesforce org API call limits and remaining usage
  hints:
    idempotent: true
    readOnly: true
  name: check-api-limits
---
