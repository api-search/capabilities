---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Hr Integration
operations: []
personas: []
provider_name: Bindbee
provider_slug: bindbee
search_terms:
- developer building hr workflow automations using unified hr data
- access unified hr and recruiting data from connected hris and ats systems
- employee time-off, tenure, and workforce data
- hris
- workforce
- hr integration
- people operations engineer integrating hr systems into internal tooling
- ats
- department hierarchy and org structure normalization
- unified access to recruiting data from ats platforms
- unified access to employee data from hris platforms
slug: hr-integration
source_filename: hr-integration.yaml
source_heading: Capability Spec
source_yaml: "name: HR Integration\ndescription: >-\n  Workflow capability for accessing unified HR data from HRIS and ATS systems\n  through Bindbee, including employee records, departments, time-off, job\n  postings, and candidates.\nversion: v1\n\nimports:\n  - shared/bindbee.yaml\n\ntools:\n  - name: list-employees\n    import: bindbee.list-employees\n    description: List all employees from the connected HRIS system with pagination.\n    inputSchema:\n      type: object\n      required:\n        - connector_token\n      properties:\n        connector_token:\n          type: string\n          description: Connector token for the specific HRIS integration\n        page_size:\n          type: integer\n          description: Number of results per page\n        cursor:\n          type: string\n          description: Pagination cursor from previous response\n  - name: get-employee\n    import: bindbee.get-employee\n    description: Get a specific employee's full record by ID.\n    inputSchema:\n\
  \      type: object\n      required:\n        - connector_token\n        - id\n      properties:\n        connector_token:\n          type: string\n          description: Connector token for the HRIS integration\n        id:\n          type: string\n          description: Employee ID\n  - name: list-departments\n    import: bindbee.list-departments\n    description: List all organizational departments from the connected HRIS.\n    inputSchema:\n      type: object\n      required:\n        - connector_token\n      properties:\n        connector_token:\n          type: string\n          description: Connector token for the HRIS integration\n  - name: list-time-off\n    import: bindbee.list-time-off\n    description: List time-off requests with optional employee filtering.\n    inputSchema:\n      type: object\n      required:\n        - connector_token\n      properties:\n        connector_token:\n          type: string\n          description: Connector token for the HRIS integration\n \
  \       employee_id:\n          type: string\n          description: Filter by employee ID\n  - name: list-jobs\n    import: bindbee.list-jobs\n    description: List open job postings from the connected ATS system.\n    inputSchema:\n      type: object\n      required:\n        - connector_token\n      properties:\n        connector_token:\n          type: string\n          description: Connector token for the ATS integration\n        status:\n          type: string\n          description: Filter by job status (open, closed, draft)\n  - name: list-candidates\n    import: bindbee.list-candidates\n    description: List candidates from the connected ATS system.\n    inputSchema:\n      type: object\n      required:\n        - connector_token\n      properties:\n        connector_token:\n          type: string\n          description: Connector token for the ATS integration\n        job_id:\n          type: string\n          description: Filter by job ID\n  - name: get-candidate\n    import:\
  \ bindbee.get-candidate\n    description: Get a specific candidate's full record by ID.\n    inputSchema:\n      type: object\n      required:\n        - connector_token\n        - id\n      properties:\n        connector_token:\n          type: string\n          description: Connector token for the ATS integration\n        id:\n          type: string\n          description: Candidate ID\n\nexpose:\n  rest:\n    port: 8080\n  mcp:\n    port: 9080\n\npersonas:\n  - id: hr-developer\n    name: HR Developer\n    description: Developer building HR workflow automations using unified HR data\n  - id: people-ops-engineer\n    name: People Ops Engineer\n    description: People operations engineer integrating HR systems into internal tooling\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bindbee/refs/heads/main/capabilities/hr-integration.yaml
tags: []
tools: []
---
