---
categories: []
consumed_apis: []
description: The Mailjet Email API enables sending transactional and marketing emails programmatically via JSON requests. The API also exposes resources for managing contacts, contact lists, segments, campaigns, templates, sender addresses, statistics, and event tracking. All requests use HTTP Basic authentication with an API key and secret pair issued from the Mailjet account dashboard.
layout: capability
name: Mailjet Email API
operations:
- description: Send transactional emails (v3.1)
  method: POST
  name: sendemail
  path: /send
- description: List contacts
  method: GET
  name: listcontacts
  path: /contact
- description: Create a contact
  method: POST
  name: createcontact
  path: /contact
- description: Get a contact
  method: GET
  name: getcontact
  path: /contact/{id}
- description: Update a contact
  method: PUT
  name: updatecontact
  path: /contact/{id}
- description: List contact lists
  method: GET
  name: listcontactslists
  path: /contactslist
- description: Create a contact list
  method: POST
  name: createcontactslist
  path: /contactslist
- description: Get a contact list
  method: GET
  name: getcontactslist
  path: /contactslist/{id}
- description: Delete a contact list
  method: DELETE
  name: deletecontactslist
  path: /contactslist/{id}
- description: Bulk add or remove contacts in a list
  method: POST
  name: managemanycontacts
  path: /contactslist/{id}/managemanycontacts
- description: List campaigns
  method: GET
  name: listcampaigns
  path: /campaign
- description: List campaign drafts
  method: GET
  name: listcampaigndrafts
  path: /campaigndraft
- description: Create a campaign draft
  method: POST
  name: createcampaigndraft
  path: /campaigndraft
- description: Send a campaign draft
  method: POST
  name: sendcampaigndraft
  path: /campaigndraft/{id}/send
- description: List templates
  method: GET
  name: listtemplates
  path: /template
- description: Create a template
  method: POST
  name: createtemplate
  path: /template
- description: List sender addresses
  method: GET
  name: listsenders
  path: /sender
- description: Create a sender address
  method: POST
  name: createsender
  path: /sender
- description: Get sending statistic counters
  method: GET
  name: getstatcounters
  path: /statcounters
- description: Get the event history of a message
  method: GET
  name: getmessagehistory
  path: /messagehistory/{id}
personas: []
provider_name: Mailjet
provider_slug: mailjet
search_terms:
- get sending statistic counters
- listcontacts
- list sender addresses
- email delivery
- deletecontactslist
- marketing email
- createcontact
- create a sender address
- api
- list templates
- list contact lists
- create a campaign draft
- listsenders
- listcontactslists
- getmessagehistory
- create a contact
- getcontact
- get the event history of a message
- mailjet
- updatecontact
- send transactional emails (v3.1)
- list campaigns
- update a contact
- managemanycontacts
- send a campaign draft
- transactional email
- createcampaigndraft
- list campaign drafts
- createsender
- email
- getcontactslist
- list contacts
- createcontactslist
- create a template
- get a contact list
- bulk add or remove contacts in a list
- createtemplate
- listcampaigns
- listtemplates
- getstatcounters
- listcampaigndrafts
- get a contact
- delete a contact list
- smtp
- sendcampaigndraft
- create a contact list
- sendemail
slug: mailjet-capability
source_filename: mailjet-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mailjet Email API\n  description: The Mailjet Email API enables sending transactional and marketing emails programmatically via JSON requests.\n    The API also exposes resources for managing contacts, contact lists, segments, campaigns, templates, sender addresses,\n    statistics, and event tracking. All requests use HTTP Basic authentication with an API key and secret pair issued from\n    the Mailjet account dashboard.\n  tags:\n  - Mailjet\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: mailjet\n    baseUri: https://api.mailjet.com/v3.1\n    description: Mailjet Email API HTTP API.\n    authentication:\n      type: basic\n      username: '{{MAILJET_USERNAME}}'\n      password: '{{MAILJET_PASSWORD}}'\n    resources:\n    - name: send\n      path: /send\n      operations:\n      - name: sendemail\n        method: POST\n        description: Send transactional emails\
  \ (v3.1)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contact\n      path: /contact\n      operations:\n      - name: listcontacts\n        method: GET\n        description: List contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontact\n        method: POST\n        description: Create a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contact-id\n      path: /contact/{id}\n      operations:\n      - name: getcontact\n        method: GET\n        description: Get a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecontact\n        method: PUT\n        description: Update a contact\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contactslist\n      path: /contactslist\n      operations:\n      - name: listcontactslists\n        method: GET\n        description: List contact lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontactslist\n        method: POST\n        description: Create a contact list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contactslist-id\n      path: /contactslist/{id}\n      operations:\n      - name: getcontactslist\n        method: GET\n        description: Get a contact list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontactslist\n        method: DELETE\n\
  \        description: Delete a contact list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contactslist-id-managemanycontacts\n      path: /contactslist/{id}/managemanycontacts\n      operations:\n      - name: managemanycontacts\n        method: POST\n        description: Bulk add or remove contacts in a list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaign\n      path: /campaign\n      operations:\n      - name: listcampaigns\n        method: GET\n        description: List campaigns\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigndraft\n      path: /campaigndraft\n      operations:\n      - name: listcampaigndrafts\n        method: GET\n        description: List campaign drafts\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcampaigndraft\n        method: POST\n        description: Create a campaign draft\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campaigndraft-id-send\n      path: /campaigndraft/{id}/send\n      operations:\n      - name: sendcampaigndraft\n        method: POST\n        description: Send a campaign draft\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: template\n      path: /template\n      operations:\n      - name: listtemplates\n        method: GET\n        description: List templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtemplate\n        method: POST\n        description:\
  \ Create a template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sender\n      path: /sender\n      operations:\n      - name: listsenders\n        method: GET\n        description: List sender addresses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsender\n        method: POST\n        description: Create a sender address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: statcounters\n      path: /statcounters\n      operations:\n      - name: getstatcounters\n        method: GET\n        description: Get sending statistic counters\n        inputParameters:\n        - name: SourceID\n          in: query\n          type: integer\n        - name: CounterSource\n          in: query\n          type: string\n\
  \        - name: CounterTiming\n          in: query\n          type: string\n        - name: CounterResolution\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messagehistory-id\n      path: /messagehistory/{id}\n      operations:\n      - name: getmessagehistory\n        method: GET\n        description: Get the event history of a message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mailjet-rest\n    description: REST adapter for Mailjet Email API.\n    resources:\n    - path: /send\n      name: sendemail\n      operations:\n      - method: POST\n        name: sendemail\n        description: Send transactional emails (v3.1)\n        call: mailjet.sendemail\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /contact\n      name: listcontacts\n      operations:\n      - method: GET\n        name: listcontacts\n        description: List contacts\n        call: mailjet.listcontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contact\n      name: createcontact\n      operations:\n      - method: POST\n        name: createcontact\n        description: Create a contact\n        call: mailjet.createcontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contact/{id}\n      name: getcontact\n      operations:\n      - method: GET\n        name: getcontact\n        description: Get a contact\n        call: mailjet.getcontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contact/{id}\n      name: updatecontact\n      operations:\n      - method: PUT\n        name: updatecontact\n        description: Update a contact\n        call: mailjet.updatecontact\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactslist\n      name: listcontactslists\n      operations:\n      - method: GET\n        name: listcontactslists\n        description: List contact lists\n        call: mailjet.listcontactslists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactslist\n      name: createcontactslist\n      operations:\n      - method: POST\n        name: createcontactslist\n        description: Create a contact list\n        call: mailjet.createcontactslist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactslist/{id}\n      name: getcontactslist\n      operations:\n      - method: GET\n        name: getcontactslist\n        description: Get a contact list\n        call: mailjet.getcontactslist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactslist/{id}\n      name: deletecontactslist\n\
  \      operations:\n      - method: DELETE\n        name: deletecontactslist\n        description: Delete a contact list\n        call: mailjet.deletecontactslist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactslist/{id}/managemanycontacts\n      name: managemanycontacts\n      operations:\n      - method: POST\n        name: managemanycontacts\n        description: Bulk add or remove contacts in a list\n        call: mailjet.managemanycontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campaign\n      name: listcampaigns\n      operations:\n      - method: GET\n        name: listcampaigns\n        description: List campaigns\n        call: mailjet.listcampaigns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campaigndraft\n      name: listcampaigndrafts\n      operations:\n      - method: GET\n        name: listcampaigndrafts\n        description: List campaign\
  \ drafts\n        call: mailjet.listcampaigndrafts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campaigndraft\n      name: createcampaigndraft\n      operations:\n      - method: POST\n        name: createcampaigndraft\n        description: Create a campaign draft\n        call: mailjet.createcampaigndraft\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campaigndraft/{id}/send\n      name: sendcampaigndraft\n      operations:\n      - method: POST\n        name: sendcampaigndraft\n        description: Send a campaign draft\n        call: mailjet.sendcampaigndraft\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /template\n      name: listtemplates\n      operations:\n      - method: GET\n        name: listtemplates\n        description: List templates\n        call: mailjet.listtemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /template\n      name: createtemplate\n      operations:\n      - method: POST\n        name: createtemplate\n        description: Create a template\n        call: mailjet.createtemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sender\n      name: listsenders\n      operations:\n      - method: GET\n        name: listsenders\n        description: List sender addresses\n        call: mailjet.listsenders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sender\n      name: createsender\n      operations:\n      - method: POST\n        name: createsender\n        description: Create a sender address\n        call: mailjet.createsender\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /statcounters\n      name: getstatcounters\n      operations:\n      - method: GET\n        name: getstatcounters\n        description: Get sending statistic counters\n        call:\
  \ mailjet.getstatcounters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /messagehistory/{id}\n      name: getmessagehistory\n      operations:\n      - method: GET\n        name: getmessagehistory\n        description: Get the event history of a message\n        call: mailjet.getmessagehistory\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mailjet-mcp\n    transport: http\n    description: MCP adapter for Mailjet Email API for AI agent use.\n    tools:\n    - name: sendemail\n      description: Send transactional emails (v3.1)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mailjet.sendemail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontacts\n      description: List contacts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n     \
  \ call: mailjet.listcontacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontact\n      description: Create a contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mailjet.createcontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontact\n      description: Get a contact\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mailjet.getcontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecontact\n      description: Update a contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mailjet.updatecontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontactslists\n      description: List contact lists\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: mailjet.listcontactslists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontactslist\n      description: Create a contact list\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mailjet.createcontactslist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontactslist\n      description: Get a contact list\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mailjet.getcontactslist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontactslist\n      description: Delete a contact list\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: mailjet.deletecontactslist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: managemanycontacts\n      description:\
  \ Bulk add or remove contacts in a list\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mailjet.managemanycontacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcampaigns\n      description: List campaigns\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mailjet.listcampaigns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcampaigndrafts\n      description: List campaign drafts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mailjet.listcampaigndrafts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcampaigndraft\n      description: Create a campaign draft\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mailjet.createcampaigndraft\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: sendcampaigndraft\n      description: Send a campaign draft\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mailjet.sendcampaigndraft\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtemplates\n      description: List templates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mailjet.listtemplates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtemplate\n      description: Create a template\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mailjet.createtemplate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsenders\n      description: List sender addresses\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n \
  \     call: mailjet.listsenders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsender\n      description: Create a sender address\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mailjet.createsender\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstatcounters\n      description: Get sending statistic counters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mailjet.getstatcounters\n      with:\n        SourceID: tools.SourceID\n        CounterSource: tools.CounterSource\n        CounterTiming: tools.CounterTiming\n        CounterResolution: tools.CounterResolution\n      inputParameters:\n      - name: SourceID\n        type: integer\n        description: SourceID\n      - name: CounterSource\n        type: string\n        description: CounterSource\n      - name: CounterTiming\n        type: string\n\
  \        description: CounterTiming\n      - name: CounterResolution\n        type: string\n        description: CounterResolution\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmessagehistory\n      description: Get the event history of a message\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mailjet.getmessagehistory\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MAILJET_USERNAME: MAILJET_USERNAME\n    MAILJET_PASSWORD: MAILJET_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mailjet/refs/heads/main/capabilities/mailjet-capability.yaml
tags:
- Mailjet
- API
tools:
- description: Send transactional emails (v3.1)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendemail
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
- description: Get a contact
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontact
- description: Update a contact
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecontact
- description: List contact lists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontactslists
- description: Create a contact list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontactslist
- description: Get a contact list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontactslist
- description: Delete a contact list
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontactslist
- description: Bulk add or remove contacts in a list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: managemanycontacts
- description: List campaigns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcampaigns
- description: List campaign drafts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcampaigndrafts
- description: Create a campaign draft
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcampaigndraft
- description: Send a campaign draft
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendcampaigndraft
- description: List templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtemplates
- description: Create a template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtemplate
- description: List sender addresses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsenders
- description: Create a sender address
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsender
- description: Get sending statistic counters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatcounters
- description: Get the event history of a message
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmessagehistory
---
