---
categories: []
consumed_apis:
- verisk-insurance-analytics
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
- get comprehensive property risk assessment
- unified underwriting workflow combining property risk, fire protection classification, catastrophe scoring, and claims benchmarking
- industry claims benchmarking and loss performance data
- property-level risk data including construction and hazard scores
- policy underwriting and risk assessment for p&c insurance
- get risk scores
- catastrophe peril exposure scores
- get iso fire protection, building code effectiveness, flood zone, earthquake zone, and wind zone risk scores for properties or portfolios
- get industry claims benchmarking metrics
- analytics
- property risk
- risk management
- property lookup by address
- get iso public protection classification (ppc) grade for a geographic location to assess fire suppression capability
- underwriting
- lookup property by address
- get peril scores
- industry claims benchmarking
- p&c insurance underwriters who evaluate property risk and price policies
- catastrophe modeling
- claims
- get fire protection class
- get iso ppc grade for a location
- insurance
- iso fire protection classification
- property risk assessment by property id
- get catastrophe peril scores for locations
- get catastrophe exposure scores for hurricane, tornado, hail, wildfire, earthquake, and flood perils for a list of locations
- get industry claims benchmarking data for loss frequency, severity, combined ratio, and loss ratio by line of business and state
- lookup property
- actuaries who model property loss costs and catastrophe exposures
- get comprehensive property risk assessment including construction, fire protection, and hazard scores for underwriting a specific property
- Catastrophe Risk Manager
- lookup property risk data by street address
- get risk scores for properties or portfolios
- insurance risk scores for underwriting
- Insurance Underwriter
- get property risk
- resolve a street address to a property record and retrieve verisk risk data for underwriting
- get claims benchmarks
- risk managers overseeing portfolio catastrophe exposure and pml estimates
- property data
- natural hazard peril scoring and catastrophe exposure analysis
- Property Actuary
slug: insurance-underwriting
source_filename: insurance-underwriting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Verisk Insurance Underwriting\"\n  description: \"Unified capability for insurance underwriters to assess property risk, retrieve ISO fire protection classifications, score catastrophe peril exposures, and benchmark claims performance. Combines Verisk Insurance Analytics API operations into a single underwriting workflow for P&C insurance carriers.\"\n  tags:\n    - Insurance\n    - Underwriting\n    - Property Risk\n    - Catastrophe Modeling\n    - Claims\n    - Analytics\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VERISK_BEARER_TOKEN: VERISK_BEARER_TOKEN\n      VERISK_API_KEY: VERISK_API_KEY\n\ncapability:\n  consumes:\n    - import: verisk-insurance-analytics\n      location: ./shared/insurance-analytics.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: verisk-underwriting-api\n      description: \"Unified REST API for insurance underwriting workflows\
  \ using Verisk data.\"\n      resources:\n        - path: /v1/properties/{propertyId}/risk\n          name: property-risk\n          description: \"Property risk assessment by property ID\"\n          operations:\n            - method: GET\n              name: get-property-risk\n              description: \"Get comprehensive property risk assessment\"\n              call: \"verisk-insurance-analytics.get-property-risk\"\n              with:\n                propertyId: \"rest.propertyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/properties/lookup\n          name: property-lookup\n          description: \"Property lookup by address\"\n          operations:\n            - method: POST\n              name: lookup-property\n              description: \"Lookup property risk data by street address\"\n              call: \"verisk-insurance-analytics.lookup-property-by-address\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/risk-scores\n          name: risk-scores\n          description: \"Insurance risk scores for underwriting\"\n          operations:\n            - method: POST\n              name: get-risk-scores\n              description: \"Get risk scores for properties or portfolios\"\n              call: \"verisk-insurance-analytics.get-risk-scores\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/fire-protection-class\n          name: fire-protection-class\n          description: \"ISO Fire Protection Classification\"\n          operations:\n            - method: GET\n              name: get-fire-protection-class\n              description: \"Get ISO PPC grade for a location\"\n              call: \"verisk-insurance-analytics.get-fire-protection-class\"\n              with:\n                latitude: \"rest.latitude\"\n              \
  \  longitude: \"rest.longitude\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/peril-scores\n          name: peril-scores\n          description: \"Catastrophe peril exposure scores\"\n          operations:\n            - method: POST\n              name: get-peril-scores\n              description: \"Get catastrophe peril scores for locations\"\n              call: \"verisk-insurance-analytics.get-peril-scores\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/claims/benchmarks\n          name: claims-benchmarks\n          description: \"Industry claims benchmarking\"\n          operations:\n            - method: GET\n              name: get-claims-benchmarks\n              description: \"Get industry claims benchmarking metrics\"\n              call: \"verisk-insurance-analytics.get-claims-benchmarks\"\n              with:\n          \
  \      lineOfBusiness: \"rest.lineOfBusiness\"\n                state: \"rest.state\"\n                year: \"rest.year\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: verisk-underwriting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted insurance underwriting using Verisk data.\"\n      tools:\n        - name: get-property-risk\n          description: \"Get comprehensive property risk assessment including construction, fire protection, and hazard scores for underwriting a specific property\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"verisk-insurance-analytics.get-property-risk\"\n          with:\n            propertyId: \"tools.propertyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: lookup-property-by-address\n          description: \"Resolve\
  \ a street address to a property record and retrieve Verisk risk data for underwriting\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"verisk-insurance-analytics.lookup-property-by-address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-risk-scores\n          description: \"Get ISO fire protection, building code effectiveness, flood zone, earthquake zone, and wind zone risk scores for properties or portfolios\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"verisk-insurance-analytics.get-risk-scores\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-fire-protection-class\n          description: \"Get ISO Public Protection Classification (PPC) grade for a geographic location to assess fire suppression capability\"\n          hints:\n            readOnly: true\n       \
  \     openWorld: true\n          call: \"verisk-insurance-analytics.get-fire-protection-class\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-peril-scores\n          description: \"Get catastrophe exposure scores for hurricane, tornado, hail, wildfire, earthquake, and flood perils for a list of locations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"verisk-insurance-analytics.get-peril-scores\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-claims-benchmarks\n          description: \"Get industry claims benchmarking data for loss frequency, severity, combined ratio, and loss ratio by line of business and state\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"verisk-insurance-analytics.get-claims-benchmarks\"\
  \n          with:\n            lineOfBusiness: \"tools.lineOfBusiness\"\n            state: \"tools.state\"\n            year: \"tools.year\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
