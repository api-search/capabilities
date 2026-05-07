---
categories: []
consumed_apis: []
description: The NuGet Catalog API is an append-only resource that records the full history of all package events on nuget.org, including packages being added, modified, listed, unlisted, deleted, deprecated, and having vulnerability status updated. It provides a chronologically ordered log of every change to the package source, enabling consumers to build and maintain their own local copy of the entire set of packages available on nuget.org. The catalog is indexed by time and uses a hierarchical structure of index, pages, and leaves. Not all package sources implement the catalog resource.
layout: capability
name: NuGet Catalog API
operations:
- description: Get the catalog index
  method: GET
  name: getcatalogindex
  path: /index.json
- description: Get a catalog page
  method: GET
  name: getcatalogpage
  path: /{pageName}.json
- description: Get a catalog leaf
  method: GET
  name: getcatalogleaf
  path: /data/{timestamp}/{packageId}.{version}.json
personas: []
provider_name: NuGet
provider_slug: nuget
search_terms:
- get the catalog index
- get a catalog page
- dependencies
- registry
- getcatalogpage
- getcatalogindex
- software distribution
- packages
- nuget
- getcatalogleaf
- api
- package management
- get a catalog leaf
- .net
slug: nuget-capability
source_filename: nuget-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NuGet Catalog API\n  description: The NuGet Catalog API is an append-only resource that records the full history of all package events on nuget.org,\n    including packages being added, modified, listed, unlisted, deleted, deprecated, and having vulnerability status updated.\n    It provides a chronologically ordered log of every change to the package source, enabling consumers to build and maintain\n    their own local copy of the entire set of packages available on nuget.org. The catalog is indexed by time and uses a hierarchical\n    structure of index, pages, and leaves. Not all package sources implement the catalog resource.\n  tags:\n  - Nuget\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nuget\n    baseUri: https://api.nuget.org/v3/catalog0\n    description: NuGet Catalog API HTTP API.\n    resources:\n    - name: index-json\n      path: /index.json\n      operations:\n\
  \      - name: getcatalogindex\n        method: GET\n        description: Get the catalog index\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pagename-json\n      path: /{pageName}.json\n      operations:\n      - name: getcatalogpage\n        method: GET\n        description: Get a catalog page\n        inputParameters:\n        - name: pageName\n          in: path\n          type: string\n          required: true\n          description: The page identifier, discovered from the catalog index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-timestamp-packageid-version-json\n      path: /data/{timestamp}/{packageId}.{version}.json\n      operations:\n      - name: getcatalogleaf\n        method: GET\n        description: Get a catalog leaf\n        inputParameters:\n        - name: timestamp\n     \
  \     in: path\n          type: string\n          required: true\n          description: The timestamp path segment, discovered from the catalog page.\n        - name: packageId\n          in: path\n          type: string\n          required: true\n          description: The lowercased package ID.\n        - name: version\n          in: path\n          type: string\n          required: true\n          description: The lowercased package version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nuget-rest\n    description: REST adapter for NuGet Catalog API.\n    resources:\n    - path: /index.json\n      name: getcatalogindex\n      operations:\n      - method: GET\n        name: getcatalogindex\n        description: Get the catalog index\n        call: nuget.getcatalogindex\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /{pageName}.json\n      name: getcatalogpage\n      operations:\n      - method: GET\n        name: getcatalogpage\n        description: Get a catalog page\n        call: nuget.getcatalogpage\n        with:\n          pageName: rest.pageName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /data/{timestamp}/{packageId}.{version}.json\n      name: getcatalogleaf\n      operations:\n      - method: GET\n        name: getcatalogleaf\n        description: Get a catalog leaf\n        call: nuget.getcatalogleaf\n        with:\n          timestamp: rest.timestamp\n          packageId: rest.packageId\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nuget-mcp\n    transport: http\n    description: MCP adapter for NuGet Catalog API for AI agent use.\n    tools:\n    - name: getcatalogindex\n      description: Get the catalog index\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nuget.getcatalogindex\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcatalogpage\n      description: Get a catalog page\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nuget.getcatalogpage\n      with:\n        pageName: tools.pageName\n      inputParameters:\n      - name: pageName\n        type: string\n        description: The page identifier, discovered from the catalog index.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcatalogleaf\n      description: Get a catalog leaf\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nuget.getcatalogleaf\n      with:\n        timestamp: tools.timestamp\n        packageId: tools.packageId\n        version: tools.version\n      inputParameters:\n   \
  \   - name: timestamp\n        type: string\n        description: The timestamp path segment, discovered from the catalog page.\n        required: true\n      - name: packageId\n        type: string\n        description: The lowercased package ID.\n        required: true\n      - name: version\n        type: string\n        description: The lowercased package version.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nuget/refs/heads/main/capabilities/nuget-capability.yaml
tags:
- Nuget
- API
tools:
- description: Get the catalog index
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcatalogindex
- description: Get a catalog page
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcatalogpage
- description: Get a catalog leaf
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcatalogleaf
---
