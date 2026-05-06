---
categories: []
consumed_apis: []
description: The Firebase Cloud Messaging HTTP v1 API enables sending notification and data messages to client apps on Android, iOS, and the web. It supports per-platform message customization, topic messaging, and condition-based targeting.
layout: capability
name: Google Firebase Firebase Cloud Messaging API (FCM)
operations:
- description: Google Firebase Send a message
  method: POST
  name: sendmessage
  path: /projects/{projectId}/messages:send
personas: []
provider_name: Google Firebase
provider_slug: google-firebase
search_terms:
- google firebase send a message
- mobile
- firebase
- hosting
- google
- sendmessage
- api
- analytics
- authentication
- google cloud
- backend as a service
- real-time database
- cloud messaging
slug: google-firebase-capability
source_filename: google-firebase-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Firebase Firebase Cloud Messaging API (FCM)\n  description: The Firebase Cloud Messaging HTTP v1 API enables sending notification and data messages to client apps on Android,\n    iOS, and the web. It supports per-platform message customization, topic messaging, and condition-based targeting.\n  tags:\n  - Google\n  - Firebase\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-firebase\n    baseUri: https://fcm.googleapis.com/v1\n    description: Google Firebase Firebase Cloud Messaging API (FCM) HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_FIREBASE_TOKEN}}'\n    resources:\n    - name: projects-projectid-messages-send\n      path: /projects/{projectId}/messages:send\n      operations:\n      - name: sendmessage\n        method: POST\n        description: Google Firebase Send a message\n        inputParameters:\n        - name:\
  \ projectId\n          in: path\n          type: string\n          required: true\n          description: The Firebase project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-firebase-rest\n    description: REST adapter for Google Firebase Firebase Cloud Messaging API (FCM).\n    resources:\n    - path: /projects/{projectId}/messages:send\n      name: sendmessage\n      operations:\n      - method: POST\n        name: sendmessage\n        description: Google Firebase Send a message\n        call: google-firebase.sendmessage\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-firebase-mcp\n    transport: http\n    description: MCP adapter for Google Firebase Firebase Cloud Messaging API (FCM) for AI agent use.\n  \
  \  tools:\n    - name: sendmessage\n      description: Google Firebase Send a message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-firebase.sendmessage\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: The Firebase project ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_FIREBASE_TOKEN: GOOGLE_FIREBASE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-firebase/refs/heads/main/capabilities/google-firebase-capability.yaml
tags:
- Google
- Firebase
- API
tools:
- description: Google Firebase Send a message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendmessage
---
