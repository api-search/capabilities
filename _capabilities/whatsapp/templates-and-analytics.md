---
categories:
- analytics
consumed_apis:
- whatsapp-business-mgmt
description: Unified workflow for managing message templates and analyzing conversation and template performance. Combines Business Management API template CRUD and analytics capabilities used by marketing teams, content managers, and business analysts.
layout: capability
name: WhatsApp Templates And Analytics
operations:
- description: Lists all message templates for a WABA.
  method: GET
  name: list-message-templates
  path: /v1/message-templates
- description: Creates a new message template.
  method: POST
  name: create-message-template
  path: /v1/message-templates
- description: Deletes a message template.
  method: DELETE
  name: delete-message-template
  path: /v1/message-templates
- description: Updates an existing message template.
  method: POST
  name: update-message-template
  path: /v1/message-templates/{message_template_id}
- description: Retrieves conversation analytics.
  method: GET
  name: get-conversation-analytics
  path: /v1/conversation-analytics
- description: Retrieves template analytics.
  method: GET
  name: get-template-analytics
  path: /v1/template-analytics
personas: []
provider_name: WhatsApp
provider_slug: whatsapp
search_terms:
- creates a new message template.
- get conversation analytics
- deletes a message template. deleting by name removes all language variants.
- update message template
- message template management.
- reporting
- list message templates
- individual message template management.
- delete message template
- retrieves conversation analytics.
- analytics
- message templates
- template performance analytics.
- marketing
- updates an existing message template.
- whatsapp
- lists all message templates for a whatsapp business account. supports filtering by name, language, status, and category.
- retrieves conversation analytics for a waba with configurable time range, granularity, and dimensional breakdown.
- lists all message templates for a waba.
- conversation analytics and reporting.
- creates a new message template. templates must be approved by meta before use.
- retrieves analytics for specific message templates including sent, delivered, read, clicked, and cost metrics.
- get template analytics
- create message template
- retrieves template analytics.
- updates an existing message template. only approved or paused templates can be edited. edits re-trigger the approval process.
- deletes a message template.
slug: templates-and-analytics
source_filename: templates-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WhatsApp Templates And Analytics\"\n  description: \"Unified workflow for managing message templates and analyzing conversation and template performance. Combines Business Management API template CRUD and analytics capabilities used by marketing teams, content managers, and business analysts.\"\n  tags:\n    - WhatsApp\n    - Message Templates\n    - Analytics\n    - Marketing\n    - Reporting\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WHATSAPP_ACCESS_TOKEN: WHATSAPP_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: whatsapp-business-mgmt\n      location: ./shared/business-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: whatsapp-templates-api\n      description: \"Unified REST API for WhatsApp message template management and analytics.\"\n      resources:\n        - path: /v1/message-templates\n          name: message-templates\n\
  \          description: \"Message template management.\"\n          operations:\n            - method: GET\n              name: list-message-templates\n              description: \"Lists all message templates for a WABA.\"\n              call: \"whatsapp-business-mgmt.list-message-templates\"\n              with:\n                waba_id: \"rest.waba_id\"\n                fields: \"rest.fields\"\n                limit: \"rest.limit\"\n                after: \"rest.after\"\n                before: \"rest.before\"\n                name: \"rest.name\"\n                language: \"rest.language\"\n                status: \"rest.status\"\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-message-template\n              description: \"Creates a new message template.\"\n              call: \"whatsapp-business-mgmt.create-message-template\"\n   \
  \           with:\n                waba_id: \"rest.waba_id\"\n                name: \"rest.name\"\n                language: \"rest.language\"\n                category: \"rest.category\"\n                components: \"rest.components\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-message-template\n              description: \"Deletes a message template.\"\n              call: \"whatsapp-business-mgmt.delete-message-template\"\n              with:\n                waba_id: \"rest.waba_id\"\n                name: \"rest.name\"\n                hsm_id: \"rest.hsm_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/message-templates/{message_template_id}\n          name: message-template\n          description: \"Individual message template management.\"\n          operations:\n            - method: POST\n\
  \              name: update-message-template\n              description: \"Updates an existing message template.\"\n              call: \"whatsapp-business-mgmt.update-message-template\"\n              with:\n                message_template_id: \"rest.message_template_id\"\n                components: \"rest.components\"\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/conversation-analytics\n          name: conversation-analytics\n          description: \"Conversation analytics and reporting.\"\n          operations:\n            - method: GET\n              name: get-conversation-analytics\n              description: \"Retrieves conversation analytics.\"\n              call: \"whatsapp-business-mgmt.get-conversation-analytics\"\n              with:\n                waba_id: \"rest.waba_id\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n\
  \                granularity: \"rest.granularity\"\n                phone_numbers: \"rest.phone_numbers\"\n                metric_types: \"rest.metric_types\"\n                conversation_categories: \"rest.conversation_categories\"\n                dimensions: \"rest.dimensions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/template-analytics\n          name: template-analytics\n          description: \"Template performance analytics.\"\n          operations:\n            - method: GET\n              name: get-template-analytics\n              description: \"Retrieves template analytics.\"\n              call: \"whatsapp-business-mgmt.get-template-analytics\"\n              with:\n                waba_id: \"rest.waba_id\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n                granularity: \"rest.granularity\"\n                template_ids: \"rest.template_ids\"\n        \
  \        metric_types: \"rest.metric_types\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: whatsapp-templates-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WhatsApp template management and analytics.\"\n      tools:\n        - name: list-message-templates\n          description: \"Lists all message templates for a WhatsApp Business Account. Supports filtering by name, language, status, and category.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-business-mgmt.list-message-templates\"\n          with:\n            waba_id: \"tools.waba_id\"\n            fields: \"tools.fields\"\n            limit: \"tools.limit\"\n            after: \"tools.after\"\n            before: \"tools.before\"\n            name: \"tools.name\"\n            language: \"tools.language\"\n            status: \"tools.status\"\
  \n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-message-template\n          description: \"Creates a new message template. Templates must be approved by Meta before use.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"whatsapp-business-mgmt.create-message-template\"\n          with:\n            waba_id: \"tools.waba_id\"\n            name: \"tools.name\"\n            language: \"tools.language\"\n            category: \"tools.category\"\n            components: \"tools.components\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-message-template\n          description: \"Updates an existing message template. Only APPROVED or PAUSED templates can be edited. Edits re-trigger the approval process.\"\n          hints:\n            readOnly: false\n            idempotent:\
  \ true\n          call: \"whatsapp-business-mgmt.update-message-template\"\n          with:\n            message_template_id: \"tools.message_template_id\"\n            components: \"tools.components\"\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-message-template\n          description: \"Deletes a message template. Deleting by name removes all language variants.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"whatsapp-business-mgmt.delete-message-template\"\n          with:\n            waba_id: \"tools.waba_id\"\n            name: \"tools.name\"\n            hsm_id: \"tools.hsm_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-conversation-analytics\n          description: \"Retrieves conversation analytics for a WABA with configurable\
  \ time range, granularity, and dimensional breakdown.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-business-mgmt.get-conversation-analytics\"\n          with:\n            waba_id: \"tools.waba_id\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n            granularity: \"tools.granularity\"\n            phone_numbers: \"tools.phone_numbers\"\n            metric_types: \"tools.metric_types\"\n            conversation_categories: \"tools.conversation_categories\"\n            dimensions: \"tools.dimensions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-template-analytics\n          description: \"Retrieves analytics for specific message templates including sent, delivered, read, clicked, and cost metrics.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"whatsapp-business-mgmt.get-template-analytics\"\
  \n          with:\n            waba_id: \"tools.waba_id\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n            granularity: \"tools.granularity\"\n            template_ids: \"tools.template_ids\"\n            metric_types: \"tools.metric_types\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/whatsapp/refs/heads/main/capabilities/templates-and-analytics.yaml
tags:
- WhatsApp
- Message Templates
- Analytics
- Marketing
- Reporting
tools:
- description: Lists all message templates for a WhatsApp Business Account. Supports filtering by name, language, status, and category.
  hints:
    idempotent: true
    readOnly: true
  name: list-message-templates
- description: Creates a new message template. Templates must be approved by Meta before use.
  hints:
    destructive: false
    readOnly: false
  name: create-message-template
- description: Updates an existing message template. Only APPROVED or PAUSED templates can be edited. Edits re-trigger the approval process.
  hints:
    idempotent: true
    readOnly: false
  name: update-message-template
- description: Deletes a message template. Deleting by name removes all language variants.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-message-template
- description: Retrieves conversation analytics for a WABA with configurable time range, granularity, and dimensional breakdown.
  hints:
    idempotent: true
    readOnly: true
  name: get-conversation-analytics
- description: Retrieves analytics for specific message templates including sent, delivered, read, clicked, and cost metrics.
  hints:
    idempotent: true
    readOnly: true
  name: get-template-analytics
---
