---
categories: []
consumed_apis:
- amplify-platform
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
- axway fetches usage reports
- security
- axway downloads a usage report
- export operations
- export download
- axway export data
- analytics customFind
- axway get activity
- analytics query
- axway organization usage
- axway update a custom query
- activity operations
- client create
- analytics create
- client remove
- app remove
- axway find apps
- axway get activity event names
- axway find custom queries
- usage upload
- analytics error
- client findOne
- axway find exports
- app find
- axway set metadata by id
- app operations
- axway add service account
- axway find crash record by id
- axway retrieve a download url
- usage download
- axway get service account json representation
- analytics customUpdate
- axway report an error
- axway uploads an automatic usage report
- axway update app
- activity find
- aca findOne
- analytics
- client update
- axway
- axway remove app
- analytics customCreate
- org findUsage
- axway get a service account
- axway remove export
- aca setMetadata
- client operations
- axway get service accounts
- axway analytics query using lexus
- telemetry operations
- axway find app
- export create
- usage uploadAutomatic
- aca operations
- client find
- monitoring
- export remove
- axway delete a custom query
- usage find
- api management
- analytics customRemove
- integration
- axway uploads a usage report
- app update
- analytics operations
- axway update service account
- applications
- app findOne
- axway delete service account
- analytics customFindOne
- enterprise
- activity findEvents
- usage operations
- export findAll
- axway get custom query
- axway create a custom query
- app create
- client download
- axway send events
- axway create app
slug: application-and-analytics
source_filename: application-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Axway Application and Analytics\n  description: Manage applications, clients, monitor analytics, usage, activity, and data exports on the Axway Amplify platform.\n  tags:\n  - Axway\n  - Applications\n  - Analytics\n  - Monitoring\n  created: '2026-04-21'\n  modified: '2026-04-21'\nbinds:\n- namespace: env\n  keys:\n    AXWAY_BEARER_TOKEN: AXWAY_BEARER_TOKEN\ncapability:\n  consumes:\n  - import: amplify-platform\n    location: ./shared/amplify-platform.yaml\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: application-and-analytics-api\n    description: Unified REST API for manage applications, clients, monitor analytics, usage, activity, and data exports on the axway amplify platform.\n    resources:\n    - path: /v1/app\n      name: app\n      description: App operations\n      operations:\n      - method: POST\n        name: app-create\n        description: Axway Create App\n        call: amplify-platform.app-create\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: app-find\n        description: Axway Find Apps\n        call: amplify-platform.app-find\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: app-findOne\n        description: Axway Find App\n        call: amplify-platform.app-findOne\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: app-remove\n        description: Axway Remove App\n        call: amplify-platform.app-remove\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: app-update\n        description: Axway Update App\n        call: amplify-platform.app-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/client\n      name: client\n      description: Client operations\n      operations:\n      - method: POST\n\
  \        name: client-create\n        description: Axway Add Service Account\n        call: amplify-platform.client-create\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: client-find\n        description: Axway Get Service Accounts\n        call: amplify-platform.client-find\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: client-download\n        description: Axway Get Service Account JSON Representation\n        call: amplify-platform.client-download\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: client-findOne\n        description: Axway Get a Service Account\n        call: amplify-platform.client-findOne\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: client-remove\n        description: Axway Delete Service Account\n        call: amplify-platform.client-remove\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: client-update\n        description: Axway Update Service Account\n        call: amplify-platform.client-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics\n      name: analytics\n      description: Analytics operations\n      operations:\n      - method: GET\n        name: analytics-query\n        description: Axway Analytics Query Using Lexus\n        call: amplify-platform.analytics-query\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: analytics-error\n        description: Axway Report an Error\n        call: amplify-platform.analytics-error\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: analytics-customCreate\n        description: Axway Create a Custom Query\n        call: amplify-platform.analytics-customCreate\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: analytics-customFind\n        description: Axway Find Custom Queries\n        call: amplify-platform.analytics-customFind\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: analytics-customRemove\n        description: Axway Delete a Custom Query\n        call: amplify-platform.analytics-customRemove\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: analytics-customUpdate\n        description: Axway Update a Custom Query\n        call: amplify-platform.analytics-customUpdate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: analytics-customFindOne\n        description: Axway Get Custom Query\n        call: amplify-platform.analytics-customFindOne\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /v1/usage\n      name: usage\n      description: Usage operations\n      operations:\n      - method: POST\n        name: usage-uploadAutomatic\n        description: Axway Uploads an Automatic Usage Report\n        call: amplify-platform.usage-uploadAutomatic\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: usage-find\n        description: Axway Fetches Usage Reports\n        call: amplify-platform.usage-find\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: usage-upload\n        description: Axway Uploads a Usage Report\n        call: amplify-platform.usage-upload\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: usage-download\n        description: Axway Downloads a Usage Report\n        call: amplify-platform.usage-download\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: GET\n        name: org-findUsage\n        description: Axway Organization Usage\n        call: amplify-platform.org-findUsage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/activity\n      name: activity\n      description: Activity operations\n      operations:\n      - method: GET\n        name: activity-findEvents\n        description: Axway Get Activity Event Names\n        call: amplify-platform.activity-findEvents\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: activity-find\n        description: Axway Get Activity\n        call: amplify-platform.activity-find\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/export\n      name: export\n      description: Export operations\n      operations:\n      - method: POST\n        name: export-create\n        description: Axway Export Data\n        call:\
  \ amplify-platform.export-create\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: export-findAll\n        description: Axway Find Exports\n        call: amplify-platform.export-findAll\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: export-download\n        description: Axway Retrieve a Download Url\n        call: amplify-platform.export-download\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: export-remove\n        description: Axway Remove Export\n        call: amplify-platform.export-remove\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/telemetry\n      name: telemetry\n      description: Telemetry operations\n      operations:\n      - method: POST\n        name: analytics-create\n        description: Axway Send Events\n        call: amplify-platform.analytics-create\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/aca\n      name: aca\n      description: Aca operations\n      operations:\n      - method: PUT\n        name: aca-setMetadata\n        description: Axway Set Metadata by ID\n        call: amplify-platform.aca-setMetadata\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: aca-findOne\n        description: Axway Find Crash Record by ID\n        call: amplify-platform.aca-findOne\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: application-and-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted manage applications, clients, monitor analytics, usage, activity, and data exports on the axway amplify platform.\n    tools:\n    - name: app-create\n      description: Axway Create App\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: amplify-platform.app-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: app-find\n      description: Axway Find Apps\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.app-find\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: app-findOne\n      description: Axway Find App\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.app-findOne\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: app-remove\n      description: Axway Remove App\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.app-remove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: app-update\n      description: Axway Update App\n      hints:\n      \
  \  readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.app-update\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: client-create\n      description: Axway Add Service Account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.client-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: client-find\n      description: Axway Get Service Accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.client-find\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: client-download\n      description: Axway Get Service Account JSON Representation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.client-download\n      outputParameters:\n     \
  \ - type: object\n        mapping: $.\n    - name: client-findOne\n      description: Axway Get a Service Account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.client-findOne\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: client-remove\n      description: Axway Delete Service Account\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.client-remove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: client-update\n      description: Axway Update Service Account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.client-update\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: analytics-query\n      description: Axway Analytics Query Using Lexus\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: amplify-platform.analytics-query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: analytics-error\n      description: Axway Report an Error\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.analytics-error\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: analytics-customCreate\n      description: Axway Create a Custom Query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.analytics-customCreate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: analytics-customFind\n      description: Axway Find Custom Queries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.analytics-customFind\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: analytics-customRemove\n      description: Axway Delete a Custom Query\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.analytics-customRemove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: analytics-customUpdate\n      description: Axway Update a Custom Query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.analytics-customUpdate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: analytics-customFindOne\n      description: Axway Get Custom Query\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.analytics-customFindOne\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: usage-uploadAutomatic\n      description: Axway Uploads an\
  \ Automatic Usage Report\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.usage-uploadAutomatic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: usage-find\n      description: Axway Fetches Usage Reports\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.usage-find\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: usage-upload\n      description: Axway Uploads a Usage Report\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.usage-upload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: usage-download\n      description: Axway Downloads a Usage Report\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.usage-download\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-findUsage\n      description: Axway Organization Usage\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-findUsage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activity-findEvents\n      description: Axway Get Activity Event Names\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.activity-findEvents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activity-find\n      description: Axway Get Activity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.activity-find\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-create\n      description: Axway Export Data\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.export-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-findAll\n      description: Axway Find Exports\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.export-findAll\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-download\n      description: Axway Retrieve a Download Url\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.export-download\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-remove\n      description: Axway Remove Export\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.export-remove\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: analytics-create\n      description: Axway Send Events\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.analytics-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: aca-setMetadata\n      description: Axway Set Metadata by ID\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.aca-setMetadata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: aca-findOne\n      description: Axway Find Crash Record by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.aca-findOne\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
