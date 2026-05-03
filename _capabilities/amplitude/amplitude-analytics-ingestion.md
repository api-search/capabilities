---
categories:
- analytics
consumed_apis:
- attribution-api
- http-v2-api
- identify-api
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
- feature flags
- privacy compliance
- identify api identifyUser
- amplitude
- uploadEvents
- manage and evaluate a/b experiments and feature flags. for product managers.
- runs experiments and feature flags
- http v2 api uploadEvents
- amplitude send attribution data
- amplitude identify a user
- amplitude upload events
- sendAttribution
- scim provisioning and privacy compliance. for it admins and compliance teams.
- identifyUser
- unified workflow for sending events and identifying users. for data engineers.
- manages privacy and compliance
- product analytics
- a/b testing
- user behavior
- identity management
- analytics
- analyzes data and manages cohorts
- attribution api sendAttribution
- experimentation
- data governance
- export raw event data and manage behavioral cohorts. for data analysts.
- event ingestion
- ingests and exports event data
- manage event schemas and chart annotations. for data governance teams.
slug: amplitude-analytics-ingestion
source_filename: amplitude-analytics-ingestion.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amplitude Analytics Ingestion\n  description: Unified workflow for sending events and identifying users. For data engineers.\n  tags:\n  - Amplitude\n  - Analytics\n  - Event Ingestion\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AMPLITUDE_API_KEY: AMPLITUDE_API_KEY\ncapability:\n  consumes:\n  - import: attribution-api\n    location: ./shared/attribution-api.yaml\n  - import: http-v2-api\n    location: ./shared/http-v2-api.yaml\n  - import: identify-api\n    location: ./shared/identify-api.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amplitude-analytics-ingestion-api\n    description: REST API for Amplitude Analytics Ingestion\n    resources:\n    - path: /v1/attribution\n      name: attribution\n      operations:\n      - method: POST\n        name: sendAttribution\n        description: Amplitude Send Attribution Data\n        call: attribution-api.sendAttribution\n  \
  \      with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      operations:\n      - method: POST\n        name: uploadEvents\n        description: Amplitude Upload Events\n        call: http-v2-api.uploadEvents\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/identify\n      name: identify\n      operations:\n      - method: POST\n        name: identifyUser\n        description: Amplitude Identify a User\n        call: identify-api.identifyUser\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amplitude-analytics-ingestion-mcp\n    transport: http\n    description: MCP for Amplitude Analytics Ingestion\n    tools:\n    - name: attribution-api-sendAttribution\n      description: Amplitude Send Attribution Data\n      hints:\n        readOnly: false\n      call: attribution-api.sendAttribution\n\
  \      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: http-v2-api-uploadEvents\n      description: Amplitude Upload Events\n      hints:\n        readOnly: false\n      call: http-v2-api.uploadEvents\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: identify-api-identifyUser\n      description: Amplitude Identify a User\n      hints:\n        readOnly: false\n      call: identify-api.identifyUser\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
