---
categories: []
consumed_apis: []
description: The Google People API provides access to information about profiles and contacts. It enables reading and managing the authenticated user's contacts and accessing profile information for authenticated users across Google services.
layout: capability
name: Google People API
operations:
- description: Google People Get Person
  method: GET
  name: getperson
  path: /people/{resourceName}
- description: Google People Batch Get People
  method: GET
  name: batchgetpeople
  path: /people:batchGet
- description: Google People Search Contacts
  method: GET
  name: searchcontacts
  path: /people:searchContacts
- description: Google People Create Contact
  method: POST
  name: createcontact
  path: /people:createContact
- description: Google People Delete Contact
  method: DELETE
  name: deletecontact
  path: /people/{resourceName}:deleteContact
- description: Google People Update Contact
  method: PATCH
  name: updatecontact
  path: /people/{resourceName}:updateContact
- description: Google People List Connections
  method: GET
  name: listconnections
  path: /people/me/connections
- description: Google People List Contact Groups
  method: GET
  name: listcontactgroups
  path: /contactGroups
- description: Google People Create Contact Group
  method: POST
  name: createcontactgroup
  path: /contactGroups
- description: Google People Get Contact Group
  method: GET
  name: getcontactgroup
  path: /contactGroups/{resourceName}
- description: Google People Update Contact Group
  method: PUT
  name: updatecontactgroup
  path: /contactGroups/{resourceName}
- description: Google People Delete Contact Group
  method: DELETE
  name: deletecontactgroup
  path: /contactGroups/{resourceName}
personas: []
provider_name: Google People
provider_slug: google-people
search_terms:
- listcontactgroups
- google people create contact group
- searchcontacts
- google people create contact
- google people update contact
- updatecontactgroup
- google people get person
- contacts
- profiles
- listconnections
- google
- google people list contact groups
- updatecontact
- deletecontactgroup
- google people batch get people
- google people list connections
- getcontactgroup
- createcontact
- getperson
- api
- address book
- google people get contact group
- google people search contacts
- people
- google people delete contact
- google people update contact group
- createcontactgroup
- google people delete contact group
- deletecontact
- batchgetpeople
slug: google-people-capability
source_filename: google-people-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google People API\n  description: The Google People API provides access to information about profiles and contacts. It enables reading and managing\n    the authenticated user's contacts and accessing profile information for authenticated users across Google services.\n  tags:\n  - Google\n  - People\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-people\n    baseUri: https://people.googleapis.com/v1\n    description: Google People API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_PEOPLE_TOKEN}}'\n    resources:\n    - name: people-resourcename\n      path: /people/{resourceName}\n      operations:\n      - name: getperson\n        method: GET\n        description: Google People Get Person\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n          description:\
  \ The resource name of the person (e.g., people/me).\n        - name: personFields\n          in: query\n          type: string\n          required: true\n          description: A field mask to restrict which fields on the person are returned.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-batchget\n      path: /people:batchGet\n      operations:\n      - name: batchgetpeople\n        method: GET\n        description: Google People Batch Get People\n        inputParameters:\n        - name: resourceNames\n          in: query\n          type: array\n          required: true\n        - name: personFields\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-searchcontacts\n      path: /people:searchContacts\n      operations:\n\
  \      - name: searchcontacts\n        method: GET\n        description: Google People Search Contacts\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        - name: readMask\n          in: query\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-createcontact\n      path: /people:createContact\n      operations:\n      - name: createcontact\n        method: POST\n        description: Google People Create Contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-resourcename-deletecontact\n      path: /people/{resourceName}:deleteContact\n      operations:\n      - name: deletecontact\n        method: DELETE\n\
  \        description: Google People Delete Contact\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-resourcename-updatecontact\n      path: /people/{resourceName}:updateContact\n      operations:\n      - name: updatecontact\n        method: PATCH\n        description: Google People Update Contact\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n        - name: updatePersonFields\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-me-connections\n      path: /people/me/connections\n      operations:\n      - name: listconnections\n\
  \        method: GET\n        description: Google People List Connections\n        inputParameters:\n        - name: personFields\n          in: query\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: sortOrder\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contactgroups\n      path: /contactGroups\n      operations:\n      - name: listcontactgroups\n        method: GET\n        description: Google People List Contact Groups\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: createcontactgroup\n        method: POST\n        description: Google People Create Contact Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contactgroups-resourcename\n      path: /contactGroups/{resourceName}\n      operations:\n      - name: getcontactgroup\n        method: GET\n        description: Google People Get Contact Group\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecontactgroup\n        method: PUT\n        description: Google People Update Contact Group\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontactgroup\n        method: DELETE\n        description: Google People Delete Contact Group\n        inputParameters:\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-people-rest\n    description: REST adapter for Google People API.\n    resources:\n    - path: /people/{resourceName}\n      name: getperson\n      operations:\n      - method: GET\n        name: getperson\n        description: Google People Get Person\n        call: google-people.getperson\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people:batchGet\n      name: batchgetpeople\n\
  \      operations:\n      - method: GET\n        name: batchgetpeople\n        description: Google People Batch Get People\n        call: google-people.batchgetpeople\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people:searchContacts\n      name: searchcontacts\n      operations:\n      - method: GET\n        name: searchcontacts\n        description: Google People Search Contacts\n        call: google-people.searchcontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people:createContact\n      name: createcontact\n      operations:\n      - method: POST\n        name: createcontact\n        description: Google People Create Contact\n        call: google-people.createcontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people/{resourceName}:deleteContact\n      name: deletecontact\n      operations:\n      - method: DELETE\n        name: deletecontact\n    \
  \    description: Google People Delete Contact\n        call: google-people.deletecontact\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people/{resourceName}:updateContact\n      name: updatecontact\n      operations:\n      - method: PATCH\n        name: updatecontact\n        description: Google People Update Contact\n        call: google-people.updatecontact\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people/me/connections\n      name: listconnections\n      operations:\n      - method: GET\n        name: listconnections\n        description: Google People List Connections\n        call: google-people.listconnections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactGroups\n      name: listcontactgroups\n      operations:\n      - method: GET\n\
  \        name: listcontactgroups\n        description: Google People List Contact Groups\n        call: google-people.listcontactgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactGroups\n      name: createcontactgroup\n      operations:\n      - method: POST\n        name: createcontactgroup\n        description: Google People Create Contact Group\n        call: google-people.createcontactgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactGroups/{resourceName}\n      name: getcontactgroup\n      operations:\n      - method: GET\n        name: getcontactgroup\n        description: Google People Get Contact Group\n        call: google-people.getcontactgroup\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactGroups/{resourceName}\n      name: updatecontactgroup\n      operations:\n      -\
  \ method: PUT\n        name: updatecontactgroup\n        description: Google People Update Contact Group\n        call: google-people.updatecontactgroup\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactGroups/{resourceName}\n      name: deletecontactgroup\n      operations:\n      - method: DELETE\n        name: deletecontactgroup\n        description: Google People Delete Contact Group\n        call: google-people.deletecontactgroup\n        with:\n          resourceName: rest.resourceName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-people-mcp\n    transport: http\n    description: MCP adapter for Google People API for AI agent use.\n    tools:\n    - name: getperson\n      description: Google People Get Person\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: google-people.getperson\n      with:\n        resourceName: tools.resourceName\n        personFields: tools.personFields\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: The resource name of the person (e.g., people/me).\n        required: true\n      - name: personFields\n        type: string\n        description: A field mask to restrict which fields on the person are returned.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batchgetpeople\n      description: Google People Batch Get People\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-people.batchgetpeople\n      with:\n        resourceNames: tools.resourceNames\n        personFields: tools.personFields\n      inputParameters:\n      - name: resourceNames\n        type: array\n        description: resourceNames\n        required: true\n      - name: personFields\n\
  \        type: string\n        description: personFields\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcontacts\n      description: Google People Search Contacts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-people.searchcontacts\n      with:\n        query: tools.query\n        readMask: tools.readMask\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: query\n        type: string\n        description: query\n        required: true\n      - name: readMask\n        type: string\n        description: readMask\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontact\n      description: Google People Create Contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: google-people.createcontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontact\n      description: Google People Delete Contact\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-people.deletecontact\n      with:\n        resourceName: tools.resourceName\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: resourceName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecontact\n      description: Google People Update Contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-people.updatecontact\n      with:\n        resourceName: tools.resourceName\n        updatePersonFields: tools.updatePersonFields\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: resourceName\n\
  \        required: true\n      - name: updatePersonFields\n        type: string\n        description: updatePersonFields\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listconnections\n      description: Google People List Connections\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-people.listconnections\n      with:\n        personFields: tools.personFields\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        sortOrder: tools.sortOrder\n      inputParameters:\n      - name: personFields\n        type: string\n        description: personFields\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: sortOrder\n        type: string\n        description: sortOrder\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: listcontactgroups\n      description: Google People List Contact Groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-people.listcontactgroups\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontactgroup\n      description: Google People Create Contact Group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-people.createcontactgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontactgroup\n      description: Google People Get Contact Group\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: google-people.getcontactgroup\n      with:\n        resourceName: tools.resourceName\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: resourceName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecontactgroup\n      description: Google People Update Contact Group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-people.updatecontactgroup\n      with:\n        resourceName: tools.resourceName\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: resourceName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontactgroup\n      description: Google People Delete Contact Group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n    \
  \  call: google-people.deletecontactgroup\n      with:\n        resourceName: tools.resourceName\n      inputParameters:\n      - name: resourceName\n        type: string\n        description: resourceName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_PEOPLE_TOKEN: GOOGLE_PEOPLE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-people/refs/heads/main/capabilities/google-people-capability.yaml
tags:
- Google
- People
- API
tools:
- description: Google People Get Person
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getperson
- description: Google People Batch Get People
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: batchgetpeople
- description: Google People Search Contacts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcontacts
- description: Google People Create Contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontact
- description: Google People Delete Contact
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontact
- description: Google People Update Contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecontact
- description: Google People List Connections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconnections
- description: Google People List Contact Groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontactgroups
- description: Google People Create Contact Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontactgroup
- description: Google People Get Contact Group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontactgroup
- description: Google People Update Contact Group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecontactgroup
- description: Google People Delete Contact Group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontactgroup
---
