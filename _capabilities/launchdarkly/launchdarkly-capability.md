---
categories: []
consumed_apis: []
description: The LaunchDarkly Relay Proxy is a small Go application that connects to the LaunchDarkly streaming API and proxies that connection to SDK clients within an organization's network. It exposes endpoints for status monitoring, flag evaluation, and SDK streaming that mirror the LaunchDarkly service endpoints. Instead of each server making outbound connections to LaunchDarkly's streaming service, multiple servers connect to the local Relay Proxy which maintains a single upstream connection.
layout: capability
name: LaunchDarkly Relay Proxy
operations:
- description: Get Relay Proxy status
  method: GET
  name: getrelayproxystatus
  path: /status
- description: Evaluate all flags for a context (GET)
  method: GET
  name: evaluateallflagsforcontext
  path: /sdk/evalx/contexts/{contextBase64}
- description: Evaluate all flags for a client-side context (GET)
  method: GET
  name: evaluateallflagsclientside
  path: /sdk/evalx/{envId}/contexts/{contextBase64}
- description: Stream all flag data (server-side)
  method: GET
  name: streamallflags
  path: /all
- description: Stream flag updates (server-side)
  method: GET
  name: streamflagsonly
  path: /flags
- description: Stream evaluated flags (client-side)
  method: GET
  name: streamclientsideeval
  path: /eval/{envId}/{contextBase64}
- description: Get latest all flags (PHP polling)
  method: GET
  name: getlatestallflags
  path: /sdk/latest-all
personas: []
provider_name: launchdarkly
provider_slug: launchdarkly
search_terms:
- streamclientsideeval
- streamallflags
- evaluate all flags for a context (get)
- evaluateallflagsclientside
- stream flag updates (server-side)
- getlatestallflags
- evaluate all flags for a client-side context (get)
- evaluateallflagsforcontext
- streamflagsonly
- getrelayproxystatus
- api
- get relay proxy status
- get latest all flags (php polling)
- stream evaluated flags (client-side)
- launchdarkly
- stream all flag data (server-side)
slug: launchdarkly-capability
source_filename: launchdarkly-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LaunchDarkly Relay Proxy\n  description: The LaunchDarkly Relay Proxy is a small Go application that connects to the LaunchDarkly streaming API and\n    proxies that connection to SDK clients within an organization's network. It exposes endpoints for status monitoring, flag\n    evaluation, and SDK streaming that mirror the LaunchDarkly service endpoints. Instead of each server making outbound connections\n    to LaunchDarkly's streaming service, multiple servers connect to the local Relay Proxy which maintains a single upstream\n    connection.\n  tags:\n  - Launchdarkly\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: launchdarkly\n    baseUri: http://localhost:8030\n    description: LaunchDarkly Relay Proxy HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{LAUNCHDARKLY_TOKEN}}'\n    resources:\n    - name:\
  \ status\n      path: /status\n      operations:\n      - name: getrelayproxystatus\n        method: GET\n        description: Get Relay Proxy status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sdk-evalx-contexts-contextbase64\n      path: /sdk/evalx/contexts/{contextBase64}\n      operations:\n      - name: evaluateallflagsforcontext\n        method: GET\n        description: Evaluate all flags for a context (GET)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sdk-evalx-envid-contexts-contextbase64\n      path: /sdk/evalx/{envId}/contexts/{contextBase64}\n      operations:\n      - name: evaluateallflagsclientside\n        method: GET\n        description: Evaluate all flags for a client-side context (GET)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: all\n      path: /all\n      operations:\n      - name: streamallflags\n        method: GET\n        description: Stream all flag data (server-side)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flags\n      path: /flags\n      operations:\n      - name: streamflagsonly\n        method: GET\n        description: Stream flag updates (server-side)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: eval-envid-contextbase64\n      path: /eval/{envId}/{contextBase64}\n      operations:\n      - name: streamclientsideeval\n        method: GET\n        description: Stream evaluated flags (client-side)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sdk-latest-all\n      path: /sdk/latest-all\n\
  \      operations:\n      - name: getlatestallflags\n        method: GET\n        description: Get latest all flags (PHP polling)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: launchdarkly-rest\n    description: REST adapter for LaunchDarkly Relay Proxy.\n    resources:\n    - path: /status\n      name: getrelayproxystatus\n      operations:\n      - method: GET\n        name: getrelayproxystatus\n        description: Get Relay Proxy status\n        call: launchdarkly.getrelayproxystatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sdk/evalx/contexts/{contextBase64}\n      name: evaluateallflagsforcontext\n      operations:\n      - method: GET\n        name: evaluateallflagsforcontext\n        description: Evaluate all flags for a context (GET)\n        call: launchdarkly.evaluateallflagsforcontext\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sdk/evalx/{envId}/contexts/{contextBase64}\n      name: evaluateallflagsclientside\n      operations:\n      - method: GET\n        name: evaluateallflagsclientside\n        description: Evaluate all flags for a client-side context (GET)\n        call: launchdarkly.evaluateallflagsclientside\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /all\n      name: streamallflags\n      operations:\n      - method: GET\n        name: streamallflags\n        description: Stream all flag data (server-side)\n        call: launchdarkly.streamallflags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flags\n      name: streamflagsonly\n      operations:\n      - method: GET\n        name: streamflagsonly\n        description: Stream flag updates (server-side)\n        call: launchdarkly.streamflagsonly\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /eval/{envId}/{contextBase64}\n      name: streamclientsideeval\n      operations:\n      - method: GET\n        name: streamclientsideeval\n        description: Stream evaluated flags (client-side)\n        call: launchdarkly.streamclientsideeval\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sdk/latest-all\n      name: getlatestallflags\n      operations:\n      - method: GET\n        name: getlatestallflags\n        description: Get latest all flags (PHP polling)\n        call: launchdarkly.getlatestallflags\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: launchdarkly-mcp\n    transport: http\n    description: MCP adapter for LaunchDarkly Relay Proxy for AI agent use.\n    tools:\n    - name: getrelayproxystatus\n      description: Get Relay Proxy status\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: launchdarkly.getrelayproxystatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: evaluateallflagsforcontext\n      description: Evaluate all flags for a context (GET)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: launchdarkly.evaluateallflagsforcontext\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: evaluateallflagsclientside\n      description: Evaluate all flags for a client-side context (GET)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: launchdarkly.evaluateallflagsclientside\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streamallflags\n      description: Stream all flag data (server-side)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: launchdarkly.streamallflags\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: streamflagsonly\n      description: Stream flag updates (server-side)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: launchdarkly.streamflagsonly\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: streamclientsideeval\n      description: Stream evaluated flags (client-side)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: launchdarkly.streamclientsideeval\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlatestallflags\n      description: Get latest all flags (PHP polling)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: launchdarkly.getlatestallflags\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LAUNCHDARKLY_TOKEN: LAUNCHDARKLY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/launchdarkly/refs/heads/main/capabilities/launchdarkly-capability.yaml
tags:
- Launchdarkly
- API
tools:
- description: Get Relay Proxy status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrelayproxystatus
- description: Evaluate all flags for a context (GET)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: evaluateallflagsforcontext
- description: Evaluate all flags for a client-side context (GET)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: evaluateallflagsclientside
- description: Stream all flag data (server-side)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: streamallflags
- description: Stream flag updates (server-side)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: streamflagsonly
- description: Stream evaluated flags (client-side)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: streamclientsideeval
- description: Get latest all flags (PHP polling)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlatestallflags
---
