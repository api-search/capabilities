---
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
- submit cross border einvoice
- list country e-invoicing mandates
- sales tax calculation, certificate management, and e-invoicing
- submit a cross-border e-invoice for customs and vat compliance
- integrates avalara apis into erp and billing systems
- Tax Manager
- vat
- calculate import duties, customs fees, and vat for cross-border shipments
- tariff
- e-invoicing mandates by country
- import duties, vat, and e-invoicing for international trade
- oversees tax strategy, compliance automation, and cost optimization
- calculate import duties and vat for cross-border shipment
- avalara
- calculate import duties
- tax exemption certificate collection and validation
- country-specific e-invoicing mandate compliance
- real-time tax calculation across us and global jurisdictions
- hs code and tax code classification for products
- taxes
- e-invoicing
- Finance Director
- International Trade Manager
- check country einvoicing mandate
- list mandates
- hs codes
- check e-invoicing compliance requirements for a destination country
- vat returns, 1099 filing, and lodging tax reporting
- manages sales tax compliance, exemption certificates, and returns filing
- cross-border tax calculations
- cross-border
- manages cross-border compliance, tariff classification, and e-invoicing
slug: avalara-cross-border-compliance
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
