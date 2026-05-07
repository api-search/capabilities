---
categories: []
consumed_apis: []
description: Manage applications, clients, monitor analytics, usage, activity, and data exports on the Axway Amplify platform.
layout: capability
name: Axway Application and Analytics
operations:
- description: Axway Create App
  method: POST
  name: app-create
  path: /v1/app
- description: Axway Find Apps
  method: GET
  name: app-find
  path: /v1/app
- description: Axway Find App
  method: GET
  name: app-findOne
  path: /v1/app
- description: Axway Remove App
  method: DELETE
  name: app-remove
  path: /v1/app
- description: Axway Update App
  method: PUT
  name: app-update
  path: /v1/app
- description: Axway Add Service Account
  method: POST
  name: client-create
  path: /v1/client
- description: Axway Get Service Accounts
  method: GET
  name: client-find
  path: /v1/client
- description: Axway Get Service Account JSON Representation
  method: GET
  name: client-download
  path: /v1/client
- description: Axway Get a Service Account
  method: GET
  name: client-findOne
  path: /v1/client
- description: Axway Delete Service Account
  method: DELETE
  name: client-remove
  path: /v1/client
- description: Axway Update Service Account
  method: PUT
  name: client-update
  path: /v1/client
- description: Axway Analytics Query Using Lexus
  method: GET
  name: analytics-query
  path: /v1/analytics
- description: Axway Report an Error
  method: POST
  name: analytics-error
  path: /v1/analytics
- description: Axway Create a Custom Query
  method: POST
  name: analytics-customCreate
  path: /v1/analytics
- description: Axway Find Custom Queries
  method: GET
  name: analytics-customFind
  path: /v1/analytics
- description: Axway Delete a Custom Query
  method: DELETE
  name: analytics-customRemove
  path: /v1/analytics
- description: Axway Update a Custom Query
  method: PUT
  name: analytics-customUpdate
  path: /v1/analytics
- description: Axway Get Custom Query
  method: GET
  name: analytics-customFindOne
  path: /v1/analytics
- description: Axway Uploads an Automatic Usage Report
  method: POST
  name: usage-uploadAutomatic
  path: /v1/usage
- description: Axway Fetches Usage Reports
  method: GET
  name: usage-find
  path: /v1/usage
- description: Axway Uploads a Usage Report
  method: POST
  name: usage-upload
  path: /v1/usage
- description: Axway Downloads a Usage Report
  method: GET
  name: usage-download
  path: /v1/usage
- description: Axway Organization Usage
  method: GET
  name: org-findUsage
  path: /v1/usage
- description: Axway Get Activity Event Names
  method: GET
  name: activity-findEvents
  path: /v1/activity
- description: Axway Get Activity
  method: GET
  name: activity-find
  path: /v1/activity
- description: Axway Export Data
  method: POST
  name: export-create
  path: /v1/export
- description: Axway Find Exports
  method: GET
  name: export-findAll
  path: /v1/export
- description: Axway Retrieve a Download Url
  method: GET
  name: export-download
  path: /v1/export
- description: Axway Remove Export
  method: DELETE
  name: export-remove
  path: /v1/export
- description: Axway Send Events
  method: POST
  name: analytics-create
  path: /v1/telemetry
- description: Axway Set Metadata by ID
  method: PUT
  name: aca-setMetadata
  path: /v1/aca
- description: Axway Find Crash Record by ID
  method: GET
  name: aca-findOne
  path: /v1/aca
personas: []
provider_name: Axway
provider_slug: axway
search_terms:
- axway delete service account
- axway export data
- axway retrieve a download url
- api management
- axway find crash record by id
- analytics customUpdate
- axway find custom queries
- axway analytics query using lexus
- export findAll
- usage download
- app remove
- app create
- client find
- aca setMetadata
- app findOne
- usage uploadAutomatic
- export create
- axway
- axway update a custom query
- axway send events
- activity findEvents
- client create
- axway get activity
- analytics query
- axway uploads an automatic usage report
- activity operations
- analytics customCreate
- client download
- axway downloads a usage report
- enterprise
- usage find
- axway set metadata by id
- security
- app find
- axway uploads a usage report
- axway report an error
- axway get custom query
- axway get service account json representation
- monitoring
- axway delete a custom query
- analytics customRemove
- client operations
- analytics customFindOne
- axway organization usage
- integration
- client findOne
- axway create a custom query
- export download
- app update
- axway update app
- activity find
- client remove
- axway get activity event names
- axway find apps
- analytics create
- analytics
- org findUsage
- app operations
- axway update service account
- axway find exports
- aca operations
- usage upload
- analytics operations
- telemetry operations
- applications
- axway add service account
- analytics customFind
- analytics error
- axway remove export
- usage operations
- axway remove app
- axway get a service account
- client update
- export operations
- export remove
- axway create app
- axway fetches usage reports
- axway find app
- axway get service accounts
- aca findOne
slug: application-and-analytics
source_filename: application-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Axway Application and Analytics\n  description: Manage applications, clients, monitor analytics, usage, activity, and data exports on the Axway Amplify platform.\n  tags:\n  - Axway\n  - Applications\n  - Analytics\n  - Monitoring\n  created: '2026-04-21'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AXWAY_BEARER_TOKEN: AXWAY_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: amplify-platform\n    baseUri: https://platform.axway.com/api/v1\n    description: Axway Amplify Platform API v1\n    authentication:\n      type: bearer\n      token: '{{env.AXWAY_BEARER_TOKEN}}'\n    resources:\n    - name: aca\n      path: /aca\n      description: Aca management operations\n      operations:\n      - name: aca-setMetadata\n        method: PUT\n        description: Axway Set Metadata by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: aca_id\n          in: path\n          type: string\n          required: true\n          description: aca_id parameter\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name parameter\n        body:\n          type: json\n          data: {}\n      - name: aca-findOne\n        method: GET\n        description: Axway Find Crash Record by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n\
  \        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: aca_id\n          in: path\n          type: string\n          required: true\n          description: aca_id parameter\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n    - name: activity\n      path: /activity\n      description: Activity management operations\n      operations:\n      - name: activity-findEvents\n        method: GET\n        description: Axway Get Activity Event Names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n \
  \         description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: authorization\n          in: header\n          type: string\n          required: false\n          description: authorization parameter\n      - name: activity-find\n        method: GET\n        description: Axway Get Activity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_guid\n          in: query\n          type: string\n          required: false\n          description: app_guid parameter\n        - name: contexts\n          in:\
  \ query\n          type: array\n          required: false\n          description: contexts parameter\n        - name: data\n          in: query\n          type: boolean\n          required: false\n          description: data parameter\n        - name: enrich\n          in: query\n          type: boolean\n          required: false\n          description: enrich parameter\n        - name: exclude_contexts\n          in: query\n          type: array\n          required: false\n          description: exclude_contexts parameter\n        - name: from\n          in: query\n          type: number\n          required: false\n          description: from parameter\n        - name: org_id\n          in: query\n          type: string\n          required: false\n          description: org_id parameter\n        - name: redact\n          in: query\n          type: boolean\n          required: false\n          description: redact parameter\n        - name: sort\n          in: query\n          type: number\n\
  \          required: false\n          description: sort parameter\n        - name: term\n          in: query\n          type: string\n          required: false\n          description: term parameter\n        - name: to\n          in: query\n          type: number\n          required: false\n          description: to parameter\n        - name: user_guid\n          in: query\n          type: string\n          required: false\n          description: user_guid parameter\n        - name: user_messages\n          in: query\n          type: boolean\n          required: false\n          description: user_messages parameter\n        - name: limit\n          in: query\n          type: number\n          required: false\n          description: limit parameter\n        - name: page\n          in: query\n          type: number\n          required: false\n          description: page parameter\n        - name: skip\n          in: query\n          type: number\n          required: false\n          description:\
  \ skip parameter\n    - name: analytics\n      path: /analytics\n      description: Analytics management operations\n      operations:\n      - name: analytics-query\n        method: GET\n        description: Axway Analytics Query Using Lexus\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: apim_tier\n          in: query\n          type: string\n          required: false\n          description: apim_tier parameter\n        - name: app_guid\n          in: query\n          type: string\n          required: false\n          description: app_guid parameter\n        - name: clients\n          in: query\n          type: array\n          required: false\n          description: clients parameter\n        - name: cross_org\n          in: query\n          type: boolean\n          required: false\n          description: cross_org parameter\n        - name: custom_query\n      \
  \    in: query\n          type: string\n          required: false\n          description: custom_query parameter\n        - name: debug\n          in: query\n          type: boolean\n          required: false\n          description: debug parameter\n        - name: endpoint\n          in: query\n          type: string\n          required: false\n          description: endpoint parameter\n        - name: events\n          in: query\n          type: string\n          required: false\n          description: events parameter\n        - name: field\n          in: query\n          type: string\n          required: false\n          description: field parameter\n        - name: from\n          in: query\n          type: number\n          required: false\n          description: from parameter\n        - name: granularity\n          in: query\n          type: string\n          required: false\n          description: granularity parameter\n        - name: group_by\n          in: query\n         \
  \ type: string\n          required: false\n          description: group_by parameter\n        - name: grquantity\n          in: query\n          type: number\n          required: false\n          description: grquantity parameter\n        - name: include_query\n          in: query\n          type: string\n          required: false\n          description: include_query parameter\n        - name: org_id\n          in: query\n          type: string\n          required: false\n          description: org_id parameter\n        - name: platform\n          in: query\n          type: string\n          required: false\n          description: platform parameter\n        - name: post_process\n          in: query\n          type: boolean\n          required: false\n          description: post_process parameter\n        - name: prefix\n          in: query\n          type: string\n          required: false\n          description: prefix parameter\n        - name: preprocessor\n          in: query\n \
  \         type: string\n          required: false\n          description: preprocessor parameter\n        - name: processor\n          in: query\n          type: string\n          required: false\n          description: processor parameter\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: query parameter\n        - name: region\n          in: query\n          type: string\n          required: false\n          description: region parameter\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: status parameter\n        - name: to\n          in: query\n          type: number\n          required: false\n          description: to parameter\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: type parameter\n        - name: username\n          in: query\n          type: string\n          required:\
  \ false\n          description: username parameter\n      - name: analytics-error\n        method: POST\n        description: Axway Report an Error\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: analytics-customCreate\n        method: POST\n        description: Axway Create a Custom Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n       \
  \ body:\n          type: json\n          data: {}\n      - name: analytics-customFind\n        method: GET\n        description: Axway Find Custom Queries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n      - name: analytics-customRemove\n        method: DELETE\n        description: Axway Delete a Custom Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n         \
  \ in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: query_id\n          in: path\n          type: string\n          required: true\n          description: query_id parameter\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n      - name: analytics-customUpdate\n        method: PUT\n        description: Axway Update a Custom Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n         \
  \ description: ' parameter'\n        - name: query_id\n          in: path\n          type: string\n          required: true\n          description: query_id parameter\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n        body:\n          type: json\n          data: {}\n      - name: analytics-customFindOne\n        method: GET\n        description: Axway Get Custom Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: query_id\n          in: path\n          type: string\n          required: true\n          description: query_id\
  \ parameter\n        - name: org_id\n          in: query\n          type: string\n          required: false\n          description: org_id parameter\n    - name: app\n      path: /app\n      description: App management operations\n      operations:\n      - name: app-create\n        method: POST\n        description: Axway Create App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data: {}\n      - name: app-find\n        method: GET\n        description: Axway Find Apps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n        inputParameters:\n        - name: fields\n          in: query\n          type: array\n          required: false\n          description: A list of fields to include in the response.\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n        - name: provider_guid\n          in: query\n          type: string\n          required: false\n          description: provider_guid parameter\n        - name: subtype\n          in: query\n          type: string\n          required: false\n          description: subtype parameter\n        - name: type\n          in: query\n          type: string\n          required: false\n          description:\
  \ type parameter\n      - name: app-findOne\n        method: GET\n        description: Axway Find App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n      - name: app-remove\n        method: DELETE\n        description: Axway Remove App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n      - name: app-update\n        method: PUT\n        description: Axway Update App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: app_id parameter\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n        body:\n          type: json\n          data: {}\n    - name: auth\n      path: /auth\n      description: Auth management operations\n      operations:\n      - name: auth-validatePassword\n        method: POST\n        description: Axway Validates a User Password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: x-auth-password\n          in: header\n          type: string\n          required: true\n          description: x-auth-password parameter\n      - name: auth-acceptTerms\n        method: PUT\n        description: Axway Accept Terms & Conditions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: grant\n          in: query\n          type: string\n          required: false\n          description: grant parameter\n      - name: auth-sessionSwitchOrg\n        method: POST\n        description: Axway Switch Signed-in Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data:\
  \ {}\n      - name: auth-signup\n        method: POST\n        description: Axway Sign Up\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-findPasswordPolicy\n        method: GET\n        description: Axway Get Effective Password Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: provider_guid\n          in: query\n          type: string\n          required: false\n          description: provider_guid parameter\n        - name: user_guid\n          in: query\n\
  \          type: string\n          required: false\n          description: user_guid parameter\n      - name: auth-onboarding\n        method: PUT\n        description: Axway Onboarding Capture\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: grant\n          in: query\n          type: string\n          required: false\n          description: grant parameter\n        body:\n          type: json\n          data: {}\n      - name: auth-mfaVerify\n        method: POST\n        description: Axway Verify an Authorization Code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data: {}\n      - name: auth-mfaSend\n        method: POST\n        description: Axway Send an Authorization Code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data: {}\n      - name: auth-logout\n        method: GET\n      \
  \  description: Axway Sign-out\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: msg\n          in: query\n          type: string\n          required: false\n          description: msg parameter\n        - name: redirect\n          in: query\n          type: string\n          required: false\n          description: redirect parameter\n      - name: auth-login\n        method: POST\n        description: Axway Sign-in\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n      \
  \    type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: grant\n          in: query\n          type: string\n          required: false\n          description: grant parameter\n        body:\n          type: json\n          data: {}\n      - name: auth-unimpersonate\n        method: DELETE\n        description: Axway Unimpersonate User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n      - name: auth-forgot\n        method: POST\n        description: Axway Send\
  \ Forgot Password Link\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-sessionFind\n        method: GET\n        description: Axway Retrieves the Current Session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: from parameter\n      - name: auth-deviceauthResend\n        method: POST\n        description: Axway Resends Device Authorization\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n      - name: auth-deviceauthValidate\n        method: POST\n        description: Axway Validates a New Sessions Device Authorization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: grant\n          in: query\n          type: string\n\
  \          required: false\n          description: grant parameter\n        body:\n          type: json\n          data: {}\n      - name: auth-sessionCheck\n        method: GET\n        description: Axway Checks if the User is Signed in\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n      - name: auth-deviceauthConfirm\n        method: POST\n        description: Axway Confirm Authenticator App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-deviceauthCreate\n        method:\
  \ GET\n        description: Axway Initiate Authenticator App Setup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n      - name: auth-deviceauthRemoveApp\n        method: DELETE\n        description: Axway Remove Authenticator App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: x-auth-password\n          in: header\n          type: string\n          required: true\n          description: x-auth-password parameter\n      - name: auth-activationSignup\n        method: POST\n        description: Axway Activate a\
  \ Signup User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-activationResend\n        method: POST\n        description: Axway Resend Activation Link\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-activationForgot\n        method: POST\n        description: Axway Reset User Password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-activationConfirm\n        method: POST\n        description: Axway Activate a User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-activationUnlock\n        method: PUT\n        description: Axway Unlock Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: activation_id\n          in: path\n          type: string\n          required: true\n          description: activation_id parameter\n      - name: auth-revokeOauth\n        method: DELETE\n        description: Axway Revoke OAuth Service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n      \
  \  - name: service\n          in: path\n          type: string\n          required: true\n          description: service parameter\n      - name: auth-deviceauthFind\n        method: GET\n        description: Axway Retrieve Authorized Devices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: user_id parameter\n      - name: auth-deviceauthRemove\n        method: DELETE\n        description: Axway Remove Authorized Device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        inputParameters:\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: device_id parameter\n      - name: auth-activationFind\n        method: GET\n        description: Axway Find Activation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: activation_id\n          in: path\n          type: string\n          required: true\n          description: activation_id parameter\n    - name: client\n      path: /client\n      description: Client management operations\n      operations:\n      - name: client-create\n   \
  \     method: POST\n        description: Axway Add Service Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data: {}\n      - name: client-find\n        method: GET\n        description: Axway Get Service Accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required:\
  \ false\n          desc\n\n# --- truncated at 32 KB (125 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/axway/refs/heads/main/capabilities/application-and-analytics.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/axway/refs/heads/main/capabilities/application-and-analytics.yaml
tags:
- Axway
- Applications
- Analytics
- Monitoring
tools:
- description: Axway Create App
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: app-create
- description: Axway Find Apps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: app-find
- description: Axway Find App
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: app-findOne
- description: Axway Remove App
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: app-remove
- description: Axway Update App
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: app-update
- description: Axway Add Service Account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: client-create
- description: Axway Get Service Accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: client-find
- description: Axway Get Service Account JSON Representation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: client-download
- description: Axway Get a Service Account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: client-findOne
- description: Axway Delete Service Account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: client-remove
- description: Axway Update Service Account
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: client-update
- description: Axway Analytics Query Using Lexus
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: analytics-query
- description: Axway Report an Error
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: analytics-error
- description: Axway Create a Custom Query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: analytics-customCreate
- description: Axway Find Custom Queries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: analytics-customFind
- description: Axway Delete a Custom Query
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: analytics-customRemove
- description: Axway Update a Custom Query
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: analytics-customUpdate
- description: Axway Get Custom Query
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: analytics-customFindOne
- description: Axway Uploads an Automatic Usage Report
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: usage-uploadAutomatic
- description: Axway Fetches Usage Reports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: usage-find
- description: Axway Uploads a Usage Report
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: usage-upload
- description: Axway Downloads a Usage Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: usage-download
- description: Axway Organization Usage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-findUsage
- description: Axway Get Activity Event Names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: activity-findEvents
- description: Axway Get Activity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: activity-find
- description: Axway Export Data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: export-create
- description: Axway Find Exports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: export-findAll
- description: Axway Retrieve a Download Url
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: export-download
- description: Axway Remove Export
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: export-remove
- description: Axway Send Events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: analytics-create
- description: Axway Set Metadata by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: aca-setMetadata
- description: Axway Find Crash Record by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: aca-findOne
---
