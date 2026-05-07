---
categories: []
consumed_apis: []
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
- brutality
- civil rights
- conducts academic or policy research on police use of force patterns
- uses data for advocacy, public education, and political campaigns
- documented evidence of police brutality during 2020 protests
- public data
- Researcher
- get incidents v2
- research workflow for journalists, prosecutors, and activists
- journalism
- research
- Legal Professional
- list incidents
- retrieve all documented police brutality incidents from the 2020 george floyd protests. returns location, date, description, tags, and source links for each incident.
- Journalist
- uses incident documentation for prosecution or civil litigation
- Activist
- get all incidents
- all documented police brutality incidents from 2020 protests.
- investigates and reports on documented police brutality incidents
- list all documented police brutality incidents.
- export incidents csv
- retrieve all police brutality incidents in the v2 data format with improved schema consistency.
- export all documented police brutality incidents as csv for use in spreadsheets, databases, and data analysis tools.
- all incidents in csv format for data analysis.
- export all incidents as csv for spreadsheet and data analysis.
- policing
slug: 2020-police-brutality-incident-research
source_filename: 2020-police-brutality-incident-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: 2020 Police Brutality Incident Research\n  description: Workflow for accessing and analyzing documented police brutality incidents from the 2020 George Floyd protests.\n    Designed for journalists, researchers, prosecutors, and activists who need programmatic access to incident data for reporting,\n    legal proceedings, and advocacy work.\n  tags:\n  - Public Data\n  - Policing\n  - Civil Rights\n  - Journalism\n  - Research\n  created: '2026-04-19'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: 2020-police-brutality\n    baseUri: https://raw.githubusercontent.com/2020PB/police-brutality/data_build\n    description: Static JSON data files for 2020 police brutality incident documentation\n    resources:\n    - name: incidents\n      path: /all-locations.json\n      description: All documented police brutality incidents\n      operations:\n      - name: get-all-incidents\n        method: GET\n     \
  \   description: Retrieve all documented police brutality incidents as JSON\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-all-incidents-v2\n        method: GET\n        description: Retrieve all incidents in v2 format with improved schema\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-all-incidents-csv\n        method: GET\n        description: Retrieve all incidents in CSV format for spreadsheet analysis\n        inputParameters: []\n        outputRawFormat: csv\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: police-brutality-research-api\n    description: REST API for accessing 2020 police brutality incident data.\n    resources:\n\
  \    - path: /v1/incidents\n      name: incidents\n      description: All documented police brutality incidents from 2020 protests.\n      operations:\n      - method: GET\n        name: list-incidents\n        description: List all documented police brutality incidents.\n        call: 2020-police-brutality.get-all-incidents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/incidents/csv\n      name: incidents-csv\n      description: All incidents in CSV format for data analysis.\n      operations:\n      - method: GET\n        name: export-incidents-csv\n        description: Export all incidents as CSV for spreadsheet and data analysis.\n        call: 2020-police-brutality.get-all-incidents-csv\n        outputParameters:\n        - type: string\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: police-brutality-research-mcp\n    transport: http\n    description: MCP server for AI-assisted research into 2020 police brutality incidents.\n\
  \    tools:\n    - name: get-all-incidents\n      description: Retrieve all documented police brutality incidents from the 2020 George Floyd protests. Returns location,\n        date, description, tags, and source links for each incident.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: 2020-police-brutality.get-all-incidents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-incidents-v2\n      description: Retrieve all police brutality incidents in the v2 data format with improved schema consistency.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: 2020-police-brutality.get-all-incidents-v2\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-incidents-csv\n      description: Export all documented police brutality incidents as CSV for use in spreadsheets, databases, and data analysis\n        tools.\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: 2020-police-brutality.get-all-incidents-csv\n      outputParameters:\n      - type: string\n        mapping: $.\n"
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
