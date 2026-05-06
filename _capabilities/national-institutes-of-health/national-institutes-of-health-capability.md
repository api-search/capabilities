---
categories: []
consumed_apis: []
description: The NIH RePORTER API provides programmatic access to information about NIH-funded research projects and their associated publications. It supports search by fiscal year, principal investigator, organization, funding agency, activity code, project number, application identifier, PubMed identifier, award amount, and free-text criteria.
layout: capability
name: NIH RePORTER API
operations:
- description: Search NIH-funded projects
  method: POST
  name: searchprojects
  path: /v2/projects/search
- description: Search publications associated with NIH projects
  method: POST
  name: searchpublications
  path: /v2/publications/search
personas: []
provider_name: National Institutes of Health
provider_slug: national-institutes-of-health
search_terms:
- federal government
- national
- search nih-funded projects
- research
- api
- search publications associated with nih projects
- institutes
- searchprojects
- of
- searchpublications
- publications
- funding
- health
slug: national-institutes-of-health-capability
source_filename: national-institutes-of-health-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NIH RePORTER API\n  description: The NIH RePORTER API provides programmatic access to information about NIH-funded research projects and their\n    associated publications. It supports search by fiscal year, principal investigator, organization, funding agency, activity\n    code, project number, application identifier, PubMed identifier, award amount, and free-text criteria.\n  tags:\n  - National\n  - Institutes\n  - Of\n  - Health\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: national-institutes-of-health\n    baseUri: https://api.reporter.nih.gov\n    description: NIH RePORTER API HTTP API.\n    resources:\n    - name: v2-projects-search\n      path: /v2/projects/search\n      operations:\n      - name: searchprojects\n        method: POST\n        description: Search NIH-funded projects\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: v2-publications-search\n      path: /v2/publications/search\n      operations:\n      - name: searchpublications\n        method: POST\n        description: Search publications associated with NIH projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: national-institutes-of-health-rest\n    description: REST adapter for NIH RePORTER API.\n    resources:\n    - path: /v2/projects/search\n      name: searchprojects\n      operations:\n      - method: POST\n        name: searchprojects\n        description: Search NIH-funded projects\n        call: national-institutes-of-health.searchprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/publications/search\n      name: searchpublications\n      operations:\n      - method: POST\n        name:\
  \ searchpublications\n        description: Search publications associated with NIH projects\n        call: national-institutes-of-health.searchpublications\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: national-institutes-of-health-mcp\n    transport: http\n    description: MCP adapter for NIH RePORTER API for AI agent use.\n    tools:\n    - name: searchprojects\n      description: Search NIH-funded projects\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: national-institutes-of-health.searchprojects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchpublications\n      description: Search publications associated with NIH projects\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: national-institutes-of-health.searchpublications\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/national-institutes-of-health/refs/heads/main/capabilities/national-institutes-of-health-capability.yaml
tags:
- National
- Institutes
- Of
- Health
- API
tools:
- description: Search NIH-funded projects
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchprojects
- description: Search publications associated with NIH projects
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchpublications
---
