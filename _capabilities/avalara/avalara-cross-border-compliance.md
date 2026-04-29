---
categories: []
consumed_apis:
- avatax
- einvoicing
description: Workflow for cross-border trade combining tariff classification, VAT calculation, and e-invoicing mandates. Used by international trade teams and importers/exporters to automate customs and tax compliance.
layout: capability
name: Avalara Cross-Border Trade Compliance
operations:
- description: Calculate import duties and VAT for cross-border shipment
  method: POST
  name: calculate-import-duties
  path: /v1/transactions
- description: List country e-invoicing mandates
  method: GET
  name: list-mandates
  path: /v1/einvoicing/mandates
personas: []
provider_name: Avalara
provider_slug: avalara
search_terms:
- cross-border tax calculations
- submit cross border einvoice
- integrates avalara apis into erp and billing systems
- hs codes
- tariff
- manages sales tax compliance, exemption certificates, and returns filing
- oversees tax strategy, compliance automation, and cost optimization
- country-specific e-invoicing mandate compliance
- real-time tax calculation across us and global jurisdictions
- vat
- cross-border
- calculate import duties
- Finance Director
- hs code and tax code classification for products
- calculate import duties and vat for cross-border shipment
- vat returns, 1099 filing, and lodging tax reporting
- list country e-invoicing mandates
- e-invoicing
- import duties, vat, and e-invoicing for international trade
- calculate import duties, customs fees, and vat for cross-border shipments
- avalara
- list mandates
- check e-invoicing compliance requirements for a destination country
- sales tax calculation, certificate management, and e-invoicing
- tax exemption certificate collection and validation
- e-invoicing mandates by country
- International Trade Manager
- Tax Manager
- manages cross-border compliance, tariff classification, and e-invoicing
- submit a cross-border e-invoice for customs and vat compliance
- check country einvoicing mandate
- taxes
slug: avalara-cross-border-compliance
source_filename: avalara-cross-border-compliance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Avalara Cross-Border Trade Compliance\n  description: Workflow for cross-border trade combining tariff classification, VAT calculation, and e-invoicing mandates. Used by international trade teams and importers/exporters to automate customs\n    and tax compliance.\n  tags:\n  - Avalara\n  - Cross-Border\n  - Tariff\n  - HS Codes\n  - E-Invoicing\n  - VAT\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AVALARA_USERNAME: AVALARA_USERNAME\n    AVALARA_PASSWORD: AVALARA_PASSWORD\n    AVALARA_BEARER_TOKEN: AVALARA_BEARER_TOKEN\ncapability:\n  consumes:\n  - import: avatax\n    location: ./shared/avatax.yaml\n  - import: einvoicing\n    location: ./shared/einvoicing.yaml\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: avalara-crossborder-api\n    description: REST API for cross-border trade compliance.\n    resources:\n    - path: /v1/transactions\n      name: transactions\n      description:\
  \ Cross-border tax calculations\n      operations:\n      - method: POST\n        name: calculate-import-duties\n        description: Calculate import duties and VAT for cross-border shipment\n        call: avatax.create-transaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/einvoicing/mandates\n      name: mandates\n      description: E-invoicing mandates by country\n      operations:\n      - method: GET\n        name: list-mandates\n        description: List country e-invoicing mandates\n        call: einvoicing.list-mandates\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: avalara-crossborder-mcp\n    transport: http\n    description: MCP server for AI-assisted cross-border compliance.\n    tools:\n    - name: calculate-import-duties\n      description: Calculate import duties, customs fees, and VAT for cross-border shipments\n      hints:\n        readOnly: false\n\
  \        openWorld: true\n      call: avatax.create-transaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-country-einvoicing-mandate\n      description: Check e-invoicing compliance requirements for a destination country\n      hints:\n        readOnly: true\n        openWorld: true\n      call: einvoicing.list-mandates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-cross-border-einvoice\n      description: Submit a cross-border e-invoice for customs and VAT compliance\n      hints:\n        readOnly: false\n        openWorld: true\n      call: einvoicing.submit-document\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/avalara/refs/heads/main/capabilities/avalara-cross-border-compliance.yaml
tags:
- Avalara
- Cross-Border
- Tariff
- HS Codes
- E-Invoicing
- VAT
tools:
- description: Calculate import duties, customs fees, and VAT for cross-border shipments
  hints:
    openWorld: true
    readOnly: false
  name: calculate-import-duties
- description: Check e-invoicing compliance requirements for a destination country
  hints:
    openWorld: true
    readOnly: true
  name: check-country-einvoicing-mandate
- description: Submit a cross-border e-invoice for customs and VAT compliance
  hints:
    openWorld: true
    readOnly: false
  name: submit-cross-border-einvoice
---
