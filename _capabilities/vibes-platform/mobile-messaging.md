---
categories: []
consumed_apis: []
description: Unified mobile messaging capability combining the Vibes Platform API and Vibes Connect API for end-to-end mobile engagement workflows. Covers SMS/MMS sending, broadcast campaign management, push notifications, acquisition campaigns, subscription list management, and event-triggered messages. Used by mobile marketing teams and developers building customer engagement workflows.
layout: capability
name: Vibes Mobile Messaging
operations:
- description: List all broadcasts for the company.
  method: GET
  name: list-broadcasts
  path: /v1/broadcasts
- description: Create a new broadcast message send.
  method: POST
  name: create-broadcast
  path: /v1/broadcasts
- description: Get broadcast details and status.
  method: GET
  name: get-broadcast
  path: /v1/broadcasts/{broadcast_id}
- description: List all acquisition campaigns.
  method: GET
  name: list-acquisition-campaigns
  path: /v1/acquisition-campaigns
- description: List pending participants in a campaign.
  method: GET
  name: list-pending-participants
  path: /v1/acquisition-campaigns/{campaign_id}/participants
- description: Add a person to an acquisition campaign.
  method: POST
  name: add-participant
  path: /v1/acquisition-campaigns/{campaign_id}/participants
- description: List all subscription lists.
  method: GET
  name: list-subscription-lists
  path: /v1/subscription-lists
- description: Get subscriber details by person key.
  method: GET
  name: get-person
  path: /v1/subscribers/{person_key}
- description: Submit an event to trigger SMS or push notifications.
  method: POST
  name: create-event
  path: /v1/events
- description: List all wallet passes.
  method: GET
  name: list-wallet-items
  path: /v1/wallet-passes
- description: Create a new wallet pass for a subscriber.
  method: POST
  name: create-wallet-item
  path: /v1/wallet-passes
- description: List all registered callbacks.
  method: GET
  name: list-callbacks
  path: /v1/callbacks
- description: Register a new callback endpoint.
  method: POST
  name: register-callback
  path: /v1/callbacks
- description: Send an SMS message via the Connect aggregation API.
  method: POST
  name: send-sms-message
  path: /v1/sms-messages
- description: Send an MMS message with pictures, links, or other media.
  method: POST
  name: send-mms-message
  path: /v1/mms-messages
- description: Retrieve carrier information for a mobile number.
  method: POST
  name: lookup-carrier
  path: /v1/carrier-lookup
personas: []
provider_name: Vibes Platform
provider_slug: vibes-platform
search_terms:
- list all broadcasts for the company.
- create event
- mms
- manage campaign participants.
- manage subscriber subscription lists.
- list wallet passes
- list pending participants in a campaign.
- get subscriber details by person key.
- push notifications
- list all mobile wallet passes (apple wallet and google pay) for the company.
- list all subscription lists.
- create a new broadcast message send.
- submit an event to trigger event-based sms messages or push notifications.
- add participant
- manage subscriber acquisition campaigns.
- send an mms message with pictures, links, or other multimedia content.
- get person
- broadcast messaging
- send sms message
- create wallet item
- list acquisition campaigns
- list wallet items
- list pending participants in an acquisition campaign.
- create broadcast
- get subscriber details and subscription status by person key.
- manage sms and push notification broadcasts.
- list all acquisition campaigns.
- submit an event to trigger sms or push notifications.
- send an mms message with pictures, links, or other media.
- acquisition campaigns
- list all registered callbacks.
- look up carrier information for mobile numbers.
- sms
- wallet passes
- list all wallet passes.
- mobile marketing
- create a new sms or push notification broadcast message send.
- list all subscriber subscription lists and their counts.
- send a transactional sms message directly via the vibes connect aggregation api.
- list callbacks
- subscription management
- manage individual subscribers.
- register callback
- manage opt-in and delivery status callbacks.
- look up the carrier and number type for a mobile number.
- list all registered callback endpoints for opt-in and delivery notifications.
- retrieve a specific broadcast.
- list subscription lists
- send mms message
- list all subscriber acquisition campaigns and their status.
- mobile engagement
- send an sms message via the connect aggregation api.
- send mms messages with multimedia content.
- retrieve carrier information for a mobile number.
- submit events to trigger messages.
- lookup carrier
- get details and delivery status for a specific broadcast.
- register a callback endpoint for opt-in or delivery status notifications.
- get subscriber
- create a new mobile wallet pass for a subscriber.
- add a person to an acquisition campaign.
- send transactional sms messages.
- list broadcasts
- get broadcast
- register a new callback endpoint.
- list pending participants
- create wallet pass
- manage mobile wallet passes.
- get broadcast details and status.
- create a new wallet pass for a subscriber.
- list all sms and push notification broadcasts for the company.
- rcs
- mobile messaging
slug: mobile-messaging
source_filename: mobile-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vibes Mobile Messaging\n  description: Unified mobile messaging capability combining the Vibes Platform API and Vibes Connect API for end-to-end mobile\n    engagement workflows. Covers SMS/MMS sending, broadcast campaign management, push notifications, acquisition campaigns,\n    subscription list management, and event-triggered messages. Used by mobile marketing teams and developers building customer\n    engagement workflows.\n  tags:\n  - Mobile Marketing\n  - SMS\n  - MMS\n  - Push Notifications\n  - Broadcast Messaging\n  - Acquisition Campaigns\n  - Subscription Management\n  - Mobile Engagement\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VIBES_PLATFORM_USERNAME: VIBES_PLATFORM_USERNAME\n    VIBES_PLATFORM_PASSWORD: VIBES_PLATFORM_PASSWORD\n    VIBES_COMPANY_KEY: VIBES_COMPANY_KEY\n    VIBES_CONNECT_USERNAME: VIBES_CONNECT_USERNAME\n    VIBES_CONNECT_PASSWORD: VIBES_CONNECT_PASSWORD\n\
  capability:\n  consumes:\n  - type: http\n    namespace: vibes-platform\n    baseUri: https://public-api.vibescm.com\n    description: Vibes Platform API for broadcast messaging, acquisition campaigns, and subscription management.\n    authentication:\n      type: basic\n      username: '{{VIBES_PLATFORM_USERNAME}}'\n      password: '{{VIBES_PLATFORM_PASSWORD}}'\n    resources:\n    - name: broadcasts\n      path: /companies/{company_key}/broadcasts\n      description: Manage SMS and push notification broadcasts.\n      operations:\n      - name: list-broadcasts\n        method: GET\n        description: Retrieve a list of broadcasts for the company.\n        inputParameters:\n        - name: company_key\n          in: path\n          type: string\n          required: true\n          description: Your Vibes company identifier.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter broadcasts by status (draft, scheduled,\
  \ sent, cancelled).\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page (max 100).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-broadcast\n        method: POST\n        description: Create a new broadcast (SMS or push notification send).\n        inputParameters:\n        - name: company_key\n          in: path\n          type: string\n          required: true\n          description: Your Vibes company identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.broadcast_name}}'\n    \
  \        message_type: '{{tools.message_type}}'\n            message_text: '{{tools.message_text}}'\n            subscription_list_id: '{{tools.subscription_list_id}}'\n            scheduled_at: '{{tools.scheduled_at}}'\n    - name: broadcast-detail\n      path: /companies/{company_key}/broadcasts/{broadcast_id}\n      description: Get, update individual broadcast.\n      operations:\n      - name: get-broadcast\n        method: GET\n        description: Retrieve metadata and status for a specific broadcast.\n        inputParameters:\n        - name: company_key\n          in: path\n          type: string\n          required: true\n          description: Your Vibes company identifier.\n        - name: broadcast_id\n          in: path\n          type: string\n          required: true\n          description: The broadcast identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acquisition-campaigns\n\
  \      path: /companies/{company_key}/campaigns/acquisition\n      description: Manage acquisition campaigns.\n      operations:\n      - name: list-acquisition-campaigns\n        method: GET\n        description: Retrieve all acquisition campaigns for the company.\n        inputParameters:\n        - name: company_key\n          in: path\n          type: string\n          required: true\n          description: Your Vibes company identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign-participants\n      path: /companies/{company_key}/campaigns/acquisition/{campaign_id}/participants\n      description: Manage acquisition campaign participants.\n      operations:\n      - name: list-pending-participants\n        method: GET\n        description: Search for pending participants in an acquisition campaign.\n        inputParameters:\n        - name: company_key\n          in: path\n   \
  \       type: string\n          required: true\n          description: Your Vibes company identifier.\n        - name: campaign_id\n          in: path\n          type: string\n          required: true\n          description: The campaign identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-participant\n        method: POST\n        description: Add a person to an acquisition campaign.\n        inputParameters:\n        - name: company_key\n          in: path\n          type: string\n          required: true\n          description: Your Vibes company identifier.\n        - name: campaign_id\n          in: path\n          type: string\n          required: true\n          description: The campaign identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            mobile_phone: '{{tools.mobile_phone}}'\n            external_person_id: '{{tools.external_person_id}}'\n    - name: subscription-lists\n      path: /companies/{company_key}/mobiledb/subscription_lists\n      description: Manage subscription lists.\n      operations:\n      - name: list-subscription-lists\n        method: GET\n        description: Retrieve all subscription lists for the company.\n        inputParameters:\n        - name: company_key\n          in: path\n          type: string\n          required: true\n          description: Your Vibes company identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: persons\n      path: /companies/{company_key}/mobiledb/persons/{person_key}\n      description: Manage subscribers in the mobile contact book.\n      operations:\n      - name: get-person\n        method: GET\n        description: Retrieve a subscriber by their internal\
  \ Vibes person key.\n        inputParameters:\n        - name: company_key\n          in: path\n          type: string\n          required: true\n          description: Your Vibes company identifier.\n        - name: person_key\n          in: path\n          type: string\n          required: true\n          description: The internal Vibes person key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /companies/{company_key}/events\n      description: Submit events that trigger messages.\n      operations:\n      - name: create-event\n        method: POST\n        description: Submit an event to trigger SMS messages and push notifications.\n        inputParameters:\n        - name: company_key\n          in: path\n          type: string\n          required: true\n          description: Your Vibes company identifier.\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            event_type: '{{tools.event_type}}'\n            person_key: '{{tools.person_key}}'\n            attributes: '{{tools.attributes}}'\n    - name: wallet-items\n      path: /companies/{company_key}/wallet_items\n      description: Manage mobile wallet passes.\n      operations:\n      - name: list-wallet-items\n        method: GET\n        description: Retrieve all wallet passes for the company.\n        inputParameters:\n        - name: company_key\n          in: path\n          type: string\n          required: true\n          description: Your Vibes company identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-wallet-item\n        method: POST\n        description: Create a new mobile wallet pass for a subscriber.\n        inputParameters:\n        -\
  \ name: company_key\n          in: path\n          type: string\n          required: true\n          description: Your Vibes company identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            person_key: '{{tools.person_key}}'\n            wallet_type: '{{tools.wallet_type}}'\n            template_id: '{{tools.template_id}}'\n            fields: '{{tools.fields}}'\n    - name: callbacks\n      path: /companies/{company_key}/callbacks\n      description: Manage callback endpoint registrations.\n      operations:\n      - name: list-callbacks\n        method: GET\n        description: Retrieve all registered callback endpoints.\n        inputParameters:\n        - name: company_key\n          in: path\n          type: string\n          required: true\n          description: Your Vibes company identifier.\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: register-callback\n        method: POST\n        description: Register a new callback endpoint for opt-in or delivery status notifications.\n        inputParameters:\n        - name: company_key\n          in: path\n          type: string\n          required: true\n          description: Your Vibes company identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            callback_type: '{{tools.callback_type}}'\n            url: '{{tools.url}}'\n  - type: http\n    namespace: vibes-connect\n    baseUri: https://messageapi.vibesapps.com\n    description: Vibes Connect aggregation API for SMS/MMS sending and carrier lookup.\n    authentication:\n      type: basic\n      username: '{{VIBES_CONNECT_USERNAME}}'\n      password: '{{VIBES_CONNECT_PASSWORD}}'\n\
  \    resources:\n    - name: sms-messages\n      path: /api/v1/sms/messages\n      description: Send SMS messages.\n      operations:\n      - name: send-sms-message\n        method: POST\n        description: Send an SMS message to a mobile number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            to: '{{tools.to}}'\n            from: '{{tools.from}}'\n            text: '{{tools.text}}'\n            callback_url: '{{tools.callback_url}}'\n    - name: mms-messages\n      path: /api/v1/mms/messages\n      description: Send MMS messages with multimedia content.\n      operations:\n      - name: send-mms-message\n        method: POST\n        description: Send an MMS message with pictures, links, or other media.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data:\n            to: '{{tools.to}}'\n            from: '{{tools.from}}'\n            subject: '{{tools.subject}}'\n            content: '{{tools.content}}'\n    - name: carrier-lookup\n      path: /api/v1/carrier-lookup\n      description: Retrieve carrier information for mobile numbers.\n      operations:\n      - name: lookup-carrier\n        method: POST\n        description: Retrieve carrier information and number type for a mobile number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            mobile_number: '{{tools.mobile_number}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vibes-mobile-messaging-api\n    description: Unified REST API for Vibes mobile messaging and engagement workflows.\n    resources:\n    - path: /v1/broadcasts\n      name: broadcasts\n      description: Manage SMS and push\
  \ notification broadcasts.\n      operations:\n      - method: GET\n        name: list-broadcasts\n        description: List all broadcasts for the company.\n        call: vibes-platform.list-broadcasts\n        with:\n          company_key: rest.company_key\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-broadcast\n        description: Create a new broadcast message send.\n        call: vibes-platform.create-broadcast\n        with:\n          company_key: rest.company_key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/broadcasts/{broadcast_id}\n      name: broadcast-detail\n      description: Retrieve a specific broadcast.\n      operations:\n      - method: GET\n        name: get-broadcast\n        description: Get broadcast details and status.\n        call: vibes-platform.get-broadcast\n        with:\n          company_key: rest.company_key\n          broadcast_id: rest.broadcast_id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/acquisition-campaigns\n      name: acquisition-campaigns\n      description: Manage subscriber acquisition campaigns.\n      operations:\n      - method: GET\n        name: list-acquisition-campaigns\n        description: List all acquisition campaigns.\n        call: vibes-platform.list-acquisition-campaigns\n        with:\n          company_key: rest.company_key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/acquisition-campaigns/{campaign_id}/participants\n      name: campaign-participants\n      description: Manage campaign participants.\n      operations:\n      - method: GET\n        name: list-pending-participants\n        description: List pending participants in a campaign.\n        call: vibes-platform.list-pending-participants\n        with:\n          company_key: rest.company_key\n          campaign_id: rest.campaign_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: add-participant\n        description: Add a person to an acquisition campaign.\n        call: vibes-platform.add-participant\n        with:\n          company_key: rest.company_key\n          campaign_id: rest.campaign_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscription-lists\n      name: subscription-lists\n      description: Manage subscriber subscription lists.\n      operations:\n      - method: GET\n        name: list-subscription-lists\n        description: List all subscription lists.\n        call: vibes-platform.list-subscription-lists\n        with:\n          company_key: rest.company_key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscribers/{person_key}\n      name: subscribers\n      description: Manage individual subscribers.\n      operations:\n      - method: GET\n        name: get-person\n\
  \        description: Get subscriber details by person key.\n        call: vibes-platform.get-person\n        with:\n          company_key: rest.company_key\n          person_key: rest.person_key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Submit events to trigger messages.\n      operations:\n      - method: POST\n        name: create-event\n        description: Submit an event to trigger SMS or push notifications.\n        call: vibes-platform.create-event\n        with:\n          company_key: rest.company_key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/wallet-passes\n      name: wallet-passes\n      description: Manage mobile wallet passes.\n      operations:\n      - method: GET\n        name: list-wallet-items\n        description: List all wallet passes.\n        call: vibes-platform.list-wallet-items\n        with:\n          company_key:\
  \ rest.company_key\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-wallet-item\n        description: Create a new wallet pass for a subscriber.\n        call: vibes-platform.create-wallet-item\n        with:\n          company_key: rest.company_key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/callbacks\n      name: callbacks\n      description: Manage opt-in and delivery status callbacks.\n      operations:\n      - method: GET\n        name: list-callbacks\n        description: List all registered callbacks.\n        call: vibes-platform.list-callbacks\n        with:\n          company_key: rest.company_key\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: register-callback\n        description: Register a new callback endpoint.\n        call: vibes-platform.register-callback\n        with:\n          company_key:\
  \ rest.company_key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sms-messages\n      name: sms-messages\n      description: Send transactional SMS messages.\n      operations:\n      - method: POST\n        name: send-sms-message\n        description: Send an SMS message via the Connect aggregation API.\n        call: vibes-connect.send-sms-message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/mms-messages\n      name: mms-messages\n      description: Send MMS messages with multimedia content.\n      operations:\n      - method: POST\n        name: send-mms-message\n        description: Send an MMS message with pictures, links, or other media.\n        call: vibes-connect.send-mms-message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/carrier-lookup\n      name: carrier-lookup\n      description: Look up carrier information for mobile numbers.\n      operations:\n\
  \      - method: POST\n        name: lookup-carrier\n        description: Retrieve carrier information for a mobile number.\n        call: vibes-connect.lookup-carrier\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vibes-mobile-messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted mobile messaging and engagement campaign management.\n    tools:\n    - name: list-broadcasts\n      description: List all SMS and push notification broadcasts for the company.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vibes-platform.list-broadcasts\n      with:\n        company_key: tools.company_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-broadcast\n      description: Create a new SMS or push notification broadcast message send.\n      hints:\n        readOnly: false\n        destructive: false\n      call: vibes-platform.create-broadcast\n\
  \      with:\n        company_key: tools.company_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-broadcast\n      description: Get details and delivery status for a specific broadcast.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vibes-platform.get-broadcast\n      with:\n        company_key: tools.company_key\n        broadcast_id: tools.broadcast_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-acquisition-campaigns\n      description: List all subscriber acquisition campaigns and their status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vibes-platform.list-acquisition-campaigns\n      with:\n        company_key: tools.company_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pending-participants\n      description: List pending participants in an acquisition campaign.\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: vibes-platform.list-pending-participants\n      with:\n        company_key: tools.company_key\n        campaign_id: tools.campaign_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-participant\n      description: Add a person to an acquisition campaign.\n      hints:\n        readOnly: false\n        destructive: false\n      call: vibes-platform.add-participant\n      with:\n        company_key: tools.company_key\n        campaign_id: tools.campaign_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-subscription-lists\n      description: List all subscriber subscription lists and their counts.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vibes-platform.list-subscription-lists\n      with:\n        company_key: tools.company_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-subscriber\n      description:\
  \ Get subscriber details and subscription status by person key.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vibes-platform.get-person\n      with:\n        company_key: tools.company_key\n        person_key: tools.person_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-event\n      description: Submit an event to trigger event-based SMS messages or push notifications.\n      hints:\n        readOnly: false\n        destructive: false\n      call: vibes-platform.create-event\n      with:\n        company_key: tools.company_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-wallet-passes\n      description: List all mobile wallet passes (Apple Wallet and Google Pay) for the company.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vibes-platform.list-wallet-items\n      with:\n        company_key: tools.company_key\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: create-wallet-pass\n      description: Create a new mobile wallet pass for a subscriber.\n      hints:\n        readOnly: false\n        destructive: false\n      call: vibes-platform.create-wallet-item\n      with:\n        company_key: tools.company_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-callbacks\n      description: List all registered callback endpoints for opt-in and delivery notifications.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vibes-platform.list-callbacks\n      with:\n        company_key: tools.company_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-callback\n      description: Register a callback endpoint for opt-in or delivery status notifications.\n      hints:\n        readOnly: false\n        destructive: false\n      call: vibes-platform.register-callback\n      with:\n        company_key: tools.company_key\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-sms-message\n      description: Send a transactional SMS message directly via the Vibes Connect aggregation API.\n      hints:\n        readOnly: false\n        destructive: false\n      call: vibes-connect.send-sms-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-mms-message\n      description: Send an MMS message with pictures, links, or other multimedia content.\n      hints:\n        readOnly: false\n        destructive: false\n      call: vibes-connect.send-mms-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-carrier\n      description: Look up the carrier and number type for a mobile number.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vibes-connect.lookup-carrier\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vibes-platform/refs/heads/main/capabilities/mobile-messaging.yaml
tags:
- Mobile Marketing
- SMS
- MMS
- Push Notifications
- Broadcast Messaging
- Acquisition Campaigns
- Subscription Management
- Mobile Engagement
tools:
- description: List all SMS and push notification broadcasts for the company.
  hints:
    openWorld: true
    readOnly: true
  name: list-broadcasts
- description: Create a new SMS or push notification broadcast message send.
  hints:
    destructive: false
    readOnly: false
  name: create-broadcast
- description: Get details and delivery status for a specific broadcast.
  hints:
    openWorld: true
    readOnly: true
  name: get-broadcast
- description: List all subscriber acquisition campaigns and their status.
  hints:
    openWorld: true
    readOnly: true
  name: list-acquisition-campaigns
- description: List pending participants in an acquisition campaign.
  hints:
    openWorld: true
    readOnly: true
  name: list-pending-participants
- description: Add a person to an acquisition campaign.
  hints:
    destructive: false
    readOnly: false
  name: add-participant
- description: List all subscriber subscription lists and their counts.
  hints:
    openWorld: true
    readOnly: true
  name: list-subscription-lists
- description: Get subscriber details and subscription status by person key.
  hints:
    openWorld: true
    readOnly: true
  name: get-subscriber
- description: Submit an event to trigger event-based SMS messages or push notifications.
  hints:
    destructive: false
    readOnly: false
  name: create-event
- description: List all mobile wallet passes (Apple Wallet and Google Pay) for the company.
  hints:
    openWorld: true
    readOnly: true
  name: list-wallet-passes
- description: Create a new mobile wallet pass for a subscriber.
  hints:
    destructive: false
    readOnly: false
  name: create-wallet-pass
- description: List all registered callback endpoints for opt-in and delivery notifications.
  hints:
    openWorld: true
    readOnly: true
  name: list-callbacks
- description: Register a callback endpoint for opt-in or delivery status notifications.
  hints:
    destructive: false
    readOnly: false
  name: register-callback
- description: Send a transactional SMS message directly via the Vibes Connect aggregation API.
  hints:
    destructive: false
    readOnly: false
  name: send-sms-message
- description: Send an MMS message with pictures, links, or other multimedia content.
  hints:
    destructive: false
    readOnly: false
  name: send-mms-message
- description: Look up the carrier and number type for a mobile number.
  hints:
    openWorld: true
    readOnly: true
  name: lookup-carrier
---
