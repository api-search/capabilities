---
categories: []
consumed_apis: []
description: The Fly.io Extensions API is a provider-facing HTTP interface that enables third-party services to integrate with the Fly.io platform as extension providers. When a Fly.io user provisions an extension via the flyctl CLI, Fly.io forwards the provisioning request to the provider's API with details about the requesting organization and user, and the provider responds with environment variable configuration that is attached to the target application. Providers must also support single sign-on login flows using OAuth, daily billing detail endpoints, and webhook delivery for resource lifecycle event
layout: capability
name: Fly.io Extensions API
operations:
- description: Provision an extension resource
  method: POST
  name: provisionextension
  path: /extensions
- description: Get extension resource details
  method: GET
  name: getextension
  path: /extensions/{extension_id}
- description: Update an extension resource
  method: PATCH
  name: updateextension
  path: /extensions/{extension_id}
- description: Delete an extension resource
  method: DELETE
  name: deleteextension
  path: /extensions/{extension_id}
- description: Initiate SSO for an extension
  method: GET
  name: initiatesso
  path: /extensions/{extension_id}/sso
- description: OAuth authorization endpoint
  method: GET
  name: oauthauthorize
  path: /oauth/authorize
- description: Exchange authorization code for access token
  method: POST
  name: oauthtoken
  path: /oauth/token
- description: Get OAuth token information
  method: GET
  name: gettokeninfo
  path: /oauth/token/info
- description: Send a webhook to Fly.io
  method: POST
  name: sendextensionwebhook
  path: /api/hooks/extensions/{provider_name}
- description: Receive a machine event webhook from Fly.io
  method: POST
  name: receiveextensionevent
  path: /extensions/events
personas: []
provider_name: fly-io
provider_slug: fly-io
search_terms:
- updateextension
- delete an extension resource
- initiatesso
- deleteextension
- fly
- provision an extension resource
- provisionextension
- io
- receive a machine event webhook from fly.io
- gettokeninfo
- exchange authorization code for access token
- api
- oauthauthorize
- initiate sso for an extension
- oauthtoken
- send a webhook to fly.io
- oauth authorization endpoint
- sendextensionwebhook
- getextension
- get extension resource details
- get oauth token information
- update an extension resource
- receiveextensionevent
slug: fly-io-capability
source_filename: fly-io-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Fly.io Extensions API\n  description: The Fly.io Extensions API is a provider-facing HTTP interface that enables third-party services to integrate\n    with the Fly.io platform as extension providers. When a Fly.io user provisions an extension via the flyctl CLI, Fly.io\n    forwards the provisioning request to the provider's API with details about the requesting organization and user, and the\n    provider responds with environment variable configuration that is attached to the target application. Providers must also\n    support single sign-on login flows using OAuth, daily billing detail endpoints, and webhook delivery for resource lifecycle\n    event\n  tags:\n  - Fly\n  - Io\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fly-io\n    baseUri: https://api.example.com\n    description: Fly.io Extensions API HTTP API.\n    authentication:\n      type: bearer\n   \
  \   token: '{{FLY_IO_TOKEN}}'\n    resources:\n    - name: extensions\n      path: /extensions\n      operations:\n      - name: provisionextension\n        method: POST\n        description: Provision an extension resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extensions-extension-id\n      path: /extensions/{extension_id}\n      operations:\n      - name: getextension\n        method: GET\n        description: Get extension resource details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateextension\n        method: PATCH\n        description: Update an extension resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteextension\n        method: DELETE\n        description: Delete an extension\
  \ resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extensions-extension-id-sso\n      path: /extensions/{extension_id}/sso\n      operations:\n      - name: initiatesso\n        method: GET\n        description: Initiate SSO for an extension\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth-authorize\n      path: /oauth/authorize\n      operations:\n      - name: oauthauthorize\n        method: GET\n        description: OAuth authorization endpoint\n        inputParameters:\n        - name: client_id\n          in: query\n          type: string\n          required: true\n          description: OAuth client ID issued to the extension provider by Fly.io.\n        - name: response_type\n          in: query\n          type: string\n          required: true\n          description: OAuth response type.\
  \ Must be code for the authorization code flow.\n        - name: redirect_uri\n          in: query\n          type: string\n          required: true\n          description: Provider callback URL to redirect the user to after authorization.\n        - name: scope\n          in: query\n          type: string\n          description: Space-separated list of requested OAuth scopes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth-token\n      path: /oauth/token\n      operations:\n      - name: oauthtoken\n        method: POST\n        description: Exchange authorization code for access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth-token-info\n      path: /oauth/token/info\n      operations:\n      - name: gettokeninfo\n        method: GET\n        description: Get OAuth token information\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-hooks-extensions-provider-name\n      path: /api/hooks/extensions/{provider_name}\n      operations:\n      - name: sendextensionwebhook\n        method: POST\n        description: Send a webhook to Fly.io\n        inputParameters:\n        - name: provider_name\n          in: path\n          type: string\n          required: true\n          description: The slug identifier of the extension provider registered with Fly.io.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extensions-events\n      path: /extensions/events\n      operations:\n      - name: receiveextensionevent\n        method: POST\n        description: Receive a machine event webhook from Fly.io\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fly-io-rest\n    description: REST adapter for Fly.io Extensions API.\n    resources:\n    - path: /extensions\n      name: provisionextension\n      operations:\n      - method: POST\n        name: provisionextension\n        description: Provision an extension resource\n        call: fly-io.provisionextension\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extensions/{extension_id}\n      name: getextension\n      operations:\n      - method: GET\n        name: getextension\n        description: Get extension resource details\n        call: fly-io.getextension\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extensions/{extension_id}\n      name: updateextension\n      operations:\n      - method: PATCH\n        name: updateextension\n        description: Update an extension resource\n        call: fly-io.updateextension\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extensions/{extension_id}\n      name: deleteextension\n      operations:\n      - method: DELETE\n        name: deleteextension\n        description: Delete an extension resource\n        call: fly-io.deleteextension\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extensions/{extension_id}/sso\n      name: initiatesso\n      operations:\n      - method: GET\n        name: initiatesso\n        description: Initiate SSO for an extension\n        call: fly-io.initiatesso\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth/authorize\n      name: oauthauthorize\n      operations:\n      - method: GET\n        name: oauthauthorize\n        description: OAuth authorization endpoint\n        call: fly-io.oauthauthorize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth/token\n      name:\
  \ oauthtoken\n      operations:\n      - method: POST\n        name: oauthtoken\n        description: Exchange authorization code for access token\n        call: fly-io.oauthtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth/token/info\n      name: gettokeninfo\n      operations:\n      - method: GET\n        name: gettokeninfo\n        description: Get OAuth token information\n        call: fly-io.gettokeninfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/hooks/extensions/{provider_name}\n      name: sendextensionwebhook\n      operations:\n      - method: POST\n        name: sendextensionwebhook\n        description: Send a webhook to Fly.io\n        call: fly-io.sendextensionwebhook\n        with:\n          provider_name: rest.provider_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /extensions/events\n      name: receiveextensionevent\n      operations:\n\
  \      - method: POST\n        name: receiveextensionevent\n        description: Receive a machine event webhook from Fly.io\n        call: fly-io.receiveextensionevent\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fly-io-mcp\n    transport: http\n    description: MCP adapter for Fly.io Extensions API for AI agent use.\n    tools:\n    - name: provisionextension\n      description: Provision an extension resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fly-io.provisionextension\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getextension\n      description: Get extension resource details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fly-io.getextension\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateextension\n      description:\
  \ Update an extension resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fly-io.updateextension\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteextension\n      description: Delete an extension resource\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: fly-io.deleteextension\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiatesso\n      description: Initiate SSO for an extension\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fly-io.initiatesso\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: oauthauthorize\n      description: OAuth authorization endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fly-io.oauthauthorize\n      with:\n        client_id:\
  \ tools.client_id\n        response_type: tools.response_type\n        redirect_uri: tools.redirect_uri\n        scope: tools.scope\n      inputParameters:\n      - name: client_id\n        type: string\n        description: OAuth client ID issued to the extension provider by Fly.io.\n        required: true\n      - name: response_type\n        type: string\n        description: OAuth response type. Must be code for the authorization code flow.\n        required: true\n      - name: redirect_uri\n        type: string\n        description: Provider callback URL to redirect the user to after authorization.\n        required: true\n      - name: scope\n        type: string\n        description: Space-separated list of requested OAuth scopes.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: oauthtoken\n      description: Exchange authorization code for access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: fly-io.oauthtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettokeninfo\n      description: Get OAuth token information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fly-io.gettokeninfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendextensionwebhook\n      description: Send a webhook to Fly.io\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fly-io.sendextensionwebhook\n      with:\n        provider_name: tools.provider_name\n      inputParameters:\n      - name: provider_name\n        type: string\n        description: The slug identifier of the extension provider registered with Fly.io.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: receiveextensionevent\n      description: Receive a machine event webhook from Fly.io\n   \
  \   hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fly-io.receiveextensionevent\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FLY_IO_TOKEN: FLY_IO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fly-io/refs/heads/main/capabilities/fly-io-capability.yaml
tags:
- Fly
- Io
- API
tools:
- description: Provision an extension resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provisionextension
- description: Get extension resource details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getextension
- description: Update an extension resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateextension
- description: Delete an extension resource
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteextension
- description: Initiate SSO for an extension
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: initiatesso
- description: OAuth authorization endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: oauthauthorize
- description: Exchange authorization code for access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oauthtoken
- description: Get OAuth token information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettokeninfo
- description: Send a webhook to Fly.io
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendextensionwebhook
- description: Receive a machine event webhook from Fly.io
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: receiveextensionevent
---
