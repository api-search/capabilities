---
categories: []
consumed_apis: []
description: End-to-end digital homebuying workflow capability for Taylor Morrison. Combines community search, floor plan browsing, lot selection, design studio, and online reservation into a unified integration experience for real estate platforms, mortgage lenders, and homebuying tools.
layout: capability
name: Taylor Morrison Digital Homebuying
operations:
- description: Find communities by location and price range
  method: GET
  name: list-communities
  path: /v1/communities
- description: Get community details
  method: GET
  name: get-community
  path: /v1/communities/{community_id}
- description: Browse available homes by filters
  method: GET
  name: list-homes
  path: /v1/homes
- description: Browse floor plans
  method: GET
  name: list-floor-plans
  path: /v1/floor-plans
- description: Get design options by floor plan and category
  method: GET
  name: list-design-options
  path: /v1/design/options
- description: View existing reservations
  method: GET
  name: list-reservations
  path: /v1/reservations
- description: Reserve a home online
  method: POST
  name: create-reservation
  path: /v1/reservations
personas: []
provider_name: taylor-morrison-home
provider_slug: taylor-morrison-home
search_terms:
- digital homebuying
- mortgage
- design studio
- homebuilding
- list floor plans
- get details about a specific taylor morrison community including amenities, pricing, and available homes
- view personalization options for a floor plan — exterior, flooring, cabinets, countertops, and more
- list homes
- taylor morrison
- new homes
- find communities by location and price range
- list reservations
- get community
- community detail and amenities
- search and browse taylor morrison communities
- floor plans
- search communities
- get design options by floor plan and category
- communities
- browse available homes by filters
- browse available and quick-move-in homes with bedroom count, price, and square footage filters
- view existing reservations
- browse available homes
- get community details
- browse floor plans
- fortune 1000
- reserve a home online
- real estate
- list design options
- view reservations
- online home reservations
- available and to-be-built homes
- get design options
- reserve a taylor morrison home digitally with lot selection, design choices, and deposit
- create reservation
- reserve home online
- reservations
- floor plan catalog
- list communities
- view existing taylor morrison home reservations and their status
- explore taylor morrison floor plans by size, bedroom count, and stories
- search taylor morrison new home communities by location, price range, or amenities
- design studio options for personalization
slug: homebuying
source_filename: homebuying.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Taylor Morrison Digital Homebuying\n  description: End-to-end digital homebuying workflow capability for Taylor Morrison. Combines community search, floor plan\n    browsing, lot selection, design studio, and online reservation into a unified integration experience for real estate platforms,\n    mortgage lenders, and homebuying tools.\n  tags:\n  - Communities\n  - Design Studio\n  - Digital Homebuying\n  - Floor Plans\n  - Homebuilding\n  - New Homes\n  - Real Estate\n  - Reservations\n  - Taylor Morrison\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TAYLOR_MORRISON_API_KEY: TAYLOR_MORRISON_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: taylor-morrison\n    baseUri: https://www.taylormorrison.com/api\n    description: Taylor Morrison homebuying platform API\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{TAYLOR_MORRISON_API_KEY}}'\n      placement:\
  \ header\n    resources:\n    - name: communities\n      path: /communities\n      description: New home communities\n      operations:\n      - name: list-communities\n        method: GET\n        description: List communities filtered by state, city, price\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: State code filter\n        - name: city\n          in: query\n          type: string\n          required: false\n          description: City filter\n        - name: price_min\n          in: query\n          type: integer\n          required: false\n          description: Minimum price\n        - name: price_max\n          in: query\n          type: integer\n          required: false\n          description: Maximum price\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: community-detail\n      path: /communities/{community_id}\n      description: Community detail\n      operations:\n      - name: get-community\n        method: GET\n        description: Get community details\n        inputParameters:\n        - name: community_id\n          in: path\n          type: string\n          required: true\n          description: Community ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: homes\n      path: /homes\n      description: Available homes\n      operations:\n      - name: list-homes\n        method: GET\n        description: List available homes\n        inputParameters:\n        - name: community_id\n          in: query\n          type: string\n          required: false\n          description: Community filter\n        - name: status\n          in: query\n\
  \          type: string\n          required: false\n          description: Home status filter\n        - name: bedrooms\n          in: query\n          type: integer\n          required: false\n          description: Bedroom count\n        - name: price_min\n          in: query\n          type: integer\n          required: false\n          description: Min price\n        - name: price_max\n          in: query\n          type: integer\n          required: false\n          description: Max price\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: floor-plans\n      path: /floor-plans\n      description: Floor plan catalog\n      operations:\n      - name: list-floor-plans\n        method: GET\n        description: List floor plans\n        inputParameters:\n        - name: community_id\n          in: query\n          type: string\n          required: false\n          description: Community filter\n  \
  \      - name: bedrooms\n          in: query\n          type: integer\n          required: false\n          description: Bedroom count\n        - name: sqft_min\n          in: query\n          type: integer\n          required: false\n          description: Min sqft\n        - name: sqft_max\n          in: query\n          type: integer\n          required: false\n          description: Max sqft\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reservations\n      path: /reservations\n      description: Online home reservations\n      operations:\n      - name: list-reservations\n        method: GET\n        description: List buyer reservations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-reservation\n        method: POST\n        description: Create online home reservation\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            community_id: '{{tools.community_id}}'\n            plan_id: '{{tools.plan_id}}'\n            lot_id: '{{tools.lot_id}}'\n            buyer_info: '{{tools.buyer_info}}'\n            deposit: '{{tools.deposit}}'\n    - name: design-options\n      path: /design/options\n      description: Design studio selections\n      operations:\n      - name: list-design-options\n        method: GET\n        description: List design options for a floor plan\n        inputParameters:\n        - name: plan_id\n          in: query\n          type: string\n          required: true\n          description: Floor plan ID\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Option category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: taylor-morrison-homebuying-api\n    description: Unified REST API for Taylor Morrison digital homebuying workflows.\n    resources:\n    - path: /v1/communities\n      name: communities\n      description: Search and browse Taylor Morrison communities\n      operations:\n      - method: GET\n        name: list-communities\n        description: Find communities by location and price range\n        call: taylor-morrison.list-communities\n        with:\n          state: rest.state\n          city: rest.city\n          metro: rest.metro\n          price_min: rest.price_min\n          price_max: rest.price_max\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/communities/{community_id}\n      name: community-detail\n      description: Community detail and amenities\n      operations:\n      - method: GET\n        name:\
  \ get-community\n        description: Get community details\n        call: taylor-morrison.get-community\n        with:\n          community_id: rest.community_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/homes\n      name: homes\n      description: Available and to-be-built homes\n      operations:\n      - method: GET\n        name: list-homes\n        description: Browse available homes by filters\n        call: taylor-morrison.list-homes\n        with:\n          community_id: rest.community_id\n          status: rest.status\n          bedrooms: rest.bedrooms\n          price_min: rest.price_min\n          price_max: rest.price_max\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/floor-plans\n      name: floor-plans\n      description: Floor plan catalog\n      operations:\n      - method: GET\n        name: list-floor-plans\n        description: Browse floor plans\n        call: taylor-morrison.list-floor-plans\n\
  \        with:\n          community_id: rest.community_id\n          bedrooms: rest.bedrooms\n          sqft_min: rest.sqft_min\n          sqft_max: rest.sqft_max\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/design/options\n      name: design-options\n      description: Design studio options for personalization\n      operations:\n      - method: GET\n        name: list-design-options\n        description: Get design options by floor plan and category\n        call: taylor-morrison.list-design-options\n        with:\n          plan_id: rest.plan_id\n          category: rest.category\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reservations\n      name: reservations\n      description: Online home reservations\n      operations:\n      - method: GET\n        name: list-reservations\n        description: View existing reservations\n        call: taylor-morrison.list-reservations\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-reservation\n        description: Reserve a home online\n        call: taylor-morrison.create-reservation\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: taylor-morrison-homebuying-mcp\n    transport: http\n    description: MCP server for AI-assisted Taylor Morrison homebuying experience.\n    tools:\n    - name: search-communities\n      description: Search Taylor Morrison new home communities by location, price range, or amenities\n      hints:\n        readOnly: true\n        openWorld: true\n      call: taylor-morrison.list-communities\n      with:\n        state: tools.state\n        city: tools.city\n        metro: tools.metro\n        price_min: tools.price_min\n        price_max: tools.price_max\n        bedrooms: tools.bedrooms\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-community-details\n      description: Get details about a specific Taylor Morrison community including amenities, pricing, and available homes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: taylor-morrison.get-community\n      with:\n        community_id: tools.community_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-available-homes\n      description: Browse available and quick-move-in homes with bedroom count, price, and square footage filters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: taylor-morrison.list-homes\n      with:\n        community_id: tools.community_id\n        status: tools.status\n        bedrooms: tools.bedrooms\n        price_min: tools.price_min\n        price_max: tools.price_max\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-floor-plans\n      description: Explore Taylor Morrison floor plans by size,\
  \ bedroom count, and stories\n      hints:\n        readOnly: true\n        openWorld: true\n      call: taylor-morrison.list-floor-plans\n      with:\n        community_id: tools.community_id\n        bedrooms: tools.bedrooms\n        sqft_min: tools.sqft_min\n        sqft_max: tools.sqft_max\n        stories: tools.stories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-design-options\n      description: View personalization options for a floor plan — exterior, flooring, cabinets, countertops, and more\n      hints:\n        readOnly: true\n        openWorld: false\n      call: taylor-morrison.list-design-options\n      with:\n        plan_id: tools.plan_id\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reserve-home-online\n      description: Reserve a Taylor Morrison home digitally with lot selection, design choices, and deposit\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: taylor-morrison.create-reservation\n      with:\n        community_id: tools.community_id\n        plan_id: tools.plan_id\n        lot_id: tools.lot_id\n        buyer_info: tools.buyer_info\n        deposit: tools.deposit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: view-reservations\n      description: View existing Taylor Morrison home reservations and their status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: taylor-morrison.list-reservations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/taylor-morrison-home/refs/heads/main/capabilities/homebuying.yaml
tags:
- Communities
- Design Studio
- Digital Homebuying
- Floor Plans
- Homebuilding
- New Homes
- Real Estate
- Reservations
- Taylor Morrison
tools:
- description: Search Taylor Morrison new home communities by location, price range, or amenities
  hints:
    openWorld: true
    readOnly: true
  name: search-communities
- description: Get details about a specific Taylor Morrison community including amenities, pricing, and available homes
  hints:
    openWorld: true
    readOnly: true
  name: get-community-details
- description: Browse available and quick-move-in homes with bedroom count, price, and square footage filters
  hints:
    openWorld: true
    readOnly: true
  name: browse-available-homes
- description: Explore Taylor Morrison floor plans by size, bedroom count, and stories
  hints:
    openWorld: true
    readOnly: true
  name: browse-floor-plans
- description: View personalization options for a floor plan — exterior, flooring, cabinets, countertops, and more
  hints:
    openWorld: false
    readOnly: true
  name: get-design-options
- description: Reserve a Taylor Morrison home digitally with lot selection, design choices, and deposit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reserve-home-online
- description: View existing Taylor Morrison home reservations and their status
  hints:
    openWorld: false
    readOnly: true
  name: view-reservations
---
