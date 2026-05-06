---
categories: []
consumed_apis: []
description: The Brevo Contacts API provides programmatic access to contact management features including creating, updating, and deleting contacts. Developers can organize contacts into lists, apply attributes and tags, import contacts in bulk, and build audience segments for targeted campaigns. The API also supports managing folders, contact attributes, and custom fields to structure contact data according to business needs.
layout: capability
name: Brevo Contacts API
operations:
- description: Get all contacts
  method: GET
  name: listcontacts
  path: /contacts
- description: Create a contact
  method: POST
  name: createcontact
  path: /contacts
- description: Get a contact's details
  method: GET
  name: getcontactinfo
  path: /contacts/{identifier}
- description: Update a contact
  method: PUT
  name: updatecontact
  path: /contacts/{identifier}
- description: Delete a contact
  method: DELETE
  name: deletecontact
  path: /contacts/{identifier}
- description: Get all contact lists
  method: GET
  name: listcontactlists
  path: /contacts/lists
- description: Create a contact list
  method: POST
  name: createcontactlist
  path: /contacts/lists
- description: Get a contact list
  method: GET
  name: getcontactlist
  path: /contacts/lists/{listId}
- description: Update a contact list
  method: PUT
  name: updatecontactlist
  path: /contacts/lists/{listId}
- description: Delete a contact list
  method: DELETE
  name: deletecontactlist
  path: /contacts/lists/{listId}
- description: Add contacts to a list
  method: POST
  name: addcontactstolist
  path: /contacts/lists/{listId}/contacts/add
- description: Remove contacts from a list
  method: POST
  name: removecontactsfromlist
  path: /contacts/lists/{listId}/contacts/remove
- description: List all contact attributes
  method: GET
  name: listcontactattributes
  path: /contacts/attributes
- description: Create a contact attribute
  method: POST
  name: createcontactattribute
  path: /contacts/attributes/{attributeCategory}/{attributeName}
- description: Delete a contact attribute
  method: DELETE
  name: deletecontactattribute
  path: /contacts/attributes/{attributeCategory}/{attributeName}
- description: Get all folders
  method: GET
  name: listfolders
  path: /contacts/folders
- description: Create a folder
  method: POST
  name: createfolder
  path: /contacts/folders
- description: Import contacts
  method: POST
  name: importcontacts
  path: /contacts/import
personas: []
provider_name: brevo
provider_slug: brevo
search_terms:
- get all contacts
- create a contact attribute
- get all folders
- add contacts to a list
- delete a contact attribute
- listcontacts
- get all contact lists
- updatecontactlist
- deletecontactattribute
- createfolder
- listfolders
- listcontactlists
- removecontactsfromlist
- list all contact attributes
- createcontactattribute
- updatecontact
- create a contact
- createcontactlist
- update a contact list
- delete a contact list
- createcontact
- importcontacts
- listcontactattributes
- update a contact
- api
- getcontactinfo
- getcontactlist
- brevo
- create a contact list
- addcontactstolist
- delete a contact
- get a contact's details
- create a folder
- import contacts
- get a contact list
- remove contacts from a list
- deletecontact
- deletecontactlist
slug: brevo-capability
source_filename: brevo-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Brevo Contacts API\n  description: The Brevo Contacts API provides programmatic access to contact management features including creating, updating,\n    and deleting contacts. Developers can organize contacts into lists, apply attributes and tags, import contacts in bulk,\n    and build audience segments for targeted campaigns. The API also supports managing folders, contact attributes, and custom\n    fields to structure contact data according to business needs.\n  tags:\n  - Brevo\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: brevo\n    baseUri: https://api.brevo.com/v3\n    description: Brevo Contacts API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: api-key\n      value: '{{BREVO_TOKEN}}'\n    resources:\n    - name: contacts\n      path: /contacts\n      operations:\n      - name: listcontacts\n        method: GET\n        description:\
  \ Get all contacts\n        inputParameters:\n        - name: modifiedSince\n          in: query\n          type: string\n          description: Filter contacts modified since this date-time in ISO 8601 format.\n        - name: sort\n          in: query\n          type: string\n          description: Sort direction for the results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontact\n        method: POST\n        description: Create a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-identifier\n      path: /contacts/{identifier}\n      operations:\n      - name: getcontactinfo\n        method: GET\n        description: Get a contact's details\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          description: Start date for\
  \ retrieving contact statistics.\n        - name: endDate\n          in: query\n          type: string\n          description: End date for retrieving contact statistics.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecontact\n        method: PUT\n        description: Update a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontact\n        method: DELETE\n        description: Delete a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-lists\n      path: /contacts/lists\n      operations:\n      - name: listcontactlists\n        method: GET\n        description: Get all contact lists\n        inputParameters:\n        - name: sort\n          in: query\n          type: string\n\
  \          description: Sort direction for the results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontactlist\n        method: POST\n        description: Create a contact list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-lists-listid\n      path: /contacts/lists/{listId}\n      operations:\n      - name: getcontactlist\n        method: GET\n        description: Get a contact list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecontactlist\n        method: PUT\n        description: Update a contact list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontactlist\n        method: DELETE\n\
  \        description: Delete a contact list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-lists-listid-contacts-add\n      path: /contacts/lists/{listId}/contacts/add\n      operations:\n      - name: addcontactstolist\n        method: POST\n        description: Add contacts to a list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-lists-listid-contacts-remove\n      path: /contacts/lists/{listId}/contacts/remove\n      operations:\n      - name: removecontactsfromlist\n        method: POST\n        description: Remove contacts from a list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-attributes\n      path: /contacts/attributes\n      operations:\n      - name: listcontactattributes\n\
  \        method: GET\n        description: List all contact attributes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-attributes-attributecategory-attributen\n      path: /contacts/attributes/{attributeCategory}/{attributeName}\n      operations:\n      - name: createcontactattribute\n        method: POST\n        description: Create a contact attribute\n        inputParameters:\n        - name: attributeCategory\n          in: path\n          type: string\n          required: true\n          description: Category of the attribute such as normal, transactional, category, calculated, or global.\n        - name: attributeName\n          in: path\n          type: string\n          required: true\n          description: Name for the new attribute.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontactattribute\n\
  \        method: DELETE\n        description: Delete a contact attribute\n        inputParameters:\n        - name: attributeCategory\n          in: path\n          type: string\n          required: true\n          description: Category of the attribute to delete.\n        - name: attributeName\n          in: path\n          type: string\n          required: true\n          description: Name of the attribute to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-folders\n      path: /contacts/folders\n      operations:\n      - name: listfolders\n        method: GET\n        description: Get all folders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfolder\n        method: POST\n        description: Create a folder\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: contacts-import\n      path: /contacts/import\n      operations:\n      - name: importcontacts\n        method: POST\n        description: Import contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: brevo-rest\n    description: REST adapter for Brevo Contacts API.\n    resources:\n    - path: /contacts\n      name: listcontacts\n      operations:\n      - method: GET\n        name: listcontacts\n        description: Get all contacts\n        call: brevo.listcontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: createcontact\n      operations:\n      - method: POST\n        name: createcontact\n        description: Create a contact\n        call: brevo.createcontact\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /contacts/{identifier}\n      name: getcontactinfo\n      operations:\n      - method: GET\n        name: getcontactinfo\n        description: Get a contact's details\n        call: brevo.getcontactinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/{identifier}\n      name: updatecontact\n      operations:\n      - method: PUT\n        name: updatecontact\n        description: Update a contact\n        call: brevo.updatecontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/{identifier}\n      name: deletecontact\n      operations:\n      - method: DELETE\n        name: deletecontact\n        description: Delete a contact\n        call: brevo.deletecontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/lists\n      name: listcontactlists\n      operations:\n      - method: GET\n        name: listcontactlists\n\
  \        description: Get all contact lists\n        call: brevo.listcontactlists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/lists\n      name: createcontactlist\n      operations:\n      - method: POST\n        name: createcontactlist\n        description: Create a contact list\n        call: brevo.createcontactlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/lists/{listId}\n      name: getcontactlist\n      operations:\n      - method: GET\n        name: getcontactlist\n        description: Get a contact list\n        call: brevo.getcontactlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/lists/{listId}\n      name: updatecontactlist\n      operations:\n      - method: PUT\n        name: updatecontactlist\n        description: Update a contact list\n        call: brevo.updatecontactlist\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /contacts/lists/{listId}\n      name: deletecontactlist\n      operations:\n      - method: DELETE\n        name: deletecontactlist\n        description: Delete a contact list\n        call: brevo.deletecontactlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/lists/{listId}/contacts/add\n      name: addcontactstolist\n      operations:\n      - method: POST\n        name: addcontactstolist\n        description: Add contacts to a list\n        call: brevo.addcontactstolist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/lists/{listId}/contacts/remove\n      name: removecontactsfromlist\n      operations:\n      - method: POST\n        name: removecontactsfromlist\n        description: Remove contacts from a list\n        call: brevo.removecontactsfromlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/attributes\n\
  \      name: listcontactattributes\n      operations:\n      - method: GET\n        name: listcontactattributes\n        description: List all contact attributes\n        call: brevo.listcontactattributes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/attributes/{attributeCategory}/{attributeName}\n      name: createcontactattribute\n      operations:\n      - method: POST\n        name: createcontactattribute\n        description: Create a contact attribute\n        call: brevo.createcontactattribute\n        with:\n          attributeCategory: rest.attributeCategory\n          attributeName: rest.attributeName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/attributes/{attributeCategory}/{attributeName}\n      name: deletecontactattribute\n      operations:\n      - method: DELETE\n        name: deletecontactattribute\n        description: Delete a contact attribute\n        call: brevo.deletecontactattribute\n\
  \        with:\n          attributeCategory: rest.attributeCategory\n          attributeName: rest.attributeName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/folders\n      name: listfolders\n      operations:\n      - method: GET\n        name: listfolders\n        description: Get all folders\n        call: brevo.listfolders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/folders\n      name: createfolder\n      operations:\n      - method: POST\n        name: createfolder\n        description: Create a folder\n        call: brevo.createfolder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/import\n      name: importcontacts\n      operations:\n      - method: POST\n        name: importcontacts\n        description: Import contacts\n        call: brevo.importcontacts\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9090\n    namespace: brevo-mcp\n    transport: http\n    description: MCP adapter for Brevo Contacts API for AI agent use.\n    tools:\n    - name: listcontacts\n      description: Get all contacts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: brevo.listcontacts\n      with:\n        modifiedSince: tools.modifiedSince\n        sort: tools.sort\n      inputParameters:\n      - name: modifiedSince\n        type: string\n        description: Filter contacts modified since this date-time in ISO 8601 format.\n      - name: sort\n        type: string\n        description: Sort direction for the results.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontact\n      description: Create a contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: brevo.createcontact\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getcontactinfo\n      description: Get a contact's details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: brevo.getcontactinfo\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n      inputParameters:\n      - name: startDate\n        type: string\n        description: Start date for retrieving contact statistics.\n      - name: endDate\n        type: string\n        description: End date for retrieving contact statistics.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecontact\n      description: Update a contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: brevo.updatecontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontact\n      description: Delete a contact\n      hints:\n        readOnly: false\n        destructive:\
  \ true\n        idempotent: true\n      call: brevo.deletecontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontactlists\n      description: Get all contact lists\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: brevo.listcontactlists\n      with:\n        sort: tools.sort\n      inputParameters:\n      - name: sort\n        type: string\n        description: Sort direction for the results.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontactlist\n      description: Create a contact list\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: brevo.createcontactlist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontactlist\n      description: Get a contact list\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ brevo.getcontactlist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecontactlist\n      description: Update a contact list\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: brevo.updatecontactlist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontactlist\n      description: Delete a contact list\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: brevo.deletecontactlist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addcontactstolist\n      description: Add contacts to a list\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: brevo.addcontactstolist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removecontactsfromlist\n      description: Remove contacts from a list\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: brevo.removecontactsfromlist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontactattributes\n      description: List all contact attributes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: brevo.listcontactattributes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontactattribute\n      description: Create a contact attribute\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: brevo.createcontactattribute\n      with:\n        attributeCategory: tools.attributeCategory\n        attributeName: tools.attributeName\n      inputParameters:\n      - name: attributeCategory\n        type: string\n        description: Category of the attribute such as normal, transactional, category, calculated, or global.\n     \
  \   required: true\n      - name: attributeName\n        type: string\n        description: Name for the new attribute.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontactattribute\n      description: Delete a contact attribute\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: brevo.deletecontactattribute\n      with:\n        attributeCategory: tools.attributeCategory\n        attributeName: tools.attributeName\n      inputParameters:\n      - name: attributeCategory\n        type: string\n        description: Category of the attribute to delete.\n        required: true\n      - name: attributeName\n        type: string\n        description: Name of the attribute to delete.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfolders\n      description: Get all folders\n      hints:\n        readOnly: true\n \
  \       destructive: false\n        idempotent: true\n      call: brevo.listfolders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createfolder\n      description: Create a folder\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: brevo.createfolder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: importcontacts\n      description: Import contacts\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: brevo.importcontacts\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BREVO_TOKEN: BREVO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/brevo/refs/heads/main/capabilities/brevo-capability.yaml
tags:
- Brevo
- API
tools:
- description: Get all contacts
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
- description: Get a contact's details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontactinfo
- description: Update a contact
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecontact
- description: Delete a contact
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontact
- description: Get all contact lists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontactlists
- description: Create a contact list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontactlist
- description: Get a contact list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontactlist
- description: Update a contact list
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecontactlist
- description: Delete a contact list
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontactlist
- description: Add contacts to a list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addcontactstolist
- description: Remove contacts from a list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: removecontactsfromlist
- description: List all contact attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontactattributes
- description: Create a contact attribute
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontactattribute
- description: Delete a contact attribute
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontactattribute
- description: Get all folders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfolders
- description: Create a folder
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfolder
- description: Import contacts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: importcontacts
---
