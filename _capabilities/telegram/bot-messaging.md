---
categories: []
consumed_apis: []
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
- webhooks
- incoming updates from telegram users
- poll telegram for new incoming messages, button clicks, and other updates via long polling
- bot information and status
- send photo
- send a native poll to a chat
- get the current list of commands in the bot's command menu
- set webhook
- get updates
- send a text message to a chat or user
- send poll
- send a document or file to a telegram chat
- send text message
- get bot info
- get bot commands
- get the total number of members in a telegram chat
- list all administrators in a telegram chat with their admin permissions
- get chat info
- get member count
- delete webhook
- send document
- remove the webhook integration and switch to long polling
- get basic information about the telegram bot including name, username, and capabilities
- send a photo to a telegram chat with an optional caption
- get webhook info
- send a photo to a chat
- get chat administrators
- get commands
- get current webhook status and configuration
- send a document or file to a chat
- get detailed information about a chat including title, description, member count, and invite link
- get bot information and verify authentication
- configure a webhook url to receive real-time updates
- get the current bot command menu
- telegram
- messaging
- list all administrators in a chat
- set the list of commands shown in the bot's command menu that users see when they type /
- poll for incoming messages, callbacks, and other updates
- create polls in chats
- chat information and management
- update the bot command menu
- send messages and media to chats
- send message
- get chat
- configure a webhook url so telegram pushes updates in real-time instead of requiring polling
- list chat admins
- get the current webhook configuration and status including last error and pending update count
- notifications
- payments
- chat
- create and send a native telegram poll to gather opinions from chat members
- bot command menu
- send a text message to a telegram chat, group, or channel. supports markdown and html formatting.
- set commands
- create poll
- set bot commands
- send documents and files to chats
- webhook configuration for real-time updates
- get information about a chat
- send photos to chats
- bots
- chat administrator list
slug: bot-messaging
source_filename: bot-messaging.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Telegram Bot Messaging\n  description: Unified capability for Telegram bot messaging workflows. Covers sending messages, media, polls, and managing\n    updates via webhooks or long polling. Designed for developers building notification systems, chatbots, and interactive\n    experiences on Telegram.\n  tags:\n  - Bots\n  - Chat\n  - Messaging\n  - Notifications\n  - Telegram\n  - Webhooks\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TELEGRAM_BOT_TOKEN: TELEGRAM_BOT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: telegram-bot\n    baseUri: https://api.telegram.org/bot{token}\n    description: Telegram Bot API - interact with bots, chats, users, and messages on the Telegram platform.\n    authentication:\n      type: apikey\n      key: token\n      value: '{{TELEGRAM_BOT_TOKEN}}'\n      placement: path\n    resources:\n    - name: bot-info\n      path: /getMe\n      description:\
  \ Bot identity and configuration\n      operations:\n      - name: get-me\n        method: POST\n        description: Get basic bot information and authentication test\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: updates\n      path: /getUpdates\n      description: Receive incoming updates via long polling\n      operations:\n      - name: get-updates\n        method: POST\n        description: Receive incoming updates using long polling\n        inputParameters:\n        - name: offset\n          in: body\n          type: integer\n          required: false\n          description: Identifier of the first update to be returned\n        - name: limit\n          in: body\n          type: integer\n          required: false\n          description: Limits number of updates to retrieve (1-100)\n        - name: timeout\n          in: body\n          type: integer\n          required: false\n        \
  \  description: Timeout in seconds for long polling\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.result\n    - name: webhook\n      path: /setWebhook\n      description: Configure incoming webhook for updates\n      operations:\n      - name: set-webhook\n        method: POST\n        description: Specify URL for incoming webhook updates\n        inputParameters:\n        - name: url\n          in: body\n          type: string\n          required: true\n          description: HTTPS URL to send updates to\n        - name: max_connections\n          in: body\n          type: integer\n          required: false\n          description: Maximum simultaneous HTTPS connections (1-100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: boolean\n          value: $.result\n      - name: delete-webhook\n        method: POST\n        description: Remove webhook integration\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: boolean\n          value: $.result\n      - name: get-webhook-info\n        method: POST\n        description: Get current webhook status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n    - name: messages\n      path: /sendMessage\n      description: Send various types of messages\n      operations:\n      - name: send-message\n        method: POST\n        description: Send a text message to a chat\n        inputParameters:\n        - name: chat_id\n          in: body\n          type: string\n          required: true\n          description: Unique identifier for the target chat\n        - name: text\n          in: body\n          type: string\n          required: true\n          description: Text of the message to be sent\n        - name: parse_mode\n          in: body\n          type: string\n      \
  \    required: false\n          description: Markdown, MarkdownV2, or HTML\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n    - name: send-photo\n      path: /sendPhoto\n      description: Send photos\n      operations:\n      - name: send-photo\n        method: POST\n        description: Send a photo to a chat\n        inputParameters:\n        - name: chat_id\n          in: body\n          type: string\n          required: true\n          description: Unique identifier for the target chat\n        - name: photo\n          in: body\n          type: string\n          required: true\n          description: Photo to send (file_id or URL)\n        - name: caption\n          in: body\n          type: string\n          required: false\n          description: Photo caption\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n\
  \    - name: send-document\n      path: /sendDocument\n      description: Send documents and files\n      operations:\n      - name: send-document\n        method: POST\n        description: Send a document file to a chat\n        inputParameters:\n        - name: chat_id\n          in: body\n          type: string\n          required: true\n          description: Unique identifier for the target chat\n        - name: document\n          in: body\n          type: string\n          required: true\n          description: File to send (file_id or URL)\n        - name: caption\n          in: body\n          type: string\n          required: false\n          description: Document caption\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n    - name: send-poll\n      path: /sendPoll\n      description: Create and send polls\n      operations:\n      - name: send-poll\n        method: POST\n        description:\
  \ Send a native poll to a chat\n        inputParameters:\n        - name: chat_id\n          in: body\n          type: string\n          required: true\n          description: Unique identifier for the target chat\n        - name: question\n          in: body\n          type: string\n          required: true\n          description: Poll question (1-300 characters)\n        - name: options\n          in: body\n          type: array\n          required: true\n          description: List of answer options (2-10)\n        - name: is_anonymous\n          in: body\n          type: boolean\n          required: false\n          description: True if the poll needs to be anonymous\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n    - name: chat-management\n      path: /getChat\n      description: Manage chat settings, members, and permissions\n      operations:\n      - name: get-chat\n        method: POST\n  \
  \      description: Get up-to-date information about a chat\n        inputParameters:\n        - name: chat_id\n          in: body\n          type: string\n          required: true\n          description: Unique identifier for the target chat\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: get-chat-administrators\n        method: POST\n        description: Get list of administrators in a chat\n        inputParameters:\n        - name: chat_id\n          in: body\n          type: string\n          required: true\n          description: Unique identifier for the target chat\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.result\n      - name: get-chat-member-count\n        method: POST\n        description: Get the number of members in a chat\n        inputParameters:\n        - name: chat_id\n          in: body\n\
  \          type: string\n          required: true\n          description: Unique identifier for the target chat\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: integer\n          value: $.result\n    - name: bot-commands\n      path: /setMyCommands\n      description: Manage bot command menus\n      operations:\n      - name: set-my-commands\n        method: POST\n        description: Set the list of bot commands\n        inputParameters:\n        - name: commands\n          in: body\n          type: array\n          required: true\n          description: List of bot commands (max 100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: boolean\n          value: $.result\n      - name: get-my-commands\n        method: POST\n        description: Get the current list of bot commands\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n   \
  \       value: $.result\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: telegram-messaging-api\n    description: Unified REST API for Telegram bot messaging and chat management.\n    resources:\n    - path: /v1/bot\n      name: bot\n      description: Bot information and status\n      operations:\n      - method: GET\n        name: get-bot-info\n        description: Get bot information and verify authentication\n        call: telegram-bot.get-me\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/updates\n      name: updates\n      description: Incoming updates from Telegram users\n      operations:\n      - method: GET\n        name: get-updates\n        description: Poll for incoming messages, callbacks, and other updates\n        call: telegram-bot.get-updates\n        with:\n          offset: rest.offset\n          limit: rest.limit\n          timeout: rest.timeout\n        outputParameters:\n        - type: array\n          mapping:\
  \ $.result\n    - path: /v1/webhook\n      name: webhook\n      description: Webhook configuration for real-time updates\n      operations:\n      - method: GET\n        name: get-webhook-info\n        description: Get current webhook status and configuration\n        call: telegram-bot.get-webhook-info\n        outputParameters:\n        - type: object\n          mapping: $.result\n      - method: POST\n        name: set-webhook\n        description: Configure a webhook URL to receive real-time updates\n        call: telegram-bot.set-webhook\n        with:\n          url: rest.url\n        outputParameters:\n        - type: boolean\n          mapping: $.result\n      - method: DELETE\n        name: delete-webhook\n        description: Remove the webhook integration and switch to long polling\n        call: telegram-bot.delete-webhook\n        outputParameters:\n        - type: boolean\n          mapping: $.result\n    - path: /v1/messages\n      name: messages\n      description: Send\
  \ messages and media to chats\n      operations:\n      - method: POST\n        name: send-message\n        description: Send a text message to a chat or user\n        call: telegram-bot.send-message\n        with:\n          chat_id: rest.chat_id\n          text: rest.text\n          parse_mode: rest.parse_mode\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/photos\n      name: photos\n      description: Send photos to chats\n      operations:\n      - method: POST\n        name: send-photo\n        description: Send a photo to a chat\n        call: telegram-bot.send-photo\n        with:\n          chat_id: rest.chat_id\n          photo: rest.photo\n          caption: rest.caption\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/documents\n      name: documents\n      description: Send documents and files to chats\n      operations:\n      - method: POST\n        name: send-document\n    \
  \    description: Send a document or file to a chat\n        call: telegram-bot.send-document\n        with:\n          chat_id: rest.chat_id\n          document: rest.document\n          caption: rest.caption\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/polls\n      name: polls\n      description: Create polls in chats\n      operations:\n      - method: POST\n        name: send-poll\n        description: Send a native poll to a chat\n        call: telegram-bot.send-poll\n        with:\n          chat_id: rest.chat_id\n          question: rest.question\n          options: rest.options\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/chats/{chat_id}\n      name: chat\n      description: Chat information and management\n      operations:\n      - method: GET\n        name: get-chat\n        description: Get information about a chat\n        call: telegram-bot.get-chat\n        with:\n   \
  \       chat_id: rest.chat_id\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/chats/{chat_id}/administrators\n      name: chat-administrators\n      description: Chat administrator list\n      operations:\n      - method: GET\n        name: get-chat-administrators\n        description: List all administrators in a chat\n        call: telegram-bot.get-chat-administrators\n        with:\n          chat_id: rest.chat_id\n        outputParameters:\n        - type: array\n          mapping: $.result\n    - path: /v1/commands\n      name: commands\n      description: Bot command menu\n      operations:\n      - method: GET\n        name: get-commands\n        description: Get the current bot command menu\n        call: telegram-bot.get-my-commands\n        outputParameters:\n        - type: array\n          mapping: $.result\n      - method: PUT\n        name: set-commands\n        description: Update the bot command menu\n        call: telegram-bot.set-my-commands\n\
  \        with:\n          commands: rest.commands\n        outputParameters:\n        - type: boolean\n          mapping: $.result\n  - type: mcp\n    port: 9090\n    namespace: telegram-messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted Telegram bot messaging, chat management, and automation.\n    tools:\n    - name: get-bot-info\n      description: Get basic information about the Telegram bot including name, username, and capabilities\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telegram-bot.get-me\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-updates\n      description: Poll Telegram for new incoming messages, button clicks, and other updates via long polling\n      hints:\n        readOnly: true\n        openWorld: true\n      call: telegram-bot.get-updates\n      with:\n        offset: tools.offset\n        limit: tools.limit\n        timeout: tools.timeout\n      outputParameters:\n\
  \      - type: array\n        mapping: $.result\n    - name: get-webhook-info\n      description: Get the current webhook configuration and status including last error and pending update count\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telegram-bot.get-webhook-info\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: set-webhook\n      description: Configure a webhook URL so Telegram pushes updates in real-time instead of requiring polling\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: telegram-bot.set-webhook\n      with:\n        url: tools.url\n      outputParameters:\n      - type: boolean\n        mapping: $.result\n    - name: send-text-message\n      description: Send a text message to a Telegram chat, group, or channel. Supports Markdown and HTML formatting.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: telegram-bot.send-message\n      with:\n        chat_id: tools.chat_id\n        text: tools.text\n        parse_mode: tools.parse_mode\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: send-photo\n      description: Send a photo to a Telegram chat with an optional caption\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telegram-bot.send-photo\n      with:\n        chat_id: tools.chat_id\n        photo: tools.photo\n        caption: tools.caption\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: send-document\n      description: Send a document or file to a Telegram chat\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telegram-bot.send-document\n      with:\n        chat_id: tools.chat_id\n        document: tools.document\n        caption: tools.caption\n      outputParameters:\n     \
  \ - type: object\n        mapping: $.result\n    - name: create-poll\n      description: Create and send a native Telegram poll to gather opinions from chat members\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: telegram-bot.send-poll\n      with:\n        chat_id: tools.chat_id\n        question: tools.question\n        options: tools.options\n        is_anonymous: tools.is_anonymous\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: get-chat-info\n      description: Get detailed information about a chat including title, description, member count, and invite link\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telegram-bot.get-chat\n      with:\n        chat_id: tools.chat_id\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: list-chat-admins\n      description: List all administrators in a Telegram chat with their admin permissions\n\
  \      hints:\n        readOnly: true\n        openWorld: false\n      call: telegram-bot.get-chat-administrators\n      with:\n        chat_id: tools.chat_id\n      outputParameters:\n      - type: array\n        mapping: $.result\n    - name: get-member-count\n      description: Get the total number of members in a Telegram chat\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telegram-bot.get-chat-member-count\n      with:\n        chat_id: tools.chat_id\n      outputParameters:\n      - type: integer\n        mapping: $.result\n    - name: set-bot-commands\n      description: Set the list of commands shown in the bot's command menu that users see when they type /\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: telegram-bot.set-my-commands\n      with:\n        commands: tools.commands\n      outputParameters:\n      - type: boolean\n        mapping: $.result\n    - name: get-bot-commands\n      description:\
  \ Get the current list of commands in the bot's command menu\n      hints:\n        readOnly: true\n        openWorld: false\n      call: telegram-bot.get-my-commands\n      outputParameters:\n      - type: array\n        mapping: $.result\n"
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
