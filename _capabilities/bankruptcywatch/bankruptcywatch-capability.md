---
categories: []
consumed_apis: []
description: The BankruptcyWatch PACER API provides a comprehensive suite of services for interacting with United States Bankruptcy Court data via PACER (Public Access to Court Electronic Records). The API enables creditors, lenders, and legal teams to search for bankruptcy cases, retrieve case details, file documents, monitor case activity, and automate bankruptcy workflows including Proof of Claim filing and loan restructuring.
layout: capability
name: BankruptcyWatch PACER API
operations:
- description: Search Bankruptcy Cases
  method: GET
  name: searchcases
  path: /cases/search
- description: Get Case Details
  method: GET
  name: getcase
  path: /cases/{caseId}
- description: Get Case Docket
  method: GET
  name: getcasedocket
  path: /cases/{caseId}/docket
- description: List Claims
  method: GET
  name: listclaims
  path: /cases/{caseId}/claims
- description: File Proof of Claim
  method: POST
  name: fileproofofclaim
  path: /cases/{caseId}/claims
- description: Create Monitor
  method: POST
  name: createmonitor
  path: /monitors
- description: List Monitors
  method: GET
  name: listmonitors
  path: /monitors
- description: Get Monitor
  method: GET
  name: getmonitor
  path: /monitors/{monitorId}
- description: Delete Monitor
  method: DELETE
  name: deletemonitor
  path: /monitors/{monitorId}
personas: []
provider_name: BankruptcyWatch
provider_slug: bankruptcywatch
search_terms:
- automated alerts for bankruptcy filings
- court data
- getcasedocket
- legal
- Bankruptcy Attorney
- listclaims
- lending
- bankruptcywatch
- file proof of claim
- compliance
- delete monitor
- getmonitor
- business or individual owed money by a bankruptcy filer
- list claims
- bankruptcy case research, claims management, and automated monitoring
- create monitor
- pacer
- api
- getcase
- bankruptcy
- searchcases
- get case details
- us bankruptcy court cases and proceedings
- deletemonitor
- Creditor
- attorney managing creditor representation in bankruptcy proceedings
- fileproofofclaim
- lender monitoring borrowers for bankruptcy filings
- createmonitor
- search bankruptcy cases
- Loan Officer
- get monitor
- list monitors
- listmonitors
- get case docket
slug: bankruptcywatch-capability
source_filename: bankruptcywatch-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: BankruptcyWatch PACER API\n  description: The BankruptcyWatch PACER API provides a comprehensive suite of services for interacting with United States\n    Bankruptcy Court data via PACER (Public Access to Court Electronic Records). The API enables creditors, lenders, and legal\n    teams to search for bankruptcy cases, retrieve case details, file documents, monitor case activity, and automate bankruptcy\n    workflows including Proof of Claim filing and loan restructuring.\n  tags:\n  - Bankruptcywatch\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bankruptcywatch\n    baseUri: https://api.bankruptcywatch.com/v1\n    description: BankruptcyWatch PACER API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{BANKRUPTCYWATCH_TOKEN}}'\n    resources:\n    - name: cases-search\n      path: /cases/search\n      operations:\n\
  \      - name: searchcases\n        method: GET\n        description: Search Bankruptcy Cases\n        inputParameters:\n        - name: debtorName\n          in: query\n          type: string\n          description: Debtor name to search for\n        - name: caseNumber\n          in: query\n          type: string\n          description: PACER case number\n        - name: district\n          in: query\n          type: string\n          description: Bankruptcy court district code\n        - name: chapter\n          in: query\n          type: string\n          description: Bankruptcy chapter (7, 11, 13, etc.)\n        - name: dateFiledFrom\n          in: query\n          type: string\n          description: Filter cases filed on or after this date (ISO 8601)\n        - name: dateFiledTo\n          in: query\n          type: string\n          description: Filter cases filed on or before this date (ISO 8601)\n        - name: status\n          in: query\n          type: string\n          description:\
  \ Case status filter (open, closed, discharged)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-caseid\n      path: /cases/{caseId}\n      operations:\n      - name: getcase\n        method: GET\n        description: Get Case Details\n        inputParameters:\n        - name: caseId\n          in: path\n          type: string\n          required: true\n          description: BankruptcyWatch case identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-caseid-docket\n      path: /cases/{caseId}/docket\n      operations:\n      - name: getcasedocket\n        method: GET\n        description: Get Case Docket\n        inputParameters:\n        - name: caseId\n          in: path\n          type: string\n          required: true\n          description: BankruptcyWatch case identifier\n        - name:\
  \ dateFrom\n          in: query\n          type: string\n          description: Filter docket entries from this date\n        - name: dateTo\n          in: query\n          type: string\n          description: Filter docket entries to this date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-caseid-claims\n      path: /cases/{caseId}/claims\n      operations:\n      - name: listclaims\n        method: GET\n        description: List Claims\n        inputParameters:\n        - name: caseId\n          in: path\n          type: string\n          required: true\n          description: BankruptcyWatch case identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fileproofofclaim\n        method: POST\n        description: File Proof of Claim\n        inputParameters:\n        - name: caseId\n        \
  \  in: path\n          type: string\n          required: true\n          description: BankruptcyWatch case identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitors\n      path: /monitors\n      operations:\n      - name: createmonitor\n        method: POST\n        description: Create Monitor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listmonitors\n        method: GET\n        description: List Monitors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitors-monitorid\n      path: /monitors/{monitorId}\n      operations:\n      - name: getmonitor\n        method: GET\n        description: Get Monitor\n        inputParameters:\n        - name: monitorId\n          in: path\n          type: string\n\
  \          required: true\n          description: Monitor identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemonitor\n        method: DELETE\n        description: Delete Monitor\n        inputParameters:\n        - name: monitorId\n          in: path\n          type: string\n          required: true\n          description: Monitor identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bankruptcywatch-rest\n    description: REST adapter for BankruptcyWatch PACER API.\n    resources:\n    - path: /cases/search\n      name: searchcases\n      operations:\n      - method: GET\n        name: searchcases\n        description: Search Bankruptcy Cases\n        call: bankruptcywatch.searchcases\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /cases/{caseId}\n      name: getcase\n      operations:\n      - method: GET\n        name: getcase\n        description: Get Case Details\n        call: bankruptcywatch.getcase\n        with:\n          caseId: rest.caseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cases/{caseId}/docket\n      name: getcasedocket\n      operations:\n      - method: GET\n        name: getcasedocket\n        description: Get Case Docket\n        call: bankruptcywatch.getcasedocket\n        with:\n          caseId: rest.caseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cases/{caseId}/claims\n      name: listclaims\n      operations:\n      - method: GET\n        name: listclaims\n        description: List Claims\n        call: bankruptcywatch.listclaims\n        with:\n          caseId: rest.caseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /cases/{caseId}/claims\n      name: fileproofofclaim\n      operations:\n      - method: POST\n        name: fileproofofclaim\n        description: File Proof of Claim\n        call: bankruptcywatch.fileproofofclaim\n        with:\n          caseId: rest.caseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /monitors\n      name: createmonitor\n      operations:\n      - method: POST\n        name: createmonitor\n        description: Create Monitor\n        call: bankruptcywatch.createmonitor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /monitors\n      name: listmonitors\n      operations:\n      - method: GET\n        name: listmonitors\n        description: List Monitors\n        call: bankruptcywatch.listmonitors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /monitors/{monitorId}\n      name: getmonitor\n      operations:\n      - method: GET\n        name: getmonitor\n\
  \        description: Get Monitor\n        call: bankruptcywatch.getmonitor\n        with:\n          monitorId: rest.monitorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /monitors/{monitorId}\n      name: deletemonitor\n      operations:\n      - method: DELETE\n        name: deletemonitor\n        description: Delete Monitor\n        call: bankruptcywatch.deletemonitor\n        with:\n          monitorId: rest.monitorId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bankruptcywatch-mcp\n    transport: http\n    description: MCP adapter for BankruptcyWatch PACER API for AI agent use.\n    tools:\n    - name: searchcases\n      description: Search Bankruptcy Cases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bankruptcywatch.searchcases\n      with:\n        debtorName: tools.debtorName\n        caseNumber: tools.caseNumber\n\
  \        district: tools.district\n        chapter: tools.chapter\n        dateFiledFrom: tools.dateFiledFrom\n        dateFiledTo: tools.dateFiledTo\n        status: tools.status\n      inputParameters:\n      - name: debtorName\n        type: string\n        description: Debtor name to search for\n      - name: caseNumber\n        type: string\n        description: PACER case number\n      - name: district\n        type: string\n        description: Bankruptcy court district code\n      - name: chapter\n        type: string\n        description: Bankruptcy chapter (7, 11, 13, etc.)\n      - name: dateFiledFrom\n        type: string\n        description: Filter cases filed on or after this date (ISO 8601)\n      - name: dateFiledTo\n        type: string\n        description: Filter cases filed on or before this date (ISO 8601)\n      - name: status\n        type: string\n        description: Case status filter (open, closed, discharged)\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getcase\n      description: Get Case Details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bankruptcywatch.getcase\n      with:\n        caseId: tools.caseId\n      inputParameters:\n      - name: caseId\n        type: string\n        description: BankruptcyWatch case identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcasedocket\n      description: Get Case Docket\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bankruptcywatch.getcasedocket\n      with:\n        caseId: tools.caseId\n        dateFrom: tools.dateFrom\n        dateTo: tools.dateTo\n      inputParameters:\n      - name: caseId\n        type: string\n        description: BankruptcyWatch case identifier\n        required: true\n      - name: dateFrom\n        type: string\n        description: Filter docket entries\
  \ from this date\n      - name: dateTo\n        type: string\n        description: Filter docket entries to this date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclaims\n      description: List Claims\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bankruptcywatch.listclaims\n      with:\n        caseId: tools.caseId\n      inputParameters:\n      - name: caseId\n        type: string\n        description: BankruptcyWatch case identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fileproofofclaim\n      description: File Proof of Claim\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bankruptcywatch.fileproofofclaim\n      with:\n        caseId: tools.caseId\n      inputParameters:\n      - name: caseId\n        type: string\n        description: BankruptcyWatch case identifier\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmonitor\n      description: Create Monitor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bankruptcywatch.createmonitor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmonitors\n      description: List Monitors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bankruptcywatch.listmonitors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmonitor\n      description: Get Monitor\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bankruptcywatch.getmonitor\n      with:\n        monitorId: tools.monitorId\n      inputParameters:\n      - name: monitorId\n        type: string\n        description: Monitor identifier\n        required: true\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemonitor\n      description: Delete Monitor\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: bankruptcywatch.deletemonitor\n      with:\n        monitorId: tools.monitorId\n      inputParameters:\n      - name: monitorId\n        type: string\n        description: Monitor identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BANKRUPTCYWATCH_TOKEN: BANKRUPTCYWATCH_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bankruptcywatch/refs/heads/main/capabilities/bankruptcywatch-capability.yaml
tags:
- Bankruptcywatch
- API
tools:
- description: Search Bankruptcy Cases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcases
- description: Get Case Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcase
- description: Get Case Docket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcasedocket
- description: List Claims
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclaims
- description: File Proof of Claim
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fileproofofclaim
- description: Create Monitor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmonitor
- description: List Monitors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmonitors
- description: Get Monitor
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmonitor
- description: Delete Monitor
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemonitor
---
