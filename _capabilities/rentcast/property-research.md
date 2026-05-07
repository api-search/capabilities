---
categories: []
consumed_apis: []
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
- for-sale property listings
- valuation
- search property records by address or geographic area
- get aggregate market statistics for a zip code
- rental market
- search properties
- get a specific property record
- market analysis
- us property record lookup and search
- search for sale listings by location
- real estate market statistics
- retrieve a property record by id
- get rent estimate
- get value estimate
- investment
- search for active and historical sale listings by location or address
- real estate
- search sale listings
- get market statistics
- get an automated rent estimate for a property
- search for long-term rental listings by location, address, or property criteria
- search us property records by address, city, state, zip code, or geographic coordinates
- search for rental listings by location
- get detailed property record by rentcast property id
- avm
- get aggregate real estate market statistics for a zip code including price trends and inventory
- get property
- rent estimate via avm
- property data
- get an automated home value estimate (avm) for a property with comparable sales
- long-term rental listings
- get an automated rent estimate (avm) for a property with comparable rentals
- get an automated home value estimate for a property
- search rental listings
- home value estimate via avm
slug: property-research
source_filename: property-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: RentCast Property Research\n  description: Unified workflow for real estate property research, market analysis, and investment evaluation using the RentCast\n    API. Combines property record lookup, rent and home value estimation, listing search, and market statistics to support\n    real estate investors, landlords, property managers, and proptech applications.\n  tags:\n  - Real Estate\n  - Property Data\n  - Valuation\n  - Investment\n  - Market Analysis\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RENTCAST_API_KEY: RENTCAST_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: rentcast\n    baseUri: https://api.rentcast.io/v1\n    description: RentCast real estate data API\n    authentication:\n      type: apikey\n      key: X-Api-Key\n      value: '{{RENTCAST_API_KEY}}'\n      placement: header\n    resources:\n    - name: properties\n      path: /properties\n      description:\
  \ US property records\n      operations:\n      - name: search-properties\n        method: GET\n        description: Search for property records by address or geographic area\n        inputParameters:\n        - name: address\n          in: query\n          type: string\n          required: false\n          description: Full property address\n        - name: city\n          in: query\n          type: string\n          required: false\n          description: City name\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: 2-character state code\n        - name: zipCode\n          in: query\n          type: string\n          required: false\n          description: 5-digit ZIP code\n        - name: latitude\n          in: query\n          type: string\n          required: false\n          description: Latitude for circular search\n        - name: longitude\n          in: query\n          type: string\n          required: false\n\
  \          description: Longitude for circular search\n        - name: radius\n          in: query\n          type: string\n          required: false\n          description: Search radius in miles\n        - name: propertyType\n          in: query\n          type: string\n          required: false\n          description: Property type filter\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Results per page (1-500)\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-property\n        method: GET\n        description: Get a single property record by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description:\
  \ RentCast property ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rent-estimate\n      path: /avm/rent/long-term\n      description: Automated rent estimate for a property\n      operations:\n      - name: get-rent-estimate\n        method: GET\n        description: Get a rent estimate with comparables for a property\n        inputParameters:\n        - name: address\n          in: query\n          type: string\n          required: false\n          description: Full property address\n        - name: latitude\n          in: query\n          type: string\n          required: false\n          description: Property latitude\n        - name: longitude\n          in: query\n          type: string\n          required: false\n          description: Property longitude\n        - name: propertyType\n          in: query\n          type: string\n          required: false\n          description: Property\
  \ type\n        - name: bedrooms\n          in: query\n          type: string\n          required: false\n          description: Number of bedrooms\n        - name: bathrooms\n          in: query\n          type: string\n          required: false\n          description: Number of bathrooms\n        - name: squareFootage\n          in: query\n          type: string\n          required: false\n          description: Living area in square feet\n        - name: compCount\n          in: query\n          type: integer\n          required: false\n          description: Number of comparables (5-25)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: value-estimate\n      path: /avm/value\n      description: Automated home value estimate for a property\n      operations:\n      - name: get-value-estimate\n        method: GET\n        description: Get a home value estimate with comparables for a property\n  \
  \      inputParameters:\n        - name: address\n          in: query\n          type: string\n          required: false\n          description: Full property address\n        - name: latitude\n          in: query\n          type: string\n          required: false\n          description: Property latitude\n        - name: longitude\n          in: query\n          type: string\n          required: false\n          description: Property longitude\n        - name: propertyType\n          in: query\n          type: string\n          required: false\n          description: Property type\n        - name: bedrooms\n          in: query\n          type: string\n          required: false\n          description: Number of bedrooms\n        - name: bathrooms\n          in: query\n          type: string\n          required: false\n          description: Number of bathrooms\n        - name: squareFootage\n          in: query\n          type: string\n          required: false\n          description:\
  \ Living area in square feet\n        - name: compCount\n          in: query\n          type: integer\n          required: false\n          description: Number of comparables (5-25)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sale-listings\n      path: /listings/sale\n      description: Sale listings in the US\n      operations:\n      - name: search-sale-listings\n        method: GET\n        description: Search for sale listings by location or address\n        inputParameters:\n        - name: address\n          in: query\n          type: string\n          required: false\n          description: Full property address\n        - name: city\n          in: query\n          type: string\n          required: false\n          description: City name\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: State code\n        - name: zipCode\n\
  \          in: query\n          type: string\n          required: false\n          description: ZIP code\n        - name: propertyType\n          in: query\n          type: string\n          required: false\n          description: Property type filter\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Listing status (Active or Inactive)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: rental-listings\n      path: /listings/rental/long-term\n      description: Long-term rental listings in the US\n      operations:\n      - name: search-rental-listings\n        method: GET\n        description: Search for rental listings by location or address\n        inputParameters:\n        - name: address\n \
  \         in: query\n          type: string\n          required: false\n          description: Full property address\n        - name: city\n          in: query\n          type: string\n          required: false\n          description: City name\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: State code\n        - name: zipCode\n          in: query\n          type: string\n          required: false\n          description: ZIP code\n        - name: propertyType\n          in: query\n          type: string\n          required: false\n          description: Property type filter\n        - name: bedrooms\n          in: query\n          type: string\n          required: false\n          description: Bedroom count filter\n        - name: price\n          in: query\n          type: string\n          required: false\n          description: Rent price filter (supports ranges)\n        - name: limit\n          in: query\n    \
  \      type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: markets\n      path: /markets\n      description: Aggregate real estate market statistics\n      operations:\n      - name: get-market-statistics\n        method: GET\n        description: Get aggregate market statistics for a zip code\n        inputParameters:\n        - name: zipCode\n          in: query\n          type: string\n          required: false\n          description: ZIP code for market data\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: State code\n        - name: city\n          in: query\n          type: string\n          required: false\n          description: City name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: rentcast-research-api\n    description: Unified REST API for RentCast property research and market analysis.\n    resources:\n    - path: /v1/properties\n      name: properties\n      description: US property record lookup and search\n      operations:\n      - method: GET\n        name: search-properties\n        description: Search property records by address or geographic area\n        call: rentcast.search-properties\n        with:\n          address: rest.address\n          city: rest.city\n          state: rest.state\n          zipCode: rest.zipCode\n          latitude: rest.latitude\n          longitude: rest.longitude\n          radius: rest.radius\n          propertyType: rest.propertyType\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/properties/{id}\n      name: property\n      description: Get\
  \ a specific property record\n      operations:\n      - method: GET\n        name: get-property\n        description: Retrieve a property record by ID\n        call: rentcast.get-property\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/estimates/rent\n      name: rent-estimate\n      description: Rent estimate via AVM\n      operations:\n      - method: GET\n        name: get-rent-estimate\n        description: Get an automated rent estimate for a property\n        call: rentcast.get-rent-estimate\n        with:\n          address: rest.address\n          propertyType: rest.propertyType\n          bedrooms: rest.bedrooms\n          bathrooms: rest.bathrooms\n          squareFootage: rest.squareFootage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/estimates/value\n      name: value-estimate\n      description: Home value estimate via AVM\n      operations:\n   \
  \   - method: GET\n        name: get-value-estimate\n        description: Get an automated home value estimate for a property\n        call: rentcast.get-value-estimate\n        with:\n          address: rest.address\n          propertyType: rest.propertyType\n          bedrooms: rest.bedrooms\n          bathrooms: rest.bathrooms\n          squareFootage: rest.squareFootage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/listings/sale\n      name: sale-listings\n      description: For-sale property listings\n      operations:\n      - method: GET\n        name: search-sale-listings\n        description: Search for sale listings by location\n        call: rentcast.search-sale-listings\n        with:\n          address: rest.address\n          city: rest.city\n          state: rest.state\n          zipCode: rest.zipCode\n          propertyType: rest.propertyType\n          status: rest.status\n          limit: rest.limit\n        outputParameters:\n\
  \        - type: array\n          mapping: $.\n    - path: /v1/listings/rental\n      name: rental-listings\n      description: Long-term rental listings\n      operations:\n      - method: GET\n        name: search-rental-listings\n        description: Search for rental listings by location\n        call: rentcast.search-rental-listings\n        with:\n          address: rest.address\n          city: rest.city\n          state: rest.state\n          zipCode: rest.zipCode\n          propertyType: rest.propertyType\n          bedrooms: rest.bedrooms\n          price: rest.price\n          limit: rest.limit\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/markets\n      name: markets\n      description: Real estate market statistics\n      operations:\n      - method: GET\n        name: get-market-statistics\n        description: Get aggregate market statistics for a zip code\n        call: rentcast.get-market-statistics\n        with:\n         \
  \ zipCode: rest.zipCode\n          state: rest.state\n          city: rest.city\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: rentcast-research-mcp\n    transport: http\n    description: MCP server for AI-assisted real estate research and property analysis using RentCast data.\n    tools:\n    - name: search-properties\n      description: Search US property records by address, city, state, zip code, or geographic coordinates\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rentcast.search-properties\n      with:\n        address: tools.address\n        city: tools.city\n        state: tools.state\n        zipCode: tools.zipCode\n        latitude: tools.latitude\n        longitude: tools.longitude\n        radius: tools.radius\n        propertyType: tools.propertyType\n        limit: tools.limit\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-property\n\
  \      description: Get detailed property record by RentCast property ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rentcast.get-property\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-rent-estimate\n      description: Get an automated rent estimate (AVM) for a property with comparable rentals\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rentcast.get-rent-estimate\n      with:\n        address: tools.address\n        propertyType: tools.propertyType\n        bedrooms: tools.bedrooms\n        bathrooms: tools.bathrooms\n        squareFootage: tools.squareFootage\n        compCount: tools.compCount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-value-estimate\n      description: Get an automated home value estimate (AVM) for a property with comparable sales\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: rentcast.get-value-estimate\n      with:\n        address: tools.address\n        propertyType: tools.propertyType\n        bedrooms: tools.bedrooms\n        bathrooms: tools.bathrooms\n        squareFootage: tools.squareFootage\n        compCount: tools.compCount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-sale-listings\n      description: Search for active and historical sale listings by location or address\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rentcast.search-sale-listings\n      with:\n        address: tools.address\n        city: tools.city\n        state: tools.state\n        zipCode: tools.zipCode\n        propertyType: tools.propertyType\n        status: tools.status\n        price: tools.price\n        limit: tools.limit\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: search-rental-listings\n      description: Search for long-term rental listings\
  \ by location, address, or property criteria\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rentcast.search-rental-listings\n      with:\n        address: tools.address\n        city: tools.city\n        state: tools.state\n        zipCode: tools.zipCode\n        propertyType: tools.propertyType\n        bedrooms: tools.bedrooms\n        price: tools.price\n        limit: tools.limit\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-market-statistics\n      description: Get aggregate real estate market statistics for a zip code including price trends and inventory\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rentcast.get-market-statistics\n      with:\n        zipCode: tools.zipCode\n        state: tools.state\n        city: tools.city\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
