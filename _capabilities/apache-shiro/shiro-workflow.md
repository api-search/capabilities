---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Shiro Workflow
operations: []
personas: []
provider_name: Apache Shiro
provider_slug: apache-shiro
search_terms:
- cryptography
- identity verification and credential management
- apache
- security
- access control and permission enforcement
- administrator managing users, roles, and permissions
- authorization
- end-to-end user login, session, and logout workflow
- permission and role checking for protected resources
- password hashing and data encryption
- developer integrating shiro security into java applications
- authentication
- java
- open source
slug: shiro-workflow
source_filename: shiro-workflow.yaml
source_heading: Capability Spec
source_yaml: "name: Apache Shiro Security Workflow\ndescription: Workflow capability for authentication, authorization, and session management using Apache Shiro.\nversion: 1.0.0-alpha1\napis:\n  - name: Apache Shiro REST API\n    url: https://raw.githubusercontent.com/api-evangelist/apache-shiro/refs/heads/main/apis.yml\nshared:\n  - url: capabilities/shared/shiro-api.yaml\nworkflow:\n  name: shiro-workflow\n  description: Authenticate users, check permissions, and manage sessions with Apache Shiro.\n  steps:\n    - name: login\n      description: Authenticate user credentials\n      api: Apache Shiro REST API\n      operation: login\n    - name: check-permission\n      description: Verify user has required permission\n      api: Apache Shiro REST API\n      operation: checkPermission\n    - name: get-roles\n      description: Get current user roles\n      api: Apache Shiro REST API\n      operation: getCurrentRoles\n    - name: logout\n      description: Invalidate user session\n     \
  \ api: Apache Shiro REST API\n      operation: logout\nexposes:\n  - type: rest\n    port: 8080\n    paths:\n      - /auth/login\n      - /auth/logout\n      - /auth/token\n      - /sessions/{sessionId}\n      - /auth/check\n      - /auth/roles\n      - /users\n      - /crypto/hash\n  - type: mcp\n    port: 9090\n    tools:\n      - name: login\n        description: Authenticate user\n        operation: login\n      - name: logout\n        description: Logout user\n        operation: logout\n      - name: generate-token\n        description: Generate auth token\n        operation: generateToken\n      - name: check-permission\n        description: Check user permission\n        operation: checkPermission\n      - name: get-current-roles\n        description: Get current user roles\n        operation: getCurrentRoles\n      - name: list-users\n        description: List users\n        operation: listUsers\n      - name: create-user\n        description: Create a user\n        operation:\
  \ createUser\n      - name: hash-password\n        description: Hash a password securely\n        operation: hashPassword\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-shiro/refs/heads/main/capabilities/shiro-workflow.yaml
tags: []
tools: []
---
