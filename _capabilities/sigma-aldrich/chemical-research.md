---
categories: []
consumed_apis:
- sigma-aldrich
description: Unified workflow capability for chemical and life science research workflows using the Sigma-Aldrich product catalog API. Enables researchers, LIMS systems, and EHS platforms to search the world's largest chemical catalog, perform structure-based lookups, retrieve safety data sheets for regulatory compliance, and check product pricing and availability. Designed for research chemists, computational chemists, EHS managers, and procurement teams working with life science materials.
layout: capability
name: Sigma-Aldrich Chemical Research
operations:
- description: Search Sigma-Aldrich product catalog by keyword, name, or formula
  method: GET
  name: search-products
  path: /v1/products/search
- description: Get product details by Sigma-Aldrich catalog number
  method: GET
  name: get-product
  path: /v1/products/{catalogNumber}
- description: Find products by CAS Registry Number
  method: GET
  name: get-product-by-cas
  path: /v1/products/cas/{casNumber}
- description: Search by chemical structure using SMILES or InChI
  method: POST
  name: search-by-structure
  path: /v1/structures/search
- description: Get GHS Safety Data Sheet for a product
  method: GET
  name: get-sds
  path: /v1/products/{catalogNumber}/sds
- description: Get product pricing and stock availability
  method: GET
  name: get-pricing
  path: /v1/products/{catalogNumber}/pricing
personas: []
provider_name: Sigma-Aldrich
provider_slug: sigma-aldrich
search_terms:
- get detailed information about a sigma-aldrich product by catalog number
- laboratory
- search for chemicals by structure using smiles or inchi notation with exact, substructure, or similarity matching
- biochemistry
- get pricing
- get product details
- product catalog search
- get product details by sigma-aldrich catalog number
- research
- product lookup by cas number
- safety data sheet retrieval
- chemical catalog
- search by chemical structure using smiles or inchi
- get sds
- cheminformatics
- search sigma-aldrich product catalog by keyword, name, or formula
- chemistry
- search chemicals
- get product by cas
- find products by cas registry number
- life science
- procurement
- product pricing and availability
- search by structure
- get product pricing
- get ghs safety data sheet for a product
- chemical structure search
- get product
- find sigma-aldrich products by cas registry number (e.g., 7732-18-5 for water)
- product lookup by catalog number
- get current pricing and stock availability for a sigma-aldrich product by country
- safety
- lims
- lookup by cas number
- get safety data sheet
- search the sigma-aldrich catalog for chemicals, reagents, and biochemicals by name, formula, or keyword
- get product pricing and stock availability
- search products
- search by chemical structure
- retrieve the ghs safety data sheet for a sigma-aldrich chemical product for regulatory compliance
slug: chemical-research
source_filename: chemical-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sigma-Aldrich Chemical Research\"\n  description: >-\n    Unified workflow capability for chemical and life science research workflows\n    using the Sigma-Aldrich product catalog API. Enables researchers, LIMS\n    systems, and EHS platforms to search the world's largest chemical catalog,\n    perform structure-based lookups, retrieve safety data sheets for regulatory\n    compliance, and check product pricing and availability. Designed for\n    research chemists, computational chemists, EHS managers, and procurement\n    teams working with life science materials.\n  tags:\n    - Life Science\n    - Chemistry\n    - Research\n    - Cheminformatics\n    - Safety\n    - LIMS\n    - Procurement\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SIGMA_ALDRICH_API_KEY: SIGMA_ALDRICH_API_KEY\n\ncapability:\n  consumes:\n    - import: sigma-aldrich\n      location: ./shared/sigma-aldrich-products.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sigma-aldrich-research-api\n      description: \"Unified REST API for Sigma-Aldrich chemical research and procurement workflows.\"\n      resources:\n        - path: /v1/products/search\n          name: product-search\n          description: \"Product catalog search\"\n          operations:\n            - method: GET\n              name: search-products\n              description: \"Search Sigma-Aldrich product catalog by keyword, name, or formula\"\n              call: \"sigma-aldrich.search-products\"\n              with:\n                q: \"rest.q\"\n                page: \"rest.page\"\n                pageSize: \"rest.pageSize\"\n                brand: \"rest.brand\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products/{catalogNumber}\n          name: product\n          description: \"Product lookup by catalog number\"\n          operations:\n\
  \            - method: GET\n              name: get-product\n              description: \"Get product details by Sigma-Aldrich catalog number\"\n              call: \"sigma-aldrich.get-product\"\n              with:\n                catalogNumber: \"rest.catalogNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products/cas/{casNumber}\n          name: product-by-cas\n          description: \"Product lookup by CAS number\"\n          operations:\n            - method: GET\n              name: get-product-by-cas\n              description: \"Find products by CAS Registry Number\"\n              call: \"sigma-aldrich.get-product-by-cas\"\n              with:\n                casNumber: \"rest.casNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/structures/search\n          name: structure-search\n          description: \"Chemical\
  \ structure search\"\n          operations:\n            - method: POST\n              name: search-by-structure\n              description: \"Search by chemical structure using SMILES or InChI\"\n              call: \"sigma-aldrich.search-by-structure\"\n              with:\n                structure: \"rest.structure\"\n                searchType: \"rest.searchType\"\n                notation: \"rest.notation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products/{catalogNumber}/sds\n          name: safety-data-sheet\n          description: \"Safety Data Sheet retrieval\"\n          operations:\n            - method: GET\n              name: get-sds\n              description: \"Get GHS Safety Data Sheet for a product\"\n              call: \"sigma-aldrich.get-product-sds\"\n              with:\n                catalogNumber: \"rest.catalogNumber\"\n                language: \"rest.language\"\n           \
  \   outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products/{catalogNumber}/pricing\n          name: pricing\n          description: \"Product pricing and availability\"\n          operations:\n            - method: GET\n              name: get-pricing\n              description: \"Get product pricing and stock availability\"\n              call: \"sigma-aldrich.get-product-pricing\"\n              with:\n                catalogNumber: \"rest.catalogNumber\"\n                country: \"rest.country\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sigma-aldrich-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted chemical research and life science procurement using Sigma-Aldrich.\"\n      tools:\n        - name: search-chemicals\n          description: \"Search the Sigma-Aldrich catalog for\
  \ chemicals, reagents, and biochemicals by name, formula, or keyword\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sigma-aldrich.search-products\"\n          with:\n            q: \"tools.q\"\n            page: \"tools.page\"\n            pageSize: \"tools.pageSize\"\n            brand: \"tools.brand\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-product-details\n          description: \"Get detailed information about a Sigma-Aldrich product by catalog number\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sigma-aldrich.get-product\"\n          with:\n            catalogNumber: \"tools.catalogNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: lookup-by-cas-number\n          description: \"Find Sigma-Aldrich products by CAS Registry Number (e.g., 7732-18-5 for\
  \ water)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sigma-aldrich.get-product-by-cas\"\n          with:\n            casNumber: \"tools.casNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-by-chemical-structure\n          description: \"Search for chemicals by structure using SMILES or InChI notation with exact, substructure, or similarity matching\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sigma-aldrich.search-by-structure\"\n          with:\n            structure: \"tools.structure\"\n            searchType: \"tools.searchType\"\n            notation: \"tools.notation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-safety-data-sheet\n          description: \"Retrieve the GHS Safety Data Sheet for a Sigma-Aldrich chemical product for regulatory\
  \ compliance\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sigma-aldrich.get-product-sds\"\n          with:\n            catalogNumber: \"tools.catalogNumber\"\n            language: \"tools.language\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-product-pricing\n          description: \"Get current pricing and stock availability for a Sigma-Aldrich product by country\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sigma-aldrich.get-product-pricing\"\n          with:\n            catalogNumber: \"tools.catalogNumber\"\n            country: \"tools.country\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sigma-aldrich/refs/heads/main/capabilities/chemical-research.yaml
tags:
- Life Science
- Chemistry
- Research
- Cheminformatics
- Safety
- LIMS
- Procurement
tools:
- description: Search the Sigma-Aldrich catalog for chemicals, reagents, and biochemicals by name, formula, or keyword
  hints:
    openWorld: true
    readOnly: true
  name: search-chemicals
- description: Get detailed information about a Sigma-Aldrich product by catalog number
  hints:
    openWorld: false
    readOnly: true
  name: get-product-details
- description: Find Sigma-Aldrich products by CAS Registry Number (e.g., 7732-18-5 for water)
  hints:
    openWorld: false
    readOnly: true
  name: lookup-by-cas-number
- description: Search for chemicals by structure using SMILES or InChI notation with exact, substructure, or similarity matching
  hints:
    openWorld: true
    readOnly: true
  name: search-by-chemical-structure
- description: Retrieve the GHS Safety Data Sheet for a Sigma-Aldrich chemical product for regulatory compliance
  hints:
    openWorld: false
    readOnly: true
  name: get-safety-data-sheet
- description: Get current pricing and stock availability for a Sigma-Aldrich product by country
  hints:
    openWorld: false
    readOnly: true
  name: get-product-pricing
---
