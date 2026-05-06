---
categories: []
consumed_apis: []
description: Pulsoid enables real-time heart rate data transmission from peripherals (BLE heart rate monitors, smartwatches, etc.) to clients. The Pulsoid REST API provides endpoints to read and submit heart rate data, manage widgets, profile, and validate tokens. Real-time streaming is available via WebSocket endpoints.
layout: capability
name: Pulsoid API
operations:
- description: Validate authorization token
  method: GET
  name: validatetoken
  path: /api/v1/token/validate
- description: Get latest heart rate
  method: GET
  name: getlatestheartrate
  path: /api/v1/data/heart_rate/latest
- description: Submit heart rate data
  method: POST
  name: submitheartrate
  path: /api/v1/data
- description: Read heart rate statistics
  method: GET
  name: getstatistics
  path: /api/v1/statistics
- description: List widgets
  method: GET
  name: listwidgets
  path: /api/v1/widgets
- description: Create widget
  method: POST
  name: createwidget
  path: /api/v1/widgets
- description: Update widget configuration
  method: POST
  name: updatewidget
  path: /api/v1/widgets/{widgetId}
- description: Read user profile
  method: GET
  name: getprofile
  path: /api/v1/profile
- description: Get GD mod configuration
  method: GET
  name: getgdconfig
  path: /api/v1/geometry-dash-mod/configuration
- description: Update GD mod configuration
  method: POST
  name: updategdconfig
  path: /api/v1/geometry-dash-mod/configuration
- description: Check feature availability
  method: GET
  name: getfeature
  path: /api/v1/features/{featureId}
- description: OAuth2 authorize
  method: POST
  name: oauthauthorize
  path: /oauth2/authorize
- description: OAuth2 token exchange/refresh
  method: POST
  name: oauthtoken
  path: /oauth2/token
- description: OAuth2 device authorization
  method: POST
  name: oauthdeviceauthorization
  path: /oauth2/device_authorization
- description: Revoke access token
  method: POST
  name: oauthrevoke
  path: /oauth2/revoke
personas: []
provider_name: Pulsoid
provider_slug: pulsoid
search_terms:
- read heart rate statistics
- get latest heart rate
- oauth2 token exchange/refresh
- getstatistics
- real-time
- websocket
- update gd mod configuration
- check feature availability
- validatetoken
- oauth2
- create widget
- submitheartrate
- oauthdeviceauthorization
- submit heart rate data
- wearables
- getlatestheartrate
- read user profile
- createwidget
- updatewidget
- revoke access token
- list widgets
- getfeature
- api
- update widget configuration
- oauthauthorize
- heart rate
- oauthtoken
- pulsoid
- getgdconfig
- oauthrevoke
- oauth2 device authorization
- streaming
- validate authorization token
- updategdconfig
- oauth2 authorize
- getprofile
- get gd mod configuration
- listwidgets
- health
slug: pulsoid-capability
source_filename: pulsoid-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pulsoid API\n  description: Pulsoid enables real-time heart rate data transmission from peripherals (BLE heart rate monitors, smartwatches,\n    etc.) to clients. The Pulsoid REST API provides endpoints to read and submit heart rate data, manage widgets, profile,\n    and validate tokens. Real-time streaming is available via WebSocket endpoints.\n  tags:\n  - Pulsoid\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pulsoid\n    baseUri: https://dev.pulsoid.net\n    description: Pulsoid API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PULSOID_TOKEN}}'\n    resources:\n    - name: api-v1-token-validate\n      path: /api/v1/token/validate\n      operations:\n      - name: validatetoken\n        method: GET\n        description: Validate authorization token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n    - name: api-v1-data-heart-rate-latest\n      path: /api/v1/data/heart_rate/latest\n      operations:\n      - name: getlatestheartrate\n        method: GET\n        description: Get latest heart rate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-data\n      path: /api/v1/data\n      operations:\n      - name: submitheartrate\n        method: POST\n        description: Submit heart rate data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-statistics\n      path: /api/v1/statistics\n      operations:\n      - name: getstatistics\n        method: GET\n        description: Read heart rate statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-widgets\n\
  \      path: /api/v1/widgets\n      operations:\n      - name: listwidgets\n        method: GET\n        description: List widgets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createwidget\n        method: POST\n        description: Create widget\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-widgets-widgetid\n      path: /api/v1/widgets/{widgetId}\n      operations:\n      - name: updatewidget\n        method: POST\n        description: Update widget configuration\n        inputParameters:\n        - name: widgetId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-profile\n      path: /api/v1/profile\n      operations:\n      -\
  \ name: getprofile\n        method: GET\n        description: Read user profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-geometry-dash-mod-configuration\n      path: /api/v1/geometry-dash-mod/configuration\n      operations:\n      - name: getgdconfig\n        method: GET\n        description: Get GD mod configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategdconfig\n        method: POST\n        description: Update GD mod configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-features-featureid\n      path: /api/v1/features/{featureId}\n      operations:\n      - name: getfeature\n        method: GET\n        description: Check feature availability\n        inputParameters:\n\
  \        - name: featureId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-authorize\n      path: /oauth2/authorize\n      operations:\n      - name: oauthauthorize\n        method: POST\n        description: OAuth2 authorize\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-token\n      path: /oauth2/token\n      operations:\n      - name: oauthtoken\n        method: POST\n        description: OAuth2 token exchange/refresh\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-device-authorization\n      path: /oauth2/device_authorization\n      operations:\n      - name: oauthdeviceauthorization\n        method: POST\n        description:\
  \ OAuth2 device authorization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-revoke\n      path: /oauth2/revoke\n      operations:\n      - name: oauthrevoke\n        method: POST\n        description: Revoke access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pulsoid-rest\n    description: REST adapter for Pulsoid API.\n    resources:\n    - path: /api/v1/token/validate\n      name: validatetoken\n      operations:\n      - method: GET\n        name: validatetoken\n        description: Validate authorization token\n        call: pulsoid.validatetoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/data/heart_rate/latest\n      name: getlatestheartrate\n      operations:\n      - method: GET\n  \
  \      name: getlatestheartrate\n        description: Get latest heart rate\n        call: pulsoid.getlatestheartrate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/data\n      name: submitheartrate\n      operations:\n      - method: POST\n        name: submitheartrate\n        description: Submit heart rate data\n        call: pulsoid.submitheartrate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/statistics\n      name: getstatistics\n      operations:\n      - method: GET\n        name: getstatistics\n        description: Read heart rate statistics\n        call: pulsoid.getstatistics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/widgets\n      name: listwidgets\n      operations:\n      - method: GET\n        name: listwidgets\n        description: List widgets\n        call: pulsoid.listwidgets\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /api/v1/widgets\n      name: createwidget\n      operations:\n      - method: POST\n        name: createwidget\n        description: Create widget\n        call: pulsoid.createwidget\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/widgets/{widgetId}\n      name: updatewidget\n      operations:\n      - method: POST\n        name: updatewidget\n        description: Update widget configuration\n        call: pulsoid.updatewidget\n        with:\n          widgetId: rest.widgetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/profile\n      name: getprofile\n      operations:\n      - method: GET\n        name: getprofile\n        description: Read user profile\n        call: pulsoid.getprofile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/geometry-dash-mod/configuration\n      name: getgdconfig\n      operations:\n\
  \      - method: GET\n        name: getgdconfig\n        description: Get GD mod configuration\n        call: pulsoid.getgdconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/geometry-dash-mod/configuration\n      name: updategdconfig\n      operations:\n      - method: POST\n        name: updategdconfig\n        description: Update GD mod configuration\n        call: pulsoid.updategdconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/features/{featureId}\n      name: getfeature\n      operations:\n      - method: GET\n        name: getfeature\n        description: Check feature availability\n        call: pulsoid.getfeature\n        with:\n          featureId: rest.featureId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/authorize\n      name: oauthauthorize\n      operations:\n      - method: POST\n        name: oauthauthorize\n        description:\
  \ OAuth2 authorize\n        call: pulsoid.oauthauthorize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/token\n      name: oauthtoken\n      operations:\n      - method: POST\n        name: oauthtoken\n        description: OAuth2 token exchange/refresh\n        call: pulsoid.oauthtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/device_authorization\n      name: oauthdeviceauthorization\n      operations:\n      - method: POST\n        name: oauthdeviceauthorization\n        description: OAuth2 device authorization\n        call: pulsoid.oauthdeviceauthorization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/revoke\n      name: oauthrevoke\n      operations:\n      - method: POST\n        name: oauthrevoke\n        description: Revoke access token\n        call: pulsoid.oauthrevoke\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pulsoid-mcp\n    transport: http\n    description: MCP adapter for Pulsoid API for AI agent use.\n    tools:\n    - name: validatetoken\n      description: Validate authorization token\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pulsoid.validatetoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlatestheartrate\n      description: Get latest heart rate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pulsoid.getlatestheartrate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitheartrate\n      description: Submit heart rate data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pulsoid.submitheartrate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ getstatistics\n      description: Read heart rate statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pulsoid.getstatistics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listwidgets\n      description: List widgets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pulsoid.listwidgets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createwidget\n      description: Create widget\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pulsoid.createwidget\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatewidget\n      description: Update widget configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pulsoid.updatewidget\n      with:\n        widgetId: tools.widgetId\n\
  \      inputParameters:\n      - name: widgetId\n        type: string\n        description: widgetId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprofile\n      description: Read user profile\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pulsoid.getprofile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgdconfig\n      description: Get GD mod configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pulsoid.getgdconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updategdconfig\n      description: Update GD mod configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pulsoid.updategdconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfeature\n\
  \      description: Check feature availability\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pulsoid.getfeature\n      with:\n        featureId: tools.featureId\n      inputParameters:\n      - name: featureId\n        type: string\n        description: featureId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: oauthauthorize\n      description: OAuth2 authorize\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pulsoid.oauthauthorize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: oauthtoken\n      description: OAuth2 token exchange/refresh\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pulsoid.oauthtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: oauthdeviceauthorization\n      description:\
  \ OAuth2 device authorization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pulsoid.oauthdeviceauthorization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: oauthrevoke\n      description: Revoke access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pulsoid.oauthrevoke\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PULSOID_TOKEN: PULSOID_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pulsoid/refs/heads/main/capabilities/pulsoid-capability.yaml
tags:
- Pulsoid
- API
tools:
- description: Validate authorization token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: validatetoken
- description: Get latest heart rate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlatestheartrate
- description: Submit heart rate data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitheartrate
- description: Read heart rate statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatistics
- description: List widgets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwidgets
- description: Create widget
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwidget
- description: Update widget configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatewidget
- description: Read user profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprofile
- description: Get GD mod configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgdconfig
- description: Update GD mod configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updategdconfig
- description: Check feature availability
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfeature
- description: OAuth2 authorize
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oauthauthorize
- description: OAuth2 token exchange/refresh
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oauthtoken
- description: OAuth2 device authorization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oauthdeviceauthorization
- description: Revoke access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oauthrevoke
---
