---
categories: []
consumed_apis: []
description: The Azure Event Hubs Data Plane REST API enables you to send events to and interact with Event Hubs directly. This API operates against the Event Hubs service endpoint at {namespace}.servicebus.windows.net and supports sending individual events, batch events, partition-specific events, and events with publisher identity. Authentication is via Azure Active Directory tokens or Shared Access Signature (SAS) tokens.
layout: capability
name: Azure Event Hubs Data Plane REST API
operations:
- description: Azure Event Hubs Send event
  method: POST
  name: sendevent
  path: /{eventHubPath}/messages
- description: Azure Event Hubs Send batch events
  method: POST
  name: sendbatchevents
  path: /{eventHubPath}/messages?batch=true
- description: Azure Event Hubs Send partition event
  method: POST
  name: sendpartitionevent
  path: /{eventHubPath}/partitions/{partitionId}/messages
- description: Azure Event Hubs Send event with publisher ID
  method: POST
  name: sendeventwithpublisherid
  path: /{eventHubPath}/publishers/{publisherId}/messages
personas: []
provider_name: Azure Event Hubs
provider_slug: microsoft-azure-event-hubs
search_terms:
- azure
- real-time processing
- hubs
- message ingestion
- iot
- sendevent
- api
- sendpartitionevent
- azure event hubs send event
- sendbatchevents
- event
- event streaming
- azure event hubs send event with publisher id
- microsoft
- azure event hubs send partition event
- big data
- sendeventwithpublisherid
- azure event hubs send batch events
slug: microsoft-azure-event-hubs-capability
source_filename: microsoft-azure-event-hubs-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Event Hubs Data Plane REST API\n  description: The Azure Event Hubs Data Plane REST API enables you to send events to and interact with Event Hubs directly.\n    This API operates against the Event Hubs service endpoint at {namespace}.servicebus.windows.net and supports sending individual\n    events, batch events, partition-specific events, and events with publisher identity. Authentication is via Azure Active\n    Directory tokens or Shared Access Signature (SAS) tokens.\n  tags:\n  - Microsoft\n  - Azure\n  - Event\n  - Hubs\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-azure-event-hubs\n    baseUri: https://my-namespace.servicebus.windows.net\n    description: Azure Event Hubs Data Plane REST API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{MICROSOFT_AZURE_EVENT_HUBS_TOKEN}}'\n\
  \    resources:\n    - name: eventhubpath-messages\n      path: /{eventHubPath}/messages\n      operations:\n      - name: sendevent\n        method: POST\n        description: Azure Event Hubs Send event\n        inputParameters:\n        - name: x-ms-retrypolicy\n          in: header\n          type: string\n          description: Set to NoRetry to disable automatic retry on send operations when transient errors occur.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: eventhubpath-messages-batch-true\n      path: /{eventHubPath}/messages?batch=true\n      operations:\n      - name: sendbatchevents\n        method: POST\n        description: Azure Event Hubs Send batch events\n        inputParameters:\n        - name: x-ms-retrypolicy\n          in: header\n          type: string\n          description: Set to NoRetry to disable automatic retry on send operations when transient errors occur.\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: eventhubpath-partitions-partitionid-messages\n      path: /{eventHubPath}/partitions/{partitionId}/messages\n      operations:\n      - name: sendpartitionevent\n        method: POST\n        description: Azure Event Hubs Send partition event\n        inputParameters:\n        - name: x-ms-retrypolicy\n          in: header\n          type: string\n          description: Set to NoRetry to disable automatic retry on send operations when transient errors occur.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: eventhubpath-publishers-publisherid-messages\n      path: /{eventHubPath}/publishers/{publisherId}/messages\n      operations:\n      - name: sendeventwithpublisherid\n        method: POST\n        description: Azure Event Hubs Send event with publisher ID\n\
  \        inputParameters:\n        - name: x-ms-retrypolicy\n          in: header\n          type: string\n          description: Set to NoRetry to disable automatic retry on send operations when transient errors occur.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-azure-event-hubs-rest\n    description: REST adapter for Azure Event Hubs Data Plane REST API.\n    resources:\n    - path: /{eventHubPath}/messages\n      name: sendevent\n      operations:\n      - method: POST\n        name: sendevent\n        description: Azure Event Hubs Send event\n        call: microsoft-azure-event-hubs.sendevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{eventHubPath}/messages?batch=true\n      name: sendbatchevents\n      operations:\n      - method: POST\n        name: sendbatchevents\n        description:\
  \ Azure Event Hubs Send batch events\n        call: microsoft-azure-event-hubs.sendbatchevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{eventHubPath}/partitions/{partitionId}/messages\n      name: sendpartitionevent\n      operations:\n      - method: POST\n        name: sendpartitionevent\n        description: Azure Event Hubs Send partition event\n        call: microsoft-azure-event-hubs.sendpartitionevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{eventHubPath}/publishers/{publisherId}/messages\n      name: sendeventwithpublisherid\n      operations:\n      - method: POST\n        name: sendeventwithpublisherid\n        description: Azure Event Hubs Send event with publisher ID\n        call: microsoft-azure-event-hubs.sendeventwithpublisherid\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-azure-event-hubs-mcp\n\
  \    transport: http\n    description: MCP adapter for Azure Event Hubs Data Plane REST API for AI agent use.\n    tools:\n    - name: sendevent\n      description: Azure Event Hubs Send event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-event-hubs.sendevent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendbatchevents\n      description: Azure Event Hubs Send batch events\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-event-hubs.sendbatchevents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendpartitionevent\n      description: Azure Event Hubs Send partition event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-event-hubs.sendpartitionevent\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: sendeventwithpublisherid\n      description: Azure Event Hubs Send event with publisher ID\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-event-hubs.sendeventwithpublisherid\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_AZURE_EVENT_HUBS_TOKEN: MICROSOFT_AZURE_EVENT_HUBS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-event-hubs/refs/heads/main/capabilities/microsoft-azure-event-hubs-capability.yaml
tags:
- Microsoft
- Azure
- Event
- Hubs
- API
tools:
- description: Azure Event Hubs Send event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendevent
- description: Azure Event Hubs Send batch events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendbatchevents
- description: Azure Event Hubs Send partition event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendpartitionevent
- description: Azure Event Hubs Send event with publisher ID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendeventwithpublisherid
---
