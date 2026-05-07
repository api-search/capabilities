---
categories: []
consumed_apis: []
description: Ion Group Acuris Entities API API capability.
layout: capability
name: Ion Group Acuris Entities API
operations:
- description: Ion Group Get list of entities (with optional filters)
  method: GET
  name: get-entities
  path: /entities
- description: Ion Group Get one entity by its ID
  method: GET
  name: get-entities-id
  path: /entities/{id}
- description: Ion Group Get entities hierarchy (with optional filters)
  method: GET
  name: get-entities-hierarchy
  path: /entities/hierarchy
personas: []
provider_name: Ion Group
provider_slug: ion-group
search_terms:
- ion group get one entity by its id
- analytics
- financial
- financial services
- ion group get list of entities (with optional filters)
- trading
- ion
- get entities hierarchy
- ion group get entities hierarchy (with optional filters)
- get entities
- api
- get entities id
- group
slug: ion-group-capability
source_filename: ion-group-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ion Group Acuris Entities API\n  description: Ion Group Acuris Entities API API capability.\n  tags:\n  - Ion\n  - Group\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ion-group\n    baseUri: https://api.acuris.com\n    description: Ion Group Acuris Entities API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{ION_GROUP_TOKEN}}'\n    resources:\n    - name: entities\n      path: /entities\n      operations:\n      - name: get-entities\n        method: GET\n        description: Ion Group Get list of entities (with optional filters)\n        inputParameters:\n        - name: Accept-Encoding\n          in: header\n          type: string\n          description: We recommend the use of GZIP compression which produces savings from 60 to 80% in the json data transfer.\n        - name: entityName\n          in: query\n\
  \          type: string\n          description: Search by entity name.\n        - name: entityType\n          in: query\n          type: array\n          description: Search by entity type.\n        - name: before\n          in: query\n          type: string\n          description: it acts as a live cursor and specify cursor where to end the result set\n        - name: after\n          in: query\n          type: string\n          description: it acts as a live cursor and specify cursor where to start the result set\n        - name: sector\n          in: query\n          type: array\n          description: Search by entity sector. <br>To see available values please visit <a href=\"/reference/docs#Industries,\n            Sectors and Subsectors\">Reference data</a>.\n        - name: subsector\n          in: query\n          type: array\n          description: Search by entity subsector. <br>To see available values please visit <a href=\"/reference/docs#Industries,\n            Sectors and\
  \ Subsectors\">Reference data</a>.\n        - name: hqCountry\n          in: query\n          type: array\n          description: Search by headquarters country. <br>To see available values please visit <a href=\"/reference/docs#Countries\n            and States\">Reference data</a>.\n        - name: hqState\n          in: query\n          type: array\n          description: Search by headquarters state. <br>To see available values please visit <a href=\"/reference/docs#Countries\n            and States\">Reference data</a>.\n        - name: instrumentIsin\n          in: query\n          type: string\n          description: Search by ISIN.\n        - name: instrumentLei\n          in: query\n          type: string\n          description: Search by LEI.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entities-id\n      path: /entities/{id}\n      operations:\n      - name: get-entities-id\n     \
  \   method: GET\n        description: Ion Group Get one entity by its ID\n        inputParameters:\n        - name: Accept-Encoding\n          in: header\n          type: string\n          description: We recommend the use of GZIP compression which produces savings from 60 to 80% in the json data transfer.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: 'ID of the entity. This parameter is required and needs to match the following RegExp: ^prime-[0-9]+$'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entities-hierarchy\n      path: /entities/hierarchy\n      operations:\n      - name: get-entities-hierarchy\n        method: GET\n        description: Ion Group Get entities hierarchy (with optional filters)\n        inputParameters:\n        - name: Accept-Encoding\n          in: header\n          type: string\n          description:\
  \ We recommend the use of GZIP compression which produces savings from 60 to 80% in the json data transfer.\n        - name: instrumentIsin\n          in: query\n          type: string\n          description: Search by ISIN.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ion-group-rest\n    description: REST adapter for Ion Group Acuris Entities API.\n    resources:\n    - path: /entities\n      name: get-entities\n      operations:\n      - method: GET\n        name: get-entities\n        description: Ion Group Get list of entities (with optional filters)\n        call: ion-group.get-entities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities/{id}\n      name: get-entities-id\n      operations:\n      - method: GET\n        name: get-entities-id\n        description: Ion Group Get one entity by its ID\n\
  \        call: ion-group.get-entities-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities/hierarchy\n      name: get-entities-hierarchy\n      operations:\n      - method: GET\n        name: get-entities-hierarchy\n        description: Ion Group Get entities hierarchy (with optional filters)\n        call: ion-group.get-entities-hierarchy\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ion-group-mcp\n    transport: http\n    description: MCP adapter for Ion Group Acuris Entities API for AI agent use.\n    tools:\n    - name: get-entities\n      description: Ion Group Get list of entities (with optional filters)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ion-group.get-entities\n      with:\n        entityName: tools.entityName\n        entityType: tools.entityType\n   \
  \     before: tools.before\n        after: tools.after\n        sector: tools.sector\n        subsector: tools.subsector\n        hqCountry: tools.hqCountry\n        hqState: tools.hqState\n        instrumentIsin: tools.instrumentIsin\n        instrumentLei: tools.instrumentLei\n      inputParameters:\n      - name: entityName\n        type: string\n        description: Search by entity name.\n      - name: entityType\n        type: array\n        description: Search by entity type.\n      - name: before\n        type: string\n        description: it acts as a live cursor and specify cursor where to end the result set\n      - name: after\n        type: string\n        description: it acts as a live cursor and specify cursor where to start the result set\n      - name: sector\n        type: array\n        description: Search by entity sector. <br>To see available values please visit <a href=\"/reference/docs#Industries,\n          Sectors and Subsectors\">Reference data</a>.\n      - name:\
  \ subsector\n        type: array\n        description: Search by entity subsector. <br>To see available values please visit <a href=\"/reference/docs#Industries,\n          Sectors and Subsectors\">Reference data</a>.\n      - name: hqCountry\n        type: array\n        description: Search by headquarters country. <br>To see available values please visit <a href=\"/reference/docs#Countries\n          and States\">Reference data</a>.\n      - name: hqState\n        type: array\n        description: Search by headquarters state. <br>To see available values please visit <a href=\"/reference/docs#Countries\n          and States\">Reference data</a>.\n      - name: instrumentIsin\n        type: string\n        description: Search by ISIN.\n      - name: instrumentLei\n        type: string\n        description: Search by LEI.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entities-id\n      description: Ion Group Get one entity by its ID\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ion-group.get-entities-id\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: 'ID of the entity. This parameter is required and needs to match the following RegExp: ^prime-[0-9]+$'\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entities-hierarchy\n      description: Ion Group Get entities hierarchy (with optional filters)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ion-group.get-entities-hierarchy\n      with:\n        instrumentIsin: tools.instrumentIsin\n      inputParameters:\n      - name: instrumentIsin\n        type: string\n        description: Search by ISIN.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ION_GROUP_TOKEN: ION_GROUP_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ion-group/refs/heads/main/capabilities/ion-group-capability.yaml
tags:
- Ion
- Group
- API
tools:
- description: Ion Group Get list of entities (with optional filters)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-entities
- description: Ion Group Get one entity by its ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-entities-id
- description: Ion Group Get entities hierarchy (with optional filters)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-entities-hierarchy
---
