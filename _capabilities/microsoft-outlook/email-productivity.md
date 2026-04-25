---
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
- productivity
- enterprise
- messages in a folder
- email
- get a specific mail folder
- update folder
- list email messages
- create folder
- move message
- get a specific attachment from a message
- delete a mail folder
- get message
- list messages in a specific mail folder
- delete attachment
- get a specific message
- list mail folders in the mailbox
- add an attachment to a message
- calendar
- update message
- contacts
- send mail
- copy message
- create a new mail folder
- reply to message
- send draft
- move a message to a different folder
- add attachment
- forward an email message to recipients
- delete an attachment from a message
- list attachments for a message
- get a mail folder
- mail folders
- create a draft email message
- send a new email message
- get folder
- send a new email message directly
- forward a message
- delete folder
- microsoft
- send a draft message
- add an attachment
- list attachments
- send an existing draft message
- outlook
- list mail folders
- create draft
- delete an email message
- get attachment
- message attachments
- update an email message
- single mail folder
- graph api
- email messages
- delete message
- list email messages in the outlook mailbox
- send a new email directly
- create a draft message
- get a specific email message by id
- reply to an email message
- single email message
- forward
- reply all to an email message
- forward message
- update a message
- delete a message
- reply to a message
- reply
- office 365
- list folder messages
- create a mail folder
- update a mail folder
- list messages
- copy a message to a different folder
- reply all to message
- list folders
- list messages in a folder
slug: email-productivity
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
