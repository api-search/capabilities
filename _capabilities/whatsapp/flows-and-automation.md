---
categories:
- automation
consumed_apis: []
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
- webhooks
- list flows
- deprecate flow
- creates a new flow.
- lists all flows for a waba.
- flow management.
- uploads or replaces the flow json definition file. the file is validated on upload.
- subscribe app
- retrieves the flow json assets including download urls.
- deletes a draft flow.
- unsubscribes app from webhooks.
- publish flow
- uploads flow json definition.
- updates a draft flow.
- lists all apps subscribed to webhook events for a waba.
- deletes a draft flow. only draft flows can be deleted; published flows must be deprecated.
- webhook subscription management.
- conversational design
- lists webhook subscriptions.
- automation
- get flow assets
- flows
- deprecates a published flow. deprecated flows remain in history but cannot be sent to customers.
- publish a flow.
- whatsapp
- get flow
- unsubscribe app
- updates a draft flow. only draft flows can be updated; published flows must be cloned.
- deprecate a flow.
- retrieves flow assets.
- delete flow
- creates a new interactive flow. supports appointment booking, surveys, lead capture, and other guided experiences.
- subscribes app to webhooks.
- retrieves details about a specific flow including status, categories, and validation errors.
- publishes a draft flow, making it available for use in messages. requires valid flow json with no errors.
- list subscribed apps
- lists all flows for a whatsapp business account.
- create flow
- publishes a draft flow.
- update flow
- flow json assets.
- retrieves details about a flow.
- interactive experiences
- deprecates a published flow.
- upload flow json
- subscribes the current app to receive webhook events for a waba.
- unsubscribes the current app from webhook events.
- individual flow management.
slug: flows-and-automation
source_filename: flows-and-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WhatsApp Flows And Automation\n  description: Unified workflow for creating and managing interactive flows, publishing lifecycle management, and webhook\n    subscriptions. Combines Flows API and Business Management API webhook capabilities used by developers building guided\n    conversational experiences and automation integrations.\n  tags:\n  - WhatsApp\n  - Flows\n  - Automation\n  - Webhooks\n  - Interactive Experiences\n  - Conversational Design\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WHATSAPP_ACCESS_TOKEN: WHATSAPP_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: whatsapp-flows\n    baseUri: https://graph.facebook.com/v21.0\n    description: WhatsApp Flows API for creating, managing, publishing, and deprecating interactive flows.\n    authentication:\n      type: bearer\n      token: '{{WHATSAPP_ACCESS_TOKEN}}'\n    resources:\n    - name: flows\n      path:\
  \ /\n      description: Create, read, update, and delete flows.\n      operations:\n      - name: list-flows\n        method: GET\n        path: /{waba_id}/flows\n        description: Lists all flows for a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-flow\n        method: POST\n        path: /{waba_id}/flows\n        description: Creates a new flow for a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business\
  \ Account ID\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            categories: '{{tools.categories}}'\n            clone_flow_id: '{{tools.clone_flow_id}}'\n            endpoint_uri: '{{tools.endpoint_uri}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-flow\n        method: GET\n        path: /{flow_id}\n        description: Retrieves details about a specific flow.\n        inputParameters:\n        - name: flow_id\n          in: path\n          type: string\n          required: true\n          description: Flow ID\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-flow\n        method: POST\n\
  \        path: /{flow_id}\n        description: Updates a flow. Only DRAFT flows can be updated.\n        inputParameters:\n        - name: flow_id\n          in: path\n          type: string\n          required: true\n          description: Flow ID\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            categories: '{{tools.categories}}'\n            endpoint_uri: '{{tools.endpoint_uri}}'\n            application_id: '{{tools.application_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-flow\n        method: DELETE\n        path: /{flow_id}\n        description: Deletes a flow. Only DRAFT flows can be deleted.\n        inputParameters:\n        - name: flow_id\n          in: path\n          type: string\n          required: true\n          description: Flow ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: assets\n      path: /\n      description: Upload and retrieve flow JSON assets.\n      operations:\n      - name: get-flow-assets\n        method: GET\n        path: /{flow_id}/assets\n        description: Retrieves the assets (flow JSON file) for a flow.\n        inputParameters:\n        - name: flow_id\n          in: path\n          type: string\n          required: true\n          description: Flow ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upload-flow-json\n        method: POST\n        path: /{flow_id}/assets\n        description: Uploads or replaces the flow JSON definition file.\n        inputParameters:\n        - name: flow_id\n          in: path\n          type: string\n          required: true\n          description: Flow ID\n        body:\n          type: json\n          data:\n            file: '{{tools.file}}'\n \
  \           name: '{{tools.name}}'\n            asset_type: '{{tools.asset_type}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lifecycle\n      path: /\n      description: Publish and deprecate flows.\n      operations:\n      - name: publish-flow\n        method: POST\n        path: /{flow_id}/publish\n        description: Publishes a draft flow, making it available for use in messages.\n        inputParameters:\n        - name: flow_id\n          in: path\n          type: string\n          required: true\n          description: Flow ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deprecate-flow\n        method: POST\n        path: /{flow_id}/deprecate\n        description: Deprecates a published flow. Deprecated flows cannot be sent to customers.\n        inputParameters:\n        - name: flow_id\n\
  \          in: path\n          type: string\n          required: true\n          description: Flow ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: whatsapp-business-mgmt\n    baseUri: https://graph.facebook.com/v21.0\n    description: WhatsApp Business Management API for managing WABAs, phone numbers, templates, analytics, users, catalogs,\n      and webhooks.\n    authentication:\n      type: bearer\n      token: '{{WHATSAPP_ACCESS_TOKEN}}'\n    resources:\n    - name: business-accounts\n      path: /\n      description: Manage WhatsApp Business Account information.\n      operations:\n      - name: get-whatsapp-business-account\n        method: GET\n        path: /{waba_id}\n        description: Retrieves information about a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n\
  \          description: WhatsApp Business Account ID\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: phone-numbers\n      path: /\n      description: List and manage phone numbers on a WABA.\n      operations:\n      - name: list-phone-numbers\n        method: GET\n        path: /{waba_id}/phone_numbers\n        description: Lists all phone numbers associated with a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated fields to return\n        - name: limit\n\
  \          in: query\n          type: integer\n          required: false\n          description: Pagination limit\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor for forward pagination\n        - name: before\n          in: query\n          type: string\n          required: false\n          description: Cursor for backward pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: message-templates\n      path: /\n      description: Create, update, and delete message templates.\n      operations:\n      - name: list-message-templates\n        method: GET\n        path: /{waba_id}/message_templates\n        description: Lists all message templates for a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ WhatsApp Business Account ID\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated fields to return\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Pagination limit\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor for forward pagination\n        - name: before\n          in: query\n          type: string\n          required: false\n          description: Cursor for backward pagination\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter by template name\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Filter by language code\n        - name: status\n          in: query\n          type: string\n          required: false\n\
  \          description: Filter by approval status (APPROVED, PENDING, REJECTED, PAUSED, DISABLED)\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by template category (AUTHENTICATION, MARKETING, UTILITY)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-message-template\n        method: POST\n        path: /{waba_id}/message_templates\n        description: Creates a new message template for a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            language: '{{tools.language}}'\n            category: '{{tools.category}}'\n            components: '{{tools.components}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-message-template\n        method: POST\n        path: /{message_template_id}\n        description: Updates an existing message template. Only APPROVED or PAUSED templates can be edited.\n        inputParameters:\n        - name: message_template_id\n          in: path\n          type: string\n          required: true\n          description: Message template ID\n        body:\n          type: json\n          data:\n            components: '{{tools.components}}'\n            category: '{{tools.category}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-message-template\n        method: DELETE\n        path: /{waba_id}/message_templates\n        description: Deletes a message template. Deleting by name removes all language variants.\n        inputParameters:\n\
  \        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Template name to delete\n        - name: hsm_id\n          in: query\n          type: string\n          required: false\n          description: Specific template ID to delete a single language variant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics\n      path: /\n      description: Retrieve conversation and template analytics.\n      operations:\n      - name: get-conversation-analytics\n        method: GET\n        path: /{waba_id}/conversation_analytics\n        description: Retrieves conversation analytics for a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type:\
  \ string\n          required: true\n          description: WhatsApp Business Account ID\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start time (Unix timestamp or YYYY-MM-DD)\n        - name: end\n          in: query\n          type: string\n          required: true\n          description: End time (Unix timestamp or YYYY-MM-DD)\n        - name: granularity\n          in: query\n          type: string\n          required: true\n          description: Time granularity (HALF_HOUR, DAILY, MONTHLY)\n        - name: phone_numbers\n          in: query\n          type: array\n          required: false\n          description: Filter by phone number IDs\n        - name: metric_types\n          in: query\n          type: array\n          required: false\n          description: Metric types (CONVERSATION, COST)\n        - name: conversation_categories\n          in: query\n          type: array\n          required: false\n \
  \         description: Conversation categories filter\n        - name: dimensions\n          in: query\n          type: array\n          required: false\n          description: Dimensions for breakdown\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-template-analytics\n        method: GET\n        path: /{waba_id}/template_analytics\n        description: Retrieves analytics for specific message templates.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start time\n        - name: end\n          in: query\n          type: string\n          required: true\n          description: End time\n        - name: granularity\n          in: query\n          type:\
  \ string\n          required: true\n          description: Time granularity (DAILY)\n        - name: template_ids\n          in: query\n          type: array\n          required: true\n          description: Template IDs to analyze (max 10)\n        - name: metric_types\n          in: query\n          type: array\n          required: false\n          description: Metric types (SENT, DELIVERED, READ, CLICKED, COST)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscribed-apps\n      path: /\n      description: Manage webhook subscriptions for a WABA.\n      operations:\n      - name: list-subscribed-apps\n        method: GET\n        path: /{waba_id}/subscribed_apps\n        description: Lists all apps subscribed to webhook events for this WABA.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp\
  \ Business Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: subscribe-app\n        method: POST\n        path: /{waba_id}/subscribed_apps\n        description: Subscribes the current app to receive webhook events for this WABA.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unsubscribe-app\n        method: DELETE\n        path: /{waba_id}/subscribed_apps\n        description: Unsubscribes the current app from webhook events.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assigned-users\n      path: /\n      description: Manage user access to a WABA.\n      operations:\n      - name: list-assigned-users\n        method: GET\n        path: /{waba_id}/assigned_users\n        description: Lists all users assigned to a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: assign-user\n        method: POST\n        path: /{waba_id}/assigned_users\n        description: Assigns a user with specific tasks to a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n      \
  \    description: WhatsApp Business Account ID\n        body:\n          type: json\n          data:\n            user: '{{tools.user}}'\n            tasks: '{{tools.tasks}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-assigned-user\n        method: DELETE\n        path: /{waba_id}/assigned_users\n        description: Removes a user from a WhatsApp Business Account.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        body:\n          type: json\n          data:\n            user: '{{tools.user}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: product-catalogs\n      path: /\n      description: Connect and manage product catalogs.\n      operations:\n      - name:\
  \ list-product-catalogs\n        method: GET\n        path: /{waba_id}/product_catalogs\n        description: Lists product catalogs connected to a WABA.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: connect-product-catalog\n        method: POST\n        path: /{waba_id}/product_catalogs\n        description: Connects a product catalog to a WABA.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        body:\n          type: json\n          data:\n            catalog_id: '{{tools.catalog_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: disconnect-product-catalog\n        method: DELETE\n        path: /{waba_id}/product_catalogs\n        description: Disconnects a product catalog from a WABA.\n        inputParameters:\n        - name: waba_id\n          in: path\n          type: string\n          required: true\n          description: WhatsApp Business Account ID\n        body:\n          type: json\n          data:\n            catalog_id: '{{tools.catalog_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: whatsapp-flows-automation-api\n    description: Unified REST API for WhatsApp flows, lifecycle management, and webhook subscriptions.\n    resources:\n    - path: /v1/flows\n      name: flows\n      description: Flow management.\n      operations:\n      - method: GET\n        name: list-flows\n        description: Lists all flows for a WABA.\n\
  \        call: whatsapp-flows.list-flows\n        with:\n          waba_id: rest.waba_id\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-flow\n        description: Creates a new flow.\n        call: whatsapp-flows.create-flow\n        with:\n          waba_id: rest.waba_id\n          name: rest.name\n          categories: rest.categories\n          clone_flow_id: rest.clone_flow_id\n          endpoint_uri: rest.endpoint_uri\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flows/{flow_id}\n      name: flow\n      description: Individual flow management.\n      operations:\n      - method: GET\n        name: get-flow\n        description: Retrieves details about a flow.\n        call: whatsapp-flows.get-flow\n        with:\n          flow_id: rest.flow_id\n          fields: rest.fields\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n      - method: POST\n        name: update-flow\n        description: Updates a draft flow.\n        call: whatsapp-flows.update-flow\n        with:\n          flow_id: rest.flow_id\n          name: rest.name\n          categories: rest.categories\n          endpoint_uri: rest.endpoint_uri\n          application_id: rest.application_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-flow\n        description: Deletes a draft flow.\n        call: whatsapp-flows.delete-flow\n        with:\n          flow_id: rest.flow_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flows/{flow_id}/assets\n      name: flow-assets\n      description: Flow JSON assets.\n      operations:\n      - method: GET\n        name: get-flow-assets\n        description: Retrieves flow assets.\n        call: whatsapp-flows.get-flow-assets\n        with:\n          flow_id: rest.flow_id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: upload-flow-json\n        description: Uploads flow JSON definition.\n        call: whatsapp-flows.upload-flow-json\n        with:\n          flow_id: rest.flow_id\n          file: rest.file\n          name: rest.name\n          asset_type: rest.asset_type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flows/{flow_id}/publish\n      name: flow-publish\n      description: Publish a flow.\n      operations:\n      - method: POST\n        name: publish-flow\n        description: Publishes a draft flow.\n        call: whatsapp-flows.publish-flow\n        with:\n          flow_id: rest.flow_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flows/{flow_id}/deprecate\n      name: flow-deprecate\n      description: Deprecate a flow.\n      operations:\n      - method: POST\n        name: deprecate-flow\n\
  \        description: Deprecates a published flow.\n        call: whatsapp-flows.deprecate-flow\n        with:\n          flow_id: rest.flow_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhook-subscriptions\n      name: webhook-subscriptions\n      description: Webhook subscription management.\n      operations:\n      - method: GET\n        name: list-subscribed-apps\n        description: Lists webhook subscriptions.\n        call: whatsapp-business-mgmt.list-subscribed-apps\n        with:\n          waba_id: rest.waba_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: subscribe-app\n        description: Subscribes app to webhooks.\n        call: whatsapp-business-mgmt.subscribe-app\n        with:\n          waba_id: rest.waba_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: unsubscribe-app\n        description:\
  \ Unsubscribes app from webhooks.\n        call: whatsapp-business-mgmt.unsubscribe-app\n        with:\n          waba_id: rest.waba_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: whatsapp-flows-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted WhatsApp flow creation, lifecycle management, and webhook automation.\n    tools:\n    - name: list-flows\n      description: Lists all flows for a WhatsApp Business Account.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: whatsapp-flows.list-flows\n      with:\n        waba_id: tools.waba_id\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-flow\n      description: Creates a new interactive flow. Supports appointment booking, surveys, lead capture, and other guided experiences.\n      hints:\n        readOnly: false\n        destructive: false\n\
  \      call: whatsapp-flows.create-flow\n      with:\n        waba_id: tools.waba_id\n        name: tools.name\n        categories: tools.categories\n        clone_flow_id: tools.clone_flow_id\n        endpoint_uri: tools.endpoint_uri\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-flow\n      description: Retrieves details about a specific flow including status, categories, and validation errors.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: whatsapp-flows.get-flow\n      with:\n        flow_id: tools.flow_id\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-flow\n      description: Updates a draft flow. Only DRAFT flows can be updated; published flows must be cloned.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: whatsapp-flows.update-flow\n      with:\n        flow_id: tools.flow_id\n        name: tools.name\n        categories:\
  \ tools.categories\n        endpoint_uri: tools.endpoint_uri\n        application_id: tools.application_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-flow\n      description: Deletes a draft flow. Only DRAFT flows can be deleted; published flows must be deprecated.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: whatsapp-flows.delete-flow\n      with:\n        flow_id: tools.flow_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-flow-assets\n      description: Retrieves the flow JSON assets including download URLs.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: whatsapp-flows.get-flow-assets\n      with:\n        flow_id: tools.flow_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upload-flow-json\n      description: Uploads or replaces the flow JSON definition file. The file is validated\
  \ on upload.\n      hints:\n        readOnly: false\n        destructive: false\n      call: whatsapp-flows.upload-flow-json\n      with:\n        flow_id: tools.flow_id\n        file: tools.file\n        name: tools.name\n        asset_type: tools.asset_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-flow\n      description: Publishes a draft flow, making it available for use in messages. Requires valid flow JSON with no errors.\n      hints:\n        readOnly: false\n        destructive: false\n      call: whatsapp-flows.publish-flow\n      with:\n        flow_id: tools.flow_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deprecate-flow\n      description: Deprecates a published flow. Deprecated flows remain in history but cannot be sent to customers.\n      hints:\n        readOnly: false\n        destructive: true\n      call: whatsapp-flows.deprecate-flow\n      with:\n        flow_id: tools.flow_id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-subscribed-apps\n      description: Lists all apps subscribed to webhook events for a WABA.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: whatsapp-business-mgmt.list-subscribed-apps\n      with:\n        waba_id: tools.waba_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: subscribe-app\n      description: Subscribes the current app to receive webhook events for a WABA.\n      hints:\n        readOnly: false\n        destructive: false\n      call: whatsapp-business-mgmt.subscribe-app\n      with:\n        waba_id: tools.waba_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unsubscribe-app\n      description: Unsubscribes the current app from webhook events.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: whatsapp-business-mgmt.unsubscribe-app\n \
  \     with:\n        waba_id: tools.waba_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
