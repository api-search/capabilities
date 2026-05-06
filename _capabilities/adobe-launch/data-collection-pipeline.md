---
categories: []
consumed_apis: []
description: Unified workflow for Adobe Experience Platform data collection. Combines Event Forwarding and Data Collection APIs for data engineers managing server-side event routing, Edge Network data ingestion, and media analytics tracking.
layout: capability
name: Adobe Launch Data Collection Pipeline
operations:
- description: List event forwarding properties
  method: GET
  name: list-event-forwarding-properties
  path: /v1/event-forwarding-properties
- description: List event forwarding rules
  method: GET
  name: list-event-forwarding-rules
  path: /v1/event-forwarding-rules
- description: List secrets for a property
  method: GET
  name: list-secrets
  path: /v1/secrets
- description: Send an interactive event to Edge Network
  method: POST
  name: send-interactive-event
  path: /v1/events
- description: Send batch events to Edge Network
  method: POST
  name: send-batch-events
  path: /v1/events
personas: []
provider_name: Adobe Launch
provider_slug: adobe-launch
search_terms:
- list event forwarding rules for a property
- create event forwarding rule
- adobe launch
- send batch events to edge network
- send batch events
- list secrets for a property
- tag management
- event forwarding
- list server-side event forwarding properties
- data collection
- list event forwarding rules
- secrets for event forwarding destinations
- list event forwarding properties
- end a media tracking session
- create a secret for an event forwarding destination
- send interactive event
- create a new event forwarding property
- create secret
- create event forwarding property
- list secrets for authenticating with forwarding destinations
- event forwarding rules
- edge network data ingestion
- send an interactive event to edge network
- marketing technology
- server-side event forwarding properties
- create a new event forwarding rule
- send an interactive event to adobe edge network
- send batch events to adobe edge network
- end media session
- list secrets
- edge network
- start a media tracking session
- start media session
slug: data-collection-pipeline
source_filename: data-collection-pipeline.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Launch Data Collection Pipeline\n  description: Unified workflow for Adobe Experience Platform data collection. Combines Event Forwarding and Data Collection\n    APIs for data engineers managing server-side event routing, Edge Network data ingestion, and media analytics tracking.\n  tags:\n  - Adobe Launch\n  - Data Collection\n  - Event Forwarding\n  - Edge Network\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_ACCESS_TOKEN: ADOBE_ACCESS_TOKEN\n    ADOBE_API_KEY: ADOBE_API_KEY\n    ADOBE_ORG_ID: ADOBE_ORG_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: event-forwarding\n    baseUri: https://reactor.adobe.io\n    description: Adobe Experience Platform Event Forwarding API\n    authentication:\n      type: bearer\n      token: '{{ADOBE_ACCESS_TOKEN}}'\n    resources:\n    - name: properties\n      path: /companies/{companyId}/properties\n      description: Event forwarding\
  \ property management (edge platform)\n      operations:\n      - name: list-properties\n        method: GET\n        description: List event forwarding properties (platform=edge)\n        inputParameters:\n        - name: companyId\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        - name: filter[platform]\n          in: query\n          type: string\n          required: true\n          description: Filter to edge platform\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-property\n        method: POST\n        description: Create an event forwarding property\n        inputParameters:\n        - name: companyId\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n    - name: rules\n      path: /properties/{propertyId}/rules\n      description: Event forwarding rule management\n      operations:\n      - name: list-rules\n        method: GET\n        description: List event forwarding rules\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-rule\n        method: POST\n        description: Create an event forwarding rule\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n    - name: secrets\n      path: /properties/{propertyId}/secrets\n      description: Secret management for event forwarding\n      operations:\n      - name: list-secrets\n        method: GET\n        description: List secrets for a property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-secret\n        method: POST\n        description: Create a new secret\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n  - type: http\n    namespace: data-collection\n    baseUri: https://edge.adobedc.net\n    description: Adobe Experience Platform Data Collection API\n    authentication:\n      type: bearer\n      token: '{{ADOBE_ACCESS_TOKEN}}'\n    resources:\n    - name: edge-network\n      path: /ee/v2\n      description: Edge Network interactive and batch data collection\n      operations:\n      - name: interact\n        method: POST\n        description: Send an interactive event with real-time response\n        inputParameters:\n        - name: datastreamId\n          in: query\n          type: string\n          required: true\n          description: Datastream configuration ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            event: '{{tools.event}}'\n\
  \      - name: collect\n        method: POST\n        description: Send batch events without expecting a response\n        inputParameters:\n        - name: datastreamId\n          in: query\n          type: string\n          required: true\n          description: Datastream configuration ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            events: '{{tools.events}}'\n    - name: media\n      path: /ee/va/v1\n      description: Media Edge API for tracking media playback\n      operations:\n      - name: media-session-start\n        method: POST\n        description: Start a media tracking session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            events: '{{tools.events}}'\n      - name: media-play\n   \
  \     method: POST\n        description: Track media play event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            events: '{{tools.events}}'\n      - name: media-session-complete\n        method: POST\n        description: Track media session complete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            events: '{{tools.events}}'\n      - name: media-session-end\n        method: POST\n        description: End a media tracking session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            events: '{{tools.events}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace:\
  \ data-collection-pipeline-api\n    description: Unified REST API for Adobe data collection pipeline management.\n    resources:\n    - path: /v1/event-forwarding-properties\n      name: event-forwarding-properties\n      description: Server-side event forwarding properties\n      operations:\n      - method: GET\n        name: list-event-forwarding-properties\n        description: List event forwarding properties\n        call: event-forwarding.list-properties\n        with:\n          companyId: rest.companyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/event-forwarding-rules\n      name: event-forwarding-rules\n      description: Event forwarding rules\n      operations:\n      - method: GET\n        name: list-event-forwarding-rules\n        description: List event forwarding rules\n        call: event-forwarding.list-rules\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n    - path: /v1/secrets\n      name: secrets\n      description: Secrets for event forwarding destinations\n      operations:\n      - method: GET\n        name: list-secrets\n        description: List secrets for a property\n        call: event-forwarding.list-secrets\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Edge Network data ingestion\n      operations:\n      - method: POST\n        name: send-interactive-event\n        description: Send an interactive event to Edge Network\n        call: data-collection.interact\n        with:\n          datastreamId: rest.datastreamId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: send-batch-events\n        description: Send batch events to Edge Network\n        call: data-collection.collect\n        with:\n          datastreamId:\
  \ rest.datastreamId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: data-collection-pipeline-mcp\n    transport: http\n    description: MCP server for AI-assisted Adobe data collection pipeline management.\n    tools:\n    - name: list-event-forwarding-properties\n      description: List server-side event forwarding properties\n      hints:\n        readOnly: true\n        openWorld: true\n      call: event-forwarding.list-properties\n      with:\n        companyId: tools.companyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-event-forwarding-property\n      description: Create a new event forwarding property\n      hints:\n        readOnly: false\n      call: event-forwarding.create-property\n      with:\n        companyId: tools.companyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-event-forwarding-rules\n      description: List\
  \ event forwarding rules for a property\n      hints:\n        readOnly: true\n        openWorld: true\n      call: event-forwarding.list-rules\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-event-forwarding-rule\n      description: Create a new event forwarding rule\n      hints:\n        readOnly: false\n      call: event-forwarding.create-rule\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-secrets\n      description: List secrets for authenticating with forwarding destinations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: event-forwarding.list-secrets\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-secret\n      description: Create a secret for an event forwarding destination\n      hints:\n\
  \        readOnly: false\n      call: event-forwarding.create-secret\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-interactive-event\n      description: Send an interactive event to Adobe Edge Network\n      hints:\n        readOnly: false\n      call: data-collection.interact\n      with:\n        datastreamId: tools.datastreamId\n        event: tools.event\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-batch-events\n      description: Send batch events to Adobe Edge Network\n      hints:\n        readOnly: false\n      call: data-collection.collect\n      with:\n        datastreamId: tools.datastreamId\n        events: tools.events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-media-session\n      description: Start a media tracking session\n      hints:\n        readOnly: false\n      call: data-collection.media-session-start\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: end-media-session\n      description: End a media tracking session\n      hints:\n        readOnly: false\n      call: data-collection.media-session-end\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-launch/refs/heads/main/capabilities/data-collection-pipeline.yaml
tags:
- Adobe Launch
- Data Collection
- Event Forwarding
- Edge Network
tools:
- description: List server-side event forwarding properties
  hints:
    openWorld: true
    readOnly: true
  name: list-event-forwarding-properties
- description: Create a new event forwarding property
  hints:
    readOnly: false
  name: create-event-forwarding-property
- description: List event forwarding rules for a property
  hints:
    openWorld: true
    readOnly: true
  name: list-event-forwarding-rules
- description: Create a new event forwarding rule
  hints:
    readOnly: false
  name: create-event-forwarding-rule
- description: List secrets for authenticating with forwarding destinations
  hints:
    openWorld: true
    readOnly: true
  name: list-secrets
- description: Create a secret for an event forwarding destination
  hints:
    readOnly: false
  name: create-secret
- description: Send an interactive event to Adobe Edge Network
  hints:
    readOnly: false
  name: send-interactive-event
- description: Send batch events to Adobe Edge Network
  hints:
    readOnly: false
  name: send-batch-events
- description: Start a media tracking session
  hints:
    readOnly: false
  name: start-media-session
- description: End a media tracking session
  hints:
    readOnly: false
  name: end-media-session
---
