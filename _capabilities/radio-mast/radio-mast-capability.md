---
categories: []
consumed_apis: []
description: The Radio Mast API allows you to integrate Radio Mast functionality into your app or website, including streaming network management, stream monitoring, listener analytics, and encoder credentials.
layout: capability
name: Radio Mast API
operations:
- description: List available API resources
  method: GET
  name: get
  path: /
- description: List Radio Mast streams
  method: GET
  name: get-radiostreams-radiomast
  path: /radiostreams/radiomast/
- description: List external streams
  method: GET
  name: get-radiostreams-external
  path: /radiostreams/external/
- description: List radio stations
  method: GET
  name: get-radiostations
  path: /radiostations/
- description: Listener session time-series analytics
  method: GET
  name: get-analytics-listener-sessions-time-series
  path: /analytics/listener-sessions/time-series/
- description: Aggregate listener session analytics
  method: GET
  name: get-analytics-listener-sessions-aggregate
  path: /analytics/listener-sessions/aggregate/
- description: Listener analytics reports
  method: GET
  name: get-analytics-reports
  path: /analytics/reports/
- description: List listener pools
  method: GET
  name: get-listener-pools
  path: /listener-pools/
personas: []
provider_name: Radio Mast
provider_slug: radio-mast
search_terms:
- analytics
- get radiostreams external
- list listener pools
- get
- get radiostations
- audio
- get radiostreams radiomast
- list radio stations
- aggregate listener session analytics
- list available api resources
- mast
- get analytics listener sessions time series
- get analytics reports
- api
- list radio mast streams
- get listener pools
- radio
- get analytics listener sessions aggregate
- broadcasting
- listener analytics reports
- streaming
- listener session time-series analytics
- list external streams
slug: radio-mast-capability
source_filename: radio-mast-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Radio Mast API\n  description: The Radio Mast API allows you to integrate Radio Mast functionality into your app or website, including streaming\n    network management, stream monitoring, listener analytics, and encoder credentials.\n  tags:\n  - Radio\n  - Mast\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: radio-mast\n    baseUri: https://api.radiomast.io/v1\n    description: Radio Mast API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{RADIO_MAST_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: get\n        method: GET\n        description: List available API resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: radiostreams-radiomast\n      path: /radiostreams/radiomast/\n\
  \      operations:\n      - name: get-radiostreams-radiomast\n        method: GET\n        description: List Radio Mast streams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: radiostreams-external\n      path: /radiostreams/external/\n      operations:\n      - name: get-radiostreams-external\n        method: GET\n        description: List external streams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: radiostations\n      path: /radiostations/\n      operations:\n      - name: get-radiostations\n        method: GET\n        description: List radio stations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-listener-sessions-time-series\n      path: /analytics/listener-sessions/time-series/\n      operations:\n\
  \      - name: get-analytics-listener-sessions-time-series\n        method: GET\n        description: Listener session time-series analytics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-listener-sessions-aggregate\n      path: /analytics/listener-sessions/aggregate/\n      operations:\n      - name: get-analytics-listener-sessions-aggregate\n        method: GET\n        description: Aggregate listener session analytics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-reports\n      path: /analytics/reports/\n      operations:\n      - name: get-analytics-reports\n        method: GET\n        description: Listener analytics reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: listener-pools\n\
  \      path: /listener-pools/\n      operations:\n      - name: get-listener-pools\n        method: GET\n        description: List listener pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: radio-mast-rest\n    description: REST adapter for Radio Mast API.\n    resources:\n    - path: /\n      name: get\n      operations:\n      - method: GET\n        name: get\n        description: List available API resources\n        call: radio-mast.get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /radiostreams/radiomast/\n      name: get-radiostreams-radiomast\n      operations:\n      - method: GET\n        name: get-radiostreams-radiomast\n        description: List Radio Mast streams\n        call: radio-mast.get-radiostreams-radiomast\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \ - path: /radiostreams/external/\n      name: get-radiostreams-external\n      operations:\n      - method: GET\n        name: get-radiostreams-external\n        description: List external streams\n        call: radio-mast.get-radiostreams-external\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /radiostations/\n      name: get-radiostations\n      operations:\n      - method: GET\n        name: get-radiostations\n        description: List radio stations\n        call: radio-mast.get-radiostations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/listener-sessions/time-series/\n      name: get-analytics-listener-sessions-time-series\n      operations:\n      - method: GET\n        name: get-analytics-listener-sessions-time-series\n        description: Listener session time-series analytics\n        call: radio-mast.get-analytics-listener-sessions-time-series\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /analytics/listener-sessions/aggregate/\n      name: get-analytics-listener-sessions-aggregate\n      operations:\n      - method: GET\n        name: get-analytics-listener-sessions-aggregate\n        description: Aggregate listener session analytics\n        call: radio-mast.get-analytics-listener-sessions-aggregate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /analytics/reports/\n      name: get-analytics-reports\n      operations:\n      - method: GET\n        name: get-analytics-reports\n        description: Listener analytics reports\n        call: radio-mast.get-analytics-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /listener-pools/\n      name: get-listener-pools\n      operations:\n      - method: GET\n        name: get-listener-pools\n        description: List listener pools\n        call: radio-mast.get-listener-pools\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: radio-mast-mcp\n    transport: http\n    description: MCP adapter for Radio Mast API for AI agent use.\n    tools:\n    - name: get\n      description: List available API resources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-mast.get\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-radiostreams-radiomast\n      description: List Radio Mast streams\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-mast.get-radiostreams-radiomast\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-radiostreams-external\n      description: List external streams\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-mast.get-radiostreams-external\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-radiostations\n      description: List radio stations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-mast.get-radiostations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-analytics-listener-sessions-time-series\n      description: Listener session time-series analytics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-mast.get-analytics-listener-sessions-time-series\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-analytics-listener-sessions-aggregate\n      description: Aggregate listener session analytics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-mast.get-analytics-listener-sessions-aggregate\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: get-analytics-reports\n      description: Listener analytics reports\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-mast.get-analytics-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-listener-pools\n      description: List listener pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: radio-mast.get-listener-pools\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    RADIO_MAST_TOKEN: RADIO_MAST_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/radio-mast/refs/heads/main/capabilities/radio-mast-capability.yaml
tags:
- Radio
- Mast
- API
tools:
- description: List available API resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: List Radio Mast streams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-radiostreams-radiomast
- description: List external streams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-radiostreams-external
- description: List radio stations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-radiostations
- description: Listener session time-series analytics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-analytics-listener-sessions-time-series
- description: Aggregate listener session analytics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-analytics-listener-sessions-aggregate
- description: Listener analytics reports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-analytics-reports
- description: List listener pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-listener-pools
---
