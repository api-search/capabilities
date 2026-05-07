---
categories: []
consumed_apis: []
description: The Google People API provides access to information about profiles and contacts. It allows you to list, create, update, delete, and search contacts, as well as manage contact groups. It replaces the legacy Google Contacts API.
layout: capability
name: Google People API (Contacts)
operations:
- description: Get a person
  method: GET
  name: getperson
  path: /people/{resourceName}
- description: List contacts
  method: GET
  name: listconnections
  path: /people/{resourceName}/connections
- description: Create a contact
  method: POST
  name: createcontact
  path: /people:createContact
- description: Update a contact
  method: PATCH
  name: updatecontact
  path: /people/{resourceName}:updateContact
- description: Delete a contact
  method: DELETE
  name: deletecontact
  path: /people/{resourceName}:deleteContact
- description: Search contacts
  method: GET
  name: searchcontacts
  path: /people:searchContacts
- description: List contact groups
  method: GET
  name: listcontactgroups
  path: /contactGroups
- description: Create a contact group
  method: POST
  name: createcontactgroup
  path: /contactGroups
- description: Get a contact group
  method: GET
  name: getcontactgroup
  path: /contactGroups/{resourceName}
- description: Update a contact group
  method: PUT
  name: updatecontactgroup
  path: /contactGroups/{resourceName}
- description: Delete a contact group
  method: DELETE
  name: deletecontactgroup
  path: /contactGroups/{resourceName}
personas: []
provider_name: Google People API
provider_slug: google-contacts
search_terms:
- deletecontact
- updatecontactgroup
- deletecontactgroup
- createcontact
- api
- profiles
- create a contact group
- delete a contact group
- address book
- get a contact group
- directory
- create a contact
- google
- updatecontact
- listcontactgroups
- contacts
- update a contact
- getperson
- update a contact group
- list contact groups
- createcontactgroup
- list contacts
- people
- delete a contact
- get a person
- search contacts
- listconnections
- searchcontacts
- getcontactgroup
slug: google-contacts-capability
source_filename: google-contacts-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google People API (Contacts)\n  description: The Google People API provides access to information about profiles and contacts. It allows you to list, create,\n    update, delete, and search contacts, as well as manage contact groups. It replaces the legacy Google Contacts API.\n  tags:\n  - Google\n  - Contacts\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-contacts\n    baseUri: https://people.googleapis.com/v1\n    description: Google People API (Contacts) HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CONTACTS_TOKEN}}'\n    resources:\n    - name: people-resourcename\n      path: /people/{resourceName}\n      operations:\n      - name: getperson\n        method: GET\n        description: Get a person\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n  \
  \        description: The resource name of the person to provide information about.\n        - name: personFields\n          in: query\n          type: string\n          description: A field mask to restrict which fields on the person are returned.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-resourcename-connections\n      path: /people/{resourceName}/connections\n      operations:\n      - name: listconnections\n        method: GET\n        description: List contacts\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n        - name: personFields\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: sortOrder\n          in: query\n          type: string\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-createcontact\n      path: /people:createContact\n      operations:\n      - name: createcontact\n        method: POST\n        description: Create a contact\n        inputParameters:\n        - name: personFields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-resourcename-updatecontact\n      path: /people/{resourceName}:updateContact\n      operations:\n      - name: updatecontact\n        method: PATCH\n        description: Update a contact\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n        - name: updatePersonFields\n          in: query\n          type: string\n        - name: personFields\n          in: query\n     \
  \     type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-resourcename-deletecontact\n      path: /people/{resourceName}:deleteContact\n      operations:\n      - name: deletecontact\n        method: DELETE\n        description: Delete a contact\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-searchcontacts\n      path: /people:searchContacts\n      operations:\n      - name: searchcontacts\n        method: GET\n        description: Search contacts\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n        - name: readMask\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n\
  \          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contactgroups\n      path: /contactGroups\n      operations:\n      - name: listcontactgroups\n        method: GET\n        description: List contact groups\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontactgroup\n        method: POST\n        description: Create a contact group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contactgroups-resourcename\n      path: /contactGroups/{resourceName}\n      operations:\n      - name: getcontactgroup\n        method: GET\n\
  \        description: Get a contact group\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n        - name: maxMembers\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecontactgroup\n        method: PUT\n        description: Update a contact group\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontactgroup\n        method: DELETE\n        description: Delete a contact group\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n        - name: deleteContacts\n          in: query\n\
  \          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-contacts-rest\n    description: REST adapter for Google People API (Contacts).\n    resources:\n    - path: /people/{resourceName}\n      name: getperson\n      operations:\n      - method: GET\n        name: getperson\n        description: Get a person\n        call: google-contacts.getperson\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people/{resourceName}/connections\n      name: listconnections\n      operations:\n      - method: GET\n        name: listconnections\n        description: List contacts\n        call: google-contacts.listconnections\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /people:createContact\n      name: createcontact\n      operations:\n      - method: POST\n        name: createcontact\n        description: Create a contact\n        call: google-contacts.createcontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people/{resourceName}:updateContact\n      name: updatecontact\n      operations:\n      - method: PATCH\n        name: updatecontact\n        description: Update a contact\n        call: google-contacts.updatecontact\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people/{resourceName}:deleteContact\n      name: deletecontact\n      operations:\n      - method: DELETE\n        name: deletecontact\n        description: Delete a contact\n        call: google-contacts.deletecontact\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /people:searchContacts\n      name: searchcontacts\n      operations:\n      - method: GET\n        name: searchcontacts\n        description: Search contacts\n        call: google-contacts.searchcontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactGroups\n      name: listcontactgroups\n      operations:\n      - method: GET\n        name: listcontactgroups\n        description: List contact groups\n        call: google-contacts.listcontactgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactGroups\n      name: createcontactgroup\n      operations:\n      - method: POST\n        name: createcontactgroup\n        description: Create a contact group\n        call: google-contacts.createcontactgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactGroups/{resourceName}\n      name: getcontactgroup\n      operations:\n\
  \      - method: GET\n        name: getcontactgroup\n        description: Get a contact group\n        call: google-contacts.getcontactgroup\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactGroups/{resourceName}\n      name: updatecontactgroup\n      operations:\n      - method: PUT\n        name: updatecontactgroup\n        description: Update a contact group\n        call: google-contacts.updatecontactgroup\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactGroups/{resourceName}\n      name: deletecontactgroup\n      operations:\n      - method: DELETE\n        name: deletecontactgroup\n        description: Delete a contact group\n        call: google-contacts.deletecontactgroup\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-contacts-mcp\n    transport: http\n    description: MCP adapter for Google People API (Contacts) for AI agent use.\n    tools:\n    - name: getperson\n      description: Get a person\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-contacts.getperson\n      with:\n        resourceName: tools.resourceName\n        personFields: tools.personFields\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: The resource name of the person to provide information about.\n        required: true\n      - name: personFields\n        type: string\n        description: A field mask to restrict which fields on the person are returned.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listconnections\n      description: List contacts\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: google-contacts.listconnections\n      with:\n        resourceName: tools.resourceName\n        personFields: tools.personFields\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        sortOrder: tools.sortOrder\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: resourceName\n        required: true\n      - name: personFields\n        type: string\n        description: personFields\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: sortOrder\n        type: string\n        description: sortOrder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontact\n      description: Create a contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-contacts.createcontact\n \
  \     with:\n        personFields: tools.personFields\n      inputParameters:\n      - name: personFields\n        type: string\n        description: personFields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecontact\n      description: Update a contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-contacts.updatecontact\n      with:\n        resourceName: tools.resourceName\n        updatePersonFields: tools.updatePersonFields\n        personFields: tools.personFields\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: resourceName\n        required: true\n      - name: updatePersonFields\n        type: string\n        description: updatePersonFields\n      - name: personFields\n        type: string\n        description: personFields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontact\n     \
  \ description: Delete a contact\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-contacts.deletecontact\n      with:\n        resourceName: tools.resourceName\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: resourceName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcontacts\n      description: Search contacts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-contacts.searchcontacts\n      with:\n        query: tools.query\n        readMask: tools.readMask\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: query\n        type: string\n        description: query\n      - name: readMask\n        type: string\n        description: readMask\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listcontactgroups\n      description: List contact groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-contacts.listcontactgroups\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontactgroup\n      description: Create a contact group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-contacts.createcontactgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontactgroup\n      description: Get a contact group\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: google-contacts.getcontactgroup\n      with:\n        resourceName: tools.resourceName\n        maxMembers: tools.maxMembers\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: resourceName\n        required: true\n      - name: maxMembers\n        type: integer\n        description: maxMembers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecontactgroup\n      description: Update a contact group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-contacts.updatecontactgroup\n      with:\n        resourceName: tools.resourceName\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: resourceName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontactgroup\n      description: Delete a contact group\n    \
  \  hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-contacts.deletecontactgroup\n      with:\n        resourceName: tools.resourceName\n        deleteContacts: tools.deleteContacts\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: resourceName\n        required: true\n      - name: deleteContacts\n        type: boolean\n        description: deleteContacts\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CONTACTS_TOKEN: GOOGLE_CONTACTS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-contacts/refs/heads/main/capabilities/google-contacts-capability.yaml
tags:
- Google
- Contacts
- API
tools:
- description: Get a person
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getperson
- description: List contacts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconnections
- description: Create a contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontact
- description: Update a contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecontact
- description: Delete a contact
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontact
- description: Search contacts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcontacts
- description: List contact groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontactgroups
- description: Create a contact group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontactgroup
- description: Get a contact group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontactgroup
- description: Update a contact group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecontactgroup
- description: Delete a contact group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontactgroup
---
