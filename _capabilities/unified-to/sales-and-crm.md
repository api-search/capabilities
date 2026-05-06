---
categories: []
consumed_apis: []
description: Unified sales and CRM workflow combining contacts, companies, deals, and activities across 47+ CRM integrations including Salesforce, HubSpot, Pipedrive, and Zoho. Used by revenue operations teams, sales developers, and CRM integrators building cross-platform sales tooling.
layout: capability
name: Unified.to Sales and CRM
operations:
- description: List contacts from a CRM integration
  method: GET
  name: list-crm-contacts
  path: /v1/crm/{connection_id}/contacts
- description: Create a new contact in a CRM integration
  method: POST
  name: create-crm-contact
  path: /v1/crm/{connection_id}/contacts
- description: List companies from a CRM integration
  method: GET
  name: list-crm-companies
  path: /v1/crm/{connection_id}/companies
- description: List deals from a CRM integration
  method: GET
  name: list-crm-deals
  path: /v1/crm/{connection_id}/deals
- description: Create a new deal in a CRM integration
  method: POST
  name: create-crm-deal
  path: /v1/crm/{connection_id}/deals
personas: []
provider_name: Unified.to
provider_slug: unified-to
search_terms:
- sales
- Revenue Operations Developer
- create crm contact
- developers building hr workflows, employee onboarding, and recruiting automation
- hris and ats management across 296+ hr and recruiting integrations
- developers building invoicing automation, expense management, and accounting sync
- crm deal and opportunity management
- People Operations Engineer
- deals
- unified.to
- contacts
- list deals and opportunities from a connected crm integration
- crm company management across all integrations
- developers building sales tools, crm sync, and revenue reporting integrations
- unified api
- list deals from a crm integration
- create a new deal in a crm integration
- list crm companies
- create crm deal
- list companies from a crm integration
- Finance Operations Engineer
- list contacts from a connected crm integration (salesforce, hubspot, pipedrive, etc.)
- list crm deals
- crm contact, company, and deal management across 47+ integrations
- integrations
- crm contact management across all integrations
- crm
- list contacts from a crm integration
- list crm contacts
- Fintech Developer
- create a new contact in a crm integration
- HR Technology Developer
- CRM Integrator
- create a new deal or opportunity in a connected crm integration
- create a new contact in a connected crm integration
- list companies from a connected crm integration
- accounting, invoicing, and payment management across 41+ integrations
slug: sales-and-crm
source_filename: sales-and-crm.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Unified.to Sales and CRM\n  description: Unified sales and CRM workflow combining contacts, companies, deals, and activities across 47+ CRM integrations\n    including Salesforce, HubSpot, Pipedrive, and Zoho. Used by revenue operations teams, sales developers, and CRM integrators\n    building cross-platform sales tooling.\n  tags:\n  - Unified.to\n  - CRM\n  - Sales\n  - Contacts\n  - Deals\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UNIFIED_TO_API_KEY: UNIFIED_TO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: unified-crm\n    baseUri: https://api.unified.to\n    description: Unified CRM API for contacts, companies, deals, and events.\n    authentication:\n      type: bearer\n      token: '{{UNIFIED_TO_API_KEY}}'\n    resources:\n    - name: contacts\n      path: /crm/{connection_id}/contact\n      description: CRM contact management\n      operations:\n      - name: list-crm-contacts\n\
  \        method: GET\n        description: List CRM contacts\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: CRM integration connection ID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-crm-contact\n        method: POST\n        description: Create a CRM contact\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: CRM integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies\n      path: /crm/{connection_id}/company\n      description: CRM company management\n      operations:\n      - name: list-crm-companies\n        method: GET\n        description: List CRM companies\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: CRM integration connection ID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-crm-company\n        method: POST\n        description: Create a CRM company\n        inputParameters:\n        -\
  \ name: connection_id\n          in: path\n          type: string\n          required: true\n          description: CRM integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deals\n      path: /crm/{connection_id}/deal\n      description: CRM deal management\n      operations:\n      - name: list-crm-deals\n        method: GET\n        description: List CRM deals\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: CRM integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-crm-deal\n        method: POST\n        description: Create a CRM deal\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: CRM integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: unified-sales-crm-api\n    description: Unified REST API for sales and CRM data across 47+ integrations.\n    resources:\n    - path: /v1/crm/{connection_id}/contacts\n      name: contacts\n      description: CRM contact management across all integrations\n      operations:\n      - method: GET\n        name: list-crm-contacts\n        description: List contacts from a CRM integration\n        call: unified-crm.list-crm-contacts\n        with:\n          connection_id: rest.connection_id\n          query: rest.query\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-crm-contact\n        description: Create a new contact\
  \ in a CRM integration\n        call: unified-crm.create-crm-contact\n        with:\n          connection_id: rest.connection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/crm/{connection_id}/companies\n      name: companies\n      description: CRM company management across all integrations\n      operations:\n      - method: GET\n        name: list-crm-companies\n        description: List companies from a CRM integration\n        call: unified-crm.list-crm-companies\n        with:\n          connection_id: rest.connection_id\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/crm/{connection_id}/deals\n      name: deals\n      description: CRM deal and opportunity management\n      operations:\n      - method: GET\n        name: list-crm-deals\n        description: List deals from a CRM integration\n        call: unified-crm.list-crm-deals\n        with:\n          connection_id:\
  \ rest.connection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-crm-deal\n        description: Create a new deal in a CRM integration\n        call: unified-crm.create-crm-deal\n        with:\n          connection_id: rest.connection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: unified-sales-crm-mcp\n    transport: http\n    description: MCP server for AI-assisted sales and CRM operations across 47+ integrations.\n    tools:\n    - name: list-crm-contacts\n      description: List contacts from a connected CRM integration (Salesforce, HubSpot, Pipedrive, etc.)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-crm.list-crm-contacts\n      with:\n        connection_id: tools.connection_id\n        query: tools.query\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: create-crm-contact\n      description: Create a new contact in a connected CRM integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: unified-crm.create-crm-contact\n      with:\n        connection_id: tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-crm-companies\n      description: List companies from a connected CRM integration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-crm.list-crm-companies\n      with:\n        connection_id: tools.connection_id\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-crm-deals\n      description: List deals and opportunities from a connected CRM integration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-crm.list-crm-deals\n      with:\n        connection_id: tools.connection_id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-crm-deal\n      description: Create a new deal or opportunity in a connected CRM integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: unified-crm.create-crm-deal\n      with:\n        connection_id: tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unified-to/refs/heads/main/capabilities/sales-and-crm.yaml
tags:
- Unified.to
- CRM
- Sales
- Contacts
- Deals
tools:
- description: List contacts from a connected CRM integration (Salesforce, HubSpot, Pipedrive, etc.)
  hints:
    openWorld: false
    readOnly: true
  name: list-crm-contacts
- description: Create a new contact in a connected CRM integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-crm-contact
- description: List companies from a connected CRM integration
  hints:
    openWorld: false
    readOnly: true
  name: list-crm-companies
- description: List deals and opportunities from a connected CRM integration
  hints:
    openWorld: false
    readOnly: true
  name: list-crm-deals
- description: Create a new deal or opportunity in a connected CRM integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-crm-deal
---
