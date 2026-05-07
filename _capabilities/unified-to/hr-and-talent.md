---
categories: []
consumed_apis: []
description: Unified HR and talent acquisition workflow combining employee management, payroll, and applicant tracking across 223 HRIS and 73 ATS integrations. Used by HR technology developers, people operations teams, and talent acquisition platforms building cross-system workforce management tools.
layout: capability
name: Unified.to HR and Talent
operations:
- description: List employees from an HRIS integration
  method: GET
  name: list-hris-employees
  path: /v1/hris/{connection_id}/employees
- description: Create a new employee record
  method: POST
  name: create-hris-employee
  path: /v1/hris/{connection_id}/employees
- description: List HR groups and departments
  method: GET
  name: list-hris-groups
  path: /v1/hris/{connection_id}/groups
- description: List employee payslips
  method: GET
  name: list-hris-payslips
  path: /v1/hris/{connection_id}/payslips
- description: List open job postings
  method: GET
  name: list-ats-jobs
  path: /v1/ats/{connection_id}/jobs
- description: List candidates
  method: GET
  name: list-ats-candidates
  path: /v1/ats/{connection_id}/candidates
- description: Create a new candidate
  method: POST
  name: create-ats-candidate
  path: /v1/ats/{connection_id}/candidates
- description: List job applications
  method: GET
  name: list-ats-applications
  path: /v1/ats/{connection_id}/applications
personas: []
provider_name: Unified.to
provider_slug: unified-to
search_terms:
- integrations
- list candidates from a connected ats integration
- list hris payslips
- list hr groups and departments
- hris
- create a new candidate in a connected ats integration
- list candidates
- candidate profiles from ats integrations
- list scheduled interviews from a connected ats integration
- list employee payslips
- developers building sales tools, crm sync, and revenue reporting integrations
- ats
- list hris employees
- hr groups and departments
- unified api
- list hris groups
- list hr groups and departments from a connected hris integration
- create ats candidate
- CRM Integrator
- unified.to
- list open job postings from a connected ats integration (greenhouse, lever, etc.)
- job postings from ats integrations
- hr
- developers building hr workflows, employee onboarding, and recruiting automation
- list job applications
- HR Technology Developer
- Fintech Developer
- list ats applications
- list ats candidates
- list employees from an hris integration
- Finance Operations Engineer
- recruiting
- list employee payslips from a connected hris integration
- employee data across hris integrations
- list ats jobs
- employee payslip data
- job applications from ats integrations
- list employees from a connected hris integration (workday, bamboohr, adp, etc.)
- employees
- People Operations Engineer
- crm contact, company, and deal management across 47+ integrations
- create a new employee record
- create a new employee record in a connected hris integration
- Revenue Operations Developer
- accounting, invoicing, and payment management across 41+ integrations
- hris and ats management across 296+ hr and recruiting integrations
- list open job postings
- developers building invoicing automation, expense management, and accounting sync
- create a new candidate
- create hris employee
- list job applications from a connected ats integration
- list ats interviews
slug: hr-and-talent
source_filename: hr-and-talent.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Unified.to HR and Talent\n  description: Unified HR and talent acquisition workflow combining employee management, payroll, and applicant tracking across\n    223 HRIS and 73 ATS integrations. Used by HR technology developers, people operations teams, and talent acquisition platforms\n    building cross-system workforce management tools.\n  tags:\n  - Unified.to\n  - HRIS\n  - ATS\n  - HR\n  - Recruiting\n  - Employees\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UNIFIED_TO_API_KEY: UNIFIED_TO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: unified-hris\n    baseUri: https://api.unified.to\n    description: Unified HRIS API for employee, group, and payroll data.\n    authentication:\n      type: bearer\n      token: '{{UNIFIED_TO_API_KEY}}'\n    resources:\n    - name: employees\n      path: /hris/{connection_id}/employee\n      description: Employee data management\n    \
  \  operations:\n      - name: list-hris-employees\n        method: GET\n        description: List HRIS employees\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: HRIS integration connection ID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-hris-employee\n        method: POST\n        description: Create a new employee record\n        inputParameters:\n        - name: connection_id\n\
  \          in: path\n          type: string\n          required: true\n          description: HRIS integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-hris-employee\n        method: GET\n        description: Get a specific employee by ID\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: HRIS integration connection ID\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Employee ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-hris-employee\n        method: PUT\n        description: Update an existing employee record\n        inputParameters:\n        - name: connection_id\n          in: path\n          type:\
  \ string\n          required: true\n          description: HRIS integration connection ID\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Employee ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /hris/{connection_id}/group\n      description: HR group and department management\n      operations:\n      - name: list-hris-groups\n        method: GET\n        description: List HR groups and departments\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: HRIS integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payslips\n      path: /hris/{connection_id}/payslip\n      description: Payslip data access\n\
  \      operations:\n      - name: list-hris-payslips\n        method: GET\n        description: List payslips for employees\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: HRIS integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: unified-ats\n    baseUri: https://api.unified.to\n    description: Unified ATS API for recruiting and talent acquisition.\n    authentication:\n      type: bearer\n      token: '{{UNIFIED_TO_API_KEY}}'\n    resources:\n    - name: jobs\n      path: /ats/{connection_id}/job\n      description: Job posting management\n      operations:\n      - name: list-ats-jobs\n        method: GET\n        description: List job postings\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n      \
  \    required: true\n          description: ATS integration connection ID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates\n      path: /ats/{connection_id}/candidate\n      description: Candidate profile management\n      operations:\n      - name: list-ats-candidates\n        method: GET\n        description: List candidates\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: ATS integration connection ID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: query\n          in: query\n          type: string\n          required: false\n\
  \          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ats-candidate\n        method: POST\n        description: Create a new candidate\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: ATS integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /ats/{connection_id}/application\n      description: Job application management\n      operations:\n      - name: list-ats-applications\n        method: GET\n        description: List job applications\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: ATS integration connection ID\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: interviews\n      path: /ats/{connection_id}/interview\n      description: Interview management\n      operations:\n      - name: list-ats-interviews\n        method: GET\n        description: List interviews\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: ATS integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: unified-hr-talent-api\n    description: Unified REST API for HR and talent management across 296+ integrations.\n    resources:\n    - path: /v1/hris/{connection_id}/employees\n      name: employees\n      description: Employee data across HRIS integrations\n      operations:\n      -\
  \ method: GET\n        name: list-hris-employees\n        description: List employees from an HRIS integration\n        call: unified-hris.list-hris-employees\n        with:\n          connection_id: rest.connection_id\n          query: rest.query\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-hris-employee\n        description: Create a new employee record\n        call: unified-hris.create-hris-employee\n        with:\n          connection_id: rest.connection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hris/{connection_id}/groups\n      name: groups\n      description: HR groups and departments\n      operations:\n      - method: GET\n        name: list-hris-groups\n        description: List HR groups and departments\n        call: unified-hris.list-hris-groups\n        with:\n          connection_id: rest.connection_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/hris/{connection_id}/payslips\n      name: payslips\n      description: Employee payslip data\n      operations:\n      - method: GET\n        name: list-hris-payslips\n        description: List employee payslips\n        call: unified-hris.list-hris-payslips\n        with:\n          connection_id: rest.connection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ats/{connection_id}/jobs\n      name: jobs\n      description: Job postings from ATS integrations\n      operations:\n      - method: GET\n        name: list-ats-jobs\n        description: List open job postings\n        call: unified-ats.list-ats-jobs\n        with:\n          connection_id: rest.connection_id\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ats/{connection_id}/candidates\n      name: candidates\n      description: Candidate profiles\
  \ from ATS integrations\n      operations:\n      - method: GET\n        name: list-ats-candidates\n        description: List candidates\n        call: unified-ats.list-ats-candidates\n        with:\n          connection_id: rest.connection_id\n          query: rest.query\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-ats-candidate\n        description: Create a new candidate\n        call: unified-ats.create-ats-candidate\n        with:\n          connection_id: rest.connection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ats/{connection_id}/applications\n      name: applications\n      description: Job applications from ATS integrations\n      operations:\n      - method: GET\n        name: list-ats-applications\n        description: List job applications\n        call: unified-ats.list-ats-applications\n        with:\n          connection_id:\
  \ rest.connection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: unified-hr-talent-mcp\n    transport: http\n    description: MCP server for AI-assisted HR and talent operations across 296+ integrations.\n    tools:\n    - name: list-hris-employees\n      description: List employees from a connected HRIS integration (Workday, BambooHR, ADP, etc.)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-hris.list-hris-employees\n      with:\n        connection_id: tools.connection_id\n        query: tools.query\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-hris-employee\n      description: Create a new employee record in a connected HRIS integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: unified-hris.create-hris-employee\n      with:\n        connection_id:\
  \ tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-hris-groups\n      description: List HR groups and departments from a connected HRIS integration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-hris.list-hris-groups\n      with:\n        connection_id: tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-hris-payslips\n      description: List employee payslips from a connected HRIS integration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-hris.list-hris-payslips\n      with:\n        connection_id: tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ats-jobs\n      description: List open job postings from a connected ATS integration (Greenhouse, Lever, etc.)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-ats.list-ats-jobs\n\
  \      with:\n        connection_id: tools.connection_id\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ats-candidates\n      description: List candidates from a connected ATS integration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-ats.list-ats-candidates\n      with:\n        connection_id: tools.connection_id\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-ats-candidate\n      description: Create a new candidate in a connected ATS integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: unified-ats.create-ats-candidate\n      with:\n        connection_id: tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ats-applications\n      description: List job applications from a connected ATS integration\n\
  \      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-ats.list-ats-applications\n      with:\n        connection_id: tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ats-interviews\n      description: List scheduled interviews from a connected ATS integration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-ats.list-ats-interviews\n      with:\n        connection_id: tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unified-to/refs/heads/main/capabilities/hr-and-talent.yaml
tags:
- Unified.to
- HRIS
- ATS
- HR
- Recruiting
- Employees
tools:
- description: List employees from a connected HRIS integration (Workday, BambooHR, ADP, etc.)
  hints:
    openWorld: false
    readOnly: true
  name: list-hris-employees
- description: Create a new employee record in a connected HRIS integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-hris-employee
- description: List HR groups and departments from a connected HRIS integration
  hints:
    openWorld: false
    readOnly: true
  name: list-hris-groups
- description: List employee payslips from a connected HRIS integration
  hints:
    openWorld: false
    readOnly: true
  name: list-hris-payslips
- description: List open job postings from a connected ATS integration (Greenhouse, Lever, etc.)
  hints:
    openWorld: false
    readOnly: true
  name: list-ats-jobs
- description: List candidates from a connected ATS integration
  hints:
    openWorld: false
    readOnly: true
  name: list-ats-candidates
- description: Create a new candidate in a connected ATS integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-ats-candidate
- description: List job applications from a connected ATS integration
  hints:
    openWorld: false
    readOnly: true
  name: list-ats-applications
- description: List scheduled interviews from a connected ATS integration
  hints:
    openWorld: false
    readOnly: true
  name: list-ats-interviews
---
