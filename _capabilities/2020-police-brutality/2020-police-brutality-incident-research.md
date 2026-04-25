---
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
- policing
- uses data for advocacy, public education, and political campaigns
- all documented police brutality incidents from 2020 protests.
- investigates and reports on documented police brutality incidents
- conducts academic or policy research on police use of force patterns
- Legal Professional
- public data
- research
- Journalist
- get incidents v2
- uses incident documentation for prosecution or civil litigation
- journalism
- retrieve all documented police brutality incidents from the 2020 george floyd protests. returns location, date, description, tags, and source links for each incident.
- all incidents in csv format for data analysis.
- documented evidence of police brutality during 2020 protests
- export all incidents as csv for spreadsheet and data analysis.
- list all documented police brutality incidents.
- brutality
- retrieve all police brutality incidents in the v2 data format with improved schema consistency.
- research workflow for journalists, prosecutors, and activists
- civil rights
- export all documented police brutality incidents as csv for use in spreadsheets, databases, and data analysis tools.
- export incidents csv
- get all incidents
- list incidents
- Researcher
- Activist
slug: 2020-police-brutality-incident-research
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
