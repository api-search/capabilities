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
- office 365
- reply all to an email message
- messages in a folder
- list folders
- list messages
- forward a message
- move a message to a different folder
- update a message
- calendar
- list email messages in the outlook mailbox
- delete attachment
- delete a message
- create draft
- create a mail folder
- move message
- reply all to message
- get a mail folder
- send an existing draft message
- list attachments for a message
- email messages
- get a specific message
- reply to a message
- delete an attachment from a message
- get message
- add attachment
- send a new email directly
- reply to an email message
- copy a message to a different folder
- productivity
- send a draft message
- delete folder
- enterprise
- outlook
- create a new mail folder
- get attachment
- update folder
- list messages in a folder
- single mail folder
- delete an email message
- email
- list attachments
- delete message
- update an email message
- update a mail folder
- update message
- forward an email message to recipients
- forward
- forward message
- message attachments
- graph api
- create folder
- delete a mail folder
- send a new email message directly
- single email message
- create a draft email message
- copy message
- get a specific mail folder
- add an attachment to a message
- send draft
- list messages in a specific mail folder
- get a specific email message by id
- list email messages
- list mail folders in the mailbox
- create a draft message
- list mail folders
- reply to message
- contacts
- microsoft
- get folder
- list folder messages
- send a new email message
- send mail
- get a specific attachment from a message
- reply
- add an attachment
- mail folders
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
