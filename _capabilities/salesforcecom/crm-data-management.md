---
categories: []
consumed_apis: []
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
- update fields on a salesforce record
- automation
- delete a salesforce crm record (moves to recycle bin, recoverable)
- create record
- retrieve a specific salesforce crm record by object type and id
- ai
- get a salesforce record by sobject type and id
- sosl cross-object search
- create new records by sobject type
- read, update, and delete individual records
- delete a salesforce record
- org api usage limits
- query
- get current salesforce org limits and api usage
- search records
- get field definitions and schema metadata for a salesforce object type
- data management
- get field definitions for a salesforce object type
- get record
- search across multiple salesforce object types using sosl full-text search
- crm
- delete record
- update record
- query records
- create a new salesforce crm record (account, contact, lead, opportunity, case)
- update fields on an existing salesforce crm record
- query salesforce records using soql (e.g., select id, name from account where industry = 'technology')
- check api limits
- execute query
- create a new salesforce record
- execute search
- cloud
- soql query execution
- execute a sosl search across multiple object types
- get field metadata
- records
- sales
- sobject field metadata
- marketing
- get org limits
- execute a soql query
- check current salesforce org api call limits and remaining usage
- salesforce
- describe sobject
slug: crm-data-management
source_filename: crm-data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce CRM Data Management\n  description: CRM data management workflow combining Salesforce REST API record operations, SOQL querying, and SOSL search\n    for managing accounts, contacts, leads, opportunities, and cases. Used by sales ops teams, integration engineers, and\n    data pipelines to synchronize and manage CRM records programmatically.\n  tags:\n  - CRM\n  - Salesforce\n  - Data Management\n  - Records\n  - Query\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n    SALESFORCE_INSTANCE: SALESFORCE_INSTANCE\ncapability:\n  consumes:\n  - type: http\n    namespace: salesforce-rest\n    baseUri: https://{SALESFORCE_INSTANCE}.salesforce.com\n    description: Salesforce REST API for CRM data access and manipulation\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n    - name: api-versions\n\
  \      path: /services/data\n      description: Available API versions\n      operations:\n      - name: list-api-versions\n        method: GET\n        description: List all available Salesforce REST API versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sobjects\n      path: /services/data/v60.0/sobjects\n      description: Salesforce sObject type list\n      operations:\n      - name: list-sobjects\n        method: GET\n        description: List all sObjects available in the org\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sobject-records\n      path: /services/data/v60.0/sobjects/{sObjectName}/{id}\n      description: CRUD operations on individual sObject records\n      operations:\n      - name: get-record\n        method: GET\n        description: Get a specific sObject record by ID\n     \
  \   inputParameters:\n        - name: sObjectName\n          in: path\n          type: string\n          required: true\n          description: API name of the sObject (e.g., Account, Contact)\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: 18-character Salesforce record ID\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-record\n        method: PATCH\n        description: Update one or more fields on a record\n        inputParameters:\n        - name: sObjectName\n          in: path\n          type: string\n          required: true\n          description: API name of the sObject\n        - name: id\n          in: path\n          type: string\n          required: true\n\
  \          description: Salesforce record ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-record\n        method: DELETE\n        description: Delete a Salesforce record (moves to recycle bin)\n        inputParameters:\n        - name: sObjectName\n          in: path\n          type: string\n          required: true\n          description: API name of the sObject\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Salesforce record ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sobject-create\n      path: /services/data/v60.0/sobjects/{sObjectName}\n      description: Create new sObject records\n      operations:\n      - name: create-record\n        method: POST\n        description: Create a new sObject record\n        inputParameters:\n\
  \        - name: sObjectName\n          in: path\n          type: string\n          required: true\n          description: API name of the sObject\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.Name}}'\n    - name: query\n      path: /services/data/v60.0/query\n      description: SOQL query execution\n      operations:\n      - name: execute-query\n        method: GET\n        description: Execute a SOQL query and return matching records\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: SOQL query string (e.g., SELECT Id, Name FROM Account LIMIT 200)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query-all\n      path: /services/data/v60.0/queryAll\n\
  \      description: SOQL query including deleted records\n      operations:\n      - name: execute-query-all\n        method: GET\n        description: Execute a SOQL query including soft-deleted records\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: SOQL query string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /services/data/v60.0/search\n      description: SOSL cross-object search\n      operations:\n      - name: execute-search\n        method: GET\n        description: Execute a SOSL search across multiple sObject types\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: SOSL search string (e.g., FIND {Joe Smith} IN ALL FIELDS RETURNING Account, Contact)\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: describe\n      path: /services/data/v60.0/sobjects/{sObjectName}/describe\n      description: sObject field metadata\n      operations:\n      - name: describe-sobject\n        method: GET\n        description: Get full field-level describe for a Salesforce sObject type\n        inputParameters:\n        - name: sObjectName\n          in: path\n          type: string\n          required: true\n          description: API name of the sObject\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: limits\n      path: /services/data/v60.0/limits\n      description: Org API and storage limits\n      operations:\n      - name: get-org-limits\n        method: GET\n        description: Get current org limits including API call usage\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: composite-batch\n      path: /services/data/v60.0/composite/batch\n      description: Composite batch requests\n      operations:\n      - name: execute-composite-batch\n        method: POST\n        description: Execute up to 25 subrequests in a single API call\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            batchRequests: '{{tools.batchRequests}}'\n            haltOnError: '{{tools.haltOnError}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: crm-data-management-api\n    description: Unified REST API for Salesforce CRM data management workflows.\n    resources:\n    - path: /v1/records/{sObjectName}\n      name: records-by-type\n      description: Create new records by sObject type\n      operations:\n      - method: POST\n        name: create-record\n        description:\
  \ Create a new Salesforce record\n        call: salesforce-rest.create-record\n        with:\n          sObjectName: rest.sObjectName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/records/{sObjectName}/{id}\n      name: record-by-id\n      description: Read, update, and delete individual records\n      operations:\n      - method: GET\n        name: get-record\n        description: Get a Salesforce record by sObject type and ID\n        call: salesforce-rest.get-record\n        with:\n          sObjectName: rest.sObjectName\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-record\n        description: Update fields on a Salesforce record\n        call: salesforce-rest.update-record\n        with:\n          sObjectName: rest.sObjectName\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n\
  \        name: delete-record\n        description: Delete a Salesforce record\n        call: salesforce-rest.delete-record\n        with:\n          sObjectName: rest.sObjectName\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/query\n      name: soql-query\n      description: SOQL query execution\n      operations:\n      - method: GET\n        name: execute-query\n        description: Execute a SOQL query\n        call: salesforce-rest.execute-query\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: sosl-search\n      description: SOSL cross-object search\n      operations:\n      - method: GET\n        name: execute-search\n        description: Execute a SOSL search across multiple object types\n        call: salesforce-rest.execute-search\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/metadata/{sObjectName}\n      name: object-metadata\n      description: sObject field metadata\n      operations:\n      - method: GET\n        name: describe-sobject\n        description: Get field definitions for a Salesforce object type\n        call: salesforce-rest.describe-sobject\n        with:\n          sObjectName: rest.sObjectName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/limits\n      name: org-limits\n      description: Org API usage limits\n      operations:\n      - method: GET\n        name: get-org-limits\n        description: Get current Salesforce org limits and API usage\n        call: salesforce-rest.get-org-limits\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: crm-data-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Salesforce CRM data management.\n    tools:\n    - name:\
  \ query-records\n      description: Query Salesforce records using SOQL (e.g., SELECT Id, Name FROM Account WHERE Industry = 'Technology')\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: salesforce-rest.execute-query\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-records\n      description: Search across multiple Salesforce object types using SOSL full-text search\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: salesforce-rest.execute-search\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-record\n      description: Retrieve a specific Salesforce CRM record by object type and ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-rest.get-record\n      with:\n        sObjectName: tools.sObjectName\n    \
  \    id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-record\n      description: Create a new Salesforce CRM record (Account, Contact, Lead, Opportunity, Case)\n      hints:\n        readOnly: false\n      call: salesforce-rest.create-record\n      with:\n        sObjectName: tools.sObjectName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-record\n      description: Update fields on an existing Salesforce CRM record\n      hints:\n        readOnly: false\n        idempotent: true\n      call: salesforce-rest.update-record\n      with:\n        sObjectName: tools.sObjectName\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-record\n      description: Delete a Salesforce CRM record (moves to recycle bin, recoverable)\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: salesforce-rest.delete-record\n\
  \      with:\n        sObjectName: tools.sObjectName\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-field-metadata\n      description: Get field definitions and schema metadata for a Salesforce object type\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-rest.describe-sobject\n      with:\n        sObjectName: tools.sObjectName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-api-limits\n      description: Check current Salesforce org API call limits and remaining usage\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-rest.get-org-limits\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
