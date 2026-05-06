---
categories:
- identity-access
consumed_apis: []
description: Unified capability for Salesforce platform administration workflows combining the platform API and UI API for identity management, OAuth administration, metadata exploration, and application configuration. Used by Salesforce admins and platform engineers.
layout: capability
name: Salesforce Platform Administration
operations:
- description: Get the authenticated user's profile information.
  method: GET
  name: get-user-info
  path: /v1/user-info
- description: List available Salesforce REST API versions.
  method: GET
  name: list-api-versions
  path: /v1/api-versions
- description: Get current API limit usage and quotas.
  method: GET
  name: get-org-limits
  path: /v1/limits
- description: Get the app switcher menu items.
  method: GET
  name: get-app-switcher-menu
  path: /v1/app-menu
- description: List all SObject types in the org.
  method: GET
  name: list-sobjects
  path: /v1/sobjects
- description: Get full metadata for an SObject type.
  method: GET
  name: full-describe-sobject
  path: /v1/sobjects/{sobjectType}/describe
- description: Get UI-ready metadata for an object.
  method: GET
  name: get-object-info
  path: /v1/object-info/{objectApiName}
- description: Get picklist values for all picklist fields on an object.
  method: GET
  name: get-picklist-values
  path: /v1/picklist-values/{objectApiName}/{recordTypeId}
personas: []
provider_name: Salesforce
provider_slug: salesforce
search_terms:
- get the authenticated user's profile information.
- get org limits
- get the app switcher menu items.
- sales
- sobject type listing.
- list all sobject types available in the salesforce org.
- identity
- get app switcher menu
- search lookup field records for typeahead.
- full sobject metadata.
- analytics
- list available salesforce rest api versions.
- list api versions
- marketing
- get the app switcher menu items available to the current user.
- get full metadata for a salesforce sobject type including all fields.
- get picklist values for all picklist fields on an object.
- cloud
- list sobjects
- oauth
- enterprise
- full describe sobject
- picklist value retrieval.
- get ui-ready metadata about a salesforce object.
- ai
- commerce
- get full metadata for an sobject type.
- get user info
- org api limits.
- crm
- get picklist values for all picklist fields on an object for a given record type.
- platform administration
- salesforce api version information.
- ui-ready object metadata.
- get list views for a salesforce object.
- get current api limit usage and remaining quotas for the org.
- get lookup records
- platform
- get current api limit usage and quotas.
- authenticated user information.
- app switcher menu items.
- list all sobject types in the org.
- get object info
- customer service
- get list views
- metadata
- get ui-ready metadata for an object.
- get picklist values
- salesforce
slug: platform-administration
source_filename: platform-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce Platform Administration\n  description: Unified capability for Salesforce platform administration workflows combining the platform API and UI API for\n    identity management, OAuth administration, metadata exploration, and application configuration. Used by Salesforce admins\n    and platform engineers.\n  tags:\n  - Salesforce\n  - Platform Administration\n  - Identity\n  - OAuth\n  - Metadata\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n    SALESFORCE_CLIENT_ID: SALESFORCE_CLIENT_ID\n    SALESFORCE_CLIENT_SECRET: SALESFORCE_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: salesforce-platform\n    baseUri: https://login.salesforce.com\n    description: Salesforce platform API for OAuth, identity, bulk operations, composite requests, SObjects, files, credentials,\n      Chatter, expression sets, and platform\
  \ events.\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n    - name: authentication\n      path: /services/auth/headless\n      description: Headless authentication and registration operations.\n      operations:\n      - name: registration-initialize\n        method: POST\n        path: /init/registration\n        description: Initialize headless registration flow.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userdata: '{{tools.userdata}}'\n      - name: registration-authorize\n        method: POST\n        path: /authorize/registration\n        description: Authorize headless registration.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data:\n            identifier: '{{tools.identifier}}'\n    - name: oauth\n      path: /services/oauth2\n      description: OAuth 2.0 token and user info operations.\n      operations:\n      - name: get-user-info\n        method: GET\n        path: /userinfo\n        description: Get the authenticated user's profile information.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revoke-token\n        method: POST\n        path: /revoke\n        description: Revoke an OAuth token.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            token: '{{tools.token}}'\n    - name: sobjects\n      path: /services/data\n      description: SObject CRUD operations.\n      operations:\n\
  \      - name: describe-global\n        method: GET\n        path: /v63.0/sobjects\n        description: List all SObject types available in the org.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: sobject-describe\n        method: GET\n        path: /v63.0/sobjects/{sobjectType}/describe\n        description: Get full metadata for an SObject type.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: sobject-create\n        method: POST\n        path: /v63.0/sobjects/{sobjectType}\n        description: Create a new SObject record.\n        inputParameters:\n        - name: sobjectType\n          in: path\n\
  \          type: string\n          required: true\n          description: The SObject type API name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n      - name: sobject-get\n        method: GET\n        path: /v63.0/sobjects/{sobjectType}/{id}\n        description: Get an SObject record by ID.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The record ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: sobject-update\n        method: PATCH\n        path: /v63.0/sobjects/{sobjectType}/{id}\n\
  \        description: Update an SObject record.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The record ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n      - name: sobject-delete\n        method: DELETE\n        path: /v63.0/sobjects/{sobjectType}/{id}\n        description: Delete an SObject record.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        - name: id\n          in: path\n          type: string\n          required: true\n      \
  \    description: The record ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: composite\n      path: /services/data/v63.0/composite\n      description: Composite and batch request operations.\n      operations:\n      - name: execute-composite\n        method: POST\n        path: /\n        description: Execute a composite request with dependent subrequests.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            compositeRequest: '{{tools.composite_request}}'\n      - name: execute-batch\n        method: POST\n        path: /batch\n        description: Execute a batch of independent requests.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            batchRequests: '{{tools.batch_requests}}'\n    - name: search\n      path: /services/data/v63.0\n      description: SOQL query and SOSL search operations.\n      operations:\n      - name: execute-search\n        method: GET\n        path: /search\n        description: Execute a SOSL search.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: The SOSL search string.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: salesforce-rest\n    baseUri: https://{instance}.salesforce.com/services/data/v63.0\n    description: Salesforce REST API for SObject CRUD, SOQL queries, SOSL searches, composite requests, and org limits.\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n\
  \    - name: versions\n      path: /\n      description: API version information.\n      operations:\n      - name: list-api-versions\n        method: GET\n        path: /\n        description: List available Salesforce REST API versions.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sobjects\n      path: /sobjects\n      description: SObject CRUD and metadata operations.\n      operations:\n      - name: list-sobjects\n        method: GET\n        path: /\n        description: List all SObject types available in the org.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-sobject\n        method: GET\n        path: /{sobjectType}\n        description: Get basic metadata for an SObject type.\n        inputParameters:\n        - name: sobjectType\n\
  \          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: full-describe-sobject\n        method: GET\n        path: /{sobjectType}/describe\n        description: Get full metadata for an SObject type including all fields.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-record\n        method: POST\n        path: /{sobjectType}\n        description: Create a new SObject record.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description:\
  \ The SObject type API name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n      - name: get-record\n        method: GET\n        path: /{sobjectType}/{id}\n        description: Get an SObject record by ID.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The 18-character record ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-record\n        method: PATCH\n        path: /{sobjectType}/{id}\n        description: Update an SObject record.\n        inputParameters:\n        -\
  \ name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The 18-character record ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n      - name: delete-record\n        method: DELETE\n        path: /{sobjectType}/{id}\n        description: Delete an SObject record.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The 18-character record ID.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-blob-field\n        method: GET\n        path: /{sobjectType}/{id}/{blobField}\n        description: Get binary content of a blob field on an SObject record.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The 18-character record ID.\n        - name: blobField\n          in: path\n          type: string\n          required: true\n          description: The blob field API name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query\n      path: /\n      description: SOQL query operations.\n      operations:\n      - name: execute-query\n        method: POST\n        path: /query\n\
  \        description: Execute a SOQL query.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            q: '{{tools.q}}'\n      - name: get-next-query-page\n        method: GET\n        path: /query/{queryId}\n        description: Get the next page of query results.\n        inputParameters:\n        - name: queryId\n          in: path\n          type: string\n          required: true\n          description: The query ID token from nextRecordsUrl.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: execute-query-all\n        method: POST\n        path: /queryAll\n        description: Execute a SOQL queryAll including deleted and archived records.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            q: '{{tools.q}}'\n    - name: search\n      path: /\n      description: SOSL search operations.\n      operations:\n      - name: execute-search\n        method: GET\n        path: /search\n        description: Execute a SOSL search across multiple objects.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: The SOSL search string.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: limits\n      path: /\n      description: Org limit operations.\n      operations:\n      - name: get-org-limits\n        method: GET\n        path: /limits\n        description: Get current API limit usage and quotas for the org.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: recent\n      path: /\n      description: Recently viewed records.\n      operations:\n      - name: get-recently-viewed-records\n        method: GET\n        path: /recent\n        description: Get recently viewed records for the current user.\n        inputParameters:\n        - name: recentlyViewedCount\n          in: query\n          type: integer\n          required: false\n          description: Number of recently viewed records to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: app-menu\n      path: /\n      description: App menu operations.\n      operations:\n      - name: get-app-switcher-menu\n        method: GET\n        path: /appMenu/AppSwitcher\n        description: Get the app switcher menu items.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: composite\n      path: /composite\n      description: Composite and batch request operations.\n      operations:\n      - name: execute-batch-request\n        method: POST\n        path: /batch\n        description: Execute a batch of up to 25 independent requests.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            batchRequests: '{{tools.batch_requests}}'\n      - name: execute-composite-request\n        method: POST\n        path: /\n        description: Execute a composite request with dependent subrequests.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            compositeRequest:\
  \ '{{tools.composite_request}}'\n      - name: collections-create\n        method: POST\n        path: /sobjects\n        description: Create up to 200 records in a single call.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            records: '{{tools.records}}'\n      - name: collections-update\n        method: PATCH\n        path: /sobjects\n        description: Update up to 200 records in a single call.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            records: '{{tools.records}}'\n      - name: collections-delete\n        method: DELETE\n        path: /sobjects\n        description: Delete up to 200 records in a single call.\n        inputParameters:\n\
  \        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of record IDs to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: collections-retrieve\n        method: GET\n        path: /sobjects/{sobjectType}\n        description: Retrieve up to 2000 records of the same type.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of record IDs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: salesforce-ui\n    baseUri: https://{instanceName}.salesforce.com/services/data/v59.0/ui-api\n\
  \    description: Salesforce UI API for records, object metadata, picklist values, list views, and lookups.\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n    - name: records\n      path: /records\n      description: Record CRUD operations with UI metadata.\n      operations:\n      - name: get-record\n        method: GET\n        path: /{recordId}\n        description: Get a record with field values formatted for UI display.\n        inputParameters:\n        - name: recordId\n          in: path\n          type: string\n          required: true\n          description: The 18-character Salesforce record ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of field API names.\n        - name: layoutTypes\n          in: query\n          type: string\n          required: false\n          description: Layout types (Full, Compact).\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-record\n        method: POST\n        path: /\n        description: Create a new Salesforce record.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            apiName: '{{tools.api_name}}'\n            fields: '{{tools.fields}}'\n      - name: update-record\n        method: PATCH\n        path: /{recordId}\n        description: Update fields on a Salesforce record.\n        inputParameters:\n        - name: recordId\n          in: path\n          type: string\n          required: true\n          description: The 18-character Salesforce record ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type:\
  \ json\n          data:\n            fields: '{{tools.fields}}'\n      - name: delete-record\n        method: DELETE\n        path: /{recordId}\n        description: Delete a Salesforce record.\n        inputParameters:\n        - name: recordId\n          in: path\n          type: string\n          required: true\n          description: The 18-character Salesforce record ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: object-info\n      path: /object-info\n      description: Object metadata operations.\n      operations:\n      - name: get-object-info\n        method: GET\n        path: /{objectApiName}\n        description: Get metadata about a Salesforce object including fields, types, and permissions.\n        inputParameters:\n        - name: objectApiName\n          in: path\n          type: string\n          required: true\n          description: The object API name.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-picklist-values\n        method: GET\n        path: /{objectApiName}/picklist-values/{recordTypeId}\n        description: Get picklist values for all picklist fields on an object.\n        inputParameters:\n        - name: objectApiName\n          in: path\n          type: string\n          required: true\n          description: The object API name.\n        - name: recordTypeId\n          in: path\n          type: string\n          required: true\n          description: The record type ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-views\n      path: /list-ui\n      description: List view operations.\n      operations:\n      - name: get-lists-by-object\n        method: GET\n        path: /{objectApiName}\n        description: Get list views for an object.\n      \
  \  inputParameters:\n        - name: objectApiName\n          in: path\n          type: string\n          required: true\n          description: The object API name.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-list-view\n        method: GET\n        path: /{objectApiName}/{listViewApiName}\n        description: Get a specific list view.\n        inputParameters:\n        - name: objectApiName\n          in: path\n          type: string\n          required: true\n          description: The object API name.\n        - name: listViewApiName\n          in: path\n          type: string\n          required: true\n          description: The list view API name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n    - name: lookups\n      path: /lookups\n      description: Lookup field search operations.\n      operations:\n      - name: get-lookup-records\n        method: GET\n        path: /{objectApiName}/{fieldApiName}\n        description: Search lookup field records for typeahead.\n        inputParameters:\n        - name: objectApiName\n          in: path\n          type: string\n          required: true\n          description: The object API name.\n        - name: fieldApiName\n          in: path\n          type: string\n          required: true\n          description: The lookup field API name.\n        - name: searchTerm\n          in: query\n          type: string\n          required: true\n          description: The search text.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: platform-administration-api\n\
  \    description: Unified REST API for Salesforce platform administration.\n    resources:\n    - path: /v1/user-info\n      name: user-info\n      description: Authenticated user information.\n      operations:\n      - method: GET\n        name: get-user-info\n        description: Get the authenticated user's profile information.\n        call: salesforce-platform.get-user-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-versions\n      name: api-versions\n      description: Salesforce API version information.\n      operations:\n      - method: GET\n        name: list-api-versions\n        description: List available Salesforce REST API versions.\n        call: salesforce-rest.list-api-versions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/limits\n      name: limits\n      description: Org API limits.\n      operations:\n      - method: GET\n        name: get-org-limits\n        description:\
  \ Get current API limit usage and quotas.\n        call: salesforce-rest.get-org-limits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/app-menu\n      name: app-menu\n      description: App switcher menu items.\n      operations:\n      - method: GET\n        name: get-app-switcher-menu\n        description: Get the app switcher menu items.\n        call: salesforce-rest.get-app-switcher-menu\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sobjects\n      name: sobjects\n      description: SObject type listing.\n      operations:\n      - method: GET\n        name: list-sobjects\n        description: List all SObject types in the org.\n        call: salesforce-rest.list-sobjects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sobjects/{sobjectType}/describe\n      name: sobject-describe\n      description: Full SObject metadata.\n      operations:\n      - method:\
  \ GET\n        name: full-describe-sobject\n        description: Get full metadata for an SObject type.\n        call: salesforce-rest.full-describe-sobject\n        with:\n          sobjectType: rest.sobjectType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/object-info/{objectApiName}\n      name: object-info\n      description: UI-ready object metadata.\n      operations:\n      - method: GET\n        name: get-object-info\n        description: Get UI-ready metadata for an object.\n        call: salesforce-ui.get-object-info\n        with:\n          objectApiName: rest.objectApiName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/picklist-values/{objectApiName}/{recordTypeId}\n      name: picklist-values\n      description: Picklist value retrieval.\n      operations:\n      - method: GET\n        name: get-picklist-values\n        description: Get picklist values for all picklist fields on an object.\n\
  \        call: salesforce-ui.get-picklist-values\n        with:\n          objectApiName: rest.objectApiName\n          recordTypeId: rest.recordTypeId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: platform-administration-mcp\n    transport: http\n    description: MCP server for AI-assisted Salesforce platform administration.\n    tools:\n    - name: get-user-info\n      description: Get the authenticated user's profile information.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-platform.get-user-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-versions\n      description: List available Salesforce REST API versions.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-rest.list-api-versions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-org-limits\n    \
  \  description: Get current API limit usage and remaining quotas for the org.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-rest.get-org-limits\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-app-switcher-menu\n      description: Get the app switcher menu items available to the current user.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-rest.get-app-switcher-menu\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sobjects\n      description: List all SObject types available in the Salesforce org.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-rest.list-sobjects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: full-describe-sobject\n      description: Get full metadata for a Salesforce SObject type including all fields.\n      hints:\n        readOnly: true\n  \
  \      idempotent: true\n      call: salesforce-rest.full-describe-sobject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-object-info\n      description: Get UI-ready metadata about a Salesforce object.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-ui.get-object-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-picklist-values\n      description: Get picklist values for all picklist fields on an object for a given record type.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-ui.get-picklist-values\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-list-views\n      description: Get list views for a Salesforce object.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-ui.get-lists-by-object\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: get-lookup-records\n      description: Search lookup field records for typeahead.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-ui.get-lookup-records\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce/refs/heads/main/capabilities/platform-administration.yaml
tags:
- Salesforce
- Platform Administration
- Identity
- OAuth
- Metadata
tools:
- description: Get the authenticated user's profile information.
  hints:
    idempotent: true
    readOnly: true
  name: get-user-info
- description: List available Salesforce REST API versions.
  hints:
    idempotent: true
    readOnly: true
  name: list-api-versions
- description: Get current API limit usage and remaining quotas for the org.
  hints:
    idempotent: true
    readOnly: true
  name: get-org-limits
- description: Get the app switcher menu items available to the current user.
  hints:
    idempotent: true
    readOnly: true
  name: get-app-switcher-menu
- description: List all SObject types available in the Salesforce org.
  hints:
    idempotent: true
    readOnly: true
  name: list-sobjects
- description: Get full metadata for a Salesforce SObject type including all fields.
  hints:
    idempotent: true
    readOnly: true
  name: full-describe-sobject
- description: Get UI-ready metadata about a Salesforce object.
  hints:
    idempotent: true
    readOnly: true
  name: get-object-info
- description: Get picklist values for all picklist fields on an object for a given record type.
  hints:
    idempotent: true
    readOnly: true
  name: get-picklist-values
- description: Get list views for a Salesforce object.
  hints:
    idempotent: true
    readOnly: true
  name: get-list-views
- description: Search lookup field records for typeahead.
  hints:
    idempotent: true
    readOnly: true
  name: get-lookup-records
---
