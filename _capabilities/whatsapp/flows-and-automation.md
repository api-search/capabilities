---
categories:
- automation
consumed_apis:
- whatsapp-flows
- whatsapp-business-mgmt
description: Unified workflow for creating and managing interactive flows, publishing lifecycle management, and webhook subscriptions. Combines Flows API and Business Management API webhook capabilities used by developers building guided conversational experiences and automation integrations.
layout: capability
name: WhatsApp Flows And Automation
operations:
- description: Lists all flows for a WABA.
  method: GET
  name: list-flows
  path: /v1/flows
- description: Creates a new flow.
  method: POST
  name: create-flow
  path: /v1/flows
- description: Retrieves details about a flow.
  method: GET
  name: get-flow
  path: /v1/flows/{flow_id}
- description: Updates a draft flow.
  method: POST
  name: update-flow
  path: /v1/flows/{flow_id}
- description: Deletes a draft flow.
  method: DELETE
  name: delete-flow
  path: /v1/flows/{flow_id}
- description: Retrieves flow assets.
  method: GET
  name: get-flow-assets
  path: /v1/flows/{flow_id}/assets
- description: Uploads flow JSON definition.
  method: POST
  name: upload-flow-json
  path: /v1/flows/{flow_id}/assets
- description: Publishes a draft flow.
  method: POST
  name: publish-flow
  path: /v1/flows/{flow_id}/publish
- description: Deprecates a published flow.
  method: POST
  name: deprecate-flow
  path: /v1/flows/{flow_id}/deprecate
- description: Lists webhook subscriptions.
  method: GET
  name: list-subscribed-apps
  path: /v1/webhook-subscriptions
- description: Subscribes app to webhooks.
  method: POST
  name: subscribe-app
  path: /v1/webhook-subscriptions
- description: Unsubscribes app from webhooks.
  method: DELETE
  name: unsubscribe-app
  path: /v1/webhook-subscriptions
personas: []
provider_name: WhatsApp
provider_slug: whatsapp
search_terms:
- conversational design
- automation
- webhooks
- list subscribed apps
- creates a new interactive flow. supports appointment booking, surveys, lead capture, and other guided experiences.
- lists webhook subscriptions.
- retrieves the flow json assets including download urls.
- flows
- create flow
- unsubscribe app
- webhook subscription management.
- unsubscribes app from webhooks.
- flow json assets.
- get flow assets
- deprecates a published flow. deprecated flows remain in history but cannot be sent to customers.
- interactive experiences
- whatsapp
- publishes a draft flow, making it available for use in messages. requires valid flow json with no errors.
- flow management.
- lists all flows for a whatsapp business account.
- subscribes the current app to receive webhook events for a waba.
- publish flow
- publish a flow.
- lists all flows for a waba.
- deprecate a flow.
- get flow
- subscribes app to webhooks.
- deprecate flow
- updates a draft flow. only draft flows can be updated; published flows must be cloned.
- unsubscribes the current app from webhook events.
- retrieves details about a specific flow including status, categories, and validation errors.
- upload flow json
- deletes a draft flow.
- uploads flow json definition.
- retrieves details about a flow.
- update flow
- lists all apps subscribed to webhook events for a waba.
- delete flow
- retrieves flow assets.
- creates a new flow.
- subscribe app
- uploads or replaces the flow json definition file. the file is validated on upload.
- updates a draft flow.
- deprecates a published flow.
- list flows
- deletes a draft flow. only draft flows can be deleted; published flows must be deprecated.
- publishes a draft flow.
- individual flow management.
slug: flows-and-automation
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WhatsApp Flows And Automation\"\n  description: \"Unified workflow for creating and managing interactive flows, publishing lifecycle management, and webhook subscriptions. Combines Flows API and Business Management API webhook capabilities used by developers building guided conversational experiences and automation integrations.\"\n  tags:\n    - WhatsApp\n    - Flows\n    - Automation\n    - Webhooks\n    - Interactive Experiences\n    - Conversational Design\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WHATSAPP_ACCESS_TOKEN: WHATSAPP_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: whatsapp-flows\n      location: ./shared/flows.yaml\n    - import: whatsapp-business-mgmt\n      location: ./shared/business-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: whatsapp-flows-automation-api\n      description: \"Unified REST API for WhatsApp\
  \ flows, lifecycle management, and webhook subscriptions.\"\n      resources:\n        - path: /v1/flows\n          name: flows\n          description: \"Flow management.\"\n          operations:\n            - method: GET\n              name: list-flows\n              description: \"Lists all flows for a WABA.\"\n              call: \"whatsapp-flows.list-flows\"\n              with:\n                waba_id: \"rest.waba_id\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-flow\n              description: \"Creates a new flow.\"\n              call: \"whatsapp-flows.create-flow\"\n              with:\n                waba_id: \"rest.waba_id\"\n                name: \"rest.name\"\n                categories: \"rest.categories\"\n                clone_flow_id: \"rest.clone_flow_id\"\n                endpoint_uri: \"rest.endpoint_uri\"\n    \
  \          outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flows/{flow_id}\n          name: flow\n          description: \"Individual flow management.\"\n          operations:\n            - method: GET\n              name: get-flow\n              description: \"Retrieves details about a flow.\"\n              call: \"whatsapp-flows.get-flow\"\n              with:\n                flow_id: \"rest.flow_id\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: update-flow\n              description: \"Updates a draft flow.\"\n              call: \"whatsapp-flows.update-flow\"\n              with:\n                flow_id: \"rest.flow_id\"\n                name: \"rest.name\"\n                categories: \"rest.categories\"\n                endpoint_uri: \"rest.endpoint_uri\"\n                application_id:\
  \ \"rest.application_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-flow\n              description: \"Deletes a draft flow.\"\n              call: \"whatsapp-flows.delete-flow\"\n              with:\n                flow_id: \"rest.flow_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flows/{flow_id}/assets\n          name: flow-assets\n          description: \"Flow JSON assets.\"\n          operations:\n            - method: GET\n              name: get-flow-assets\n              description: \"Retrieves flow assets.\"\n              call: \"whatsapp-flows.get-flow-assets\"\n              with:\n                flow_id: \"rest.flow_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: upload-flow-json\n\
  \              description: \"Uploads flow JSON definition.\"\n              call: \"whatsapp-flows.upload-flow-json\"\n              with:\n                flow_id: \"rest.flow_id\"\n                file: \"rest.file\"\n                name: \"rest.name\"\n                asset_type: \"rest.asset_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flows/{flow_id}/publish\n          name: flow-publish\n          description: \"Publish a flow.\"\n          operations:\n            - method: POST\n              name: publish-flow\n              description: \"Publishes a draft flow.\"\n              call: \"whatsapp-flows.publish-flow\"\n              with:\n                flow_id: \"rest.flow_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flows/{flow_id}/deprecate\n          name: flow-deprecate\n          description: \"Deprecate\
  \ a flow.\"\n          operations:\n            - method: POST\n              name: deprecate-flow\n              description: \"Deprecates a published flow.\"\n              call: \"whatsapp-flows.deprecate-flow\"\n              with:\n                flow_id: \"rest.flow_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/webhook-subscriptions\n          name: webhook-subscriptions\n          description: \"Webhook subscription management.\"\n          operations:\n            - method: GET\n              name: list-subscribed-apps\n              description: \"Lists webhook subscriptions.\"\n              call: \"whatsapp-business-mgmt.list-subscribed-apps\"\n              with:\n                waba_id: \"rest.waba_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: subscribe-app\n              description:\
  \ \"Subscribes app to webhooks.\"\n              call: \"whatsapp-business-mgmt.subscribe-app\"\n              with:\n                waba_id: \"rest.waba_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: unsubscribe-app\n              description: \"Unsubscribes app from webhooks.\"\n              call: \"whatsapp-business-mgmt.unsubscribe-app\"\n              with:\n                waba_id: \"rest.waba_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: whatsapp-flows-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WhatsApp flow creation, lifecycle management, and webhook automation.\"\n      tools:\n        - name: list-flows\n          description: \"Lists all flows for a WhatsApp Business Account.\"\n          hints:\n            readOnly:\
  \ true\n            idempotent: true\n          call: \"whatsapp-flows.list-flows\"\n          with:\n            waba_id: \"tools.waba_id\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-flow\n          description: \"Creates a new interactive flow. Supports appointment booking, surveys, lead capture, and other guided experiences.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"whatsapp-flows.create-flow\"\n          with:\n            waba_id: \"tools.waba_id\"\n            name: \"tools.name\"\n            categories: \"tools.categories\"\n            clone_flow_id: \"tools.clone_flow_id\"\n            endpoint_uri: \"tools.endpoint_uri\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-flow\n          description: \"Retrieves details about a specific flow including status,\
  \ categories, and validation errors.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-flows.get-flow\"\n          with:\n            flow_id: \"tools.flow_id\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-flow\n          description: \"Updates a draft flow. Only DRAFT flows can be updated; published flows must be cloned.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"whatsapp-flows.update-flow\"\n          with:\n            flow_id: \"tools.flow_id\"\n            name: \"tools.name\"\n            categories: \"tools.categories\"\n            endpoint_uri: \"tools.endpoint_uri\"\n            application_id: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-flow\n          description: \"\
  Deletes a draft flow. Only DRAFT flows can be deleted; published flows must be deprecated.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"whatsapp-flows.delete-flow\"\n          with:\n            flow_id: \"tools.flow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-flow-assets\n          description: \"Retrieves the flow JSON assets including download URLs.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-flows.get-flow-assets\"\n          with:\n            flow_id: \"tools.flow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: upload-flow-json\n          description: \"Uploads or replaces the flow JSON definition file. The file is validated on upload.\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n          call: \"whatsapp-flows.upload-flow-json\"\n          with:\n            flow_id: \"tools.flow_id\"\n            file: \"tools.file\"\n            name: \"tools.name\"\n            asset_type: \"tools.asset_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: publish-flow\n          description: \"Publishes a draft flow, making it available for use in messages. Requires valid flow JSON with no errors.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"whatsapp-flows.publish-flow\"\n          with:\n            flow_id: \"tools.flow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: deprecate-flow\n          description: \"Deprecates a published flow. Deprecated flows remain in history but cannot be sent to customers.\"\n          hints:\n            readOnly: false\n            destructive: true\n  \
  \        call: \"whatsapp-flows.deprecate-flow\"\n          with:\n            flow_id: \"tools.flow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-subscribed-apps\n          description: \"Lists all apps subscribed to webhook events for a WABA.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-business-mgmt.list-subscribed-apps\"\n          with:\n            waba_id: \"tools.waba_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: subscribe-app\n          description: \"Subscribes the current app to receive webhook events for a WABA.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"whatsapp-business-mgmt.subscribe-app\"\n          with:\n            waba_id: \"tools.waba_id\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: unsubscribe-app\n          description: \"Unsubscribes the current app from webhook events.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"whatsapp-business-mgmt.unsubscribe-app\"\n          with:\n            waba_id: \"tools.waba_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/whatsapp/refs/heads/main/capabilities/flows-and-automation.yaml
tags:
- WhatsApp
- Flows
- Automation
- Webhooks
- Interactive Experiences
- Conversational Design
tools:
- description: Lists all flows for a WhatsApp Business Account.
  hints:
    idempotent: true
    readOnly: true
  name: list-flows
- description: Creates a new interactive flow. Supports appointment booking, surveys, lead capture, and other guided experiences.
  hints:
    destructive: false
    readOnly: false
  name: create-flow
- description: Retrieves details about a specific flow including status, categories, and validation errors.
  hints:
    idempotent: true
    readOnly: true
  name: get-flow
- description: Updates a draft flow. Only DRAFT flows can be updated; published flows must be cloned.
  hints:
    idempotent: true
    readOnly: false
  name: update-flow
- description: Deletes a draft flow. Only DRAFT flows can be deleted; published flows must be deprecated.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-flow
- description: Retrieves the flow JSON assets including download URLs.
  hints:
    idempotent: true
    readOnly: true
  name: get-flow-assets
- description: Uploads or replaces the flow JSON definition file. The file is validated on upload.
  hints:
    destructive: false
    readOnly: false
  name: upload-flow-json
- description: Publishes a draft flow, making it available for use in messages. Requires valid flow JSON with no errors.
  hints:
    destructive: false
    readOnly: false
  name: publish-flow
- description: Deprecates a published flow. Deprecated flows remain in history but cannot be sent to customers.
  hints:
    destructive: true
    readOnly: false
  name: deprecate-flow
- description: Lists all apps subscribed to webhook events for a WABA.
  hints:
    idempotent: true
    readOnly: true
  name: list-subscribed-apps
- description: Subscribes the current app to receive webhook events for a WABA.
  hints:
    destructive: false
    readOnly: false
  name: subscribe-app
- description: Unsubscribes the current app from webhook events.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: unsubscribe-app
---
