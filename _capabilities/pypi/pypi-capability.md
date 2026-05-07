---
categories: []
consumed_apis: []
description: The PyPI Index API implements the PEP 503 (HTML) and PEP 691 (JSON) simple repository standards for discovering and downloading Python packages. It provides a machine-readable index of all registered projects and their available distribution files. The API is available in both HTML and JSON formats, with JSON recommended for new integrations. This is the primary API that package installers like pip use to resolve and download dependencies from the Python Package Index.
layout: capability
name: PyPI Index API
operations:
- description: List all projects
  method: GET
  name: listprojects
  path: /simple/
- description: Get project distribution files
  method: GET
  name: getprojectfiles
  path: /simple/{project}/
personas: []
provider_name: PyPI
provider_slug: pypi
search_terms:
- list all projects
- open source
- python
- getprojectfiles
- listprojects
- pypi
- packages
- get project distribution files
- api
- package management
- developer tools
slug: pypi-capability
source_filename: pypi-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PyPI Index API\n  description: The PyPI Index API implements the PEP 503 (HTML) and PEP 691 (JSON) simple repository standards for discovering\n    and downloading Python packages. It provides a machine-readable index of all registered projects and their available distribution\n    files. The API is available in both HTML and JSON formats, with JSON recommended for new integrations. This is the primary\n    API that package installers like pip use to resolve and download dependencies from the Python Package Index.\n  tags:\n  - Pypi\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pypi\n    baseUri: https://pypi.org\n    description: PyPI Index API HTTP API.\n    resources:\n    - name: simple\n      path: /simple/\n      operations:\n      - name: listprojects\n        method: GET\n        description: List all projects\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: simple-project\n      path: /simple/{project}/\n      operations:\n      - name: getprojectfiles\n        method: GET\n        description: Get project distribution files\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pypi-rest\n    description: REST adapter for PyPI Index API.\n    resources:\n    - path: /simple/\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: List all projects\n        call: pypi.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /simple/{project}/\n      name: getprojectfiles\n      operations:\n      - method: GET\n        name: getprojectfiles\n        description: Get project distribution files\n        call: pypi.getprojectfiles\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pypi-mcp\n    transport: http\n    description: MCP adapter for PyPI Index API for AI agent use.\n    tools:\n    - name: listprojects\n      description: List all projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pypi.listprojects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprojectfiles\n      description: Get project distribution files\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pypi.getprojectfiles\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pypi/refs/heads/main/capabilities/pypi-capability.yaml
tags:
- Pypi
- API
tools:
- description: List all projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Get project distribution files
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectfiles
---
