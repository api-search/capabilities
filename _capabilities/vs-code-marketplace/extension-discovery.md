---
categories: []
consumed_apis:
- vscode-gallery
description: Extension discovery and management workflow for the VS Code Marketplace Gallery API. Enables searching for extensions by keyword, tag, or category; retrieving publisher details; and downloading VSIX packages. Used by developer tooling, IDE integrations, and automation workflows that manage VS Code extension ecosystems.
layout: capability
name: VS Code Extension Discovery
operations:
- description: Search extensions by keyword, tag, publisher, or extension ID.
  method: POST
  name: search-extensions
  path: /v1/extensions
- description: Retrieve details about a specific extension publisher.
  method: GET
  name: get-publisher
  path: /v1/publishers/{publisherName}
personas: []
provider_name: VS Code Marketplace
provider_slug: vs-code-marketplace
search_terms:
- get information about a vs code extension publisher, including their extensions.
- search extensions by keyword, tag, publisher, or extension id.
- get details for a specific vs code extension by its publisher.name id (e.g., ms-python.python).
- search extensions
- search extensions by category
- search vs code marketplace for extensions with a specific tag.
- developer tools
- search vs code marketplace for extensions by keyword, tag, or category. returns extension metadata, install counts, and ratings.
- search extensions by tag
- search trending extensions
- ide
- visual studio code
- search and discover vs code extensions.
- get publisher
- search vs code marketplace for extensions in a specific category (e.g., debuggers, themes, linters).
- extensions
- find the most popular and trending vs code extensions sorted by install count.
- get extension by id
- microsoft
- marketplace
- get publisher information.
- retrieve details about a specific extension publisher.
slug: extension-discovery
source_filename: extension-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"VS Code Extension Discovery\"\n  description: >-\n    Extension discovery and management workflow for the VS Code Marketplace Gallery API.\n    Enables searching for extensions by keyword, tag, or category; retrieving publisher\n    details; and downloading VSIX packages. Used by developer tooling, IDE integrations,\n    and automation workflows that manage VS Code extension ecosystems.\n  tags:\n    - Developer Tools\n    - Extensions\n    - IDE\n    - Marketplace\n    - Microsoft\n    - Visual Studio Code\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys: {}\n\ncapability:\n  consumes:\n    - import: vscode-gallery\n      location: ./shared/gallery-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vscode-extension-discovery-api\n      description: \"Unified REST API for VS Code extension discovery and publisher information.\"\n      resources:\n        -\
  \ path: /v1/extensions\n          name: extensions\n          description: \"Search and discover VS Code extensions.\"\n          operations:\n            - method: POST\n              name: search-extensions\n              description: \"Search extensions by keyword, tag, publisher, or extension ID.\"\n              call: \"vscode-gallery.query-extensions\"\n              with:\n                filters: \"rest.filters\"\n                flags: \"rest.flags\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/publishers/{publisherName}\n          name: publisher\n          description: \"Get publisher information.\"\n          operations:\n            - method: GET\n              name: get-publisher\n              description: \"Retrieve details about a specific extension publisher.\"\n              call: \"vscode-gallery.get-publisher\"\n              with:\n                publisherName: \"rest.publisherName\"\n  \
  \            outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vscode-extension-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted VS Code extension discovery and analysis.\"\n      tools:\n        - name: search-extensions\n          description: \"Search VS Code Marketplace for extensions by keyword, tag, or category. Returns extension metadata, install counts, and ratings.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"vscode-gallery.query-extensions\"\n          with:\n            filters: \"tools.filters\"\n            flags: \"tools.flags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-extensions-by-tag\n          description: \"Search VS Code Marketplace for extensions with a specific tag.\"\n          hints:\n  \
  \          readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"vscode-gallery.query-extensions\"\n          with:\n            filters:\n              - criteria:\n                  - filterType: 1\n                    value: \"tools.tag\"\n                pageNumber: 1\n                pageSize: 20\n                sortBy: 4\n                sortOrder: 2\n            flags: 16863\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-extensions-by-category\n          description: \"Search VS Code Marketplace for extensions in a specific category (e.g., Debuggers, Themes, Linters).\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"vscode-gallery.query-extensions\"\n          with:\n            filters:\n              - criteria:\n                  - filterType: 5\n                    value: \"tools.category\"\n   \
  \             pageNumber: 1\n                pageSize: 20\n                sortBy: 4\n                sortOrder: 2\n            flags: 16863\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-extension-by-id\n          description: \"Get details for a specific VS Code extension by its publisher.name ID (e.g., ms-python.python).\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vscode-gallery.query-extensions\"\n          with:\n            filters:\n              - criteria:\n                  - filterType: 7\n                    value: \"tools.extensionId\"\n                pageNumber: 1\n                pageSize: 1\n            flags: 16863\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-publisher\n          description: \"Get information about a VS Code extension publisher, including their extensions.\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"vscode-gallery.get-publisher\"\n          with:\n            publisherName: \"tools.publisherName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-trending-extensions\n          description: \"Find the most popular and trending VS Code extensions sorted by install count.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"vscode-gallery.query-extensions\"\n          with:\n            filters:\n              - criteria:\n                  - filterType: 8\n                    value: \"Microsoft.VisualStudio.Code\"\n                pageNumber: 1\n                pageSize: 25\n                sortBy: 12\n                sortOrder: 2\n            flags: 16863\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vs-code-marketplace/refs/heads/main/capabilities/extension-discovery.yaml
tags:
- Developer Tools
- Extensions
- IDE
- Marketplace
- Microsoft
- Visual Studio Code
tools:
- description: Search VS Code Marketplace for extensions by keyword, tag, or category. Returns extension metadata, install counts, and ratings.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-extensions
- description: Search VS Code Marketplace for extensions with a specific tag.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-extensions-by-tag
- description: Search VS Code Marketplace for extensions in a specific category (e.g., Debuggers, Themes, Linters).
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-extensions-by-category
- description: Get details for a specific VS Code extension by its publisher.name ID (e.g., ms-python.python).
  hints:
    idempotent: true
    readOnly: true
  name: get-extension-by-id
- description: Get information about a VS Code extension publisher, including their extensions.
  hints:
    idempotent: true
    readOnly: true
  name: get-publisher
- description: Find the most popular and trending VS Code extensions sorted by install count.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-trending-extensions
---
