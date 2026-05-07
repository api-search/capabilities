---
categories: []
consumed_apis: []
description: The New York Public Library's What's On The Menu API provides programmatic access to over 17,000 historical restaurant menus from the New York City area dating back to the 1850s. Explore menus, pages, and dishes including prices, names, dates, and full-text search across the dataset.
layout: capability
name: NYPL What's On The Menu API
operations:
- description: List menus
  method: GET
  name: get-menus
  path: /menus
- description: Get menu
  method: GET
  name: get-menus-id
  path: /menus/{id}
- description: Get menu pages
  method: GET
  name: get-menus-id-pages
  path: /menus/{id}/pages
- description: Get menu dishes
  method: GET
  name: get-menus-id-dishes
  path: /menus/{id}/dishes
- description: Search menus
  method: GET
  name: get-menus-search
  path: /menus/search
- description: List dishes
  method: GET
  name: get-dishes
  path: /dishes
- description: Get dish
  method: GET
  name: get-dishes-id
  path: /dishes/{id}
- description: Get menus for a dish
  method: GET
  name: get-dishes-id-menus
  path: /dishes/{id}/menus
- description: Search dishes
  method: GET
  name: get-dishes-search
  path: /dishes/search
personas: []
provider_name: New York Public Library What's On The Menu
provider_slug: new-york-public-library-whats-on-the-menu
search_terms:
- menus
- food
- restaurants
- new
- list menus
- get dishes
- history
- get menus id dishes
- get menus for a dish
- get dishes id menus
- get dishes id
- public
- get menu pages
- 'on'
- search menus
- libraries
- search dishes
- library
- get menu
- get dish
- whats
- get menus id pages
- get menu dishes
- get dishes search
- get menus search
- get menus id
- list dishes
- get menus
- open data
- york
slug: new-york-public-library-whats-on-the-menu-capability
source_filename: new-york-public-library-whats-on-the-menu-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NYPL What's On The Menu API\n  description: The New York Public Library's What's On The Menu API provides programmatic access to over 17,000 historical\n    restaurant menus from the New York City area dating back to the 1850s. Explore menus, pages, and dishes including prices,\n    names, dates, and full-text search across the dataset.\n  tags:\n  - New\n  - York\n  - Public\n  - Library\n  - Whats\n  - 'On'\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: new-york-public-library-whats-on-the-menu\n    baseUri: http://api.menus.nypl.org\n    description: NYPL What's On The Menu API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: token\n      value: '{{NEW_YORK_PUBLIC_LIBRARY_WHATS_ON_THE_MENU_TOKEN}}'\n    resources:\n    - name: menus\n      path: /menus\n      operations:\n      - name: get-menus\n        method: GET\n        description: List\
  \ menus\n        inputParameters:\n        - name: min_year\n          in: query\n          type: integer\n        - name: max_year\n          in: query\n          type: integer\n        - name: sort_by\n          in: query\n          type: string\n        - name: status\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: menus-id\n      path: /menus/{id}\n      operations:\n      - name: get-menus-id\n        method: GET\n        description: Get menu\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: menus-id-pages\n      path: /menus/{id}/pages\n      operations:\n      - name: get-menus-id-pages\n        method: GET\n        description: Get menu pages\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: menus-id-dishes\n      path: /menus/{id}/dishes\n      operations:\n      - name: get-menus-id-dishes\n        method: GET\n        description: Get menu dishes\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: menus-search\n      path: /menus/search\n      operations:\n      - name: get-menus-search\n        method: GET\n        description: Search menus\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        - name: sort_by\n          in: query\n          type:\
  \ string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dishes\n      path: /dishes\n      operations:\n      - name: get-dishes\n        method: GET\n        description: List dishes\n        inputParameters:\n        - name: min_year\n          in: query\n          type: integer\n        - name: max_year\n          in: query\n          type: integer\n        - name: sort_by\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dishes-id\n      path: /dishes/{id}\n      operations:\n      - name: get-dishes-id\n        method: GET\n        description: Get dish\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: dishes-id-menus\n      path: /dishes/{id}/menus\n      operations:\n      - name: get-dishes-id-menus\n        method: GET\n        description: Get menus for a dish\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dishes-search\n      path: /dishes/search\n      operations:\n      - name: get-dishes-search\n        method: GET\n        description: Search dishes\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        - name: sort_by\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ new-york-public-library-whats-on-the-menu-rest\n    description: REST adapter for NYPL What's On The Menu API.\n    resources:\n    - path: /menus\n      name: get-menus\n      operations:\n      - method: GET\n        name: get-menus\n        description: List menus\n        call: new-york-public-library-whats-on-the-menu.get-menus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /menus/{id}\n      name: get-menus-id\n      operations:\n      - method: GET\n        name: get-menus-id\n        description: Get menu\n        call: new-york-public-library-whats-on-the-menu.get-menus-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /menus/{id}/pages\n      name: get-menus-id-pages\n      operations:\n      - method: GET\n        name: get-menus-id-pages\n        description: Get menu pages\n        call: new-york-public-library-whats-on-the-menu.get-menus-id-pages\n     \
  \   with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /menus/{id}/dishes\n      name: get-menus-id-dishes\n      operations:\n      - method: GET\n        name: get-menus-id-dishes\n        description: Get menu dishes\n        call: new-york-public-library-whats-on-the-menu.get-menus-id-dishes\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /menus/search\n      name: get-menus-search\n      operations:\n      - method: GET\n        name: get-menus-search\n        description: Search menus\n        call: new-york-public-library-whats-on-the-menu.get-menus-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dishes\n      name: get-dishes\n      operations:\n      - method: GET\n        name: get-dishes\n        description: List dishes\n        call: new-york-public-library-whats-on-the-menu.get-dishes\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dishes/{id}\n      name: get-dishes-id\n      operations:\n      - method: GET\n        name: get-dishes-id\n        description: Get dish\n        call: new-york-public-library-whats-on-the-menu.get-dishes-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dishes/{id}/menus\n      name: get-dishes-id-menus\n      operations:\n      - method: GET\n        name: get-dishes-id-menus\n        description: Get menus for a dish\n        call: new-york-public-library-whats-on-the-menu.get-dishes-id-menus\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dishes/search\n      name: get-dishes-search\n      operations:\n      - method: GET\n        name: get-dishes-search\n        description: Search dishes\n        call: new-york-public-library-whats-on-the-menu.get-dishes-search\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: new-york-public-library-whats-on-the-menu-mcp\n    transport: http\n    description: MCP adapter for NYPL What's On The Menu API for AI agent use.\n    tools:\n    - name: get-menus\n      description: List menus\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: new-york-public-library-whats-on-the-menu.get-menus\n      with:\n        min_year: tools.min_year\n        max_year: tools.max_year\n        sort_by: tools.sort_by\n        status: tools.status\n      inputParameters:\n      - name: min_year\n        type: integer\n        description: min_year\n      - name: max_year\n        type: integer\n        description: max_year\n      - name: sort_by\n        type: string\n        description: sort_by\n      - name: status\n        type: string\n        description: status\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-menus-id\n      description: Get menu\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: new-york-public-library-whats-on-the-menu.get-menus-id\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-menus-id-pages\n      description: Get menu pages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: new-york-public-library-whats-on-the-menu.get-menus-id-pages\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-menus-id-dishes\n      description: Get menu dishes\n      hints:\n   \
  \     readOnly: true\n        destructive: false\n        idempotent: true\n      call: new-york-public-library-whats-on-the-menu.get-menus-id-dishes\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-menus-search\n      description: Search menus\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: new-york-public-library-whats-on-the-menu.get-menus-search\n      with:\n        query: tools.query\n        sort_by: tools.sort_by\n      inputParameters:\n      - name: query\n        type: string\n        description: query\n        required: true\n      - name: sort_by\n        type: string\n        description: sort_by\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dishes\n      description: List dishes\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: new-york-public-library-whats-on-the-menu.get-dishes\n      with:\n        min_year: tools.min_year\n        max_year: tools.max_year\n        sort_by: tools.sort_by\n      inputParameters:\n      - name: min_year\n        type: integer\n        description: min_year\n      - name: max_year\n        type: integer\n        description: max_year\n      - name: sort_by\n        type: string\n        description: sort_by\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dishes-id\n      description: Get dish\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: new-york-public-library-whats-on-the-menu.get-dishes-id\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n    - name: get-dishes-id-menus\n      description: Get menus for a dish\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: new-york-public-library-whats-on-the-menu.get-dishes-id-menus\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dishes-search\n      description: Search dishes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: new-york-public-library-whats-on-the-menu.get-dishes-search\n      with:\n        query: tools.query\n        sort_by: tools.sort_by\n      inputParameters:\n      - name: query\n        type: string\n        description: query\n        required: true\n      - name: sort_by\n        type: string\n        description: sort_by\n      outputParameters:\n  \
  \    - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NEW_YORK_PUBLIC_LIBRARY_WHATS_ON_THE_MENU_TOKEN: NEW_YORK_PUBLIC_LIBRARY_WHATS_ON_THE_MENU_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/new-york-public-library-whats-on-the-menu/refs/heads/main/capabilities/new-york-public-library-whats-on-the-menu-capability.yaml
tags:
- New
- York
- Public
- Library
- Whats
- 'On'
tools:
- description: List menus
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-menus
- description: Get menu
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-menus-id
- description: Get menu pages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-menus-id-pages
- description: Get menu dishes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-menus-id-dishes
- description: Search menus
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-menus-search
- description: List dishes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dishes
- description: Get dish
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dishes-id
- description: Get menus for a dish
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dishes-id-menus
- description: Search dishes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dishes-search
---
