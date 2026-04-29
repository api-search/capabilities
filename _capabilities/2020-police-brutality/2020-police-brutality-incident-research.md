---
api_specs:
- filename: 2020-police-brutality-openapi.yml
  format: yaml
  label: 2020-police-brutality
  slug: 2020-police-brutality
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/2020-police-brutality/refs/heads/main/openapi/2020-police-brutality-openapi.yml
categories: []
consumed_apis:
- 2020-police-brutality
description: Workflow for accessing and analyzing documented police brutality incidents from the 2020 George Floyd protests. Designed for journalists, researchers, prosecutors, and activists who need programmatic access to incident data for reporting, legal proceedings, and advocacy work.
layout: capability
name: 2020 Police Brutality Incident Research
operations:
- description: List all documented police brutality incidents.
  method: GET
  name: list-incidents
  path: /v1/incidents
- description: Export all incidents as CSV for spreadsheet and data analysis.
  method: GET
  name: export-incidents-csv
  path: /v1/incidents/csv
personas: []
provider_name: 2020 Police Brutality
provider_slug: 2020-police-brutality
search_terms:
- public data
- export incidents csv
- all incidents in csv format for data analysis.
- Journalist
- Activist
- Researcher
- uses incident documentation for prosecution or civil litigation
- brutality
- documented evidence of police brutality during 2020 protests
- Legal Professional
- get incidents v2
- policing
- list all documented police brutality incidents.
- conducts academic or policy research on police use of force patterns
- export all incidents as csv for spreadsheet and data analysis.
- retrieve all police brutality incidents in the v2 data format with improved schema consistency.
- all documented police brutality incidents from 2020 protests.
- civil rights
- research
- get all incidents
- research workflow for journalists, prosecutors, and activists
- export all documented police brutality incidents as csv for use in spreadsheets, databases, and data analysis tools.
- investigates and reports on documented police brutality incidents
- journalism
- uses data for advocacy, public education, and political campaigns
- retrieve all documented police brutality incidents from the 2020 george floyd protests. returns location, date, description, tags, and source links for each incident.
- list incidents
slug: 2020-police-brutality-incident-research
source_filename: 2020-police-brutality-incident-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: 2020 Police Brutality Incident Research\n  description: >-\n    Workflow for accessing and analyzing documented police brutality incidents\n    from the 2020 George Floyd protests. Designed for journalists, researchers,\n    prosecutors, and activists who need programmatic access to incident data\n    for reporting, legal proceedings, and advocacy work.\n  tags:\n    - Public Data\n    - Policing\n    - Civil Rights\n    - Journalism\n    - Research\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\ncapability:\n  consumes:\n    - import: 2020-police-brutality\n      location: ./shared/2020-police-brutality.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: police-brutality-research-api\n      description: \"REST API for accessing 2020 police brutality incident data.\"\n      resources:\n        - path: /v1/incidents\n          name: incidents\n          description: \"All documented police brutality\
  \ incidents from 2020 protests.\"\n          operations:\n            - method: GET\n              name: list-incidents\n              description: \"List all documented police brutality incidents.\"\n              call: \"2020-police-brutality.get-all-incidents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/incidents/csv\n          name: incidents-csv\n          description: \"All incidents in CSV format for data analysis.\"\n          operations:\n            - method: GET\n              name: export-incidents-csv\n              description: \"Export all incidents as CSV for spreadsheet and data analysis.\"\n              call: \"2020-police-brutality.get-all-incidents-csv\"\n              outputParameters:\n                - type: string\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: police-brutality-research-mcp\n      transport: http\n      description: \"MCP server\
  \ for AI-assisted research into 2020 police brutality incidents.\"\n      tools:\n        - name: get-all-incidents\n          description: >-\n            Retrieve all documented police brutality incidents from the 2020 George Floyd\n            protests. Returns location, date, description, tags, and source links for each incident.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"2020-police-brutality.get-all-incidents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-incidents-v2\n          description: >-\n            Retrieve all police brutality incidents in the v2 data format with\n            improved schema consistency.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"2020-police-brutality.get-all-incidents-v2\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: export-incidents-csv\n\
  \          description: >-\n            Export all documented police brutality incidents as CSV for use in\n            spreadsheets, databases, and data analysis tools.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"2020-police-brutality.get-all-incidents-csv\"\n          outputParameters:\n            - type: string\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/2020-police-brutality/refs/heads/main/capabilities/2020-police-brutality-incident-research.yaml
tags:
- Public Data
- Policing
- Civil Rights
- Journalism
- Research
tools:
- description: Retrieve all documented police brutality incidents from the 2020 George Floyd protests. Returns location, date, description, tags, and source links for each incident.
  hints:
    openWorld: true
    readOnly: true
  name: get-all-incidents
- description: Retrieve all police brutality incidents in the v2 data format with improved schema consistency.
  hints:
    openWorld: true
    readOnly: true
  name: get-incidents-v2
- description: Export all documented police brutality incidents as CSV for use in spreadsheets, databases, and data analysis tools.
  hints:
    openWorld: true
    readOnly: true
  name: export-incidents-csv
---
