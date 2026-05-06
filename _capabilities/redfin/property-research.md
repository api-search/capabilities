---
categories: []
consumed_apis: []
description: Unified capability for researching individual properties on Redfin. Combines property search, listing details, AVM estimates, neighborhood statistics, and commute data to support buyers, investors, and agents researching specific properties or locations.
layout: capability
name: Redfin Property Research
operations:
- description: Search properties by region, price range, property type, and filters.
  method: GET
  name: search-properties
  path: /v1/properties
- description: 'Get above-the-fold details: price, beds, baths, address, and status.'
  method: GET
  name: get-property-summary
  path: /v1/properties/{propertyId}/summary
- description: Get below-the-fold property details with MLS data, history, and school info.
  method: GET
  name: get-property-details
  path: /v1/properties/{propertyId}/details
- description: Get historical Redfin Estimate data showing value trends over time.
  method: GET
  name: get-property-estimate
  path: /v1/properties/{propertyId}/estimate
- description: Get neighborhood demographics, walkability, and school ratings.
  method: GET
  name: get-neighborhood-stats
  path: /v1/properties/{propertyId}/neighborhood
- description: Get drive, transit, bike, and walk commute estimates.
  method: GET
  name: get-commute-info
  path: /v1/properties/{propertyId}/commute
personas: []
provider_name: Redfin
provider_slug: redfin
search_terms:
- search and browse property listings.
- redfin
- neighborhood statistics and location context.
- get historical redfin estimate data showing value trends over time.
- historical redfin estimate (avm) valuations.
- get property estimate
- search properties
- home values
- get neighborhood statistics including walkability, transit, and school ratings.
- neighborhoods
- get neighborhood demographics, walkability, and school ratings.
- get mls data, sales history, tax records, and schools for a property.
- detailed mls data, history, schools, and similar homes.
- real estate
- get property summary
- get property details
- get redfin estimate
- property data
- primary listing details for a property.
- get drive, transit, bike, and walk commute estimates.
- get commute time estimates (drive, transit, bike, walk) for a property.
- search properties by region, price range, property type, and filters.
- housing market
- csv export
- 'get core listing details for a property: price, beds, baths, square footage, and status.'
- get below-the-fold property details with mls data, history, and school info.
- commute time estimates for the property.
- search redfin property listings by region, price range, and property type filters.
- get historical redfin estimate (avm) showing property value trends over time.
- gis
- get property history
- listings
- property research
- get commute info
- get neighborhood stats
- 'get above-the-fold details: price, beds, baths, address, and status.'
slug: property-research
source_filename: property-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Redfin Property Research\n  description: Unified capability for researching individual properties on Redfin. Combines property search, listing details,\n    AVM estimates, neighborhood statistics, and commute data to support buyers, investors, and agents researching specific\n    properties or locations.\n  tags:\n  - Redfin\n  - Property Research\n  - Real Estate\n  - Home Values\n  - Neighborhoods\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REDFIN_API_KEY: REDFIN_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: redfin-stingray\n    baseUri: https://www.redfin.com/stingray\n    description: Redfin Stingray REST API for property search and details.\n    resources:\n    - name: property-search\n      path: /do/gis-search\n      description: GIS-based property search with filters.\n      operations:\n      - name: gis-search\n        method: GET\n        description: Search\
  \ properties via GIS with region, price, and property type filters.\n        inputParameters:\n        - name: region_id\n          in: query\n          type: integer\n          required: false\n          description: Unique identifier for a Redfin region.\n        - name: region_type\n          in: query\n          type: integer\n          required: false\n          description: Region type code (1=neighborhood, 2=zip, 5=county, 6=city).\n        - name: uipt\n          in: query\n          type: string\n          required: false\n          description: 'Property type filter (comma-separated: 1=house, 2=condo, 3=townhouse).'\n        - name: status\n          in: query\n          type: integer\n          required: false\n          description: Listing status filter (1=active, 130=pending).\n        - name: min_price\n          in: query\n          type: integer\n          required: false\n          description: Minimum listing price in USD.\n        - name: max_price\n          in: query\n\
  \          type: integer\n          required: false\n          description: Maximum listing price in USD.\n        - name: num_beds\n          in: query\n          type: integer\n          required: false\n          description: Minimum number of bedrooms.\n        - name: num_baths\n          in: query\n          type: integer\n          required: false\n          description: Minimum number of bathrooms.\n        - name: num_homes\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return.\n        - name: page_number\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: property-search-api\n      path: /api/gis\n      description: Alternative GIS property search endpoint.\n      operations:\n      - name: gis-api-search\n\
  \        method: GET\n        description: Alternative GIS-based property search returning JSON results.\n        inputParameters:\n        - name: region_id\n          in: query\n          type: integer\n          required: false\n          description: Region identifier.\n        - name: region_type\n          in: query\n          type: integer\n          required: false\n          description: Region type code.\n        - name: num_homes\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: property-initial-info\n      path: /api/home/details/initialInfo\n      description: Initial property info returning propertyId and listingId.\n      operations:\n      - name: get-initial-info\n        method: GET\n        description: Retrieve initial property identifiers from a Redfin\
  \ URL path.\n        inputParameters:\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: Redfin property URL path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: property-above-fold\n      path: /api/home/details/aboveTheFold\n      description: 'Primary property details: price, address, photos, and listing status.'\n      operations:\n      - name: get-above-the-fold\n        method: GET\n        description: Get above-the-fold property details including price, beds, baths, and sq ft.\n        inputParameters:\n        - name: propertyId\n          in: query\n          type: integer\n          required: true\n          description: Redfin property identifier.\n        - name: listingId\n          in: query\n          type: integer\n          required: false\n          description: Redfin listing identifier.\n        - name: accessLevel\n\
  \          in: query\n          type: integer\n          required: false\n          description: Access level controlling data detail.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: property-below-fold\n      path: /api/home/details/belowTheFold\n      description: Detailed MLS data, tax info, schools, and property history.\n      operations:\n      - name: get-below-the-fold\n        method: GET\n        description: Get below-the-fold property details with MLS data, history, and schools.\n        inputParameters:\n        - name: propertyId\n          in: query\n          type: integer\n          required: true\n          description: Redfin property identifier.\n        - name: listingId\n          in: query\n          type: integer\n          required: false\n          description: Redfin listing identifier.\n        - name: accessLevel\n          in: query\n          type: integer\n      \
  \    required: false\n          description: Access level.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: property-avm\n      path: /api/home/details/avmHistoricalData\n      description: Historical AVM (Redfin Estimate) time-series data.\n      operations:\n      - name: get-avm-historical-data\n        method: GET\n        description: Retrieve historical Redfin Estimate valuations for a property.\n        inputParameters:\n        - name: propertyId\n          in: query\n          type: integer\n          required: true\n          description: Redfin property identifier.\n        - name: accessLevel\n          in: query\n          type: integer\n          required: false\n          description: Access level.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: neighborhood-stats\n      path: /api/home/details/neighborhoodStats/statsInfo\n\
  \      description: Neighborhood statistics including demographics, walk/transit scores.\n      operations:\n      - name: get-neighborhood-stats\n        method: GET\n        description: Get neighborhood statistics for a property location.\n        inputParameters:\n        - name: propertyId\n          in: query\n          type: integer\n          required: true\n          description: Redfin property identifier.\n        - name: accessLevel\n          in: query\n          type: integer\n          required: false\n          description: Access level.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commute-info\n      path: /api/home/details/commute/commuteInfo\n      description: Commute time estimates for drive, transit, bike, and walk.\n      operations:\n      - name: get-commute-info\n        method: GET\n        description: Get commute information including transit and drive times.\n  \
  \      inputParameters:\n        - name: propertyId\n          in: query\n          type: integer\n          required: true\n          description: Redfin property identifier.\n        - name: accessLevel\n          in: query\n          type: integer\n          required: false\n          description: Access level.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: region-trends\n      path: /api/region/{regionType}/{regionId}/{code}/trends\n      description: Market trend data for a region.\n      operations:\n      - name: get-region-trends\n        method: GET\n        description: Get market trend data for a region including prices and sales volume.\n        inputParameters:\n        - name: regionType\n          in: path\n          type: string\n          required: true\n          description: Region type (neighborhood, zipcode, city, county).\n        - name: regionId\n          in: path\n   \
  \       type: integer\n          required: true\n          description: Region identifier.\n        - name: code\n          in: path\n          type: string\n          required: true\n          description: Region code.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: redfin-property-research-api\n    description: Unified REST API for researching Redfin property listings.\n    resources:\n    - path: /v1/properties\n      name: properties\n      description: Search and browse property listings.\n      operations:\n      - method: GET\n        name: search-properties\n        description: Search properties by region, price range, property type, and filters.\n        call: redfin-stingray.gis-search\n        with:\n          region_id: rest.region_id\n          region_type: rest.region_type\n          uipt: rest.uipt\n          status: rest.status\n  \
  \        min_price: rest.min_price\n          max_price: rest.max_price\n          num_beds: rest.num_beds\n          num_baths: rest.num_baths\n          num_homes: rest.num_homes\n          page_number: rest.page_number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/{propertyId}/summary\n      name: property-summary\n      description: Primary listing details for a property.\n      operations:\n      - method: GET\n        name: get-property-summary\n        description: 'Get above-the-fold details: price, beds, baths, address, and status.'\n        call: redfin-stingray.get-above-the-fold\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/{propertyId}/details\n      name: property-details\n      description: Detailed MLS data, history, schools, and similar homes.\n      operations:\n      - method: GET\n        name: get-property-details\n\
  \        description: Get below-the-fold property details with MLS data, history, and school info.\n        call: redfin-stingray.get-below-the-fold\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/{propertyId}/estimate\n      name: property-estimate\n      description: Historical Redfin Estimate (AVM) valuations.\n      operations:\n      - method: GET\n        name: get-property-estimate\n        description: Get historical Redfin Estimate data showing value trends over time.\n        call: redfin-stingray.get-avm-historical-data\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/{propertyId}/neighborhood\n      name: property-neighborhood\n      description: Neighborhood statistics and location context.\n      operations:\n      - method: GET\n        name: get-neighborhood-stats\n\
  \        description: Get neighborhood demographics, walkability, and school ratings.\n        call: redfin-stingray.get-neighborhood-stats\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/{propertyId}/commute\n      name: property-commute\n      description: Commute time estimates for the property.\n      operations:\n      - method: GET\n        name: get-commute-info\n        description: Get drive, transit, bike, and walk commute estimates.\n        call: redfin-stingray.get-commute-info\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: redfin-property-research-mcp\n    transport: http\n    description: MCP server for AI-assisted Redfin property research.\n    tools:\n    - name: search-properties\n      description: Search Redfin property listings by region,\
  \ price range, and property type filters.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: redfin-stingray.gis-search\n      with:\n        region_id: tools.region_id\n        region_type: tools.region_type\n        uipt: tools.uipt\n        min_price: tools.min_price\n        max_price: tools.max_price\n        num_beds: tools.num_beds\n        num_baths: tools.num_baths\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-property-summary\n      description: 'Get core listing details for a property: price, beds, baths, square footage, and status.'\n      hints:\n        readOnly: true\n        openWorld: true\n      call: redfin-stingray.get-above-the-fold\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-property-history\n      description: Get MLS data, sales history, tax records, and schools for a property.\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: redfin-stingray.get-below-the-fold\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-redfin-estimate\n      description: Get historical Redfin Estimate (AVM) showing property value trends over time.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: redfin-stingray.get-avm-historical-data\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-neighborhood-stats\n      description: Get neighborhood statistics including walkability, transit, and school ratings.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: redfin-stingray.get-neighborhood-stats\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-commute-info\n      description: Get commute time\
  \ estimates (drive, transit, bike, walk) for a property.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: redfin-stingray.get-commute-info\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/redfin/refs/heads/main/capabilities/property-research.yaml
tags:
- Redfin
- Property Research
- Real Estate
- Home Values
- Neighborhoods
tools:
- description: Search Redfin property listings by region, price range, and property type filters.
  hints:
    openWorld: true
    readOnly: true
  name: search-properties
- description: 'Get core listing details for a property: price, beds, baths, square footage, and status.'
  hints:
    openWorld: true
    readOnly: true
  name: get-property-summary
- description: Get MLS data, sales history, tax records, and schools for a property.
  hints:
    openWorld: true
    readOnly: true
  name: get-property-history
- description: Get historical Redfin Estimate (AVM) showing property value trends over time.
  hints:
    openWorld: true
    readOnly: true
  name: get-redfin-estimate
- description: Get neighborhood statistics including walkability, transit, and school ratings.
  hints:
    openWorld: true
    readOnly: true
  name: get-neighborhood-stats
- description: Get commute time estimates (drive, transit, bike, walk) for a property.
  hints:
    openWorld: true
    readOnly: true
  name: get-commute-info
---
