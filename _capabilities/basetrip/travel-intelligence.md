---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Travel Intelligence
operations: []
personas: []
provider_name: Basetrip
provider_slug: basetrip
search_terms:
- Travel Content Publisher
- Travel App Developer
- embed country, city, safety, cost, visa, and health data into travel platforms
- health
- safety
- Trip Planner
- travel planning, booking, and destination information
- travel
- visa
- content creator embedding destination guides with live data
- individual or business planning international travel
- countries
- developer building travel booking or trip planning apps
- travel safety ratings and advisories
- cities
slug: travel-intelligence
source_yaml: "name: Travel Intelligence\ndescription: >-\n  Workflow capability for embedding travel intelligence data into travel apps,\n  booking platforms, and trip planning tools using the Basetrip API.\nversion: \"1.0\"\napis:\n  - basetrip:basetrip-api\npersonas:\n  - Travel App Developer\n  - Trip Planner\n  - Travel Content Publisher\ntools:\n  - name: get_country_info\n    description: Retrieve comprehensive country information including capital, currency, languages, and timezone.\n    operation: getCountry\n    api: basetrip:basetrip-api\n  - name: list_cities\n    description: List all cities for a given country to present destination options.\n    operation: listCitiesByCountry\n    api: basetrip:basetrip-api\n  - name: get_travel_phrases\n    description: Fetch travel phrases for a destination country to help travelers communicate.\n    operation: listPhrasesByCountry\n    api: basetrip:basetrip-api\n  - name: check_safety\n    description: Get current safety ratings and advisories\
  \ before booking travel.\n    operation: getCountrySafety\n    api: basetrip:basetrip-api\n  - name: estimate_costs\n    description: Retrieve daily budget estimates across budget, mid-range, and luxury tiers.\n    operation: getCountryCost\n    api: basetrip:basetrip-api\n  - name: check_visa_requirements\n    description: Check visa requirements for a traveler's passport and destination country.\n    operation: getVisaRequirements\n    api: basetrip:basetrip-api\n  - name: get_health_advisories\n    description: Retrieve vaccination requirements and health risks for destination countries.\n    operation: getCountryHealth\n    api: basetrip:basetrip-api\nmcp:\n  adapter: basetrip-mcp\n  namespace: basetrip-api\n  port: 9080\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/basetrip/refs/heads/main/capabilities/travel-intelligence.yaml
tags: []
tools: []
---
