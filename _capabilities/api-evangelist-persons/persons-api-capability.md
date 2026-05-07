---
categories: []
consumed_apis: []
description: This is a template APIs.json for a persons API, to be used in storytelling, training, and knowledge bases.
layout: capability
name: Persons API
operations:
- description: Retrieves Persons
  method: GET
  name: getpersons
  path: /persons
- description: Persons Create Person
  method: POST
  name: createperson
  path: /persons
- description: Persons Retrieve Person
  method: GET
  name: getperson
  path: /persons/{personId}
- description: Persons Update Person
  method: PUT
  name: updateperson
  path: /persons/{personId}
- description: Persons Delete Person
  method: DELETE
  name: deleteperson
  path: /persons/{personId}
- description: Persons Cancel Person
  method: PUT
  name: sendperson
  path: /persons/{personId}/cancle
personas: []
provider_name: Persons
provider_slug: api-evangelist-persons
search_terms:
- updateperson
- persons
- persons retrieve person
- retrieves persons
- persons cancel person
- persons create person
- persons update person
- application programming interface
- sendperson
- persons delete person
- api
- createperson
- getpersons
- deleteperson
- getperson
slug: persons-api-capability
source_filename: persons-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Persons API\n  description: This is a template APIs.json for a persons API, to be used in storytelling, training, and knowledge bases.\n  tags:\n  - Persons\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: persons-api\n    baseUri: https://api.example.com\n    description: Persons API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: api-key\n      value: '{{PERSONS_API_TOKEN}}'\n    resources:\n    - name: persons\n      path: /persons\n      operations:\n      - name: getpersons\n        method: GET\n        description: Retrieves Persons\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createperson\n        method: POST\n        description: Persons Create Person\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: persons-personid\n      path: /persons/{personId}\n      operations:\n      - name: getperson\n        method: GET\n        description: Persons Retrieve Person\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateperson\n        method: PUT\n        description: Persons Update Person\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteperson\n        method: DELETE\n        description: Persons Delete Person\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: persons-personid-cancle\n      path: /persons/{personId}/cancle\n      operations:\n      - name: sendperson\n        method: PUT\n        description: Persons Cancel Person\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: persons-api-rest\n    description: REST adapter for Persons API.\n    resources:\n    - path: /persons\n      name: getpersons\n      operations:\n      - method: GET\n        name: getpersons\n        description: Retrieves Persons\n        call: persons-api.getpersons\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /persons\n      name: createperson\n      operations:\n      - method: POST\n        name: createperson\n        description: Persons Create Person\n        call: persons-api.createperson\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /persons/{personId}\n      name: getperson\n      operations:\n      - method: GET\n        name: getperson\n        description: Persons Retrieve Person\n        call: persons-api.getperson\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /persons/{personId}\n      name: updateperson\n      operations:\n      - method: PUT\n        name: updateperson\n        description: Persons Update Person\n        call: persons-api.updateperson\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /persons/{personId}\n      name: deleteperson\n      operations:\n      - method: DELETE\n        name: deleteperson\n        description: Persons Delete Person\n        call: persons-api.deleteperson\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /persons/{personId}/cancle\n      name: sendperson\n      operations:\n      - method: PUT\n        name: sendperson\n        description: Persons Cancel Person\n        call: persons-api.sendperson\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: persons-api-mcp\n    transport: http\n    description:\
  \ MCP adapter for Persons API for AI agent use.\n    tools:\n    - name: getpersons\n      description: Retrieves Persons\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: persons-api.getpersons\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createperson\n      description: Persons Create Person\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: persons-api.createperson\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getperson\n      description: Persons Retrieve Person\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: persons-api.getperson\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateperson\n      description: Persons Update Person\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ true\n      call: persons-api.updateperson\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteperson\n      description: Persons Delete Person\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: persons-api.deleteperson\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendperson\n      description: Persons Cancel Person\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: persons-api.sendperson\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PERSONS_API_TOKEN: PERSONS_API_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/api-evangelist-persons/refs/heads/main/capabilities/persons-api-capability.yaml
tags:
- Persons
- Api
- API
tools:
- description: Retrieves Persons
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpersons
- description: Persons Create Person
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createperson
- description: Persons Retrieve Person
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getperson
- description: Persons Update Person
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateperson
- description: Persons Delete Person
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteperson
- description: Persons Cancel Person
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sendperson
---
