---
categories: []
consumed_apis:
- taylor-morrison
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
- list homes
- reservations
- create reservation
- floor plans
- view existing reservations
- search taylor morrison new home communities by location, price range, or amenities
- get details about a specific taylor morrison community including amenities, pricing, and available homes
- digital homebuying
- community detail and amenities
- real estate
- get design options by floor plan and category
- communities
- search communities
- get community details
- reserve a taylor morrison home digitally with lot selection, design choices, and deposit
- design studio
- view personalization options for a floor plan — exterior, flooring, cabinets, countertops, and more
- browse available homes
- new homes
- available and to-be-built homes
- get community
- reserve a home online
- get design options
- browse available and quick-move-in homes with bedroom count, price, and square footage filters
- list communities
- list reservations
- reserve home online
- view reservations
- taylor morrison
- design studio options for personalization
- list design options
- floor plan catalog
- mortgage
- online home reservations
- search and browse taylor morrison communities
- browse floor plans
- browse available homes by filters
- explore taylor morrison floor plans by size, bedroom count, and stories
- view existing taylor morrison home reservations and their status
- fortune 1000
- list floor plans
- find communities by location and price range
- homebuilding
slug: homebuying
source_filename: homebuying.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Taylor Morrison Digital Homebuying\"\n  description: >-\n    End-to-end digital homebuying workflow capability for Taylor Morrison. Combines\n    community search, floor plan browsing, lot selection, design studio, and online\n    reservation into a unified integration experience for real estate platforms,\n    mortgage lenders, and homebuying tools.\n  tags:\n    - Communities\n    - Design Studio\n    - Digital Homebuying\n    - Floor Plans\n    - Homebuilding\n    - New Homes\n    - Real Estate\n    - Reservations\n    - Taylor Morrison\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TAYLOR_MORRISON_API_KEY: TAYLOR_MORRISON_API_KEY\n\ncapability:\n  consumes:\n    - import: taylor-morrison\n      location: ./shared/taylor-morrison-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: taylor-morrison-homebuying-api\n      description: \"Unified REST\
  \ API for Taylor Morrison digital homebuying workflows.\"\n      resources:\n        - path: /v1/communities\n          name: communities\n          description: \"Search and browse Taylor Morrison communities\"\n          operations:\n            - method: GET\n              name: list-communities\n              description: \"Find communities by location and price range\"\n              call: \"taylor-morrison.list-communities\"\n              with:\n                state: \"rest.state\"\n                city: \"rest.city\"\n                metro: \"rest.metro\"\n                price_min: \"rest.price_min\"\n                price_max: \"rest.price_max\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/communities/{community_id}\n          name: community-detail\n          description: \"Community detail and amenities\"\n          operations:\n            - method: GET\n   \
  \           name: get-community\n              description: \"Get community details\"\n              call: \"taylor-morrison.get-community\"\n              with:\n                community_id: \"rest.community_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/homes\n          name: homes\n          description: \"Available and to-be-built homes\"\n          operations:\n            - method: GET\n              name: list-homes\n              description: \"Browse available homes by filters\"\n              call: \"taylor-morrison.list-homes\"\n              with:\n                community_id: \"rest.community_id\"\n                status: \"rest.status\"\n                bedrooms: \"rest.bedrooms\"\n                price_min: \"rest.price_min\"\n                price_max: \"rest.price_max\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/floor-plans\n\
  \          name: floor-plans\n          description: \"Floor plan catalog\"\n          operations:\n            - method: GET\n              name: list-floor-plans\n              description: \"Browse floor plans\"\n              call: \"taylor-morrison.list-floor-plans\"\n              with:\n                community_id: \"rest.community_id\"\n                bedrooms: \"rest.bedrooms\"\n                sqft_min: \"rest.sqft_min\"\n                sqft_max: \"rest.sqft_max\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/design/options\n          name: design-options\n          description: \"Design studio options for personalization\"\n          operations:\n            - method: GET\n              name: list-design-options\n              description: \"Get design options by floor plan and category\"\n              call: \"taylor-morrison.list-design-options\"\n              with:\n                plan_id: \"\
  rest.plan_id\"\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reservations\n          name: reservations\n          description: \"Online home reservations\"\n          operations:\n            - method: GET\n              name: list-reservations\n              description: \"View existing reservations\"\n              call: \"taylor-morrison.list-reservations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-reservation\n              description: \"Reserve a home online\"\n              call: \"taylor-morrison.create-reservation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: taylor-morrison-homebuying-mcp\n      transport: http\n      description: \"MCP\
  \ server for AI-assisted Taylor Morrison homebuying experience.\"\n      tools:\n        - name: search-communities\n          description: \"Search Taylor Morrison new home communities by location, price range, or amenities\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"taylor-morrison.list-communities\"\n          with:\n            state: \"tools.state\"\n            city: \"tools.city\"\n            metro: \"tools.metro\"\n            price_min: \"tools.price_min\"\n            price_max: \"tools.price_max\"\n            bedrooms: \"tools.bedrooms\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-community-details\n          description: \"Get details about a specific Taylor Morrison community including amenities, pricing, and available homes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"\
  taylor-morrison.get-community\"\n          with:\n            community_id: \"tools.community_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: browse-available-homes\n          description: \"Browse available and quick-move-in homes with bedroom count, price, and square footage filters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"taylor-morrison.list-homes\"\n          with:\n            community_id: \"tools.community_id\"\n            status: \"tools.status\"\n            bedrooms: \"tools.bedrooms\"\n            price_min: \"tools.price_min\"\n            price_max: \"tools.price_max\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: browse-floor-plans\n          description: \"Explore Taylor Morrison floor plans by size, bedroom count, and stories\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"taylor-morrison.list-floor-plans\"\n          with:\n            community_id: \"tools.community_id\"\n            bedrooms: \"tools.bedrooms\"\n            sqft_min: \"tools.sqft_min\"\n            sqft_max: \"tools.sqft_max\"\n            stories: \"tools.stories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-design-options\n          description: \"View personalization options for a floor plan — exterior, flooring, cabinets, countertops, and more\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"taylor-morrison.list-design-options\"\n          with:\n            plan_id: \"tools.plan_id\"\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reserve-home-online\n          description: \"Reserve a Taylor Morrison home digitally with lot selection, design choices,\
  \ and deposit\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"taylor-morrison.create-reservation\"\n          with:\n            community_id: \"tools.community_id\"\n            plan_id: \"tools.plan_id\"\n            lot_id: \"tools.lot_id\"\n            buyer_info: \"tools.buyer_info\"\n            deposit: \"tools.deposit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: view-reservations\n          description: \"View existing Taylor Morrison home reservations and their status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"taylor-morrison.list-reservations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
