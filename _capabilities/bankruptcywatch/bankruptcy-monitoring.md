---
categories: []
consumed_apis:
- bankruptcywatch-pacer
description: BankruptcyWatch bankruptcy monitoring and case management workflow for creditors, lenders, and legal teams. Covers case search, docket retrieval, claims management, Proof of Claim filing, and automated bankruptcy monitoring alerts.
layout: capability
name: BankruptcyWatch Bankruptcy Monitoring
operations: []
personas: []
provider_name: BankruptcyWatch
provider_slug: bankruptcywatch
search_terms:
- get case docket
- lending
- list claims register for a bankruptcy case
- file a proof of claim for a bankruptcy case
- list monitors
- Bankruptcy Attorney
- retrieve docket entries for a bankruptcy case
- get bankruptcy case
- attorney managing creditor representation in bankruptcy proceedings
- create a bankruptcy monitoring alert for a debtor or entity
- Creditor
- creditor
- pacer
- bankruptcy case research, claims management, and automated monitoring
- us bankruptcy court cases and proceedings
- legal
- bankruptcy
- search bankruptcy cases
- Loan Officer
- create bankruptcy monitor
- automated alerts for bankruptcy filings
- court data
- list case claims
- search for bankruptcy cases across all us bankruptcy court districts
- business or individual owed money by a bankruptcy filer
- get detailed information about a specific bankruptcy case
- lender monitoring borrowers for bankruptcy filings
- compliance
- list all active bankruptcy monitoring alerts
- file proof of claim
- bankruptcywatch
slug: bankruptcy-monitoring
source_filename: bankruptcy-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"BankruptcyWatch Bankruptcy Monitoring\"\n  description: >-\n    BankruptcyWatch bankruptcy monitoring and case management workflow for creditors,\n    lenders, and legal teams. Covers case search, docket retrieval, claims management,\n    Proof of Claim filing, and automated bankruptcy monitoring alerts.\n  tags:\n    - BankruptcyWatch\n    - Bankruptcy\n    - PACER\n    - Creditor\n    - Legal\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BANKRUPTCYWATCH_API_KEY: BANKRUPTCYWATCH_API_KEY\n\ncapability:\n  consumes:\n    - import: bankruptcywatch-pacer\n      location: ./shared/pacer-api.yaml\n\n  exposes:\n    - type: mcp\n      port: 9080\n      namespace: bankruptcywatch-mcp\n      transport: http\n      description: \"MCP server for AI-assisted bankruptcy monitoring and case research.\"\n      tools:\n        - name: search-bankruptcy-cases\n          description: Search\
  \ for bankruptcy cases across all US bankruptcy court districts\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"bankruptcywatch-pacer.searchCases\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-bankruptcy-case\n          description: Get detailed information about a specific bankruptcy case\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bankruptcywatch-pacer.getCase\"\n          with:\n            caseId: \"tools.caseId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-case-docket\n          description: Retrieve docket entries for a bankruptcy case\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bankruptcywatch-pacer.getCaseDocket\"\n          with:\n            caseId: \"tools.caseId\"\n          outputParameters:\n       \
  \     - type: object\n              mapping: \"$.\"\n        - name: list-case-claims\n          description: List claims register for a bankruptcy case\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bankruptcywatch-pacer.listClaims\"\n          with:\n            caseId: \"tools.caseId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: file-proof-of-claim\n          description: File a Proof of Claim for a bankruptcy case\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"bankruptcywatch-pacer.fileProofOfClaim\"\n          with:\n            caseId: \"tools.caseId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bankruptcy-monitor\n          description: Create a bankruptcy monitoring alert for a debtor or entity\n          hints:\n            readOnly: false\n            openWorld:\
  \ false\n          call: \"bankruptcywatch-pacer.createMonitor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-monitors\n          description: List all active bankruptcy monitoring alerts\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bankruptcywatch-pacer.listMonitors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bankruptcywatch/refs/heads/main/capabilities/bankruptcy-monitoring.yaml
tags:
- BankruptcyWatch
- Bankruptcy
- PACER
- Creditor
- Legal
tools:
- description: Search for bankruptcy cases across all US bankruptcy court districts
  hints:
    openWorld: true
    readOnly: true
  name: search-bankruptcy-cases
- description: Get detailed information about a specific bankruptcy case
  hints:
    openWorld: false
    readOnly: true
  name: get-bankruptcy-case
- description: Retrieve docket entries for a bankruptcy case
  hints:
    openWorld: false
    readOnly: true
  name: get-case-docket
- description: List claims register for a bankruptcy case
  hints:
    openWorld: false
    readOnly: true
  name: list-case-claims
- description: File a Proof of Claim for a bankruptcy case
  hints:
    openWorld: false
    readOnly: false
  name: file-proof-of-claim
- description: Create a bankruptcy monitoring alert for a debtor or entity
  hints:
    openWorld: false
    readOnly: false
  name: create-bankruptcy-monitor
- description: List all active bankruptcy monitoring alerts
  hints:
    openWorld: false
    readOnly: true
  name: list-monitors
---
