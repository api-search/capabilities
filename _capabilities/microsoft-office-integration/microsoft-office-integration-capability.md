---
categories: []
consumed_apis: []
description: The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Microsoft Entra activity logs. Customers and partners can use this information to create new or enhance existing operations, security, and compliance-monitoring solutions for the enterprise. The API relies on Microsoft Entra ID and the OAuth2 protocol for authentication and authorization.
layout: capability
name: Microsoft Office Integration Microsoft Office 365 Management Activity API
operations:
- description: Microsoft Office Integration Start a subscription
  method: POST
  name: startsubscription
  path: /subscriptions/start
- description: Microsoft Office Integration Stop a subscription
  method: POST
  name: stopsubscription
  path: /subscriptions/stop
- description: Microsoft Office Integration List current subscriptions
  method: GET
  name: listsubscriptions
  path: /subscriptions/list
- description: Microsoft Office Integration List available content
  method: GET
  name: listavailablecontent
  path: /subscriptions/content
- description: Microsoft Office Integration List notifications
  method: GET
  name: listnotifications
  path: /subscriptions/notifications
- description: Microsoft Office Integration Retrieve resource friendly names
  method: GET
  name: listdlpsensitivetypes
  path: /resources/dlpSensitiveTypes
personas: []
provider_name: Microsoft Office Integration
provider_slug: microsoft-office-integration
search_terms:
- microsoft office integration list notifications
- microsoft 365
- integration
- microsoft office integration list available content
- listdlpsensitivetypes
- microsoft office integration start a subscription
- stopsubscription
- office
- microsoft office integration list current subscriptions
- microsoft office integration
- api
- microsoft office integration stop a subscription
- listsubscriptions
- office 365
- listavailablecontent
- startsubscription
- microsoft
- listnotifications
- microsoft office integration retrieve resource friendly names
slug: microsoft-office-integration-capability
source_filename: microsoft-office-integration-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Office Integration Microsoft Office 365 Management Activity API\n  description: The Office 365 Management Activity API provides information about various user, admin, system, and policy actions\n    and events from Office 365 and Microsoft Entra activity logs. Customers and partners can use this information to create\n    new or enhance existing operations, security, and compliance-monitoring solutions for the enterprise. The API relies on\n    Microsoft Entra ID and the OAuth2 protocol for authentication and authorization.\n  tags:\n  - Microsoft\n  - Office\n  - Integration\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-office-integration\n    baseUri: https://manage.office.com/api/v1.0/{tenant_id}/activity/feed\n    description: Microsoft Office Integration Microsoft Office 365 Management Activity API HTTP API.\n    authentication:\n      type:\
  \ bearer\n      token: '{{MICROSOFT_OFFICE_INTEGRATION_TOKEN}}'\n    resources:\n    - name: subscriptions-start\n      path: /subscriptions/start\n      operations:\n      - name: startsubscription\n        method: POST\n        description: Microsoft Office Integration Start a subscription\n        inputParameters:\n        - name: contentType\n          in: query\n          type: string\n          required: true\n          description: Must be a valid content type.\n        - name: PublisherIdentifier\n          in: query\n          type: string\n          description: The tenant GUID of the vendor coding against the API. Used for throttling the request rate.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-stop\n      path: /subscriptions/stop\n      operations:\n      - name: stopsubscription\n        method: POST\n        description: Microsoft Office Integration Stop a subscription\n\
  \        inputParameters:\n        - name: contentType\n          in: query\n          type: string\n          required: true\n        - name: PublisherIdentifier\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-list\n      path: /subscriptions/list\n      operations:\n      - name: listsubscriptions\n        method: GET\n        description: Microsoft Office Integration List current subscriptions\n        inputParameters:\n        - name: PublisherIdentifier\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-content\n      path: /subscriptions/content\n      operations:\n      - name: listavailablecontent\n        method: GET\n        description: Microsoft Office Integration List available content\n\
  \        inputParameters:\n        - name: contentType\n          in: query\n          type: string\n          required: true\n        - name: PublisherIdentifier\n          in: query\n          type: string\n        - name: startTime\n          in: query\n          type: string\n          description: Start of the time range (UTC). Must be specified together with endTime and no more than 24 hours apart.\n        - name: endTime\n          in: query\n          type: string\n          description: End of the time range (UTC). Must be specified together with startTime and no more than 24 hours apart.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-notifications\n      path: /subscriptions/notifications\n      operations:\n      - name: listnotifications\n        method: GET\n        description: Microsoft Office Integration List notifications\n        inputParameters:\n        - name:\
  \ contentType\n          in: query\n          type: string\n          required: true\n        - name: PublisherIdentifier\n          in: query\n          type: string\n        - name: startTime\n          in: query\n          type: string\n        - name: endTime\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources-dlpsensitivetypes\n      path: /resources/dlpSensitiveTypes\n      operations:\n      - name: listdlpsensitivetypes\n        method: GET\n        description: Microsoft Office Integration Retrieve resource friendly names\n        inputParameters:\n        - name: PublisherIdentifier\n          in: query\n          type: string\n        - name: Accept-Language\n          in: header\n          type: string\n          description: Language code for localized names (e.g. en-US, es).\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-office-integration-rest\n    description: REST adapter for Microsoft Office Integration Microsoft Office 365 Management Activity API.\n    resources:\n    - path: /subscriptions/start\n      name: startsubscription\n      operations:\n      - method: POST\n        name: startsubscription\n        description: Microsoft Office Integration Start a subscription\n        call: microsoft-office-integration.startsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/stop\n      name: stopsubscription\n      operations:\n      - method: POST\n        name: stopsubscription\n        description: Microsoft Office Integration Stop a subscription\n        call: microsoft-office-integration.stopsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/list\n\
  \      name: listsubscriptions\n      operations:\n      - method: GET\n        name: listsubscriptions\n        description: Microsoft Office Integration List current subscriptions\n        call: microsoft-office-integration.listsubscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/content\n      name: listavailablecontent\n      operations:\n      - method: GET\n        name: listavailablecontent\n        description: Microsoft Office Integration List available content\n        call: microsoft-office-integration.listavailablecontent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/notifications\n      name: listnotifications\n      operations:\n      - method: GET\n        name: listnotifications\n        description: Microsoft Office Integration List notifications\n        call: microsoft-office-integration.listnotifications\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /resources/dlpSensitiveTypes\n      name: listdlpsensitivetypes\n      operations:\n      - method: GET\n        name: listdlpsensitivetypes\n        description: Microsoft Office Integration Retrieve resource friendly names\n        call: microsoft-office-integration.listdlpsensitivetypes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-office-integration-mcp\n    transport: http\n    description: MCP adapter for Microsoft Office Integration Microsoft Office 365 Management Activity API for AI agent use.\n    tools:\n    - name: startsubscription\n      description: Microsoft Office Integration Start a subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-office-integration.startsubscription\n      with:\n        contentType: tools.contentType\n        PublisherIdentifier: tools.PublisherIdentifier\n\
  \      inputParameters:\n      - name: contentType\n        type: string\n        description: Must be a valid content type.\n        required: true\n      - name: PublisherIdentifier\n        type: string\n        description: The tenant GUID of the vendor coding against the API. Used for throttling the request rate.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopsubscription\n      description: Microsoft Office Integration Stop a subscription\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-office-integration.stopsubscription\n      with:\n        contentType: tools.contentType\n        PublisherIdentifier: tools.PublisherIdentifier\n      inputParameters:\n      - name: contentType\n        type: string\n        description: contentType\n        required: true\n      - name: PublisherIdentifier\n        type: string\n        description: PublisherIdentifier\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listsubscriptions\n      description: Microsoft Office Integration List current subscriptions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-office-integration.listsubscriptions\n      with:\n        PublisherIdentifier: tools.PublisherIdentifier\n      inputParameters:\n      - name: PublisherIdentifier\n        type: string\n        description: PublisherIdentifier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listavailablecontent\n      description: Microsoft Office Integration List available content\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-office-integration.listavailablecontent\n      with:\n        contentType: tools.contentType\n        PublisherIdentifier: tools.PublisherIdentifier\n        startTime: tools.startTime\n        endTime: tools.endTime\n\
  \      inputParameters:\n      - name: contentType\n        type: string\n        description: contentType\n        required: true\n      - name: PublisherIdentifier\n        type: string\n        description: PublisherIdentifier\n      - name: startTime\n        type: string\n        description: Start of the time range (UTC). Must be specified together with endTime and no more than 24 hours apart.\n      - name: endTime\n        type: string\n        description: End of the time range (UTC). Must be specified together with startTime and no more than 24 hours apart.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnotifications\n      description: Microsoft Office Integration List notifications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-office-integration.listnotifications\n      with:\n        contentType: tools.contentType\n        PublisherIdentifier: tools.PublisherIdentifier\n\
  \        startTime: tools.startTime\n        endTime: tools.endTime\n      inputParameters:\n      - name: contentType\n        type: string\n        description: contentType\n        required: true\n      - name: PublisherIdentifier\n        type: string\n        description: PublisherIdentifier\n      - name: startTime\n        type: string\n        description: startTime\n      - name: endTime\n        type: string\n        description: endTime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdlpsensitivetypes\n      description: Microsoft Office Integration Retrieve resource friendly names\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-office-integration.listdlpsensitivetypes\n      with:\n        PublisherIdentifier: tools.PublisherIdentifier\n      inputParameters:\n      - name: PublisherIdentifier\n        type: string\n        description: PublisherIdentifier\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_OFFICE_INTEGRATION_TOKEN: MICROSOFT_OFFICE_INTEGRATION_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-office-integration/refs/heads/main/capabilities/microsoft-office-integration-capability.yaml
tags:
- Microsoft
- Office
- Integration
- API
tools:
- description: Microsoft Office Integration Start a subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startsubscription
- description: Microsoft Office Integration Stop a subscription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopsubscription
- description: Microsoft Office Integration List current subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubscriptions
- description: Microsoft Office Integration List available content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listavailablecontent
- description: Microsoft Office Integration List notifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnotifications
- description: Microsoft Office Integration Retrieve resource friendly names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdlpsensitivetypes
---
