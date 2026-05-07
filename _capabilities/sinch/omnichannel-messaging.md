---
categories: []
consumed_apis: []
description: Unified omnichannel messaging workflow combining SMS batch messaging and Conversation API for multi-channel delivery across SMS, WhatsApp, RCS, Facebook Messenger, Viber, Telegram, and more. Used by marketing teams, customer engagement platforms, and notification services needing to reach customers on their preferred channel.
layout: capability
name: Sinch Omnichannel Messaging
operations:
- description: Send a batch SMS message to multiple recipients
  method: POST
  name: send-sms-batch
  path: /v1/sms/batches
- description: List sent SMS batches
  method: GET
  name: list-sms-batches
  path: /v1/sms/batches
- description: List inbound SMS messages
  method: GET
  name: list-inbound-sms
  path: /v1/sms/inbounds
- description: Send a message via any supported channel
  method: POST
  name: send-message
  path: /v1/messages
- description: List sent and received messages
  method: GET
  name: list-messages
  path: /v1/messages
- description: Create a new contact
  method: POST
  name: create-contact
  path: /v1/contacts
- description: List contacts
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: List conversation threads
  method: GET
  name: list-conversations
  path: /v1/conversations
personas: []
provider_name: Sinch
provider_slug: sinch
search_terms:
- send a message via any supported channel
- create a new omnichannel contact
- create a new contact
- list inbound sms
- list inbound sms messages
- send sms
- list messaging contacts
- list sent sms batches
- get sms delivery report
- list received inbound sms messages
- list sent and received messages across all channels
- send a batch sms message to one or more phone numbers
- create contact
- send omnichannel message
- manage messaging contacts
- send sms messages in bulk
- get delivery report for an sms batch
- sms
- whatsapp
- send a batch sms message to multiple recipients
- cpaas
- send message
- list conversations
- list sent sms batches with delivery status
- send omnichannel messages via conversation api
- conversation
- list contacts
- list messages
- verification
- send a message via whatsapp, rcs, facebook messenger, viber, or other channels
- send sms batch
- list conversation threads
- voice
- omnichannel
- retrieve received sms messages
- list sms batches
- messaging
- list sent and received messages
- manage conversation threads
- list conversation threads across channels
- communications
slug: omnichannel-messaging
source_filename: omnichannel-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sinch Omnichannel Messaging\n  description: Unified omnichannel messaging workflow combining SMS batch messaging and Conversation API for multi-channel\n    delivery across SMS, WhatsApp, RCS, Facebook Messenger, Viber, Telegram, and more. Used by marketing teams, customer engagement\n    platforms, and notification services needing to reach customers on their preferred channel.\n  tags:\n  - Messaging\n  - SMS\n  - Omnichannel\n  - WhatsApp\n  - Conversation\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SINCH_API_TOKEN: SINCH_API_TOKEN\n    SINCH_SERVICE_PLAN_ID: SINCH_SERVICE_PLAN_ID\n    SINCH_PROJECT_ID: SINCH_PROJECT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: sinch-sms\n    baseUri: https://us.sms.api.sinch.com\n    description: Sinch SMS API for global messaging\n    authentication:\n      type: bearer\n      token: '{{SINCH_API_TOKEN}}'\n    resources:\n    - name: batches\n\
  \      path: /xms/v1/{service_plan_id}/batches\n      description: Send and manage SMS batches\n      operations:\n      - name: send-batch\n        method: POST\n        description: Send a batch SMS message to one or more recipients\n        inputParameters:\n        - name: service_plan_id\n          in: path\n          type: string\n          required: true\n          description: The service plan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            from: '{{tools.from}}'\n            to: '{{tools.to}}'\n            body: '{{tools.body}}'\n      - name: list-batches\n        method: GET\n        description: List SMS batches\n        inputParameters:\n        - name: service_plan_id\n          in: path\n          type: string\n          required: true\n          description: The service plan ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: delivery-reports\n      path: /xms/v1/{service_plan_id}/batches/{batch_id}/delivery_report\n      description: Retrieve delivery reports for SMS batches\n      operations:\n      - name: get-batch-delivery-report\n        method: GET\n        description: Retrieve a batch delivery report\n        inputParameters:\n        - name: service_plan_id\n          in: path\n          type: string\n          required: true\n          description: The service plan ID\n        - name: batch_id\n          in: path\n          type: string\n          required: true\n          description: The batch identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inbound-messages\n      path: /xms/v1/{service_plan_id}/inbounds\n      description: Retrieve inbound SMS messages\n      operations:\n      - name: list-inbound-messages\n  \
  \      method: GET\n        description: List inbound SMS messages\n        inputParameters:\n        - name: service_plan_id\n          in: path\n          type: string\n          required: true\n          description: The service plan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: sinch-conversation\n    baseUri: https://us.conversation.api.sinch.com\n    description: Sinch Conversation API for omnichannel messaging\n    authentication:\n      type: bearer\n      token: '{{SINCH_API_TOKEN}}'\n    resources:\n    - name: messages\n      path: /v1/projects/{project_id}/messages\n      description: Send and manage messages across channels\n      operations:\n      - name: send-message\n        method: POST\n        description: Send a message across any supported channel\n        inputParameters:\n        - name: project_id\n          in: path\n          type: string\n    \
  \      required: true\n          description: The Sinch project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            app_id: '{{tools.app_id}}'\n            recipient: '{{tools.recipient}}'\n            message: '{{tools.message}}'\n      - name: list-messages\n        method: GET\n        description: List messages\n        inputParameters:\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: The Sinch project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /v1/projects/{project_id}/contacts\n      description: Manage conversation contacts\n      operations:\n      - name: create-contact\n        method: POST\n        description: Create a new contact\n\
  \        inputParameters:\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: The Sinch project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            channel_identities: '{{tools.channel_identities}}'\n            display_name: '{{tools.display_name}}'\n      - name: list-contacts\n        method: GET\n        description: List contacts\n        inputParameters:\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: The Sinch project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations\n      path: /v1/projects/{project_id}/conversations\n      description: Manage conversation threads\n      operations:\n\
  \      - name: list-conversations\n        method: GET\n        description: List conversations\n        inputParameters:\n        - name: project_id\n          in: path\n          type: string\n          required: true\n          description: The Sinch project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: omnichannel-messaging-api\n    description: Unified REST API for Sinch omnichannel messaging workflows.\n    resources:\n    - path: /v1/sms/batches\n      name: sms-batches\n      description: Send SMS messages in bulk\n      operations:\n      - method: POST\n        name: send-sms-batch\n        description: Send a batch SMS message to multiple recipients\n        call: sinch-sms.send-batch\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-sms-batches\n        description:\
  \ List sent SMS batches\n        call: sinch-sms.list-batches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sms/inbounds\n      name: sms-inbound\n      description: Retrieve received SMS messages\n      operations:\n      - method: GET\n        name: list-inbound-sms\n        description: List inbound SMS messages\n        call: sinch-sms.list-inbound-messages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/messages\n      name: messages\n      description: Send omnichannel messages via Conversation API\n      operations:\n      - method: POST\n        name: send-message\n        description: Send a message via any supported channel\n        call: sinch-conversation.send-message\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-messages\n        description: List sent and received messages\n        call: sinch-conversation.list-messages\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts\n      name: contacts\n      description: Manage messaging contacts\n      operations:\n      - method: POST\n        name: create-contact\n        description: Create a new contact\n        call: sinch-conversation.create-contact\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-contacts\n        description: List contacts\n        call: sinch-conversation.list-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/conversations\n      name: conversations\n      description: Manage conversation threads\n      operations:\n      - method: GET\n        name: list-conversations\n        description: List conversation threads\n        call: sinch-conversation.list-conversations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n\
  \    namespace: omnichannel-messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted omnichannel messaging and customer engagement.\n    tools:\n    - name: send-sms\n      description: Send a batch SMS message to one or more phone numbers\n      hints:\n        readOnly: false\n        destructive: false\n      call: sinch-sms.send-batch\n      with:\n        from: tools.from\n        to: tools.to\n        body: tools.body\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sms-batches\n      description: List sent SMS batches with delivery status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sinch-sms.list-batches\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sms-delivery-report\n      description: Get delivery report for an SMS batch\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sinch-sms.get-batch-delivery-report\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-inbound-sms\n      description: List received inbound SMS messages\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sinch-sms.list-inbound-messages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-omnichannel-message\n      description: Send a message via WhatsApp, RCS, Facebook Messenger, Viber, or other channels\n      hints:\n        readOnly: false\n        destructive: false\n      call: sinch-conversation.send-message\n      with:\n        app_id: tools.app_id\n        recipient: tools.recipient\n        message: tools.message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-messages\n      description: List sent and received messages across all channels\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sinch-conversation.list-messages\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: create-contact\n      description: Create a new omnichannel contact\n      hints:\n        readOnly: false\n        destructive: false\n      call: sinch-conversation.create-contact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-contacts\n      description: List messaging contacts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sinch-conversation.list-contacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-conversations\n      description: List conversation threads across channels\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sinch-conversation.list-conversations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sinch/refs/heads/main/capabilities/omnichannel-messaging.yaml
tags:
- Messaging
- SMS
- Omnichannel
- WhatsApp
- Conversation
tools:
- description: Send a batch SMS message to one or more phone numbers
  hints:
    destructive: false
    readOnly: false
  name: send-sms
- description: List sent SMS batches with delivery status
  hints:
    openWorld: true
    readOnly: true
  name: list-sms-batches
- description: Get delivery report for an SMS batch
  hints:
    openWorld: false
    readOnly: true
  name: get-sms-delivery-report
- description: List received inbound SMS messages
  hints:
    openWorld: true
    readOnly: true
  name: list-inbound-sms
- description: Send a message via WhatsApp, RCS, Facebook Messenger, Viber, or other channels
  hints:
    destructive: false
    readOnly: false
  name: send-omnichannel-message
- description: List sent and received messages across all channels
  hints:
    openWorld: true
    readOnly: true
  name: list-messages
- description: Create a new omnichannel contact
  hints:
    destructive: false
    readOnly: false
  name: create-contact
- description: List messaging contacts
  hints:
    openWorld: true
    readOnly: true
  name: list-contacts
- description: List conversation threads across channels
  hints:
    openWorld: true
    readOnly: true
  name: list-conversations
---
