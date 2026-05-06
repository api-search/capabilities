---
categories: []
consumed_apis: []
description: Cloud EDA license management capability using the Synopsys Cloud OpenLink API. Enables semiconductor vendors and customers to query product entitlements and generate license files for EDA tools, supporting both synchronous and asynchronous license delivery.
layout: capability
name: Synopsys EDA License Management
operations:
- description: Query available EDA tool entitlements for a customer.
  method: POST
  name: get-entitlements
  path: /v1/entitlements
- description: Generate a license file for a customer entitlement.
  method: POST
  name: generate-license
  path: /v1/licenses
- description: Download a previously generated license file.
  method: GET
  name: download-license
  path: /v1/licenses/{licenseId}
personas: []
provider_name: Synopsys
provider_slug: synopsys
search_terms:
- generate a license file for a specific eda tool entitlement.
- software security
- semiconductor design
- download license
- synopsys
- get entitlements
- license management
- eda tools
- eda product license entitlements.
- query available eda tool entitlements for a customer.
- generate license
- query eda tool license entitlements for a synopsys cloud customer.
- license file generation and download.
- download a previously generated eda tool license file.
- static analysis
- cloud platform
- download a previously generated license file.
- download generated license files.
- generate a license file for a customer entitlement.
- application security testing
- software composition analysis
slug: eda-license-management
source_filename: eda-license-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Synopsys EDA License Management\n  description: Cloud EDA license management capability using the Synopsys Cloud OpenLink API. Enables semiconductor vendors\n    and customers to query product entitlements and generate license files for EDA tools, supporting both synchronous and\n    asynchronous license delivery.\n  tags:\n  - Synopsys\n  - EDA Tools\n  - License Management\n  - Semiconductor Design\n  - Cloud Platform\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SYNOPSYS_OPENLINK_API_KEY: SYNOPSYS_OPENLINK_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: synopsys-openlink\n    baseUri: https://api.synopsys.com/openlink/v1\n    description: Synopsys Cloud OpenLink vendor entitlement and license API.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{SYNOPSYS_OPENLINK_API_KEY}}'\n      placement: header\n    resources:\n    - name: entitlements\n\
  \      path: /entitlements\n      description: Vendor entitlement queries.\n      operations:\n      - name: get-entitlements\n        method: POST\n        description: Retrieves available licenses for a specific customer.\n        inputParameters:\n        - name: customerId\n          in: body\n          type: string\n          required: true\n        - name: productId\n          in: body\n          type: string\n          required: true\n        - name: requestId\n          in: body\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customerId}}'\n            productId: '{{tools.productId}}'\n            requestId: '{{tools.requestId}}'\n    - name: licenses\n      path: /licenses\n      description: License file generation.\n      operations:\n      - name: generate-license\n\
  \        method: POST\n        description: Generates a license file for a customer entitlement.\n        inputParameters:\n        - name: entitlementId\n          in: body\n          type: string\n          required: true\n        - name: customerId\n          in: body\n          type: string\n          required: true\n        - name: hostId\n          in: body\n          type: string\n          required: false\n        - name: quantity\n          in: body\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            entitlementId: '{{tools.entitlementId}}'\n            customerId: '{{tools.customerId}}'\n            hostId: '{{tools.hostId}}'\n            quantity: '{{tools.quantity}}'\n      - name: download-license\n        method: GET\n        description: Downloads a previously generated license file.\n\
  \        inputParameters:\n        - name: licenseId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: synopsys-eda-license-api\n    description: Unified REST API for Synopsys EDA tool license management.\n    resources:\n    - path: /v1/entitlements\n      name: entitlements\n      description: EDA product license entitlements.\n      operations:\n      - method: POST\n        name: get-entitlements\n        description: Query available EDA tool entitlements for a customer.\n        call: synopsys-openlink.get-entitlements\n        with:\n          customerId: rest.customerId\n          productId: rest.productId\n          requestId: rest.requestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/licenses\n      name: licenses\n      description:\
  \ License file generation and download.\n      operations:\n      - method: POST\n        name: generate-license\n        description: Generate a license file for a customer entitlement.\n        call: synopsys-openlink.generate-license\n        with:\n          entitlementId: rest.entitlementId\n          customerId: rest.customerId\n          hostId: rest.hostId\n          quantity: rest.quantity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/licenses/{licenseId}\n      name: license-download\n      description: Download generated license files.\n      operations:\n      - method: GET\n        name: download-license\n        description: Download a previously generated license file.\n        call: synopsys-openlink.download-license\n        with:\n          licenseId: rest.licenseId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: synopsys-eda-license-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted EDA license management using Synopsys Cloud OpenLink.\n    tools:\n    - name: get-entitlements\n      description: Query EDA tool license entitlements for a Synopsys Cloud customer.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: synopsys-openlink.get-entitlements\n      with:\n        customerId: tools.customerId\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-license\n      description: Generate a license file for a specific EDA tool entitlement.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: synopsys-openlink.generate-license\n      with:\n        entitlementId: tools.entitlementId\n        customerId: tools.customerId\n        hostId: tools.hostId\n        quantity: tools.quantity\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: download-license\n      description: Download a previously generated EDA tool license file.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: synopsys-openlink.download-license\n      with:\n        licenseId: tools.licenseId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/synopsys/refs/heads/main/capabilities/eda-license-management.yaml
tags:
- Synopsys
- EDA Tools
- License Management
- Semiconductor Design
- Cloud Platform
tools:
- description: Query EDA tool license entitlements for a Synopsys Cloud customer.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: get-entitlements
- description: Generate a license file for a specific EDA tool entitlement.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-license
- description: Download a previously generated EDA tool license file.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: download-license
---
