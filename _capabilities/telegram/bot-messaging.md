---
api_specs:
- filename: telegram-bot-openapi.yml
  format: yaml
  label: telegram-bot
  slug: telegram-bot
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/telegram/refs/heads/main/openapi/telegram-bot-openapi.yml
categories: []
consumed_apis:
- telegram-bot
description: Unified capability for Telegram bot messaging workflows. Covers sending messages, media, polls, and managing updates via webhooks or long polling. Designed for developers building notification systems, chatbots, and interactive experiences on Telegram.
layout: capability
name: Telegram Bot Messaging
operations:
- description: Get bot information and verify authentication
  method: GET
  name: get-bot-info
  path: /v1/bot
- description: Poll for incoming messages, callbacks, and other updates
  method: GET
  name: get-updates
  path: /v1/updates
- description: Get current webhook status and configuration
  method: GET
  name: get-webhook-info
  path: /v1/webhook
- description: Configure a webhook URL to receive real-time updates
  method: POST
  name: set-webhook
  path: /v1/webhook
- description: Remove the webhook integration and switch to long polling
  method: DELETE
  name: delete-webhook
  path: /v1/webhook
- description: Send a text message to a chat or user
  method: POST
  name: send-message
  path: /v1/messages
- description: Send a photo to a chat
  method: POST
  name: send-photo
  path: /v1/photos
- description: Send a document or file to a chat
  method: POST
  name: send-document
  path: /v1/documents
- description: Send a native poll to a chat
  method: POST
  name: send-poll
  path: /v1/polls
- description: Get information about a chat
  method: GET
  name: get-chat
  path: /v1/chats/{chat_id}
- description: List all administrators in a chat
  method: GET
  name: get-chat-administrators
  path: /v1/chats/{chat_id}/administrators
- description: Get the current bot command menu
  method: GET
  name: get-commands
  path: /v1/commands
- description: Update the bot command menu
  method: PUT
  name: set-commands
  path: /v1/commands
personas: []
provider_name: Telegram
provider_slug: telegram
search_terms:
- send documents and files to chats
- configure a webhook url to receive real-time updates
- get chat info
- bot command menu
- get updates
- get bot commands
- get basic information about the telegram bot including name, username, and capabilities
- send message
- get chat
- get the current list of commands in the bot's command menu
- get bot info
- set webhook
- get webhook info
- get the current webhook configuration and status including last error and pending update count
- get the current bot command menu
- create polls in chats
- bots
- get member count
- set bot commands
- send a native poll to a chat
- bot information and status
- poll for incoming messages, callbacks, and other updates
- get chat administrators
- webhooks
- send poll
- configure a webhook url so telegram pushes updates in real-time instead of requiring polling
- get information about a chat
- send text message
- payments
- send messages and media to chats
- set commands
- chat
- incoming updates from telegram users
- messaging
- send a text message to a telegram chat, group, or channel. supports markdown and html formatting.
- send a document or file to a telegram chat
- set the list of commands shown in the bot's command menu that users see when they type /
- remove the webhook integration and switch to long polling
- get the total number of members in a telegram chat
- send photos to chats
- webhook configuration for real-time updates
- get bot information and verify authentication
- list all administrators in a chat
- get detailed information about a chat including title, description, member count, and invite link
- chat administrator list
- get commands
- telegram
- create and send a native telegram poll to gather opinions from chat members
- send a photo to a telegram chat with an optional caption
- send a text message to a chat or user
- delete webhook
- send a document or file to a chat
- chat information and management
- update the bot command menu
- create poll
- list all administrators in a telegram chat with their admin permissions
- list chat admins
- get current webhook status and configuration
- poll telegram for new incoming messages, button clicks, and other updates via long polling
- send document
- notifications
- send a photo to a chat
- send photo
slug: bot-messaging
source_filename: bot-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Telegram Bot Messaging\"\n  description: >-\n    Unified capability for Telegram bot messaging workflows. Covers sending messages,\n    media, polls, and managing updates via webhooks or long polling. Designed for\n    developers building notification systems, chatbots, and interactive experiences\n    on Telegram.\n  tags:\n    - Bots\n    - Chat\n    - Messaging\n    - Notifications\n    - Telegram\n    - Webhooks\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TELEGRAM_BOT_TOKEN: TELEGRAM_BOT_TOKEN\n\ncapability:\n  consumes:\n    - import: telegram-bot\n      location: ./shared/telegram-bot.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: telegram-messaging-api\n      description: \"Unified REST API for Telegram bot messaging and chat management.\"\n      resources:\n        - path: /v1/bot\n          name: bot\n          description: \"Bot information\
  \ and status\"\n          operations:\n            - method: GET\n              name: get-bot-info\n              description: \"Get bot information and verify authentication\"\n              call: \"telegram-bot.get-me\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/updates\n          name: updates\n          description: \"Incoming updates from Telegram users\"\n          operations:\n            - method: GET\n              name: get-updates\n              description: \"Poll for incoming messages, callbacks, and other updates\"\n              call: \"telegram-bot.get-updates\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n                timeout: \"rest.timeout\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.result\"\n\n        - path: /v1/webhook\n          name: webhook\n          description: \"Webhook\
  \ configuration for real-time updates\"\n          operations:\n            - method: GET\n              name: get-webhook-info\n              description: \"Get current webhook status and configuration\"\n              call: \"telegram-bot.get-webhook-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n            - method: POST\n              name: set-webhook\n              description: \"Configure a webhook URL to receive real-time updates\"\n              call: \"telegram-bot.set-webhook\"\n              with:\n                url: \"rest.url\"\n              outputParameters:\n                - type: boolean\n                  mapping: \"$.result\"\n            - method: DELETE\n              name: delete-webhook\n              description: \"Remove the webhook integration and switch to long polling\"\n              call: \"telegram-bot.delete-webhook\"\n              outputParameters:\n                - type: boolean\n\
  \                  mapping: \"$.result\"\n\n        - path: /v1/messages\n          name: messages\n          description: \"Send messages and media to chats\"\n          operations:\n            - method: POST\n              name: send-message\n              description: \"Send a text message to a chat or user\"\n              call: \"telegram-bot.send-message\"\n              with:\n                chat_id: \"rest.chat_id\"\n                text: \"rest.text\"\n                parse_mode: \"rest.parse_mode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n\n        - path: /v1/photos\n          name: photos\n          description: \"Send photos to chats\"\n          operations:\n            - method: POST\n              name: send-photo\n              description: \"Send a photo to a chat\"\n              call: \"telegram-bot.send-photo\"\n              with:\n                chat_id: \"rest.chat_id\"\n                photo:\
  \ \"rest.photo\"\n                caption: \"rest.caption\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n\n        - path: /v1/documents\n          name: documents\n          description: \"Send documents and files to chats\"\n          operations:\n            - method: POST\n              name: send-document\n              description: \"Send a document or file to a chat\"\n              call: \"telegram-bot.send-document\"\n              with:\n                chat_id: \"rest.chat_id\"\n                document: \"rest.document\"\n                caption: \"rest.caption\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n\n        - path: /v1/polls\n          name: polls\n          description: \"Create polls in chats\"\n          operations:\n            - method: POST\n              name: send-poll\n              description: \"Send a native poll to a chat\"\n   \
  \           call: \"telegram-bot.send-poll\"\n              with:\n                chat_id: \"rest.chat_id\"\n                question: \"rest.question\"\n                options: \"rest.options\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n\n        - path: /v1/chats/{chat_id}\n          name: chat\n          description: \"Chat information and management\"\n          operations:\n            - method: GET\n              name: get-chat\n              description: \"Get information about a chat\"\n              call: \"telegram-bot.get-chat\"\n              with:\n                chat_id: \"rest.chat_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n\n        - path: /v1/chats/{chat_id}/administrators\n          name: chat-administrators\n          description: \"Chat administrator list\"\n          operations:\n            - method: GET\n              name: get-chat-administrators\n\
  \              description: \"List all administrators in a chat\"\n              call: \"telegram-bot.get-chat-administrators\"\n              with:\n                chat_id: \"rest.chat_id\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.result\"\n\n        - path: /v1/commands\n          name: commands\n          description: \"Bot command menu\"\n          operations:\n            - method: GET\n              name: get-commands\n              description: \"Get the current bot command menu\"\n              call: \"telegram-bot.get-my-commands\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.result\"\n            - method: PUT\n              name: set-commands\n              description: \"Update the bot command menu\"\n              call: \"telegram-bot.set-my-commands\"\n              with:\n                commands: \"rest.commands\"\n              outputParameters:\n                -\
  \ type: boolean\n                  mapping: \"$.result\"\n\n    - type: mcp\n      port: 9090\n      namespace: telegram-messaging-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Telegram bot messaging, chat management, and automation.\"\n      tools:\n        - name: get-bot-info\n          description: \"Get basic information about the Telegram bot including name, username, and capabilities\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telegram-bot.get-me\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-updates\n          description: \"Poll Telegram for new incoming messages, button clicks, and other updates via long polling\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"telegram-bot.get-updates\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n     \
  \       timeout: \"tools.timeout\"\n          outputParameters:\n            - type: array\n              mapping: \"$.result\"\n\n        - name: get-webhook-info\n          description: \"Get the current webhook configuration and status including last error and pending update count\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telegram-bot.get-webhook-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n\n        - name: set-webhook\n          description: \"Configure a webhook URL so Telegram pushes updates in real-time instead of requiring polling\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"telegram-bot.set-webhook\"\n          with:\n            url: \"tools.url\"\n          outputParameters:\n            - type: boolean\n              mapping: \"$.result\"\n\n        - name: send-text-message\n  \
  \        description: \"Send a text message to a Telegram chat, group, or channel. Supports Markdown and HTML formatting.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telegram-bot.send-message\"\n          with:\n            chat_id: \"tools.chat_id\"\n            text: \"tools.text\"\n            parse_mode: \"tools.parse_mode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n\n        - name: send-photo\n          description: \"Send a photo to a Telegram chat with an optional caption\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telegram-bot.send-photo\"\n          with:\n            chat_id: \"tools.chat_id\"\n            photo: \"tools.photo\"\n            caption: \"tools.caption\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\
  \n\n        - name: send-document\n          description: \"Send a document or file to a Telegram chat\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telegram-bot.send-document\"\n          with:\n            chat_id: \"tools.chat_id\"\n            document: \"tools.document\"\n            caption: \"tools.caption\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n\n        - name: create-poll\n          description: \"Create and send a native Telegram poll to gather opinions from chat members\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"telegram-bot.send-poll\"\n          with:\n            chat_id: \"tools.chat_id\"\n            question: \"tools.question\"\n            options: \"tools.options\"\n            is_anonymous: \"tools.is_anonymous\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.result\"\n\n        - name: get-chat-info\n          description: \"Get detailed information about a chat including title, description, member count, and invite link\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telegram-bot.get-chat\"\n          with:\n            chat_id: \"tools.chat_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n\n        - name: list-chat-admins\n          description: \"List all administrators in a Telegram chat with their admin permissions\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telegram-bot.get-chat-administrators\"\n          with:\n            chat_id: \"tools.chat_id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.result\"\n\n        - name: get-member-count\n          description: \"Get the total number of\
  \ members in a Telegram chat\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"telegram-bot.get-chat-member-count\"\n          with:\n            chat_id: \"tools.chat_id\"\n          outputParameters:\n            - type: integer\n              mapping: \"$.result\"\n\n        - name: set-bot-commands\n          description: \"Set the list of commands shown in the bot's command menu that users see when they type /\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"telegram-bot.set-my-commands\"\n          with:\n            commands: \"tools.commands\"\n          outputParameters:\n            - type: boolean\n              mapping: \"$.result\"\n\n        - name: get-bot-commands\n          description: \"Get the current list of commands in the bot's command menu\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"\
  telegram-bot.get-my-commands\"\n          outputParameters:\n            - type: array\n              mapping: \"$.result\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/telegram/refs/heads/main/capabilities/bot-messaging.yaml
tags:
- Bots
- Chat
- Messaging
- Notifications
- Telegram
- Webhooks
tools:
- description: Get basic information about the Telegram bot including name, username, and capabilities
  hints:
    openWorld: false
    readOnly: true
  name: get-bot-info
- description: Poll Telegram for new incoming messages, button clicks, and other updates via long polling
  hints:
    openWorld: true
    readOnly: true
  name: get-updates
- description: Get the current webhook configuration and status including last error and pending update count
  hints:
    openWorld: false
    readOnly: true
  name: get-webhook-info
- description: Configure a webhook URL so Telegram pushes updates in real-time instead of requiring polling
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-webhook
- description: Send a text message to a Telegram chat, group, or channel. Supports Markdown and HTML formatting.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-text-message
- description: Send a photo to a Telegram chat with an optional caption
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-photo
- description: Send a document or file to a Telegram chat
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-document
- description: Create and send a native Telegram poll to gather opinions from chat members
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-poll
- description: Get detailed information about a chat including title, description, member count, and invite link
  hints:
    openWorld: false
    readOnly: true
  name: get-chat-info
- description: List all administrators in a Telegram chat with their admin permissions
  hints:
    openWorld: false
    readOnly: true
  name: list-chat-admins
- description: Get the total number of members in a Telegram chat
  hints:
    openWorld: false
    readOnly: true
  name: get-member-count
- description: Set the list of commands shown in the bot's command menu that users see when they type /
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-bot-commands
- description: Get the current list of commands in the bot's command menu
  hints:
    openWorld: false
    readOnly: true
  name: get-bot-commands
---
