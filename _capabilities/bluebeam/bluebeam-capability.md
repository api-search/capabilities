---
categories: []
consumed_apis: []
description: The Bluebeam Studio API enables programmatic access to Studio Sessions for document collaboration, markup management, and PDF review workflows. OAuth 2.0 REST APIs allow third-party applications to create and manage studio sessions, retrieve markup data, and integrate document annotations into AEC construction workflows.
layout: capability
name: Bluebeam Studio API
operations:
- description: List sessions
  method: GET
  name: listsessions
  path: /studio/v1/sessions
- description: Create a Studio Session
  method: POST
  name: createsession
  path: /studio/v1/sessions
- description: Get session by ID
  method: GET
  name: getsession
  path: /studio/v1/sessions/{sessionId}
- description: Update session
  method: PATCH
  name: updatesession
  path: /studio/v1/sessions/{sessionId}
- description: Finish/close a session
  method: POST
  name: finishsession
  path: /studio/v1/sessions/{sessionId}/finish
- description: List session documents
  method: GET
  name: listsessiondocuments
  path: /studio/v1/sessions/{sessionId}/documents
- description: Upload document to session
  method: POST
  name: uploadsessiondocument
  path: /studio/v1/sessions/{sessionId}/documents
- description: Get document markups
  method: GET
  name: getdocumentmarkups
  path: /studio/v1/sessions/{sessionId}/documents/{documentId}/markups
- description: List session users/attendees
  method: GET
  name: listsessionusers
  path: /studio/v1/sessions/{sessionId}/users
- description: Invite user to session
  method: POST
  name: invitesessionuser
  path: /studio/v1/sessions/{sessionId}/users
personas: []
provider_name: bluebeam
provider_slug: bluebeam
search_terms:
- createsession
- listsessions
- list session documents
- api
- uploadsessiondocument
- get document markups
- invite user to session
- bluebeam
- finish/close a session
- upload document to session
- finishsession
- get session by id
- update session
- invitesessionuser
- updatesession
- listsessiondocuments
- list session users/attendees
- list sessions
- create a studio session
- getdocumentmarkups
- getsession
- listsessionusers
slug: bluebeam-capability
source_filename: bluebeam-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bluebeam Studio API\n  description: The Bluebeam Studio API enables programmatic access to Studio Sessions for document collaboration, markup management,\n    and PDF review workflows. OAuth 2.0 REST APIs allow third-party applications to create and manage studio sessions, retrieve\n    markup data, and integrate document annotations into AEC construction workflows.\n  tags:\n  - Bluebeam\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bluebeam\n    baseUri: https://api.bluebeam.com\n    description: Bluebeam Studio API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{BLUEBEAM_TOKEN}}'\n    resources:\n    - name: studio-v1-sessions\n      path: /studio/v1/sessions\n      operations:\n      - name: listsessions\n        method: GET\n        description: List sessions\n        inputParameters:\n        - name: status\n          in: query\n         \
  \ type: string\n          description: Filter by session status\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsession\n        method: POST\n        description: Create a Studio Session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: studio-v1-sessions-sessionid\n      path: /studio/v1/sessions/{sessionId}\n      operations:\n      - name: getsession\n        method: GET\n        description: Get session by ID\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: updatesession\n        method: PATCH\n        description: Update session\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: studio-v1-sessions-sessionid-finish\n      path: /studio/v1/sessions/{sessionId}/finish\n      operations:\n      - name: finishsession\n        method: POST\n        description: Finish/close a session\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: studio-v1-sessions-sessionid-documents\n      path: /studio/v1/sessions/{sessionId}/documents\n      operations:\n      - name: listsessiondocuments\n        method: GET\n        description:\
  \ List session documents\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadsessiondocument\n        method: POST\n        description: Upload document to session\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: studio-v1-sessions-sessionid-documents-documenti\n      path: /studio/v1/sessions/{sessionId}/documents/{documentId}/markups\n      operations:\n      - name: getdocumentmarkups\n        method: GET\n        description: Get document markups\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required:\
  \ true\n        - name: documentId\n          in: path\n          type: string\n          required: true\n        - name: pageNumber\n          in: query\n          type: integer\n          description: Filter markups by page number\n        - name: markupType\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: studio-v1-sessions-sessionid-users\n      path: /studio/v1/sessions/{sessionId}/users\n      operations:\n      - name: listsessionusers\n        method: GET\n        description: List session users/attendees\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invitesessionuser\n        method: POST\n        description: Invite user to session\n\
  \        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bluebeam-rest\n    description: REST adapter for Bluebeam Studio API.\n    resources:\n    - path: /studio/v1/sessions\n      name: listsessions\n      operations:\n      - method: GET\n        name: listsessions\n        description: List sessions\n        call: bluebeam.listsessions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /studio/v1/sessions\n      name: createsession\n      operations:\n      - method: POST\n        name: createsession\n        description: Create a Studio Session\n        call: bluebeam.createsession\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /studio/v1/sessions/{sessionId}\n\
  \      name: getsession\n      operations:\n      - method: GET\n        name: getsession\n        description: Get session by ID\n        call: bluebeam.getsession\n        with:\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /studio/v1/sessions/{sessionId}\n      name: updatesession\n      operations:\n      - method: PATCH\n        name: updatesession\n        description: Update session\n        call: bluebeam.updatesession\n        with:\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /studio/v1/sessions/{sessionId}/finish\n      name: finishsession\n      operations:\n      - method: POST\n        name: finishsession\n        description: Finish/close a session\n        call: bluebeam.finishsession\n        with:\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /studio/v1/sessions/{sessionId}/documents\n      name: listsessiondocuments\n      operations:\n      - method: GET\n        name: listsessiondocuments\n        description: List session documents\n        call: bluebeam.listsessiondocuments\n        with:\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /studio/v1/sessions/{sessionId}/documents\n      name: uploadsessiondocument\n      operations:\n      - method: POST\n        name: uploadsessiondocument\n        description: Upload document to session\n        call: bluebeam.uploadsessiondocument\n        with:\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /studio/v1/sessions/{sessionId}/documents/{documentId}/markups\n      name: getdocumentmarkups\n      operations:\n      - method: GET\n        name: getdocumentmarkups\n        description: Get document markups\n        call:\
  \ bluebeam.getdocumentmarkups\n        with:\n          sessionId: rest.sessionId\n          documentId: rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /studio/v1/sessions/{sessionId}/users\n      name: listsessionusers\n      operations:\n      - method: GET\n        name: listsessionusers\n        description: List session users/attendees\n        call: bluebeam.listsessionusers\n        with:\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /studio/v1/sessions/{sessionId}/users\n      name: invitesessionuser\n      operations:\n      - method: POST\n        name: invitesessionuser\n        description: Invite user to session\n        call: bluebeam.invitesessionuser\n        with:\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bluebeam-mcp\n   \
  \ transport: http\n    description: MCP adapter for Bluebeam Studio API for AI agent use.\n    tools:\n    - name: listsessions\n      description: List sessions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bluebeam.listsessions\n      with:\n        status: tools.status\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by session status\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsession\n      description: Create a Studio Session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bluebeam.createsession\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ getsession\n      description: Get session by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bluebeam.getsession\n      with:\n        sessionId: tools.sessionId\n      inputParameters:\n      - name: sessionId\n        type: string\n        description: sessionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesession\n      description: Update session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bluebeam.updatesession\n      with:\n        sessionId: tools.sessionId\n      inputParameters:\n      - name: sessionId\n        type: string\n        description: sessionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: finishsession\n      description: Finish/close a session\n      hints:\n        readOnly: false\n        destructive: false\n     \
  \   idempotent: false\n      call: bluebeam.finishsession\n      with:\n        sessionId: tools.sessionId\n      inputParameters:\n      - name: sessionId\n        type: string\n        description: sessionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsessiondocuments\n      description: List session documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bluebeam.listsessiondocuments\n      with:\n        sessionId: tools.sessionId\n      inputParameters:\n      - name: sessionId\n        type: string\n        description: sessionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadsessiondocument\n      description: Upload document to session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bluebeam.uploadsessiondocument\n      with:\n       \
  \ sessionId: tools.sessionId\n      inputParameters:\n      - name: sessionId\n        type: string\n        description: sessionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdocumentmarkups\n      description: Get document markups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bluebeam.getdocumentmarkups\n      with:\n        sessionId: tools.sessionId\n        documentId: tools.documentId\n        pageNumber: tools.pageNumber\n        markupType: tools.markupType\n      inputParameters:\n      - name: sessionId\n        type: string\n        description: sessionId\n        required: true\n      - name: documentId\n        type: string\n        description: documentId\n        required: true\n      - name: pageNumber\n        type: integer\n        description: Filter markups by page number\n      - name: markupType\n        type: string\n        description: markupType\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsessionusers\n      description: List session users/attendees\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bluebeam.listsessionusers\n      with:\n        sessionId: tools.sessionId\n      inputParameters:\n      - name: sessionId\n        type: string\n        description: sessionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: invitesessionuser\n      description: Invite user to session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bluebeam.invitesessionuser\n      with:\n        sessionId: tools.sessionId\n      inputParameters:\n      - name: sessionId\n        type: string\n        description: sessionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n\
  \  keys:\n    BLUEBEAM_TOKEN: BLUEBEAM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bluebeam/refs/heads/main/capabilities/bluebeam-capability.yaml
tags:
- Bluebeam
- API
tools:
- description: List sessions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsessions
- description: Create a Studio Session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsession
- description: Get session by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsession
- description: Update session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesession
- description: Finish/close a session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: finishsession
- description: List session documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsessiondocuments
- description: Upload document to session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadsessiondocument
- description: Get document markups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocumentmarkups
- description: List session users/attendees
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsessionusers
- description: Invite user to session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invitesessionuser
---
