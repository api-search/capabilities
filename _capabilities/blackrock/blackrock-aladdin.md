---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Blackrock Aladdin
operations: []
personas: []
provider_name: BlackRock
provider_slug: blackrock
search_terms:
- fintech
- finance
- investment management
- portfolio management
- risk analytics
- asset management
slug: blackrock-aladdin
source_filename: blackrock-aladdin.yaml
source_heading: Capability Spec
source_yaml: "name: BlackRock Aladdin API Capability\ndescription: >-\n  Naftiko capability definition for BlackRock Aladdin APIs providing portfolio\n  analytics, risk reporting, data access, and order management for institutional\n  asset managers.\nversion: 1.0.0\ncapabilities:\n  - name: getPortfolio\n    description: Retrieve portfolio composition, positions, and market values\n    method: GET\n    path: /portfolios/{portfolioId}\n    parameters:\n      - name: portfolioId\n        type: string\n        required: true\n      - name: asOfDate\n        type: date\n        required: false\n  - name: listPortfolios\n    description: List all portfolios accessible to the authenticated client\n    method: GET\n    path: /portfolios\n  - name: getRiskReport\n    description: Retrieve risk analytics report for a portfolio\n    method: GET\n    path: /portfolios/{portfolioId}/risk\n    parameters:\n      - name: portfolioId\n        type: string\n        required: true\n      - name: asOfDate\n\
  \        type: date\n        required: false\n  - name: runStressTest\n    description: Run a stress test scenario against a portfolio\n    method: POST\n    path: /portfolios/{portfolioId}/stress-tests\n  - name: getPerformance\n    description: Retrieve performance attribution for a portfolio\n    method: GET\n    path: /portfolios/{portfolioId}/performance\n  - name: submitOrder\n    description: Submit a trade order to the Aladdin OMS\n    method: POST\n    path: /orders\n  - name: getOrder\n    description: Retrieve status of a trade order\n    method: GET\n    path: /orders/{orderId}\nauthentication:\n  type: oauth2\n  flows:\n    clientCredentials:\n      tokenUrl: https://aladdin.blackrock.com/oauth/token\n      scopes:\n        portfolios:read: Read portfolio data\n        risk:read: Read risk analytics\n        orders:write: Submit trade orders\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/blackrock/refs/heads/main/capabilities/blackrock-aladdin.yaml
tags: []
tools: []
---
