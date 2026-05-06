---
categories: []
consumed_apis: []
description: Software discovery and alternatives research capability using the SaaSHub platform. Enables product research, competitive analysis, and vendor replacement discovery for SaaS procurement and IT asset management workflows.
layout: capability
name: SaaSHub Software Discovery
operations:
- description: Look up a software product on SaaSHub by name
  method: GET
  name: get-product
  path: /v1/products/{query}
- description: Get top 10 software alternatives for a product
  method: GET
  name: get-alternatives
  path: /v1/alternatives/{query}
personas: []
provider_name: SaaSHub
provider_slug: saashub
search_terms:
- get top 10 software alternatives for a product
- software product alternatives
- software discovery
- competitive analysis
- software product lookup
- get product
- get alternatives
- look up detailed information about a software product on saashub including name, tagline, categories, pricing, and website url.
- saas procurement
- software catalog
- saas
- find the top 10 software alternatives for a given product on saashub. useful for vendor replacement research, competitive analysis, and procurement decisions.
- look up a software product on saashub by name
- lookup software product
- saashub
- alternatives
- find software alternatives
slug: software-discovery
source_filename: software-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SaaSHub Software Discovery\n  description: Software discovery and alternatives research capability using the SaaSHub platform. Enables product research,\n    competitive analysis, and vendor replacement discovery for SaaS procurement and IT asset management workflows.\n  tags:\n  - SaaSHub\n  - Software Discovery\n  - Alternatives\n  - SaaS Procurement\n  - Competitive Analysis\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAASHUB_API_KEY: SAASHUB_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: saashub\n    baseUri: https://www.saashub.com/api\n    description: SaaSHub public REST API for software discovery\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{SAASHUB_API_KEY}}'\n      placement: query\n    resources:\n    - name: product\n      path: /product\n      description: Software product lookup by name\n      operations:\n      - name: get-product\n\
  \        method: GET\n        description: Get software product data by name query\n        inputParameters:\n        - name: query\n          in: path\n          type: string\n          required: true\n          description: Product name to search for (e.g., basecamp, slack, notion)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alternatives\n      path: /alternatives\n      description: Software alternatives discovery\n      operations:\n      - name: get-product-alternatives\n        method: GET\n        description: Get a product and its top 10 alternatives by name query\n        inputParameters:\n        - name: query\n          in: path\n          type: string\n          required: true\n          description: Product name to find alternatives for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  -\
  \ type: rest\n    port: 8080\n    namespace: software-discovery-api\n    description: Unified REST API for software discovery and alternatives research.\n    resources:\n    - path: /v1/products/{query}\n      name: products\n      description: Software product lookup\n      operations:\n      - method: GET\n        name: get-product\n        description: Look up a software product on SaaSHub by name\n        call: saashub.get-product\n        with:\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alternatives/{query}\n      name: alternatives\n      description: Software product alternatives\n      operations:\n      - method: GET\n        name: get-alternatives\n        description: Get top 10 software alternatives for a product\n        call: saashub.get-product-alternatives\n        with:\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port:\
  \ 9090\n    namespace: software-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted software discovery and procurement research.\n    tools:\n    - name: lookup-software-product\n      description: Look up detailed information about a software product on SaaSHub including name, tagline, categories, pricing,\n        and website URL.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: saashub.get-product\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-software-alternatives\n      description: Find the top 10 software alternatives for a given product on SaaSHub. Useful for vendor replacement research,\n        competitive analysis, and procurement decisions.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: saashub.get-product-alternatives\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/saashub/refs/heads/main/capabilities/software-discovery.yaml
tags:
- SaaSHub
- Software Discovery
- Alternatives
- SaaS Procurement
- Competitive Analysis
tools:
- description: Look up detailed information about a software product on SaaSHub including name, tagline, categories, pricing, and website URL.
  hints:
    openWorld: true
    readOnly: true
  name: lookup-software-product
- description: Find the top 10 software alternatives for a given product on SaaSHub. Useful for vendor replacement research, competitive analysis, and procurement decisions.
  hints:
    openWorld: true
    readOnly: true
  name: find-software-alternatives
---
