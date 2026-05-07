---
categories: []
consumed_apis: []
description: Public FHIR-based Drug Formulary API exposing Cigna's covered drug lists, formulary tiers, prior authorization, step therapy, and quantity limits. Implements the HL7 Da Vinci PDex US Drug Formulary IG required by the CMS Interoperability and Patient Access rule.
layout: capability
name: Cigna Drug Formulary API
operations:
- description: Retrieve the FHIR capability statement
  method: GET
  name: getcapabilitystatement
  path: /metadata
- description: List drug formulary plans offered by Cigna
  method: GET
  name: searchformularyplan
  path: /InsurancePlan
- description: Search covered drugs and formulary tier, step therapy, and prior auth
  method: GET
  name: searchmedicationknowledge
  path: /MedicationKnowledge
personas: []
provider_name: Cigna
provider_slug: cigna
search_terms:
- retrieve the fhir capability statement
- smart on fhir
- provider directory
- list drug formulary plans offered by cigna
- cms interoperability
- da vinci
- getcapabilitystatement
- searchformularyplan
- searchmedicationknowledge
- fhir
- health insurance
- healthcare
- api
- drug formulary
- cigna
- patient access
- search covered drugs and formulary tier, step therapy, and prior auth
slug: cigna-capability
source_filename: cigna-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Cigna Drug Formulary API\n  description: Public FHIR-based Drug Formulary API exposing Cigna's covered drug lists, formulary tiers, prior authorization,\n    step therapy, and quantity limits. Implements the HL7 Da Vinci PDex US Drug Formulary IG required by the CMS Interoperability\n    and Patient Access rule.\n  tags:\n  - Cigna\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: cigna\n    baseUri: https://fhir.cigna.com/DrugFormulary/v1\n    description: Cigna Drug Formulary API HTTP API.\n    resources:\n    - name: metadata\n      path: /metadata\n      operations:\n      - name: getcapabilitystatement\n        method: GET\n        description: Retrieve the FHIR capability statement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insuranceplan\n      path: /InsurancePlan\n\
  \      operations:\n      - name: searchformularyplan\n        method: GET\n        description: List drug formulary plans offered by Cigna\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: medicationknowledge\n      path: /MedicationKnowledge\n      operations:\n      - name: searchmedicationknowledge\n        method: GET\n        description: Search covered drugs and formulary tier, step therapy, and prior auth\n        inputParameters:\n        - name: code\n          in: query\n          type: string\n          description: RxNorm or NDC code\n        - name: DrugPlan\n          in: query\n          type: string\n          description: InsurancePlan id of the formulary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: cigna-rest\n    description: REST adapter for Cigna Drug Formulary API.\n    resources:\n    - path: /metadata\n      name: getcapabilitystatement\n      operations:\n      - method: GET\n        name: getcapabilitystatement\n        description: Retrieve the FHIR capability statement\n        call: cigna.getcapabilitystatement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /InsurancePlan\n      name: searchformularyplan\n      operations:\n      - method: GET\n        name: searchformularyplan\n        description: List drug formulary plans offered by Cigna\n        call: cigna.searchformularyplan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /MedicationKnowledge\n      name: searchmedicationknowledge\n      operations:\n      - method: GET\n        name: searchmedicationknowledge\n        description: Search covered drugs and formulary tier, step therapy, and\
  \ prior auth\n        call: cigna.searchmedicationknowledge\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cigna-mcp\n    transport: http\n    description: MCP adapter for Cigna Drug Formulary API for AI agent use.\n    tools:\n    - name: getcapabilitystatement\n      description: Retrieve the FHIR capability statement\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cigna.getcapabilitystatement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchformularyplan\n      description: List drug formulary plans offered by Cigna\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cigna.searchformularyplan\n      with:\n        status: tools.status\n      inputParameters:\n      - name: status\n        type: string\n        description: status\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: searchmedicationknowledge\n      description: Search covered drugs and formulary tier, step therapy, and prior auth\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cigna.searchmedicationknowledge\n      with:\n        code: tools.code\n        DrugPlan: tools.DrugPlan\n      inputParameters:\n      - name: code\n        type: string\n        description: RxNorm or NDC code\n      - name: DrugPlan\n        type: string\n        description: InsurancePlan id of the formulary\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cigna/refs/heads/main/capabilities/cigna-capability.yaml
tags:
- Cigna
- API
tools:
- description: Retrieve the FHIR capability statement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcapabilitystatement
- description: List drug formulary plans offered by Cigna
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchformularyplan
- description: Search covered drugs and formulary tier, step therapy, and prior auth
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchmedicationknowledge
---
