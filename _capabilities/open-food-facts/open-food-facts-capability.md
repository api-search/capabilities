---
categories: []
consumed_apis: []
description: Open Food Facts is a collaborative, free, and open database of food products from around the world. The HTTP API provides read access to product data by barcode, full-text and faceted search, and access to Open Food Facts taxonomies.
layout: capability
name: Open Food Facts API
operations:
- description: Get a product by barcode
  method: GET
  name: getproductbybarcode
  path: /api/v2/product/{barcode}
- description: Get a product by barcode (JSON)
  method: GET
  name: getproductbybarcodejson
  path: /api/v2/product/{barcode}.json
- description: Search products
  method: GET
  name: searchproducts
  path: /api/v2/search
- description: Retrieve taxonomy entries
  method: GET
  name: gettaxonomy
  path: /api/v2/taxonomy
- description: Taxonomy autocomplete suggestions
  method: GET
  name: taxonomysuggestions
  path: /api/v3/taxonomy_suggestions
- description: Get a product (v3)
  method: GET
  name: getproductv3
  path: /api/v3/product/{barcode}
- description: Legacy suggestion endpoint
  method: GET
  name: legacysuggest
  path: /cgi/suggest.pl
personas: []
provider_name: Open Food Facts
provider_slug: open-food-facts
search_terms:
- gettaxonomy
- get a product by barcode
- taxonomysuggestions
- get a product (v3)
- api
- open
- searchproducts
- legacysuggest
- legacy suggestion endpoint
- getproductbybarcode
- taxonomy autocomplete suggestions
- facts
- search products
- retrieve taxonomy entries
- getproductv3
- getproductbybarcodejson
- get a product by barcode (json)
- food
slug: open-food-facts-capability
source_filename: open-food-facts-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Open Food Facts API\n  description: Open Food Facts is a collaborative, free, and open database of food products from around the world. The HTTP\n    API provides read access to product data by barcode, full-text and faceted search, and access to Open Food Facts taxonomies.\n  tags:\n  - Open\n  - Food\n  - Facts\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: open-food-facts\n    baseUri: https://world.openfoodfacts.org\n    description: Open Food Facts API HTTP API.\n    resources:\n    - name: api-v2-product-barcode\n      path: /api/v2/product/{barcode}\n      operations:\n      - name: getproductbybarcode\n        method: GET\n        description: Get a product by barcode\n        inputParameters:\n        - name: barcode\n          in: path\n          type: string\n          required: true\n          description: Product barcode such as an EAN-13.\n        - name:\
  \ fields\n          in: query\n          type: string\n          description: Comma-separated list of fields to return.\n        - name: lc\n          in: query\n          type: string\n          description: Language code for localized fields (e.g., en, fr).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-product-barcode-json\n      path: /api/v2/product/{barcode}.json\n      operations:\n      - name: getproductbybarcodejson\n        method: GET\n        description: Get a product by barcode (JSON)\n        inputParameters:\n        - name: barcode\n          in: path\n          type: string\n          required: true\n        - name: fields\n          in: query\n          type: string\n        - name: blame\n          in: query\n          type: integer\n          description: When 1, include modification history.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: api-v2-search\n      path: /api/v2/search\n      operations:\n      - name: searchproducts\n        method: GET\n        description: Search products\n        inputParameters:\n        - name: code\n          in: query\n          type: string\n          description: Comma-separated list of barcodes for bulk lookup.\n        - name: categories_tags_en\n          in: query\n          type: string\n        - name: brands_tags\n          in: query\n          type: string\n        - name: labels_tags\n          in: query\n          type: string\n        - name: countries_tags_en\n          in: query\n          type: string\n        - name: nutrition_grades_tags\n          in: query\n          type: string\n        - name: fields\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        - name: page_size\n          in: query\n          type: integer\n        - name:\
  \ sort_by\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-taxonomy\n      path: /api/v2/taxonomy\n      operations:\n      - name: gettaxonomy\n        method: GET\n        description: Retrieve taxonomy entries\n        inputParameters:\n        - name: tagtype\n          in: query\n          type: string\n          required: true\n        - name: tags\n          in: query\n          type: string\n          description: Comma-separated taxonomy tag identifiers.\n        - name: fields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-taxonomy-suggestions\n      path: /api/v3/taxonomy_suggestions\n      operations:\n      - name: taxonomysuggestions\n        method: GET\n        description: Taxonomy autocomplete\
  \ suggestions\n        inputParameters:\n        - name: tagtype\n          in: query\n          type: string\n          required: true\n        - name: string\n          in: query\n          type: string\n          description: Prefix to match.\n        - name: lc\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-product-barcode\n      path: /api/v3/product/{barcode}\n      operations:\n      - name: getproductv3\n        method: GET\n        description: Get a product (v3)\n        inputParameters:\n        - name: barcode\n          in: path\n          type: string\n          required: true\n        - name: fields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: cgi-suggest-pl\n      path: /cgi/suggest.pl\n      operations:\n      - name: legacysuggest\n        method: GET\n        description: Legacy suggestion endpoint\n        inputParameters:\n        - name: tagtype\n          in: query\n          type: string\n          required: true\n        - name: term\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: open-food-facts-rest\n    description: REST adapter for Open Food Facts API.\n    resources:\n    - path: /api/v2/product/{barcode}\n      name: getproductbybarcode\n      operations:\n      - method: GET\n        name: getproductbybarcode\n        description: Get a product by barcode\n        call: open-food-facts.getproductbybarcode\n        with:\n          barcode: rest.barcode\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /api/v2/product/{barcode}.json\n      name: getproductbybarcodejson\n      operations:\n      - method: GET\n        name: getproductbybarcodejson\n        description: Get a product by barcode (JSON)\n        call: open-food-facts.getproductbybarcodejson\n        with:\n          barcode: rest.barcode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/search\n      name: searchproducts\n      operations:\n      - method: GET\n        name: searchproducts\n        description: Search products\n        call: open-food-facts.searchproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/taxonomy\n      name: gettaxonomy\n      operations:\n      - method: GET\n        name: gettaxonomy\n        description: Retrieve taxonomy entries\n        call: open-food-facts.gettaxonomy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/taxonomy_suggestions\n\
  \      name: taxonomysuggestions\n      operations:\n      - method: GET\n        name: taxonomysuggestions\n        description: Taxonomy autocomplete suggestions\n        call: open-food-facts.taxonomysuggestions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/product/{barcode}\n      name: getproductv3\n      operations:\n      - method: GET\n        name: getproductv3\n        description: Get a product (v3)\n        call: open-food-facts.getproductv3\n        with:\n          barcode: rest.barcode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cgi/suggest.pl\n      name: legacysuggest\n      operations:\n      - method: GET\n        name: legacysuggest\n        description: Legacy suggestion endpoint\n        call: open-food-facts.legacysuggest\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: open-food-facts-mcp\n    transport:\
  \ http\n    description: MCP adapter for Open Food Facts API for AI agent use.\n    tools:\n    - name: getproductbybarcode\n      description: Get a product by barcode\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-food-facts.getproductbybarcode\n      with:\n        barcode: tools.barcode\n        fields: tools.fields\n        lc: tools.lc\n      inputParameters:\n      - name: barcode\n        type: string\n        description: Product barcode such as an EAN-13.\n        required: true\n      - name: fields\n        type: string\n        description: Comma-separated list of fields to return.\n      - name: lc\n        type: string\n        description: Language code for localized fields (e.g., en, fr).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproductbybarcodejson\n      description: Get a product by barcode (JSON)\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: open-food-facts.getproductbybarcodejson\n      with:\n        barcode: tools.barcode\n        fields: tools.fields\n        blame: tools.blame\n      inputParameters:\n      - name: barcode\n        type: string\n        description: barcode\n        required: true\n      - name: fields\n        type: string\n        description: fields\n      - name: blame\n        type: integer\n        description: When 1, include modification history.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchproducts\n      description: Search products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-food-facts.searchproducts\n      with:\n        code: tools.code\n        categories_tags_en: tools.categories_tags_en\n        brands_tags: tools.brands_tags\n        labels_tags: tools.labels_tags\n        countries_tags_en: tools.countries_tags_en\n        nutrition_grades_tags:\
  \ tools.nutrition_grades_tags\n        fields: tools.fields\n        page: tools.page\n        page_size: tools.page_size\n        sort_by: tools.sort_by\n      inputParameters:\n      - name: code\n        type: string\n        description: Comma-separated list of barcodes for bulk lookup.\n      - name: categories_tags_en\n        type: string\n        description: categories_tags_en\n      - name: brands_tags\n        type: string\n        description: brands_tags\n      - name: labels_tags\n        type: string\n        description: labels_tags\n      - name: countries_tags_en\n        type: string\n        description: countries_tags_en\n      - name: nutrition_grades_tags\n        type: string\n        description: nutrition_grades_tags\n      - name: fields\n        type: string\n        description: fields\n      - name: page\n        type: integer\n        description: page\n      - name: page_size\n        type: integer\n        description: page_size\n      - name: sort_by\n\
  \        type: string\n        description: sort_by\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettaxonomy\n      description: Retrieve taxonomy entries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-food-facts.gettaxonomy\n      with:\n        tagtype: tools.tagtype\n        tags: tools.tags\n        fields: tools.fields\n      inputParameters:\n      - name: tagtype\n        type: string\n        description: tagtype\n        required: true\n      - name: tags\n        type: string\n        description: Comma-separated taxonomy tag identifiers.\n      - name: fields\n        type: string\n        description: fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: taxonomysuggestions\n      description: Taxonomy autocomplete suggestions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-food-facts.taxonomysuggestions\n\
  \      with:\n        tagtype: tools.tagtype\n        string: tools.string\n        lc: tools.lc\n        limit: tools.limit\n      inputParameters:\n      - name: tagtype\n        type: string\n        description: tagtype\n        required: true\n      - name: string\n        type: string\n        description: Prefix to match.\n      - name: lc\n        type: string\n        description: lc\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproductv3\n      description: Get a product (v3)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-food-facts.getproductv3\n      with:\n        barcode: tools.barcode\n        fields: tools.fields\n      inputParameters:\n      - name: barcode\n        type: string\n        description: barcode\n        required: true\n      - name: fields\n        type: string\n        description: fields\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: legacysuggest\n      description: Legacy suggestion endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-food-facts.legacysuggest\n      with:\n        tagtype: tools.tagtype\n        term: tools.term\n      inputParameters:\n      - name: tagtype\n        type: string\n        description: tagtype\n        required: true\n      - name: term\n        type: string\n        description: term\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/open-food-facts/refs/heads/main/capabilities/open-food-facts-capability.yaml
tags:
- Open
- Food
- Facts
- API
tools:
- description: Get a product by barcode
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproductbybarcode
- description: Get a product by barcode (JSON)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproductbybarcodejson
- description: Search products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchproducts
- description: Retrieve taxonomy entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettaxonomy
- description: Taxonomy autocomplete suggestions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: taxonomysuggestions
- description: Get a product (v3)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproductv3
- description: Legacy suggestion endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: legacysuggest
---
