---
categories: []
consumed_apis: []
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
- search vs code marketplace for extensions by keyword, tag, or category. returns extension metadata, install counts, and ratings.
- marketplace
- visual studio code
- developer tools
- get information about a vs code extension publisher, including their extensions.
- search trending extensions
- search extensions by keyword, tag, publisher, or extension id.
- ide
- get details for a specific vs code extension by its publisher.name id (e.g., ms-python.python).
- search extensions by category
- get publisher information.
- get extension by id
- search vs code marketplace for extensions in a specific category (e.g., debuggers, themes, linters).
- search extensions
- search vs code marketplace for extensions with a specific tag.
- extensions
- search extensions by tag
- find the most popular and trending vs code extensions sorted by install count.
- microsoft
- search and discover vs code extensions.
- retrieve details about a specific extension publisher.
- get publisher
slug: extension-discovery
source_filename: extension-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: VS Code Extension Discovery\n  description: Extension discovery and management workflow for the VS Code Marketplace Gallery API. Enables searching for\n    extensions by keyword, tag, or category; retrieving publisher details; and downloading VSIX packages. Used by developer\n    tooling, IDE integrations, and automation workflows that manage VS Code extension ecosystems.\n  tags:\n  - Developer Tools\n  - Extensions\n  - IDE\n  - Marketplace\n  - Microsoft\n  - Visual Studio Code\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys: {}\ncapability:\n  consumes:\n  - type: http\n    namespace: vscode-gallery\n    baseUri: https://marketplace.visualstudio.com/_apis/public/gallery\n    description: VS Code Marketplace Gallery API for extension discovery and download.\n    resources:\n    - name: extension-query\n      path: /extensionquery\n      description: Query and search extensions in the Marketplace.\n\
  \      operations:\n      - name: query-extensions\n        method: POST\n        description: Search and filter VS Code extensions by keyword, tag, category, or extension ID.\n        inputParameters:\n        - name: filters\n          in: body\n          type: array\n          required: true\n          description: Array of filter criteria.\n        - name: flags\n          in: body\n          type: integer\n          required: false\n          description: Response detail bitmask (16863 = all attributes).\n        - name: assetTypes\n          in: body\n          type: array\n          required: false\n          description: Specific asset types to include.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extension-download\n      path: /publishers/{publisherName}/vsextensions/{extensionName}/{version}/vspackage\n      description: Download extension VSIX packages.\n      operations:\n      -\
  \ name: download-extension\n        method: GET\n        description: Download the VSIX package for a specific extension version.\n        inputParameters:\n        - name: publisherName\n          in: path\n          type: string\n          required: true\n          description: Publisher name (e.g., ms-python).\n        - name: extensionName\n          in: path\n          type: string\n          required: true\n          description: Extension name (e.g., python).\n        - name: version\n          in: path\n          type: string\n          required: true\n          description: Version string or 'latest'.\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: publisher\n      path: /publishers/{publisherName}\n      description: Retrieve publisher information.\n      operations:\n      - name: get-publisher\n        method: GET\n        description: Get details about a specific Marketplace publisher.\n\
  \        inputParameters:\n        - name: publisherName\n          in: path\n          type: string\n          required: true\n          description: Publisher unique name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vscode-extension-discovery-api\n    description: Unified REST API for VS Code extension discovery and publisher information.\n    resources:\n    - path: /v1/extensions\n      name: extensions\n      description: Search and discover VS Code extensions.\n      operations:\n      - method: POST\n        name: search-extensions\n        description: Search extensions by keyword, tag, publisher, or extension ID.\n        call: vscode-gallery.query-extensions\n        with:\n          filters: rest.filters\n          flags: rest.flags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/publishers/{publisherName}\n\
  \      name: publisher\n      description: Get publisher information.\n      operations:\n      - method: GET\n        name: get-publisher\n        description: Retrieve details about a specific extension publisher.\n        call: vscode-gallery.get-publisher\n        with:\n          publisherName: rest.publisherName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vscode-extension-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted VS Code extension discovery and analysis.\n    tools:\n    - name: search-extensions\n      description: Search VS Code Marketplace for extensions by keyword, tag, or category. Returns extension metadata, install\n        counts, and ratings.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: vscode-gallery.query-extensions\n      with:\n        filters: tools.filters\n        flags: tools.flags\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: search-extensions-by-tag\n      description: Search VS Code Marketplace for extensions with a specific tag.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: vscode-gallery.query-extensions\n      with:\n        filters:\n        - criteria:\n          - filterType: 1\n            value: tools.tag\n          pageNumber: 1\n          pageSize: 20\n          sortBy: 4\n          sortOrder: 2\n        flags: 16863\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-extensions-by-category\n      description: Search VS Code Marketplace for extensions in a specific category (e.g., Debuggers, Themes, Linters).\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: vscode-gallery.query-extensions\n      with:\n        filters:\n        - criteria:\n          - filterType: 5\n            value: tools.category\n\
  \          pageNumber: 1\n          pageSize: 20\n          sortBy: 4\n          sortOrder: 2\n        flags: 16863\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-extension-by-id\n      description: Get details for a specific VS Code extension by its publisher.name ID (e.g., ms-python.python).\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vscode-gallery.query-extensions\n      with:\n        filters:\n        - criteria:\n          - filterType: 7\n            value: tools.extensionId\n          pageNumber: 1\n          pageSize: 1\n        flags: 16863\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-publisher\n      description: Get information about a VS Code extension publisher, including their extensions.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vscode-gallery.get-publisher\n      with:\n        publisherName: tools.publisherName\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: search-trending-extensions\n      description: Find the most popular and trending VS Code extensions sorted by install count.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: vscode-gallery.query-extensions\n      with:\n        filters:\n        - criteria:\n          - filterType: 8\n            value: Microsoft.VisualStudio.Code\n          pageNumber: 1\n          pageSize: 25\n          sortBy: 12\n          sortOrder: 2\n        flags: 16863\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
