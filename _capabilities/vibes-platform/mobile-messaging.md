---
api_specs:
- filename: vibes-platform-openapi.yml
  format: yaml
  label: vibes-platform
  slug: vibes-platform
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/vibes-platform/refs/heads/main/openapi/vibes-platform-openapi.yml
- filename: vibes-connect-openapi.yml
  format: yaml
  label: vibes-connect
  slug: vibes-connect
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/vibes-platform/refs/heads/main/openapi/vibes-connect-openapi.yml
categories: []
consumed_apis:
- vibes-platform
- vibes-connect
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
- mobile marketing
- send mms messages with multimedia content.
- manage campaign participants.
- submit an event to trigger sms or push notifications.
- mms
- list pending participants in a campaign.
- manage mobile wallet passes.
- list wallet passes
- push notifications
- create a new sms or push notification broadcast message send.
- get subscriber details by person key.
- list wallet items
- retrieve a specific broadcast.
- send a transactional sms message directly via the vibes connect aggregation api.
- manage opt-in and delivery status callbacks.
- create wallet pass
- mobile engagement
- manage individual subscribers.
- list acquisition campaigns
- rcs
- subscription management
- get subscriber details and subscription status by person key.
- get person
- look up carrier information for mobile numbers.
- register a new callback endpoint.
- send an sms message via the connect aggregation api.
- list all mobile wallet passes (apple wallet and google pay) for the company.
- list callbacks
- manage sms and push notification broadcasts.
- get broadcast
- sms
- send sms message
- get details and delivery status for a specific broadcast.
- list all subscriber acquisition campaigns and their status.
- list all registered callbacks.
- add a person to an acquisition campaign.
- lookup carrier
- retrieve carrier information for a mobile number.
- list pending participants in an acquisition campaign.
- list pending participants
- create event
- get subscriber
- send an mms message with pictures, links, or other multimedia content.
- submit an event to trigger event-based sms messages or push notifications.
- list all registered callback endpoints for opt-in and delivery notifications.
- list all broadcasts for the company.
- create broadcast
- create wallet item
- list broadcasts
- mobile messaging
- register callback
- send mms message
- create a new broadcast message send.
- list all wallet passes.
- broadcast messaging
- acquisition campaigns
- manage subscriber subscription lists.
- list all acquisition campaigns.
- list subscription lists
- send an mms message with pictures, links, or other media.
- register a callback endpoint for opt-in or delivery status notifications.
- list all sms and push notification broadcasts for the company.
- submit events to trigger messages.
- get broadcast details and status.
- create a new wallet pass for a subscriber.
- send transactional sms messages.
- wallet passes
- manage subscriber acquisition campaigns.
- look up the carrier and number type for a mobile number.
- list all subscriber subscription lists and their counts.
- list all subscription lists.
- add participant
- create a new mobile wallet pass for a subscriber.
slug: mobile-messaging
source_filename: mobile-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vibes Mobile Messaging\"\n  description: >-\n    Unified mobile messaging capability combining the Vibes Platform API and\n    Vibes Connect API for end-to-end mobile engagement workflows. Covers\n    SMS/MMS sending, broadcast campaign management, push notifications,\n    acquisition campaigns, subscription list management, and event-triggered\n    messages. Used by mobile marketing teams and developers building\n    customer engagement workflows.\n  tags:\n    - Mobile Marketing\n    - SMS\n    - MMS\n    - Push Notifications\n    - Broadcast Messaging\n    - Acquisition Campaigns\n    - Subscription Management\n    - Mobile Engagement\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VIBES_PLATFORM_USERNAME: VIBES_PLATFORM_USERNAME\n      VIBES_PLATFORM_PASSWORD: VIBES_PLATFORM_PASSWORD\n      VIBES_COMPANY_KEY: VIBES_COMPANY_KEY\n      VIBES_CONNECT_USERNAME: VIBES_CONNECT_USERNAME\n\
  \      VIBES_CONNECT_PASSWORD: VIBES_CONNECT_PASSWORD\n\ncapability:\n  consumes:\n    - import: vibes-platform\n      location: ./shared/vibes-platform.yaml\n    - import: vibes-connect\n      location: ./shared/vibes-connect.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vibes-mobile-messaging-api\n      description: \"Unified REST API for Vibes mobile messaging and engagement workflows.\"\n      resources:\n        - path: /v1/broadcasts\n          name: broadcasts\n          description: \"Manage SMS and push notification broadcasts.\"\n          operations:\n            - method: GET\n              name: list-broadcasts\n              description: \"List all broadcasts for the company.\"\n              call: \"vibes-platform.list-broadcasts\"\n              with:\n                company_key: \"rest.company_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name:\
  \ create-broadcast\n              description: \"Create a new broadcast message send.\"\n              call: \"vibes-platform.create-broadcast\"\n              with:\n                company_key: \"rest.company_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/broadcasts/{broadcast_id}\n          name: broadcast-detail\n          description: \"Retrieve a specific broadcast.\"\n          operations:\n            - method: GET\n              name: get-broadcast\n              description: \"Get broadcast details and status.\"\n              call: \"vibes-platform.get-broadcast\"\n              with:\n                company_key: \"rest.company_key\"\n                broadcast_id: \"rest.broadcast_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/acquisition-campaigns\n          name: acquisition-campaigns\n          description: \"\
  Manage subscriber acquisition campaigns.\"\n          operations:\n            - method: GET\n              name: list-acquisition-campaigns\n              description: \"List all acquisition campaigns.\"\n              call: \"vibes-platform.list-acquisition-campaigns\"\n              with:\n                company_key: \"rest.company_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/acquisition-campaigns/{campaign_id}/participants\n          name: campaign-participants\n          description: \"Manage campaign participants.\"\n          operations:\n            - method: GET\n              name: list-pending-participants\n              description: \"List pending participants in a campaign.\"\n              call: \"vibes-platform.list-pending-participants\"\n              with:\n                company_key: \"rest.company_key\"\n                campaign_id: \"rest.campaign_id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-participant\n              description: \"Add a person to an acquisition campaign.\"\n              call: \"vibes-platform.add-participant\"\n              with:\n                company_key: \"rest.company_key\"\n                campaign_id: \"rest.campaign_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/subscription-lists\n          name: subscription-lists\n          description: \"Manage subscriber subscription lists.\"\n          operations:\n            - method: GET\n              name: list-subscription-lists\n              description: \"List all subscription lists.\"\n              call: \"vibes-platform.list-subscription-lists\"\n              with:\n                company_key: \"rest.company_key\"\n              outputParameters:\n                - type: object\n             \
  \     mapping: \"$.\"\n\n        - path: /v1/subscribers/{person_key}\n          name: subscribers\n          description: \"Manage individual subscribers.\"\n          operations:\n            - method: GET\n              name: get-person\n              description: \"Get subscriber details by person key.\"\n              call: \"vibes-platform.get-person\"\n              with:\n                company_key: \"rest.company_key\"\n                person_key: \"rest.person_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events\n          name: events\n          description: \"Submit events to trigger messages.\"\n          operations:\n            - method: POST\n              name: create-event\n              description: \"Submit an event to trigger SMS or push notifications.\"\n              call: \"vibes-platform.create-event\"\n              with:\n                company_key: \"rest.company_key\"\n   \
  \           outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/wallet-passes\n          name: wallet-passes\n          description: \"Manage mobile wallet passes.\"\n          operations:\n            - method: GET\n              name: list-wallet-items\n              description: \"List all wallet passes.\"\n              call: \"vibes-platform.list-wallet-items\"\n              with:\n                company_key: \"rest.company_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-wallet-item\n              description: \"Create a new wallet pass for a subscriber.\"\n              call: \"vibes-platform.create-wallet-item\"\n              with:\n                company_key: \"rest.company_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/callbacks\n\
  \          name: callbacks\n          description: \"Manage opt-in and delivery status callbacks.\"\n          operations:\n            - method: GET\n              name: list-callbacks\n              description: \"List all registered callbacks.\"\n              call: \"vibes-platform.list-callbacks\"\n              with:\n                company_key: \"rest.company_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: register-callback\n              description: \"Register a new callback endpoint.\"\n              call: \"vibes-platform.register-callback\"\n              with:\n                company_key: \"rest.company_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sms-messages\n          name: sms-messages\n          description: \"Send transactional SMS messages.\"\n          operations:\n         \
  \   - method: POST\n              name: send-sms-message\n              description: \"Send an SMS message via the Connect aggregation API.\"\n              call: \"vibes-connect.send-sms-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/mms-messages\n          name: mms-messages\n          description: \"Send MMS messages with multimedia content.\"\n          operations:\n            - method: POST\n              name: send-mms-message\n              description: \"Send an MMS message with pictures, links, or other media.\"\n              call: \"vibes-connect.send-mms-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/carrier-lookup\n          name: carrier-lookup\n          description: \"Look up carrier information for mobile numbers.\"\n          operations:\n            - method: POST\n              name: lookup-carrier\n\
  \              description: \"Retrieve carrier information for a mobile number.\"\n              call: \"vibes-connect.lookup-carrier\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vibes-mobile-messaging-mcp\n      transport: http\n      description: \"MCP server for AI-assisted mobile messaging and engagement campaign management.\"\n      tools:\n        - name: list-broadcasts\n          description: \"List all SMS and push notification broadcasts for the company.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vibes-platform.list-broadcasts\"\n          with:\n            company_key: \"tools.company_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-broadcast\n          description: \"Create a new SMS or push notification broadcast message send.\"\n          hints:\n\
  \            readOnly: false\n            destructive: false\n          call: \"vibes-platform.create-broadcast\"\n          with:\n            company_key: \"tools.company_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-broadcast\n          description: \"Get details and delivery status for a specific broadcast.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vibes-platform.get-broadcast\"\n          with:\n            company_key: \"tools.company_key\"\n            broadcast_id: \"tools.broadcast_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-acquisition-campaigns\n          description: \"List all subscriber acquisition campaigns and their status.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vibes-platform.list-acquisition-campaigns\"\n          with:\n\
  \            company_key: \"tools.company_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pending-participants\n          description: \"List pending participants in an acquisition campaign.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vibes-platform.list-pending-participants\"\n          with:\n            company_key: \"tools.company_key\"\n            campaign_id: \"tools.campaign_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-participant\n          description: \"Add a person to an acquisition campaign.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"vibes-platform.add-participant\"\n          with:\n            company_key: \"tools.company_key\"\n            campaign_id: \"tools.campaign_id\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-subscription-lists\n          description: \"List all subscriber subscription lists and their counts.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vibes-platform.list-subscription-lists\"\n          with:\n            company_key: \"tools.company_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-subscriber\n          description: \"Get subscriber details and subscription status by person key.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vibes-platform.get-person\"\n          with:\n            company_key: \"tools.company_key\"\n            person_key: \"tools.person_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-event\n          description: \"Submit an event to trigger event-based SMS messages or push\
  \ notifications.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"vibes-platform.create-event\"\n          with:\n            company_key: \"tools.company_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-wallet-passes\n          description: \"List all mobile wallet passes (Apple Wallet and Google Pay) for the company.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vibes-platform.list-wallet-items\"\n          with:\n            company_key: \"tools.company_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-wallet-pass\n          description: \"Create a new mobile wallet pass for a subscriber.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"vibes-platform.create-wallet-item\"\n          with:\n          \
  \  company_key: \"tools.company_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-callbacks\n          description: \"List all registered callback endpoints for opt-in and delivery notifications.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vibes-platform.list-callbacks\"\n          with:\n            company_key: \"tools.company_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: register-callback\n          description: \"Register a callback endpoint for opt-in or delivery status notifications.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"vibes-platform.register-callback\"\n          with:\n            company_key: \"tools.company_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-sms-message\n\
  \          description: \"Send a transactional SMS message directly via the Vibes Connect aggregation API.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"vibes-connect.send-sms-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-mms-message\n          description: \"Send an MMS message with pictures, links, or other multimedia content.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"vibes-connect.send-mms-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-carrier\n          description: \"Look up the carrier and number type for a mobile number.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vibes-connect.lookup-carrier\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n"
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
