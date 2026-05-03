---
categories: []
consumed_apis:
- appwrite
description: Workflow capability for building mobile and web application backends using Appwrite. Provides AI-assisted management of users, databases, file storage, and backend configuration for developers building with Appwrite as their Backend-as-a-Service.
layout: capability
name: Appwrite Mobile Backend
operations: []
personas: []
provider_name: Appwrite
provider_slug: appwrite
search_terms:
- lists appwrite databases available in the backend project
- appwrite
- open source
- list project users
- list storage buckets
- mobile
- developer building ios, android, or web apps with appwrite
- creates a new user account in the appwrite backend for a mobile app
- lists all registered users in the appwrite project backend
- backends
- applications
- cloud function deployment and execution
- developer tools
- configure and manage a mobile app backend with appwrite
- user authentication and account management
- database and file storage management
- list databases
- provision user
- administrator managing appwrite project users and configuration
- lists file storage buckets configured in the appwrite backend
- backend-as-a-service
slug: mobile-backend
source_filename: mobile-backend.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Appwrite Mobile Backend\n  description: >-\n    Workflow capability for building mobile and web application backends using Appwrite.\n    Provides AI-assisted management of users, databases, file storage, and backend\n    configuration for developers building with Appwrite as their Backend-as-a-Service.\n  tags:\n    - Appwrite\n    - Mobile\n    - Backend-as-a-Service\n    - Open Source\n    - Developer Tools\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APPWRITE_PROJECT_ID: APPWRITE_PROJECT_ID\n      APPWRITE_API_KEY: APPWRITE_API_KEY\n\ncapability:\n  consumes:\n    - import: appwrite\n      location: ./shared/appwrite-api.yaml\n\n  exposes:\n    - type: mcp\n      port: 9090\n      namespace: mobile-backend-mcp\n      transport: http\n      description: MCP server for AI-assisted mobile and web backend management with Appwrite.\n      tools:\n        - name: list-project-users\n\
  \          description: Lists all registered users in the Appwrite project backend\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appwrite.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: provision-user\n          description: Creates a new user account in the Appwrite backend for a mobile app\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"appwrite.create-user\"\n          with:\n            userId: \"tools.userId\"\n            email: \"tools.email\"\n            password: \"tools.password\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-databases\n          description: Lists Appwrite databases available in the backend project\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"\
  appwrite.list-databases\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-storage-buckets\n          description: Lists file storage buckets configured in the Appwrite backend\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appwrite.list-buckets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
