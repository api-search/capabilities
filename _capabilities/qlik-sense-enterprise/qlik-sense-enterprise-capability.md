---
categories: []
consumed_apis: []
description: REST API for retrieving product information about a Qlik Sense site, including system details, installed components, external URLs, and third-party software information. The About Service API provides read-only endpoints that return JSON-formatted information about the Qlik Sense deployment.
layout: capability
name: Qlik Sense Enterprise Qlik Sense About Service API
operations:
- description: Qlik Sense Enterprise Get system information
  method: GET
  name: getsysteminfo
  path: /systeminfo
- description: Qlik Sense Enterprise Get installed components
  method: GET
  name: getcomponents
  path: /components
- description: Qlik Sense Enterprise Get external URLs
  method: GET
  name: getexternalurls
  path: /externalurls
- description: Qlik Sense Enterprise Get third-party software information
  method: GET
  name: getthirdpartyinfo
  path: /thirdparty
personas: []
provider_name: Qlik Sense Enterprise
provider_slug: qlik-sense-enterprise
search_terms:
- analytics
- qlik sense enterprise get installed components
- getcomponents
- rest api
- qlik
- getthirdpartyinfo
- qlik sense enterprise get third-party software information
- data visualization
- enterprise
- business intelligence
- qlik sense enterprise get system information
- api
- sense
- getsysteminfo
- qlik sense enterprise get external urls
- getexternalurls
slug: qlik-sense-enterprise-capability
source_filename: qlik-sense-enterprise-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Qlik Sense Enterprise Qlik Sense About Service API\n  description: REST API for retrieving product information about a Qlik Sense site, including system details, installed components,\n    external URLs, and third-party software information. The About Service API provides read-only endpoints that return JSON-formatted\n    information about the Qlik Sense deployment.\n  tags:\n  - Qlik\n  - Sense\n  - Enterprise\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: qlik-sense-enterprise\n    baseUri: https://localhost/api/about/v1\n    description: Qlik Sense Enterprise Qlik Sense About Service API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Qlik-Xrfkey\n      value: '{{QLIK_SENSE_ENTERPRISE_TOKEN}}'\n    resources:\n    - name: systeminfo\n      path: /systeminfo\n      operations:\n      - name: getsysteminfo\n        method: GET\n\
  \        description: Qlik Sense Enterprise Get system information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: components\n      path: /components\n      operations:\n      - name: getcomponents\n        method: GET\n        description: Qlik Sense Enterprise Get installed components\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: externalurls\n      path: /externalurls\n      operations:\n      - name: getexternalurls\n        method: GET\n        description: Qlik Sense Enterprise Get external URLs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: thirdparty\n      path: /thirdparty\n      operations:\n      - name: getthirdpartyinfo\n        method: GET\n        description: Qlik Sense Enterprise Get third-party\
  \ software information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: qlik-sense-enterprise-rest\n    description: REST adapter for Qlik Sense Enterprise Qlik Sense About Service API.\n    resources:\n    - path: /systeminfo\n      name: getsysteminfo\n      operations:\n      - method: GET\n        name: getsysteminfo\n        description: Qlik Sense Enterprise Get system information\n        call: qlik-sense-enterprise.getsysteminfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /components\n      name: getcomponents\n      operations:\n      - method: GET\n        name: getcomponents\n        description: Qlik Sense Enterprise Get installed components\n        call: qlik-sense-enterprise.getcomponents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /externalurls\n   \
  \   name: getexternalurls\n      operations:\n      - method: GET\n        name: getexternalurls\n        description: Qlik Sense Enterprise Get external URLs\n        call: qlik-sense-enterprise.getexternalurls\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /thirdparty\n      name: getthirdpartyinfo\n      operations:\n      - method: GET\n        name: getthirdpartyinfo\n        description: Qlik Sense Enterprise Get third-party software information\n        call: qlik-sense-enterprise.getthirdpartyinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: qlik-sense-enterprise-mcp\n    transport: http\n    description: MCP adapter for Qlik Sense Enterprise Qlik Sense About Service API for AI agent use.\n    tools:\n    - name: getsysteminfo\n      description: Qlik Sense Enterprise Get system information\n      hints:\n        readOnly: true\n        destructive: false\n      \
  \  idempotent: true\n      call: qlik-sense-enterprise.getsysteminfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcomponents\n      description: Qlik Sense Enterprise Get installed components\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense-enterprise.getcomponents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getexternalurls\n      description: Qlik Sense Enterprise Get external URLs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense-enterprise.getexternalurls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getthirdpartyinfo\n      description: Qlik Sense Enterprise Get third-party software information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense-enterprise.getthirdpartyinfo\n   \
  \   outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    QLIK_SENSE_ENTERPRISE_TOKEN: QLIK_SENSE_ENTERPRISE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/qlik-sense-enterprise/refs/heads/main/capabilities/qlik-sense-enterprise-capability.yaml
tags:
- Qlik
- Sense
- Enterprise
- API
tools:
- description: Qlik Sense Enterprise Get system information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsysteminfo
- description: Qlik Sense Enterprise Get installed components
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcomponents
- description: Qlik Sense Enterprise Get external URLs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexternalurls
- description: Qlik Sense Enterprise Get third-party software information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getthirdpartyinfo
---
