---
categories: []
consumed_apis:
- ballerina-central
description: Ballerina Central package registry workflow for discovering, searching, and retrieving Ballerina language packages. Serves Ballerina developers and integration engineers building on the Ballerina language ecosystem.
layout: capability
name: Ballerina Package Registry
operations:
- description: Search for Ballerina packages
  method: GET
  name: search-packages
  path: /v1/packages
- description: Get package details
  method: GET
  name: get-package
  path: /v1/packages/{org}/{package}
personas: []
provider_name: Ballerina
provider_slug: ballerina
search_terms:
- discovery and retrieval of ballerina language packages
- developer building integration services using the ballerina language
- get details about a specific version of a ballerina package
- integrations
- open source
- package discovery and retrieval from ballerina central
- Integration Engineer
- programming language
- get ballerina package
- get ballerina package version
- get details about a specific ballerina package including versions and documentation
- search for ballerina packages in the central registry by name, keyword, or organization
- Ballerina Developer
- engineer building enterprise integrations using ballerina language packages
- orchestrations
- search packages
- ballerina
- package registry
- integration
- get package details
- package details
- get package
- search ballerina packages
- search for ballerina packages
- package discovery and search
slug: package-registry
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Ballerina Package Registry\"\n  description: >-\n    Ballerina Central package registry workflow for discovering, searching, and retrieving\n    Ballerina language packages. Serves Ballerina developers and integration engineers building\n    on the Ballerina language ecosystem.\n  tags:\n    - Ballerina\n    - Package Registry\n    - Integration\n    - Open Source\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BALLERINA_TOKEN: BALLERINA_TOKEN\n\ncapability:\n  consumes:\n    - import: ballerina-central\n      location: ./shared/central-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ballerina-registry-api\n      description: \"Unified REST API for Ballerina package registry.\"\n      resources:\n        - path: /v1/packages\n          name: packages\n          description: Package discovery and search\n          operations:\n            - method:\
  \ GET\n              name: search-packages\n              description: Search for Ballerina packages\n              call: \"ballerina-central.search-packages\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/packages/{org}/{package}\n          name: package\n          description: Package details\n          operations:\n            - method: GET\n              name: get-package\n              description: Get package details\n              call: \"ballerina-central.get-package\"\n              with:\n                org: \"rest.org\"\n                package: \"rest.package\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: ballerina-registry-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Ballerina package discovery.\"\n      tools:\n\
  \        - name: search-ballerina-packages\n          description: Search for Ballerina packages in the Central registry by name, keyword, or organization\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ballerina-central.search-packages\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-ballerina-package\n          description: Get details about a specific Ballerina package including versions and documentation\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ballerina-central.get-package\"\n          with:\n            org: \"tools.org\"\n            package: \"tools.package\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-ballerina-package-version\n          description: Get details about a specific version of a Ballerina package\n\
  \          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ballerina-central.get-package-version\"\n          with:\n            org: \"tools.org\"\n            package: \"tools.package\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ballerina/refs/heads/main/capabilities/package-registry.yaml
tags:
- Ballerina
- Package Registry
- Integration
- Open Source
tools:
- description: Search for Ballerina packages in the Central registry by name, keyword, or organization
  hints:
    openWorld: true
    readOnly: true
  name: search-ballerina-packages
- description: Get details about a specific Ballerina package including versions and documentation
  hints:
    openWorld: true
    readOnly: true
  name: get-ballerina-package
- description: Get details about a specific version of a Ballerina package
  hints:
    openWorld: true
    readOnly: true
  name: get-ballerina-package-version
---
