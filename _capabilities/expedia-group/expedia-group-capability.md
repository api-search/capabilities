---
categories: []
consumed_apis: []
description: 'The EPS Deposit API manages the deposit policy for a property, offering operations to create/update, read and delete it. <br/><br/>To start experimenting, please use your existing EQC credentials and properties. We''ve also made the following test credentials available: EQCtest12933870 / ew67nk33 assigned to test property ID 12933870.'
layout: capability
name: Expedia Group EPS Deposit API
operations:
- description: Expedia Group Obtain the deposit policy for a given property
  method: GET
  name: getdepositpolicy
  path: /properties/{propertyId}/depositPolicy
- description: Expedia Group Create/update the deposit policy for a given property
  method: PUT
  name: setdepositpolicy
  path: /properties/{propertyId}/depositPolicy
- description: Expedia Group Delete the deposit policy for a given property
  method: DELETE
  name: deletedepositpolicy
  path: /properties/{propertyId}/depositPolicy
personas: []
provider_name: Expedia Group
provider_slug: expedia-group
search_terms:
- expedia
- expedia group delete the deposit policy for a given property
- lodging
- travel
- expedia group create/update the deposit policy for a given property
- getdepositpolicy
- expedia group obtain the deposit policy for a given property
- api
- deletedepositpolicy
- flights
- setdepositpolicy
- group
- hotels
slug: expedia-group-capability
source_filename: expedia-group-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Expedia Group EPS Deposit API\n  description: 'The EPS Deposit API manages the deposit policy for a property, offering operations to create/update, read\n    and delete it. <br/><br/>To start experimenting, please use your existing EQC credentials and properties. We''ve also\n    made the following test credentials available: EQCtest12933870 / ew67nk33 assigned to test property ID 12933870.'\n  tags:\n  - Expedia\n  - Group\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: expedia-group\n    baseUri: https://services.expediapartnercentral.com\n    description: Expedia Group EPS Deposit API HTTP API.\n    authentication:\n      type: basic\n      username: '{{EXPEDIA_GROUP_USERNAME}}'\n      password: '{{EXPEDIA_GROUP_PASSWORD}}'\n    resources:\n    - name: properties-propertyid-depositpolicy\n      path: /properties/{propertyId}/depositPolicy\n      operations:\n    \
  \  - name: getdepositpolicy\n        method: GET\n        description: Expedia Group Obtain the deposit policy for a given property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Expedia Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setdepositpolicy\n        method: PUT\n        description: Expedia Group Create/update the deposit policy for a given property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Expedia Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedepositpolicy\n        method: DELETE\n        description: Expedia Group Delete the deposit policy for a given property\n\
  \        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Expedia Property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: expedia-group-rest\n    description: REST adapter for Expedia Group EPS Deposit API.\n    resources:\n    - path: /properties/{propertyId}/depositPolicy\n      name: getdepositpolicy\n      operations:\n      - method: GET\n        name: getdepositpolicy\n        description: Expedia Group Obtain the deposit policy for a given property\n        call: expedia-group.getdepositpolicy\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /properties/{propertyId}/depositPolicy\n      name: setdepositpolicy\n      operations:\n      - method: PUT\n        name:\
  \ setdepositpolicy\n        description: Expedia Group Create/update the deposit policy for a given property\n        call: expedia-group.setdepositpolicy\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /properties/{propertyId}/depositPolicy\n      name: deletedepositpolicy\n      operations:\n      - method: DELETE\n        name: deletedepositpolicy\n        description: Expedia Group Delete the deposit policy for a given property\n        call: expedia-group.deletedepositpolicy\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: expedia-group-mcp\n    transport: http\n    description: MCP adapter for Expedia Group EPS Deposit API for AI agent use.\n    tools:\n    - name: getdepositpolicy\n      description: Expedia Group Obtain the deposit policy for a given property\n \
  \     hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: expedia-group.getdepositpolicy\n      with:\n        propertyId: tools.propertyId\n      inputParameters:\n      - name: propertyId\n        type: string\n        description: Expedia Property ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setdepositpolicy\n      description: Expedia Group Create/update the deposit policy for a given property\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: expedia-group.setdepositpolicy\n      with:\n        propertyId: tools.propertyId\n      inputParameters:\n      - name: propertyId\n        type: string\n        description: Expedia Property ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedepositpolicy\n      description: Expedia Group Delete the deposit policy for\
  \ a given property\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: expedia-group.deletedepositpolicy\n      with:\n        propertyId: tools.propertyId\n      inputParameters:\n      - name: propertyId\n        type: string\n        description: Expedia Property ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    EXPEDIA_GROUP_USERNAME: EXPEDIA_GROUP_USERNAME\n    EXPEDIA_GROUP_PASSWORD: EXPEDIA_GROUP_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/expedia-group/refs/heads/main/capabilities/expedia-group-capability.yaml
tags:
- Expedia
- Group
- API
tools:
- description: Expedia Group Obtain the deposit policy for a given property
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdepositpolicy
- description: Expedia Group Create/update the deposit policy for a given property
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setdepositpolicy
- description: Expedia Group Delete the deposit policy for a given property
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedepositpolicy
---
