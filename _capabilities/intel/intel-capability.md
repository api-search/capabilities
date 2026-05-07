---
categories: []
consumed_apis: []
description: Intel oneAPI provides a unified programming model for heterogeneous computing across CPUs, GPUs, AI accelerators, and FPGAs.
layout: capability
name: Intel oneAPI
operations:
- description: Get Developer Tools
  method: GET
  name: gettools
  path: /tools
- description: Get Toolkits
  method: GET
  name: gettoolkits
  path: /toolkits
personas: []
provider_name: intel
provider_slug: intel
search_terms:
- get toolkits
- get developer tools
- gettoolkits
- gettools
- intel
- api
slug: intel-capability
source_filename: intel-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Intel oneAPI\n  description: Intel oneAPI provides a unified programming model for heterogeneous computing across CPUs, GPUs, AI accelerators,\n    and FPGAs.\n  tags:\n  - Intel\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: intel\n    baseUri: https://api-portal.intel.com\n    description: Intel oneAPI HTTP API.\n    resources:\n    - name: tools\n      path: /tools\n      operations:\n      - name: gettools\n        method: GET\n        description: Get Developer Tools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: toolkits\n      path: /toolkits\n      operations:\n      - name: gettoolkits\n        method: GET\n        description: Get Toolkits\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \  exposes:\n  - type: rest\n    port: 8080\n    namespace: intel-rest\n    description: REST adapter for Intel oneAPI.\n    resources:\n    - path: /tools\n      name: gettools\n      operations:\n      - method: GET\n        name: gettools\n        description: Get Developer Tools\n        call: intel.gettools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /toolkits\n      name: gettoolkits\n      operations:\n      - method: GET\n        name: gettoolkits\n        description: Get Toolkits\n        call: intel.gettoolkits\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: intel-mcp\n    transport: http\n    description: MCP adapter for Intel oneAPI for AI agent use.\n    tools:\n    - name: gettools\n      description: Get Developer Tools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intel.gettools\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: gettoolkits\n      description: Get Toolkits\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intel.gettoolkits\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/intel/refs/heads/main/capabilities/intel-capability.yaml
tags:
- Intel
- API
tools:
- description: Get Developer Tools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettools
- description: Get Toolkits
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettoolkits
---
