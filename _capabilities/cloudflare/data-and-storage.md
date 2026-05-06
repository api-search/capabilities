---
categories:
- object-storage
consumed_apis: []
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
- r2 create bucket
- d1 database management.
- r2 delete bucket
- hyperdrive delete config
- delete an r2 bucket.
- read a kv value.
- dns
- storage
- create an r2 bucket.
- execute sql query on a d1 database.
- list buckets
- object storage
- list hyperdrive configs
- r2 list buckets
- kv list namespaces
- hyperdrive list configs
- kv namespace management.
- delete a hyperdrive configuration.
- d1 delete database
- kv read value
- list hyperdrive configurations.
- serverless
- r2 list objects
- create a kv namespace.
- r2 get bucket
- kv write value
- list hyperdrive configs.
- kv create namespace
- cloud
- containers
- security
- list kv namespaces.
- list keys in a kv namespace.
- ddos protection
- list objects in an r2 bucket.
- create a hyperdrive configuration.
- d1 query database
- cloudflare
- artificial intelligence
- edge computing
- r2 bucket management.
- database
- list kv namespaces
- ai gateway
- cdn
- hyperdrive configuration management.
- delete a kv value.
- write a kv value.
- d1 create database
- kv list keys
- list r2 buckets.
- delete a d1 database.
- get r2 bucket details.
- list databases
- hyperdrive create config
- api gateway
- web performance
- data
- create a d1 database.
- platform
- list r2 storage buckets.
- kv delete value
- real-time communication
- d1 list databases
- list d1 databases.
- edge
slug: data-and-storage
source_filename: data-and-storage.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Cloudflare Data and Storage\n  description: Unified data and storage management combining R2 object storage, D1 serverless SQL, KV key-value store, and\n    Hyperdrive database acceleration. Used by developers building data-driven applications on Cloudflare's edge.\n  tags:\n  - Cloudflare\n  - Storage\n  - Database\n  - Data\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CLOUDFLARE_API_TOKEN: CLOUDFLARE_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: cloudflare-r2\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare R2 API for managing object storage buckets and configuration.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: buckets\n      path: /accounts/{account_id}/r2/buckets\n      description: Manage R2 storage buckets.\n      operations:\n      - name: list-r2-buckets\n        method:\
  \ GET\n        description: List all R2 buckets for an account.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-r2-bucket\n        method: POST\n        description: Create a new R2 bucket.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            locationHint: '{{tools.location_hint}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket\n      path: /accounts/{account_id}/r2/buckets/{bucket_name}\n      description: Manage\
  \ a specific R2 bucket.\n      operations:\n      - name: get-r2-bucket\n        method: GET\n        description: Get R2 bucket details.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: bucket_name\n          in: path\n          type: string\n          required: true\n          description: Bucket name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-r2-bucket\n        method: DELETE\n        description: Delete an R2 bucket.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: bucket_name\n          in: path\n          type: string\n          required: true\n          description: Bucket name.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket-objects\n      path: /accounts/{account_id}/r2/buckets/{bucket_name}/objects\n      description: List objects in an R2 bucket.\n      operations:\n      - name: list-r2-objects\n        method: GET\n        description: List objects in a bucket.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: bucket_name\n          in: path\n          type: string\n          required: true\n          description: Bucket name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cloudflare-d1\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare D1 API for managing serverless SQL databases.\n    authentication:\n      type: bearer\n\
  \      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: databases\n      path: /accounts/{account_id}/d1/database\n      description: Manage D1 databases.\n      operations:\n      - name: list-databases\n        method: GET\n        description: List all D1 databases.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-database\n        method: POST\n        description: Create a new D1 database.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: database\n      path: /accounts/{account_id}/d1/database/{database_id}\n      description: Manage a specific D1 database.\n      operations:\n      - name: get-database\n        method: GET\n        description: Get D1 database details.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: database_id\n          in: path\n          type: string\n          required: true\n          description: Database identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-database\n        method: DELETE\n        description: Delete a D1 database.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Account identifier.\n        - name: database_id\n          in: path\n          type: string\n          required: true\n          description: Database identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: database-query\n      path: /accounts/{account_id}/d1/database/{database_id}/query\n      description: Execute queries on a D1 database.\n      operations:\n      - name: query-database\n        method: POST\n        description: Execute a SQL query on a D1 database.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: database_id\n          in: path\n          type: string\n          required: true\n          description: Database identifier.\n        body:\n          type: json\n          data:\n            sql: '{{tools.sql}}'\n            params: '{{tools.params}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cloudflare-kv\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare Workers KV API for managing key-value storage.\n    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: namespaces\n      path: /accounts/{account_id}/storage/kv/namespaces\n      description: Manage KV namespaces.\n      operations:\n      - name: list-kv-namespaces\n        method: GET\n        description: List all KV namespaces.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-kv-namespace\n        method: POST\n    \
  \    description: Create a new KV namespace.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespace\n      path: /accounts/{account_id}/storage/kv/namespaces/{namespace_id}\n      description: Manage a specific KV namespace.\n      operations:\n      - name: get-kv-namespace\n        method: GET\n        description: Get KV namespace details.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: namespace_id\n          in: path\n          type: string\n          required: true\n          description: Namespace\
  \ identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-kv-namespace\n        method: DELETE\n        description: Delete a KV namespace.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: namespace_id\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: keys\n      path: /accounts/{account_id}/storage/kv/namespaces/{namespace_id}/keys\n      description: Manage KV keys.\n      operations:\n      - name: list-kv-keys\n        method: GET\n        description: List keys in a namespace.\n        inputParameters:\n        - name: account_id\n          in:\
  \ path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: namespace_id\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: values\n      path: /accounts/{account_id}/storage/kv/namespaces/{namespace_id}/values/{key_name}\n      description: Read and write KV values.\n      operations:\n      - name: read-kv-value\n        method: GET\n        description: Read a key-value pair.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: namespace_id\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier.\n        - name: key_name\n          in:\
  \ path\n          type: string\n          required: true\n          description: Key name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: write-kv-value\n        method: PUT\n        description: Write a key-value pair.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: namespace_id\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier.\n        - name: key_name\n          in: path\n          type: string\n          required: true\n          description: Key name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-kv-value\n        method: DELETE\n        description: Delete a key-value pair.\n        inputParameters:\n\
  \        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: namespace_id\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier.\n        - name: key_name\n          in: path\n          type: string\n          required: true\n          description: Key name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bulk\n      path: /accounts/{account_id}/storage/kv/namespaces/{namespace_id}/bulk\n      description: Bulk KV operations.\n      operations:\n      - name: bulk-write-kv-pairs\n        method: PUT\n        description: Write multiple key-value pairs.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: namespace_id\n\
  \          in: path\n          type: string\n          required: true\n          description: Namespace identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: bulk-delete-kv-pairs\n        method: DELETE\n        description: Delete multiple key-value pairs.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: namespace_id\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cloudflare-hyperdrive\n    baseUri: https://api.cloudflare.com/client/v4\n    description: Cloudflare Hyperdrive API for managing database acceleration configurations.\n\
  \    authentication:\n      type: bearer\n      token: '{{CLOUDFLARE_API_TOKEN}}'\n    resources:\n    - name: configs\n      path: /accounts/{account_id}/hyperdrive/configs\n      description: Manage Hyperdrive configurations.\n      operations:\n      - name: list-hyperdrive-configs\n        method: GET\n        description: List all Hyperdrive configurations.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-hyperdrive-config\n        method: POST\n        description: Create a new Hyperdrive configuration.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        body:\n          type: json\n          data:\n\
  \            name: '{{tools.name}}'\n            origin: '{{tools.origin}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: config\n      path: /accounts/{account_id}/hyperdrive/configs/{config_id}\n      description: Manage a specific Hyperdrive configuration.\n      operations:\n      - name: get-hyperdrive-config\n        method: GET\n        description: Get Hyperdrive configuration details.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: config_id\n          in: path\n          type: string\n          required: true\n          description: Configuration identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-hyperdrive-config\n        method: DELETE\n \
  \       description: Delete a Hyperdrive configuration.\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        - name: config_id\n          in: path\n          type: string\n          required: true\n          description: Configuration identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: data-storage-api\n    description: Unified REST API for Cloudflare data and storage services.\n    resources:\n    - path: /v1/buckets\n      name: buckets\n      description: R2 bucket management.\n      operations:\n      - method: GET\n        name: list-buckets\n        description: List R2 buckets.\n        call: cloudflare-r2.list-r2-buckets\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /v1/databases\n      name: databases\n      description: D1 database management.\n      operations:\n      - method: GET\n        name: list-databases\n        description: List D1 databases.\n        call: cloudflare-d1.list-databases\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/kv-namespaces\n      name: kv-namespaces\n      description: KV namespace management.\n      operations:\n      - method: GET\n        name: list-kv-namespaces\n        description: List KV namespaces.\n        call: cloudflare-kv.list-kv-namespaces\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hyperdrive-configs\n      name: hyperdrive-configs\n      description: Hyperdrive configuration management.\n      operations:\n      - method: GET\n        name: list-hyperdrive-configs\n\
  \        description: List Hyperdrive configs.\n        call: cloudflare-hyperdrive.list-hyperdrive-configs\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: data-storage-mcp\n    transport: http\n    description: MCP server for AI-assisted Cloudflare data and storage management.\n    tools:\n    - name: r2-list-buckets\n      description: List R2 storage buckets.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-r2.list-r2-buckets\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: r2-create-bucket\n      description: Create an R2 bucket.\n      hints:\n        readOnly: false\n      call: cloudflare-r2.create-r2-bucket\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ r2-get-bucket\n      description: Get R2 bucket details.\n      hints:\n        readOnly: true\n      call: cloudflare-r2.get-r2-bucket\n      with:\n        account_id: tools.account_id\n        bucket_name: tools.bucket_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: r2-list-objects\n      description: List objects in an R2 bucket.\n      hints:\n        readOnly: true\n      call: cloudflare-r2.list-r2-objects\n      with:\n        account_id: tools.account_id\n        bucket_name: tools.bucket_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: r2-delete-bucket\n      description: Delete an R2 bucket.\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudflare-r2.delete-r2-bucket\n      with:\n        account_id: tools.account_id\n        bucket_name: tools.bucket_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: d1-list-databases\n      description:\
  \ List D1 databases.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-d1.list-databases\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: d1-create-database\n      description: Create a D1 database.\n      hints:\n        readOnly: false\n      call: cloudflare-d1.create-database\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: d1-query-database\n      description: Execute SQL query on a D1 database.\n      hints:\n        readOnly: false\n      call: cloudflare-d1.query-database\n      with:\n        account_id: tools.account_id\n        database_id: tools.database_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: d1-delete-database\n      description: Delete a D1 database.\n      hints:\n        destructive: true\n        idempotent: true\n      call:\
  \ cloudflare-d1.delete-database\n      with:\n        account_id: tools.account_id\n        database_id: tools.database_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: kv-list-namespaces\n      description: List KV namespaces.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-kv.list-kv-namespaces\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: kv-create-namespace\n      description: Create a KV namespace.\n      hints:\n        readOnly: false\n      call: cloudflare-kv.create-kv-namespace\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: kv-list-keys\n      description: List keys in a KV namespace.\n      hints:\n        readOnly: true\n      call: cloudflare-kv.list-kv-keys\n      with:\n        account_id: tools.account_id\n        namespace_id: tools.namespace_id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: kv-read-value\n      description: Read a KV value.\n      hints:\n        readOnly: true\n      call: cloudflare-kv.read-kv-value\n      with:\n        account_id: tools.account_id\n        namespace_id: tools.namespace_id\n        key_name: tools.key_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: kv-write-value\n      description: Write a KV value.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloudflare-kv.write-kv-value\n      with:\n        account_id: tools.account_id\n        namespace_id: tools.namespace_id\n        key_name: tools.key_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: kv-delete-value\n      description: Delete a KV value.\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudflare-kv.delete-kv-value\n      with:\n        account_id: tools.account_id\n\
  \        namespace_id: tools.namespace_id\n        key_name: tools.key_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hyperdrive-list-configs\n      description: List Hyperdrive configurations.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloudflare-hyperdrive.list-hyperdrive-configs\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hyperdrive-create-config\n      description: Create a Hyperdrive configuration.\n      hints:\n        readOnly: false\n      call: cloudflare-hyperdrive.create-hyperdrive-config\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hyperdrive-delete-config\n      description: Delete a Hyperdrive configuration.\n      hints:\n        destructive: true\n        idempotent: true\n      call: cloudflare-hyperdrive.delete-hyperdrive-config\n\
  \      with:\n        account_id: tools.account_id\n        config_id: tools.config_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
