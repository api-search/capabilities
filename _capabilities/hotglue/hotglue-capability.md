---
categories: []
consumed_apis: []
description: The Hotglue API v2 enables programmatic management of embedded integrations including linked connectors, flow configurations, job execution, tenant management, and connector state for SaaS product integrations.
layout: capability
name: Hotglue API V2
operations:
- description: Retrieve linked connectors
  method: GET
  name: getlinkedconnectors
  path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors
- description: Link a connector
  method: POST
  name: linkconnector
  path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors
- description: Update a linked connector
  method: PATCH
  name: updatelinkedconnector
  path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors
- description: Unlink a connector
  method: DELETE
  name: unlinkconnector
  path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors
- description: Trigger connector discovery
  method: GET
  name: triggerdiscover
  path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/discover
- description: Poll discover status
  method: GET
  name: polldiscover
  path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/discover/poll
- description: Retrieve connector state
  method: GET
  name: getconnectorstate
  path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/state
- description: Set connector state
  method: PUT
  name: setconnectorstate
  path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/state
- description: Delete connector state
  method: DELETE
  name: deleteconnectorstate
  path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/state
- description: Run a job
  method: POST
  name: runjob
  path: /v2/{env_id}/{flow_id}/{tenant}/jobs
- description: Retrieve available connectors
  method: GET
  name: listavailableconnectors
  path: /v2/{env_id}/availableConnectors
- description: Retrieve supported connectors
  method: GET
  name: listsupportedconnectors
  path: /v2/{env_id}/{flow_id}/supportedConnectors
personas: []
provider_name: Hotglue
provider_slug: hotglue
search_terms:
- update a linked connector
- retrieve connector state
- api
- embedded integrations
- set connector state
- delete connector state
- retrieve supported connectors
- polldiscover
- listavailableconnectors
- run a job
- trigger connector discovery
- hotglue
- getlinkedconnectors
- integration platform
- poll discover status
- retrieve linked connectors
- setconnectorstate
- ipaas
- listsupportedconnectors
- linkconnector
- connectors
- runjob
- triggerdiscover
- retrieve available connectors
- updatelinkedconnector
- link a connector
- etl
- unlinkconnector
- getconnectorstate
- deleteconnectorstate
- unlink a connector
slug: hotglue-capability
source_filename: hotglue-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hotglue API V2\n  description: The Hotglue API v2 enables programmatic management of embedded integrations including linked connectors, flow\n    configurations, job execution, tenant management, and connector state for SaaS product integrations.\n  tags:\n  - Hotglue\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hotglue\n    baseUri: https://api.hotglue.com\n    description: Hotglue API V2 HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{HOTGLUE_TOKEN}}'\n    resources:\n    - name: v2-env-id-flow-id-tenant-linkedconnectors\n      path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors\n      operations:\n      - name: getlinkedconnectors\n        method: GET\n        description: Retrieve linked connectors\n        inputParameters:\n        - name: config\n          in: query\n          type: boolean\n  \
  \        description: Request the underlying config for the linked source.\n        - name: catalog\n          in: query\n          type: boolean\n          description: Request the catalog of available fields.\n        - name: token\n          in: query\n          type: string\n          required: true\n          description: JWT token from private signing key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: linkconnector\n        method: POST\n        description: Link a connector\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelinkedconnector\n        method: PATCH\n        description: Update a linked connector\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unlinkconnector\n        method: DELETE\n\
  \        description: Unlink a connector\n        inputParameters:\n        - name: connector_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-env-id-flow-id-tenant-linkedconnectors-discov\n      path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/discover\n      operations:\n      - name: triggerdiscover\n        method: GET\n        description: Trigger connector discovery\n        inputParameters:\n        - name: connector_id\n          in: query\n          type: string\n          required: true\n        - name: v2_source\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-env-id-flow-id-tenant-linkedconnectors-discov\n      path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/discover/poll\n\
  \      operations:\n      - name: polldiscover\n        method: GET\n        description: Poll discover status\n        inputParameters:\n        - name: connector_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-env-id-flow-id-tenant-linkedconnectors-state\n      path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/state\n      operations:\n      - name: getconnectorstate\n        method: GET\n        description: Retrieve connector state\n        inputParameters:\n        - name: connector_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setconnectorstate\n        method: PUT\n        description: Set connector state\n        inputParameters:\n        -\
  \ name: connector_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteconnectorstate\n        method: DELETE\n        description: Delete connector state\n        inputParameters:\n        - name: connector_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-env-id-flow-id-tenant-jobs\n      path: /v2/{env_id}/{flow_id}/{tenant}/jobs\n      operations:\n      - name: runjob\n        method: POST\n        description: Run a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-env-id-availableconnectors\n      path: /v2/{env_id}/availableConnectors\n      operations:\n\
  \      - name: listavailableconnectors\n        method: GET\n        description: Retrieve available connectors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-env-id-flow-id-supportedconnectors\n      path: /v2/{env_id}/{flow_id}/supportedConnectors\n      operations:\n      - name: listsupportedconnectors\n        method: GET\n        description: Retrieve supported connectors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hotglue-rest\n    description: REST adapter for Hotglue API V2.\n    resources:\n    - path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors\n      name: getlinkedconnectors\n      operations:\n      - method: GET\n        name: getlinkedconnectors\n        description: Retrieve linked connectors\n        call: hotglue.getlinkedconnectors\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors\n      name: linkconnector\n      operations:\n      - method: POST\n        name: linkconnector\n        description: Link a connector\n        call: hotglue.linkconnector\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors\n      name: updatelinkedconnector\n      operations:\n      - method: PATCH\n        name: updatelinkedconnector\n        description: Update a linked connector\n        call: hotglue.updatelinkedconnector\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors\n      name: unlinkconnector\n      operations:\n      - method: DELETE\n        name: unlinkconnector\n        description: Unlink a connector\n        call: hotglue.unlinkconnector\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/discover\n      name: triggerdiscover\n      operations:\n      - method: GET\n        name: triggerdiscover\n        description: Trigger connector discovery\n        call: hotglue.triggerdiscover\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/discover/poll\n      name: polldiscover\n      operations:\n      - method: GET\n        name: polldiscover\n        description: Poll discover status\n        call: hotglue.polldiscover\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/state\n      name: getconnectorstate\n      operations:\n      - method: GET\n        name: getconnectorstate\n        description: Retrieve connector state\n        call: hotglue.getconnectorstate\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/state\n      name: setconnectorstate\n      operations:\n      - method: PUT\n        name: setconnectorstate\n        description: Set connector state\n        call: hotglue.setconnectorstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{env_id}/{flow_id}/{tenant}/linkedConnectors/state\n      name: deleteconnectorstate\n      operations:\n      - method: DELETE\n        name: deleteconnectorstate\n        description: Delete connector state\n        call: hotglue.deleteconnectorstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{env_id}/{flow_id}/{tenant}/jobs\n      name: runjob\n      operations:\n      - method: POST\n        name: runjob\n        description: Run a job\n        call: hotglue.runjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{env_id}/availableConnectors\n\
  \      name: listavailableconnectors\n      operations:\n      - method: GET\n        name: listavailableconnectors\n        description: Retrieve available connectors\n        call: hotglue.listavailableconnectors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/{env_id}/{flow_id}/supportedConnectors\n      name: listsupportedconnectors\n      operations:\n      - method: GET\n        name: listsupportedconnectors\n        description: Retrieve supported connectors\n        call: hotglue.listsupportedconnectors\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hotglue-mcp\n    transport: http\n    description: MCP adapter for Hotglue API V2 for AI agent use.\n    tools:\n    - name: getlinkedconnectors\n      description: Retrieve linked connectors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hotglue.getlinkedconnectors\n\
  \      with:\n        config: tools.config\n        catalog: tools.catalog\n        token: tools.token\n      inputParameters:\n      - name: config\n        type: boolean\n        description: Request the underlying config for the linked source.\n      - name: catalog\n        type: boolean\n        description: Request the catalog of available fields.\n      - name: token\n        type: string\n        description: JWT token from private signing key.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: linkconnector\n      description: Link a connector\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hotglue.linkconnector\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatelinkedconnector\n      description: Update a linked connector\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hotglue.updatelinkedconnector\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unlinkconnector\n      description: Unlink a connector\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hotglue.unlinkconnector\n      with:\n        connector_id: tools.connector_id\n      inputParameters:\n      - name: connector_id\n        type: string\n        description: connector_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: triggerdiscover\n      description: Trigger connector discovery\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hotglue.triggerdiscover\n      with:\n        connector_id: tools.connector_id\n        v2_source: tools.v2_source\n      inputParameters:\n      - name: connector_id\n        type: string\n        description: connector_id\n        required: true\n      - name: v2_source\n        type: boolean\n\
  \        description: v2_source\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: polldiscover\n      description: Poll discover status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hotglue.polldiscover\n      with:\n        connector_id: tools.connector_id\n      inputParameters:\n      - name: connector_id\n        type: string\n        description: connector_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconnectorstate\n      description: Retrieve connector state\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hotglue.getconnectorstate\n      with:\n        connector_id: tools.connector_id\n      inputParameters:\n      - name: connector_id\n        type: string\n        description: connector_id\n        required: true\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n    - name: setconnectorstate\n      description: Set connector state\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hotglue.setconnectorstate\n      with:\n        connector_id: tools.connector_id\n      inputParameters:\n      - name: connector_id\n        type: string\n        description: connector_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteconnectorstate\n      description: Delete connector state\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hotglue.deleteconnectorstate\n      with:\n        connector_id: tools.connector_id\n      inputParameters:\n      - name: connector_id\n        type: string\n        description: connector_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runjob\n      description: Run a job\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hotglue.runjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listavailableconnectors\n      description: Retrieve available connectors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hotglue.listavailableconnectors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsupportedconnectors\n      description: Retrieve supported connectors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hotglue.listsupportedconnectors\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HOTGLUE_TOKEN: HOTGLUE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hotglue/refs/heads/main/capabilities/hotglue-capability.yaml
tags:
- Hotglue
- API
tools:
- description: Retrieve linked connectors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlinkedconnectors
- description: Link a connector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: linkconnector
- description: Update a linked connector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatelinkedconnector
- description: Unlink a connector
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: unlinkconnector
- description: Trigger connector discovery
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: triggerdiscover
- description: Poll discover status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: polldiscover
- description: Retrieve connector state
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnectorstate
- description: Set connector state
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setconnectorstate
- description: Delete connector state
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteconnectorstate
- description: Run a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runjob
- description: Retrieve available connectors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listavailableconnectors
- description: Retrieve supported connectors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsupportedconnectors
---
