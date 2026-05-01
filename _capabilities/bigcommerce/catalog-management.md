---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Catalog Management
operations: []
personas: []
provider_name: BigCommerce
provider_slug: bigcommerce
search_terms:
- shopping cart and checkout flow management
- payments
- payment method configuration and transaction processing
- orders
- product catalog management including products, variants, and categories
- shipping zone, method, and carrier configuration
- retail
- catalog
- saas
- online store owner managing catalog, orders, and customers via api
- developer building bigcommerce store integrations and customizations
- manage product catalog including products, categories, and brands
- customer account and address book management
- checkout
- e-commerce
- order lifecycle management from placement to fulfillment
slug: catalog-management
source_filename: catalog-management.yaml
source_heading: Capability Spec
source_yaml: "name: Catalog Management\ndescription: >-\n  Workflow capability for managing BigCommerce product catalogs including\n  products, variants, categories, and brands.\nversion: v1\n\nimports:\n  - shared/bigcommerce.yaml\n\ntools:\n  - name: list-products\n    import: bigcommerce.list-products\n    description: List all products in the BigCommerce catalog with filtering options.\n    inputSchema:\n      type: object\n      properties:\n        limit:\n          type: integer\n          description: Number of products per page\n        page:\n          type: integer\n          description: Page number for pagination\n        keyword:\n          type: string\n          description: Filter products by keyword\n  - name: get-product\n    import: bigcommerce.get-product\n    description: Get a single product by its ID including all variants and images.\n    inputSchema:\n      type: object\n      required:\n        - product_id\n      properties:\n        product_id:\n          type:\
  \ integer\n          description: The product ID to retrieve\n  - name: create-product\n    import: bigcommerce.create-product\n    description: Create a new product in the BigCommerce catalog.\n    inputSchema:\n      type: object\n      required:\n        - name\n        - price\n        - type\n        - weight\n      properties:\n        name:\n          type: string\n          description: Product name\n        price:\n          type: number\n          description: Product price\n        type:\n          type: string\n          description: Product type (physical or digital)\n        sku:\n          type: string\n          description: Stock keeping unit\n  - name: update-product\n    import: bigcommerce.update-product\n    description: Update an existing product's details, price, or inventory.\n    inputSchema:\n      type: object\n      required:\n        - product_id\n      properties:\n        product_id:\n          type: integer\n          description: The product ID to update\n\
  \  - name: delete-product\n    import: bigcommerce.delete-product\n    description: Delete a product from the catalog.\n    inputSchema:\n      type: object\n      required:\n        - product_id\n      properties:\n        product_id:\n          type: integer\n          description: The product ID to delete\n  - name: list-categories\n    import: bigcommerce.list-categories\n    description: List all product categories in the category tree.\n    inputSchema:\n      type: object\n      properties:\n        parent_id:\n          type: integer\n          description: Filter by parent category ID\n  - name: create-category\n    import: bigcommerce.create-category\n    description: Create a new product category.\n    inputSchema:\n      type: object\n      required:\n        - name\n        - parent_id\n      properties:\n        name:\n          type: string\n          description: Category name\n        parent_id:\n          type: integer\n          description: Parent category ID (0 for\
  \ root)\n  - name: list-orders\n    import: bigcommerce.list-orders\n    description: List all store orders with status filtering.\n    inputSchema:\n      type: object\n      properties:\n        status_id:\n          type: integer\n          description: Filter by order status ID\n        limit:\n          type: integer\n          description: Number of orders per page\n  - name: get-order\n    import: bigcommerce.get-order\n    description: Get a specific order by ID including all line items.\n    inputSchema:\n      type: object\n      required:\n        - order_id\n      properties:\n        order_id:\n          type: integer\n          description: The order ID to retrieve\n  - name: list-customers\n    import: bigcommerce.list-customers\n    description: List all store customers.\n    inputSchema:\n      type: object\n      properties:\n        email:\n          type: string\n          description: Filter by customer email\n  - name: create-customer\n    import: bigcommerce.create-customer\n\
  \    description: Create a new customer account in the store.\n    inputSchema:\n      type: object\n      required:\n        - email\n        - first_name\n        - last_name\n      properties:\n        email:\n          type: string\n          description: Customer email address\n        first_name:\n          type: string\n          description: Customer first name\n        last_name:\n          type: string\n          description: Customer last name\n\nexpose:\n  rest:\n    port: 8080\n  mcp:\n    port: 9080\n\npersonas:\n  - id: store-developer\n    name: Store Developer\n    description: Developer building BigCommerce integrations, apps, and custom storefronts\n  - id: merchant\n    name: Merchant\n    description: Store owner managing catalog, orders, and customers through automation\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bigcommerce/refs/heads/main/capabilities/catalog-management.yaml
tags: []
tools: []
---
