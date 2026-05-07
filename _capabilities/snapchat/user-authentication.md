---
categories: []
consumed_apis: []
description: Workflow capability for integrating Snapchat user identity into third-party applications. Uses Login Kit OAuth 2.0 to authenticate users via their Snapchat credentials, retrieve user profile data including display name and Bitmoji avatar, and manage token lifecycle. Used by app developers building social features, personalization, or Snapchat-connected experiences.
layout: capability
name: Snapchat User Authentication
operations:
- description: Get Authenticated User Profile
  method: GET
  name: get-user-profile
  path: /v1/me
personas: []
provider_name: Snapchat
provider_slug: snapchat
search_terms:
- marketing
- social media
- ar
- retrieve the authenticated snapchat user's display name and bitmoji avatar
- get authenticated user profile
- oauth
- augmented reality
- messaging
- snapchat
- advertising
- get user profile
- identity
- get the authenticated user's snapchat profile
- user management
- authentication
slug: user-authentication
source_filename: user-authentication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Snapchat User Authentication\n  description: Workflow capability for integrating Snapchat user identity into third-party applications. Uses Login Kit OAuth\n    2.0 to authenticate users via their Snapchat credentials, retrieve user profile data including display name and Bitmoji\n    avatar, and manage token lifecycle. Used by app developers building social features, personalization, or Snapchat-connected\n    experiences.\n  tags:\n  - Authentication\n  - Identity\n  - OAuth\n  - Snapchat\n  - User Management\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SNAPCHAT_CLIENT_ID: SNAPCHAT_CLIENT_ID\n    SNAPCHAT_CLIENT_SECRET: SNAPCHAT_CLIENT_SECRET\n    SNAPCHAT_ACCESS_TOKEN: SNAPCHAT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: snapchat-login\n    baseUri: https://kit.snapchat.com/v1\n    description: Snapchat Login Kit API for OAuth user authentication\n    authentication:\n\
  \      type: bearer\n      token: '{{SNAPCHAT_ACCESS_TOKEN}}'\n    resources:\n    - name: user-profile\n      path: /me\n      description: Retrieve authenticated user profile\n      operations:\n      - name: get-user-profile\n        method: GET\n        description: Get Authenticated User Profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: snapchat-auth-api\n    description: Unified REST API for Snapchat user authentication and profile access.\n    resources:\n    - path: /v1/me\n      name: user-profile\n      description: Get the authenticated user's Snapchat profile\n      operations:\n      - method: GET\n        name: get-user-profile\n        description: Get Authenticated User Profile\n        call: snapchat-login.get-user-profile\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n\
  \    namespace: snapchat-auth-mcp\n    transport: http\n    description: MCP server for AI-assisted Snapchat user identity and profile management.\n    tools:\n    - name: get-user-profile\n      description: Retrieve the authenticated Snapchat user's display name and Bitmoji avatar\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snapchat-login.get-user-profile\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snapchat/refs/heads/main/capabilities/user-authentication.yaml
tags:
- Authentication
- Identity
- OAuth
- Snapchat
- User Management
tools:
- description: Retrieve the authenticated Snapchat user's display name and Bitmoji avatar
  hints:
    openWorld: false
    readOnly: true
  name: get-user-profile
---
