---
categories: []
consumed_apis: []
description: Public Radio.co API for retrieving station status, metadata, and currently-playing track information. Use these endpoints to power custom players, websites, and applications.
layout: capability
name: Radio.co Public API
operations:
- description: Retrieve full station status
  method: GET
  name: get-stations-stationid-status
  path: /stations/{stationId}/status
- description: Retrieve station metadata
  method: GET
  name: get-api-v2-stationid
  path: /api/v2/{stationId}
- description: Get the currently playing track
  method: GET
  name: get-api-v2-stationid-track-current
  path: /api/v2/{stationId}/track/current
personas: []
provider_name: Radio.co
provider_slug: radio-co
search_terms:
- streaming
- retrieve station metadata
- retrieve full station status
- co
- get stations stationid status
- get api v2 stationid
- get the currently playing track
- get api v2 stationid track current
- radio
- api
- music
- audio
slug: radio-co-capability
source_filename: radio-co-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Radio.co Public API\n  description: Public Radio.co API for retrieving station status, metadata, and currently-playing track information. Use these\n    endpoints to power custom players, websites, and applications.\n  tags:\n  - Radio\n  - Co\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: radio-co\n    baseUri: https://public.radio.co\n    description: Radio.co Public API HTTP API.\n    resources:\n    - name: stations-stationid-status\n      path: /stations/{stationId}/status\n      operations:\n      - name: get-stations-stationid-status\n        method: GET\n        description: Retrieve full station status\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ api-v2-stationid\n      path: /api/v2/{stationId}\n      operations:\n      - name: get-api-v2-stationid\n        method: GET\n        description: Retrieve station metadata\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-stationid-track-current\n      path: /api/v2/{stationId}/track/current\n      operations:\n      - name: get-api-v2-stationid-track-current\n        method: GET\n        description: Get the currently playing track\n        inputParameters:\n        - name: stationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: radio-co-rest\n    description:\
  \ REST adapter for Radio.co Public API.\n    resources:\n    - path: /stations/{stationId}/status\n      name: get-stations-stationid-status\n      operations:\n      - method: GET\n        name: get-stations-stationid-status\n        description: Retrieve full station status\n        call: radio-co.get-stations-stationid-status\n        with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/{stationId}\n      name: get-api-v2-stationid\n      operations:\n      - method: GET\n        name: get-api-v2-stationid\n        description: Retrieve station metadata\n        call: radio-co.get-api-v2-stationid\n        with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/{stationId}/track/current\n      name: get-api-v2-stationid-track-current\n      operations:\n      - method: GET\n        name: get-api-v2-stationid-track-current\n\
  \        description: Get the currently playing track\n        call: radio-co.get-api-v2-stationid-track-current\n        with:\n          stationId: rest.stationId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: radio-co-mcp\n    transport: http\n    description: MCP adapter for Radio.co Public API for AI agent use.\n    tools:\n    - name: get-stations-stationid-status\n      description: Retrieve full station status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-co.get-stations-stationid-status\n      with:\n        stationId: tools.stationId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-v2-stationid\n      description: Retrieve station metadata\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: radio-co.get-api-v2-stationid\n      with:\n        stationId: tools.stationId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-v2-stationid-track-current\n      description: Get the currently playing track\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-co.get-api-v2-stationid-track-current\n      with:\n        stationId: tools.stationId\n      inputParameters:\n      - name: stationId\n        type: string\n        description: stationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/radio-co/refs/heads/main/capabilities/radio-co-capability.yaml
tags:
- Radio
- Co
- API
tools:
- description: Retrieve full station status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-stations-stationid-status
- description: Retrieve station metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-v2-stationid
- description: Get the currently playing track
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-v2-stationid-track-current
---
