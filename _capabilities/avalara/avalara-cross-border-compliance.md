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
- check country einvoicing mandate
- manages sales tax compliance, exemption certificates, and returns filing
- check e-invoicing compliance requirements for a destination country
- oversees tax strategy, compliance automation, and cost optimization
- submit a cross-border e-invoice for customs and vat compliance
- e-invoicing
- submit cross border einvoice
- calculate import duties, customs fees, and vat for cross-border shipments
- International Trade Manager
- calculate import duties and vat for cross-border shipment
- e-invoicing mandates by country
- cross-border tax calculations
- Finance Director
- hs codes
- real-time tax calculation across us and global jurisdictions
- list mandates
- vat
- country-specific e-invoicing mandate compliance
- integrates avalara apis into erp and billing systems
- sales tax calculation, certificate management, and e-invoicing
- Tax Manager
- calculate import duties
- hs code and tax code classification for products
- import duties, vat, and e-invoicing for international trade
- cross-border
- tax exemption certificate collection and validation
- vat returns, 1099 filing, and lodging tax reporting
- tariff
- manages cross-border compliance, tariff classification, and e-invoicing
- taxes
- avalara
- list country e-invoicing mandates
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
