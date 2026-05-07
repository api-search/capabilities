---
categories: []
consumed_apis: []
description: Unified capability for insurance underwriters to assess property risk, retrieve ISO fire protection classifications, score catastrophe peril exposures, and benchmark claims performance. Combines Verisk Insurance Analytics API operations into a single underwriting workflow for P&C insurance carriers.
layout: capability
name: Verisk Insurance Underwriting
operations:
- description: Get comprehensive property risk assessment
  method: GET
  name: get-property-risk
  path: /v1/properties/{propertyId}/risk
- description: Lookup property risk data by street address
  method: POST
  name: lookup-property
  path: /v1/properties/lookup
- description: Get risk scores for properties or portfolios
  method: POST
  name: get-risk-scores
  path: /v1/risk-scores
- description: Get ISO PPC grade for a location
  method: GET
  name: get-fire-protection-class
  path: /v1/fire-protection-class
- description: Get catastrophe peril scores for locations
  method: POST
  name: get-peril-scores
  path: /v1/peril-scores
- description: Get industry claims benchmarking metrics
  method: GET
  name: get-claims-benchmarks
  path: /v1/claims/benchmarks
personas: []
provider_name: Verisk
provider_slug: verisk
search_terms:
- analytics
- get industry claims benchmarking data for loss frequency, severity, combined ratio, and loss ratio by line of business and state
- property lookup by address
- p&c insurance underwriters who evaluate property risk and price policies
- get iso public protection classification (ppc) grade for a geographic location to assess fire suppression capability
- get comprehensive property risk assessment
- claims
- get iso fire protection, building code effectiveness, flood zone, earthquake zone, and wind zone risk scores for properties or portfolios
- industry claims benchmarking and loss performance data
- property risk assessment by property id
- get claims benchmarks
- catastrophe peril exposure scores
- get catastrophe exposure scores for hurricane, tornado, hail, wildfire, earthquake, and flood perils for a list of locations
- insurance risk scores for underwriting
- catastrophe modeling
- Insurance Underwriter
- get industry claims benchmarking metrics
- risk managers overseeing portfolio catastrophe exposure and pml estimates
- get peril scores
- get catastrophe peril scores for locations
- get risk scores for properties or portfolios
- lookup property by address
- property risk
- actuaries who model property loss costs and catastrophe exposures
- lookup property
- get fire protection class
- get iso ppc grade for a location
- unified underwriting workflow combining property risk, fire protection classification, catastrophe scoring, and claims benchmarking
- policy underwriting and risk assessment for p&c insurance
- underwriting
- Property Actuary
- natural hazard peril scoring and catastrophe exposure analysis
- property data
- industry claims benchmarking
- get comprehensive property risk assessment including construction, fire protection, and hazard scores for underwriting a specific property
- Catastrophe Risk Manager
- resolve a street address to a property record and retrieve verisk risk data for underwriting
- get property risk
- insurance
- get risk scores
- property-level risk data including construction and hazard scores
- risk management
- iso fire protection classification
- lookup property risk data by street address
slug: insurance-underwriting
source_filename: insurance-underwriting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Verisk Insurance Underwriting\n  description: Unified capability for insurance underwriters to assess property risk, retrieve ISO fire protection classifications,\n    score catastrophe peril exposures, and benchmark claims performance. Combines Verisk Insurance Analytics API operations\n    into a single underwriting workflow for P&C insurance carriers.\n  tags:\n  - Insurance\n  - Underwriting\n  - Property Risk\n  - Catastrophe Modeling\n  - Claims\n  - Analytics\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VERISK_BEARER_TOKEN: VERISK_BEARER_TOKEN\n    VERISK_API_KEY: VERISK_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: verisk-insurance-analytics\n    baseUri: https://api.verisk.com/insurance/v1\n    description: Verisk Insurance Analytics REST API for property risk, peril scores, and claims benchmarking.\n    authentication:\n      type: bearer\n      token: '{{VERISK_BEARER_TOKEN}}'\n\
  \    resources:\n    - name: property-risk\n      path: /property/risk/{propertyId}\n      description: Property risk assessments and hazard scores\n      operations:\n      - name: get-property-risk\n        method: GET\n        description: Get comprehensive risk data for a specific property\n        inputParameters:\n        - name: propertyId\n          in: path\n          type: string\n          required: true\n          description: Property identifier (address or ISO property ID)\n        - name: includePerils\n          in: query\n          type: array\n          required: false\n          description: Peril types to include in response\n        - name: asOfDate\n          in: query\n          type: string\n          required: false\n          description: Historical risk assessment date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: property-lookup\n      path: /property/lookup\n     \
  \ description: Address-to-property resolution and risk data\n      operations:\n      - name: lookup-property-by-address\n        method: POST\n        description: Resolve a street address to a property record and return risk data\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            streetAddress: '{{tools.streetAddress}}'\n            city: '{{tools.city}}'\n            state: '{{tools.state}}'\n            zipCode: '{{tools.zipCode}}'\n            includeRiskData: '{{tools.includeRiskData}}'\n    - name: risk-scores\n      path: /risk/scores\n      description: Insurance risk scores for properties and portfolios\n      operations:\n      - name: get-risk-scores\n        method: POST\n        description: Get risk scores for properties, policies, or portfolios\n        inputParameters: []\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            locations: '{{tools.locations}}'\n            scoreTypes: '{{tools.scoreTypes}}'\n    - name: fire-protection-class\n      path: /risk/fire-protection-class\n      description: ISO Fire Protection Classification data\n      operations:\n      - name: get-fire-protection-class\n        method: GET\n        description: Get ISO Public Protection Classification (PPC) grade for a location\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Location latitude\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Location longitude\n        - name: constructionType\n          in: query\n          type: string\n          required: false\n          description: ISO construction\
  \ class\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: catastrophe-peril-scores\n      path: /catastrophe/peril-scores\n      description: Catastrophe peril exposure scores\n      operations:\n      - name: get-peril-scores\n        method: POST\n        description: Get catastrophe exposure scores for natural hazard perils\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            locations: '{{tools.locations}}'\n            perils: '{{tools.perils}}'\n    - name: claims-benchmarks\n      path: /claims/benchmarks\n      description: Industry claims benchmarking data\n      operations:\n      - name: get-claims-benchmarks\n        method: GET\n        description: Get industry claims benchmarking data for loss frequency, severity, and\
  \ combined ratio\n        inputParameters:\n        - name: lineOfBusiness\n          in: query\n          type: string\n          required: true\n          description: Line of insurance business\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: US state code\n        - name: year\n          in: query\n          type: integer\n          required: false\n          description: Data year\n        - name: metricType\n          in: query\n          type: string\n          required: false\n          description: Metric type to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: verisk-underwriting-api\n    description: Unified REST API for insurance underwriting workflows using Verisk data.\n    resources:\n    - path: /v1/properties/{propertyId}/risk\n      name: property-risk\n\
  \      description: Property risk assessment by property ID\n      operations:\n      - method: GET\n        name: get-property-risk\n        description: Get comprehensive property risk assessment\n        call: verisk-insurance-analytics.get-property-risk\n        with:\n          propertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/lookup\n      name: property-lookup\n      description: Property lookup by address\n      operations:\n      - method: POST\n        name: lookup-property\n        description: Lookup property risk data by street address\n        call: verisk-insurance-analytics.lookup-property-by-address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/risk-scores\n      name: risk-scores\n      description: Insurance risk scores for underwriting\n      operations:\n      - method: POST\n        name: get-risk-scores\n        description: Get risk scores\
  \ for properties or portfolios\n        call: verisk-insurance-analytics.get-risk-scores\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fire-protection-class\n      name: fire-protection-class\n      description: ISO Fire Protection Classification\n      operations:\n      - method: GET\n        name: get-fire-protection-class\n        description: Get ISO PPC grade for a location\n        call: verisk-insurance-analytics.get-fire-protection-class\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/peril-scores\n      name: peril-scores\n      description: Catastrophe peril exposure scores\n      operations:\n      - method: POST\n        name: get-peril-scores\n        description: Get catastrophe peril scores for locations\n        call: verisk-insurance-analytics.get-peril-scores\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /v1/claims/benchmarks\n      name: claims-benchmarks\n      description: Industry claims benchmarking\n      operations:\n      - method: GET\n        name: get-claims-benchmarks\n        description: Get industry claims benchmarking metrics\n        call: verisk-insurance-analytics.get-claims-benchmarks\n        with:\n          lineOfBusiness: rest.lineOfBusiness\n          state: rest.state\n          year: rest.year\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: verisk-underwriting-mcp\n    transport: http\n    description: MCP server for AI-assisted insurance underwriting using Verisk data.\n    tools:\n    - name: get-property-risk\n      description: Get comprehensive property risk assessment including construction, fire protection, and hazard scores for\n        underwriting a specific property\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: verisk-insurance-analytics.get-property-risk\n      with:\n        propertyId: tools.propertyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-property-by-address\n      description: Resolve a street address to a property record and retrieve Verisk risk data for underwriting\n      hints:\n        readOnly: true\n        openWorld: true\n      call: verisk-insurance-analytics.lookup-property-by-address\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-risk-scores\n      description: Get ISO fire protection, building code effectiveness, flood zone, earthquake zone, and wind zone risk scores\n        for properties or portfolios\n      hints:\n        readOnly: true\n        openWorld: true\n      call: verisk-insurance-analytics.get-risk-scores\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fire-protection-class\n      description: Get ISO Public Protection Classification\
  \ (PPC) grade for a geographic location to assess fire suppression\n        capability\n      hints:\n        readOnly: true\n        openWorld: true\n      call: verisk-insurance-analytics.get-fire-protection-class\n      with:\n        latitude: tools.latitude\n        longitude: tools.longitude\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-peril-scores\n      description: Get catastrophe exposure scores for hurricane, tornado, hail, wildfire, earthquake, and flood perils for\n        a list of locations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: verisk-insurance-analytics.get-peril-scores\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-claims-benchmarks\n      description: Get industry claims benchmarking data for loss frequency, severity, combined ratio, and loss ratio by line\n        of business and state\n      hints:\n        readOnly: true\n        openWorld: true\n   \
  \   call: verisk-insurance-analytics.get-claims-benchmarks\n      with:\n        lineOfBusiness: tools.lineOfBusiness\n        state: tools.state\n        year: tools.year\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/verisk/refs/heads/main/capabilities/insurance-underwriting.yaml
tags:
- Insurance
- Underwriting
- Property Risk
- Catastrophe Modeling
- Claims
- Analytics
tools:
- description: Get comprehensive property risk assessment including construction, fire protection, and hazard scores for underwriting a specific property
  hints:
    openWorld: true
    readOnly: true
  name: get-property-risk
- description: Resolve a street address to a property record and retrieve Verisk risk data for underwriting
  hints:
    openWorld: true
    readOnly: true
  name: lookup-property-by-address
- description: Get ISO fire protection, building code effectiveness, flood zone, earthquake zone, and wind zone risk scores for properties or portfolios
  hints:
    openWorld: true
    readOnly: true
  name: get-risk-scores
- description: Get ISO Public Protection Classification (PPC) grade for a geographic location to assess fire suppression capability
  hints:
    openWorld: true
    readOnly: true
  name: get-fire-protection-class
- description: Get catastrophe exposure scores for hurricane, tornado, hail, wildfire, earthquake, and flood perils for a list of locations
  hints:
    openWorld: true
    readOnly: true
  name: get-peril-scores
- description: Get industry claims benchmarking data for loss frequency, severity, combined ratio, and loss ratio by line of business and state
  hints:
    openWorld: true
    readOnly: true
  name: get-claims-benchmarks
---
