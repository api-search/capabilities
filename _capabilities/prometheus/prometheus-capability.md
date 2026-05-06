---
categories: []
consumed_apis: []
description: The Prometheus Alertmanager HTTP API v2 provides endpoints for querying active alert status, creating and managing silences, retrieving receiver configurations, and checking cluster peer status. Alertmanager deduplicates, groups, and routes alert notifications to receivers such as email, PagerDuty, Slack, and OpsGenie. The API base path is /api/v2.
layout: capability
name: Prometheus Alertmanager API
operations:
- description: Prometheus Get active alerts
  method: GET
  name: getalerts
  path: /api/v2/alerts
- description: Prometheus Post alerts
  method: POST
  name: postalerts
  path: /api/v2/alerts
- description: Prometheus List silences
  method: GET
  name: listsilences
  path: /api/v2/silences
- description: Prometheus Create or update silence
  method: POST
  name: createsilence
  path: /api/v2/silences
- description: Prometheus Get silence by ID
  method: GET
  name: getsilence
  path: /api/v2/silence/{silenceID}
- description: Prometheus Expire silence
  method: DELETE
  name: deletesilence
  path: /api/v2/silence/{silenceID}
- description: Prometheus List receivers
  method: GET
  name: listreceivers
  path: /api/v2/receivers
- description: Prometheus Get Alertmanager status
  method: GET
  name: getstatus
  path: /api/v2/status
- description: Prometheus Get alert groups
  method: GET
  name: getalertgroups
  path: /api/v2/alerts/groups
personas: []
provider_name: Prometheus
provider_slug: prometheus
search_terms:
- getalerts
- listsilences
- prometheus list receivers
- listreceivers
- prometheus post alerts
- prometheus create or update silence
- getsilence
- metrics
- prometheus get active alerts
- alerting
- prometheus list silences
- monitoring
- prometheus get silence by id
- prometheus get alertmanager status
- prometheus
- postalerts
- time series
- getstatus
- api
- observability
- deletesilence
- prometheus get alert groups
- prometheus expire silence
- createsilence
- getalertgroups
slug: prometheus-capability
source_filename: prometheus-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Prometheus Alertmanager API\n  description: The Prometheus Alertmanager HTTP API v2 provides endpoints for querying active alert status, creating and managing\n    silences, retrieving receiver configurations, and checking cluster peer status. Alertmanager deduplicates, groups, and\n    routes alert notifications to receivers such as email, PagerDuty, Slack, and OpsGenie. The API base path is /api/v2.\n  tags:\n  - Prometheus\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: prometheus\n    baseUri: http://localhost:9093\n    description: Prometheus Alertmanager API HTTP API.\n    resources:\n    - name: api-v2-alerts\n      path: /api/v2/alerts\n      operations:\n      - name: getalerts\n        method: GET\n        description: Prometheus Get active alerts\n        inputParameters:\n        - name: active\n          in: query\n          type: boolean\n          description:\
  \ Only return active (non-silenced, non-inhibited) alerts.\n        - name: silenced\n          in: query\n          type: boolean\n          description: Include silenced alerts in results.\n        - name: inhibited\n          in: query\n          type: boolean\n          description: Include inhibited alerts in results.\n        - name: unprocessed\n          in: query\n          type: boolean\n          description: Include unprocessed alerts that have not yet been routed.\n        - name: filter\n          in: query\n          type: array\n          description: A list of label matchers to filter alerts by. Matchers use the syntax label=value, label!=value, label=~regex,\n            or label!~regex.\n        - name: receiver\n          in: query\n          type: string\n          description: Filter by receiver name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postalerts\n        method:\
  \ POST\n        description: Prometheus Post alerts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-silences\n      path: /api/v2/silences\n      operations:\n      - name: listsilences\n        method: GET\n        description: Prometheus List silences\n        inputParameters:\n        - name: filter\n          in: query\n          type: array\n          description: Label matchers to filter silences by.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsilence\n        method: POST\n        description: Prometheus Create or update silence\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-silence-silenceid\n      path: /api/v2/silence/{silenceID}\n      operations:\n      - name: getsilence\n  \
  \      method: GET\n        description: Prometheus Get silence by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesilence\n        method: DELETE\n        description: Prometheus Expire silence\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-receivers\n      path: /api/v2/receivers\n      operations:\n      - name: listreceivers\n        method: GET\n        description: Prometheus List receivers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-status\n      path: /api/v2/status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Prometheus Get Alertmanager status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n    - name: api-v2-alerts-groups\n      path: /api/v2/alerts/groups\n      operations:\n      - name: getalertgroups\n        method: GET\n        description: Prometheus Get alert groups\n        inputParameters:\n        - name: active\n          in: query\n          type: boolean\n          description: Include active alerts.\n        - name: silenced\n          in: query\n          type: boolean\n          description: Include silenced alerts.\n        - name: inhibited\n          in: query\n          type: boolean\n          description: Include inhibited alerts.\n        - name: filter\n          in: query\n          type: array\n          description: Label matchers to filter by.\n        - name: receiver\n          in: query\n          type: string\n          description: Filter by receiver name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type:\
  \ rest\n    port: 8080\n    namespace: prometheus-rest\n    description: REST adapter for Prometheus Alertmanager API.\n    resources:\n    - path: /api/v2/alerts\n      name: getalerts\n      operations:\n      - method: GET\n        name: getalerts\n        description: Prometheus Get active alerts\n        call: prometheus.getalerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/alerts\n      name: postalerts\n      operations:\n      - method: POST\n        name: postalerts\n        description: Prometheus Post alerts\n        call: prometheus.postalerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/silences\n      name: listsilences\n      operations:\n      - method: GET\n        name: listsilences\n        description: Prometheus List silences\n        call: prometheus.listsilences\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/silences\n\
  \      name: createsilence\n      operations:\n      - method: POST\n        name: createsilence\n        description: Prometheus Create or update silence\n        call: prometheus.createsilence\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/silence/{silenceID}\n      name: getsilence\n      operations:\n      - method: GET\n        name: getsilence\n        description: Prometheus Get silence by ID\n        call: prometheus.getsilence\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/silence/{silenceID}\n      name: deletesilence\n      operations:\n      - method: DELETE\n        name: deletesilence\n        description: Prometheus Expire silence\n        call: prometheus.deletesilence\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/receivers\n      name: listreceivers\n      operations:\n      - method: GET\n        name: listreceivers\n       \
  \ description: Prometheus List receivers\n        call: prometheus.listreceivers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/status\n      name: getstatus\n      operations:\n      - method: GET\n        name: getstatus\n        description: Prometheus Get Alertmanager status\n        call: prometheus.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/alerts/groups\n      name: getalertgroups\n      operations:\n      - method: GET\n        name: getalertgroups\n        description: Prometheus Get alert groups\n        call: prometheus.getalertgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: prometheus-mcp\n    transport: http\n    description: MCP adapter for Prometheus Alertmanager API for AI agent use.\n    tools:\n    - name: getalerts\n      description: Prometheus Get active alerts\n      hints:\n \
  \       readOnly: true\n        destructive: false\n        idempotent: true\n      call: prometheus.getalerts\n      with:\n        active: tools.active\n        silenced: tools.silenced\n        inhibited: tools.inhibited\n        unprocessed: tools.unprocessed\n        filter: tools.filter\n        receiver: tools.receiver\n      inputParameters:\n      - name: active\n        type: boolean\n        description: Only return active (non-silenced, non-inhibited) alerts.\n      - name: silenced\n        type: boolean\n        description: Include silenced alerts in results.\n      - name: inhibited\n        type: boolean\n        description: Include inhibited alerts in results.\n      - name: unprocessed\n        type: boolean\n        description: Include unprocessed alerts that have not yet been routed.\n      - name: filter\n        type: array\n        description: A list of label matchers to filter alerts by. Matchers use the syntax label=value, label!=value, label=~regex,\n    \
  \      or label!~regex.\n      - name: receiver\n        type: string\n        description: Filter by receiver name.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postalerts\n      description: Prometheus Post alerts\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: prometheus.postalerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsilences\n      description: Prometheus List silences\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prometheus.listsilences\n      with:\n        filter: tools.filter\n      inputParameters:\n      - name: filter\n        type: array\n        description: Label matchers to filter silences by.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsilence\n      description: Prometheus Create or update silence\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: prometheus.createsilence\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsilence\n      description: Prometheus Get silence by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prometheus.getsilence\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesilence\n      description: Prometheus Expire silence\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: prometheus.deletesilence\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreceivers\n      description: Prometheus List receivers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prometheus.listreceivers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstatus\n\
  \      description: Prometheus Get Alertmanager status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prometheus.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getalertgroups\n      description: Prometheus Get alert groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prometheus.getalertgroups\n      with:\n        active: tools.active\n        silenced: tools.silenced\n        inhibited: tools.inhibited\n        filter: tools.filter\n        receiver: tools.receiver\n      inputParameters:\n      - name: active\n        type: boolean\n        description: Include active alerts.\n      - name: silenced\n        type: boolean\n        description: Include silenced alerts.\n      - name: inhibited\n        type: boolean\n        description: Include inhibited alerts.\n      - name: filter\n        type: array\n        description:\
  \ Label matchers to filter by.\n      - name: receiver\n        type: string\n        description: Filter by receiver name.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/prometheus/refs/heads/main/capabilities/prometheus-capability.yaml
tags:
- Prometheus
- API
tools:
- description: Prometheus Get active alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalerts
- description: Prometheus Post alerts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postalerts
- description: Prometheus List silences
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsilences
- description: Prometheus Create or update silence
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsilence
- description: Prometheus Get silence by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsilence
- description: Prometheus Expire silence
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesilence
- description: Prometheus List receivers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreceivers
- description: Prometheus Get Alertmanager status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
- description: Prometheus Get alert groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalertgroups
---
