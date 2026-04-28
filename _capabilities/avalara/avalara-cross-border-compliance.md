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
- calculate import duties
- hs code and tax code classification for products
- vat returns, 1099 filing, and lodging tax reporting
- calculate import duties, customs fees, and vat for cross-border shipments
- country-specific e-invoicing mandate compliance
- integrates avalara apis into erp and billing systems
- taxes
- cross-border tax calculations
- Finance Director
- manages cross-border compliance, tariff classification, and e-invoicing
- import duties, vat, and e-invoicing for international trade
- list mandates
- list country e-invoicing mandates
- tax exemption certificate collection and validation
- Tax Manager
- submit cross border einvoice
- real-time tax calculation across us and global jurisdictions
- check country einvoicing mandate
- submit a cross-border e-invoice for customs and vat compliance
- tariff
- sales tax calculation, certificate management, and e-invoicing
- cross-border
- e-invoicing
- check e-invoicing compliance requirements for a destination country
- avalara
- manages sales tax compliance, exemption certificates, and returns filing
- hs codes
- e-invoicing mandates by country
- calculate import duties and vat for cross-border shipment
- vat
- International Trade Manager
- oversees tax strategy, compliance automation, and cost optimization
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
