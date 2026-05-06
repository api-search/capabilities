---
categories: []
consumed_apis: []
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
- Integration Engineer
- integration
- Ballerina Developer
- search for ballerina packages
- developer building integration services using the ballerina language
- search packages
- ballerina
- package registry
- programming language
- get ballerina package version
- open source
- get package details
- orchestrations
- integrations
- discovery and retrieval of ballerina language packages
- search for ballerina packages in the central registry by name, keyword, or organization
- get details about a specific ballerina package including versions and documentation
- get details about a specific version of a ballerina package
- package discovery and search
- get ballerina package
- package discovery and retrieval from ballerina central
- engineer building enterprise integrations using ballerina language packages
- search ballerina packages
- package details
- get package
slug: package-registry
source_filename: package-registry.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ballerina Package Registry\n  description: Ballerina Central package registry workflow for discovering, searching, and retrieving Ballerina language packages.\n    Serves Ballerina developers and integration engineers building on the Ballerina language ecosystem.\n  tags:\n  - Ballerina\n  - Package Registry\n  - Integration\n  - Open Source\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BALLERINA_TOKEN: BALLERINA_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: ballerina-central\n    baseUri: https://api.central.ballerina.io\n    description: Ballerina Central package registry API\n    authentication:\n      type: bearer\n      token: '{{BALLERINA_TOKEN}}'\n    resources:\n    - name: packages\n      path: /2.0/packages\n      description: Package search and discovery\n      operations:\n      - name: search-packages\n        method: GET\n        description: Search for packages\
  \ in Ballerina Central\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: page-size\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-package\n        method: GET\n        description: Get details about a specific package\n        inputParameters:\n        - name: org\n          in: path\n          type: string\n          required: true\n        - name: package\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-package-version\n        method: GET\n\
  \        description: Get a specific version of a package\n        inputParameters:\n        - name: org\n          in: path\n          type: string\n          required: true\n        - name: package\n          in: path\n          type: string\n          required: true\n        - name: version\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ballerina-registry-api\n    description: Unified REST API for Ballerina package registry.\n    resources:\n    - path: /v1/packages\n      name: packages\n      description: Package discovery and search\n      operations:\n      - method: GET\n        name: search-packages\n        description: Search for Ballerina packages\n        call: ballerina-central.search-packages\n        with:\n          q: rest.q\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /v1/packages/{org}/{package}\n      name: package\n      description: Package details\n      operations:\n      - method: GET\n        name: get-package\n        description: Get package details\n        call: ballerina-central.get-package\n        with:\n          org: rest.org\n          package: rest.package\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: ballerina-registry-mcp\n    transport: http\n    description: MCP server for AI-assisted Ballerina package discovery.\n    tools:\n    - name: search-ballerina-packages\n      description: Search for Ballerina packages in the Central registry by name, keyword, or organization\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ballerina-central.search-packages\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ballerina-package\n\
  \      description: Get details about a specific Ballerina package including versions and documentation\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ballerina-central.get-package\n      with:\n        org: tools.org\n        package: tools.package\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ballerina-package-version\n      description: Get details about a specific version of a Ballerina package\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ballerina-central.get-package-version\n      with:\n        org: tools.org\n        package: tools.package\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
