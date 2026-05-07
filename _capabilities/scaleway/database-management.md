---
categories: []
consumed_apis: []
description: Unified workflow capability for managing Scaleway managed database services including PostgreSQL, MySQL, and Redis instances, backups, and notifications via transactional email. Used by database administrators and application developers to provision, monitor, and maintain managed database infrastructure on Scaleway's European cloud.
layout: capability
name: Scaleway Database Management
operations:
- description: List managed database instances
  method: GET
  name: list-db-instances
  path: /v1/databases
- description: Create a managed database instance
  method: POST
  name: create-db-instance
  path: /v1/databases
- description: Get database instance details
  method: GET
  name: get-db-instance
  path: /v1/databases/{id}
- description: Delete a database instance
  method: DELETE
  name: delete-db-instance
  path: /v1/databases/{id}
- description: List database backups
  method: GET
  name: list-db-backups
  path: /v1/database-backups
- description: Create a database backup
  method: POST
  name: create-db-backup
  path: /v1/database-backups
- description: List available database engine versions
  method: GET
  name: list-database-engines
  path: /v1/database-engines
- description: Send a database alert or notification email
  method: POST
  name: send-notification-email
  path: /v1/emails
personas: []
provider_name: Scaleway
provider_slug: scaleway
search_terms:
- delete a database instance
- database instance management
- notifications
- database backup management
- create a database backup
- containers
- get db instance
- manage a specific database instance
- list scaleway managed database instances
- ai
- scaleway
- create db backup
- cloud computing
- infrastructure
- send a database alert or notification email
- serverless
- create a managed database instance
- available database engines
- kubernetes
- send database alerts or notifications via transactional email
- backup
- list database backups
- european cloud
- redis
- email notification management
- database
- list managed database instances
- get database instance details
- storage
- create db instance
- mysql
- postgresql
- delete a managed database instance
- list database engines
- create a new managed postgresql, mysql, or redis instance
- list db backups
- delete db instance
- get details of a specific database instance
- list db instances
- list available database engine versions
- send notification email
slug: database-management
source_filename: database-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Scaleway Database Management\n  description: Unified workflow capability for managing Scaleway managed database services including PostgreSQL, MySQL, and\n    Redis instances, backups, and notifications via transactional email. Used by database administrators and application developers\n    to provision, monitor, and maintain managed database infrastructure on Scaleway's European cloud.\n  tags:\n  - Backup\n  - Cloud Computing\n  - Database\n  - MySQL\n  - Notifications\n  - PostgreSQL\n  - Redis\n  - Scaleway\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCALEWAY_API_KEY: SCALEWAY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: scaleway-db\n    baseUri: https://api.scaleway.com\n    description: Scaleway Managed Database API\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALEWAY_API_KEY}}'\n      placement: header\n    resources:\n   \
  \ - name: instances\n      path: /rdb/v1/regions/{region}/instances\n      description: Database instance management\n      operations:\n      - name: list-db-instances\n        method: GET\n        description: List Database Instances\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n          description: Region (e.g., fr-par)\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-db-instance\n        method: POST\n        description: Create a Database Instance\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n       \
  \   type: json\n          data:\n            name: '{{tools.name}}'\n            engine: '{{tools.engine}}'\n            node_type: '{{tools.node_type}}'\n    - name: instance\n      path: /rdb/v1/regions/{region}/instances/{instance_id}\n      description: Manage a specific database instance\n      operations:\n      - name: get-db-instance\n        method: GET\n        description: Get Database Instance\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: instance_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-db-instance\n        method: DELETE\n        description: Delete a Database Instance\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: instance_id\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: backups\n      path: /rdb/v1/regions/{region}/backups\n      description: Database backup management\n      operations:\n      - name: list-db-backups\n        method: GET\n        description: List Database Backups\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-db-backup\n        method: POST\n        description: Create a Database Backup\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            instance_id: '{{tools.instance_id}}'\n            name: '{{tools.name}}'\n    - name: database-engines\n      path: /rdb/v1/regions/{region}/database-engines\n      description: Available database engines\n      operations:\n      - name: list-database-engines\n        method: GET\n        description: List available database engine versions\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: scaleway-tem\n    baseUri: https://api.scaleway.com\n    description: Scaleway Transactional Email API\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALEWAY_API_KEY}}'\n      placement: header\n    resources:\n    - name: domains\n      path: /transactional-email/v1alpha1/regions/{region}/domains\n\
  \      description: Email domain management\n      operations:\n      - name: list-tem-domains\n        method: GET\n        description: List Email Domains\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-tem-domain\n        method: POST\n        description: Register an Email Domain\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            project_id: '{{tools.project_id}}'\n    - name: emails\n      path: /transactional-email/v1alpha1/regions/{region}/emails\n      description: Email\
  \ sending and tracking\n      operations:\n      - name: list-emails\n        method: GET\n        description: List Emails\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-email\n        method: POST\n        description: Send a Transactional Email\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            from:\n              email: '{{tools.from_email}}'\n              name: '{{tools.from_name}}'\n            to:\n          \
  \  - email: '{{tools.to_email}}'\n            subject: '{{tools.subject}}'\n            html: '{{tools.html}}'\n    - name: email\n      path: /transactional-email/v1alpha1/regions/{region}/emails/{email_id}\n      description: Manage a specific email\n      operations:\n      - name: get-email\n        method: GET\n        description: Get Email details\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: email_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: scaleway-database-api\n    description: Unified REST API for Scaleway database management and notifications.\n    resources:\n    - path: /v1/databases\n      name: databases\n      description: Database instance management\n      operations:\n\
  \      - method: GET\n        name: list-db-instances\n        description: List managed database instances\n        call: scaleway-db.list-db-instances\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-db-instance\n        description: Create a managed database instance\n        call: scaleway-db.create-db-instance\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/databases/{id}\n      name: database\n      description: Manage a specific database instance\n      operations:\n      - method: GET\n        name: get-db-instance\n        description: Get database instance details\n        call: scaleway-db.get-db-instance\n        with:\n          region: rest.region\n          instance_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n\
  \        name: delete-db-instance\n        description: Delete a database instance\n        call: scaleway-db.delete-db-instance\n        with:\n          region: rest.region\n          instance_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/database-backups\n      name: database-backups\n      description: Database backup management\n      operations:\n      - method: GET\n        name: list-db-backups\n        description: List database backups\n        call: scaleway-db.list-db-backups\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-db-backup\n        description: Create a database backup\n        call: scaleway-db.create-db-backup\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/database-engines\n      name: database-engines\n\
  \      description: Available database engines\n      operations:\n      - method: GET\n        name: list-database-engines\n        description: List available database engine versions\n        call: scaleway-db.list-database-engines\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/emails\n      name: emails\n      description: Email notification management\n      operations:\n      - method: POST\n        name: send-notification-email\n        description: Send a database alert or notification email\n        call: scaleway-tem.send-email\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: scaleway-database-mcp\n    transport: http\n    description: MCP server for AI-assisted Scaleway database management.\n    tools:\n    - name: list-db-instances\n      description: List Scaleway managed\
  \ database instances\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-db.list-db-instances\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-db-instance\n      description: Create a new managed PostgreSQL, MySQL, or Redis instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-db.create-db-instance\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-db-instance\n      description: Get details of a specific database instance\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scaleway-db.get-db-instance\n      with:\n        region: tools.region\n        instance_id: tools.instance_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-db-instance\n      description: Delete\
  \ a managed database instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: scaleway-db.delete-db-instance\n      with:\n        region: tools.region\n        instance_id: tools.instance_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-db-backups\n      description: List database backups\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-db.list-db-backups\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-db-backup\n      description: Create a database backup\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-db.create-db-backup\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-database-engines\n      description: List available database\
  \ engine versions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-db.list-database-engines\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-notification-email\n      description: Send database alerts or notifications via transactional email\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-tem.send-email\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scaleway/refs/heads/main/capabilities/database-management.yaml
tags:
- Backup
- Cloud Computing
- Database
- MySQL
- Notifications
- PostgreSQL
- Redis
- Scaleway
tools:
- description: List Scaleway managed database instances
  hints:
    openWorld: true
    readOnly: true
  name: list-db-instances
- description: Create a new managed PostgreSQL, MySQL, or Redis instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-db-instance
- description: Get details of a specific database instance
  hints:
    openWorld: false
    readOnly: true
  name: get-db-instance
- description: Delete a managed database instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-db-instance
- description: List database backups
  hints:
    openWorld: true
    readOnly: true
  name: list-db-backups
- description: Create a database backup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-db-backup
- description: List available database engine versions
  hints:
    openWorld: true
    readOnly: true
  name: list-database-engines
- description: Send database alerts or notifications via transactional email
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-notification-email
---
