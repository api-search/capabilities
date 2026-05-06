---
categories: []
consumed_apis: []
description: Unified workflow capability combining Supabase's database, authentication, and storage services for full-stack application development. Used by developers building web and mobile applications who need a complete backend without managing infrastructure. Combines the Management API, Auth API, Database REST API, and Storage API into a single coherent developer experience.
layout: capability
name: Supabase Backend As A Service
operations:
- description: List all projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new project
  method: POST
  name: create-project
  path: /v1/projects
- description: Get project details
  method: GET
  name: get-project
  path: /v1/projects/{ref}
- description: Get project API keys
  method: GET
  name: get-api-keys
  path: /v1/projects/{ref}/api-keys
- description: Get project health status
  method: GET
  name: get-health
  path: /v1/projects/{ref}/health
- description: Register a new user
  method: POST
  name: sign-up
  path: /v1/auth/signup
- description: Sign in a user
  method: POST
  name: sign-in
  path: /v1/auth/signin
- description: List all users
  method: GET
  name: list-users
  path: /v1/auth/users
- description: Query table rows
  method: GET
  name: select-rows
  path: /v1/data/{table}
- description: Insert rows
  method: POST
  name: insert-rows
  path: /v1/data/{table}
- description: Invoke a PostgreSQL function
  method: POST
  name: invoke-function
  path: /v1/rpc/{function_name}
- description: List all storage buckets
  method: GET
  name: list-buckets
  path: /v1/buckets
- description: Create a storage bucket
  method: POST
  name: create-bucket
  path: /v1/buckets
- description: List all organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
personas: []
provider_name: Supabase
provider_slug: supabase
search_terms:
- sign up
- edge functions
- get project details
- manage supabase projects
- manage a specific project
- get project health
- call a postgresql stored function via rpc
- sign in a user and get jwt access token
- storage
- create a new project
- list buckets
- list organizations
- create signed url
- create a signed url for temporary access to a private file
- get the currently authenticated user's profile
- user registration
- real time
- full stack
- backend as a service
- create function
- user login
- user management (admin)
- insert one or more rows into a database table
- organization management
- supabase
- update rows
- list all users
- create a new supabase project
- query rows from a database table with filtering and pagination
- list all supabase projects
- database crud operations
- update rows in a table matching filter criteria
- create project
- get project health and service status
- list all projects
- deploy a new edge function to a project
- open source
- storage bucket management
- list secrets stored for a project
- list all organizations
- create a new storage bucket
- list all edge functions for a project
- database
- list all users in the project (admin)
- postgresql
- sign in
- authentication
- project health status
- postgresql function invocation
- get api keys
- get project
- list projects
- get project health status
- sign in a user
- get details for a specific project
- list functions
- list all organizations the user belongs to
- get user
- list all storage buckets in the project
- create a storage bucket
- list users
- list all storage buckets
- register a new user with email and password
- invoke a postgresql function
- insert rows
- invoke function
- list secrets
- create bucket
- select rows
- query table rows
- retrieve project api keys
- get project api keys
- get health
- register a new user
- get the api keys (anon, service_role) for a project
slug: backend-as-a-service
source_filename: backend-as-a-service.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Supabase Backend As A Service\n  description: Unified workflow capability combining Supabase's database, authentication, and storage services for full-stack\n    application development. Used by developers building web and mobile applications who need a complete backend without managing\n    infrastructure. Combines the Management API, Auth API, Database REST API, and Storage API into a single coherent developer\n    experience.\n  tags:\n  - Supabase\n  - Backend As A Service\n  - Full Stack\n  - PostgreSQL\n  - Authentication\n  - Storage\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SUPABASE_ACCESS_TOKEN: SUPABASE_ACCESS_TOKEN\n    SUPABASE_ANON_KEY: SUPABASE_ANON_KEY\n    SUPABASE_SERVICE_ROLE_KEY: SUPABASE_SERVICE_ROLE_KEY\n    SUPABASE_PROJECT_REF: SUPABASE_PROJECT_REF\ncapability:\n  consumes:\n  - type: http\n    namespace: supabase-mgmt\n    baseUri: https://api.supabase.com/v1\n  \
  \  description: Supabase Management API for project and organization control\n    authentication:\n      type: bearer\n      token: '{{SUPABASE_ACCESS_TOKEN}}'\n    resources:\n    - name: projects\n      path: /projects\n      description: Manage Supabase projects\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            organization_id: '{{tools.organization_id}}'\n            db_pass: '{{tools.db_pass}}'\n            region: '{{tools.region}}'\n    - name: project\n      path: /projects/{ref}\n\
  \      description: Manage a specific project by reference ID\n      operations:\n      - name: get-project\n        method: GET\n        description: Get project details\n        inputParameters:\n        - name: ref\n          in: path\n          type: string\n          required: true\n          description: Project reference ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-project\n        method: DELETE\n        description: Delete a project\n        inputParameters:\n        - name: ref\n          in: path\n          type: string\n          required: true\n          description: Project reference ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project-api-keys\n      path: /projects/{ref}/api-keys\n      description: Retrieve API keys for a project\n      operations:\n      - name: get-project-api-keys\n\
  \        method: GET\n        description: Get project API keys\n        inputParameters:\n        - name: ref\n          in: path\n          type: string\n          required: true\n          description: Project reference ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project-health\n      path: /projects/{ref}/health\n      description: Monitor project health\n      operations:\n      - name: get-project-health\n        method: GET\n        description: Get project health status\n        inputParameters:\n        - name: ref\n          in: path\n          type: string\n          required: true\n          description: Project reference ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: functions\n      path: /projects/{ref}/functions\n      description: Manage Edge Functions for a project\n      operations:\n\
  \      - name: list-functions\n        method: GET\n        description: List Edge Functions\n        inputParameters:\n        - name: ref\n          in: path\n          type: string\n          required: true\n          description: Project reference ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-function\n        method: POST\n        description: Create an Edge Function\n        inputParameters:\n        - name: ref\n          in: path\n          type: string\n          required: true\n          description: Project reference ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            slug: '{{tools.slug}}'\n            name: '{{tools.name}}'\n            body: '{{tools.body}}'\n    - name: secrets\n      path: /projects/{ref}/secrets\n      description:\
  \ Manage project secrets\n      operations:\n      - name: list-secrets\n        method: GET\n        description: List project secrets\n        inputParameters:\n        - name: ref\n          in: path\n          type: string\n          required: true\n          description: Project reference ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-secrets\n        method: POST\n        description: Create project secrets\n        inputParameters:\n        - name: ref\n          in: path\n          type: string\n          required: true\n          description: Project reference ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            secrets: '{{tools.secrets}}'\n    - name: organizations\n      path: /organizations\n      description: Manage organizations\n\
  \      operations:\n      - name: list-organizations\n        method: GET\n        description: List all organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-organization\n        method: POST\n        description: Create an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n  - type: http\n    namespace: supabase-auth\n    baseUri: https://{{SUPABASE_PROJECT_REF}}.supabase.co/auth/v1\n    description: Supabase Auth API for user authentication and management\n    authentication:\n      type: apikey\n      key: apikey\n      value: '{{SUPABASE_ANON_KEY}}'\n      placement: header\n    resources:\n    - name: signup\n      path: /signup\n      description: User registration\n      operations:\n      - name:\
  \ sign-up\n        method: POST\n        description: Sign up a new user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            password: '{{tools.password}}'\n    - name: token\n      path: /token\n      description: User authentication token operations\n      operations:\n      - name: sign-in\n        method: POST\n        description: Sign in with credentials\n        inputParameters:\n        - name: grant_type\n          in: query\n          type: string\n          required: true\n          description: 'Grant type: password, refresh_token, or id_token'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            password: '{{tools.password}}'\n\
  \    - name: logout\n      path: /logout\n      description: User logout\n      operations:\n      - name: sign-out\n        method: POST\n        description: Sign out a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /user\n      description: Current user operations\n      operations:\n      - name: get-user\n        method: GET\n        description: Get the current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PUT\n        description: Update the current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            password: '{{tools.password}}'\n    - name: admin-users\n\
  \      path: /admin/users\n      description: Administrative user management (requires service_role key)\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users (admin)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a user (admin)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            password: '{{tools.password}}'\n  - type: http\n    namespace: supabase-db\n    baseUri: https://{{SUPABASE_PROJECT_REF}}.supabase.co/rest/v1\n    description: Supabase PostgREST auto-generated database REST API\n    authentication:\n      type: apikey\n      key: apikey\n      value: '{{SUPABASE_ANON_KEY}}'\n      placement: header\n\
  \    resources:\n    - name: table\n      path: /{table}\n      description: CRUD operations on database tables\n      operations:\n      - name: select-rows\n        method: GET\n        description: Select rows from a table\n        inputParameters:\n        - name: table\n          in: path\n          type: string\n          required: true\n          description: Table or view name\n        - name: select\n          in: query\n          type: string\n          required: false\n          description: Comma-separated columns to return\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: Column to sort by\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum rows to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Rows to skip\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: array\n          value: $.\n      - name: insert-rows\n        method: POST\n        description: Insert rows into a table\n        inputParameters:\n        - name: table\n          in: path\n          type: string\n          required: true\n          description: Table name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n        body:\n          type: json\n          data:\n            row_data: '{{tools.row_data}}'\n      - name: update-rows\n        method: PATCH\n        description: Update rows in a table\n        inputParameters:\n        - name: table\n          in: path\n          type: string\n          required: true\n          description: Table name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n        body:\n          type: json\n          data:\n            updates: '{{tools.updates}}'\n\
  \      - name: delete-rows\n        method: DELETE\n        description: Delete rows from a table\n        inputParameters:\n        - name: table\n          in: path\n          type: string\n          required: true\n          description: Table name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: rpc\n      path: /rpc/{function_name}\n      description: Invoke PostgreSQL stored functions\n      operations:\n      - name: invoke-function\n        method: POST\n        description: Invoke a PostgreSQL function\n        inputParameters:\n        - name: function_name\n          in: path\n          type: string\n          required: true\n          description: PostgreSQL function name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            args: '{{tools.args}}'\n\
  \  - type: http\n    namespace: supabase-storage\n    baseUri: https://{{SUPABASE_PROJECT_REF}}.supabase.co/storage/v1\n    description: Supabase Storage API for object storage and file management\n    authentication:\n      type: apikey\n      key: apikey\n      value: '{{SUPABASE_ANON_KEY}}'\n      placement: header\n    resources:\n    - name: buckets\n      path: /bucket\n      description: Manage storage buckets\n      operations:\n      - name: list-buckets\n        method: GET\n        description: List all buckets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-bucket\n        method: POST\n        description: Create a new bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.id}}'\n            public: '{{tools.public}}'\n\
  \    - name: objects\n      path: /object/{bucket_id}\n      description: Manage objects within a bucket\n      operations:\n      - name: upload-file\n        method: POST\n        description: Upload a file to a bucket\n        inputParameters:\n        - name: bucket_id\n          in: path\n          type: string\n          required: true\n          description: Bucket ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: object-download\n      path: /object/authenticated/{bucket_id}/{object_name}\n      description: Download private files\n      operations:\n      - name: download-file\n        method: GET\n        description: Download a private file\n        inputParameters:\n        - name: bucket_id\n          in: path\n          type: string\n          required: true\n          description: Bucket ID\n        - name: object_name\n          in: path\n          type: string\n          required:\
  \ true\n          description: Object path within the bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: signed-url\n      path: /object/sign/{bucket_id}/{object_name}\n      description: Generate signed URLs for temporary access\n      operations:\n      - name: create-signed-url\n        method: POST\n        description: Create a signed URL\n        inputParameters:\n        - name: bucket_id\n          in: path\n          type: string\n          required: true\n          description: Bucket ID\n        - name: object_name\n          in: path\n          type: string\n          required: true\n          description: Object path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            expiresIn: '{{tools.expiresIn}}'\n  exposes:\n  - type: rest\n    port:\
  \ 8080\n    namespace: supabase-baas-api\n    description: Unified REST API for Supabase backend services.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: Manage Supabase projects\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all projects\n        call: supabase-mgmt.list-projects\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create a new project\n        call: supabase-mgmt.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{ref}\n      name: project\n      description: Manage a specific project\n      operations:\n      - method: GET\n        name: get-project\n        description: Get project details\n        call: supabase-mgmt.get-project\n        with:\n          ref: rest.ref\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n    - path: /v1/projects/{ref}/api-keys\n      name: api-keys\n      description: Retrieve project API keys\n      operations:\n      - method: GET\n        name: get-api-keys\n        description: Get project API keys\n        call: supabase-mgmt.get-project-api-keys\n        with:\n          ref: rest.ref\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{ref}/health\n      name: project-health\n      description: Project health status\n      operations:\n      - method: GET\n        name: get-health\n        description: Get project health status\n        call: supabase-mgmt.get-project-health\n        with:\n          ref: rest.ref\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/auth/signup\n      name: signup\n      description: User registration\n      operations:\n      - method: POST\n        name: sign-up\n        description: Register a new user\n        call: supabase-auth.sign-up\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/auth/signin\n      name: signin\n      description: User login\n      operations:\n      - method: POST\n        name: sign-in\n        description: Sign in a user\n        call: supabase-auth.sign-in\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/auth/users\n      name: users\n      description: User management (admin)\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users\n        call: supabase-auth.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data/{table}\n      name: table-data\n      description: Database CRUD operations\n      operations:\n      - method: GET\n        name: select-rows\n        description: Query table rows\n        call: supabase-db.select-rows\n        with:\n          table: rest.table\n        outputParameters:\n        -\
  \ type: array\n          mapping: $.\n      - method: POST\n        name: insert-rows\n        description: Insert rows\n        call: supabase-db.insert-rows\n        with:\n          table: rest.table\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/rpc/{function_name}\n      name: rpc\n      description: PostgreSQL function invocation\n      operations:\n      - method: POST\n        name: invoke-function\n        description: Invoke a PostgreSQL function\n        call: supabase-db.invoke-function\n        with:\n          function_name: rest.function_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets\n      name: buckets\n      description: Storage bucket management\n      operations:\n      - method: GET\n        name: list-buckets\n        description: List all storage buckets\n        call: supabase-storage.list-buckets\n        outputParameters:\n        - type: array\n          mapping:\
  \ $.\n      - method: POST\n        name: create-bucket\n        description: Create a storage bucket\n        call: supabase-storage.create-bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations\n      name: organizations\n      description: Organization management\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List all organizations\n        call: supabase-mgmt.list-organizations\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: supabase-baas-mcp\n    transport: http\n    description: MCP server for AI-assisted Supabase application development.\n    tools:\n    - name: list-projects\n      description: List all Supabase projects\n      hints:\n        readOnly: true\n        openWorld: false\n      call: supabase-mgmt.list-projects\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name:\
  \ create-project\n      description: Create a new Supabase project\n      hints:\n        readOnly: false\n        destructive: false\n      call: supabase-mgmt.create-project\n      with:\n        name: tools.name\n        organization_id: tools.organization_id\n        db_pass: tools.db_pass\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project\n      description: Get details for a specific project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: supabase-mgmt.get-project\n      with:\n        ref: tools.ref\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project-health\n      description: Get project health and service status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: supabase-mgmt.get-project-health\n      with:\n        ref: tools.ref\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-keys\n\
  \      description: Get the API keys (anon, service_role) for a project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: supabase-mgmt.get-project-api-keys\n      with:\n        ref: tools.ref\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-functions\n      description: List all Edge Functions for a project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: supabase-mgmt.list-functions\n      with:\n        ref: tools.ref\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-function\n      description: Deploy a new Edge Function to a project\n      hints:\n        readOnly: false\n        destructive: false\n      call: supabase-mgmt.create-function\n      with:\n        ref: tools.ref\n        slug: tools.slug\n        name: tools.name\n        body: tools.body\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-secrets\n     \
  \ description: List secrets stored for a project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: supabase-mgmt.list-secrets\n      with:\n        ref: tools.ref\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-organizations\n      description: List all organizations the user belongs to\n      hints:\n        readOnly: true\n        openWorld: false\n      call: supabase-mgmt.list-organizations\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: sign-up\n      description: Register a new user with email and password\n      hints:\n        readOnly: false\n        destructive: false\n      call: supabase-auth.sign-up\n      with:\n        email: tools.email\n        password: tools.password\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sign-in\n      description: Sign in a user and get JWT access token\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n      call: supabase-auth.sign-in\n      with:\n        email: tools.email\n        password: tools.password\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get the currently authenticated user's profile\n      hints:\n        readOnly: true\n        openWorld: false\n      call: supabase-auth.get-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all users in the project (admin)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: supabase-auth.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: select-rows\n      description: Query rows from a database table with filtering and pagination\n      hints:\n        readOnly: true\n        openWorld: false\n      call: supabase-db.select-rows\n      with:\n        table: tools.table\n        select: tools.select\n        limit: tools.limit\n\
  \        offset: tools.offset\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: insert-rows\n      description: Insert one or more rows into a database table\n      hints:\n        readOnly: false\n        destructive: false\n      call: supabase-db.insert-rows\n      with:\n        table: tools.table\n        row_data: tools.row_data\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: update-rows\n      description: Update rows in a table matching filter criteria\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: supabase-db.update-rows\n      with:\n        table: tools.table\n        updates: tools.updates\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: invoke-function\n      description: Call a PostgreSQL stored function via RPC\n      hints:\n        readOnly: false\n        destructive: false\n      call: supabase-db.invoke-function\n  \
  \    with:\n        function_name: tools.function_name\n        args: tools.args\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-buckets\n      description: List all storage buckets in the project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: supabase-storage.list-buckets\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-bucket\n      description: Create a new storage bucket\n      hints:\n        readOnly: false\n        destructive: false\n      call: supabase-storage.create-bucket\n      with:\n        id: tools.id\n        public: tools.public\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-signed-url\n      description: Create a signed URL for temporary access to a private file\n      hints:\n        readOnly: false\n        destructive: false\n      call: supabase-storage.create-signed-url\n      with:\n        bucket_id: tools.bucket_id\n\
  \        object_name: tools.object_name\n        expiresIn: tools.expiresIn\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/supabase/refs/heads/main/capabilities/backend-as-a-service.yaml
tags:
- Supabase
- Backend As A Service
- Full Stack
- PostgreSQL
- Authentication
- Storage
tools:
- description: List all Supabase projects
  hints:
    openWorld: false
    readOnly: true
  name: list-projects
- description: Create a new Supabase project
  hints:
    destructive: false
    readOnly: false
  name: create-project
- description: Get details for a specific project
  hints:
    openWorld: false
    readOnly: true
  name: get-project
- description: Get project health and service status
  hints:
    openWorld: false
    readOnly: true
  name: get-project-health
- description: Get the API keys (anon, service_role) for a project
  hints:
    openWorld: false
    readOnly: true
  name: get-api-keys
- description: List all Edge Functions for a project
  hints:
    openWorld: false
    readOnly: true
  name: list-functions
- description: Deploy a new Edge Function to a project
  hints:
    destructive: false
    readOnly: false
  name: create-function
- description: List secrets stored for a project
  hints:
    openWorld: false
    readOnly: true
  name: list-secrets
- description: List all organizations the user belongs to
  hints:
    openWorld: false
    readOnly: true
  name: list-organizations
- description: Register a new user with email and password
  hints:
    destructive: false
    readOnly: false
  name: sign-up
- description: Sign in a user and get JWT access token
  hints:
    destructive: false
    readOnly: false
  name: sign-in
- description: Get the currently authenticated user's profile
  hints:
    openWorld: false
    readOnly: true
  name: get-user
- description: List all users in the project (admin)
  hints:
    openWorld: false
    readOnly: true
  name: list-users
- description: Query rows from a database table with filtering and pagination
  hints:
    openWorld: false
    readOnly: true
  name: select-rows
- description: Insert one or more rows into a database table
  hints:
    destructive: false
    readOnly: false
  name: insert-rows
- description: Update rows in a table matching filter criteria
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-rows
- description: Call a PostgreSQL stored function via RPC
  hints:
    destructive: false
    readOnly: false
  name: invoke-function
- description: List all storage buckets in the project
  hints:
    openWorld: false
    readOnly: true
  name: list-buckets
- description: Create a new storage bucket
  hints:
    destructive: false
    readOnly: false
  name: create-bucket
- description: Create a signed URL for temporary access to a private file
  hints:
    destructive: false
    readOnly: false
  name: create-signed-url
---
