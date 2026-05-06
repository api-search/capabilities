---
categories: []
consumed_apis: []
description: Workflow capability for building mobile and web application backends using Appwrite. Provides AI-assisted management of users, databases, file storage, and backend configuration for developers building with Appwrite as their Backend-as-a-Service.
layout: capability
name: Appwrite Mobile Backend
operations: []
personas: []
provider_name: Appwrite
provider_slug: appwrite
search_terms:
- developer tools
- database and file storage management
- lists appwrite databases available in the backend project
- applications
- cloud function deployment and execution
- backend-as-a-service
- provision user
- user authentication and account management
- appwrite
- creates a new user account in the appwrite backend for a mobile app
- backends
- open source
- developer building ios, android, or web apps with appwrite
- list storage buckets
- configure and manage a mobile app backend with appwrite
- list databases
- administrator managing appwrite project users and configuration
- list project users
- mobile
- lists file storage buckets configured in the appwrite backend
- lists all registered users in the appwrite project backend
slug: mobile-backend
source_filename: mobile-backend.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Appwrite Mobile Backend\n  description: Workflow capability for building mobile and web application backends using Appwrite. Provides AI-assisted management\n    of users, databases, file storage, and backend configuration for developers building with Appwrite as their Backend-as-a-Service.\n  tags:\n  - Appwrite\n  - Mobile\n  - Backend-as-a-Service\n  - Open Source\n  - Developer Tools\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APPWRITE_PROJECT_ID: APPWRITE_PROJECT_ID\n    APPWRITE_API_KEY: APPWRITE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: appwrite\n    baseUri: https://cloud.appwrite.io/v1\n    description: Appwrite Cloud API\n    authentication:\n      type: apikey\n      header: X-Appwrite-Project\n      key: '{{APPWRITE_PROJECT_ID}}'\n    resources:\n    - name: account\n      path: /account\n      description: User account management\n      operations:\n  \
  \    - name: get-account\n        method: GET\n        description: Returns authenticated user account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: Server-side user management\n      operations:\n      - name: list-users\n        method: GET\n        description: Returns a list of project users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Creates a new user account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userId: '{{tools.userId}}'\n            email: '{{tools.email}}'\n            password: '{{tools.password}}'\n            name: '{{tools.name}}'\n\
  \    - name: databases\n      path: /databases\n      description: Database management\n      operations:\n      - name: list-databases\n        method: GET\n        description: Returns a list of project databases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: buckets\n      path: /storage/buckets\n      description: Storage bucket management\n      operations:\n      - name: list-buckets\n        method: GET\n        description: Returns a list of storage buckets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9090\n    namespace: mobile-backend-mcp\n    transport: http\n    description: MCP server for AI-assisted mobile and web backend management with Appwrite.\n    tools:\n    - name: list-project-users\n      description: Lists all registered users in the Appwrite project backend\n\
  \      hints:\n        readOnly: true\n        idempotent: true\n      call: appwrite.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provision-user\n      description: Creates a new user account in the Appwrite backend for a mobile app\n      hints:\n        readOnly: false\n        destructive: false\n      call: appwrite.create-user\n      with:\n        userId: tools.userId\n        email: tools.email\n        password: tools.password\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-databases\n      description: Lists Appwrite databases available in the backend project\n      hints:\n        readOnly: true\n        idempotent: true\n      call: appwrite.list-databases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-storage-buckets\n      description: Lists file storage buckets configured in the Appwrite backend\n      hints:\n        readOnly:\
  \ true\n        idempotent: true\n      call: appwrite.list-buckets\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/appwrite/refs/heads/main/capabilities/mobile-backend.yaml
tags:
- Appwrite
- Mobile
- Backend-as-a-Service
- Open Source
- Developer Tools
tools:
- description: Lists all registered users in the Appwrite project backend
  hints:
    idempotent: true
    readOnly: true
  name: list-project-users
- description: Creates a new user account in the Appwrite backend for a mobile app
  hints:
    destructive: false
    readOnly: false
  name: provision-user
- description: Lists Appwrite databases available in the backend project
  hints:
    idempotent: true
    readOnly: true
  name: list-databases
- description: Lists file storage buckets configured in the Appwrite backend
  hints:
    idempotent: true
    readOnly: true
  name: list-storage-buckets
---
