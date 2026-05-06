---
categories: []
consumed_apis: []
description: Google Voice is a telecommunications service by Google that provides call forwarding, voicemail, text messaging, and voice calling. While Google Voice does not offer an official public REST API, the platform integrates with Google Workspace for business telephony. This specification documents the known endpoints and capabilities based on the Google Workspace Admin SDK and related voice management interfaces for provisioning and managing Google Voice services programmatically.
layout: capability
name: Google Voice API
operations:
- description: Google Voice List Buildings
  method: GET
  name: listbuildings
  path: /admin/directory/v1/customer/{customerId}/resources/buildings
- description: Google Voice List Users
  method: GET
  name: listusers
  path: /admin/directory/v1/users
- description: Google Voice Get User
  method: GET
  name: getuser
  path: /admin/directory/v1/users/{userKey}
personas: []
provider_name: Google Voice
provider_slug: google-voice
search_terms:
- google voice list users
- google voice get user
- getuser
- voip
- messaging
- voicemail
- voice
- google
- api
- telecommunications
- listusers
- google voice
- listbuildings
- google voice list buildings
- phone
slug: google-voice-capability
source_filename: google-voice-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Voice API\n  description: Google Voice is a telecommunications service by Google that provides call forwarding, voicemail, text messaging,\n    and voice calling. While Google Voice does not offer an official public REST API, the platform integrates with Google\n    Workspace for business telephony. This specification documents the known endpoints and capabilities based on the Google\n    Workspace Admin SDK and related voice management interfaces for provisioning and managing Google Voice services programmatically.\n  tags:\n  - Google\n  - Voice\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-voice\n    baseUri: https://admin.googleapis.com\n    description: Google Voice API HTTP API.\n    resources:\n    - name: admin-directory-v1-customer-customerid-resources\n      path: /admin/directory/v1/customer/{customerId}/resources/buildings\n      operations:\n\
  \      - name: listbuildings\n        method: GET\n        description: Google Voice List Buildings\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: The Google Workspace customer ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-directory-v1-users\n      path: /admin/directory/v1/users\n      operations:\n      - name: listusers\n        method: GET\n        description: Google Voice List Users\n        inputParameters:\n        - name: domain\n          in: query\n          type: string\n          description: The domain name.\n        - name: maxResults\n          in: query\n          type: integer\n          description: Maximum number of results.\n        - name: pageToken\n          in: query\n          type: string\n          description: Token for pagination.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-directory-v1-users-userkey\n      path: /admin/directory/v1/users/{userKey}\n      operations:\n      - name: getuser\n        method: GET\n        description: Google Voice Get User\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n          description: The user's email address or unique ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-voice-rest\n    description: REST adapter for Google Voice API.\n    resources:\n    - path: /admin/directory/v1/customer/{customerId}/resources/buildings\n      name: listbuildings\n      operations:\n      - method: GET\n        name: listbuildings\n        description: Google Voice List Buildings\n        call: google-voice.listbuildings\n\
  \        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: Google Voice List Users\n        call: google-voice.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/directory/v1/users/{userKey}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Google Voice Get User\n        call: google-voice.getuser\n        with:\n          userKey: rest.userKey\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-voice-mcp\n    transport: http\n    description: MCP adapter for Google Voice API for AI agent use.\n    tools:\n    - name: listbuildings\n      description: Google Voice List Buildings\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-voice.listbuildings\n      with:\n        customerId: tools.customerId\n      inputParameters:\n      - name: customerId\n        type: string\n        description: The Google Workspace customer ID.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: Google Voice List Users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-voice.listusers\n      with:\n        domain: tools.domain\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: domain\n        type: string\n        description: The domain name.\n      - name: maxResults\n        type: integer\n        description: Maximum number of results.\n      - name: pageToken\n        type: string\n        description: Token for pagination.\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Google Voice Get User\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-voice.getuser\n      with:\n        userKey: tools.userKey\n      inputParameters:\n      - name: userKey\n        type: string\n        description: The user's email address or unique ID.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-voice/refs/heads/main/capabilities/google-voice-capability.yaml
tags:
- Google
- Voice
- API
tools:
- description: Google Voice List Buildings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuildings
- description: Google Voice List Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Google Voice Get User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
---
