---
categories: []
consumed_apis: []
description: The Chronicle API provides programmatic access to Google Cloud's security analytics platform. It supports ingesting security telemetry, searching security data using UDM, managing detection rules, investigating alerts, and accessing threat intelligence.
layout: capability
name: Google Cloud Chronicle API
operations:
- description: Google Cloud Chronicle List detection rules
  method: GET
  name: listrules
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}/rules
- description: Google Cloud Chronicle Create a detection rule
  method: POST
  name: createrule
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}/rules
- description: Google Cloud Chronicle Get a detection rule
  method: GET
  name: getrule
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}/rules/{ruleId}
- description: Google Cloud Chronicle Update a detection rule
  method: PATCH
  name: updaterule
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}/rules/{ruleId}
- description: Google Cloud Chronicle Delete a detection rule
  method: DELETE
  name: deleterule
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}/rules/{ruleId}
- description: Google Cloud Chronicle List alerts
  method: GET
  name: listalerts
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}/alerts
- description: Google Cloud Chronicle List feeds
  method: GET
  name: listfeeds
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}/feeds
- description: Google Cloud Chronicle Create a feed
  method: POST
  name: createfeed
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}/feeds
- description: Google Cloud Chronicle List reference lists
  method: GET
  name: listreferencelists
  path: /projects/{projectId}/locations/{location}/instances/{instanceId}/referenceLists
personas: []
provider_name: Google Cloud Chronicle
provider_slug: google-cloud-chronicle
search_terms:
- google cloud chronicle list alerts
- updaterule
- log management
- google cloud chronicle update a detection rule
- google cloud chronicle delete a detection rule
- chronicle
- createfeed
- listreferencelists
- cloud
- google
- listfeeds
- siem
- security analytics
- google cloud chronicle list reference lists
- getrule
- api
- google cloud chronicle create a feed
- createrule
- security operations
- threat detection
- listrules
- google cloud chronicle get a detection rule
- google cloud chronicle create a detection rule
- deleterule
- listalerts
- google cloud chronicle list feeds
- google cloud chronicle list detection rules
- incident response
slug: google-cloud-chronicle-capability
source_filename: google-cloud-chronicle-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Chronicle API\n  description: The Chronicle API provides programmatic access to Google Cloud's security analytics platform. It supports ingesting\n    security telemetry, searching security data using UDM, managing detection rules, investigating alerts, and accessing threat\n    intelligence.\n  tags:\n  - Google\n  - Cloud\n  - Chronicle\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-chronicle\n    baseUri: https://chronicle.googleapis.com/v1alpha\n    description: Google Cloud Chronicle API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_CHRONICLE_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-instances-\n      path: /projects/{projectId}/locations/{location}/instances/{instanceId}/rules\n      operations:\n      - name: listrules\n        method: GET\n        description: Google\
  \ Cloud Chronicle List detection rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrule\n        method: POST\n        description: Google Cloud Chronicle Create a detection rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-instances-\n      path: /projects/{projectId}/locations/{location}/instances/{instanceId}/rules/{ruleId}\n      operations:\n      - name: getrule\n        method: GET\n        description: Google Cloud Chronicle Get a detection rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterule\n        method: PATCH\n        description: Google Cloud Chronicle Update a detection rule\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deleterule\n        method: DELETE\n        description: Google Cloud Chronicle Delete a detection rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-instances-\n      path: /projects/{projectId}/locations/{location}/instances/{instanceId}/alerts\n      operations:\n      - name: listalerts\n        method: GET\n        description: Google Cloud Chronicle List alerts\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          description: Filter expression for alerts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-instances-\n      path: /projects/{projectId}/locations/{location}/instances/{instanceId}/feeds\n\
  \      operations:\n      - name: listfeeds\n        method: GET\n        description: Google Cloud Chronicle List feeds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfeed\n        method: POST\n        description: Google Cloud Chronicle Create a feed\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-instances-\n      path: /projects/{projectId}/locations/{location}/instances/{instanceId}/referenceLists\n      operations:\n      - name: listreferencelists\n        method: GET\n        description: Google Cloud Chronicle List reference lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-chronicle-rest\n    description:\
  \ REST adapter for Google Cloud Chronicle API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}/rules\n      name: listrules\n      operations:\n      - method: GET\n        name: listrules\n        description: Google Cloud Chronicle List detection rules\n        call: google-cloud-chronicle.listrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}/rules\n      name: createrule\n      operations:\n      - method: POST\n        name: createrule\n        description: Google Cloud Chronicle Create a detection rule\n        call: google-cloud-chronicle.createrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}/rules/{ruleId}\n      name: getrule\n      operations:\n      - method: GET\n        name: getrule\n        description: Google Cloud\
  \ Chronicle Get a detection rule\n        call: google-cloud-chronicle.getrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}/rules/{ruleId}\n      name: updaterule\n      operations:\n      - method: PATCH\n        name: updaterule\n        description: Google Cloud Chronicle Update a detection rule\n        call: google-cloud-chronicle.updaterule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}/rules/{ruleId}\n      name: deleterule\n      operations:\n      - method: DELETE\n        name: deleterule\n        description: Google Cloud Chronicle Delete a detection rule\n        call: google-cloud-chronicle.deleterule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}/alerts\n  \
  \    name: listalerts\n      operations:\n      - method: GET\n        name: listalerts\n        description: Google Cloud Chronicle List alerts\n        call: google-cloud-chronicle.listalerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}/feeds\n      name: listfeeds\n      operations:\n      - method: GET\n        name: listfeeds\n        description: Google Cloud Chronicle List feeds\n        call: google-cloud-chronicle.listfeeds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}/feeds\n      name: createfeed\n      operations:\n      - method: POST\n        name: createfeed\n        description: Google Cloud Chronicle Create a feed\n        call: google-cloud-chronicle.createfeed\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/instances/{instanceId}/referenceLists\n\
  \      name: listreferencelists\n      operations:\n      - method: GET\n        name: listreferencelists\n        description: Google Cloud Chronicle List reference lists\n        call: google-cloud-chronicle.listreferencelists\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-chronicle-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Chronicle API for AI agent use.\n    tools:\n    - name: listrules\n      description: Google Cloud Chronicle List detection rules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-chronicle.listrules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrule\n      description: Google Cloud Chronicle Create a detection rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-chronicle.createrule\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrule\n      description: Google Cloud Chronicle Get a detection rule\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-chronicle.getrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updaterule\n      description: Google Cloud Chronicle Update a detection rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-chronicle.updaterule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterule\n      description: Google Cloud Chronicle Delete a detection rule\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-chronicle.deleterule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listalerts\n      description: Google\
  \ Cloud Chronicle List alerts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-chronicle.listalerts\n      with:\n        filter: tools.filter\n      inputParameters:\n      - name: filter\n        type: string\n        description: Filter expression for alerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfeeds\n      description: Google Cloud Chronicle List feeds\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-chronicle.listfeeds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createfeed\n      description: Google Cloud Chronicle Create a feed\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-chronicle.createfeed\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreferencelists\n\
  \      description: Google Cloud Chronicle List reference lists\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-chronicle.listreferencelists\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_CHRONICLE_TOKEN: GOOGLE_CLOUD_CHRONICLE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-chronicle/refs/heads/main/capabilities/google-cloud-chronicle-capability.yaml
tags:
- Google
- Cloud
- Chronicle
- API
tools:
- description: Google Cloud Chronicle List detection rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrules
- description: Google Cloud Chronicle Create a detection rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrule
- description: Google Cloud Chronicle Get a detection rule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrule
- description: Google Cloud Chronicle Update a detection rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updaterule
- description: Google Cloud Chronicle Delete a detection rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterule
- description: Google Cloud Chronicle List alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalerts
- description: Google Cloud Chronicle List feeds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfeeds
- description: Google Cloud Chronicle Create a feed
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfeed
- description: Google Cloud Chronicle List reference lists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreferencelists
---
