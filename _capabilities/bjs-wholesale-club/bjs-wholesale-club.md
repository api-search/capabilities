---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Bjs Wholesale Club
operations: []
personas: []
provider_name: BJ's Wholesale Club
provider_slug: bjs-wholesale-club
search_terms:
- wholesale
- membership
- retail
- ecommerce
slug: bjs-wholesale-club
source_filename: bjs-wholesale-club.yaml
source_heading: Capability Spec
source_yaml: "name: BJ's Wholesale Club Partner API Capability\ndescription: >-\n  Naftiko capability definition for BJ's Wholesale Club partner API providing\n  product catalog, membership verification, inventory, and order management.\nversion: 1.0.0\ncapabilities:\n  - name: listProducts\n    description: Retrieve paginated product catalog with pricing and availability\n    method: GET\n    path: /products\n    parameters:\n      - name: category\n        type: string\n        required: false\n      - name: page\n        type: integer\n        required: false\n      - name: limit\n        type: integer\n        required: false\n  - name: getProduct\n    description: Retrieve details for a specific product by ID\n    method: GET\n    path: /products/{productId}\n    parameters:\n      - name: productId\n        type: string\n        required: true\n  - name: getProductInventory\n    description: Check inventory availability across club locations\n    method: GET\n    path: /products/{productId}/inventory\n\
  \    parameters:\n      - name: productId\n        type: string\n        required: true\n      - name: clubId\n        type: string\n        required: false\n  - name: verifyMembership\n    description: Verify BJ's membership number and return status and tier\n    method: POST\n    path: /membership/verify\n    body:\n      membershipNumber: string\n      lastName: string\n  - name: createOrder\n    description: Create a new order through BJ's digital commerce platform\n    method: POST\n    path: /orders\n  - name: getOrder\n    description: Retrieve status and details for a specific order\n    method: GET\n    path: /orders/{orderId}\n  - name: listClubs\n    description: List BJ's club locations with address, hours, and services\n    method: GET\n    path: /clubs\nauthentication:\n  type: apiKey\n  header: X-BJS-API-Key\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bjs-wholesale-club/refs/heads/main/capabilities/bjs-wholesale-club.yaml
tags: []
tools: []
---
