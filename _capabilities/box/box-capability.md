---
categories: []
consumed_apis: []
description: Needs a description.
layout: capability
name: Box Authorize API
operations:
- description: Box Authorize user
  method: GET
  name: get-authorize
  path: /authorize
personas: []
provider_name: Box
provider_slug: box
search_terms:
- cloud storage
- documents
- file sharing
- enterprise
- collaboration
- api
- get authorize
- box authorize user
- box
- content management
slug: box-capability
source_filename: box-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Box Authorize API\n  description: Needs a description.\n  tags:\n  - Box\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: box\n    baseUri: https://api.example.com\n    description: Box Authorize API HTTP API.\n    resources:\n    - name: authorize\n      path: /authorize\n      operations:\n      - name: get-authorize\n        method: GET\n        description: Box Authorize user\n        inputParameters:\n        - name: response_type\n          in: query\n          type: string\n          required: true\n          description: The type of response we'd like to receive.\n        - name: client_id\n          in: query\n          type: string\n          required: true\n          description: The Client ID of the application that is requesting to authenticate the user. To get the Client ID\n            for your application, log in to your Box developer console an\n    \
  \    - name: redirect_uri\n          in: query\n          type: string\n          description: The URI to which Box redirects the browser after the user has granted or denied the application permission.\n            This URI match one of the redirect URIs in the confi\n        - name: state\n          in: query\n          type: string\n          description: A custom string of your choice. Box will pass the same string to the redirect URL when authentication\n            is complete. This parameter can be used to identify a user\n        - name: scope\n          in: query\n          type: string\n          description: A space-separated list of application scopes you'd like to authenticate the user for. This defaults\n            to all the scopes configured for the application in its conf\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: box-rest\n \
  \   description: REST adapter for Box Authorize API.\n    resources:\n    - path: /authorize\n      name: get-authorize\n      operations:\n      - method: GET\n        name: get-authorize\n        description: Box Authorize user\n        call: box.get-authorize\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: box-mcp\n    transport: http\n    description: MCP adapter for Box Authorize API for AI agent use.\n    tools:\n    - name: get-authorize\n      description: Box Authorize user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: box.get-authorize\n      with:\n        response_type: tools.response_type\n        client_id: tools.client_id\n        redirect_uri: tools.redirect_uri\n        state: tools.state\n        scope: tools.scope\n      inputParameters:\n      - name: response_type\n        type: string\n        description: The type of response we'd like\
  \ to receive.\n        required: true\n      - name: client_id\n        type: string\n        description: The Client ID of the application that is requesting to authenticate the user. To get the Client ID for\n          your application, log in to your Box developer console an\n        required: true\n      - name: redirect_uri\n        type: string\n        description: The URI to which Box redirects the browser after the user has granted or denied the application permission.\n          This URI match one of the redirect URIs in the confi\n      - name: state\n        type: string\n        description: A custom string of your choice. Box will pass the same string to the redirect URL when authentication\n          is complete. This parameter can be used to identify a user\n      - name: scope\n        type: string\n        description: A space-separated list of application scopes you'd like to authenticate the user for. This defaults to\n          all the scopes configured for the application\
  \ in its conf\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/box/refs/heads/main/capabilities/box-capability.yaml
tags:
- Box
- API
tools:
- description: Box Authorize user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-authorize
---
