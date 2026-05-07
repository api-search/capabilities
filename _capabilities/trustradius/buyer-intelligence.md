---
categories: []
consumed_apis: []
description: Unified B2B buyer intelligence capability combining product data, verified reviews, and category research. Used by sales and marketing teams to research software categories, compare products, access verified buyer reviews, and surface competitive intelligence. Enables AI-assisted vendor evaluation, competitive analysis, and review-based demand generation workflows.
layout: capability
name: TrustRadius Buyer Intelligence
operations:
- description: List B2B software products with TrustRadius scores.
  method: GET
  name: list-products
  path: /v1/products
- description: Get detailed product profile.
  method: GET
  name: get-product
  path: /v1/products/{productSlug}
- description: Get aggregate product ratings.
  method: GET
  name: get-product-ratings
  path: /v1/products/{productSlug}/ratings
- description: List software categories.
  method: GET
  name: list-categories
  path: /v1/categories
- description: Get category with top products.
  method: GET
  name: get-category
  path: /v1/categories/{categorySlug}
- description: List verified B2B software reviews.
  method: GET
  name: list-reviews
  path: /v1/reviews
- description: Get full review content.
  method: GET
  name: get-review
  path: /v1/reviews/{reviewId}
personas: []
provider_name: TrustRadius
provider_slug: trustradius
search_terms:
- get detailed product profile.
- b2b software products
- intent data
- list verified b2b software reviews.
- list software categories.
- get detailed product profile including trustradius score, categories, and aggregate ratings.
- buyer intelligence
- get product
- list products
- reviews
- b2b software reviews
- get full review content.
- get review
- list verified b2b software reviews with filtering by product, industry, company size, and minimum score.
- product ratings
- software reviews
- list b2b software products with trustradius scores.
- get multi-dimensional rating breakdown for a product across usability, support, and value.
- software categories
- list categories
- list all b2b software categories available on trustradius.
- list b2b software products in a category with trustradius scores and review counts.
- competitive analysis
- verified reviews
- get category
- list reviews
- get the complete text, ratings, pros, and cons from a specific verified b2b software review.
- categories
- individual review
- product reviews
- get category with top products.
- get a software category with its top-rated products for category research.
- category details
- get aggregate product ratings.
- get product ratings
- product profile
slug: buyer-intelligence
source_filename: buyer-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TrustRadius Buyer Intelligence\n  description: Unified B2B buyer intelligence capability combining product data, verified reviews, and category research.\n    Used by sales and marketing teams to research software categories, compare products, access verified buyer reviews, and\n    surface competitive intelligence. Enables AI-assisted vendor evaluation, competitive analysis, and review-based demand\n    generation workflows.\n  tags:\n  - B2B Software Reviews\n  - Buyer Intelligence\n  - Intent Data\n  - Product Reviews\n  - Software Categories\n  - Competitive Analysis\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRUSTRADIUS_API_KEY: TRUSTRADIUS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: trustradius-products\n    baseUri: https://api.trustradius.com/v1\n    description: TrustRadius product and category data.\n    authentication:\n      type: apikey\n      key: X-API-Key\n\
  \      value: '{{TRUSTRADIUS_API_KEY}}'\n      placement: header\n    resources:\n    - name: products\n      path: /products\n      description: B2B software product listings\n      operations:\n      - name: list-products\n        method: GET\n        description: Retrieve B2B software products with ratings and review counts.\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: perPage\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: product\n      path: /products/{productSlug}\n      description: Individual product details\n      operations:\n      - name: get-product\n        method: GET\n        description: Get detailed product profile including\
  \ TrustRadius score.\n        inputParameters:\n        - name: productSlug\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: product-ratings\n      path: /products/{productSlug}/ratings\n      description: Product aggregate ratings\n      operations:\n      - name: get-product-ratings\n        method: GET\n        description: Get aggregate rating breakdown for a product.\n        inputParameters:\n        - name: productSlug\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories\n      path: /categories\n      description: Software categories\n      operations:\n      - name: list-categories\n        method: GET\n        description: List all software categories on\
  \ TrustRadius.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: category\n      path: /categories/{categorySlug}\n      description: Category details with top products\n      operations:\n      - name: get-category\n        method: GET\n        description: Get category details including top-rated products.\n        inputParameters:\n        - name: categorySlug\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: trustradius-reviews\n    baseUri: https://api.trustradius.com/v1\n    description: TrustRadius verified review data.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{TRUSTRADIUS_API_KEY}}'\n      placement: header\n    resources:\n    - name: reviews\n      path: /reviews\n      description:\
  \ Verified user reviews\n      operations:\n      - name: list-reviews\n        method: GET\n        description: List verified reviews with filtering by product, category, industry, and rating.\n        inputParameters:\n        - name: product\n          in: query\n          type: string\n          required: false\n        - name: category\n          in: query\n          type: string\n          required: false\n        - name: industry\n          in: query\n          type: string\n          required: false\n        - name: companySize\n          in: query\n          type: string\n          required: false\n        - name: minScore\n          in: query\n          type: integer\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: perPage\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n    - name: review\n      path: /reviews/{reviewId}\n      description: Individual review\n      operations:\n      - name: get-review\n        method: GET\n        description: Get full content of a specific review.\n        inputParameters:\n        - name: reviewId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: trustradius-buyer-intelligence-api\n    description: Unified REST API for B2B software research, product comparison, and buyer review access.\n    resources:\n    - path: /v1/products\n      name: products\n      description: B2B software products\n      operations:\n      - method: GET\n        name: list-products\n        description: List B2B software products with TrustRadius scores.\n        call: trustradius-products.list-products\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{productSlug}\n      name: product\n      description: Product profile\n      operations:\n      - method: GET\n        name: get-product\n        description: Get detailed product profile.\n        call: trustradius-products.get-product\n        with:\n          productSlug: rest.productSlug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{productSlug}/ratings\n      name: product-ratings\n      description: Product ratings\n      operations:\n      - method: GET\n        name: get-product-ratings\n        description: Get aggregate product ratings.\n        call: trustradius-products.get-product-ratings\n        with:\n          productSlug: rest.productSlug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/categories\n      name: categories\n      description: Software categories\n      operations:\n\
  \      - method: GET\n        name: list-categories\n        description: List software categories.\n        call: trustradius-products.list-categories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/categories/{categorySlug}\n      name: category\n      description: Category details\n      operations:\n      - method: GET\n        name: get-category\n        description: Get category with top products.\n        call: trustradius-products.get-category\n        with:\n          categorySlug: rest.categorySlug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reviews\n      name: reviews\n      description: Verified reviews\n      operations:\n      - method: GET\n        name: list-reviews\n        description: List verified B2B software reviews.\n        call: trustradius-reviews.list-reviews\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reviews/{reviewId}\n\
  \      name: review\n      description: Individual review\n      operations:\n      - method: GET\n        name: get-review\n        description: Get full review content.\n        call: trustradius-reviews.get-review\n        with:\n          reviewId: rest.reviewId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: trustradius-buyer-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted B2B software research, competitive analysis, and buyer review access.\n    tools:\n    - name: list-products\n      description: List B2B software products in a category with TrustRadius scores and review counts.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trustradius-products.list-products\n      with:\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product\n      description: Get detailed product profile\
  \ including TrustRadius score, categories, and aggregate ratings.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trustradius-products.get-product\n      with:\n        productSlug: tools.productSlug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product-ratings\n      description: Get multi-dimensional rating breakdown for a product across usability, support, and value.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trustradius-products.get-product-ratings\n      with:\n        productSlug: tools.productSlug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-categories\n      description: List all B2B software categories available on TrustRadius.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trustradius-products.list-categories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-category\n   \
  \   description: Get a software category with its top-rated products for category research.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trustradius-products.get-category\n      with:\n        categorySlug: tools.categorySlug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reviews\n      description: List verified B2B software reviews with filtering by product, industry, company size, and minimum score.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trustradius-reviews.list-reviews\n      with:\n        product: tools.product\n        category: tools.category\n        industry: tools.industry\n        companySize: tools.companySize\n        minScore: tools.minScore\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-review\n      description: Get the complete text, ratings, pros, and cons from a specific verified B2B software review.\n      hints:\n      \
  \  readOnly: true\n        openWorld: false\n      call: trustradius-reviews.get-review\n      with:\n        reviewId: tools.reviewId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/capabilities/buyer-intelligence.yaml
tags:
- B2B Software Reviews
- Buyer Intelligence
- Intent Data
- Product Reviews
- Software Categories
- Competitive Analysis
tools:
- description: List B2B software products in a category with TrustRadius scores and review counts.
  hints:
    openWorld: true
    readOnly: true
  name: list-products
- description: Get detailed product profile including TrustRadius score, categories, and aggregate ratings.
  hints:
    openWorld: false
    readOnly: true
  name: get-product
- description: Get multi-dimensional rating breakdown for a product across usability, support, and value.
  hints:
    openWorld: false
    readOnly: true
  name: get-product-ratings
- description: List all B2B software categories available on TrustRadius.
  hints:
    openWorld: true
    readOnly: true
  name: list-categories
- description: Get a software category with its top-rated products for category research.
  hints:
    openWorld: false
    readOnly: true
  name: get-category
- description: List verified B2B software reviews with filtering by product, industry, company size, and minimum score.
  hints:
    openWorld: true
    readOnly: true
  name: list-reviews
- description: Get the complete text, ratings, pros, and cons from a specific verified B2B software review.
  hints:
    openWorld: false
    readOnly: true
  name: get-review
---
