---
api_specs:
- filename: shovels-openapi.yml
  format: yaml
  label: shovels
  slug: shovels
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/shovels/refs/heads/main/openapi/shovels-openapi.yml
categories: []
consumed_apis:
- shovels
description: 'Workflow capability for identifying qualified contractors, researching their work history, accessing decision maker contacts, and analyzing market activity. Combines permit search, contractor search, employee lookup, and geographic metrics into a unified contractor sales and marketing intelligence workflow. Primary users: materials suppliers, construction tech companies, home services firms, and energy/climate companies targeting contractors.'
layout: capability
name: Shovels Contractor Intelligence
operations:
- description: Search contractors by geography, specialty, and quality metrics
  method: GET
  name: search-contractors
  path: /v1/contractors
- description: Get detailed contractor profile by ID
  method: GET
  name: get-contractor
  path: /v1/contractors/{id}
- description: Retrieve permit history for a contractor
  method: GET
  name: get-contractor-permits
  path: /v1/contractors/{id}/permits
- description: Get employee contact list for a contractor
  method: GET
  name: get-contractor-employees
  path: /v1/contractors/{id}/employees
- description: Get permit performance metrics for a contractor
  method: GET
  name: get-contractor-metrics
  path: /v1/contractors/{id}/metrics
- description: Search building permits by geography, type, and date range
  method: GET
  name: search-permits
  path: /v1/permits
- description: Get a specific permit by ID
  method: GET
  name: get-permit
  path: /v1/permits/{id}
- description: Search addresses that have associated permits
  method: GET
  name: search-addresses
  path: /v1/addresses
- description: Get resident contact information for an address
  method: GET
  name: get-residents
  path: /v1/addresses/{geo_id}/residents
- description: Get current permit activity metrics for a geographic area
  method: GET
  name: get-address-metrics
  path: /v1/market/{geo_id}/metrics
- description: Search for cities to get geo_id values
  method: GET
  name: search-cities
  path: /v1/geography/cities
- description: Search for US states to get geo_id values
  method: GET
  name: search-states
  path: /v1/geography/states
- description: Get all available permit type tags for filtering
  method: GET
  name: get-tags
  path: /v1/tags
personas: []
provider_name: Shovels
provider_slug: shovels
search_terms:
- sales intelligence
- search and retrieve qualified contractor profiles
- get employee contact list for a contractor
- search for cities to get geo_id values
- search for us states to resolve geo_id values.
- search permits
- search addresses
- all permits associated with a contractor
- property data
- get tags
- get the list of employees and decision makers at a contractor company, including names, titles, phone numbers, and email addresses for sales outreach.
- search contractors by geography, specialty, and quality metrics
- search for city names to resolve geo_id values for use in permit and contractor searches.
- get address metrics
- get resident contact information for an address
- get a specific permit by id
- get contractor
- search contractors
- get details for a specific building permit by id.
- market analytics
- full contractor profile with metrics
- get all available permit classification tags (solar, roofing, hvac, electrical, plumbing, adu, etc.) for use as filter values in permit and contractor searches.
- get permit tags
- contractors
- address search and lookup
- retrieve the complete permit history for a contractor, showing all projects undertaken, job values, locations, and permit statuses.
- get contractor permits
- residents at a permit address
- available permit classification tags
- get resident contact information for a specific address, useful for homeowner outreach related to nearby permit activity.
- search for us property addresses that have at least one associated permit. returns address records with geo_id values needed for metric queries.
- get current permit activity metrics for a geographic area including permit count, active permits, average job value, and contractor count.
- decision makers and employees at a contractor company
- get detailed contractor profile by id
- lead generation
- search building permits by geography and date range. filter by permit type (tags), property type, status, and job value range to identify market opportunities and active construction activity.
- performance metrics for a contractor
- get detailed profile for a specific contractor by id, including business details, contact information, license, classification, and permit statistics.
- retrieve permit history for a contractor
- building permit search for market research
- get contractor employees
- individual permit details
- get all available permit type tags for filtering
- get address residents
- market intelligence
- search addresses that have associated permits
- get permit
- market activity metrics for a geography
- search states
- search for licensed contractors in a geographic area filtered by specialty, date range, and quality metrics like inspection pass rate. returns contractor profiles with contact information and permit statistics.
- get contractor metrics
- construction
- search for us states to get geo_id values
- search building permits by geography, type, and date range
- get current permit activity metrics for a geographic area
- get market metrics
- city lookup for geo_id resolution
- building permits
- get permit performance metrics for a contractor
- state lookup for geo_id resolution
- real estate
- get residents
- search cities
- get performance metrics for a contractor including inspection pass rate, average job value, total job value, and active permit count.
slug: contractor-intelligence
source_filename: contractor-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Shovels Contractor Intelligence\"\n  description: >-\n    Workflow capability for identifying qualified contractors, researching their\n    work history, accessing decision maker contacts, and analyzing market activity.\n    Combines permit search, contractor search, employee lookup, and geographic\n    metrics into a unified contractor sales and marketing intelligence workflow.\n    Primary users: materials suppliers, construction tech companies, home services\n    firms, and energy/climate companies targeting contractors.\n  tags:\n    - Construction\n    - Contractors\n    - Building Permits\n    - Sales Intelligence\n    - Market Analytics\n    - Lead Generation\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SHOVELS_API_KEY: SHOVELS_API_KEY\n\ncapability:\n  consumes:\n    - import: shovels\n      location: ./shared/shovels.yaml\n\n  exposes:\n    - type: rest\n      port:\
  \ 8080\n      namespace: shovels-contractor-intelligence-api\n      description: \"Unified REST API for contractor intelligence and permit market analytics.\"\n      resources:\n        - path: /v1/contractors\n          name: contractors\n          description: Search and retrieve qualified contractor profiles\n          operations:\n            - method: GET\n              name: search-contractors\n              description: Search contractors by geography, specialty, and quality metrics\n              call: \"shovels.search-contractors\"\n              with:\n                geo_id: \"rest.geo_id\"\n                permit_from: \"rest.permit_from\"\n                permit_to: \"rest.permit_to\"\n                tags: \"rest.tags\"\n                min_inspection_pass_rate: \"rest.min_inspection_pass_rate\"\n                size: \"rest.size\"\n                cursor: \"rest.cursor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \n        - path: /v1/contractors/{id}\n          name: contractor-detail\n          description: Full contractor profile with metrics\n          operations:\n            - method: GET\n              name: get-contractor\n              description: Get detailed contractor profile by ID\n              call: \"shovels.get-contractor-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/contractors/{id}/permits\n          name: contractor-permits\n          description: All permits associated with a contractor\n          operations:\n            - method: GET\n              name: get-contractor-permits\n              description: Retrieve permit history for a contractor\n              call: \"shovels.get-contractor-permits\"\n              with:\n                id: \"rest.id\"\n                cursor: \"rest.cursor\"\n                size: \"rest.size\"\n   \
  \           outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/contractors/{id}/employees\n          name: contractor-employees\n          description: Decision makers and employees at a contractor company\n          operations:\n            - method: GET\n              name: get-contractor-employees\n              description: Get employee contact list for a contractor\n              call: \"shovels.get-contractor-employees\"\n              with:\n                id: \"rest.id\"\n                cursor: \"rest.cursor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/contractors/{id}/metrics\n          name: contractor-metrics\n          description: Performance metrics for a contractor\n          operations:\n            - method: GET\n              name: get-contractor-metrics\n              description: Get permit performance metrics for a contractor\n\
  \              call: \"shovels.get-contractor-metrics\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/permits\n          name: permits\n          description: Building permit search for market research\n          operations:\n            - method: GET\n              name: search-permits\n              description: Search building permits by geography, type, and date range\n              call: \"shovels.search-permits\"\n              with:\n                geo_id: \"rest.geo_id\"\n                permit_from: \"rest.permit_from\"\n                permit_to: \"rest.permit_to\"\n                tags: \"rest.tags\"\n                property_type: \"rest.property_type\"\n                status: \"rest.status\"\n                min_job_value: \"rest.min_job_value\"\n                size: \"rest.size\"\n                cursor: \"rest.cursor\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/permits/{id}\n          name: permit-detail\n          description: Individual permit details\n          operations:\n            - method: GET\n              name: get-permit\n              description: Get a specific permit by ID\n              call: \"shovels.get-permit-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/addresses\n          name: addresses\n          description: Address search and lookup\n          operations:\n            - method: GET\n              name: search-addresses\n              description: Search addresses that have associated permits\n              call: \"shovels.search-addresses\"\n              with:\n                q: \"rest.q\"\n                cursor: \"rest.cursor\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n        - path: /v1/addresses/{geo_id}/residents\n          name: address-residents\n          description: Residents at a permit address\n          operations:\n            - method: GET\n              name: get-residents\n              description: Get resident contact information for an address\n              call: \"shovels.get-address-residents\"\n              with:\n                geo_id: \"rest.geo_id\"\n                cursor: \"rest.cursor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/market/{geo_id}/metrics\n          name: market-metrics\n          description: Market activity metrics for a geography\n          operations:\n            - method: GET\n              name: get-address-metrics\n              description: Get current permit activity metrics for a geographic area\n              call: \"shovels.get-address-metrics-current\"\n              with:\n \
  \               geo_id: \"rest.geo_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/geography/cities\n          name: cities\n          description: City lookup for geo_id resolution\n          operations:\n            - method: GET\n              name: search-cities\n              description: Search for cities to get geo_id values\n              call: \"shovels.search-cities\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/geography/states\n          name: states\n          description: State lookup for geo_id resolution\n          operations:\n            - method: GET\n              name: search-states\n              description: Search for US states to get geo_id values\n              call: \"shovels.search-states\"\n              with:\n                q: \"rest.q\"\n        \
  \      outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tags\n          name: permit-tags\n          description: Available permit classification tags\n          operations:\n            - method: GET\n              name: get-tags\n              description: Get all available permit type tags for filtering\n              call: \"shovels.get-tags\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: shovels-contractor-intelligence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted contractor research and permit market intelligence.\"\n      tools:\n        - name: search-contractors\n          description: >-\n            Search for licensed contractors in a geographic area filtered by specialty,\n            date range, and quality metrics like inspection pass rate. Returns contractor\n            profiles\
  \ with contact information and permit statistics.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shovels.search-contractors\"\n          with:\n            geo_id: \"tools.geo_id\"\n            permit_from: \"tools.permit_from\"\n            permit_to: \"tools.permit_to\"\n            tags: \"tools.tags\"\n            min_inspection_pass_rate: \"tools.min_inspection_pass_rate\"\n            size: \"tools.size\"\n            cursor: \"tools.cursor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-contractor\n          description: >-\n            Get detailed profile for a specific contractor by ID, including business\n            details, contact information, license, classification, and permit statistics.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shovels.get-contractor-by-id\"\n          with:\n            id: \"tools.id\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-contractor-permits\n          description: >-\n            Retrieve the complete permit history for a contractor, showing all\n            projects undertaken, job values, locations, and permit statuses.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shovels.get-contractor-permits\"\n          with:\n            id: \"tools.id\"\n            cursor: \"tools.cursor\"\n            size: \"tools.size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-contractor-employees\n          description: >-\n            Get the list of employees and decision makers at a contractor company,\n            including names, titles, phone numbers, and email addresses for sales outreach.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shovels.get-contractor-employees\"\
  \n          with:\n            id: \"tools.id\"\n            cursor: \"tools.cursor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-contractor-metrics\n          description: >-\n            Get performance metrics for a contractor including inspection pass rate,\n            average job value, total job value, and active permit count.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shovels.get-contractor-metrics\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-permits\n          description: >-\n            Search building permits by geography and date range. Filter by permit type\n            (tags), property type, status, and job value range to identify market\n            opportunities and active construction activity.\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"shovels.search-permits\"\n          with:\n            geo_id: \"tools.geo_id\"\n            permit_from: \"tools.permit_from\"\n            permit_to: \"tools.permit_to\"\n            tags: \"tools.tags\"\n            property_type: \"tools.property_type\"\n            status: \"tools.status\"\n            min_job_value: \"tools.min_job_value\"\n            size: \"tools.size\"\n            cursor: \"tools.cursor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-permit\n          description: Get details for a specific building permit by ID.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shovels.get-permit-by-id\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-addresses\n          description: >-\n           \
  \ Search for US property addresses that have at least one associated permit.\n            Returns address records with geo_id values needed for metric queries.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shovels.search-addresses\"\n          with:\n            q: \"tools.q\"\n            cursor: \"tools.cursor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-address-residents\n          description: >-\n            Get resident contact information for a specific address, useful for\n            homeowner outreach related to nearby permit activity.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shovels.get-address-residents\"\n          with:\n            geo_id: \"tools.geo_id\"\n            cursor: \"tools.cursor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-market-metrics\n\
  \          description: >-\n            Get current permit activity metrics for a geographic area including\n            permit count, active permits, average job value, and contractor count.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shovels.get-address-metrics-current\"\n          with:\n            geo_id: \"tools.geo_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-cities\n          description: Search for city names to resolve geo_id values for use in permit and contractor searches.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shovels.search-cities\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-states\n          description: Search for US states to resolve geo_id values.\n          hints:\n          \
  \  readOnly: true\n            openWorld: true\n          call: \"shovels.search-states\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-permit-tags\n          description: >-\n            Get all available permit classification tags (solar, roofing, hvac, electrical,\n            plumbing, adu, etc.) for use as filter values in permit and contractor searches.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shovels.get-tags\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shovels/refs/heads/main/capabilities/contractor-intelligence.yaml
tags:
- Construction
- Contractors
- Building Permits
- Sales Intelligence
- Market Analytics
- Lead Generation
tools:
- description: Search for licensed contractors in a geographic area filtered by specialty, date range, and quality metrics like inspection pass rate. Returns contractor profiles with contact information and permit statistics.
  hints:
    openWorld: true
    readOnly: true
  name: search-contractors
- description: Get detailed profile for a specific contractor by ID, including business details, contact information, license, classification, and permit statistics.
  hints:
    openWorld: false
    readOnly: true
  name: get-contractor
- description: Retrieve the complete permit history for a contractor, showing all projects undertaken, job values, locations, and permit statuses.
  hints:
    openWorld: false
    readOnly: true
  name: get-contractor-permits
- description: Get the list of employees and decision makers at a contractor company, including names, titles, phone numbers, and email addresses for sales outreach.
  hints:
    openWorld: false
    readOnly: true
  name: get-contractor-employees
- description: Get performance metrics for a contractor including inspection pass rate, average job value, total job value, and active permit count.
  hints:
    openWorld: false
    readOnly: true
  name: get-contractor-metrics
- description: Search building permits by geography and date range. Filter by permit type (tags), property type, status, and job value range to identify market opportunities and active construction activity.
  hints:
    openWorld: true
    readOnly: true
  name: search-permits
- description: Get details for a specific building permit by ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-permit
- description: Search for US property addresses that have at least one associated permit. Returns address records with geo_id values needed for metric queries.
  hints:
    openWorld: true
    readOnly: true
  name: search-addresses
- description: Get resident contact information for a specific address, useful for homeowner outreach related to nearby permit activity.
  hints:
    openWorld: false
    readOnly: true
  name: get-address-residents
- description: Get current permit activity metrics for a geographic area including permit count, active permits, average job value, and contractor count.
  hints:
    openWorld: false
    readOnly: true
  name: get-market-metrics
- description: Search for city names to resolve geo_id values for use in permit and contractor searches.
  hints:
    openWorld: true
    readOnly: true
  name: search-cities
- description: Search for US states to resolve geo_id values.
  hints:
    openWorld: true
    readOnly: true
  name: search-states
- description: Get all available permit classification tags (solar, roofing, hvac, electrical, plumbing, adu, etc.) for use as filter values in permit and contractor searches.
  hints:
    openWorld: false
    readOnly: true
  name: get-permit-tags
---
