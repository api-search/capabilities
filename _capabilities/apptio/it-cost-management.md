---
categories: []
consumed_apis: []
description: Workflow capability for managing IT costs and technology investments using Apptio. Supports IT finance teams analyzing technology spending, tracking budgets, and generating cost allocation reports for business stakeholders.
layout: capability
name: Apptio IT Cost Management
operations: []
personas: []
provider_name: Apptio
provider_slug: apptio
search_terms:
- tracking and allocating technology costs by department
- analytics
- get financial reports
- technology business management
- apptio
- it finance
- reviews it budget plans and tracks spending against targets
- retrieves technology business management reports for executive review
- planning and monitoring it budget spending
- generating financial and technology management reports
- review it budgets
- manages technology cost allocations and budget planning
- lists and analyzes technology cost allocations by department and category
- analyze technology costs
- reviews technology investment performance and cost trends
- cost management
- analyze technology spending and manage it budgets with apptio
slug: it-cost-management
source_filename: it-cost-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apptio IT Cost Management\n  description: Workflow capability for managing IT costs and technology investments using Apptio. Supports IT finance teams\n    analyzing technology spending, tracking budgets, and generating cost allocation reports for business stakeholders.\n  tags:\n  - Apptio\n  - IT Finance\n  - Cost Management\n  - Technology Business Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APPTIO_API_TOKEN: APPTIO_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: apptio\n    baseUri: https://api.apptio.com/v1\n    description: Apptio TBM API\n    authentication:\n      type: bearer\n      token: '{{APPTIO_API_TOKEN}}'\n    resources:\n    - name: cost-allocations\n      path: /cost-allocations\n      description: Technology cost allocation records\n      operations:\n      - name: list-cost-allocations\n        method: GET\n        description: Returns cost\
  \ allocation records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cost-allocation\n        method: GET\n        description: Returns a specific cost allocation\n        inputParameters:\n        - name: allocationId\n          in: path\n          type: string\n          required: true\n          description: Allocation identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: budgets\n      path: /budgets\n      description: IT budget management\n      operations:\n      - name: list-budgets\n        method: GET\n        description: Returns IT budgets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /reports\n      description: Financial reports\n      operations:\n      - name: list-reports\n\
  \        method: GET\n        description: Returns available financial reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9090\n    namespace: it-cost-mcp\n    transport: http\n    description: MCP server for AI-assisted IT cost management with Apptio.\n    tools:\n    - name: analyze-technology-costs\n      description: Lists and analyzes technology cost allocations by department and category\n      hints:\n        readOnly: true\n        idempotent: true\n      call: apptio.list-cost-allocations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: review-it-budgets\n      description: Reviews IT budget plans and tracks spending against targets\n      hints:\n        readOnly: true\n        idempotent: true\n      call: apptio.list-budgets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-financial-reports\n\
  \      description: Retrieves technology business management reports for executive review\n      hints:\n        readOnly: true\n        idempotent: true\n      call: apptio.list-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apptio/refs/heads/main/capabilities/it-cost-management.yaml
tags:
- Apptio
- IT Finance
- Cost Management
- Technology Business Management
tools:
- description: Lists and analyzes technology cost allocations by department and category
  hints:
    idempotent: true
    readOnly: true
  name: analyze-technology-costs
- description: Reviews IT budget plans and tracks spending against targets
  hints:
    idempotent: true
    readOnly: true
  name: review-it-budgets
- description: Retrieves technology business management reports for executive review
  hints:
    idempotent: true
    readOnly: true
  name: get-financial-reports
---
