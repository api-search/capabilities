---
categories: []
consumed_apis: []
description: The Application Discovery API extends beyond the capabilities of the Simple Edge Discovery API by not only locating the nearest Edge Cloud Zone but also directly linking to the application endpoints within those Edge Cloud Zones.
layout: capability
name: Global System for Mobile Communications GSMA Camara Project Application Endpoint Discovery API
operations:
- description: Global System for Mobile Communications Returns the Endpoint of the closest App Instance to user device identified in the request.
  method: GET
  name: getappendpoints
  path: /app-endpoints
personas: []
provider_name: Global System for Mobile Communications
provider_slug: global-system-for-mobile-communications
search_terms:
- global
- telco
- getappendpoints
- networking
- telecommunications
- system
- networks
- global system for mobile communications returns the endpoint of the closest app instance to user device identified in the request.
- api
- standards
- for
- mobile
- communications
slug: global-system-for-mobile-communications-capability
source_filename: global-system-for-mobile-communications-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Global System for Mobile Communications GSMA Camara Project Application Endpoint Discovery API\n  description: The Application Discovery API extends beyond the capabilities of the Simple Edge Discovery API by not only\n    locating the nearest Edge Cloud Zone but also directly linking to the application endpoints within those Edge Cloud Zones.\n  tags:\n  - Global\n  - System\n  - For\n  - Mobile\n  - Communications\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: global-system-for-mobile-communications\n    baseUri: https://localhost:443/application-endpoint-discovery/vwip\n    description: Global System for Mobile Communications GSMA Camara Project Application Endpoint Discovery API HTTP API.\n    resources:\n    - name: app-endpoints\n      path: /app-endpoints\n      operations:\n      - name: getappendpoints\n        method: GET\n        description: Global System\
  \ for Mobile Communications Returns the Endpoint of the closest App Instance to user device\n          identified in the request.\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          required: true\n          description: Filter the Edge Cloud Zones according to the parameter value. For this API the only supported value\n            is `closest`.\n        - name: IPv4-Address\n          in: header\n          type: string\n          description: The public IPv4 address allocated to the device.\n        - name: IPv6-Address\n          in: header\n          type: string\n          description: The public IPv6 address allocated to the device.\n        - name: Network-Access-Identifier\n          in: header\n          type: string\n          description: 3GPP network access identifier for the subscription being used by the device.\n        - name: Phone-Number\n          in: header\n          type: string\n          required: true\n     \
  \     description: MSISDN in E.164 format (starting with country code) of the mobile subscription being used by the device.\n            Optionally prefixed with '+'.\n        - name: AppId\n          in: header\n          type: string\n          required: true\n          description: A globally unique identifier associated with the application. OP generates this identifier when the\n            application is submitted over NBI.\n        - name: X-Correlator\n          in: header\n          type: string\n          description: When the API Consumer includes the \"X-Correlator\" header in the request, the API provider must include\n            it in the response with the same value that was used in t\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: global-system-for-mobile-communications-rest\n    description: REST adapter for Global System for Mobile\
  \ Communications GSMA Camara Project Application Endpoint Discovery\n      API.\n    resources:\n    - path: /app-endpoints\n      name: getappendpoints\n      operations:\n      - method: GET\n        name: getappendpoints\n        description: Global System for Mobile Communications Returns the Endpoint of the closest App Instance to user device\n          identified in the request.\n        call: global-system-for-mobile-communications.getappendpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: global-system-for-mobile-communications-mcp\n    transport: http\n    description: MCP adapter for Global System for Mobile Communications GSMA Camara Project Application Endpoint Discovery\n      API for AI agent use.\n    tools:\n    - name: getappendpoints\n      description: Global System for Mobile Communications Returns the Endpoint of the closest App Instance to user device\n        identified in the request.\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: global-system-for-mobile-communications.getappendpoints\n      with:\n        filter: tools.filter\n      inputParameters:\n      - name: filter\n        type: string\n        description: Filter the Edge Cloud Zones according to the parameter value. For this API the only supported value is\n          `closest`.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/global-system-for-mobile-communications/refs/heads/main/capabilities/global-system-for-mobile-communications-capability.yaml
tags:
- Global
- System
- For
- Mobile
- Communications
- API
tools:
- description: Global System for Mobile Communications Returns the Endpoint of the closest App Instance to user device identified in the request.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getappendpoints
---
