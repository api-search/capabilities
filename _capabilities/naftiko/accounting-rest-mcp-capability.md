---
categories: []
consumed_apis: []
description: A accounting-API capability (REST + MCP dual exposure) wrapping a representative endpoint, brought as the apidays NYC follow-on artifact.
layout: capability
name: Accounting Rest Mcp Capability
operations:
- description: List all open (non-zero balance) invoices.
  method: GET
  name: list-open-invoices
  path: /invoices
- description: Get a single invoice by ID.
  method: GET
  name: get-invoice
  path: /invoices/{{invoice_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- list all open invoices in the bound quickbooks company.
- get invoice
- spec-driven integration
- get customer
- governance
- list open invoices
- mcp
- ai
- capabilities
- quickbooks
- naftiko
- api integration
- list all open (non-zero balance) invoices.
- get a single quickbooks invoice by id.
- accounting
- get a quickbooks customer by id.
- get a single invoice by id.
slug: accounting-rest-mcp-capability
source_filename: accounting-rest-mcp-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Accounting Rest Mcp Capability\n  description: A accounting-API capability (REST + MCP dual exposure) wrapping a representative endpoint, brought as the apidays NYC follow-on artifact.\n  tags:\n  - Naftiko\n  - Accounting\n  - QuickBooks\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: quickbooks-env\n  description: Intuit QuickBooks Online OAuth2 bearer and realm (company) ID.\n  keys:\n    QB_TOKEN: QB_TOKEN\n    QB_REALM_ID: QB_REALM_ID\ncapability:\n  consumes:\n  - namespace: quickbooks\n    type: http\n    baseUri: https://quickbooks.api.intuit.com\n    authentication:\n      type: bearer\n      token: '{{QB_TOKEN}}'\n    resources:\n    - name: invoices\n      path: /v3/company/{{QB_REALM_ID}}/query\n      operations:\n      - name: query-invoices\n        method: GET\n        inputParameters:\n        - name: query\n          in: query\n          description: SQL-like QBO query, e.g. 'select * from Invoice\
  \ where Balance > 0'.\n    - name: invoice\n      path: /v3/company/{{QB_REALM_ID}}/invoice/{{invoice_id}}\n      operations:\n      - name: get-invoice\n        method: GET\n        inputParameters:\n        - name: invoice_id\n          in: path\n    - name: customers\n      path: /v3/company/{{QB_REALM_ID}}/customer/{{customer_id}}\n      operations:\n      - name: get-customer\n        method: GET\n        inputParameters:\n        - name: customer_id\n          in: path\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: accounting-rest-mcp-capability-rest\n    description: REST surface over QuickBooks invoices and customers.\n    resources:\n    - name: invoices\n      path: /invoices\n      operations:\n      - method: GET\n        name: list-open-invoices\n        description: List all open (non-zero balance) invoices.\n        call: quickbooks.query-invoices\n    - name: invoice\n      path: /invoices/{{invoice_id}}\n      operations:\n      - method:\
  \ GET\n        name: get-invoice\n        description: Get a single invoice by ID.\n        inputParameters:\n        - name: invoice_id\n          in: path\n          type: string\n        call: quickbooks.get-invoice\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: accounting-rest-mcp-capability-mcp\n    description: MCP server giving agents typed access to QuickBooks accounting data.\n    tools:\n    - name: list-open-invoices\n      description: List all open invoices in the bound QuickBooks company.\n      hints:\n        readOnly: true\n      call: quickbooks.query-invoices\n    - name: get-invoice\n      description: Get a single QuickBooks invoice by ID.\n      hints:\n        readOnly: true\n      inputParameters:\n      - name: invoice_id\n        type: string\n        required: true\n      call: quickbooks.get-invoice\n    - name: get-customer\n      description: Get a QuickBooks customer by ID.\n      hints:\n        readOnly: true\n      inputParameters:\n\
  \      - name: customer_id\n        type: string\n        required: true\n      call: quickbooks.get-customer\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: accounting-rest-mcp-capability-skills\n    description: Agent Skill bundle for QuickBooks accounting access.\n    skills:\n    - name: accounting-rest-mcp-capability\n      description: REST + MCP dual exposure of QuickBooks accounting data.\n      location: file:///opt/naftiko/skills/accounting-rest-mcp-capability\n      allowed-tools: list-open-invoices,get-invoice,get-customer\n      tools:\n      - name: list-open-invoices\n        description: List open invoices.\n        from:\n          sourceNamespace: accounting-rest-mcp-capability-mcp\n          action: list-open-invoices\n      - name: get-invoice\n        description: Get an invoice.\n        from:\n          sourceNamespace: accounting-rest-mcp-capability-mcp\n          action: get-invoice\n      - name: get-customer\n        description: Get a\
  \ customer.\n        from:\n          sourceNamespace: accounting-rest-mcp-capability-mcp\n          action: get-customer\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/accounting-rest-mcp-capability.yaml
tags:
- Naftiko
- Accounting
- QuickBooks
tools:
- description: List all open invoices in the bound QuickBooks company.
  hints:
    readOnly: true
  name: list-open-invoices
- description: Get a single QuickBooks invoice by ID.
  hints:
    readOnly: true
  name: get-invoice
- description: Get a QuickBooks customer by ID.
  hints:
    readOnly: true
  name: get-customer
---
