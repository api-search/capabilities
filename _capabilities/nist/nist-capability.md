---
categories: []
consumed_apis: []
description: The National Vulnerability Database (NVD) CVE API provides programmatic access to CVE records, CVSS metrics, weakness (CWE) data, and configuration information for security vulnerabilities.
layout: capability
name: NIST NVD CVE API
operations:
- description: Search CVE records
  method: GET
  name: getcves
  path: /cves/2.0
- description: Retrieve CVE change history
  method: GET
  name: getcvehistory
  path: /cvehistory/2.0
personas: []
provider_name: National Institute of Standards and Technology (NIST)
provider_slug: nist
search_terms:
- government
- measurements
- retrieve cve change history
- getcvehistory
- nist
- getcves
- api
- cybersecurity
- research
- scientific data
- search cve records
- standards
slug: nist-capability
source_filename: nist-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NIST NVD CVE API\n  description: The National Vulnerability Database (NVD) CVE API provides programmatic access to CVE records, CVSS metrics,\n    weakness (CWE) data, and configuration information for security vulnerabilities.\n  tags:\n  - Nist\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nist\n    baseUri: https://services.nvd.nist.gov/rest/json\n    description: NIST NVD CVE API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: apiKey\n      value: '{{NIST_TOKEN}}'\n    resources:\n    - name: cves-2-0\n      path: /cves/2.0\n      operations:\n      - name: getcves\n        method: GET\n        description: Search CVE records\n        inputParameters:\n        - name: cveId\n          in: query\n          type: string\n          description: Returns a single CVE record by its CVE identifier.\n        - name: cpeName\n         \
  \ in: query\n          type: string\n          description: Returns CVE records associated with the supplied CPE 2.3 name.\n        - name: cvssV3Severity\n          in: query\n          type: string\n          description: Filter results by CVSS v3 qualitative severity rating.\n        - name: keywordSearch\n          in: query\n          type: string\n          description: Returns CVE records where the description contains the keyword.\n        - name: pubStartDate\n          in: query\n          type: string\n          description: Filter by CVE publish start date (ISO 8601).\n        - name: pubEndDate\n          in: query\n          type: string\n          description: Filter by CVE publish end date (ISO 8601).\n        - name: lastModStartDate\n          in: query\n          type: string\n          description: Filter by last modified start date (ISO 8601).\n        - name: lastModEndDate\n          in: query\n          type: string\n          description: Filter by last modified\
  \ end date (ISO 8601).\n        - name: resultsPerPage\n          in: query\n          type: integer\n          description: Number of CVE records to return per page (max 2000).\n        - name: startIndex\n          in: query\n          type: integer\n          description: Zero-based offset into the result set.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cvehistory-2-0\n      path: /cvehistory/2.0\n      operations:\n      - name: getcvehistory\n        method: GET\n        description: Retrieve CVE change history\n        inputParameters:\n        - name: cveId\n          in: query\n          type: string\n          description: Returns the change history for a single CVE.\n        - name: changeStartDate\n          in: query\n          type: string\n          description: Filter changes that occurred on or after this date (ISO 8601).\n        - name: changeEndDate\n          in: query\n\
  \          type: string\n          description: Filter changes that occurred on or before this date (ISO 8601).\n        - name: resultsPerPage\n          in: query\n          type: integer\n          description: Number of change records to return per page (max 5000).\n        - name: startIndex\n          in: query\n          type: integer\n          description: Zero-based offset into the result set.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nist-rest\n    description: REST adapter for NIST NVD CVE API.\n    resources:\n    - path: /cves/2.0\n      name: getcves\n      operations:\n      - method: GET\n        name: getcves\n        description: Search CVE records\n        call: nist.getcves\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cvehistory/2.0\n      name: getcvehistory\n      operations:\n\
  \      - method: GET\n        name: getcvehistory\n        description: Retrieve CVE change history\n        call: nist.getcvehistory\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nist-mcp\n    transport: http\n    description: MCP adapter for NIST NVD CVE API for AI agent use.\n    tools:\n    - name: getcves\n      description: Search CVE records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nist.getcves\n      with:\n        cveId: tools.cveId\n        cpeName: tools.cpeName\n        cvssV3Severity: tools.cvssV3Severity\n        keywordSearch: tools.keywordSearch\n        pubStartDate: tools.pubStartDate\n        pubEndDate: tools.pubEndDate\n        lastModStartDate: tools.lastModStartDate\n        lastModEndDate: tools.lastModEndDate\n        resultsPerPage: tools.resultsPerPage\n        startIndex: tools.startIndex\n      inputParameters:\n      -\
  \ name: cveId\n        type: string\n        description: Returns a single CVE record by its CVE identifier.\n      - name: cpeName\n        type: string\n        description: Returns CVE records associated with the supplied CPE 2.3 name.\n      - name: cvssV3Severity\n        type: string\n        description: Filter results by CVSS v3 qualitative severity rating.\n      - name: keywordSearch\n        type: string\n        description: Returns CVE records where the description contains the keyword.\n      - name: pubStartDate\n        type: string\n        description: Filter by CVE publish start date (ISO 8601).\n      - name: pubEndDate\n        type: string\n        description: Filter by CVE publish end date (ISO 8601).\n      - name: lastModStartDate\n        type: string\n        description: Filter by last modified start date (ISO 8601).\n      - name: lastModEndDate\n        type: string\n        description: Filter by last modified end date (ISO 8601).\n      - name: resultsPerPage\n\
  \        type: integer\n        description: Number of CVE records to return per page (max 2000).\n      - name: startIndex\n        type: integer\n        description: Zero-based offset into the result set.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcvehistory\n      description: Retrieve CVE change history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nist.getcvehistory\n      with:\n        cveId: tools.cveId\n        changeStartDate: tools.changeStartDate\n        changeEndDate: tools.changeEndDate\n        resultsPerPage: tools.resultsPerPage\n        startIndex: tools.startIndex\n      inputParameters:\n      - name: cveId\n        type: string\n        description: Returns the change history for a single CVE.\n      - name: changeStartDate\n        type: string\n        description: Filter changes that occurred on or after this date (ISO 8601).\n      - name: changeEndDate\n     \
  \   type: string\n        description: Filter changes that occurred on or before this date (ISO 8601).\n      - name: resultsPerPage\n        type: integer\n        description: Number of change records to return per page (max 5000).\n      - name: startIndex\n        type: integer\n        description: Zero-based offset into the result set.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NIST_TOKEN: NIST_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nist/refs/heads/main/capabilities/nist-capability.yaml
tags:
- Nist
- API
tools:
- description: Search CVE records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcves
- description: Retrieve CVE change history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcvehistory
---
