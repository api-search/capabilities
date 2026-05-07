---
categories: []
consumed_apis: []
description: Unified capability for telecom revenue operations. Combines Subex ROC APIs for revenue leakage detection, fraud case management, subscriber risk scoring, CDR reconciliation, and analytics. Used by telecom operators' revenue assurance and fraud management teams.
layout: capability
name: Subex Revenue Operations Center
operations:
- description: List revenue leakage alerts
  method: GET
  name: list-leakage-alerts
  path: /v1/leakages
- description: Get a leakage alert
  method: GET
  name: get-leakage-alert
  path: /v1/leakages/{leakageId}
- description: List fraud cases
  method: GET
  name: list-fraud-cases
  path: /v1/fraud-cases
- description: Get a fraud case
  method: GET
  name: get-fraud-case
  path: /v1/fraud-cases/{caseId}
- description: Get subscriber fraud risk score
  method: GET
  name: get-subscriber-risk-score
  path: /v1/subscribers/{msisdn}/risk-score
- description: List reconciliation runs
  method: GET
  name: list-reconciliation-runs
  path: /v1/reconciliation/runs
- description: Get analytics summary
  method: GET
  name: get-analytics-summary
  path: /v1/analytics/summary
personas: []
provider_name: Subex
provider_slug: subex
search_terms:
- list reconciliation runs
- analytics
- get a leakage alert
- list subex revenue leakage alerts with optional severity and type filters
- get details of a specific revenue leakage alert
- fraud management
- telecom
- individual leakage alert
- update leakage alert
- list telecom fraud cases with optional fraud type and status filters
- subscriber risk scoring
- get details of a specific telecom fraud case
- update the status or assignment of a revenue leakage alert
- get analytics summary
- revenue leakage alerts
- get subscriber risk score
- individual fraud case
- get a fraud case
- get leakage alert
- revenue analytics
- list leakage alerts
- get summary analytics for revenue assurance and fraud kpis
- list cdr and billing reconciliation runs
- subex
- list fraud cases
- list revenue leakage alerts
- bss/oss
- revenue assurance
- get the fraud risk score for a telecom subscriber by their msisdn
- fraud case management
- cdr reconciliation
- get subscriber fraud risk score
- get fraud case
slug: revenue-operations-center
source_filename: revenue-operations-center.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Subex Revenue Operations Center\n  description: Unified capability for telecom revenue operations. Combines Subex ROC APIs for revenue leakage detection, fraud\n    case management, subscriber risk scoring, CDR reconciliation, and analytics. Used by telecom operators' revenue assurance\n    and fraud management teams.\n  tags:\n  - Subex\n  - Telecom\n  - Revenue Assurance\n  - Fraud Management\n  - CDR Reconciliation\n  - Analytics\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SUBEX_BEARER_TOKEN: SUBEX_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: subex-roc\n    baseUri: https://api.subex.example.com/roc/v1\n    description: Subex ROC API for revenue assurance and fraud management.\n    authentication:\n      type: bearer\n      token: '{{SUBEX_BEARER_TOKEN}}'\n    resources:\n    - name: revenue-leakages\n      path: /revenue-assurance/leakages\n      description:\
  \ Revenue leakage alert management\n      operations:\n      - name: list-leakage-alerts\n        method: GET\n        description: List all revenue leakage alerts\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Filter start date (YYYY-MM-DD)\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: Filter end date (YYYY-MM-DD)\n        - name: leakageType\n          in: query\n          type: string\n          required: false\n          description: Filter by leakage type\n        - name: severity\n          in: query\n          type: string\n          required: false\n          description: Filter by severity (CRITICAL, HIGH, MEDIUM, LOW)\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status (OPEN, IN_PROGRESS, RESOLVED, CLOSED)\n        - name:\
  \ page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: revenue-leakage\n      path: /revenue-assurance/leakages/{leakageId}\n      description: Individual leakage alert\n      operations:\n      - name: get-leakage-alert\n        method: GET\n        description: Get a specific revenue leakage alert by ID\n        inputParameters:\n        - name: leakageId\n          in: path\n          type: string\n          required: true\n          description: Leakage alert ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-leakage-alert\n        method: PUT\n        description:\
  \ Update a leakage alert status or assignee\n        inputParameters:\n        - name: leakageId\n          in: path\n          type: string\n          required: true\n          description: Leakage alert ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fraud-cases\n      path: /fraud/cases\n      description: Fraud case management\n      operations:\n      - name: list-fraud-cases\n        method: GET\n        description: List all fraud cases\n        inputParameters:\n        - name: fraudType\n          in: query\n          type: string\n          required: false\n          description: Filter by fraud type (SIM_SWAP, BYPASS_FRAUD, IRSF, etc.)\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        - name: minRiskScore\n          in: query\n          type: integer\n          required: false\n        \
  \  description: Minimum risk score filter\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fraud-case\n      path: /fraud/cases/{caseId}\n      description: Individual fraud case\n      operations:\n      - name: get-fraud-case\n        method: GET\n        description: Get a specific fraud case by ID\n        inputParameters:\n        - name: caseId\n          in: path\n          type: string\n          required: true\n          description: Fraud case ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriber-risk-score\n      path: /fraud/subscribers/{msisdn}/risk-score\n      description: Subscriber risk scoring\n      operations:\n      - name: get-subscriber-risk-score\n        method: GET\n        description:\
  \ Get fraud risk score for a subscriber\n        inputParameters:\n        - name: msisdn\n          in: path\n          type: string\n          required: true\n          description: Subscriber MSISDN in international format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reconciliation-runs\n      path: /reconciliation/runs\n      description: CDR reconciliation run management\n      operations:\n      - name: list-reconciliation-runs\n        method: GET\n        description: List CDR and billing reconciliation runs\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by run status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-summary\n      path: /analytics/summary\n      description: Revenue\
  \ and risk analytics summary\n      operations:\n      - name: get-analytics-summary\n        method: GET\n        description: Get summary analytics for revenue assurance and fraud metrics\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: false\n        - name: endDate\n          in: query\n          type: string\n          required: false\n        - name: granularity\n          in: query\n          type: string\n          required: false\n          description: DAILY, WEEKLY, MONTHLY\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: subex-revenue-ops-api\n    description: Unified REST API for Subex telecom revenue operations.\n    resources:\n    - path: /v1/leakages\n      name: leakages\n      description: Revenue leakage alerts\n      operations:\n      - method: GET\n        name:\
  \ list-leakage-alerts\n        description: List revenue leakage alerts\n        call: subex-roc.list-leakage-alerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/leakages/{leakageId}\n      name: leakage\n      description: Individual leakage alert\n      operations:\n      - method: GET\n        name: get-leakage-alert\n        description: Get a leakage alert\n        call: subex-roc.get-leakage-alert\n        with:\n          leakageId: rest.leakageId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fraud-cases\n      name: fraud-cases\n      description: Fraud case management\n      operations:\n      - method: GET\n        name: list-fraud-cases\n        description: List fraud cases\n        call: subex-roc.list-fraud-cases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fraud-cases/{caseId}\n      name: fraud-case\n      description: Individual fraud\
  \ case\n      operations:\n      - method: GET\n        name: get-fraud-case\n        description: Get a fraud case\n        call: subex-roc.get-fraud-case\n        with:\n          caseId: rest.caseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscribers/{msisdn}/risk-score\n      name: subscriber-risk-score\n      description: Subscriber risk scoring\n      operations:\n      - method: GET\n        name: get-subscriber-risk-score\n        description: Get subscriber fraud risk score\n        call: subex-roc.get-subscriber-risk-score\n        with:\n          msisdn: rest.msisdn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reconciliation/runs\n      name: reconciliation-runs\n      description: CDR reconciliation\n      operations:\n      - method: GET\n        name: list-reconciliation-runs\n        description: List reconciliation runs\n        call: subex-roc.list-reconciliation-runs\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/summary\n      name: analytics\n      description: Revenue analytics\n      operations:\n      - method: GET\n        name: get-analytics-summary\n        description: Get analytics summary\n        call: subex-roc.get-analytics-summary\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: subex-revenue-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted Subex telecom revenue operations.\n    tools:\n    - name: list-leakage-alerts\n      description: List Subex revenue leakage alerts with optional severity and type filters\n      hints:\n        readOnly: true\n      call: subex-roc.list-leakage-alerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-leakage-alert\n      description: Get details of a specific revenue leakage alert\n      hints:\n        readOnly: true\n\
  \      call: subex-roc.get-leakage-alert\n      with:\n        leakageId: tools.leakageId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-leakage-alert\n      description: Update the status or assignment of a revenue leakage alert\n      hints:\n        readOnly: false\n        destructive: false\n      call: subex-roc.update-leakage-alert\n      with:\n        leakageId: tools.leakageId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-fraud-cases\n      description: List telecom fraud cases with optional fraud type and status filters\n      hints:\n        readOnly: true\n      call: subex-roc.list-fraud-cases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fraud-case\n      description: Get details of a specific telecom fraud case\n      hints:\n        readOnly: true\n      call: subex-roc.get-fraud-case\n      with:\n        caseId: tools.caseId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-subscriber-risk-score\n      description: Get the fraud risk score for a telecom subscriber by their MSISDN\n      hints:\n        readOnly: true\n      call: subex-roc.get-subscriber-risk-score\n      with:\n        msisdn: tools.msisdn\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reconciliation-runs\n      description: List CDR and billing reconciliation runs\n      hints:\n        readOnly: true\n      call: subex-roc.list-reconciliation-runs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-analytics-summary\n      description: Get summary analytics for revenue assurance and fraud KPIs\n      hints:\n        readOnly: true\n      call: subex-roc.get-analytics-summary\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/subex/refs/heads/main/capabilities/revenue-operations-center.yaml
tags:
- Subex
- Telecom
- Revenue Assurance
- Fraud Management
- CDR Reconciliation
- Analytics
tools:
- description: List Subex revenue leakage alerts with optional severity and type filters
  hints:
    readOnly: true
  name: list-leakage-alerts
- description: Get details of a specific revenue leakage alert
  hints:
    readOnly: true
  name: get-leakage-alert
- description: Update the status or assignment of a revenue leakage alert
  hints:
    destructive: false
    readOnly: false
  name: update-leakage-alert
- description: List telecom fraud cases with optional fraud type and status filters
  hints:
    readOnly: true
  name: list-fraud-cases
- description: Get details of a specific telecom fraud case
  hints:
    readOnly: true
  name: get-fraud-case
- description: Get the fraud risk score for a telecom subscriber by their MSISDN
  hints:
    readOnly: true
  name: get-subscriber-risk-score
- description: List CDR and billing reconciliation runs
  hints:
    readOnly: true
  name: list-reconciliation-runs
- description: Get summary analytics for revenue assurance and fraud KPIs
  hints:
    readOnly: true
  name: get-analytics-summary
---
