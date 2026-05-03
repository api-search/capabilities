---
categories: []
consumed_apis:
- redfin-stingray
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
- get property history
- get neighborhood demographics, walkability, and school ratings.
- property data
- housing market
- 'get core listing details for a property: price, beds, baths, square footage, and status.'
- home values
- csv export
- get historical redfin estimate data showing value trends over time.
- historical redfin estimate (avm) valuations.
- get drive, transit, bike, and walk commute estimates.
- real estate
- neighborhoods
- get neighborhood statistics including walkability, transit, and school ratings.
- get below-the-fold property details with mls data, history, and school info.
- search and browse property listings.
- property research
- search properties
- commute time estimates for the property.
- primary listing details for a property.
- get property estimate
- get neighborhood stats
- get property summary
- search redfin property listings by region, price range, and property type filters.
- get mls data, sales history, tax records, and schools for a property.
- get commute info
- get historical redfin estimate (avm) showing property value trends over time.
- get redfin estimate
- detailed mls data, history, schools, and similar homes.
- search properties by region, price range, property type, and filters.
- gis
- redfin
- neighborhood statistics and location context.
- listings
- get commute time estimates (drive, transit, bike, walk) for a property.
- get property details
- 'get above-the-fold details: price, beds, baths, address, and status.'
slug: property-research
source_filename: property-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Redfin Property Research\"\n  description: >-\n    Unified capability for researching individual properties on Redfin.\n    Combines property search, listing details, AVM estimates, neighborhood\n    statistics, and commute data to support buyers, investors, and agents\n    researching specific properties or locations.\n  tags:\n    - Redfin\n    - Property Research\n    - Real Estate\n    - Home Values\n    - Neighborhoods\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REDFIN_API_KEY: REDFIN_API_KEY\n\ncapability:\n  consumes:\n    - import: redfin-stingray\n      location: ./shared/stingray-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: redfin-property-research-api\n      description: \"Unified REST API for researching Redfin property listings.\"\n      resources:\n        - path: /v1/properties\n          name: properties\n          description:\
  \ \"Search and browse property listings.\"\n          operations:\n            - method: GET\n              name: search-properties\n              description: \"Search properties by region, price range, property type, and filters.\"\n              call: \"redfin-stingray.gis-search\"\n              with:\n                region_id: \"rest.region_id\"\n                region_type: \"rest.region_type\"\n                uipt: \"rest.uipt\"\n                status: \"rest.status\"\n                min_price: \"rest.min_price\"\n                max_price: \"rest.max_price\"\n                num_beds: \"rest.num_beds\"\n                num_baths: \"rest.num_baths\"\n                num_homes: \"rest.num_homes\"\n                page_number: \"rest.page_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/properties/{propertyId}/summary\n          name: property-summary\n          description: \"Primary listing details\
  \ for a property.\"\n          operations:\n            - method: GET\n              name: get-property-summary\n              description: \"Get above-the-fold details: price, beds, baths, address, and status.\"\n              call: \"redfin-stingray.get-above-the-fold\"\n              with:\n                propertyId: \"rest.propertyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/properties/{propertyId}/details\n          name: property-details\n          description: \"Detailed MLS data, history, schools, and similar homes.\"\n          operations:\n            - method: GET\n              name: get-property-details\n              description: \"Get below-the-fold property details with MLS data, history, and school info.\"\n              call: \"redfin-stingray.get-below-the-fold\"\n              with:\n                propertyId: \"rest.propertyId\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n        - path: /v1/properties/{propertyId}/estimate\n          name: property-estimate\n          description: \"Historical Redfin Estimate (AVM) valuations.\"\n          operations:\n            - method: GET\n              name: get-property-estimate\n              description: \"Get historical Redfin Estimate data showing value trends over time.\"\n              call: \"redfin-stingray.get-avm-historical-data\"\n              with:\n                propertyId: \"rest.propertyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/properties/{propertyId}/neighborhood\n          name: property-neighborhood\n          description: \"Neighborhood statistics and location context.\"\n          operations:\n            - method: GET\n              name: get-neighborhood-stats\n              description: \"Get neighborhood demographics, walkability, and school ratings.\"\n\
  \              call: \"redfin-stingray.get-neighborhood-stats\"\n              with:\n                propertyId: \"rest.propertyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/properties/{propertyId}/commute\n          name: property-commute\n          description: \"Commute time estimates for the property.\"\n          operations:\n            - method: GET\n              name: get-commute-info\n              description: \"Get drive, transit, bike, and walk commute estimates.\"\n              call: \"redfin-stingray.get-commute-info\"\n              with:\n                propertyId: \"rest.propertyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: redfin-property-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Redfin property research.\"\n      tools:\n      \
  \  - name: search-properties\n          description: \"Search Redfin property listings by region, price range, and property type filters.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"redfin-stingray.gis-search\"\n          with:\n            region_id: \"tools.region_id\"\n            region_type: \"tools.region_type\"\n            uipt: \"tools.uipt\"\n            min_price: \"tools.min_price\"\n            max_price: \"tools.max_price\"\n            num_beds: \"tools.num_beds\"\n            num_baths: \"tools.num_baths\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-property-summary\n          description: \"Get core listing details for a property: price, beds, baths, square footage, and status.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"redfin-stingray.get-above-the-fold\"\n          with:\n            propertyId: \"\
  tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-property-history\n          description: \"Get MLS data, sales history, tax records, and schools for a property.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"redfin-stingray.get-below-the-fold\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-redfin-estimate\n          description: \"Get historical Redfin Estimate (AVM) showing property value trends over time.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"redfin-stingray.get-avm-historical-data\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-neighborhood-stats\n\
  \          description: \"Get neighborhood statistics including walkability, transit, and school ratings.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"redfin-stingray.get-neighborhood-stats\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-commute-info\n          description: \"Get commute time estimates (drive, transit, bike, walk) for a property.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"redfin-stingray.get-commute-info\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
