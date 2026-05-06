---
categories: []
consumed_apis: []
description: Advanced search API using Artifactory Query Language (AQL), a SQL-like query language for finding and filtering artifacts, builds, and entries in JFrog Artifactory. AQL provides powerful querying capabilities including domain queries, field filtering, sorting, limiting, and inclusion of related entities.
layout: capability
name: JFrog Artifactory Query Language (AQL) API
operations:
- description: JFrog Artifactory Execute AQL Query
  method: POST
  name: executeaqlquery
  path: /api/search/aql
personas: []
provider_name: JFrog Artifactory
provider_slug: artifactory
search_terms:
- docker registry
- maven
- ci/cd
- executeaqlquery
- package management
- api
- jfrog artifactory execute aql query
- artifactory
- repository
- artifacts
- devops
slug: artifactory-capability
source_filename: artifactory-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: JFrog Artifactory Query Language (AQL) API\n  description: Advanced search API using Artifactory Query Language (AQL), a SQL-like query language for finding and filtering\n    artifacts, builds, and entries in JFrog Artifactory. AQL provides powerful querying capabilities including domain queries,\n    field filtering, sorting, limiting, and inclusion of related entities.\n  tags:\n  - Artifactory\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: artifactory\n    baseUri: https://myserver.jfrog.io/artifactory\n    description: JFrog Artifactory Query Language (AQL) API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ARTIFACTORY_TOKEN}}'\n    resources:\n    - name: api-search-aql\n      path: /api/search/aql\n      operations:\n      - name: executeaqlquery\n        method: POST\n        description: JFrog Artifactory Execute AQL Query\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: artifactory-rest\n    description: REST adapter for JFrog Artifactory Query Language (AQL) API.\n    resources:\n    - path: /api/search/aql\n      name: executeaqlquery\n      operations:\n      - method: POST\n        name: executeaqlquery\n        description: JFrog Artifactory Execute AQL Query\n        call: artifactory.executeaqlquery\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: artifactory-mcp\n    transport: http\n    description: MCP adapter for JFrog Artifactory Query Language (AQL) API for AI agent use.\n    tools:\n    - name: executeaqlquery\n      description: JFrog Artifactory Execute AQL Query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: artifactory.executeaqlquery\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ARTIFACTORY_TOKEN: ARTIFACTORY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/artifactory/refs/heads/main/capabilities/artifactory-capability.yaml
tags:
- Artifactory
- API
tools:
- description: JFrog Artifactory Execute AQL Query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executeaqlquery
---
