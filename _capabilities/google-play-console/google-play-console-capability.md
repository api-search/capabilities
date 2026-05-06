---
categories: []
consumed_apis: []
description: The Play Developer Reporting API provides programmatic access to Play Console reporting data, including app quality metrics such as crash rates, ANR rates, and other performance indicators.
layout: capability
name: Google Play Console Developer Reporting Google Play Developer Reporting API
operations:
- description: Google Play Console Developer Reporting Search apps
  method: GET
  name: searchapps
  path: /v1alpha1/apps:search
- description: Google Play Console Developer Reporting Get crash rate metric set
  method: GET
  name: getcrashratemetricset
  path: /v1alpha1/{name}/crashRateMetricSet
- description: Google Play Console Developer Reporting Get ANR rate metric set
  method: GET
  name: getanrratemetricset
  path: /v1alpha1/{name}/anrRateMetricSet
- description: Google Play Console Developer Reporting Get error count metric set
  method: GET
  name: geterrorcountmetricset
  path: /v1alpha1/{name}/errorCountMetricSet
personas: []
provider_name: Google Play Console Developer Reporting
provider_slug: google-play-console
search_terms:
- searchapps
- google play console developer reporting get crash rate metric set
- android
- apps
- geterrorcountmetricset
- google play console
- google
- api
- play
- getanrratemetricset
- google play console developer reporting get anr rate metric set
- google play console developer reporting get error count metric set
- google play console developer reporting search apps
- getcrashratemetricset
- analytics
- reporting
- quality
- console
slug: google-play-console-capability
source_filename: google-play-console-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Play Console Developer Reporting Google Play Developer Reporting API\n  description: The Play Developer Reporting API provides programmatic access to Play Console reporting data, including app\n    quality metrics such as crash rates, ANR rates, and other performance indicators.\n  tags:\n  - Google\n  - Play\n  - Console\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-play-console\n    baseUri: https://playdeveloperreporting.googleapis.com\n    description: Google Play Console Developer Reporting Google Play Developer Reporting API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_PLAY_CONSOLE_TOKEN}}'\n    resources:\n    - name: v1alpha1-apps-search\n      path: /v1alpha1/apps:search\n      operations:\n      - name: searchapps\n        method: GET\n        description: Google Play Console Developer Reporting Search apps\n  \
  \      inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1alpha1-name-crashratemetricset\n      path: /v1alpha1/{name}/crashRateMetricSet\n      operations:\n      - name: getcrashratemetricset\n        method: GET\n        description: Google Play Console Developer Reporting Get crash rate metric set\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1alpha1-name-anrratemetricset\n      path: /v1alpha1/{name}/anrRateMetricSet\n      operations:\n      - name: getanrratemetricset\n        method: GET\n        description: Google Play\
  \ Console Developer Reporting Get ANR rate metric set\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1alpha1-name-errorcountmetricset\n      path: /v1alpha1/{name}/errorCountMetricSet\n      operations:\n      - name: geterrorcountmetricset\n        method: GET\n        description: Google Play Console Developer Reporting Get error count metric set\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-play-console-rest\n    description: REST adapter for Google Play Console Developer Reporting Google Play Developer Reporting\
  \ API.\n    resources:\n    - path: /v1alpha1/apps:search\n      name: searchapps\n      operations:\n      - method: GET\n        name: searchapps\n        description: Google Play Console Developer Reporting Search apps\n        call: google-play-console.searchapps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1alpha1/{name}/crashRateMetricSet\n      name: getcrashratemetricset\n      operations:\n      - method: GET\n        name: getcrashratemetricset\n        description: Google Play Console Developer Reporting Get crash rate metric set\n        call: google-play-console.getcrashratemetricset\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1alpha1/{name}/anrRateMetricSet\n      name: getanrratemetricset\n      operations:\n      - method: GET\n        name: getanrratemetricset\n        description: Google Play Console Developer Reporting Get ANR rate metric\
  \ set\n        call: google-play-console.getanrratemetricset\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1alpha1/{name}/errorCountMetricSet\n      name: geterrorcountmetricset\n      operations:\n      - method: GET\n        name: geterrorcountmetricset\n        description: Google Play Console Developer Reporting Get error count metric set\n        call: google-play-console.geterrorcountmetricset\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-play-console-mcp\n    transport: http\n    description: MCP adapter for Google Play Console Developer Reporting Google Play Developer Reporting API for AI agent\n      use.\n    tools:\n    - name: searchapps\n      description: Google Play Console Developer Reporting Search apps\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: google-play-console.searchapps\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcrashratemetricset\n      description: Google Play Console Developer Reporting Get crash rate metric set\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-play-console.getcrashratemetricset\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getanrratemetricset\n      description: Google Play Console Developer Reporting Get ANR rate\
  \ metric set\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-play-console.getanrratemetricset\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: geterrorcountmetricset\n      description: Google Play Console Developer Reporting Get error count metric set\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-play-console.geterrorcountmetricset\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_PLAY_CONSOLE_TOKEN: GOOGLE_PLAY_CONSOLE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-play-console/refs/heads/main/capabilities/google-play-console-capability.yaml
tags:
- Google
- Play
- Console
- API
tools:
- description: Google Play Console Developer Reporting Search apps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchapps
- description: Google Play Console Developer Reporting Get crash rate metric set
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcrashratemetricset
- description: Google Play Console Developer Reporting Get ANR rate metric set
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getanrratemetricset
- description: Google Play Console Developer Reporting Get error count metric set
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geterrorcountmetricset
---
