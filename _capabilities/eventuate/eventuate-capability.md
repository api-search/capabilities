---
categories: []
consumed_apis: []
description: The Eventuate REST API provides HTTP endpoints for managing aggregates, events, subscriptions, and event-sourced entities in the Eventuate platform for distributed data management in microservices.
layout: capability
name: Eventuate REST API
operations:
- description: Create an entity
  method: POST
  name: createentity
  path: /entity/{entityType}
- description: Get an entity
  method: GET
  name: getentity
  path: /entity/{entityType}/{entityId}
- description: Update an entity
  method: POST
  name: updateentity
  path: /entity/{entityType}/{entityId}
- description: Get events for an entity
  method: GET
  name: getentityevents
  path: /entity/{entityType}/{entityId}/events
- description: Create an event subscription
  method: POST
  name: createsubscription
  path: /subscriptions
- description: Get a subscription
  method: GET
  name: getsubscription
  path: /subscriptions/{subscriptionId}
- description: Delete a subscription
  method: DELETE
  name: deletesubscription
  path: /subscriptions/{subscriptionId}
- description: Get events from a subscription
  method: GET
  name: getsubscriptionevents
  path: /subscriptions/{subscriptionId}/events
- description: Acknowledge events
  method: POST
  name: acknowledgeevents
  path: /subscriptions/{subscriptionId}/acknowledge
- description: Health check
  method: GET
  name: gethealth
  path: /health
personas: []
provider_name: Eventuate
provider_slug: eventuate
search_terms:
- event-driven
- getsubscriptionevents
- getentity
- api
- createsubscription
- acknowledgeevents
- create an event subscription
- health check
- acknowledge events
- event sourcing
- getsubscription
- deletesubscription
- sagas
- create an entity
- cqrs
- eventuate
- gethealth
- update an entity
- get events for an entity
- get an entity
- get a subscription
- delete a subscription
- updateentity
- getentityevents
- distributed data
- microservices
- createentity
- get events from a subscription
slug: eventuate-capability
source_filename: eventuate-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Eventuate REST API\n  description: The Eventuate REST API provides HTTP endpoints for managing aggregates, events, subscriptions, and event-sourced\n    entities in the Eventuate platform for distributed data management in microservices.\n  tags:\n  - Eventuate\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: eventuate\n    baseUri: http://localhost:8080\n    description: Eventuate REST API HTTP API.\n    resources:\n    - name: entity-entitytype\n      path: /entity/{entityType}\n      operations:\n      - name: createentity\n        method: POST\n        description: Create an entity\n        inputParameters:\n        - name: entityType\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-entitytype-entityid\n\
  \      path: /entity/{entityType}/{entityId}\n      operations:\n      - name: getentity\n        method: GET\n        description: Get an entity\n        inputParameters:\n        - name: entityType\n          in: path\n          type: string\n          required: true\n        - name: entityId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateentity\n        method: POST\n        description: Update an entity\n        inputParameters:\n        - name: entityType\n          in: path\n          type: string\n          required: true\n        - name: entityId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entity-entitytype-entityid-events\n      path: /entity/{entityType}/{entityId}/events\n\
  \      operations:\n      - name: getentityevents\n        method: GET\n        description: Get events for an entity\n        inputParameters:\n        - name: entityType\n          in: path\n          type: string\n          required: true\n        - name: entityId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /subscriptions\n      operations:\n      - name: createsubscription\n        method: POST\n        description: Create an event subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid\n      path: /subscriptions/{subscriptionId}\n      operations:\n      - name: getsubscription\n        method: GET\n        description: Get a subscription\n        inputParameters:\n\
  \        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesubscription\n        method: DELETE\n        description: Delete a subscription\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-events\n      path: /subscriptions/{subscriptionId}/events\n      operations:\n      - name: getsubscriptionevents\n        method: GET\n        description: Get events from a subscription\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n        - name: maxEvents\n          in: query\n     \
  \     type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-acknowledge\n      path: /subscriptions/{subscriptionId}/acknowledge\n      operations:\n      - name: acknowledgeevents\n        method: POST\n        description: Acknowledge events\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /health\n      operations:\n      - name: gethealth\n        method: GET\n        description: Health check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: eventuate-rest\n    description: REST adapter\
  \ for Eventuate REST API.\n    resources:\n    - path: /entity/{entityType}\n      name: createentity\n      operations:\n      - method: POST\n        name: createentity\n        description: Create an entity\n        call: eventuate.createentity\n        with:\n          entityType: rest.entityType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entity/{entityType}/{entityId}\n      name: getentity\n      operations:\n      - method: GET\n        name: getentity\n        description: Get an entity\n        call: eventuate.getentity\n        with:\n          entityType: rest.entityType\n          entityId: rest.entityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entity/{entityType}/{entityId}\n      name: updateentity\n      operations:\n      - method: POST\n        name: updateentity\n        description: Update an entity\n        call: eventuate.updateentity\n        with:\n          entityType: rest.entityType\n\
  \          entityId: rest.entityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entity/{entityType}/{entityId}/events\n      name: getentityevents\n      operations:\n      - method: GET\n        name: getentityevents\n        description: Get events for an entity\n        call: eventuate.getentityevents\n        with:\n          entityType: rest.entityType\n          entityId: rest.entityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions\n      name: createsubscription\n      operations:\n      - method: POST\n        name: createsubscription\n        description: Create an event subscription\n        call: eventuate.createsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}\n      name: getsubscription\n      operations:\n      - method: GET\n        name: getsubscription\n        description: Get a subscription\n\
  \        call: eventuate.getsubscription\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}\n      name: deletesubscription\n      operations:\n      - method: DELETE\n        name: deletesubscription\n        description: Delete a subscription\n        call: eventuate.deletesubscription\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/events\n      name: getsubscriptionevents\n      operations:\n      - method: GET\n        name: getsubscriptionevents\n        description: Get events from a subscription\n        call: eventuate.getsubscriptionevents\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/acknowledge\n\
  \      name: acknowledgeevents\n      operations:\n      - method: POST\n        name: acknowledgeevents\n        description: Acknowledge events\n        call: eventuate.acknowledgeevents\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /health\n      name: gethealth\n      operations:\n      - method: GET\n        name: gethealth\n        description: Health check\n        call: eventuate.gethealth\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: eventuate-mcp\n    transport: http\n    description: MCP adapter for Eventuate REST API for AI agent use.\n    tools:\n    - name: createentity\n      description: Create an entity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eventuate.createentity\n      with:\n        entityType: tools.entityType\n      inputParameters:\n\
  \      - name: entityType\n        type: string\n        description: entityType\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getentity\n      description: Get an entity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eventuate.getentity\n      with:\n        entityType: tools.entityType\n        entityId: tools.entityId\n      inputParameters:\n      - name: entityType\n        type: string\n        description: entityType\n        required: true\n      - name: entityId\n        type: string\n        description: entityId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateentity\n      description: Update an entity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eventuate.updateentity\n      with:\n        entityType: tools.entityType\n        entityId:\
  \ tools.entityId\n      inputParameters:\n      - name: entityType\n        type: string\n        description: entityType\n        required: true\n      - name: entityId\n        type: string\n        description: entityId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getentityevents\n      description: Get events for an entity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eventuate.getentityevents\n      with:\n        entityType: tools.entityType\n        entityId: tools.entityId\n      inputParameters:\n      - name: entityType\n        type: string\n        description: entityType\n        required: true\n      - name: entityId\n        type: string\n        description: entityId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsubscription\n      description: Create an event subscription\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eventuate.createsubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubscription\n      description: Get a subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eventuate.getsubscription\n      with:\n        subscriptionId: tools.subscriptionId\n      inputParameters:\n      - name: subscriptionId\n        type: string\n        description: subscriptionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesubscription\n      description: Delete a subscription\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: eventuate.deletesubscription\n      with:\n        subscriptionId: tools.subscriptionId\n      inputParameters:\n      - name: subscriptionId\n        type: string\n  \
  \      description: subscriptionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubscriptionevents\n      description: Get events from a subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eventuate.getsubscriptionevents\n      with:\n        subscriptionId: tools.subscriptionId\n        maxEvents: tools.maxEvents\n      inputParameters:\n      - name: subscriptionId\n        type: string\n        description: subscriptionId\n        required: true\n      - name: maxEvents\n        type: integer\n        description: maxEvents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acknowledgeevents\n      description: Acknowledge events\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eventuate.acknowledgeevents\n      with:\n        subscriptionId: tools.subscriptionId\n    \
  \  inputParameters:\n      - name: subscriptionId\n        type: string\n        description: subscriptionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethealth\n      description: Health check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eventuate.gethealth\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/eventuate/refs/heads/main/capabilities/eventuate-capability.yaml
tags:
- Eventuate
- API
tools:
- description: Create an entity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createentity
- description: Get an entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getentity
- description: Update an entity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateentity
- description: Get events for an entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getentityevents
- description: Create an event subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubscription
- description: Get a subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubscription
- description: Delete a subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesubscription
- description: Get events from a subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubscriptionevents
- description: Acknowledge events
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: acknowledgeevents
- description: Health check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealth
---
