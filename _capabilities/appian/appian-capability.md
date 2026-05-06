---
categories: []
consumed_apis: []
description: The Application Package Details API uses the UUID of an application to retrieve data about any in-flight packages for that application. It can be used to link packages to change management systems or obtain identifiers for packages that can then be used with the Deployment REST API to perform exports and deployments. Packages are returned in order of last modified timestamp, with the most recently modified package appearing first, up to a maximum of 100 packages.
layout: capability
name: Appian Application Package Details API
operations:
- description: Appian Get application package details
  method: GET
  name: getapplicationpackages
  path: /applications/{applicationUuid}/packages
personas: []
provider_name: Appian
provider_slug: appian
search_terms:
- getapplicationpackages
- low-code
- appian
- business process management
- process automation
- appian get application package details
- api
- enterprise software
- bpm
- workflow
- rpa
- automation
slug: appian-capability
source_filename: appian-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Appian Application Package Details API\n  description: The Application Package Details API uses the UUID of an application to retrieve data about any in-flight packages\n    for that application. It can be used to link packages to change management systems or obtain identifiers for packages\n    that can then be used with the Deployment REST API to perform exports and deployments. Packages are returned in order\n    of last modified timestamp, with the most recently modified package appearing first, up to a maximum of 100 packages.\n  tags:\n  - Appian\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: appian\n    baseUri: https://mysite.appiancloud.com/suite/deployment-management/v2\n    description: Appian Application Package Details API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: appian-api-key\n      value: '{{APPIAN_TOKEN}}'\n\
  \    resources:\n    - name: applications-applicationuuid-packages\n      path: /applications/{applicationUuid}/packages\n      operations:\n      - name: getapplicationpackages\n        method: GET\n        description: Appian Get application package details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: appian-rest\n    description: REST adapter for Appian Application Package Details API.\n    resources:\n    - path: /applications/{applicationUuid}/packages\n      name: getapplicationpackages\n      operations:\n      - method: GET\n        name: getapplicationpackages\n        description: Appian Get application package details\n        call: appian.getapplicationpackages\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: appian-mcp\n    transport: http\n    description: MCP adapter\
  \ for Appian Application Package Details API for AI agent use.\n    tools:\n    - name: getapplicationpackages\n      description: Appian Get application package details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: appian.getapplicationpackages\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    APPIAN_TOKEN: APPIAN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/appian/refs/heads/main/capabilities/appian-capability.yaml
tags:
- Appian
- API
tools:
- description: Appian Get application package details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplicationpackages
---
