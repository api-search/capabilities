---
categories:
- crm-sales
consumed_apis: []
description: Unified workflow for CRM users combining customer management, case management, sales, chatbot integration, and notifications across PeopleSoft CRM, Chatbot Integration, and Notification Framework APIs.
layout: capability
name: PeopleSoft Customer Engagement
operations:
- description: Retrieve customer records.
  method: GET
  name: list-customers
  path: /v1/customers
- description: Retrieve details for a specific customer.
  method: GET
  name: get-customer
  path: /v1/customers/{customerId}
- description: Retrieve support and service cases.
  method: GET
  name: list-cases
  path: /v1/cases
- description: Create a new support or service case.
  method: POST
  name: create-case
  path: /v1/cases
- description: Retrieve sales opportunities.
  method: GET
  name: list-opportunities
  path: /v1/opportunities
- description: Retrieve available chatbot intents.
  method: GET
  name: list-intents
  path: /v1/intents
- description: Process a chatbot intent fulfillment request.
  method: POST
  name: fulfill-intent
  path: /v1/intent-fulfillments
- description: Retrieve notifications for the current user.
  method: GET
  name: list-notifications
  path: /v1/notifications
- description: Send a notification via email, text, or in-app channels.
  method: POST
  name: send-notification
  path: /v1/notifications
personas: []
provider_name: PeopleSoft
provider_slug: peoplesoft
search_terms:
- sales
- supply chain management
- get customer
- sales opportunities
- retrieve customer records.
- case management
- peopletools platform services.
- list notifications
- peoplesoft
- individual customer details
- retrieve sales opportunities.
- retrieve details for a specific customer.
- list cases
- chatbot intents
- retrieve available chatbot intents.
- campus solutions.
- fulfill intent
- financial and supply chain management.
- customer records
- list intents
- human capital management.
- create case
- chatbot
- erp
- send notification
- financial management
- crm
- notification management
- hcm
- retrieve notifications for the current user.
- retrieve support and service cases.
- list customers
- list opportunities
- customer engagement
- campus solutions
- support and service cases
- enterprise software
- process a chatbot intent fulfillment request.
- chatbot intent fulfillments
- create a new support or service case.
- send a notification via email, text, or in-app channels.
slug: customer-engagement
source_filename: customer-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PeopleSoft Customer Engagement\n  description: Unified workflow for CRM users combining customer management, case management, sales, chatbot integration,\n    and notifications across PeopleSoft CRM, Chatbot Integration, and Notification Framework APIs.\n  tags:\n  - PeopleSoft\n  - CRM\n  - Customer Engagement\n  - Case Management\n  - Sales\n  - Chatbot\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n    PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: crm\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/crm/v1\n    description: PeopleSoft CRM API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: customers\n      path: /customers\n      description: Customer data operations\n  \
  \    operations:\n      - name: list-customers\n        method: GET\n        description: Retrieve customer records.\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search term for customer name or ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-customer\n        method: GET\n        description: Retrieve details for a specific customer.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: The customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases\n      path: /cases\n      description: Case management operations\n      operations:\n      - name: list-cases\n        method: GET\n        description:\
  \ Retrieve support and service cases.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-case\n        method: POST\n        description: Create a new support or service case.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            case: '{{tools.case}}'\n    - name: sales\n      path: /sales\n      description: Sales operations\n      operations:\n      - name: list-opportunities\n        method: GET\n        description: Retrieve sales opportunities.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: chatbot\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/chatbot/v1\n    description: PeopleSoft Chatbot Integration Framework API\n\
  \    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: intents\n      path: /\n      description: Chatbot integration operations\n      operations:\n      - name: list-intents\n        method: GET\n        description: Retrieve available chatbot intents and their configurations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fulfill-intent\n        method: POST\n        description: Process a chatbot intent fulfillment request from Oracle Digital Assistant.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            intent: '{{tools.intent}}'\n            parameters: '{{tools.parameters}}'\n            userId: '{{tools.userId}}'\n  - type: http\n    namespace: notification-framework\n\
  \    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/notifications/v1\n    description: PeopleSoft Notification Framework API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: notifications\n      path: /notifications\n      description: Notification management operations\n      operations:\n      - name: list-notifications\n        method: GET\n        description: Retrieve a list of notifications for the current user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-notification\n        method: POST\n        description: Send a notification via email, text, or in-app channels.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n           \
  \ channel: '{{tools.channel}}'\n            recipients: '{{tools.recipients}}'\n            message: '{{tools.message}}'\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: customer-engagement-api\n    description: Unified REST API for PeopleSoft customer engagement workflows.\n    resources:\n    - path: /v1/customers\n      name: customers\n      description: Customer records\n      operations:\n      - method: GET\n        name: list-customers\n        description: Retrieve customer records.\n        call: crm.list-customers\n        with:\n          search: rest.search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{customerId}\n      name: customer-detail\n      description: Individual customer details\n      operations:\n      - method: GET\n        name: get-customer\n        description: Retrieve details for a specific customer.\n        call: crm.get-customer\n        with:\n          customerId: rest.customerId\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cases\n      name: cases\n      description: Support and service cases\n      operations:\n      - method: GET\n        name: list-cases\n        description: Retrieve support and service cases.\n        call: crm.list-cases\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-case\n        description: Create a new support or service case.\n        call: crm.create-case\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/opportunities\n      name: opportunities\n      description: Sales opportunities\n      operations:\n      - method: GET\n        name: list-opportunities\n        description: Retrieve sales opportunities.\n        call: crm.list-opportunities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/intents\n      name: intents\n      description:\
  \ Chatbot intents\n      operations:\n      - method: GET\n        name: list-intents\n        description: Retrieve available chatbot intents.\n        call: chatbot.list-intents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/intent-fulfillments\n      name: fulfillments\n      description: Chatbot intent fulfillments\n      operations:\n      - method: POST\n        name: fulfill-intent\n        description: Process a chatbot intent fulfillment request.\n        call: chatbot.fulfill-intent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/notifications\n      name: notifications\n      description: Notification management\n      operations:\n      - method: GET\n        name: list-notifications\n        description: Retrieve notifications for the current user.\n        call: notification-framework.list-notifications\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ POST\n        name: send-notification\n        description: Send a notification via email, text, or in-app channels.\n        call: notification-framework.send-notification\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: customer-engagement-mcp\n    transport: http\n    description: MCP server for AI-assisted PeopleSoft customer engagement workflows.\n    tools:\n    - name: list-customers\n      description: Retrieve customer records.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: crm.list-customers\n      with:\n        search: tools.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer\n      description: Retrieve details for a specific customer.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: crm.get-customer\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-cases\n      description: Retrieve support and service cases.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: crm.list-cases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-case\n      description: Create a new support or service case.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: crm.create-case\n      with:\n        case: tools.case\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-opportunities\n      description: Retrieve sales opportunities.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: crm.list-opportunities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-intents\n      description: Retrieve available chatbot intents.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: chatbot.list-intents\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fulfill-intent\n      description: Process a chatbot intent fulfillment request.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chatbot.fulfill-intent\n      with:\n        intent: tools.intent\n        parameters: tools.parameters\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-notifications\n      description: Retrieve notifications for the current user.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: notification-framework.list-notifications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-notification\n      description: Send a notification via email, text, or in-app channels.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: notification-framework.send-notification\n\
  \      with:\n        channel: tools.channel\n        recipients: tools.recipients\n        message: tools.message\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/capabilities/customer-engagement.yaml
tags:
- PeopleSoft
- CRM
- Customer Engagement
- Case Management
- Sales
- Chatbot
tools:
- description: Retrieve customer records.
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Retrieve details for a specific customer.
  hints:
    openWorld: true
    readOnly: true
  name: get-customer
- description: Retrieve support and service cases.
  hints:
    openWorld: true
    readOnly: true
  name: list-cases
- description: Create a new support or service case.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-case
- description: Retrieve sales opportunities.
  hints:
    openWorld: true
    readOnly: true
  name: list-opportunities
- description: Retrieve available chatbot intents.
  hints:
    openWorld: true
    readOnly: true
  name: list-intents
- description: Process a chatbot intent fulfillment request.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fulfill-intent
- description: Retrieve notifications for the current user.
  hints:
    openWorld: true
    readOnly: true
  name: list-notifications
- description: Send a notification via email, text, or in-app channels.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-notification
---
