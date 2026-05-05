---
categories: []
consumed_apis:
- supabase-mgmt
- supabase-auth
- supabase-db
- supabase-storage
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
- register a new user
- manage supabase projects
- postgresql function invocation
- list secrets
- list organizations
- list all organizations the user belongs to
- project health status
- query table rows
- insert rows
- get project health and service status
- get the api keys (anon, service_role) for a project
- list users
- create function
- real time
- get api keys
- user login
- create bucket
- get user
- list all storage buckets in the project
- list functions
- edge functions
- backend as a service
- open source
- register a new user with email and password
- organization management
- sign in a user and get jwt access token
- invoke a postgresql function
- storage
- create a new project
- storage bucket management
- get details for a specific project
- get project details
- supabase
- create a new storage bucket
- list all edge functions for a project
- list projects
- create a storage bucket
- database
- user registration
- create a new supabase project
- get project health status
- list all users in the project (admin)
- query rows from a database table with filtering and pagination
- sign up
- invoke function
- postgresql
- sign in
- list all users
- sign in a user
- list all supabase projects
- list all projects
- deploy a new edge function to a project
- list secrets stored for a project
- get the currently authenticated user's profile
- create signed url
- database crud operations
- get project health
- insert one or more rows into a database table
- full stack
- list all organizations
- manage a specific project
- authentication
- get project api keys
- user management (admin)
- list all storage buckets
- list buckets
- update rows
- create a signed url for temporary access to a private file
- call a postgresql stored function via rpc
- create project
- get project
- update rows in a table matching filter criteria
- get health
- select rows
- retrieve project api keys
slug: backend-as-a-service
source_filename: backend-as-a-service.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Supabase Backend As A Service\"\n  description: >-\n    Unified workflow capability combining Supabase's database, authentication, and\n    storage services for full-stack application development. Used by developers\n    building web and mobile applications who need a complete backend without\n    managing infrastructure. Combines the Management API, Auth API, Database REST\n    API, and Storage API into a single coherent developer experience.\n  tags:\n    - Supabase\n    - Backend As A Service\n    - Full Stack\n    - PostgreSQL\n    - Authentication\n    - Storage\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SUPABASE_ACCESS_TOKEN: SUPABASE_ACCESS_TOKEN\n      SUPABASE_ANON_KEY: SUPABASE_ANON_KEY\n      SUPABASE_SERVICE_ROLE_KEY: SUPABASE_SERVICE_ROLE_KEY\n      SUPABASE_PROJECT_REF: SUPABASE_PROJECT_REF\n\ncapability:\n  consumes:\n    - import: supabase-mgmt\n      location:\
  \ ./shared/management-api.yaml\n    - import: supabase-auth\n      location: ./shared/auth-api.yaml\n    - import: supabase-db\n      location: ./shared/database-rest-api.yaml\n    - import: supabase-storage\n      location: ./shared/storage-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: supabase-baas-api\n      description: \"Unified REST API for Supabase backend services.\"\n      resources:\n        - path: /v1/projects\n          name: projects\n          description: \"Manage Supabase projects\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all projects\"\n              call: \"supabase-mgmt.list-projects\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create a new project\"\n              call: \"supabase-mgmt.create-project\"\n    \
  \          outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{ref}\n          name: project\n          description: \"Manage a specific project\"\n          operations:\n            - method: GET\n              name: get-project\n              description: \"Get project details\"\n              call: \"supabase-mgmt.get-project\"\n              with:\n                ref: \"rest.ref\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{ref}/api-keys\n          name: api-keys\n          description: \"Retrieve project API keys\"\n          operations:\n            - method: GET\n              name: get-api-keys\n              description: \"Get project API keys\"\n              call: \"supabase-mgmt.get-project-api-keys\"\n              with:\n                ref: \"rest.ref\"\n              outputParameters:\n                - type: object\n  \
  \                mapping: \"$.\"\n        - path: /v1/projects/{ref}/health\n          name: project-health\n          description: \"Project health status\"\n          operations:\n            - method: GET\n              name: get-health\n              description: \"Get project health status\"\n              call: \"supabase-mgmt.get-project-health\"\n              with:\n                ref: \"rest.ref\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/auth/signup\n          name: signup\n          description: \"User registration\"\n          operations:\n            - method: POST\n              name: sign-up\n              description: \"Register a new user\"\n              call: \"supabase-auth.sign-up\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/auth/signin\n          name: signin\n          description: \"User login\"\n        \
  \  operations:\n            - method: POST\n              name: sign-in\n              description: \"Sign in a user\"\n              call: \"supabase-auth.sign-in\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/auth/users\n          name: users\n          description: \"User management (admin)\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all users\"\n              call: \"supabase-auth.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data/{table}\n          name: table-data\n          description: \"Database CRUD operations\"\n          operations:\n            - method: GET\n              name: select-rows\n              description: \"Query table rows\"\n              call: \"supabase-db.select-rows\"\n              with:\n                table: \"rest.table\"\
  \n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: insert-rows\n              description: \"Insert rows\"\n              call: \"supabase-db.insert-rows\"\n              with:\n                table: \"rest.table\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/rpc/{function_name}\n          name: rpc\n          description: \"PostgreSQL function invocation\"\n          operations:\n            - method: POST\n              name: invoke-function\n              description: \"Invoke a PostgreSQL function\"\n              call: \"supabase-db.invoke-function\"\n              with:\n                function_name: \"rest.function_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/buckets\n          name: buckets\n          description: \"Storage\
  \ bucket management\"\n          operations:\n            - method: GET\n              name: list-buckets\n              description: \"List all storage buckets\"\n              call: \"supabase-storage.list-buckets\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-bucket\n              description: \"Create a storage bucket\"\n              call: \"supabase-storage.create-bucket\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations\n          name: organizations\n          description: \"Organization management\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List all organizations\"\n              call: \"supabase-mgmt.list-organizations\"\n              outputParameters:\n                - type: array\n                  mapping:\
  \ \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: supabase-baas-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Supabase application development.\"\n      tools:\n        - name: list-projects\n          description: \"List all Supabase projects\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supabase-mgmt.list-projects\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-project\n          description: \"Create a new Supabase project\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supabase-mgmt.create-project\"\n          with:\n            name: \"tools.name\"\n            organization_id: \"tools.organization_id\"\n            db_pass: \"tools.db_pass\"\n            region: \"tools.region\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n    \
  \    - name: get-project\n          description: \"Get details for a specific project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supabase-mgmt.get-project\"\n          with:\n            ref: \"tools.ref\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-project-health\n          description: \"Get project health and service status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supabase-mgmt.get-project-health\"\n          with:\n            ref: \"tools.ref\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-api-keys\n          description: \"Get the API keys (anon, service_role) for a project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supabase-mgmt.get-project-api-keys\"\n          with:\n            ref: \"tools.ref\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-functions\n          description: \"List all Edge Functions for a project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supabase-mgmt.list-functions\"\n          with:\n            ref: \"tools.ref\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-function\n          description: \"Deploy a new Edge Function to a project\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supabase-mgmt.create-function\"\n          with:\n            ref: \"tools.ref\"\n            slug: \"tools.slug\"\n            name: \"tools.name\"\n            body: \"tools.body\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-secrets\n          description: \"List secrets stored for a\
  \ project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supabase-mgmt.list-secrets\"\n          with:\n            ref: \"tools.ref\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: list-organizations\n          description: \"List all organizations the user belongs to\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supabase-mgmt.list-organizations\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: sign-up\n          description: \"Register a new user with email and password\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supabase-auth.sign-up\"\n          with:\n            email: \"tools.email\"\n            password: \"tools.password\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: sign-in\n          description: \"Sign in a user and get JWT access token\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supabase-auth.sign-in\"\n          with:\n            email: \"tools.email\"\n            password: \"tools.password\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Get the currently authenticated user's profile\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supabase-auth.get-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List all users in the project (admin)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supabase-auth.list-users\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: select-rows\n          description: \"Query rows from a database table with filtering and pagination\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supabase-db.select-rows\"\n          with:\n            table: \"tools.table\"\n            select: \"tools.select\"\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: insert-rows\n          description: \"Insert one or more rows into a database table\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supabase-db.insert-rows\"\n          with:\n            table: \"tools.table\"\n            row_data: \"tools.row_data\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: update-rows\n          description: \"Update rows in a table matching filter\
  \ criteria\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"supabase-db.update-rows\"\n          with:\n            table: \"tools.table\"\n            updates: \"tools.updates\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: invoke-function\n          description: \"Call a PostgreSQL stored function via RPC\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supabase-db.invoke-function\"\n          with:\n            function_name: \"tools.function_name\"\n            args: \"tools.args\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-buckets\n          description: \"List all storage buckets in the project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"supabase-storage.list-buckets\"\n    \
  \      outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-bucket\n          description: \"Create a new storage bucket\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supabase-storage.create-bucket\"\n          with:\n            id: \"tools.id\"\n            public: \"tools.public\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-signed-url\n          description: \"Create a signed URL for temporary access to a private file\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"supabase-storage.create-signed-url\"\n          with:\n            bucket_id: \"tools.bucket_id\"\n            object_name: \"tools.object_name\"\n            expiresIn: \"tools.expiresIn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
