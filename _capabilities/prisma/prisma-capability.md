---
categories: []
consumed_apis: []
description: API for Prisma Accelerate, a fully managed global connection pool and caching layer for existing databases. Accelerate intercepts Prisma Client queries via a proxy protocol, applies query-level cache policies with configurable TTL and stale-while-revalidate strategies, and provides tag-based cache invalidation. The proxy uses the prisma:// connection protocol to route queries through Accelerate's global edge network.
layout: capability
name: Prisma Accelerate API
operations:
- description: Prisma Execute a proxied database query
  method: POST
  name: executequery
  path: /{apiVersion}/{engineHash}/graphql
- description: Prisma Invalidate cache entries by tags
  method: POST
  name: invalidatecachebytags
  path: /invalidate
- description: Prisma Invalidate all cache entries
  method: POST
  name: invalidateallcache
  path: /invalidate-all
- description: Prisma Check Accelerate service health
  method: GET
  name: gethealthstatus
  path: /health
personas: []
provider_name: Prisma
provider_slug: prisma
search_terms:
- prisma execute a proxied database query
- prisma check accelerate service health
- gethealthstatus
- invalidatecachebytags
- executequery
- invalidateallcache
- prisma invalidate cache entries by tags
- prisma
- api
- prisma invalidate all cache entries
slug: prisma-capability
source_filename: prisma-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Prisma Accelerate API\n  description: API for Prisma Accelerate, a fully managed global connection pool and caching layer for existing databases.\n    Accelerate intercepts Prisma Client queries via a proxy protocol, applies query-level cache policies with configurable\n    TTL and stale-while-revalidate strategies, and provides tag-based cache invalidation. The proxy uses the prisma:// connection\n    protocol to route queries through Accelerate's global edge network.\n  tags:\n  - Prisma\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: prisma\n    baseUri: https://accelerate.prisma-data.net\n    description: Prisma Accelerate API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{PRISMA_TOKEN}}'\n    resources:\n    - name: apiversion-enginehash-graphql\n      path: /{apiVersion}/{engineHash}/graphql\n  \
  \    operations:\n      - name: executequery\n        method: POST\n        description: Prisma Execute a proxied database query\n        inputParameters:\n        - name: apiVersion\n          in: path\n          type: string\n          required: true\n          description: Prisma engine API version\n        - name: engineHash\n          in: path\n          type: string\n          required: true\n          description: Prisma engine version hash for protocol compatibility\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invalidate\n      path: /invalidate\n      operations:\n      - name: invalidatecachebytags\n        method: POST\n        description: Prisma Invalidate cache entries by tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invalidate-all\n      path: /invalidate-all\n      operations:\n\
  \      - name: invalidateallcache\n        method: POST\n        description: Prisma Invalidate all cache entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /health\n      operations:\n      - name: gethealthstatus\n        method: GET\n        description: Prisma Check Accelerate service health\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: prisma-rest\n    description: REST adapter for Prisma Accelerate API.\n    resources:\n    - path: /{apiVersion}/{engineHash}/graphql\n      name: executequery\n      operations:\n      - method: POST\n        name: executequery\n        description: Prisma Execute a proxied database query\n        call: prisma.executequery\n        with:\n          apiVersion: rest.apiVersion\n          engineHash:\
  \ rest.engineHash\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /invalidate\n      name: invalidatecachebytags\n      operations:\n      - method: POST\n        name: invalidatecachebytags\n        description: Prisma Invalidate cache entries by tags\n        call: prisma.invalidatecachebytags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /invalidate-all\n      name: invalidateallcache\n      operations:\n      - method: POST\n        name: invalidateallcache\n        description: Prisma Invalidate all cache entries\n        call: prisma.invalidateallcache\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /health\n      name: gethealthstatus\n      operations:\n      - method: GET\n        name: gethealthstatus\n        description: Prisma Check Accelerate service health\n        call: prisma.gethealthstatus\n        outputParameters:\n        - type: object\n        \
  \  mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: prisma-mcp\n    transport: http\n    description: MCP adapter for Prisma Accelerate API for AI agent use.\n    tools:\n    - name: executequery\n      description: Prisma Execute a proxied database query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: prisma.executequery\n      with:\n        apiVersion: tools.apiVersion\n        engineHash: tools.engineHash\n      inputParameters:\n      - name: apiVersion\n        type: string\n        description: Prisma engine API version\n        required: true\n      - name: engineHash\n        type: string\n        description: Prisma engine version hash for protocol compatibility\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: invalidatecachebytags\n      description: Prisma Invalidate cache entries by tags\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: prisma.invalidatecachebytags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: invalidateallcache\n      description: Prisma Invalidate all cache entries\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: prisma.invalidateallcache\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethealthstatus\n      description: Prisma Check Accelerate service health\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prisma.gethealthstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PRISMA_TOKEN: PRISMA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/prisma/refs/heads/main/capabilities/prisma-capability.yaml
tags:
- Prisma
- API
tools:
- description: Prisma Execute a proxied database query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executequery
- description: Prisma Invalidate cache entries by tags
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invalidatecachebytags
- description: Prisma Invalidate all cache entries
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invalidateallcache
- description: Prisma Check Accelerate service health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealthstatus
---
