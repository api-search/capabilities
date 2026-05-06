---
categories: []
consumed_apis: []
description: Unified capability for housing market analytics and data access on Redfin. Combines regional market trend data from the Stingray API and bulk market tracker datasets from the Data Center. Supports analysts, data scientists, and market researchers tracking housing trends at all geographic levels from national to neighborhood.
layout: capability
name: Redfin Market Analytics
operations:
- description: Get market trend data for a region including prices, volume, and days on market.
  method: GET
  name: get-region-trends
  path: /v1/trends/{regionType}/{regionId}/{code}
- description: Download national housing market tracker dataset (compressed TSV).
  method: GET
  name: get-national-market-data
  path: /v1/market-data/national
- description: Download metro MSA housing market tracker dataset (compressed TSV).
  method: GET
  name: get-metro-market-data
  path: /v1/market-data/metro
- description: Download state-level housing market tracker dataset (compressed TSV).
  method: GET
  name: get-state-market-data
  path: /v1/market-data/state
- description: Download county-level housing market tracker dataset (compressed TSV).
  method: GET
  name: get-county-market-data
  path: /v1/market-data/county
- description: Download city-level housing market tracker dataset (compressed TSV).
  method: GET
  name: get-city-market-data
  path: /v1/market-data/city
- description: Download ZIP code housing market tracker dataset (compressed TSV).
  method: GET
  name: get-zip-code-market-data
  path: /v1/market-data/zip-code
- description: Download neighborhood housing market tracker dataset (compressed TSV).
  method: GET
  name: get-neighborhood-market-data
  path: /v1/market-data/neighborhood
personas: []
provider_name: Redfin
provider_slug: redfin
search_terms:
- download redfin city-level housing market tracker dataset.
- regional market trends from stingray api.
- redfin
- get zip code market data
- download county-level housing market tracker dataset (compressed tsv).
- download redfin zip code housing market tracker dataset (most granular).
- neighborhood-level housing market tracker download.
- download zip code housing market tracker dataset (compressed tsv).
- download neighborhood housing market tracker dataset (compressed tsv).
- get region trends
- get city market data
- get national market data
- home values
- get market trend data for a region including prices, volume, and days on market.
- download redfin neighborhood-level housing market tracker dataset.
- county-level housing market tracker download.
- real estate
- download metro msa housing market tracker dataset (compressed tsv).
- property data
- get metro market data
- get state market data
- market analytics
- 'get housing market trends for a specific region: prices, volume, days on market, inventory.'
- download state-level housing market tracker dataset (compressed tsv).
- statistics
- download national housing market tracker dataset (compressed tsv).
- city-level housing market tracker download.
- csv export
- metro-level housing market tracker download.
- zip code-level housing market tracker download.
- download city-level housing market tracker dataset (compressed tsv).
- get county market data
- download redfin metro msa housing market tracker dataset.
- gis
- national housing market tracker download.
- listings
- download redfin state-level housing market tracker dataset.
- data science
- state-level housing market tracker download.
- housing market
- get neighborhood market data
- download redfin national housing market tracker dataset with all key metrics.
slug: market-analytics
source_filename: market-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Redfin Market Analytics\n  description: Unified capability for housing market analytics and data access on Redfin. Combines regional market trend data\n    from the Stingray API and bulk market tracker datasets from the Data Center. Supports analysts, data scientists, and market\n    researchers tracking housing trends at all geographic levels from national to neighborhood.\n  tags:\n  - Redfin\n  - Housing Market\n  - Market Analytics\n  - Real Estate\n  - Statistics\n  - Data Science\n  created: '2026-05-02'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: redfin-stingray\n    baseUri: https://www.redfin.com/stingray\n    description: Redfin Stingray REST API for property search and details.\n    resources:\n    - name: property-search\n      path: /do/gis-search\n      description: GIS-based property search with filters.\n      operations:\n      - name: gis-search\n        method: GET\n        description:\
  \ Search properties via GIS with region, price, and property type filters.\n        inputParameters:\n        - name: region_id\n          in: query\n          type: integer\n          required: false\n          description: Unique identifier for a Redfin region.\n        - name: region_type\n          in: query\n          type: integer\n          required: false\n          description: Region type code (1=neighborhood, 2=zip, 5=county, 6=city).\n        - name: uipt\n          in: query\n          type: string\n          required: false\n          description: 'Property type filter (comma-separated: 1=house, 2=condo, 3=townhouse).'\n        - name: status\n          in: query\n          type: integer\n          required: false\n          description: Listing status filter (1=active, 130=pending).\n        - name: min_price\n          in: query\n          type: integer\n          required: false\n          description: Minimum listing price in USD.\n        - name: max_price\n        \
  \  in: query\n          type: integer\n          required: false\n          description: Maximum listing price in USD.\n        - name: num_beds\n          in: query\n          type: integer\n          required: false\n          description: Minimum number of bedrooms.\n        - name: num_baths\n          in: query\n          type: integer\n          required: false\n          description: Minimum number of bathrooms.\n        - name: num_homes\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return.\n        - name: page_number\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: property-search-api\n      path: /api/gis\n      description: Alternative GIS property search endpoint.\n      operations:\n      -\
  \ name: gis-api-search\n        method: GET\n        description: Alternative GIS-based property search returning JSON results.\n        inputParameters:\n        - name: region_id\n          in: query\n          type: integer\n          required: false\n          description: Region identifier.\n        - name: region_type\n          in: query\n          type: integer\n          required: false\n          description: Region type code.\n        - name: num_homes\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: property-initial-info\n      path: /api/home/details/initialInfo\n      description: Initial property info returning propertyId and listingId.\n      operations:\n      - name: get-initial-info\n        method: GET\n        description: Retrieve initial property identifiers\
  \ from a Redfin URL path.\n        inputParameters:\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: Redfin property URL path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: property-above-fold\n      path: /api/home/details/aboveTheFold\n      description: 'Primary property details: price, address, photos, and listing status.'\n      operations:\n      - name: get-above-the-fold\n        method: GET\n        description: Get above-the-fold property details including price, beds, baths, and sq ft.\n        inputParameters:\n        - name: propertyId\n          in: query\n          type: integer\n          required: true\n          description: Redfin property identifier.\n        - name: listingId\n          in: query\n          type: integer\n          required: false\n          description: Redfin listing identifier.\n     \
  \   - name: accessLevel\n          in: query\n          type: integer\n          required: false\n          description: Access level controlling data detail.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: property-below-fold\n      path: /api/home/details/belowTheFold\n      description: Detailed MLS data, tax info, schools, and property history.\n      operations:\n      - name: get-below-the-fold\n        method: GET\n        description: Get below-the-fold property details with MLS data, history, and schools.\n        inputParameters:\n        - name: propertyId\n          in: query\n          type: integer\n          required: true\n          description: Redfin property identifier.\n        - name: listingId\n          in: query\n          type: integer\n          required: false\n          description: Redfin listing identifier.\n        - name: accessLevel\n          in: query\n       \
  \   type: integer\n          required: false\n          description: Access level.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: property-avm\n      path: /api/home/details/avmHistoricalData\n      description: Historical AVM (Redfin Estimate) time-series data.\n      operations:\n      - name: get-avm-historical-data\n        method: GET\n        description: Retrieve historical Redfin Estimate valuations for a property.\n        inputParameters:\n        - name: propertyId\n          in: query\n          type: integer\n          required: true\n          description: Redfin property identifier.\n        - name: accessLevel\n          in: query\n          type: integer\n          required: false\n          description: Access level.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: neighborhood-stats\n \
  \     path: /api/home/details/neighborhoodStats/statsInfo\n      description: Neighborhood statistics including demographics, walk/transit scores.\n      operations:\n      - name: get-neighborhood-stats\n        method: GET\n        description: Get neighborhood statistics for a property location.\n        inputParameters:\n        - name: propertyId\n          in: query\n          type: integer\n          required: true\n          description: Redfin property identifier.\n        - name: accessLevel\n          in: query\n          type: integer\n          required: false\n          description: Access level.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commute-info\n      path: /api/home/details/commute/commuteInfo\n      description: Commute time estimates for drive, transit, bike, and walk.\n      operations:\n      - name: get-commute-info\n        method: GET\n        description: Get commute\
  \ information including transit and drive times.\n        inputParameters:\n        - name: propertyId\n          in: query\n          type: integer\n          required: true\n          description: Redfin property identifier.\n        - name: accessLevel\n          in: query\n          type: integer\n          required: false\n          description: Access level.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: region-trends\n      path: /api/region/{regionType}/{regionId}/{code}/trends\n      description: Market trend data for a region.\n      operations:\n      - name: get-region-trends\n        method: GET\n        description: Get market trend data for a region including prices and sales volume.\n        inputParameters:\n        - name: regionType\n          in: path\n          type: string\n          required: true\n          description: Region type (neighborhood, zipcode, city, county).\n\
  \        - name: regionId\n          in: path\n          type: integer\n          required: true\n          description: Region identifier.\n        - name: code\n          in: path\n          type: string\n          required: true\n          description: Region code.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: redfin-data-center\n    baseUri: https://redfin-public-data.s3.us-west-2.amazonaws.com\n    description: Redfin Data Center S3 bucket for housing market datasets.\n    resources:\n    - name: national-market-tracker\n      path: /redfin_market_tracker/us_national_market_tracker.tsv000.gz\n      description: National-level housing market tracker dataset.\n      operations:\n      - name: download-national-market-tracker\n        method: GET\n        description: Download national aggregate housing market data in compressed TSV format.\n        outputRawFormat: binary\n\
  \        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: metro-market-tracker\n      path: /redfin_market_tracker/redfin_metro_market_tracker.tsv000.gz\n      description: Metro-level housing market tracker dataset.\n      operations:\n      - name: download-metro-market-tracker\n        method: GET\n        description: Download metro MSA housing market data in compressed TSV format.\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: state-market-tracker\n      path: /redfin_market_tracker/state_market_tracker.tsv000.gz\n      description: State-level housing market tracker dataset.\n      operations:\n      - name: download-state-market-tracker\n        method: GET\n        description: Download state-level housing market data in compressed TSV format.\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n      \
  \    type: string\n          value: $.\n    - name: county-market-tracker\n      path: /redfin_market_tracker/county_market_tracker.tsv000.gz\n      description: County-level housing market tracker dataset.\n      operations:\n      - name: download-county-market-tracker\n        method: GET\n        description: Download county-level housing market data in compressed TSV format.\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: city-market-tracker\n      path: /redfin_market_tracker/city_market_tracker.tsv000.gz\n      description: City-level housing market tracker dataset.\n      operations:\n      - name: download-city-market-tracker\n        method: GET\n        description: Download city-level housing market data in compressed TSV format.\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: zip-code-market-tracker\n\
  \      path: /redfin_market_tracker/zip_code_market_tracker.tsv000.gz\n      description: ZIP code-level housing market tracker dataset.\n      operations:\n      - name: download-zip-code-market-tracker\n        method: GET\n        description: Download ZIP code housing market data in compressed TSV format.\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: neighborhood-market-tracker\n      path: /redfin_market_tracker/neighborhood_market_tracker.tsv000.gz\n      description: Neighborhood-level housing market tracker dataset.\n      operations:\n      - name: download-neighborhood-market-tracker\n        method: GET\n        description: Download neighborhood housing market data in compressed TSV format.\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: redfin-market-analytics-api\n\
  \    description: Unified REST API for Redfin housing market analytics and data downloads.\n    resources:\n    - path: /v1/trends/{regionType}/{regionId}/{code}\n      name: regional-trends\n      description: Regional market trends from Stingray API.\n      operations:\n      - method: GET\n        name: get-region-trends\n        description: Get market trend data for a region including prices, volume, and days on market.\n        call: redfin-stingray.get-region-trends\n        with:\n          regionType: rest.regionType\n          regionId: rest.regionId\n          code: rest.code\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/market-data/national\n      name: national-market-data\n      description: National housing market tracker download.\n      operations:\n      - method: GET\n        name: get-national-market-data\n        description: Download national housing market tracker dataset (compressed TSV).\n        call: redfin-data-center.download-national-market-tracker\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/market-data/metro\n      name: metro-market-data\n      description: Metro-level housing market tracker download.\n      operations:\n      - method: GET\n        name: get-metro-market-data\n        description: Download metro MSA housing market tracker dataset (compressed TSV).\n        call: redfin-data-center.download-metro-market-tracker\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/market-data/state\n      name: state-market-data\n      description: State-level housing market tracker download.\n      operations:\n      - method: GET\n        name: get-state-market-data\n        description: Download state-level housing market tracker dataset (compressed TSV).\n        call: redfin-data-center.download-state-market-tracker\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/market-data/county\n      name: county-market-data\n\
  \      description: County-level housing market tracker download.\n      operations:\n      - method: GET\n        name: get-county-market-data\n        description: Download county-level housing market tracker dataset (compressed TSV).\n        call: redfin-data-center.download-county-market-tracker\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/market-data/city\n      name: city-market-data\n      description: City-level housing market tracker download.\n      operations:\n      - method: GET\n        name: get-city-market-data\n        description: Download city-level housing market tracker dataset (compressed TSV).\n        call: redfin-data-center.download-city-market-tracker\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/market-data/zip-code\n      name: zip-code-market-data\n      description: ZIP code-level housing market tracker download.\n      operations:\n      - method: GET\n        name:\
  \ get-zip-code-market-data\n        description: Download ZIP code housing market tracker dataset (compressed TSV).\n        call: redfin-data-center.download-zip-code-market-tracker\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/market-data/neighborhood\n      name: neighborhood-market-data\n      description: Neighborhood-level housing market tracker download.\n      operations:\n      - method: GET\n        name: get-neighborhood-market-data\n        description: Download neighborhood housing market tracker dataset (compressed TSV).\n        call: redfin-data-center.download-neighborhood-market-tracker\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: redfin-market-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted Redfin housing market analytics.\n    tools:\n    - name: get-region-trends\n      description: 'Get housing market trends for a\
  \ specific region: prices, volume, days on market, inventory.'\n      hints:\n        readOnly: true\n        openWorld: true\n      call: redfin-stingray.get-region-trends\n      with:\n        regionType: tools.regionType\n        regionId: tools.regionId\n        code: tools.code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-national-market-data\n      description: Download Redfin national housing market tracker dataset with all key metrics.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: redfin-data-center.download-national-market-tracker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-metro-market-data\n      description: Download Redfin metro MSA housing market tracker dataset.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: redfin-data-center.download-metro-market-tracker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-state-market-data\n      description: Download Redfin state-level housing market tracker dataset.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: redfin-data-center.download-state-market-tracker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-city-market-data\n      description: Download Redfin city-level housing market tracker dataset.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: redfin-data-center.download-city-market-tracker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-zip-code-market-data\n      description: Download Redfin ZIP code housing market tracker dataset (most granular).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: redfin-data-center.download-zip-code-market-tracker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-neighborhood-market-data\n      description: Download\
  \ Redfin neighborhood-level housing market tracker dataset.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: redfin-data-center.download-neighborhood-market-tracker\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/redfin/refs/heads/main/capabilities/market-analytics.yaml
tags:
- Redfin
- Housing Market
- Market Analytics
- Real Estate
- Statistics
- Data Science
tools:
- description: 'Get housing market trends for a specific region: prices, volume, days on market, inventory.'
  hints:
    openWorld: true
    readOnly: true
  name: get-region-trends
- description: Download Redfin national housing market tracker dataset with all key metrics.
  hints:
    openWorld: false
    readOnly: true
  name: get-national-market-data
- description: Download Redfin metro MSA housing market tracker dataset.
  hints:
    openWorld: false
    readOnly: true
  name: get-metro-market-data
- description: Download Redfin state-level housing market tracker dataset.
  hints:
    openWorld: false
    readOnly: true
  name: get-state-market-data
- description: Download Redfin city-level housing market tracker dataset.
  hints:
    openWorld: false
    readOnly: true
  name: get-city-market-data
- description: Download Redfin ZIP code housing market tracker dataset (most granular).
  hints:
    openWorld: false
    readOnly: true
  name: get-zip-code-market-data
- description: Download Redfin neighborhood-level housing market tracker dataset.
  hints:
    openWorld: false
    readOnly: true
  name: get-neighborhood-market-data
---
