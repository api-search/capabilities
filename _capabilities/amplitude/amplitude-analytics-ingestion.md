---
categories:
- analytics
consumed_apis: []
description: Unified workflow for sending events and identifying users. For data engineers.
layout: capability
name: Amplitude Analytics Ingestion
operations:
- description: Amplitude Send Attribution Data
  method: POST
  name: sendAttribution
  path: /v1/attribution
- description: Amplitude Upload Events
  method: POST
  name: uploadEvents
  path: /v1/events
- description: Amplitude Identify a User
  method: POST
  name: identifyUser
  path: /v1/identify
personas: []
provider_name: Amplitude
provider_slug: amplitude
search_terms:
- analytics
- feature flags
- unified workflow for sending events and identifying users. for data engineers.
- manage event schemas and chart annotations. for data governance teams.
- experimentation
- runs experiments and feature flags
- manages privacy and compliance
- attribution api sendAttribution
- ingests and exports event data
- event ingestion
- identity management
- http v2 api uploadEvents
- product analytics
- analyzes data and manages cohorts
- privacy compliance
- amplitude upload events
- amplitude
- identify api identifyUser
- manage and evaluate a/b experiments and feature flags. for product managers.
- scim provisioning and privacy compliance. for it admins and compliance teams.
- identifyUser
- amplitude send attribution data
- amplitude identify a user
- a/b testing
- export raw event data and manage behavioral cohorts. for data analysts.
- data governance
- user behavior
- uploadEvents
- sendAttribution
slug: amplitude-analytics-ingestion
source_filename: amplitude-analytics-ingestion.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amplitude Analytics Ingestion\n  description: Unified workflow for sending events and identifying users. For data engineers.\n  tags:\n  - Amplitude\n  - Analytics\n  - Event Ingestion\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AMPLITUDE_API_KEY: AMPLITUDE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: attribution-api\n    baseUri: https://api2.amplitude.com\n    description: The Amplitude Attribution API allows developers to send attribution campaign events to Amplitude from ad\n      networks, attribution providers, or custom marketing tools. It associates users with the campaigns, channels, and creatives\n      that drove their acquisition or re-engagement. This API is used to enrich Amplitude user profiles with marketing attribution\n      data for campaign performance analysis and ROI measurement.\n    resources:\n    - name: attribution\n      path: /attribution\n\
  \      description: Attribution operations\n      operations:\n      - name: sendAttribution\n        method: POST\n        description: Amplitude Send Attribution Data\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: http-v2-api\n    baseUri: https://api2.amplitude.com\n    description: The Amplitude HTTP V2 API enables developers to send event data directly from servers or clients to Amplitude's\n      analytics platform. It supports uploading individual or batched events along with user properties, event properties,\n      and group properties. This API is the primary method for server-side event ingestion and is designed for high-throughput\n      data collection with built-in validation and error reporting.\n    resources:\n    - name: events\n      path: /events\n      description: Events operations\n      operations:\n      - name: uploadEvents\n\
  \        method: POST\n        description: Amplitude Upload Events\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: identify-api\n    baseUri: https://api2.amplitude.com\n    description: The Amplitude Identify API allows developers to update user properties for a specific user without needing\n      to send an accompanying event. This is useful for setting or modifying user attributes such as demographics, subscription\n      status, or preferences outside of the normal event tracking flow. The API supports operations like set, unset, append,\n      and prepend on user properties.\n    resources:\n    - name: identify\n      path: /identify\n      description: Identify operations\n      operations:\n      - name: identifyUser\n        method: POST\n        description: Amplitude Identify a User\n        inputParameters: []\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amplitude-analytics-ingestion-api\n    description: REST API for Amplitude Analytics Ingestion\n    resources:\n    - path: /v1/attribution\n      name: attribution\n      operations:\n      - method: POST\n        name: sendAttribution\n        description: Amplitude Send Attribution Data\n        call: attribution-api.sendAttribution\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      operations:\n      - method: POST\n        name: uploadEvents\n        description: Amplitude Upload Events\n        call: http-v2-api.uploadEvents\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/identify\n      name: identify\n      operations:\n      - method: POST\n        name: identifyUser\n\
  \        description: Amplitude Identify a User\n        call: identify-api.identifyUser\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amplitude-analytics-ingestion-mcp\n    transport: http\n    description: MCP for Amplitude Analytics Ingestion\n    tools:\n    - name: attribution-api-sendAttribution\n      description: Amplitude Send Attribution Data\n      hints:\n        readOnly: false\n      call: attribution-api.sendAttribution\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: http-v2-api-uploadEvents\n      description: Amplitude Upload Events\n      hints:\n        readOnly: false\n      call: http-v2-api.uploadEvents\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: identify-api-identifyUser\n      description: Amplitude Identify a User\n      hints:\n        readOnly: false\n      call: identify-api.identifyUser\n\
  \      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amplitude/refs/heads/main/capabilities/amplitude-analytics-ingestion.yaml
tags:
- Amplitude
- Analytics
- Event Ingestion
tools:
- description: Amplitude Send Attribution Data
  hints:
    readOnly: false
  name: attribution-api-sendAttribution
- description: Amplitude Upload Events
  hints:
    readOnly: false
  name: http-v2-api-uploadEvents
- description: Amplitude Identify a User
  hints:
    readOnly: false
  name: identify-api-identifyUser
---
