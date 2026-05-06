---
categories: []
consumed_apis: []
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
- building permits
- get market metrics
- construction
- retrieve permit history for a contractor
- search for licensed contractors in a geographic area filtered by specialty, date range, and quality metrics like inspection pass rate. returns contractor profiles with contact information and permit statistics.
- search and retrieve qualified contractor profiles
- decision makers and employees at a contractor company
- search cities
- contractors
- search permits
- available permit classification tags
- get all available permit type tags for filtering
- get permit tags
- address search and lookup
- get contractor permits
- get current permit activity metrics for a geographic area including permit count, active permits, average job value, and contractor count.
- get a specific permit by id
- get detailed profile for a specific contractor by id, including business details, contact information, license, classification, and permit statistics.
- get permit performance metrics for a contractor
- retrieve the complete permit history for a contractor, showing all projects undertaken, job values, locations, and permit statuses.
- get detailed contractor profile by id
- get employee contact list for a contractor
- get residents
- get performance metrics for a contractor including inspection pass rate, average job value, total job value, and active permit count.
- get contractor employees
- real estate
- market activity metrics for a geography
- search for us states to get geo_id values
- property data
- get address residents
- get permit
- market analytics
- get resident contact information for an address
- sales intelligence
- state lookup for geo_id resolution
- get tags
- get resident contact information for a specific address, useful for homeowner outreach related to nearby permit activity.
- residents at a permit address
- search for city names to resolve geo_id values for use in permit and contractor searches.
- search for cities to get geo_id values
- performance metrics for a contractor
- get contractor
- search addresses that have associated permits
- get details for a specific building permit by id.
- search states
- search for us states to resolve geo_id values.
- search building permits by geography, type, and date range
- lead generation
- get address metrics
- get the list of employees and decision makers at a contractor company, including names, titles, phone numbers, and email addresses for sales outreach.
- get contractor metrics
- full contractor profile with metrics
- market intelligence
- search contractors
- get all available permit classification tags (solar, roofing, hvac, electrical, plumbing, adu, etc.) for use as filter values in permit and contractor searches.
- search addresses
- search contractors by geography, specialty, and quality metrics
- city lookup for geo_id resolution
- get current permit activity metrics for a geographic area
- all permits associated with a contractor
- building permit search for market research
- search building permits by geography and date range. filter by permit type (tags), property type, status, and job value range to identify market opportunities and active construction activity.
- search for us property addresses that have at least one associated permit. returns address records with geo_id values needed for metric queries.
- individual permit details
slug: contractor-intelligence
source_filename: contractor-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Shovels Contractor Intelligence\n  description: 'Workflow capability for identifying qualified contractors, researching their work history, accessing decision\n    maker contacts, and analyzing market activity. Combines permit search, contractor search, employee lookup, and geographic\n    metrics into a unified contractor sales and marketing intelligence workflow. Primary users: materials suppliers, construction\n    tech companies, home services firms, and energy/climate companies targeting contractors.'\n  tags:\n  - Construction\n  - Contractors\n  - Building Permits\n  - Sales Intelligence\n  - Market Analytics\n  - Lead Generation\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHOVELS_API_KEY: SHOVELS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: shovels\n    baseUri: https://api.shovels.ai/v2\n    description: Shovels building permit and contractor intelligence API\n\
  \    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{SHOVELS_API_KEY}}'\n      placement: header\n    resources:\n    - name: permits\n      path: /permits\n      description: Building permit records from US jurisdictions\n      operations:\n      - name: search-permits\n        method: GET\n        description: Search permits by geography and date range\n        inputParameters:\n        - name: geo_id\n          in: query\n          type: string\n          required: true\n          description: Geographic location identifier\n        - name: permit_from\n          in: query\n          type: string\n          required: true\n          description: Start date filter (YYYY-MM-DD)\n        - name: permit_to\n          in: query\n          type: string\n          required: true\n          description: End date filter (YYYY-MM-DD)\n        - name: tags\n          in: query\n          type: string\n          required: false\n          description: Permit type tags\
  \ filter\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Permit status filter\n        - name: property_type\n          in: query\n          type: string\n          required: false\n          description: Property type filter\n        - name: min_job_value\n          in: query\n          type: number\n          required: false\n          description: Minimum job value filter\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Results per page (max 100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-permit-by-id\n        method: GET\n        description: Get a specific permit by ID\n        inputParameters:\n        -\
  \ name: id\n          in: path\n          type: string\n          required: true\n          description: Unique permit identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contractors\n      path: /contractors\n      description: Licensed contractor profiles and work history\n      operations:\n      - name: search-contractors\n        method: GET\n        description: Search contractors by geography, specialty, and performance\n        inputParameters:\n        - name: geo_id\n          in: query\n          type: string\n          required: true\n          description: Geographic location identifier\n        - name: permit_from\n          in: query\n          type: string\n          required: true\n          description: Permit date range start (YYYY-MM-DD)\n        - name: permit_to\n          in: query\n          type: string\n          required: true\n          description: Permit date\
  \ range end (YYYY-MM-DD)\n        - name: tags\n          in: query\n          type: string\n          required: false\n          description: Contractor specialty tags\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Contractor name filter\n        - name: min_inspection_pass_rate\n          in: query\n          type: number\n          required: false\n          description: Minimum inspection pass rate (0-1)\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Results per page (max 100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-contractor-by-id\n        method: GET\n        description: Get detailed contractor profile\
  \ by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Unique contractor identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-contractor-permits\n        method: GET\n        description: Get all permits associated with a contractor\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Contractor ID\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ get-contractor-employees\n        method: GET\n        description: Get employees and decision makers for a contractor\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Contractor ID\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-contractor-metrics\n        method: GET\n        description: Get performance metrics for a contractor\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Contractor ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: addresses\n      path: /addresses\n      description:\
  \ Address search and property metrics\n      operations:\n      - name: search-addresses\n        method: GET\n        description: Search addresses with associated permits\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Address search text\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-address-metrics-current\n        method: GET\n        description: Get current permit metrics for an address\n        inputParameters:\n        - name: geo_id\n          in: path\n          type: string\n          required: true\n          description: Address geo_id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n      - name: get-address-residents\n        method: GET\n        description: Get resident information for an address\n        inputParameters:\n        - name: geo_id\n          in: path\n          type: string\n          required: true\n          description: Address geo_id\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: geography\n      path: /cities\n      description: Geographic search endpoints for cities, counties, jurisdictions, states\n      operations:\n      - name: search-cities\n        method: GET\n        description: Search for cities by name\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: City name search term\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-counties\n        method: GET\n        description: Search for counties by name\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: County name search term\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-states\n        method: GET\n        description: Search for US states by name\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: State name search term\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-jurisdictions\n        method: GET\n        description: Search for permit jurisdictions by name\n\
  \        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Jurisdiction name search term\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lists\n      path: /tags\n      description: Reference data for filter values\n      operations:\n      - name: get-tags\n        method: GET\n        description: Get all available permit classification tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: shovels-contractor-intelligence-api\n    description: Unified REST API for contractor intelligence and permit market analytics.\n    resources:\n    - path: /v1/contractors\n      name: contractors\n      description: Search and retrieve qualified contractor profiles\n      operations:\n      -\
  \ method: GET\n        name: search-contractors\n        description: Search contractors by geography, specialty, and quality metrics\n        call: shovels.search-contractors\n        with:\n          geo_id: rest.geo_id\n          permit_from: rest.permit_from\n          permit_to: rest.permit_to\n          tags: rest.tags\n          min_inspection_pass_rate: rest.min_inspection_pass_rate\n          size: rest.size\n          cursor: rest.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contractors/{id}\n      name: contractor-detail\n      description: Full contractor profile with metrics\n      operations:\n      - method: GET\n        name: get-contractor\n        description: Get detailed contractor profile by ID\n        call: shovels.get-contractor-by-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contractors/{id}/permits\n      name: contractor-permits\n\
  \      description: All permits associated with a contractor\n      operations:\n      - method: GET\n        name: get-contractor-permits\n        description: Retrieve permit history for a contractor\n        call: shovels.get-contractor-permits\n        with:\n          id: rest.id\n          cursor: rest.cursor\n          size: rest.size\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contractors/{id}/employees\n      name: contractor-employees\n      description: Decision makers and employees at a contractor company\n      operations:\n      - method: GET\n        name: get-contractor-employees\n        description: Get employee contact list for a contractor\n        call: shovels.get-contractor-employees\n        with:\n          id: rest.id\n          cursor: rest.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contractors/{id}/metrics\n      name: contractor-metrics\n      description:\
  \ Performance metrics for a contractor\n      operations:\n      - method: GET\n        name: get-contractor-metrics\n        description: Get permit performance metrics for a contractor\n        call: shovels.get-contractor-metrics\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/permits\n      name: permits\n      description: Building permit search for market research\n      operations:\n      - method: GET\n        name: search-permits\n        description: Search building permits by geography, type, and date range\n        call: shovels.search-permits\n        with:\n          geo_id: rest.geo_id\n          permit_from: rest.permit_from\n          permit_to: rest.permit_to\n          tags: rest.tags\n          property_type: rest.property_type\n          status: rest.status\n          min_job_value: rest.min_job_value\n          size: rest.size\n          cursor: rest.cursor\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/permits/{id}\n      name: permit-detail\n      description: Individual permit details\n      operations:\n      - method: GET\n        name: get-permit\n        description: Get a specific permit by ID\n        call: shovels.get-permit-by-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/addresses\n      name: addresses\n      description: Address search and lookup\n      operations:\n      - method: GET\n        name: search-addresses\n        description: Search addresses that have associated permits\n        call: shovels.search-addresses\n        with:\n          q: rest.q\n          cursor: rest.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/addresses/{geo_id}/residents\n      name: address-residents\n      description: Residents at a permit address\n      operations:\n      - method: GET\n\
  \        name: get-residents\n        description: Get resident contact information for an address\n        call: shovels.get-address-residents\n        with:\n          geo_id: rest.geo_id\n          cursor: rest.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/market/{geo_id}/metrics\n      name: market-metrics\n      description: Market activity metrics for a geography\n      operations:\n      - method: GET\n        name: get-address-metrics\n        description: Get current permit activity metrics for a geographic area\n        call: shovels.get-address-metrics-current\n        with:\n          geo_id: rest.geo_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/geography/cities\n      name: cities\n      description: City lookup for geo_id resolution\n      operations:\n      - method: GET\n        name: search-cities\n        description: Search for cities to get geo_id values\n        call:\
  \ shovels.search-cities\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/geography/states\n      name: states\n      description: State lookup for geo_id resolution\n      operations:\n      - method: GET\n        name: search-states\n        description: Search for US states to get geo_id values\n        call: shovels.search-states\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tags\n      name: permit-tags\n      description: Available permit classification tags\n      operations:\n      - method: GET\n        name: get-tags\n        description: Get all available permit type tags for filtering\n        call: shovels.get-tags\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: shovels-contractor-intelligence-mcp\n    transport: http\n    description: MCP server\
  \ for AI-assisted contractor research and permit market intelligence.\n    tools:\n    - name: search-contractors\n      description: Search for licensed contractors in a geographic area filtered by specialty, date range, and quality metrics\n        like inspection pass rate. Returns contractor profiles with contact information and permit statistics.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shovels.search-contractors\n      with:\n        geo_id: tools.geo_id\n        permit_from: tools.permit_from\n        permit_to: tools.permit_to\n        tags: tools.tags\n        min_inspection_pass_rate: tools.min_inspection_pass_rate\n        size: tools.size\n        cursor: tools.cursor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contractor\n      description: Get detailed profile for a specific contractor by ID, including business details, contact information,\n        license, classification, and permit statistics.\n\
  \      hints:\n        readOnly: true\n        openWorld: false\n      call: shovels.get-contractor-by-id\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contractor-permits\n      description: Retrieve the complete permit history for a contractor, showing all projects undertaken, job values, locations,\n        and permit statuses.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shovels.get-contractor-permits\n      with:\n        id: tools.id\n        cursor: tools.cursor\n        size: tools.size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contractor-employees\n      description: Get the list of employees and decision makers at a contractor company, including names, titles, phone numbers,\n        and email addresses for sales outreach.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shovels.get-contractor-employees\n\
  \      with:\n        id: tools.id\n        cursor: tools.cursor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contractor-metrics\n      description: Get performance metrics for a contractor including inspection pass rate, average job value, total job value,\n        and active permit count.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shovels.get-contractor-metrics\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-permits\n      description: Search building permits by geography and date range. Filter by permit type (tags), property type, status,\n        and job value range to identify market opportunities and active construction activity.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shovels.search-permits\n      with:\n        geo_id: tools.geo_id\n        permit_from: tools.permit_from\n        permit_to: tools.permit_to\n\
  \        tags: tools.tags\n        property_type: tools.property_type\n        status: tools.status\n        min_job_value: tools.min_job_value\n        size: tools.size\n        cursor: tools.cursor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-permit\n      description: Get details for a specific building permit by ID.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shovels.get-permit-by-id\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-addresses\n      description: Search for US property addresses that have at least one associated permit. Returns address records with\n        geo_id values needed for metric queries.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shovels.search-addresses\n      with:\n        q: tools.q\n        cursor: tools.cursor\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-address-residents\n      description: Get resident contact information for a specific address, useful for homeowner outreach related to nearby\n        permit activity.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shovels.get-address-residents\n      with:\n        geo_id: tools.geo_id\n        cursor: tools.cursor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-market-metrics\n      description: Get current permit activity metrics for a geographic area including permit count, active permits, average\n        job value, and contractor count.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shovels.get-address-metrics-current\n      with:\n        geo_id: tools.geo_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-cities\n      description: Search for city names to resolve geo_id values for use in permit and contractor searches.\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: shovels.search-cities\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-states\n      description: Search for US states to resolve geo_id values.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shovels.search-states\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-permit-tags\n      description: Get all available permit classification tags (solar, roofing, hvac, electrical, plumbing, adu, etc.) for\n        use as filter values in permit and contractor searches.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shovels.get-tags\n      outputParameters:\n      - type: array\n        mapping: $.\n"
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
