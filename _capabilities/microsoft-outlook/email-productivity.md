---
categories:
- messaging
consumed_apis:
- graph-mail
description: Unified capability for Microsoft Outlook email productivity combining mail operations, folder management, and attachment handling via Microsoft Graph. Used by productivity teams, IT administrators, and automation engineers.
layout: capability
name: Microsoft Outlook Email Productivity
operations:
- description: List email messages
  method: GET
  name: list-messages
  path: /v1/messages
- description: Create a draft message
  method: POST
  name: create-draft
  path: /v1/messages
- description: Get a specific message
  method: GET
  name: get-message
  path: /v1/messages/{id}
- description: Update a message
  method: PATCH
  name: update-message
  path: /v1/messages/{id}
- description: Delete a message
  method: DELETE
  name: delete-message
  path: /v1/messages/{id}
- description: Send a draft message
  method: POST
  name: send-draft
  path: /v1/messages/{id}/send
- description: Reply to a message
  method: POST
  name: reply
  path: /v1/messages/{id}/reply
- description: Forward a message
  method: POST
  name: forward
  path: /v1/messages/{id}/forward
- description: List attachments
  method: GET
  name: list-attachments
  path: /v1/messages/{id}/attachments
- description: Add an attachment
  method: POST
  name: add-attachment
  path: /v1/messages/{id}/attachments
- description: Send a new email message
  method: POST
  name: send-mail
  path: /v1/send-mail
- description: List mail folders
  method: GET
  name: list-folders
  path: /v1/folders
- description: Create a mail folder
  method: POST
  name: create-folder
  path: /v1/folders
- description: Get a mail folder
  method: GET
  name: get-folder
  path: /v1/folders/{id}
- description: Update a mail folder
  method: PATCH
  name: update-folder
  path: /v1/folders/{id}
- description: Delete a mail folder
  method: DELETE
  name: delete-folder
  path: /v1/folders/{id}
- description: List messages in a folder
  method: GET
  name: list-folder-messages
  path: /v1/folders/{id}/messages
personas: []
provider_name: Microsoft Outlook
provider_slug: microsoft-outlook
search_terms:
- get attachment
- forward a message
- send a new email message
- email
- move message
- forward message
- contacts
- email messages
- create a mail folder
- reply to message
- list folder messages
- calendar
- create a draft message
- send draft
- add an attachment
- send a new email directly
- delete a mail folder
- create a draft email message
- update a mail folder
- delete an email message
- outlook
- reply all to message
- delete a message
- send a new email message directly
- list messages in a specific mail folder
- delete message
- microsoft
- reply to an email message
- move a message to a different folder
- get a specific message
- list mail folders in the mailbox
- create folder
- reply all to an email message
- get message
- update a message
- list email messages in the outlook mailbox
- copy message
- reply to a message
- delete folder
- update an email message
- send a draft message
- mail folders
- forward an email message to recipients
- create draft
- list messages
- update message
- list folders
- single email message
- office 365
- enterprise
- graph api
- add an attachment to a message
- list email messages
- get folder
- messages in a folder
- list messages in a folder
- send an existing draft message
- productivity
- list attachments
- copy a message to a different folder
- delete an attachment from a message
- single mail folder
- get a specific email message by id
- create a new mail folder
- list attachments for a message
- update folder
- reply
- send mail
- get a specific mail folder
- get a mail folder
- forward
- delete attachment
- add attachment
- message attachments
- get a specific attachment from a message
- list mail folders
slug: email-productivity
source_filename: email-productivity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Microsoft Outlook Email Productivity\"\n  description: \"Unified capability for Microsoft Outlook email productivity combining mail operations, folder management, and attachment handling via Microsoft Graph. Used by productivity teams, IT administrators, and automation engineers.\"\n  tags:\n    - Microsoft\n    - Outlook\n    - Email\n    - Productivity\n    - Graph API\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MICROSOFT_GRAPH_TOKEN: MICROSOFT_GRAPH_TOKEN\n\ncapability:\n  consumes:\n    - import: graph-mail\n      location: ./shared/graph-mail.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: email-productivity-api\n      description: \"Unified REST API for Microsoft Outlook email productivity.\"\n      resources:\n        - path: /v1/messages\n          name: messages\n          description: \"Email messages\"\n          operations:\n       \
  \     - method: GET\n              name: list-messages\n              description: \"List email messages\"\n              call: \"graph-mail.list-messages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-draft\n              description: \"Create a draft message\"\n              call: \"graph-mail.create-draft-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages/{id}\n          name: message\n          description: \"Single email message\"\n          operations:\n            - method: GET\n              name: get-message\n              description: \"Get a specific message\"\n              call: \"graph-mail.get-message\"\n              with:\n                message-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n          \
  \  - method: PATCH\n              name: update-message\n              description: \"Update a message\"\n              call: \"graph-mail.update-message\"\n              with:\n                message-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-message\n              description: \"Delete a message\"\n              call: \"graph-mail.delete-message\"\n              with:\n                message-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages/{id}/send\n          name: send-draft\n          description: \"Send a draft message\"\n          operations:\n            - method: POST\n              name: send-draft\n              description: \"Send a draft message\"\n              call: \"graph-mail.send-draft-message\"\n              with:\n                message-id:\
  \ \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages/{id}/reply\n          name: reply\n          description: \"Reply to a message\"\n          operations:\n            - method: POST\n              name: reply\n              description: \"Reply to a message\"\n              call: \"graph-mail.reply-to-message\"\n              with:\n                message-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/messages/{id}/forward\n          name: forward\n          description: \"Forward a message\"\n          operations:\n            - method: POST\n              name: forward\n              description: \"Forward a message\"\n              call: \"graph-mail.forward-message\"\n              with:\n                message-id: \"rest.id\"\n              outputParameters:\n                - type: object\n      \
  \            mapping: \"$.\"\n        - path: /v1/messages/{id}/attachments\n          name: attachments\n          description: \"Message attachments\"\n          operations:\n            - method: GET\n              name: list-attachments\n              description: \"List attachments\"\n              call: \"graph-mail.list-attachments\"\n              with:\n                message-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-attachment\n              description: \"Add an attachment\"\n              call: \"graph-mail.add-attachment\"\n              with:\n                message-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/send-mail\n          name: send-mail\n          description: \"Send a new email directly\"\n          operations:\n            - method: POST\n   \
  \           name: send-mail\n              description: \"Send a new email message\"\n              call: \"graph-mail.send-mail\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/folders\n          name: folders\n          description: \"Mail folders\"\n          operations:\n            - method: GET\n              name: list-folders\n              description: \"List mail folders\"\n              call: \"graph-mail.list-mail-folders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-folder\n              description: \"Create a mail folder\"\n              call: \"graph-mail.create-mail-folder\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/folders/{id}\n          name: folder\n          description: \"Single mail folder\"\n        \
  \  operations:\n            - method: GET\n              name: get-folder\n              description: \"Get a mail folder\"\n              call: \"graph-mail.get-mail-folder\"\n              with:\n                mailFolder-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-folder\n              description: \"Update a mail folder\"\n              call: \"graph-mail.update-mail-folder\"\n              with:\n                mailFolder-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-folder\n              description: \"Delete a mail folder\"\n              call: \"graph-mail.delete-mail-folder\"\n              with:\n                mailFolder-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                 \
  \ mapping: \"$.\"\n        - path: /v1/folders/{id}/messages\n          name: folder-messages\n          description: \"Messages in a folder\"\n          operations:\n            - method: GET\n              name: list-folder-messages\n              description: \"List messages in a folder\"\n              call: \"graph-mail.list-messages-in-folder\"\n              with:\n                mailFolder-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: email-productivity-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Microsoft Outlook email productivity.\"\n      tools:\n        - name: list-messages\n          description: \"List email messages in the Outlook mailbox\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"graph-mail.list-messages\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: get-message\n          description: \"Get a specific email message by ID\"\n          hints:\n            readOnly: true\n          call: \"graph-mail.get-message\"\n          with:\n            message-id: \"tools.message_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-mail\n          description: \"Send a new email message directly\"\n          hints:\n            readOnly: false\n          call: \"graph-mail.send-mail\"\n          with:\n            message: \"tools.message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-draft\n          description: \"Create a draft email message\"\n          hints:\n            readOnly: false\n          call: \"graph-mail.create-draft-message\"\n          with:\n            subject: \"tools.subject\"\n            body: \"tools.body\"\n            to_recipients: \"tools.to_recipients\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-draft\n          description: \"Send an existing draft message\"\n          hints:\n            readOnly: false\n          call: \"graph-mail.send-draft-message\"\n          with:\n            message-id: \"tools.message_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-message\n          description: \"Update an email message\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"graph-mail.update-message\"\n          with:\n            message-id: \"tools.message_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-message\n          description: \"Delete an email message\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"graph-mail.delete-message\"\n     \
  \     with:\n            message-id: \"tools.message_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reply-to-message\n          description: \"Reply to an email message\"\n          hints:\n            readOnly: false\n          call: \"graph-mail.reply-to-message\"\n          with:\n            message-id: \"tools.message_id\"\n            comment: \"tools.comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reply-all-to-message\n          description: \"Reply all to an email message\"\n          hints:\n            readOnly: false\n          call: \"graph-mail.reply-all-to-message\"\n          with:\n            message-id: \"tools.message_id\"\n            comment: \"tools.comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: forward-message\n          description: \"Forward an email message to recipients\"\
  \n          hints:\n            readOnly: false\n          call: \"graph-mail.forward-message\"\n          with:\n            message-id: \"tools.message_id\"\n            comment: \"tools.comment\"\n            to_recipients: \"tools.to_recipients\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: copy-message\n          description: \"Copy a message to a different folder\"\n          hints:\n            readOnly: false\n          call: \"graph-mail.copy-message\"\n          with:\n            message-id: \"tools.message_id\"\n            destination_id: \"tools.destination_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: move-message\n          description: \"Move a message to a different folder\"\n          hints:\n            readOnly: false\n          call: \"graph-mail.move-message\"\n          with:\n            message-id: \"tools.message_id\"\n            destination_id:\
  \ \"tools.destination_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-folders\n          description: \"List mail folders in the mailbox\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"graph-mail.list-mail-folders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-folder\n          description: \"Create a new mail folder\"\n          hints:\n            readOnly: false\n          call: \"graph-mail.create-mail-folder\"\n          with:\n            display_name: \"tools.display_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-folder\n          description: \"Get a specific mail folder\"\n          hints:\n            readOnly: true\n          call: \"graph-mail.get-mail-folder\"\n          with:\n            mailFolder-id: \"tools.folder_id\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-folder\n          description: \"Delete a mail folder\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"graph-mail.delete-mail-folder\"\n          with:\n            mailFolder-id: \"tools.folder_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-folder-messages\n          description: \"List messages in a specific mail folder\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"graph-mail.list-messages-in-folder\"\n          with:\n            mailFolder-id: \"tools.folder_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-attachments\n          description: \"List attachments for a message\"\n          hints:\n            readOnly: true\n          call: \"graph-mail.list-attachments\"\
  \n          with:\n            message-id: \"tools.message_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-attachment\n          description: \"Get a specific attachment from a message\"\n          hints:\n            readOnly: true\n          call: \"graph-mail.get-attachment\"\n          with:\n            message-id: \"tools.message_id\"\n            attachment-id: \"tools.attachment_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-attachment\n          description: \"Add an attachment to a message\"\n          hints:\n            readOnly: false\n          call: \"graph-mail.add-attachment\"\n          with:\n            message-id: \"tools.message_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-attachment\n          description: \"Delete an attachment from a message\"\n          hints:\n\
  \            readOnly: false\n            destructive: true\n          call: \"graph-mail.delete-attachment\"\n          with:\n            message-id: \"tools.message_id\"\n            attachment-id: \"tools.attachment_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-outlook/refs/heads/main/capabilities/email-productivity.yaml
tags:
- Microsoft
- Outlook
- Email
- Productivity
- Graph API
tools:
- description: List email messages in the Outlook mailbox
  hints:
    openWorld: true
    readOnly: true
  name: list-messages
- description: Get a specific email message by ID
  hints:
    readOnly: true
  name: get-message
- description: Send a new email message directly
  hints:
    readOnly: false
  name: send-mail
- description: Create a draft email message
  hints:
    readOnly: false
  name: create-draft
- description: Send an existing draft message
  hints:
    readOnly: false
  name: send-draft
- description: Update an email message
  hints:
    idempotent: true
    readOnly: false
  name: update-message
- description: Delete an email message
  hints:
    destructive: true
    readOnly: false
  name: delete-message
- description: Reply to an email message
  hints:
    readOnly: false
  name: reply-to-message
- description: Reply all to an email message
  hints:
    readOnly: false
  name: reply-all-to-message
- description: Forward an email message to recipients
  hints:
    readOnly: false
  name: forward-message
- description: Copy a message to a different folder
  hints:
    readOnly: false
  name: copy-message
- description: Move a message to a different folder
  hints:
    readOnly: false
  name: move-message
- description: List mail folders in the mailbox
  hints:
    openWorld: true
    readOnly: true
  name: list-folders
- description: Create a new mail folder
  hints:
    readOnly: false
  name: create-folder
- description: Get a specific mail folder
  hints:
    readOnly: true
  name: get-folder
- description: Delete a mail folder
  hints:
    destructive: true
    readOnly: false
  name: delete-folder
- description: List messages in a specific mail folder
  hints:
    openWorld: true
    readOnly: true
  name: list-folder-messages
- description: List attachments for a message
  hints:
    readOnly: true
  name: list-attachments
- description: Get a specific attachment from a message
  hints:
    readOnly: true
  name: get-attachment
- description: Add an attachment to a message
  hints:
    readOnly: false
  name: add-attachment
- description: Delete an attachment from a message
  hints:
    destructive: true
    readOnly: false
  name: delete-attachment
---
