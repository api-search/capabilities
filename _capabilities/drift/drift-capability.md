---
categories: []
consumed_apis: []
description: Drift is a cloud-based solution designed to help businesses automate sales processes by adding live chat windows to websites for increased customer experience and loyalty. Key features include chatbots, geo-targeting, offline access, proactive chating and transfers/routing.
layout: capability
name: Drift
operations:
- description: Drift Create a contact
  method: POST
  name: post-contacts
  path: /contacts
- description: Drift List contacts by externalId
  method: GET
  name: get-contacts
  path: /contacts
- description: Update a contact - Drift Id
  method: PATCH
  name: patch-contacts-id
  path: /contacts/{id}
- description: Fetch a contact by Drift Id
  method: GET
  name: get-contacts-id
  path: /contacts/{id}
- description: Drift Delete a contact
  method: POST
  name: post-contacts-id
  path: /contacts/{id}
- description: Drift Update a contact - ExternalId
  method: PATCH
  name: patch-contacts-normalize
  path: /contacts/normalize
- description: Drift List contacts by email
  method: GET
  name: get-contacts
  path: /contacts/
- description: Drift Unsubscribe contacts from emails
  method: POST
  name: post-emails-unsubscribe
  path: /emails/unsubscribe
- description: Drift Post a timeline event to a contact - externalId
  method: POST
  name: post-contacts-timeline
  path: /contacts/timeline
- description: Drift List custom contact attributes
  method: GET
  name: get-contacts-attributes
  path: /contacts/attributes
- description: Drift Fetch a user
  method: GET
  name: get-users-id
  path: /users/{id}
- description: Drift List all users
  method: GET
  name: get-users-list
  path: /users/list
- description: Drift Update a user
  method: PATCH
  name: patch-users-update
  path: /users/update
- description: Drift Fetch booked meetings
  method: GET
  name: get-users-meetings-org
  path: /users/meetings/org
- description: Drift Create a message
  method: POST
  name: post-conversations-id-messages
  path: /conversations/{id}/messages
- description: Drift Fetch a conversation's messages
  method: GET
  name: get-conversations-id-messages
  path: /conversations/{id}/messages
- description: Drift Fetch a conversation
  method: GET
  name: get-conversations-id
  path: /conversations/{id}
- description: Drift Fetch a conversation's transcript as a string
  method: GET
  name: get-conversations-id-transcript
  path: /conversations/{id}/transcript
- description: Drift Fetch a conversation's transcript as a JSON object
  method: GET
  name: get-conversations-id-json-transcript
  path: /conversations/{id}/json_transcript
- description: Drift Fetch a conversation's attachments
  method: GET
  name: get-attachments-id-data
  path: /attachments/{id}/data
- description: Drift Create a conversation
  method: POST
  name: post-conversations-new
  path: /conversations/new
- description: Drift List conversation statuses
  method: GET
  name: get-conversations-stats
  path: /conversations/stats
- description: Drift List conversations
  method: GET
  name: get-conversations-list
  path: /conversations/list
- description: Drift Create an account
  method: POST
  name: post-accounts-create
  path: /accounts/create
- description: Drift Fetch an account
  method: GET
  name: get-accounts-id
  path: /accounts/{id}
- description: Drift Delete an account
  method: DELETE
  name: delete-accounts-id
  path: /accounts/{id}
- description: Drift List accounts
  method: GET
  name: get-accounts
  path: /accounts
- description: Drift Update an account
  method: PATCH
  name: patch-accounts-update
  path: /accounts/update
- description: Drift List playbooks
  method: GET
  name: get-playbooks-list
  path: /playbooks/list
- description: Drift List conversational landing pages (CLP)
  method: GET
  name: get-playbooks-clp
  path: /playbooks/clp
- description: Drift List teams
  method: GET
  name: get-teams-org
  path: /teams/org
- description: Drift List teams by user
  method: GET
  name: get-teams-users-id
  path: /teams/users/{id}
- description: Drift Trigger app uninstall
  method: POST
  name: post-app-uninstall
  path: /app/uninstall
- description: Drift Get token information
  method: POST
  name: post-app-token-info
  path: /app/token_info
- description: Drift Fetch GDPR data
  method: POST
  name: post-gdpr-retrieve
  path: /gdpr/retrieve
- description: Drift Delete GDPR data
  method: POST
  name: post-gdpr-delete
  path: /gdpr/delete
- description: Drift List user objects
  method: GET
  name: get-scim-users
  path: /scim/Users
- description: Drift Provision a user
  method: POST
  name: post-scim-users
  path: /scim/Users
- description: Drift Update a user
  method: PUT
  name: put-scim-users
  path: /scim/Users
- description: Drift Deprovision a user
  method: DELETE
  name: delete-scim-users
  path: /scim/Users
- description: Drift Fetch a user object
  method: GET
  name: get-scim-users-id
  path: /scim/Users/{id}
personas: []
provider_name: Drift
provider_slug: drift
search_terms:
- delete scim users
- drift list conversation statuses
- drift update an account
- post conversations new
- drift list teams by user
- get playbooks list
- drift
- drift delete gdpr data
- drift list conversational landing pages (clp)
- drift list teams
- drift create an account
- drift update a contact - externalid
- api
- drift fetch a conversation's transcript as a string
- put scim users
- drift unsubscribe contacts from emails
- post gdpr delete
- drift create a contact
- drift delete an account
- post accounts create
- drift fetch a conversation's messages
- drift list user objects
- conversational ai
- drift create a conversation
- chatbots
- get scim users
- drift update a user
- get users list
- drift get token information
- drift fetch a user object
- drift fetch gdpr data
- get contacts attributes
- drift list conversations
- post app uninstall
- get conversations id json transcript
- get attachments id data
- fetch a contact by drift id
- post contacts timeline
- drift delete a contact
- get contacts id
- get teams users id
- get accounts id
- drift list custom contact attributes
- get teams org
- update a contact - drift id
- drift list contacts by email
- drift post a timeline event to a contact - externalid
- get conversations id transcript
- get playbooks clp
- patch users update
- drift fetch an account
- patch accounts update
- drift list accounts
- drift fetch booked meetings
- live chat
- drift fetch a conversation's transcript as a json object
- post emails unsubscribe
- get conversations id
- post gdpr retrieve
- get conversations id messages
- post conversations id messages
- delete accounts id
- sales
- drift deprovision a user
- get users id
- drift list contacts by externalid
- drift trigger app uninstall
- marketing
- patch contacts id
- drift create a message
- patch contacts normalize
- drift fetch a conversation
- post contacts id
- drift list playbooks
- get contacts
- drift fetch a conversation's attachments
- post contacts
- get users meetings org
- drift list all users
- drift provision a user
- drift fetch a user
- get accounts
- get conversations list
- get scim users id
- post app token info
- get conversations stats
- post scim users
slug: drift-capability
source_filename: drift-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Drift\n  description: Drift is a cloud-based solution designed to help businesses automate sales processes by adding live chat windows\n    to websites for increased customer experience and loyalty. Key features include chatbots, geo-targeting, offline access,\n    proactive chating and transfers/routing.\n  tags:\n  - Drift\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: drift\n    baseUri: http://{{base_url}}\n    description: Drift HTTP API.\n    authentication:\n      type: bearer\n      token: '{{DRIFT_TOKEN}}'\n    resources:\n    - name: contacts\n      path: /contacts\n      operations:\n      - name: post-contacts\n        method: POST\n        description: Drift Create a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-contacts\n        method: GET\n   \
  \     description: Drift List contacts by externalId\n        inputParameters:\n        - name: idType\n          in: query\n          type: string\n        - name: id\n          in: query\n          type: string\n          description: Your unique externalId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-id\n      path: /contacts/{id}\n      operations:\n      - name: patch-contacts-id\n        method: PATCH\n        description: Update a contact - Drift Id\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Drift contactId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-contacts-id\n        method: GET\n        description: Fetch a contact by Drift Id\n        inputParameters:\n        - name: id\n  \
  \        in: path\n          type: string\n          required: true\n          description: Drift contactId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-contacts-id\n        method: POST\n        description: Drift Delete a contact\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-normalize\n      path: /contacts/normalize\n      operations:\n      - name: patch-contacts-normalize\n        method: PATCH\n        description: Drift Update a contact - ExternalId\n        inputParameters:\n        - name: idType\n          in: query\n          type: string\n          description: One of drift, external, internal\n        - name: id\n          in: query\n          type: string\n\
  \          description: Your unique externalId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /contacts/\n      operations:\n      - name: get-contacts\n        method: GET\n        description: Drift List contacts by email\n        inputParameters:\n        - name: email\n          in: query\n          type: string\n          description: The email address of the requested contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: emails-unsubscribe\n      path: /emails/unsubscribe\n      operations:\n      - name: post-emails-unsubscribe\n        method: POST\n        description: Drift Unsubscribe contacts from emails\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-timeline\n      path:\
  \ /contacts/timeline\n      operations:\n      - name: post-contacts-timeline\n        method: POST\n        description: Drift Post a timeline event to a contact - externalId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-attributes\n      path: /contacts/attributes\n      operations:\n      - name: get-contacts-attributes\n        method: GET\n        description: Drift List custom contact attributes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-id\n      path: /users/{id}\n      operations:\n      - name: get-users-id\n        method: GET\n        description: Drift Fetch a user\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n    - name: users-list\n      path: /users/list\n      operations:\n      - name: get-users-list\n        method: GET\n        description: Drift List all users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-update\n      path: /users/update\n      operations:\n      - name: patch-users-update\n        method: PATCH\n        description: Drift Update a user\n        inputParameters:\n        - name: userId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-meetings-org\n      path: /users/meetings/org\n      operations:\n      - name: get-users-meetings-org\n        method: GET\n        description: Drift Fetch booked meetings\n        inputParameters:\n        - name: min_start_time\n          in: query\n        \
  \  type: string\n        - name: max_start_time\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-id-messages\n      path: /conversations/{id}/messages\n      operations:\n      - name: post-conversations-id-messages\n        method: POST\n        description: Drift Create a message\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Drift conversationId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-conversations-id-messages\n        method: GET\n        description: Drift Fetch a conversation's messages\n        inputParameters:\n        - name: next\n          in: query\n          type: string\n          description: Page number where page sizes are\
  \ always 50\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Drift conversationId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-id\n      path: /conversations/{id}\n      operations:\n      - name: get-conversations-id\n        method: GET\n        description: Drift Fetch a conversation\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Drift conversationId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-id-transcript\n      path: /conversations/{id}/transcript\n      operations:\n      - name: get-conversations-id-transcript\n        method: GET\n        description: Drift Fetch a conversation's transcript as a string\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Drift conversationId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-id-json-transcript\n      path: /conversations/{id}/json_transcript\n      operations:\n      - name: get-conversations-id-json-transcript\n        method: GET\n        description: Drift Fetch a conversation's transcript as a JSON object\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Drift conversationId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: attachments-id-data\n      path: /attachments/{id}/data\n      operations:\n      - name: get-attachments-id-data\n        method: GET\n\
  \        description: Drift Fetch a conversation's attachments\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Drift documentId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-new\n      path: /conversations/new\n      operations:\n      - name: post-conversations-new\n        method: POST\n        description: Drift Create a conversation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-stats\n      path: /conversations/stats\n      operations:\n      - name: get-conversations-stats\n        method: GET\n        description: Drift List conversation statuses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: conversations-list\n      path: /conversations/list\n      operations:\n      - name: get-conversations-list\n        method: GET\n        description: Drift List conversations\n        inputParameters:\n        - name: limit\n          in: query\n          type: string\n          description: Max number of conversations to retrieve (max 100, default 25).\n        - name: statusId\n          in: query\n          type: string\n          description: 'Return only conversations that match the provided status code. Uses the following values: OPEN, CLOSED,\n            PENDING'\n        - name: page_token\n          in: query\n          type: string\n          description: Allows you to move to the next page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-create\n      path: /accounts/create\n      operations:\n      - name: post-accounts-create\n        method: POST\n        description:\
  \ Drift Create an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-id\n      path: /accounts/{id}\n      operations:\n      - name: get-accounts-id\n        method: GET\n        description: Drift Fetch an account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Drift accountId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-accounts-id\n        method: DELETE\n        description: Drift Delete an account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Drift accountId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ accounts\n      path: /accounts\n      operations:\n      - name: get-accounts\n        method: GET\n        description: Drift List accounts\n        inputParameters:\n        - name: index\n          in: query\n          type: string\n          description: Used as a starting index of the the accounts query in the authenticated Drift user's account\n        - name: size\n          in: query\n          type: string\n          description: Number of accounts per batch (default=10, max=65)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-update\n      path: /accounts/update\n      operations:\n      - name: patch-accounts-update\n        method: PATCH\n        description: Drift Update an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: playbooks-list\n      path: /playbooks/list\n      operations:\n\
  \      - name: get-playbooks-list\n        method: GET\n        description: Drift List playbooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: playbooks-clp\n      path: /playbooks/clp\n      operations:\n      - name: get-playbooks-clp\n        method: GET\n        description: Drift List conversational landing pages (CLP)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams-org\n      path: /teams/org\n      operations:\n      - name: get-teams-org\n        method: GET\n        description: Drift List teams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams-users-id\n      path: /teams/users/{id}\n      operations:\n      - name: get-teams-users-id\n        method: GET\n        description: Drift List teams\
  \ by user\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Drift userId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: app-uninstall\n      path: /app/uninstall\n      operations:\n      - name: post-app-uninstall\n        method: POST\n        description: Drift Trigger app uninstall\n        inputParameters:\n        - name: clientId\n          in: query\n          type: string\n        - name: clientSecret\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: app-token-info\n      path: /app/token_info\n      operations:\n      - name: post-app-token-info\n        method: POST\n        description: Drift Get token information\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: gdpr-retrieve\n      path: /gdpr/retrieve\n      operations:\n      - name: post-gdpr-retrieve\n        method: POST\n        description: Drift Fetch GDPR data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gdpr-delete\n      path: /gdpr/delete\n      operations:\n      - name: post-gdpr-delete\n        method: POST\n        description: Drift Delete GDPR data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scim-users\n      path: /scim/Users\n      operations:\n      - name: get-scim-users\n        method: GET\n        description: Drift List user objects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-scim-users\n        method:\
  \ POST\n        description: Drift Provision a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-scim-users\n        method: PUT\n        description: Drift Update a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-scim-users\n        method: DELETE\n        description: Drift Deprovision a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scim-users-id\n      path: /scim/Users/{id}\n      operations:\n      - name: get-scim-users-id\n        method: GET\n        description: Drift Fetch a user object\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Drift userId\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: drift-rest\n    description: REST adapter for Drift.\n    resources:\n    - path: /contacts\n      name: post-contacts\n      operations:\n      - method: POST\n        name: post-contacts\n        description: Drift Create a contact\n        call: drift.post-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: get-contacts\n      operations:\n      - method: GET\n        name: get-contacts\n        description: Drift List contacts by externalId\n        call: drift.get-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/{id}\n      name: patch-contacts-id\n      operations:\n      - method: PATCH\n        name: patch-contacts-id\n        description: Update a contact - Drift Id\n        call: drift.patch-contacts-id\n \
  \       with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/{id}\n      name: get-contacts-id\n      operations:\n      - method: GET\n        name: get-contacts-id\n        description: Fetch a contact by Drift Id\n        call: drift.get-contacts-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/{id}\n      name: post-contacts-id\n      operations:\n      - method: POST\n        name: post-contacts-id\n        description: Drift Delete a contact\n        call: drift.post-contacts-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/normalize\n      name: patch-contacts-normalize\n      operations:\n      - method: PATCH\n        name: patch-contacts-normalize\n        description: Drift Update a contact - ExternalId\n        call: drift.patch-contacts-normalize\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/\n      name: get-contacts\n      operations:\n      - method: GET\n        name: get-contacts\n        description: Drift List contacts by email\n        call: drift.get-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /emails/unsubscribe\n      name: post-emails-unsubscribe\n      operations:\n      - method: POST\n        name: post-emails-unsubscribe\n        description: Drift Unsubscribe contacts from emails\n        call: drift.post-emails-unsubscribe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/timeline\n      name: post-contacts-timeline\n      operations:\n      - method: POST\n        name: post-contacts-timeline\n        description: Drift Post a timeline event to a contact - externalId\n        call: drift.post-contacts-timeline\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /contacts/attributes\n      name: get-contacts-attributes\n      operations:\n      - method: GET\n        name: get-contacts-attributes\n        description: Drift List custom contact attributes\n        call: drift.get-contacts-attributes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}\n      name: get-users-id\n      operations:\n      - method: GET\n        name: get-users-id\n        description: Drift Fetch a user\n        call: drift.get-users-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/list\n      name: get-users-list\n      operations:\n      - method: GET\n        name: get-users-list\n        description: Drift List all users\n        call: drift.get-users-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/update\n      name: patch-users-update\n      operations:\n\
  \      - method: PATCH\n        name: patch-users-update\n        description: Drift Update a user\n        call: drift.patch-users-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/meetings/org\n      name: get-users-meetings-org\n      operations:\n      - method: GET\n        name: get-users-meetings-org\n        description: Drift Fetch booked meetings\n        call: drift.get-users-meetings-org\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{id}/messages\n      name: post-conversations-id-messages\n      operations:\n      - method: POST\n        name: post-conversations-id-messages\n        description: Drift Create a message\n        call: drift.post-conversations-id-messages\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{id}/messages\n      name: get-conversations-id-messages\n   \
  \   operations:\n      - method: GET\n        name: get-conversations-id-messages\n        description: Drift Fetch a conversation's messages\n        call: drift.get-conversations-id-messages\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{id}\n      name: get-conversations-id\n      operations:\n      - method: GET\n        name: get-conversations-id\n        description: Drift Fetch a conversation\n        call: drift.get-conversations-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{id}/transcript\n      name: get-conversations-id-transcript\n      operations:\n      - method: GET\n        name: get-conversations-id-transcript\n        description: Drift Fetch a conversation's transcript as a string\n        call: drift.get-conversations-id-transcript\n        with:\n          id: rest.id\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{id}/json_transcript\n      name: get-conversations-id-json-transcript\n      operations:\n      - method: GET\n        name: get-conversations-id-json-transcript\n        description: Drift Fetch a conversation's transcript as a JSON object\n        call: drift.get-conversations-id-json-transcript\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /attachments/{id}/data\n      name: get-attachments-id-data\n      operations:\n      - method: GET\n        name: get-attachments-id-data\n        description: Drift Fetch a conversation's attachments\n        call: drift.get-attachments-id-data\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/new\n      name: post-conversations-new\n      operations:\n      - method: POST\n        name:\
  \ post-conversations-new\n        description: Drift Create a conversation\n        call: drift.post-conversations-new\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/stats\n      name: get-conversations-stats\n      operations:\n      - method: GET\n        name: get-conversations-stats\n        description: Drift List conversation statuses\n        call: drift.get-conversations-stats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/list\n      name: get-conversations-list\n      operations:\n      - method: GET\n        name: get-conversations-list\n        description: Drift List conversations\n        call: drift.get-conversations-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/create\n      name: post-accounts-create\n      operations:\n      - method: POST\n        name: post-accounts-create\n        description: Drift Create\
  \ an account\n        call: drift.post-accounts-create\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{id}\n      name: get-accounts-id\n      operations:\n      - method: GET\n        name: get-accounts-id\n        description: Drift Fetch an account\n        call: drift.get-accounts-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{id}\n      name: delete-accounts-id\n      operations:\n      - method: DELETE\n        name: delete-accounts-id\n        description: Drift Delete an account\n        call: drift.delete-accounts-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts\n      name: get-accounts\n      operations:\n      - method: GET\n        name: get-accounts\n        description: Drift List accounts\n        call: drift.get-accounts\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /accounts/update\n      name: patch-accounts-update\n      operations:\n      - method: PATCH\n        name: patch-accounts-update\n        description: Drift Update an account\n        call: drift.patch-accounts-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /playbooks/list\n      name: get-playbooks-list\n      operations:\n      - method: GET\n        name: get-playbooks-list\n        description: Drift List playbooks\n        call: drift.get-playbooks-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /playbooks/clp\n      name: get-playbooks-clp\n      operations:\n      - method: GET\n        name: get-playbooks-clp\n        description: Drift List conversational landing pages (CLP)\n        call: drift.get-playbooks-clp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/org\n      name: get-teams-org\n\
  \      operations:\n      - method: GET\n        name: get-teams-org\n        description: Drift List teams\n        call: drift.get-teams-org\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/users/{id}\n      name: get-teams-users-id\n      operations:\n      - method: GET\n        name: get-teams-users-id\n        description: Drift List teams by user\n        call: drift.get-teams-users-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /app/uninstall\n      name: post-app-uninstall\n      operations:\n      - method: POST\n        name: post-app-uninstall\n        description: Drift Trigger app uninstall\n        call: drift.post-app-uninstall\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /app/token_info\n      name: post-app-token-info\n      operations:\n      - method: POST\n        name: post-app-token-info\n        description:\
  \ Drift Get token information\n        call: drift.post-app-token-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gdpr/retrieve\n      name: post-gdpr-retrieve\n      operations:\n      - method: POST\n        name: post-gdpr-retrieve\n        description: Drift Fetch GDPR data\n        call: drift.post-gdpr-retrieve\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gdpr/delete\n      name: post-gdpr-delete\n      operations:\n      - method: POST\n        name: post-gdpr-delete\n        description: Drift Delete GDPR data\n        call: drift.post-gdpr-delete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scim/Users\n      name: get-scim-users\n      operations:\n      - method: GET\n        name: get-scim-users\n        description: Drift List user objects\n        call: drift.get-scim-users\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /scim/Users\n      name: post-scim-users\n      operations:\n      - method: POST\n        name: post-scim-users\n        description: Drift Provision a user\n        call: drift.post-scim-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scim/Users\n      name: put-scim-users\n      operations:\n      - method: PUT\n        name: put-scim-users\n        description: Drift Update a user\n        call: drift.put-scim-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scim/Users\n      name: delete-scim-users\n      operations:\n      - method: DELETE\n        name: delete-scim-users\n        description: Drift Deprovision a user\n        call: drift.delete-scim-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scim/Users/{id}\n      name: get-scim-users-id\n      operations:\n      - method: GET\n        name: get-scim-users-id\n        description:\
  \ Drift Fetch a user object\n        call: drift.get-scim-users-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: drift-mcp\n    transport: http\n    description: MCP adapter for Drift for AI agent use.\n    tools:\n    - name: post-contacts\n      description: Drift Create a contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: drift.post-contacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contacts\n      description: Drift List contacts by externalId\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drift.get-contacts\n      with:\n        idType: tools.idType\n        id: tools.id\n      inputParameters:\n      - name: idType\n        type: string\n        description: idType\n      - name: id\n        type: string\n\
  \        description: Your unique externalId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patch-contacts-id\n      description: Update a contact - Drift Id\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: drift.patch-contacts-id\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: Drift contactId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contacts-id\n      description: Fetch a contact by Drift Id\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drift.get-contacts-id\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: Drift contactId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-contacts-id\n\
  \      description: Drift Delete a contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: drift.post-contacts-id\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patch-contacts-normalize\n      description: Drift Update a contact - ExternalId\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: drift.patch-contacts-normalize\n      with:\n        idType: tools.idType\n        id: tools.id\n      inputParameters:\n      - name: idType\n        type: string\n        description: One of drift, external, internal\n      - name: id\n        type: string\n        description: Your unique externalId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contacts\n      description:\
  \ Drift List contacts by email\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: drift.get-contacts\n      with:\n        email: tools.email\n      inputParameters:\n      - name: email\n        type: string\n        description: The email address of the requested contact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-emails-unsubscribe\n      description: Drift Unsubscribe contacts from emails\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: drift.post-emails-unsubscribe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-contacts-timeline\n      description: Drift Post a timeline event to a contact - externalId\n      hints:\n        readOnly: false\n    \n\n# --- truncated at 32 KB (44 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/drift/refs/heads/main/capabilities/drift-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/drift/refs/heads/main/capabilities/drift-capability.yaml
tags:
- Drift
- API
tools:
- description: Drift Create a contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-contacts
- description: Drift List contacts by externalId
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-contacts
- description: Update a contact - Drift Id
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-contacts-id
- description: Fetch a contact by Drift Id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-contacts-id
- description: Drift Delete a contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-contacts-id
- description: Drift Update a contact - ExternalId
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-contacts-normalize
- description: Drift List contacts by email
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-contacts
- description: Drift Unsubscribe contacts from emails
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-emails-unsubscribe
- description: Drift Post a timeline event to a contact - externalId
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-contacts-timeline
- description: Drift List custom contact attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-contacts-attributes
- description: Drift Fetch a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-users-id
- description: Drift List all users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-users-list
- description: Drift Update a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-users-update
- description: Drift Fetch booked meetings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-users-meetings-org
- description: Drift Create a message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-conversations-id-messages
- description: Drift Fetch a conversation's messages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-conversations-id-messages
- description: Drift Fetch a conversation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-conversations-id
- description: Drift Fetch a conversation's transcript as a string
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-conversations-id-transcript
- description: Drift Fetch a conversation's transcript as a JSON object
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-conversations-id-json-transcript
- description: Drift Fetch a conversation's attachments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-attachments-id-data
- description: Drift Create a conversation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-conversations-new
- description: Drift List conversation statuses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-conversations-stats
- description: Drift List conversations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-conversations-list
- description: Drift Create an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-accounts-create
- description: Drift Fetch an account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-accounts-id
- description: Drift Delete an account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-accounts-id
- description: Drift List accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-accounts
- description: Drift Update an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-accounts-update
- description: Drift List playbooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-playbooks-list
- description: Drift List conversational landing pages (CLP)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-playbooks-clp
- description: Drift List teams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-teams-org
- description: Drift List teams by user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-teams-users-id
- description: Drift Trigger app uninstall
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-app-uninstall
- description: Drift Get token information
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-app-token-info
- description: Drift Fetch GDPR data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-gdpr-retrieve
- description: Drift Delete GDPR data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-gdpr-delete
- description: Drift List user objects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-scim-users
- description: Drift Provision a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-scim-users
- description: Drift Update a user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-scim-users
- description: Drift Deprovision a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-scim-users
- description: Drift Fetch a user object
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-scim-users-id
---
