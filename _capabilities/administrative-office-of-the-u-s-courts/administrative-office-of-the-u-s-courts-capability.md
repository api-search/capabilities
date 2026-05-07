---
categories: []
consumed_apis: []
description: API for authenticating users with PACER credentials.
layout: capability
name: Administrative Office of the U.S. Courts PACER Authentication API
operations:
- description: Administrative Office of the U.S. Courts Authenticate a user
  method: POST
  name: post-services-cso-auth
  path: /services/cso-auth
- description: Administrative Office of the U.S. Courts Logout a user
  method: POST
  name: post-services-cso-logout
  path: /services/cso-logout
personas: []
provider_name: Administrative Office of the U.S. Courts
provider_slug: administrative-office-of-the-u-s-courts
search_terms:
- judiciary
- post services cso logout
- administrative office of the u.s. courts authenticate a user
- the
- of
- administrative office of the u.s. courts logout a user
- legal
- federal government
- case records
- office
- post services cso auth
- pacer
- open data
- administrative
- courts
slug: administrative-office-of-the-u-s-courts-capability
source_filename: administrative-office-of-the-u-s-courts-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Administrative Office of the U.S. Courts PACER Authentication API\n  description: API for authenticating users with PACER credentials.\n  tags:\n  - Administrative\n  - Office\n  - Of\n  - The\n  - U\n  - S\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: administrative-office-of-the-u-s-courts\n    baseUri: https://qa-login.uscourts.gov\n    description: Administrative Office of the U.S. Courts PACER Authentication API HTTP API.\n    resources:\n    - name: services-cso-auth\n      path: /services/cso-auth\n      operations:\n      - name: post-services-cso-auth\n        method: POST\n        description: Administrative Office of the U.S. Courts Authenticate a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-cso-logout\n      path: /services/cso-logout\n      operations:\n\
  \      - name: post-services-cso-logout\n        method: POST\n        description: Administrative Office of the U.S. Courts Logout a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: administrative-office-of-the-u-s-courts-rest\n    description: REST adapter for Administrative Office of the U.S. Courts PACER Authentication API.\n    resources:\n    - path: /services/cso-auth\n      name: post-services-cso-auth\n      operations:\n      - method: POST\n        name: post-services-cso-auth\n        description: Administrative Office of the U.S. Courts Authenticate a user\n        call: administrative-office-of-the-u-s-courts.post-services-cso-auth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/cso-logout\n      name: post-services-cso-logout\n      operations:\n      - method: POST\n        name: post-services-cso-logout\n\
  \        description: Administrative Office of the U.S. Courts Logout a user\n        call: administrative-office-of-the-u-s-courts.post-services-cso-logout\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: administrative-office-of-the-u-s-courts-mcp\n    transport: http\n    description: MCP adapter for Administrative Office of the U.S. Courts PACER Authentication API for AI agent use.\n    tools:\n    - name: post-services-cso-auth\n      description: Administrative Office of the U.S. Courts Authenticate a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: administrative-office-of-the-u-s-courts.post-services-cso-auth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-services-cso-logout\n      description: Administrative Office of the U.S. Courts Logout a user\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: administrative-office-of-the-u-s-courts.post-services-cso-logout\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/administrative-office-of-the-u-s-courts/refs/heads/main/capabilities/administrative-office-of-the-u-s-courts-capability.yaml
tags:
- Administrative
- Office
- Of
- The
- U
- S
tools:
- description: Administrative Office of the U.S. Courts Authenticate a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-cso-auth
- description: Administrative Office of the U.S. Courts Logout a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-services-cso-logout
---
