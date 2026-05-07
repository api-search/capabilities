---
categories: []
consumed_apis: []
description: REST APIs under the Microsoft Graph /copilot/ namespace that enable secure access to Microsoft 365 Copilot capabilities including retrieval, search, chat, interaction export, and change notifications. These APIs provide production-ready AI capabilities that work directly with Microsoft 365 data while respecting existing permissions, sensitivity labels, compliance controls, and policy enforcement.
layout: capability
name: Microsoft Copilot Microsoft 365 Copilot APIs
operations:
- description: Microsoft Copilot Retrieve Grounding Data
  method: POST
  name: copilot-retrieval
  path: /copilot/retrieval
- description: Microsoft Copilot Perform Hybrid Search
  method: POST
  name: copilot-search
  path: /copilot/search
- description: Microsoft Copilot Start a Chat Conversation
  method: POST
  name: copilot-chat-startconversation
  path: /copilot/chat/conversations
- description: Microsoft Copilot Continue a Chat Conversation
  method: POST
  name: copilot-chat-continueconversation
  path: /copilot/chat/conversations/{conversationId}/messages
- description: Microsoft Copilot List All Enterprise Copilot Interactions
  method: GET
  name: copilot-interactionhistory-getallenterpriseinter
  path: /copilot/interactionHistory/getAllEnterpriseInteractions
- description: Microsoft Copilot Create Subscription for Copilot Interaction Notifications
  method: POST
  name: copilot-changenotifications-createsubscription
  path: /subscriptions
personas: []
provider_name: Microsoft Copilot
provider_slug: microsoft-copilot
search_terms:
- extensibility
- copilot chat continueconversation
- copilot search
- microsoft 365
- microsoft copilot start a chat conversation
- api
- copilot changenotifications createsubscription
- copilot chat startconversation
- ai assistant
- artificial intelligence
- chatbot
- productivity
- microsoft
- microsoft copilot list all enterprise copilot interactions
- microsoft copilot perform hybrid search
- agents
- generative ai
- copilot interactionhistory getallenterpriseinter
- copilot
- copilot retrieval
- microsoft copilot continue a chat conversation
- microsoft copilot create subscription for copilot interaction notifications
- microsoft copilot retrieve grounding data
slug: microsoft-copilot-capability
source_filename: microsoft-copilot-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Copilot Microsoft 365 Copilot APIs\n  description: REST APIs under the Microsoft Graph /copilot/ namespace that enable secure access to Microsoft 365 Copilot\n    capabilities including retrieval, search, chat, interaction export, and change notifications. These APIs provide production-ready\n    AI capabilities that work directly with Microsoft 365 data while respecting existing permissions, sensitivity labels,\n    compliance controls, and policy enforcement.\n  tags:\n  - Microsoft\n  - Copilot\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-copilot\n    baseUri: https://graph.microsoft.com/v1.0\n    description: Microsoft Copilot Microsoft 365 Copilot APIs HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_COPILOT_TOKEN}}'\n    resources:\n    - name: copilot-retrieval\n      path: /copilot/retrieval\n      operations:\n\
  \      - name: copilot-retrieval\n        method: POST\n        description: Microsoft Copilot Retrieve Grounding Data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: copilot-search\n      path: /copilot/search\n      operations:\n      - name: copilot-search\n        method: POST\n        description: Microsoft Copilot Perform Hybrid Search\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: copilot-chat-conversations\n      path: /copilot/chat/conversations\n      operations:\n      - name: copilot-chat-startconversation\n        method: POST\n        description: Microsoft Copilot Start a Chat Conversation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: copilot-chat-conversations-conversationid-messag\n      path: /copilot/chat/conversations/{conversationId}/messages\n\
  \      operations:\n      - name: copilot-chat-continueconversation\n        method: POST\n        description: Microsoft Copilot Continue a Chat Conversation\n        inputParameters:\n        - name: conversationId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the conversation to continue.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: copilot-interactionhistory-getallenterpriseinter\n      path: /copilot/interactionHistory/getAllEnterpriseInteractions\n      operations:\n      - name: copilot-interactionhistory-getallenterpriseinter\n        method: GET\n        description: Microsoft Copilot List All Enterprise Copilot Interactions\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          description: OData filter expression to filter interactions by date range, user, or\
  \ application.\n        - name: $top\n          in: query\n          type: integer\n          description: Maximum number of interactions to return per page.\n        - name: $skipToken\n          in: query\n          type: string\n          description: Pagination token for retrieving the next page of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /subscriptions\n      operations:\n      - name: copilot-changenotifications-createsubscription\n        method: POST\n        description: Microsoft Copilot Create Subscription for Copilot Interaction Notifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-copilot-rest\n    description: REST adapter for Microsoft Copilot Microsoft 365 Copilot APIs.\n    resources:\n\
  \    - path: /copilot/retrieval\n      name: copilot-retrieval\n      operations:\n      - method: POST\n        name: copilot-retrieval\n        description: Microsoft Copilot Retrieve Grounding Data\n        call: microsoft-copilot.copilot-retrieval\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /copilot/search\n      name: copilot-search\n      operations:\n      - method: POST\n        name: copilot-search\n        description: Microsoft Copilot Perform Hybrid Search\n        call: microsoft-copilot.copilot-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /copilot/chat/conversations\n      name: copilot-chat-startconversation\n      operations:\n      - method: POST\n        name: copilot-chat-startconversation\n        description: Microsoft Copilot Start a Chat Conversation\n        call: microsoft-copilot.copilot-chat-startconversation\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /copilot/chat/conversations/{conversationId}/messages\n      name: copilot-chat-continueconversation\n      operations:\n      - method: POST\n        name: copilot-chat-continueconversation\n        description: Microsoft Copilot Continue a Chat Conversation\n        call: microsoft-copilot.copilot-chat-continueconversation\n        with:\n          conversationId: rest.conversationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /copilot/interactionHistory/getAllEnterpriseInteractions\n      name: copilot-interactionhistory-getallenterpriseinter\n      operations:\n      - method: GET\n        name: copilot-interactionhistory-getallenterpriseinter\n        description: Microsoft Copilot List All Enterprise Copilot Interactions\n        call: microsoft-copilot.copilot-interactionhistory-getallenterpriseinter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions\n     \
  \ name: copilot-changenotifications-createsubscription\n      operations:\n      - method: POST\n        name: copilot-changenotifications-createsubscription\n        description: Microsoft Copilot Create Subscription for Copilot Interaction Notifications\n        call: microsoft-copilot.copilot-changenotifications-createsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-copilot-mcp\n    transport: http\n    description: MCP adapter for Microsoft Copilot Microsoft 365 Copilot APIs for AI agent use.\n    tools:\n    - name: copilot-retrieval\n      description: Microsoft Copilot Retrieve Grounding Data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-copilot.copilot-retrieval\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copilot-search\n      description: Microsoft Copilot Perform Hybrid Search\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-copilot.copilot-search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copilot-chat-startconversation\n      description: Microsoft Copilot Start a Chat Conversation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-copilot.copilot-chat-startconversation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copilot-chat-continueconversation\n      description: Microsoft Copilot Continue a Chat Conversation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-copilot.copilot-chat-continueconversation\n      with:\n        conversationId: tools.conversationId\n      inputParameters:\n      - name: conversationId\n        type: string\n        description: The unique identifier of the conversation\
  \ to continue.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copilot-interactionhistory-getallenterpriseinter\n      description: Microsoft Copilot List All Enterprise Copilot Interactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-copilot.copilot-interactionhistory-getallenterpriseinter\n      with:\n        $filter: tools.$filter\n        $top: tools.$top\n        $skipToken: tools.$skipToken\n      inputParameters:\n      - name: $filter\n        type: string\n        description: OData filter expression to filter interactions by date range, user, or application.\n      - name: $top\n        type: integer\n        description: Maximum number of interactions to return per page.\n      - name: $skipToken\n        type: string\n        description: Pagination token for retrieving the next page of results.\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: copilot-changenotifications-createsubscription\n      description: Microsoft Copilot Create Subscription for Copilot Interaction Notifications\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-copilot.copilot-changenotifications-createsubscription\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_COPILOT_TOKEN: MICROSOFT_COPILOT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-copilot/refs/heads/main/capabilities/microsoft-copilot-capability.yaml
tags:
- Microsoft
- Copilot
- API
tools:
- description: Microsoft Copilot Retrieve Grounding Data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copilot-retrieval
- description: Microsoft Copilot Perform Hybrid Search
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copilot-search
- description: Microsoft Copilot Start a Chat Conversation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copilot-chat-startconversation
- description: Microsoft Copilot Continue a Chat Conversation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copilot-chat-continueconversation
- description: Microsoft Copilot List All Enterprise Copilot Interactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: copilot-interactionhistory-getallenterpriseinter
- description: Microsoft Copilot Create Subscription for Copilot Interaction Notifications
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copilot-changenotifications-createsubscription
---
