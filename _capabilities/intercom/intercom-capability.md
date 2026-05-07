---
categories: []
consumed_apis: []
description: The Intercom API provides programmatic access to the Intercom AI-powered customer service platform. It enables developers to manage contacts, companies, conversations, articles, segments, messages, and data events, and to build seamless integrations with the Intercom Help Desk and Messenger.
layout: capability
name: Intercom API
operations:
- description: Identify an admin
  method: GET
  name: getme
  path: /me
- description: List admins
  method: GET
  name: listadmins
  path: /admins
- description: List contacts
  method: GET
  name: listcontacts
  path: /contacts
- description: Create a contact
  method: POST
  name: createcontact
  path: /contacts
- description: Retrieve a contact
  method: GET
  name: getcontact
  path: /contacts/{contact_id}
- description: List companies
  method: GET
  name: listcompanies
  path: /companies
- description: Create or update a company
  method: POST
  name: createorupdatecompany
  path: /companies
- description: List conversations
  method: GET
  name: listconversations
  path: /conversations
- description: Create a conversation
  method: POST
  name: createconversation
  path: /conversations
- description: Retrieve a conversation
  method: GET
  name: getconversation
  path: /conversations/{conversation_id}
- description: List articles
  method: GET
  name: listarticles
  path: /articles
- description: Create an article
  method: POST
  name: createarticle
  path: /articles
- description: List segments
  method: GET
  name: listsegments
  path: /segments
- description: Create a message
  method: POST
  name: createmessage
  path: /messages
- description: Submit a data event
  method: POST
  name: submitevent
  path: /events
- description: List data events
  method: GET
  name: listevents
  path: /events
- description: List news items
  method: GET
  name: listnewsitems
  path: /news/news_items
- description: Create a news item
  method: POST
  name: createnewsitem
  path: /news/news_items
personas: []
provider_name: Intercom
provider_slug: intercom
search_terms:
- listcontacts
- listarticles
- intercom
- customer support
- createcontact
- ai
- api
- listnewsitems
- create or update a company
- create a contact
- getcontact
- submitevent
- list admins
- create a news item
- createarticle
- create a message
- listadmins
- getme
- list conversations
- identify an admin
- create a conversation
- listcompanies
- list contacts
- list news items
- list articles
- createnewsitem
- getconversation
- submit a data event
- createmessage
- listevents
- list segments
- retrieve a contact
- createorupdatecompany
- retrieve a conversation
- createconversation
- customer service
- list data events
- list companies
- messaging
- create an article
- listsegments
- listconversations
slug: intercom-capability
source_filename: intercom-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Intercom API\n  description: The Intercom API provides programmatic access to the Intercom AI-powered customer service platform. It enables\n    developers to manage contacts, companies, conversations, articles, segments, messages, and data events, and to build seamless\n    integrations with the Intercom Help Desk and Messenger.\n  tags:\n  - Intercom\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: intercom\n    baseUri: https://api.intercom.io\n    description: Intercom API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{INTERCOM_TOKEN}}'\n    resources:\n    - name: me\n      path: /me\n      operations:\n      - name: getme\n        method: GET\n        description: Identify an admin\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admins\n      path: /admins\n\
  \      operations:\n      - name: listadmins\n        method: GET\n        description: List admins\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /contacts\n      operations:\n      - name: listcontacts\n        method: GET\n        description: List contacts\n        inputParameters:\n        - name: per_page\n          in: query\n          type: integer\n        - name: starting_after\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontact\n        method: POST\n        description: Create a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-contact-id\n      path: /contacts/{contact_id}\n      operations:\n      - name: getcontact\n\
  \        method: GET\n        description: Retrieve a contact\n        inputParameters:\n        - name: contact_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies\n      path: /companies\n      operations:\n      - name: listcompanies\n        method: GET\n        description: List companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorupdatecompany\n        method: POST\n        description: Create or update a company\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations\n      path: /conversations\n      operations:\n      - name: listconversations\n        method: GET\n        description: List conversations\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createconversation\n        method: POST\n        description: Create a conversation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-conversation-id\n      path: /conversations/{conversation_id}\n      operations:\n      - name: getconversation\n        method: GET\n        description: Retrieve a conversation\n        inputParameters:\n        - name: conversation_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: articles\n      path: /articles\n      operations:\n      - name: listarticles\n        method: GET\n        description: List articles\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createarticle\n        method: POST\n        description: Create an article\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: segments\n      path: /segments\n      operations:\n      - name: listsegments\n        method: GET\n        description: List segments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages\n      path: /messages\n      operations:\n      - name: createmessage\n        method: POST\n        description: Create a message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      operations:\n      - name: submitevent\n        method: POST\n        description: Submit\
  \ a data event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listevents\n        method: GET\n        description: List data events\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n        - name: user_id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: news-news-items\n      path: /news/news_items\n      operations:\n      - name: listnewsitems\n        method: GET\n        description: List news items\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnewsitem\n        method: POST\n        description: Create a news item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: intercom-rest\n    description: REST adapter for Intercom API.\n    resources:\n    - path: /me\n      name: getme\n      operations:\n      - method: GET\n        name: getme\n        description: Identify an admin\n        call: intercom.getme\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admins\n      name: listadmins\n      operations:\n      - method: GET\n        name: listadmins\n        description: List admins\n        call: intercom.listadmins\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: listcontacts\n      operations:\n      - method: GET\n        name: listcontacts\n        description: List contacts\n        call: intercom.listcontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: createcontact\n      operations:\n \
  \     - method: POST\n        name: createcontact\n        description: Create a contact\n        call: intercom.createcontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/{contact_id}\n      name: getcontact\n      operations:\n      - method: GET\n        name: getcontact\n        description: Retrieve a contact\n        call: intercom.getcontact\n        with:\n          contact_id: rest.contact_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies\n      name: listcompanies\n      operations:\n      - method: GET\n        name: listcompanies\n        description: List companies\n        call: intercom.listcompanies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies\n      name: createorupdatecompany\n      operations:\n      - method: POST\n        name: createorupdatecompany\n        description: Create or update a company\n        call:\
  \ intercom.createorupdatecompany\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations\n      name: listconversations\n      operations:\n      - method: GET\n        name: listconversations\n        description: List conversations\n        call: intercom.listconversations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations\n      name: createconversation\n      operations:\n      - method: POST\n        name: createconversation\n        description: Create a conversation\n        call: intercom.createconversation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{conversation_id}\n      name: getconversation\n      operations:\n      - method: GET\n        name: getconversation\n        description: Retrieve a conversation\n        call: intercom.getconversation\n        with:\n          conversation_id: rest.conversation_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /articles\n      name: listarticles\n      operations:\n      - method: GET\n        name: listarticles\n        description: List articles\n        call: intercom.listarticles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /articles\n      name: createarticle\n      operations:\n      - method: POST\n        name: createarticle\n        description: Create an article\n        call: intercom.createarticle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /segments\n      name: listsegments\n      operations:\n      - method: GET\n        name: listsegments\n        description: List segments\n        call: intercom.listsegments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /messages\n      name: createmessage\n      operations:\n      - method: POST\n        name: createmessage\n        description: Create a message\n\
  \        call: intercom.createmessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events\n      name: submitevent\n      operations:\n      - method: POST\n        name: submitevent\n        description: Submit a data event\n        call: intercom.submitevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events\n      name: listevents\n      operations:\n      - method: GET\n        name: listevents\n        description: List data events\n        call: intercom.listevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /news/news_items\n      name: listnewsitems\n      operations:\n      - method: GET\n        name: listnewsitems\n        description: List news items\n        call: intercom.listnewsitems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /news/news_items\n      name: createnewsitem\n      operations:\n      - method:\
  \ POST\n        name: createnewsitem\n        description: Create a news item\n        call: intercom.createnewsitem\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: intercom-mcp\n    transport: http\n    description: MCP adapter for Intercom API for AI agent use.\n    tools:\n    - name: getme\n      description: Identify an admin\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercom.getme\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listadmins\n      description: List admins\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercom.listadmins\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontacts\n      description: List contacts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n   \
  \   call: intercom.listcontacts\n      with:\n        per_page: tools.per_page\n        starting_after: tools.starting_after\n      inputParameters:\n      - name: per_page\n        type: integer\n        description: per_page\n      - name: starting_after\n        type: string\n        description: starting_after\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontact\n      description: Create a contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intercom.createcontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontact\n      description: Retrieve a contact\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercom.getcontact\n      with:\n        contact_id: tools.contact_id\n      inputParameters:\n      - name: contact_id\n        type: string\n        description: contact_id\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcompanies\n      description: List companies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercom.listcompanies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorupdatecompany\n      description: Create or update a company\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intercom.createorupdatecompany\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listconversations\n      description: List conversations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercom.listconversations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createconversation\n      description: Create a conversation\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: intercom.createconversation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconversation\n      description: Retrieve a conversation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercom.getconversation\n      with:\n        conversation_id: tools.conversation_id\n      inputParameters:\n      - name: conversation_id\n        type: string\n        description: conversation_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listarticles\n      description: List articles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercom.listarticles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createarticle\n      description: Create an article\n      hints:\n        readOnly: false\n    \
  \    destructive: false\n        idempotent: false\n      call: intercom.createarticle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsegments\n      description: List segments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercom.listsegments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmessage\n      description: Create a message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intercom.createmessage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitevent\n      description: Submit a data event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intercom.submitevent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listevents\n      description: List data events\n    \
  \  hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercom.listevents\n      with:\n        type: tools.type\n        user_id: tools.user_id\n      inputParameters:\n      - name: type\n        type: string\n        description: type\n      - name: user_id\n        type: string\n        description: user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnewsitems\n      description: List news items\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intercom.listnewsitems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnewsitem\n      description: Create a news item\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intercom.createnewsitem\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    INTERCOM_TOKEN:\
  \ INTERCOM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/intercom/refs/heads/main/capabilities/intercom-capability.yaml
tags:
- Intercom
- API
tools:
- description: Identify an admin
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getme
- description: List admins
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadmins
- description: List contacts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontacts
- description: Create a contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontact
- description: Retrieve a contact
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontact
- description: List companies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcompanies
- description: Create or update a company
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorupdatecompany
- description: List conversations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconversations
- description: Create a conversation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconversation
- description: Retrieve a conversation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconversation
- description: List articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listarticles
- description: Create an article
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createarticle
- description: List segments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsegments
- description: Create a message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmessage
- description: Submit a data event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitevent
- description: List data events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevents
- description: List news items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnewsitems
- description: Create a news item
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnewsitem
---
