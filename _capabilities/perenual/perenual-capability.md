---
categories: []
consumed_apis: []
description: Perenual provides a comprehensive plant database API offering access to over 10,000+ plant species, including details on care, watering, sunlight, edibility, toxicity, pests, diseases, and care guides.
layout: capability
name: Perenual API
operations:
- description: List plant species
  method: GET
  name: getspecieslist
  path: /species-list
- description: Get plant species details
  method: GET
  name: getspeciesdetails
  path: /species/details/{id}
- description: List pests and diseases
  method: GET
  name: getpestdiseaselist
  path: /pest-disease-list
- description: List plant care guides
  method: GET
  name: getcareguides
  path: /species-care-guide-list
- description: Get hardiness map for species
  method: GET
  name: gethardinessmap
  path: /hardiness-map
personas: []
provider_name: Perenual
provider_slug: perenual
search_terms:
- plants
- getcareguides
- getspecieslist
- botany
- gardening
- perenual
- api
- get plant species details
- horticulture
- getspeciesdetails
- getpestdiseaselist
- list pests and diseases
- get hardiness map for species
- list plant care guides
- list plant species
- gethardinessmap
slug: perenual-capability
source_filename: perenual-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Perenual API\n  description: Perenual provides a comprehensive plant database API offering access to over 10,000+ plant species, including\n    details on care, watering, sunlight, edibility, toxicity, pests, diseases, and care guides.\n  tags:\n  - Perenual\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: perenual\n    baseUri: https://perenual.com/api/v2\n    description: Perenual API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{PERENUAL_TOKEN}}'\n    resources:\n    - name: species-list\n      path: /species-list\n      operations:\n      - name: getspecieslist\n        method: GET\n        description: List plant species\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n        - name: q\n          in: query\n          type: string\n        - name: order\n       \
  \   in: query\n          type: string\n        - name: edible\n          in: query\n          type: boolean\n        - name: poisonous\n          in: query\n          type: boolean\n        - name: cycle\n          in: query\n          type: string\n        - name: watering\n          in: query\n          type: string\n        - name: sunlight\n          in: query\n          type: string\n        - name: indoor\n          in: query\n          type: boolean\n        - name: hardiness\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: species-details-id\n      path: /species/details/{id}\n      operations:\n      - name: getspeciesdetails\n        method: GET\n        description: Get plant species details\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pest-disease-list\n      path: /pest-disease-list\n      operations:\n      - name: getpestdiseaselist\n        method: GET\n        description: List pests and diseases\n        inputParameters:\n        - name: id\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        - name: q\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: species-care-guide-list\n      path: /species-care-guide-list\n      operations:\n      - name: getcareguides\n        method: GET\n        description: List plant care guides\n        inputParameters:\n        - name: species_id\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        - name:\
  \ q\n          in: query\n          type: string\n        - name: type\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hardiness-map\n      path: /hardiness-map\n      operations:\n      - name: gethardinessmap\n        method: GET\n        description: Get hardiness map for species\n        inputParameters:\n        - name: species_id\n          in: query\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: perenual-rest\n    description: REST adapter for Perenual API.\n    resources:\n    - path: /species-list\n      name: getspecieslist\n      operations:\n      - method: GET\n        name: getspecieslist\n        description: List plant species\n        call: perenual.getspecieslist\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /species/details/{id}\n      name: getspeciesdetails\n      operations:\n      - method: GET\n        name: getspeciesdetails\n        description: Get plant species details\n        call: perenual.getspeciesdetails\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pest-disease-list\n      name: getpestdiseaselist\n      operations:\n      - method: GET\n        name: getpestdiseaselist\n        description: List pests and diseases\n        call: perenual.getpestdiseaselist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /species-care-guide-list\n      name: getcareguides\n      operations:\n      - method: GET\n        name: getcareguides\n        description: List plant care guides\n        call: perenual.getcareguides\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /hardiness-map\n      name: gethardinessmap\n      operations:\n      - method: GET\n        name: gethardinessmap\n        description: Get hardiness map for species\n        call: perenual.gethardinessmap\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: perenual-mcp\n    transport: http\n    description: MCP adapter for Perenual API for AI agent use.\n    tools:\n    - name: getspecieslist\n      description: List plant species\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: perenual.getspecieslist\n      with:\n        page: tools.page\n        q: tools.q\n        order: tools.order\n        edible: tools.edible\n        poisonous: tools.poisonous\n        cycle: tools.cycle\n        watering: tools.watering\n        sunlight: tools.sunlight\n        indoor: tools.indoor\n        hardiness: tools.hardiness\n      inputParameters:\n      -\
  \ name: page\n        type: integer\n        description: page\n      - name: q\n        type: string\n        description: q\n      - name: order\n        type: string\n        description: order\n      - name: edible\n        type: boolean\n        description: edible\n      - name: poisonous\n        type: boolean\n        description: poisonous\n      - name: cycle\n        type: string\n        description: cycle\n      - name: watering\n        type: string\n        description: watering\n      - name: sunlight\n        type: string\n        description: sunlight\n      - name: indoor\n        type: boolean\n        description: indoor\n      - name: hardiness\n        type: integer\n        description: hardiness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getspeciesdetails\n      description: Get plant species details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: perenual.getspeciesdetails\n\
  \      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpestdiseaselist\n      description: List pests and diseases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: perenual.getpestdiseaselist\n      with:\n        id: tools.id\n        page: tools.page\n        q: tools.q\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n      - name: page\n        type: integer\n        description: page\n      - name: q\n        type: string\n        description: q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcareguides\n      description: List plant care guides\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: perenual.getcareguides\n  \
  \    with:\n        species_id: tools.species_id\n        page: tools.page\n        q: tools.q\n        type: tools.type\n      inputParameters:\n      - name: species_id\n        type: integer\n        description: species_id\n      - name: page\n        type: integer\n        description: page\n      - name: q\n        type: string\n        description: q\n      - name: type\n        type: string\n        description: type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethardinessmap\n      description: Get hardiness map for species\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: perenual.gethardinessmap\n      with:\n        species_id: tools.species_id\n      inputParameters:\n      - name: species_id\n        type: integer\n        description: species_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PERENUAL_TOKEN:\
  \ PERENUAL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/perenual/refs/heads/main/capabilities/perenual-capability.yaml
tags:
- Perenual
- API
tools:
- description: List plant species
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getspecieslist
- description: Get plant species details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getspeciesdetails
- description: List pests and diseases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpestdiseaselist
- description: List plant care guides
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcareguides
- description: Get hardiness map for species
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethardinessmap
---
