---
categories: []
consumed_apis: []
description: The Ocelot Administration API allows runtime changes to the Ocelot .NET API Gateway configuration via an authenticated HTTP API. It supports retrieving and overwriting the active configuration and clearing output cache regions without restarting the gateway. The API is authenticated via Bearer tokens issued by Ocelot's built-in IdentityServer or an external identity provider.
layout: capability
name: Ocelot Administration API
operations:
- description: Issue an admin access token
  method: POST
  name: issueadmintoken
  path: /administration/connect/token
- description: Get current Ocelot configuration
  method: GET
  name: getconfiguration
  path: /administration/configuration
- description: Overwrite Ocelot configuration
  method: POST
  name: setconfiguration
  path: /administration/configuration
- description: Clear an output cache region
  method: DELETE
  name: clearcacheregion
  path: /administration/outputcache/{region}
personas: []
provider_name: Ocelot
provider_slug: ocelot
search_terms:
- issueadmintoken
- .net
- issue an admin access token
- getconfiguration
- clear an output cache region
- api
- ocelot
- setconfiguration
- clearcacheregion
- microservices
- overwrite ocelot configuration
- api gateway
- open source
- get current ocelot configuration
slug: ocelot-capability
source_filename: ocelot-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ocelot Administration API\n  description: The Ocelot Administration API allows runtime changes to the Ocelot .NET API Gateway configuration via an authenticated\n    HTTP API. It supports retrieving and overwriting the active configuration and clearing output cache regions without restarting\n    the gateway. The API is authenticated via Bearer tokens issued by Ocelot's built-in IdentityServer or an external identity\n    provider.\n  tags:\n  - Ocelot\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ocelot\n    baseUri: http://localhost:5000\n    description: Ocelot Administration API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{OCELOT_TOKEN}}'\n    resources:\n    - name: administration-connect-token\n      path: /administration/connect/token\n      operations:\n      - name: issueadmintoken\n        method: POST\n        description: Issue an\
  \ admin access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: administration-configuration\n      path: /administration/configuration\n      operations:\n      - name: getconfiguration\n        method: GET\n        description: Get current Ocelot configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setconfiguration\n        method: POST\n        description: Overwrite Ocelot configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: administration-outputcache-region\n      path: /administration/outputcache/{region}\n      operations:\n      - name: clearcacheregion\n        method: DELETE\n        description: Clear an output cache region\n        inputParameters:\n        - name: region\n    \
  \      in: path\n          type: string\n          required: true\n          description: Cache region name as configured in FileCacheOptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ocelot-rest\n    description: REST adapter for Ocelot Administration API.\n    resources:\n    - path: /administration/connect/token\n      name: issueadmintoken\n      operations:\n      - method: POST\n        name: issueadmintoken\n        description: Issue an admin access token\n        call: ocelot.issueadmintoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /administration/configuration\n      name: getconfiguration\n      operations:\n      - method: GET\n        name: getconfiguration\n        description: Get current Ocelot configuration\n        call: ocelot.getconfiguration\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /administration/configuration\n      name: setconfiguration\n      operations:\n      - method: POST\n        name: setconfiguration\n        description: Overwrite Ocelot configuration\n        call: ocelot.setconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /administration/outputcache/{region}\n      name: clearcacheregion\n      operations:\n      - method: DELETE\n        name: clearcacheregion\n        description: Clear an output cache region\n        call: ocelot.clearcacheregion\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ocelot-mcp\n    transport: http\n    description: MCP adapter for Ocelot Administration API for AI agent use.\n    tools:\n    - name: issueadmintoken\n      description: Issue an admin access token\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: ocelot.issueadmintoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconfiguration\n      description: Get current Ocelot configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ocelot.getconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setconfiguration\n      description: Overwrite Ocelot configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ocelot.setconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clearcacheregion\n      description: Clear an output cache region\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ocelot.clearcacheregion\n      with:\n        region: tools.region\n      inputParameters:\n    \
  \  - name: region\n        type: string\n        description: Cache region name as configured in FileCacheOptions\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OCELOT_TOKEN: OCELOT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ocelot/refs/heads/main/capabilities/ocelot-capability.yaml
tags:
- Ocelot
- API
tools:
- description: Issue an admin access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: issueadmintoken
- description: Get current Ocelot configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconfiguration
- description: Overwrite Ocelot configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setconfiguration
- description: Clear an output cache region
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: clearcacheregion
---
