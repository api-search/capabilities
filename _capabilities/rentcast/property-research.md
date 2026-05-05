---
categories: []
consumed_apis:
- rentcast
description: Unified workflow for real estate property research, market analysis, and investment evaluation using the RentCast API. Combines property record lookup, rent and home value estimation, listing search, and market statistics to support real estate investors, landlords, property managers, and proptech applications.
layout: capability
name: RentCast Property Research
operations:
- description: Search property records by address or geographic area
  method: GET
  name: search-properties
  path: /v1/properties
- description: Retrieve a property record by ID
  method: GET
  name: get-property
  path: /v1/properties/{id}
- description: Get an automated rent estimate for a property
  method: GET
  name: get-rent-estimate
  path: /v1/estimates/rent
- description: Get an automated home value estimate for a property
  method: GET
  name: get-value-estimate
  path: /v1/estimates/value
- description: Search for sale listings by location
  method: GET
  name: search-sale-listings
  path: /v1/listings/sale
- description: Search for rental listings by location
  method: GET
  name: search-rental-listings
  path: /v1/listings/rental
- description: Get aggregate market statistics for a zip code
  method: GET
  name: get-market-statistics
  path: /v1/markets
personas: []
provider_name: RentCast
provider_slug: rentcast
search_terms:
- search property records by address or geographic area
- investment
- search us property records by address, city, state, zip code, or geographic coordinates
- rent estimate via avm
- search properties
- real estate
- search rental listings
- get detailed property record by rentcast property id
- market analysis
- retrieve a property record by id
- search for sale listings by location
- get a specific property record
- get aggregate market statistics for a zip code
- search sale listings
- get an automated home value estimate for a property
- us property record lookup and search
- get an automated rent estimate (avm) for a property with comparable rentals
- valuation
- rental market
- for-sale property listings
- get an automated home value estimate (avm) for a property with comparable sales
- search for rental listings by location
- home value estimate via avm
- long-term rental listings
- real estate market statistics
- get aggregate real estate market statistics for a zip code including price trends and inventory
- get rent estimate
- search for long-term rental listings by location, address, or property criteria
- get value estimate
- search for active and historical sale listings by location or address
- get an automated rent estimate for a property
- get property
- property data
- avm
- get market statistics
slug: property-research
source_filename: property-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"RentCast Property Research\"\n  description: >-\n    Unified workflow for real estate property research, market analysis, and\n    investment evaluation using the RentCast API. Combines property record lookup,\n    rent and home value estimation, listing search, and market statistics to\n    support real estate investors, landlords, property managers, and proptech\n    applications.\n  tags:\n    - Real Estate\n    - Property Data\n    - Valuation\n    - Investment\n    - Market Analysis\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RENTCAST_API_KEY: RENTCAST_API_KEY\n\ncapability:\n  consumes:\n    - import: rentcast\n      location: ./shared/rentcast-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: rentcast-research-api\n      description: \"Unified REST API for RentCast property research and market analysis.\"\n      resources:\n        - path:\
  \ /v1/properties\n          name: properties\n          description: \"US property record lookup and search\"\n          operations:\n            - method: GET\n              name: search-properties\n              description: \"Search property records by address or geographic area\"\n              call: \"rentcast.search-properties\"\n              with:\n                address: \"rest.address\"\n                city: \"rest.city\"\n                state: \"rest.state\"\n                zipCode: \"rest.zipCode\"\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                radius: \"rest.radius\"\n                propertyType: \"rest.propertyType\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/properties/{id}\n          name: property\n          description: \"Get a specific property\
  \ record\"\n          operations:\n            - method: GET\n              name: get-property\n              description: \"Retrieve a property record by ID\"\n              call: \"rentcast.get-property\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/estimates/rent\n          name: rent-estimate\n          description: \"Rent estimate via AVM\"\n          operations:\n            - method: GET\n              name: get-rent-estimate\n              description: \"Get an automated rent estimate for a property\"\n              call: \"rentcast.get-rent-estimate\"\n              with:\n                address: \"rest.address\"\n                propertyType: \"rest.propertyType\"\n                bedrooms: \"rest.bedrooms\"\n                bathrooms: \"rest.bathrooms\"\n                squareFootage: \"rest.squareFootage\"\n              outputParameters:\n  \
  \              - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/estimates/value\n          name: value-estimate\n          description: \"Home value estimate via AVM\"\n          operations:\n            - method: GET\n              name: get-value-estimate\n              description: \"Get an automated home value estimate for a property\"\n              call: \"rentcast.get-value-estimate\"\n              with:\n                address: \"rest.address\"\n                propertyType: \"rest.propertyType\"\n                bedrooms: \"rest.bedrooms\"\n                bathrooms: \"rest.bathrooms\"\n                squareFootage: \"rest.squareFootage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/listings/sale\n          name: sale-listings\n          description: \"For-sale property listings\"\n          operations:\n            - method: GET\n              name: search-sale-listings\n\
  \              description: \"Search for sale listings by location\"\n              call: \"rentcast.search-sale-listings\"\n              with:\n                address: \"rest.address\"\n                city: \"rest.city\"\n                state: \"rest.state\"\n                zipCode: \"rest.zipCode\"\n                propertyType: \"rest.propertyType\"\n                status: \"rest.status\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/listings/rental\n          name: rental-listings\n          description: \"Long-term rental listings\"\n          operations:\n            - method: GET\n              name: search-rental-listings\n              description: \"Search for rental listings by location\"\n              call: \"rentcast.search-rental-listings\"\n              with:\n                address: \"rest.address\"\n                city: \"rest.city\"\n          \
  \      state: \"rest.state\"\n                zipCode: \"rest.zipCode\"\n                propertyType: \"rest.propertyType\"\n                bedrooms: \"rest.bedrooms\"\n                price: \"rest.price\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/markets\n          name: markets\n          description: \"Real estate market statistics\"\n          operations:\n            - method: GET\n              name: get-market-statistics\n              description: \"Get aggregate market statistics for a zip code\"\n              call: \"rentcast.get-market-statistics\"\n              with:\n                zipCode: \"rest.zipCode\"\n                state: \"rest.state\"\n                city: \"rest.city\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: rentcast-research-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted real estate research and property analysis using RentCast data.\"\n      tools:\n        - name: search-properties\n          description: \"Search US property records by address, city, state, zip code, or geographic coordinates\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rentcast.search-properties\"\n          with:\n            address: \"tools.address\"\n            city: \"tools.city\"\n            state: \"tools.state\"\n            zipCode: \"tools.zipCode\"\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            radius: \"tools.radius\"\n            propertyType: \"tools.propertyType\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-property\n          description: \"Get detailed property record by RentCast property ID\"\
  \n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rentcast.get-property\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-rent-estimate\n          description: \"Get an automated rent estimate (AVM) for a property with comparable rentals\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rentcast.get-rent-estimate\"\n          with:\n            address: \"tools.address\"\n            propertyType: \"tools.propertyType\"\n            bedrooms: \"tools.bedrooms\"\n            bathrooms: \"tools.bathrooms\"\n            squareFootage: \"tools.squareFootage\"\n            compCount: \"tools.compCount\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-value-estimate\n          description: \"Get an automated home value estimate (AVM) for\
  \ a property with comparable sales\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rentcast.get-value-estimate\"\n          with:\n            address: \"tools.address\"\n            propertyType: \"tools.propertyType\"\n            bedrooms: \"tools.bedrooms\"\n            bathrooms: \"tools.bathrooms\"\n            squareFootage: \"tools.squareFootage\"\n            compCount: \"tools.compCount\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-sale-listings\n          description: \"Search for active and historical sale listings by location or address\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rentcast.search-sale-listings\"\n          with:\n            address: \"tools.address\"\n            city: \"tools.city\"\n            state: \"tools.state\"\n            zipCode: \"tools.zipCode\"\n            propertyType: \"tools.propertyType\"\
  \n            status: \"tools.status\"\n            price: \"tools.price\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: search-rental-listings\n          description: \"Search for long-term rental listings by location, address, or property criteria\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rentcast.search-rental-listings\"\n          with:\n            address: \"tools.address\"\n            city: \"tools.city\"\n            state: \"tools.state\"\n            zipCode: \"tools.zipCode\"\n            propertyType: \"tools.propertyType\"\n            bedrooms: \"tools.bedrooms\"\n            price: \"tools.price\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-market-statistics\n          description: \"Get aggregate real estate market statistics\
  \ for a zip code including price trends and inventory\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rentcast.get-market-statistics\"\n          with:\n            zipCode: \"tools.zipCode\"\n            state: \"tools.state\"\n            city: \"tools.city\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rentcast/refs/heads/main/capabilities/property-research.yaml
tags:
- Real Estate
- Property Data
- Valuation
- Investment
- Market Analysis
tools:
- description: Search US property records by address, city, state, zip code, or geographic coordinates
  hints:
    openWorld: true
    readOnly: true
  name: search-properties
- description: Get detailed property record by RentCast property ID
  hints:
    openWorld: false
    readOnly: true
  name: get-property
- description: Get an automated rent estimate (AVM) for a property with comparable rentals
  hints:
    openWorld: true
    readOnly: true
  name: get-rent-estimate
- description: Get an automated home value estimate (AVM) for a property with comparable sales
  hints:
    openWorld: true
    readOnly: true
  name: get-value-estimate
- description: Search for active and historical sale listings by location or address
  hints:
    openWorld: true
    readOnly: true
  name: search-sale-listings
- description: Search for long-term rental listings by location, address, or property criteria
  hints:
    openWorld: true
    readOnly: true
  name: search-rental-listings
- description: Get aggregate real estate market statistics for a zip code including price trends and inventory
  hints:
    openWorld: true
    readOnly: true
  name: get-market-statistics
---
