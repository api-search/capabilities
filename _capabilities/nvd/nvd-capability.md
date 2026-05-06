---
categories: []
consumed_apis: []
description: 'The NVD CVE API provides programmatic access to CVE (Common Vulnerabilities and Exposures) records including CVSS severity scores, affected product lists, CWE classifications, and reference links. Without an API key: 5 requests per 30 seconds; with key: 50 requests per 30 seconds.'
layout: capability
name: NVD CVE API
operations:
- description: Get CVE records
  method: GET
  name: getcves
  path: /cves/2.0
- description: Get CVE change history
  method: GET
  name: getcvechangehistory
  path: /cvehistory/2.0
- description: Get CPE (Common Platform Enumeration) records
  method: GET
  name: getcpes
  path: /cpes/2.0
- description: Get CPE match criteria
  method: GET
  name: getcpematch
  path: /cpematch/2.0
- description: Get NVD data sources
  method: GET
  name: getsources
  path: /source/2.0
personas: []
provider_name: NVD
provider_slug: nvd
search_terms:
- get cpe match criteria
- get cve records
- cve
- getcvechangehistory
- vulnerability
- getcves
- api
- getcpes
- getcpematch
- getsources
- security
- cvss
- nvd
- cpe
- get cve change history
- get nvd data sources
- get cpe (common platform enumeration) records
slug: nvd-capability
source_filename: nvd-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NVD CVE API\n  description: 'The NVD CVE API provides programmatic access to CVE (Common Vulnerabilities and Exposures) records including\n    CVSS severity scores, affected product lists, CWE classifications, and reference links. Without an API key: 5 requests\n    per 30 seconds; with key: 50 requests per 30 seconds.'\n  tags:\n  - Nvd\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nvd\n    baseUri: https://services.nvd.nist.gov/rest/json\n    description: NVD CVE API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: apiKey\n      value: '{{NVD_TOKEN}}'\n    resources:\n    - name: cves-2-0\n      path: /cves/2.0\n      operations:\n      - name: getcves\n        method: GET\n        description: Get CVE records\n        inputParameters:\n        - name: cveId\n          in: query\n          type: string\n          description: Specific\
  \ CVE ID (e.g., CVE-2021-44228)\n        - name: keywordSearch\n          in: query\n          type: string\n          description: Free text search across CVE description\n        - name: keywordExactMatch\n          in: query\n          type: boolean\n          description: Require exact keyword match when true\n        - name: cvssV3Severity\n          in: query\n          type: string\n          description: Filter by CVSS v3.x base severity\n        - name: cvssV2Severity\n          in: query\n          type: string\n          description: Filter by CVSS v2.0 base severity\n        - name: cvssV3Metrics\n          in: query\n          type: string\n          description: Filter by CVSS v3 vector string\n        - name: cweId\n          in: query\n          type: string\n          description: CWE weakness ID (e.g., CWE-79)\n        - name: cpeName\n          in: query\n          type: string\n          description: CPE 2.3 formatted string to find CVEs affecting a specific product\n\
  \        - name: isVulnerable\n          in: query\n          type: boolean\n          description: When true, only return CVEs where the CPE match is vulnerable (must use cpeName)\n        - name: virtualMatchString\n          in: query\n          type: string\n          description: CPE match string with wildcards\n        - name: pubStartDate\n          in: query\n          type: string\n          description: CVE publication start date (ISO 8601, max 120-day range)\n        - name: pubEndDate\n          in: query\n          type: string\n        - name: lastModStartDate\n          in: query\n          type: string\n          description: Last modification start date\n        - name: lastModEndDate\n          in: query\n          type: string\n        - name: sourceIdentifier\n          in: query\n          type: string\n          description: CVE source organization identifier\n        - name: hasKev\n          in: query\n          type: boolean\n          description: When true, only\
  \ return CVEs in CISA's Known Exploited Vulnerabilities catalog\n        - name: hasCertAlerts\n          in: query\n          type: boolean\n        - name: hasCertNotes\n          in: query\n          type: boolean\n        - name: hasOval\n          in: query\n          type: boolean\n        - name: noRejected\n          in: query\n          type: boolean\n          description: Exclude CVEs with REJECTED status\n        - name: resultsPerPage\n          in: query\n          type: integer\n          description: Number of results per page (max 2000)\n        - name: startIndex\n          in: query\n          type: integer\n          description: Zero-based start index for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cvehistory-2-0\n      path: /cvehistory/2.0\n      operations:\n      - name: getcvechangehistory\n        method: GET\n        description: Get CVE change history\n\
  \        inputParameters:\n        - name: cveId\n          in: query\n          type: string\n        - name: changeStartDate\n          in: query\n          type: string\n          required: true\n        - name: changeEndDate\n          in: query\n          type: string\n          required: true\n        - name: eventName\n          in: query\n          type: string\n        - name: resultsPerPage\n          in: query\n          type: integer\n        - name: startIndex\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cpes-2-0\n      path: /cpes/2.0\n      operations:\n      - name: getcpes\n        method: GET\n        description: Get CPE (Common Platform Enumeration) records\n        inputParameters:\n        - name: cpeNameId\n          in: query\n          type: string\n          description: CPE UUID identifier\n        - name: cpeMatchString\n\
  \          in: query\n          type: string\n          description: CPE 2.3 match string (wildcards supported)\n        - name: keywordSearch\n          in: query\n          type: string\n        - name: keywordExactMatch\n          in: query\n          type: boolean\n        - name: lastModStartDate\n          in: query\n          type: string\n        - name: lastModEndDate\n          in: query\n          type: string\n        - name: matchCriteriaId\n          in: query\n          type: string\n        - name: resultsPerPage\n          in: query\n          type: integer\n        - name: startIndex\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cpematch-2-0\n      path: /cpematch/2.0\n      operations:\n      - name: getcpematch\n        method: GET\n        description: Get CPE match criteria\n        inputParameters:\n        - name: cveId\n  \
  \        in: query\n          type: string\n        - name: matchCriteriaId\n          in: query\n          type: string\n        - name: lastModStartDate\n          in: query\n          type: string\n        - name: lastModEndDate\n          in: query\n          type: string\n        - name: resultsPerPage\n          in: query\n          type: integer\n        - name: startIndex\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: source-2-0\n      path: /source/2.0\n      operations:\n      - name: getsources\n        method: GET\n        description: Get NVD data sources\n        inputParameters:\n        - name: sourceIdentifier\n          in: query\n          type: string\n        - name: lastModStartDate\n          in: query\n          type: string\n        - name: lastModEndDate\n          in: query\n          type: string\n        - name: resultsPerPage\n\
  \          in: query\n          type: integer\n        - name: startIndex\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nvd-rest\n    description: REST adapter for NVD CVE API.\n    resources:\n    - path: /cves/2.0\n      name: getcves\n      operations:\n      - method: GET\n        name: getcves\n        description: Get CVE records\n        call: nvd.getcves\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cvehistory/2.0\n      name: getcvechangehistory\n      operations:\n      - method: GET\n        name: getcvechangehistory\n        description: Get CVE change history\n        call: nvd.getcvechangehistory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cpes/2.0\n      name: getcpes\n      operations:\n      - method:\
  \ GET\n        name: getcpes\n        description: Get CPE (Common Platform Enumeration) records\n        call: nvd.getcpes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cpematch/2.0\n      name: getcpematch\n      operations:\n      - method: GET\n        name: getcpematch\n        description: Get CPE match criteria\n        call: nvd.getcpematch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /source/2.0\n      name: getsources\n      operations:\n      - method: GET\n        name: getsources\n        description: Get NVD data sources\n        call: nvd.getsources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nvd-mcp\n    transport: http\n    description: MCP adapter for NVD CVE API for AI agent use.\n    tools:\n    - name: getcves\n      description: Get CVE records\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: nvd.getcves\n      with:\n        cveId: tools.cveId\n        keywordSearch: tools.keywordSearch\n        keywordExactMatch: tools.keywordExactMatch\n        cvssV3Severity: tools.cvssV3Severity\n        cvssV2Severity: tools.cvssV2Severity\n        cvssV3Metrics: tools.cvssV3Metrics\n        cweId: tools.cweId\n        cpeName: tools.cpeName\n        isVulnerable: tools.isVulnerable\n        virtualMatchString: tools.virtualMatchString\n        pubStartDate: tools.pubStartDate\n        pubEndDate: tools.pubEndDate\n        lastModStartDate: tools.lastModStartDate\n        lastModEndDate: tools.lastModEndDate\n        sourceIdentifier: tools.sourceIdentifier\n        hasKev: tools.hasKev\n        hasCertAlerts: tools.hasCertAlerts\n        hasCertNotes: tools.hasCertNotes\n        hasOval: tools.hasOval\n        noRejected: tools.noRejected\n        resultsPerPage: tools.resultsPerPage\n        startIndex: tools.startIndex\n      inputParameters:\n\
  \      - name: cveId\n        type: string\n        description: Specific CVE ID (e.g., CVE-2021-44228)\n      - name: keywordSearch\n        type: string\n        description: Free text search across CVE description\n      - name: keywordExactMatch\n        type: boolean\n        description: Require exact keyword match when true\n      - name: cvssV3Severity\n        type: string\n        description: Filter by CVSS v3.x base severity\n      - name: cvssV2Severity\n        type: string\n        description: Filter by CVSS v2.0 base severity\n      - name: cvssV3Metrics\n        type: string\n        description: Filter by CVSS v3 vector string\n      - name: cweId\n        type: string\n        description: CWE weakness ID (e.g., CWE-79)\n      - name: cpeName\n        type: string\n        description: CPE 2.3 formatted string to find CVEs affecting a specific product\n      - name: isVulnerable\n        type: boolean\n        description: When true, only return CVEs where the CPE match\
  \ is vulnerable (must use cpeName)\n      - name: virtualMatchString\n        type: string\n        description: CPE match string with wildcards\n      - name: pubStartDate\n        type: string\n        description: CVE publication start date (ISO 8601, max 120-day range)\n      - name: pubEndDate\n        type: string\n        description: pubEndDate\n      - name: lastModStartDate\n        type: string\n        description: Last modification start date\n      - name: lastModEndDate\n        type: string\n        description: lastModEndDate\n      - name: sourceIdentifier\n        type: string\n        description: CVE source organization identifier\n      - name: hasKev\n        type: boolean\n        description: When true, only return CVEs in CISA's Known Exploited Vulnerabilities catalog\n      - name: hasCertAlerts\n        type: boolean\n        description: hasCertAlerts\n      - name: hasCertNotes\n        type: boolean\n        description: hasCertNotes\n      - name: hasOval\n\
  \        type: boolean\n        description: hasOval\n      - name: noRejected\n        type: boolean\n        description: Exclude CVEs with REJECTED status\n      - name: resultsPerPage\n        type: integer\n        description: Number of results per page (max 2000)\n      - name: startIndex\n        type: integer\n        description: Zero-based start index for pagination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcvechangehistory\n      description: Get CVE change history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nvd.getcvechangehistory\n      with:\n        cveId: tools.cveId\n        changeStartDate: tools.changeStartDate\n        changeEndDate: tools.changeEndDate\n        eventName: tools.eventName\n        resultsPerPage: tools.resultsPerPage\n        startIndex: tools.startIndex\n      inputParameters:\n      - name: cveId\n        type: string\n        description: cveId\n\
  \      - name: changeStartDate\n        type: string\n        description: changeStartDate\n        required: true\n      - name: changeEndDate\n        type: string\n        description: changeEndDate\n        required: true\n      - name: eventName\n        type: string\n        description: eventName\n      - name: resultsPerPage\n        type: integer\n        description: resultsPerPage\n      - name: startIndex\n        type: integer\n        description: startIndex\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcpes\n      description: Get CPE (Common Platform Enumeration) records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nvd.getcpes\n      with:\n        cpeNameId: tools.cpeNameId\n        cpeMatchString: tools.cpeMatchString\n        keywordSearch: tools.keywordSearch\n        keywordExactMatch: tools.keywordExactMatch\n        lastModStartDate: tools.lastModStartDate\n        lastModEndDate:\
  \ tools.lastModEndDate\n        matchCriteriaId: tools.matchCriteriaId\n        resultsPerPage: tools.resultsPerPage\n        startIndex: tools.startIndex\n      inputParameters:\n      - name: cpeNameId\n        type: string\n        description: CPE UUID identifier\n      - name: cpeMatchString\n        type: string\n        description: CPE 2.3 match string (wildcards supported)\n      - name: keywordSearch\n        type: string\n        description: keywordSearch\n      - name: keywordExactMatch\n        type: boolean\n        description: keywordExactMatch\n      - name: lastModStartDate\n        type: string\n        description: lastModStartDate\n      - name: lastModEndDate\n        type: string\n        description: lastModEndDate\n      - name: matchCriteriaId\n        type: string\n        description: matchCriteriaId\n      - name: resultsPerPage\n        type: integer\n        description: resultsPerPage\n      - name: startIndex\n        type: integer\n        description:\
  \ startIndex\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcpematch\n      description: Get CPE match criteria\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nvd.getcpematch\n      with:\n        cveId: tools.cveId\n        matchCriteriaId: tools.matchCriteriaId\n        lastModStartDate: tools.lastModStartDate\n        lastModEndDate: tools.lastModEndDate\n        resultsPerPage: tools.resultsPerPage\n        startIndex: tools.startIndex\n      inputParameters:\n      - name: cveId\n        type: string\n        description: cveId\n      - name: matchCriteriaId\n        type: string\n        description: matchCriteriaId\n      - name: lastModStartDate\n        type: string\n        description: lastModStartDate\n      - name: lastModEndDate\n        type: string\n        description: lastModEndDate\n      - name: resultsPerPage\n        type: integer\n        description: resultsPerPage\n \
  \     - name: startIndex\n        type: integer\n        description: startIndex\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsources\n      description: Get NVD data sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nvd.getsources\n      with:\n        sourceIdentifier: tools.sourceIdentifier\n        lastModStartDate: tools.lastModStartDate\n        lastModEndDate: tools.lastModEndDate\n        resultsPerPage: tools.resultsPerPage\n        startIndex: tools.startIndex\n      inputParameters:\n      - name: sourceIdentifier\n        type: string\n        description: sourceIdentifier\n      - name: lastModStartDate\n        type: string\n        description: lastModStartDate\n      - name: lastModEndDate\n        type: string\n        description: lastModEndDate\n      - name: resultsPerPage\n        type: integer\n        description: resultsPerPage\n      - name: startIndex\n      \
  \  type: integer\n        description: startIndex\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NVD_TOKEN: NVD_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nvd/refs/heads/main/capabilities/nvd-capability.yaml
tags:
- Nvd
- API
tools:
- description: Get CVE records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcves
- description: Get CVE change history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcvechangehistory
- description: Get CPE (Common Platform Enumeration) records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcpes
- description: Get CPE match criteria
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcpematch
- description: Get NVD data sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsources
---
