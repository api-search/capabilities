---
categories: []
consumed_apis: []
description: Pantry is a free service that provides perishable data storage for small projects. Use the RESTful API to post JSON objects and Pantry will store them. Data is automatically deleted after a period of inactivity.
layout: capability
name: Pantry API
operations:
- description: Create a new pantry
  method: POST
  name: createpantry
  path: /pantry/create
- description: Get pantry details
  method: GET
  name: getpantry
  path: /pantry/{pantryID}
- description: Update pantry details
  method: PUT
  name: updatepantry
  path: /pantry/{pantryID}
- description: Delete a pantry
  method: DELETE
  name: deletepantry
  path: /pantry/{pantryID}
- description: Create a basket
  method: POST
  name: createbasket
  path: /pantry/{pantryID}/basket/{basketName}
- description: Update basket contents
  method: PUT
  name: updatebasket
  path: /pantry/{pantryID}/basket/{basketName}
- description: Get basket contents
  method: GET
  name: getbasket
  path: /pantry/{pantryID}/basket/{basketName}
- description: Delete a basket
  method: DELETE
  name: deletebasket
  path: /pantry/{pantryID}/basket/{basketName}
- description: Create a public basket link
  method: GET
  name: createpublicbasket
  path: /pantry/{pantryID}/basket/{basketName}/public
personas: []
provider_name: Pantry
provider_slug: pantry
search_terms:
- get pantry details
- createpantry
- api
- createpublicbasket
- create a basket
- deletebasket
- delete a basket
- update pantry details
- developer tools
- data storage
- getbasket
- update basket contents
- updatebasket
- create a new pantry
- json
- deletepantry
- create a public basket link
- pantry
- delete a pantry
- getpantry
- get basket contents
- updatepantry
- createbasket
slug: pantry-capability
source_filename: pantry-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pantry API\n  description: Pantry is a free service that provides perishable data storage for small projects. Use the RESTful API to post\n    JSON objects and Pantry will store them. Data is automatically deleted after a period of inactivity.\n  tags:\n  - Pantry\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pantry\n    baseUri: https://getpantry.cloud/apiv1\n    description: Pantry API HTTP API.\n    resources:\n    - name: pantry-create\n      path: /pantry/create\n      operations:\n      - name: createpantry\n        method: POST\n        description: Create a new pantry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pantry-pantryid\n      path: /pantry/{pantryID}\n      operations:\n      - name: getpantry\n        method: GET\n        description: Get pantry details\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepantry\n        method: PUT\n        description: Update pantry details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepantry\n        method: DELETE\n        description: Delete a pantry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pantry-pantryid-basket-basketname\n      path: /pantry/{pantryID}/basket/{basketName}\n      operations:\n      - name: createbasket\n        method: POST\n        description: Create a basket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebasket\n        method: PUT\n        description: Update basket contents\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getbasket\n        method: GET\n        description: Get basket contents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebasket\n        method: DELETE\n        description: Delete a basket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pantry-pantryid-basket-basketname-public\n      path: /pantry/{pantryID}/basket/{basketName}/public\n      operations:\n      - name: createpublicbasket\n        method: GET\n        description: Create a public basket link\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pantry-rest\n    description:\
  \ REST adapter for Pantry API.\n    resources:\n    - path: /pantry/create\n      name: createpantry\n      operations:\n      - method: POST\n        name: createpantry\n        description: Create a new pantry\n        call: pantry.createpantry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pantry/{pantryID}\n      name: getpantry\n      operations:\n      - method: GET\n        name: getpantry\n        description: Get pantry details\n        call: pantry.getpantry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pantry/{pantryID}\n      name: updatepantry\n      operations:\n      - method: PUT\n        name: updatepantry\n        description: Update pantry details\n        call: pantry.updatepantry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pantry/{pantryID}\n      name: deletepantry\n      operations:\n      - method: DELETE\n        name: deletepantry\n  \
  \      description: Delete a pantry\n        call: pantry.deletepantry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pantry/{pantryID}/basket/{basketName}\n      name: createbasket\n      operations:\n      - method: POST\n        name: createbasket\n        description: Create a basket\n        call: pantry.createbasket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pantry/{pantryID}/basket/{basketName}\n      name: updatebasket\n      operations:\n      - method: PUT\n        name: updatebasket\n        description: Update basket contents\n        call: pantry.updatebasket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pantry/{pantryID}/basket/{basketName}\n      name: getbasket\n      operations:\n      - method: GET\n        name: getbasket\n        description: Get basket contents\n        call: pantry.getbasket\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /pantry/{pantryID}/basket/{basketName}\n      name: deletebasket\n      operations:\n      - method: DELETE\n        name: deletebasket\n        description: Delete a basket\n        call: pantry.deletebasket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pantry/{pantryID}/basket/{basketName}/public\n      name: createpublicbasket\n      operations:\n      - method: GET\n        name: createpublicbasket\n        description: Create a public basket link\n        call: pantry.createpublicbasket\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pantry-mcp\n    transport: http\n    description: MCP adapter for Pantry API for AI agent use.\n    tools:\n    - name: createpantry\n      description: Create a new pantry\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pantry.createpantry\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpantry\n      description: Get pantry details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pantry.getpantry\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepantry\n      description: Update pantry details\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: pantry.updatepantry\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletepantry\n      description: Delete a pantry\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pantry.deletepantry\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbasket\n      description: Create a basket\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ pantry.createbasket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatebasket\n      description: Update basket contents\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: pantry.updatebasket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbasket\n      description: Get basket contents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pantry.getbasket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebasket\n      description: Delete a basket\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pantry.deletebasket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpublicbasket\n      description: Create a public basket link\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: pantry.createpublicbasket\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pantry/refs/heads/main/capabilities/pantry-capability.yaml
tags:
- Pantry
- API
tools:
- description: Create a new pantry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpantry
- description: Get pantry details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpantry
- description: Update pantry details
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepantry
- description: Delete a pantry
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepantry
- description: Create a basket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbasket
- description: Update basket contents
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatebasket
- description: Get basket contents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbasket
- description: Delete a basket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebasket
- description: Create a public basket link
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: createpublicbasket
---
