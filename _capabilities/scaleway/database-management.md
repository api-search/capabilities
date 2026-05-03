---
categories: []
consumed_apis:
- scaleway-db
- scaleway-tem
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
- infrastructure
- create a database backup
- list db instances
- get database instance details
- create db instance
- scaleway
- delete db instance
- get details of a specific database instance
- storage
- manage a specific database instance
- kubernetes
- create a new managed postgresql, mysql, or redis instance
- email notification management
- list available database engine versions
- get db instance
- send notification email
- ai
- list database backups
- create db backup
- send a database alert or notification email
- delete a managed database instance
- send database alerts or notifications via transactional email
- available database engines
- list managed database instances
- containers
- list db backups
- notifications
- serverless
- database instance management
- delete a database instance
- database
- list database engines
- redis
- european cloud
- list scaleway managed database instances
- cloud computing
- backup
- mysql
- database backup management
- postgresql
- create a managed database instance
slug: database-management
source_filename: database-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Scaleway Database Management\"\n  description: >-\n    Unified workflow capability for managing Scaleway managed database services including\n    PostgreSQL, MySQL, and Redis instances, backups, and notifications via transactional\n    email. Used by database administrators and application developers to provision,\n    monitor, and maintain managed database infrastructure on Scaleway's European cloud.\n  tags:\n    - Backup\n    - Cloud Computing\n    - Database\n    - MySQL\n    - Notifications\n    - PostgreSQL\n    - Redis\n    - Scaleway\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SCALEWAY_API_KEY: SCALEWAY_API_KEY\n\ncapability:\n  consumes:\n    - import: scaleway-db\n      location: ./shared/database.yaml\n    - import: scaleway-tem\n      location: ./shared/transactional-email.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: scaleway-database-api\n\
  \      description: \"Unified REST API for Scaleway database management and notifications.\"\n      resources:\n        - path: /v1/databases\n          name: databases\n          description: \"Database instance management\"\n          operations:\n            - method: GET\n              name: list-db-instances\n              description: \"List managed database instances\"\n              call: \"scaleway-db.list-db-instances\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-db-instance\n              description: \"Create a managed database instance\"\n              call: \"scaleway-db.create-db-instance\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/databases/{id}\n          name:\
  \ database\n          description: \"Manage a specific database instance\"\n          operations:\n            - method: GET\n              name: get-db-instance\n              description: \"Get database instance details\"\n              call: \"scaleway-db.get-db-instance\"\n              with:\n                region: \"rest.region\"\n                instance_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-db-instance\n              description: \"Delete a database instance\"\n              call: \"scaleway-db.delete-db-instance\"\n              with:\n                region: \"rest.region\"\n                instance_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/database-backups\n          name: database-backups\n          description: \"Database backup management\"\n \
  \         operations:\n            - method: GET\n              name: list-db-backups\n              description: \"List database backups\"\n              call: \"scaleway-db.list-db-backups\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-db-backup\n              description: \"Create a database backup\"\n              call: \"scaleway-db.create-db-backup\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/database-engines\n          name: database-engines\n          description: \"Available database engines\"\n          operations:\n            - method: GET\n              name: list-database-engines\n              description: \"List available database engine versions\"\n            \
  \  call: \"scaleway-db.list-database-engines\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/emails\n          name: emails\n          description: \"Email notification management\"\n          operations:\n            - method: POST\n              name: send-notification-email\n              description: \"Send a database alert or notification email\"\n              call: \"scaleway-tem.send-email\"\n              with:\n                region: \"rest.region\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9094\n      namespace: scaleway-database-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Scaleway database management.\"\n      tools:\n        - name: list-db-instances\n          description: \"List Scaleway managed database instances\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-db.list-db-instances\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-db-instance\n          description: \"Create a new managed PostgreSQL, MySQL, or Redis instance\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scaleway-db.create-db-instance\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-db-instance\n          description: \"Get details of a specific database instance\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"scaleway-db.get-db-instance\"\n          with:\n            region: \"tools.region\"\n            instance_id:\
  \ \"tools.instance_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-db-instance\n          description: \"Delete a managed database instance\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"scaleway-db.delete-db-instance\"\n          with:\n            region: \"tools.region\"\n            instance_id: \"tools.instance_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-db-backups\n          description: \"List database backups\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-db.list-db-backups\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-db-backup\n          description: \"Create a database backup\"\n\
  \          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scaleway-db.create-db-backup\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-database-engines\n          description: \"List available database engine versions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scaleway-db.list-database-engines\"\n          with:\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-notification-email\n          description: \"Send database alerts or notifications via transactional email\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"scaleway-tem.send-email\"\n          with:\n            region:\
  \ \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
