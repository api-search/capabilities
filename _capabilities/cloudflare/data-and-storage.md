---
categories:
- object-storage
consumed_apis:
- cloudflare-r2
- cloudflare-d1
- cloudflare-kv
- cloudflare-hyperdrive
description: Unified data and storage management combining R2 object storage, D1 serverless SQL, KV key-value store, and Hyperdrive database acceleration. Used by developers building data-driven applications on Cloudflare's edge.
layout: capability
name: Cloudflare Data and Storage
operations:
- description: List R2 buckets.
  method: GET
  name: list-buckets
  path: /v1/buckets
- description: List D1 databases.
  method: GET
  name: list-databases
  path: /v1/databases
- description: List KV namespaces.
  method: GET
  name: list-kv-namespaces
  path: /v1/kv-namespaces
- description: List Hyperdrive configs.
  method: GET
  name: list-hyperdrive-configs
  path: /v1/hyperdrive-configs
personas: []
provider_name: Cloudflare
provider_slug: cloudflare
search_terms:
- kv delete value
- r2 create bucket
- kv namespace management.
- list kv namespaces
- list databases
- list keys in a kv namespace.
- create a kv namespace.
- dns
- r2 delete bucket
- create a d1 database.
- d1 query database
- containers
- list d1 databases.
- hyperdrive list configs
- write a kv value.
- list hyperdrive configs
- web performance
- d1 database management.
- list r2 buckets.
- d1 list databases
- delete a hyperdrive configuration.
- real-time communication
- kv list namespaces
- d1 delete database
- artificial intelligence
- kv list keys
- edge
- execute sql query on a d1 database.
- kv create namespace
- create a hyperdrive configuration.
- get r2 bucket details.
- cloudflare
- list r2 storage buckets.
- database
- storage
- kv read value
- cloud
- platform
- serverless
- list buckets
- kv write value
- api gateway
- delete a d1 database.
- ddos protection
- r2 get bucket
- delete a kv value.
- ai gateway
- list hyperdrive configs.
- cdn
- hyperdrive configuration management.
- hyperdrive delete config
- security
- object storage
- list kv namespaces.
- edge computing
- r2 bucket management.
- list hyperdrive configurations.
- data
- create an r2 bucket.
- read a kv value.
- hyperdrive create config
- r2 list buckets
- delete an r2 bucket.
- d1 create database
- list objects in an r2 bucket.
- r2 list objects
slug: data-and-storage
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Cloudflare Data and Storage\"\n  description: \"Unified data and storage management combining R2 object storage, D1 serverless SQL, KV key-value store, and Hyperdrive database acceleration. Used by developers building data-driven applications on Cloudflare's edge.\"\n  tags:\n    - Cloudflare\n    - Storage\n    - Database\n    - Data\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      CLOUDFLARE_API_TOKEN: CLOUDFLARE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: cloudflare-r2\n      location: ./shared/r2.yaml\n    - import: cloudflare-d1\n      location: ./shared/d1.yaml\n    - import: cloudflare-kv\n      location: ./shared/kv.yaml\n    - import: cloudflare-hyperdrive\n      location: ./shared/hyperdrive.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: data-storage-api\n      description: \"Unified REST API for Cloudflare data and storage services.\"\
  \n      resources:\n        - path: /v1/buckets\n          name: buckets\n          description: \"R2 bucket management.\"\n          operations:\n            - method: GET\n              name: list-buckets\n              description: \"List R2 buckets.\"\n              call: \"cloudflare-r2.list-r2-buckets\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/databases\n          name: databases\n          description: \"D1 database management.\"\n          operations:\n            - method: GET\n              name: list-databases\n              description: \"List D1 databases.\"\n              call: \"cloudflare-d1.list-databases\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/kv-namespaces\n          name:\
  \ kv-namespaces\n          description: \"KV namespace management.\"\n          operations:\n            - method: GET\n              name: list-kv-namespaces\n              description: \"List KV namespaces.\"\n              call: \"cloudflare-kv.list-kv-namespaces\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hyperdrive-configs\n          name: hyperdrive-configs\n          description: \"Hyperdrive configuration management.\"\n          operations:\n            - method: GET\n              name: list-hyperdrive-configs\n              description: \"List Hyperdrive configs.\"\n              call: \"cloudflare-hyperdrive.list-hyperdrive-configs\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port:\
  \ 9081\n      namespace: data-storage-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Cloudflare data and storage management.\"\n      tools:\n        - name: r2-list-buckets\n          description: \"List R2 storage buckets.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-r2.list-r2-buckets\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: r2-create-bucket\n          description: \"Create an R2 bucket.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-r2.create-r2-bucket\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: r2-get-bucket\n          description: \"Get R2 bucket details.\"\n          hints:\n            readOnly: true\n    \
  \      call: \"cloudflare-r2.get-r2-bucket\"\n          with:\n            account_id: \"tools.account_id\"\n            bucket_name: \"tools.bucket_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: r2-list-objects\n          description: \"List objects in an R2 bucket.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-r2.list-r2-objects\"\n          with:\n            account_id: \"tools.account_id\"\n            bucket_name: \"tools.bucket_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: r2-delete-bucket\n          description: \"Delete an R2 bucket.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-r2.delete-r2-bucket\"\n          with:\n            account_id: \"tools.account_id\"\n            bucket_name: \"tools.bucket_name\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n        - name: d1-list-databases\n          description: \"List D1 databases.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-d1.list-databases\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: d1-create-database\n          description: \"Create a D1 database.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-d1.create-database\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: d1-query-database\n          description: \"Execute SQL query on a D1 database.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-d1.query-database\"\n          with:\n            account_id: \"tools.account_id\"\n\
  \            database_id: \"tools.database_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: d1-delete-database\n          description: \"Delete a D1 database.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-d1.delete-database\"\n          with:\n            account_id: \"tools.account_id\"\n            database_id: \"tools.database_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: kv-list-namespaces\n          description: \"List KV namespaces.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-kv.list-kv-namespaces\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: kv-create-namespace\n          description: \"Create a KV namespace.\"\
  \n          hints:\n            readOnly: false\n          call: \"cloudflare-kv.create-kv-namespace\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: kv-list-keys\n          description: \"List keys in a KV namespace.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-kv.list-kv-keys\"\n          with:\n            account_id: \"tools.account_id\"\n            namespace_id: \"tools.namespace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: kv-read-value\n          description: \"Read a KV value.\"\n          hints:\n            readOnly: true\n          call: \"cloudflare-kv.read-kv-value\"\n          with:\n            account_id: \"tools.account_id\"\n            namespace_id: \"tools.namespace_id\"\n            key_name: \"tools.key_name\"\n          outputParameters:\n       \
  \     - type: object\n              mapping: \"$.\"\n        - name: kv-write-value\n          description: \"Write a KV value.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"cloudflare-kv.write-kv-value\"\n          with:\n            account_id: \"tools.account_id\"\n            namespace_id: \"tools.namespace_id\"\n            key_name: \"tools.key_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: kv-delete-value\n          description: \"Delete a KV value.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-kv.delete-kv-value\"\n          with:\n            account_id: \"tools.account_id\"\n            namespace_id: \"tools.namespace_id\"\n            key_name: \"tools.key_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: hyperdrive-list-configs\n    \
  \      description: \"List Hyperdrive configurations.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloudflare-hyperdrive.list-hyperdrive-configs\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: hyperdrive-create-config\n          description: \"Create a Hyperdrive configuration.\"\n          hints:\n            readOnly: false\n          call: \"cloudflare-hyperdrive.create-hyperdrive-config\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: hyperdrive-delete-config\n          description: \"Delete a Hyperdrive configuration.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"cloudflare-hyperdrive.delete-hyperdrive-config\"\n          with:\n         \
  \   account_id: \"tools.account_id\"\n            config_id: \"tools.config_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloudflare/refs/heads/main/capabilities/data-and-storage.yaml
tags:
- Cloudflare
- Storage
- Database
- Data
tools:
- description: List R2 storage buckets.
  hints:
    openWorld: true
    readOnly: true
  name: r2-list-buckets
- description: Create an R2 bucket.
  hints:
    readOnly: false
  name: r2-create-bucket
- description: Get R2 bucket details.
  hints:
    readOnly: true
  name: r2-get-bucket
- description: List objects in an R2 bucket.
  hints:
    readOnly: true
  name: r2-list-objects
- description: Delete an R2 bucket.
  hints:
    destructive: true
    idempotent: true
  name: r2-delete-bucket
- description: List D1 databases.
  hints:
    openWorld: true
    readOnly: true
  name: d1-list-databases
- description: Create a D1 database.
  hints:
    readOnly: false
  name: d1-create-database
- description: Execute SQL query on a D1 database.
  hints:
    readOnly: false
  name: d1-query-database
- description: Delete a D1 database.
  hints:
    destructive: true
    idempotent: true
  name: d1-delete-database
- description: List KV namespaces.
  hints:
    openWorld: true
    readOnly: true
  name: kv-list-namespaces
- description: Create a KV namespace.
  hints:
    readOnly: false
  name: kv-create-namespace
- description: List keys in a KV namespace.
  hints:
    readOnly: true
  name: kv-list-keys
- description: Read a KV value.
  hints:
    readOnly: true
  name: kv-read-value
- description: Write a KV value.
  hints:
    idempotent: true
    readOnly: false
  name: kv-write-value
- description: Delete a KV value.
  hints:
    destructive: true
    idempotent: true
  name: kv-delete-value
- description: List Hyperdrive configurations.
  hints:
    openWorld: true
    readOnly: true
  name: hyperdrive-list-configs
- description: Create a Hyperdrive configuration.
  hints:
    readOnly: false
  name: hyperdrive-create-config
- description: Delete a Hyperdrive configuration.
  hints:
    destructive: true
    idempotent: true
  name: hyperdrive-delete-config
---
