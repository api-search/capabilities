---
categories: []
consumed_apis: []
description: The Gmail API lets you view and manage Gmail mailbox data like threads, messages, and labels. It provides RESTful access to Gmail mailboxes including message sending, drafting, organizing with labels, managing settings, and push notifications for mailbox changes.
layout: capability
name: Google Gmail API
operations:
- description: Google Gmail Get user profile
  method: GET
  name: getuserprofile
  path: /gmail/v1/users/{userId}/profile
- description: Google Gmail List messages
  method: GET
  name: listmessages
  path: /gmail/v1/users/{userId}/messages
- description: Google Gmail Insert message
  method: POST
  name: insertmessage
  path: /gmail/v1/users/{userId}/messages
- description: Google Gmail Get message
  method: GET
  name: getmessage
  path: /gmail/v1/users/{userId}/messages/{id}
- description: Google Gmail Delete message
  method: DELETE
  name: deletemessage
  path: /gmail/v1/users/{userId}/messages/{id}
- description: Google Gmail Send message
  method: POST
  name: sendmessage
  path: /gmail/v1/users/{userId}/messages/send
- description: Google Gmail Modify message
  method: POST
  name: modifymessage
  path: /gmail/v1/users/{userId}/messages/{id}/modify
- description: Google Gmail Trash message
  method: POST
  name: trashmessage
  path: /gmail/v1/users/{userId}/messages/{id}/trash
- description: Google Gmail Untrash message
  method: POST
  name: untrashmessage
  path: /gmail/v1/users/{userId}/messages/{id}/untrash
- description: Google Gmail List labels
  method: GET
  name: listlabels
  path: /gmail/v1/users/{userId}/labels
- description: Google Gmail Create label
  method: POST
  name: createlabel
  path: /gmail/v1/users/{userId}/labels
- description: Google Gmail Get label
  method: GET
  name: getlabel
  path: /gmail/v1/users/{userId}/labels/{id}
- description: Google Gmail Update label
  method: PUT
  name: updatelabel
  path: /gmail/v1/users/{userId}/labels/{id}
- description: Google Gmail Delete label
  method: DELETE
  name: deletelabel
  path: /gmail/v1/users/{userId}/labels/{id}
- description: Google Gmail List threads
  method: GET
  name: listthreads
  path: /gmail/v1/users/{userId}/threads
- description: Google Gmail Get thread
  method: GET
  name: getthread
  path: /gmail/v1/users/{userId}/threads/{id}
- description: Google Gmail Delete thread
  method: DELETE
  name: deletethread
  path: /gmail/v1/users/{userId}/threads/{id}
- description: Google Gmail List drafts
  method: GET
  name: listdrafts
  path: /gmail/v1/users/{userId}/drafts
- description: Google Gmail Create draft
  method: POST
  name: createdraft
  path: /gmail/v1/users/{userId}/drafts
- description: Google Gmail Get draft
  method: GET
  name: getdraft
  path: /gmail/v1/users/{userId}/drafts/{id}
- description: Google Gmail Update draft
  method: PUT
  name: updatedraft
  path: /gmail/v1/users/{userId}/drafts/{id}
- description: Google Gmail Delete draft
  method: DELETE
  name: deletedraft
  path: /gmail/v1/users/{userId}/drafts/{id}
- description: Google Gmail Send draft
  method: POST
  name: senddraft
  path: /gmail/v1/users/{userId}/drafts/send
- description: Google Gmail List history
  method: GET
  name: listhistory
  path: /gmail/v1/users/{userId}/history
- description: Google Gmail Watch mailbox
  method: POST
  name: watchmailbox
  path: /gmail/v1/users/{userId}/watch
- description: Google Gmail Stop watching mailbox
  method: POST
  name: stopmailboxwatch
  path: /gmail/v1/users/{userId}/stop
- description: Google Gmail Get auto-forwarding settings
  method: GET
  name: getautoforwarding
  path: /gmail/v1/users/{userId}/settings/autoForwarding
- description: Google Gmail List filters
  method: GET
  name: listfilters
  path: /gmail/v1/users/{userId}/settings/filters
- description: Google Gmail Create filter
  method: POST
  name: createfilter
  path: /gmail/v1/users/{userId}/settings/filters
personas: []
provider_name: Google Gmail
provider_slug: google-gmail
search_terms:
- google gmail list threads
- watchmailbox
- deletemessage
- google gmail get draft
- getmessage
- google gmail delete draft
- getautoforwarding
- deletedraft
- createdraft
- google gmail create draft
- api
- google gmail list history
- google gmail stop watching mailbox
- google gmail insert message
- google gmail list labels
- google gmail untrash message
- listhistory
- drafts
- google gmail get user profile
- google gmail create label
- google
- listdrafts
- google gmail watch mailbox
- google gmail update label
- google gmail modify message
- google gmail get message
- deletelabel
- stopmailboxwatch
- listfilters
- getlabel
- createfilter
- sendmessage
- email
- trashmessage
- google gmail list drafts
- gmail
- insertmessage
- google gmail send message
- google gmail trash message
- updatelabel
- google gmail get label
- getdraft
- google gmail get thread
- senddraft
- google gmail update draft
- modifymessage
- google gmail list filters
- threads
- google gmail send draft
- google gmail delete thread
- google workspace
- listthreads
- untrashmessage
- getuserprofile
- google gmail delete message
- listmessages
- listlabels
- createlabel
- labels
- messaging
- google gmail create filter
- deletethread
- updatedraft
- getthread
- google gmail delete label
- google gmail list messages
- google gmail get auto-forwarding settings
slug: google-gmail-capability
source_filename: google-gmail-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Gmail API\n  description: The Gmail API lets you view and manage Gmail mailbox data like threads, messages, and labels. It provides RESTful\n    access to Gmail mailboxes including message sending, drafting, organizing with labels, managing settings, and push notifications\n    for mailbox changes.\n  tags:\n  - Google\n  - Gmail\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-gmail\n    baseUri: https://gmail.googleapis.com\n    description: Google Gmail API HTTP API.\n    resources:\n    - name: gmail-v1-users-userid-profile\n      path: /gmail/v1/users/{userId}/profile\n      operations:\n      - name: getuserprofile\n        method: GET\n        description: Google Gmail Get user profile\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-messages\n      path: /gmail/v1/users/{userId}/messages\n      operations:\n      - name: listmessages\n        method: GET\n        description: Google Gmail List messages\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: q\n          in: query\n          type: string\n        - name: labelIds\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertmessage\n        method: POST\n        description: Google Gmail Insert message\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-messages-id\n      path: /gmail/v1/users/{userId}/messages/{id}\n      operations:\n      - name: getmessage\n        method: GET\n        description: Google Gmail Get message\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemessage\n        method: DELETE\n        description: Google Gmail Delete message\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n    \
  \    - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-messages-send\n      path: /gmail/v1/users/{userId}/messages/send\n      operations:\n      - name: sendmessage\n        method: POST\n        description: Google Gmail Send message\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-messages-id-modify\n      path: /gmail/v1/users/{userId}/messages/{id}/modify\n      operations:\n      - name: modifymessage\n        method: POST\n        description: Google Gmail Modify message\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n\
  \          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-messages-id-trash\n      path: /gmail/v1/users/{userId}/messages/{id}/trash\n      operations:\n      - name: trashmessage\n        method: POST\n        description: Google Gmail Trash message\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-messages-id-untrash\n      path: /gmail/v1/users/{userId}/messages/{id}/untrash\n      operations:\n      - name: untrashmessage\n        method: POST\n   \
  \     description: Google Gmail Untrash message\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-labels\n      path: /gmail/v1/users/{userId}/labels\n      operations:\n      - name: listlabels\n        method: GET\n        description: Google Gmail List labels\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlabel\n        method: POST\n        description: Google Gmail Create label\n        inputParameters:\n        - name: userId\n          in: path\n\
  \          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-labels-id\n      path: /gmail/v1/users/{userId}/labels/{id}\n      operations:\n      - name: getlabel\n        method: GET\n        description: Google Gmail Get label\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelabel\n        method: PUT\n        description: Google Gmail Update label\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelabel\n        method: DELETE\n        description: Google Gmail Delete label\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-threads\n      path: /gmail/v1/users/{userId}/threads\n      operations:\n      - name: listthreads\n        method: GET\n        description: Google Gmail List threads\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        - name:\
  \ pageToken\n          in: query\n          type: string\n        - name: q\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-threads-id\n      path: /gmail/v1/users/{userId}/threads/{id}\n      operations:\n      - name: getthread\n        method: GET\n        description: Google Gmail Get thread\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletethread\n        method: DELETE\n        description: Google Gmail Delete thread\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required:\
  \ true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-drafts\n      path: /gmail/v1/users/{userId}/drafts\n      operations:\n      - name: listdrafts\n        method: GET\n        description: Google Gmail List drafts\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdraft\n        method: POST\n        description: Google Gmail Create draft\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: gmail-v1-users-userid-drafts-id\n      path: /gmail/v1/users/{userId}/drafts/{id}\n      operations:\n      - name: getdraft\n        method: GET\n        description: Google Gmail Get draft\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedraft\n        method: PUT\n        description: Google Gmail Update draft\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: deletedraft\n        method: DELETE\n        description: Google Gmail Delete draft\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-drafts-send\n      path: /gmail/v1/users/{userId}/drafts/send\n      operations:\n      - name: senddraft\n        method: POST\n        description: Google Gmail Send draft\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-history\n      path: /gmail/v1/users/{userId}/history\n      operations:\n     \
  \ - name: listhistory\n        method: GET\n        description: Google Gmail List history\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: startHistoryId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-watch\n      path: /gmail/v1/users/{userId}/watch\n      operations:\n      - name: watchmailbox\n        method: POST\n        description: Google Gmail Watch mailbox\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-stop\n      path: /gmail/v1/users/{userId}/stop\n      operations:\n     \
  \ - name: stopmailboxwatch\n        method: POST\n        description: Google Gmail Stop watching mailbox\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-settings-autoforwarding\n      path: /gmail/v1/users/{userId}/settings/autoForwarding\n      operations:\n      - name: getautoforwarding\n        method: GET\n        description: Google Gmail Get auto-forwarding settings\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gmail-v1-users-userid-settings-filters\n      path: /gmail/v1/users/{userId}/settings/filters\n      operations:\n      - name: listfilters\n\
  \        method: GET\n        description: Google Gmail List filters\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfilter\n        method: POST\n        description: Google Gmail Create filter\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-gmail-rest\n    description: REST adapter for Google Gmail API.\n    resources:\n    - path: /gmail/v1/users/{userId}/profile\n      name: getuserprofile\n      operations:\n      - method: GET\n        name: getuserprofile\n        description: Google Gmail Get user profile\n\
  \        call: google-gmail.getuserprofile\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/messages\n      name: listmessages\n      operations:\n      - method: GET\n        name: listmessages\n        description: Google Gmail List messages\n        call: google-gmail.listmessages\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/messages\n      name: insertmessage\n      operations:\n      - method: POST\n        name: insertmessage\n        description: Google Gmail Insert message\n        call: google-gmail.insertmessage\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/messages/{id}\n      name: getmessage\n      operations:\n      - method: GET\n        name:\
  \ getmessage\n        description: Google Gmail Get message\n        call: google-gmail.getmessage\n        with:\n          userId: rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/messages/{id}\n      name: deletemessage\n      operations:\n      - method: DELETE\n        name: deletemessage\n        description: Google Gmail Delete message\n        call: google-gmail.deletemessage\n        with:\n          userId: rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/messages/send\n      name: sendmessage\n      operations:\n      - method: POST\n        name: sendmessage\n        description: Google Gmail Send message\n        call: google-gmail.sendmessage\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/messages/{id}/modify\n\
  \      name: modifymessage\n      operations:\n      - method: POST\n        name: modifymessage\n        description: Google Gmail Modify message\n        call: google-gmail.modifymessage\n        with:\n          userId: rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/messages/{id}/trash\n      name: trashmessage\n      operations:\n      - method: POST\n        name: trashmessage\n        description: Google Gmail Trash message\n        call: google-gmail.trashmessage\n        with:\n          userId: rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/messages/{id}/untrash\n      name: untrashmessage\n      operations:\n      - method: POST\n        name: untrashmessage\n        description: Google Gmail Untrash message\n        call: google-gmail.untrashmessage\n        with:\n          userId:\
  \ rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/labels\n      name: listlabels\n      operations:\n      - method: GET\n        name: listlabels\n        description: Google Gmail List labels\n        call: google-gmail.listlabels\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/labels\n      name: createlabel\n      operations:\n      - method: POST\n        name: createlabel\n        description: Google Gmail Create label\n        call: google-gmail.createlabel\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/labels/{id}\n      name: getlabel\n      operations:\n      - method: GET\n        name: getlabel\n        description: Google Gmail Get label\n        call: google-gmail.getlabel\n\
  \        with:\n          userId: rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/labels/{id}\n      name: updatelabel\n      operations:\n      - method: PUT\n        name: updatelabel\n        description: Google Gmail Update label\n        call: google-gmail.updatelabel\n        with:\n          userId: rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/labels/{id}\n      name: deletelabel\n      operations:\n      - method: DELETE\n        name: deletelabel\n        description: Google Gmail Delete label\n        call: google-gmail.deletelabel\n        with:\n          userId: rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/threads\n      name: listthreads\n      operations:\n      - method: GET\n\
  \        name: listthreads\n        description: Google Gmail List threads\n        call: google-gmail.listthreads\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/threads/{id}\n      name: getthread\n      operations:\n      - method: GET\n        name: getthread\n        description: Google Gmail Get thread\n        call: google-gmail.getthread\n        with:\n          userId: rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/threads/{id}\n      name: deletethread\n      operations:\n      - method: DELETE\n        name: deletethread\n        description: Google Gmail Delete thread\n        call: google-gmail.deletethread\n        with:\n          userId: rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/drafts\n\
  \      name: listdrafts\n      operations:\n      - method: GET\n        name: listdrafts\n        description: Google Gmail List drafts\n        call: google-gmail.listdrafts\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/drafts\n      name: createdraft\n      operations:\n      - method: POST\n        name: createdraft\n        description: Google Gmail Create draft\n        call: google-gmail.createdraft\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/drafts/{id}\n      name: getdraft\n      operations:\n      - method: GET\n        name: getdraft\n        description: Google Gmail Get draft\n        call: google-gmail.getdraft\n        with:\n          userId: rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /gmail/v1/users/{userId}/drafts/{id}\n      name: updatedraft\n      operations:\n      - method: PUT\n        name: updatedraft\n        description: Google Gmail Update draft\n        call: google-gmail.updatedraft\n        with:\n          userId: rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/drafts/{id}\n      name: deletedraft\n      operations:\n      - method: DELETE\n        name: deletedraft\n        description: Google Gmail Delete draft\n        call: google-gmail.deletedraft\n        with:\n          userId: rest.userId\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/drafts/send\n      name: senddraft\n      operations:\n      - method: POST\n        name: senddraft\n        description: Google Gmail Send draft\n        call: google-gmail.senddraft\n        with:\n      \
  \    userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/history\n      name: listhistory\n      operations:\n      - method: GET\n        name: listhistory\n        description: Google Gmail List history\n        call: google-gmail.listhistory\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/watch\n      name: watchmailbox\n      operations:\n      - method: POST\n        name: watchmailbox\n        description: Google Gmail Watch mailbox\n        call: google-gmail.watchmailbox\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/stop\n      name: stopmailboxwatch\n      operations:\n      - method: POST\n        name: stopmailboxwatch\n        description: Google Gmail Stop watching mailbox\n \
  \       call: google-gmail.stopmailboxwatch\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/settings/autoForwarding\n      name: getautoforwarding\n      operations:\n      - method: GET\n        name: getautoforwarding\n        description: Google Gmail Get auto-forwarding settings\n        call: google-gmail.getautoforwarding\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/settings/filters\n      name: listfilters\n      operations:\n      - method: GET\n        name: listfilters\n        description: Google Gmail List filters\n        call: google-gmail.listfilters\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gmail/v1/users/{userId}/settings/filters\n      name: createfilter\n  \
  \    operations:\n      - method: POST\n        name: createfilter\n        description: Google Gmail Create filter\n        call: google-gmail.createfilter\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-gmail-mcp\n    transport: http\n    description: MCP adapter for Google Gmail API for AI agent use.\n    tools:\n    - name: getuserprofile\n      description: Google Gmail Get user profile\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-gmail.getuserprofile\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmessages\n      description: Google Gmail List messages\n      hints:\n        readOnly: true\n \
  \       destructive: false\n        idempotent: true\n      call: google-gmail.listmessages\n      with:\n        userId: tools.userId\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n        q: tools.q\n        labelIds: tools.labelIds\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: q\n        type: string\n        description: q\n      - name: labelIds\n        type: array\n        description: labelIds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertmessage\n      description: Google Gmail Insert message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-gmail.insertmessage\n      with:\n        userId: tools.userId\n\
  \      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmessage\n      description: Google Gmail Get message\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-gmail.getmessage\n      with:\n        userId: tools.userId\n        id: tools.id\n        format: tools.format\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      - name: format\n        type: string\n        description: format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemessage\n      description: Google Gmail Delete message\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n\
  \      call: google-gmail.deletemessage\n      with:\n        userId: tools.userId\n        id: tools.id\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendmessage\n      description: Google Gmail Send message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-gmail.sendmessage\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modifymessage\n      description: Google Gmail Modify message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ google-gmail.modifymessage\n      with:\n        userId: tools.userId\n        id: tools.id\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trashmessage\n      description: Google Gmail Trash message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-gmail.trashmessage\n      with:\n        userId: tools.userId\n        id: tools.id\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: untrashmessage\n      description: Google Gmail Untrash message\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-gmail.untrashmessage\n      with:\n        userId: tools.userId\n        id: tools.id\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlabels\n      description: Google Gmail List labels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-gmail.listlabels\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createlabel\n      description: Google Gmail Create label\n      hints:\n     \
  \   readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-gmail.createlabel\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlabel\n      description: Google Gmail Get label\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-gmail.getlabel\n      with:\n        userId: tools.userId\n        id: tools.id\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatelabel\n      description: Google Gmail Update label\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: true\n      call: google-gmail.updatelabel\n      with:\n        userId: tools.userId\n        id: tools.id\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletelabel\n      description: Google Gmail Delete label\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-gmail.deletelabel\n      with:\n        userId: tools.userId\n        id: tools.id\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listthreads\n      description:\
  \ Google Gmail List threads\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-gmail.listthreads\n      with:\n        userId: tools.userId\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n        q: tools.q\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: q\n        type: string\n        description: q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getthread\n      description: Google Gmail Get thread\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-gmail.getthread\n \n\n# --- truncated at 32 KB (38 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/google-gmail/refs/heads/main/capabilities/google-gmail-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-gmail/refs/heads/main/capabilities/google-gmail-capability.yaml
tags:
- Google
- Gmail
- API
tools:
- description: Google Gmail Get user profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserprofile
- description: Google Gmail List messages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmessages
- description: Google Gmail Insert message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertmessage
- description: Google Gmail Get message
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmessage
- description: Google Gmail Delete message
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemessage
- description: Google Gmail Send message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendmessage
- description: Google Gmail Modify message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: modifymessage
- description: Google Gmail Trash message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: trashmessage
- description: Google Gmail Untrash message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: untrashmessage
- description: Google Gmail List labels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlabels
- description: Google Gmail Create label
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlabel
- description: Google Gmail Get label
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlabel
- description: Google Gmail Update label
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelabel
- description: Google Gmail Delete label
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelabel
- description: Google Gmail List threads
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listthreads
- description: Google Gmail Get thread
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getthread
- description: Google Gmail Delete thread
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletethread
- description: Google Gmail List drafts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdrafts
- description: Google Gmail Create draft
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdraft
- description: Google Gmail Get draft
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdraft
- description: Google Gmail Update draft
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedraft
- description: Google Gmail Delete draft
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedraft
- description: Google Gmail Send draft
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: senddraft
- description: Google Gmail List history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listhistory
- description: Google Gmail Watch mailbox
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: watchmailbox
- description: Google Gmail Stop watching mailbox
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopmailboxwatch
- description: Google Gmail Get auto-forwarding settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautoforwarding
- description: Google Gmail List filters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfilters
- description: Google Gmail Create filter
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfilter
---
