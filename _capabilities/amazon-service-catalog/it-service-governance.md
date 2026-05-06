---
categories:
- compliance
consumed_apis: []
description: Unified capability for IT service governance including portfolio management, product catalog curation, and self-service product provisioning. Used by IT Administrators and End Users.
layout: capability
name: Amazon Service Catalog IT Service Governance
operations:
- description: List all IT service portfolios
  method: GET
  name: list-portfolios
  path: /v1/portfolios
- description: Create an IT service portfolio
  method: POST
  name: create-portfolio
  path: /v1/portfolios
- description: Browse approved products
  method: GET
  name: search-products
  path: /v1/products
- description: Add a product to the catalog
  method: POST
  name: create-product
  path: /v1/products
- description: Provision an approved product
  method: POST
  name: provision-product
  path: /v1/provisioned-products
personas: []
provider_name: Amazon Service Catalog
provider_slug: amazon-service-catalog
search_terms:
- describe portfolio
- it governance
- add a new product to the it service catalog
- check the status of a provisioned product
- create a new it service catalog portfolio
- compliance
- terminate provisioned product
- it service portfolio management
- self-service provision an approved it product
- cloud governance
- create portfolio
- terminate and decommission a provisioned product
- browse approved products
- list all it service catalog portfolios
- list all it service portfolios
- provision product
- self-service
- self-service product provisioning
- browse and search approved it products
- approved product catalog
- provision an approved product
- list portfolios
- get details about an it service portfolio
- service catalog
- create product
- create an it service portfolio
- amazon service catalog
- add a product to the catalog
- search products
- describe provisioned product
slug: it-service-governance
source_filename: it-service-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Service Catalog IT Service Governance\n  description: Unified capability for IT service governance including portfolio management, product catalog curation, and\n    self-service product provisioning. Used by IT Administrators and End Users.\n  tags:\n  - Amazon Service Catalog\n  - IT Governance\n  - Cloud Governance\n  - Self-Service\n  - Compliance\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-service-catalog\n    baseUri: https://servicecatalog.us-east-1.amazonaws.com\n    description: Amazon Service Catalog REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: AWS4-HMAC-SHA256 Credential={{AWS_ACCESS_KEY_ID}}\n      placement: header\n    resources:\n    - name: portfolios\n\
  \      path: /portfolios\n      description: Portfolio management operations\n      operations:\n      - name: list-portfolios\n        method: GET\n        description: Lists all portfolios in the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-portfolio\n        method: POST\n        description: Creates a portfolio\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-portfolio\n        method: GET\n        description: Gets information about a portfolio\n        inputParameters:\n        - name: PortfolioId\n          in: path\n          type: string\n          required: true\n          description: The portfolio identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-portfolio\n\
  \        method: DELETE\n        description: Deletes a portfolio\n        inputParameters:\n        - name: PortfolioId\n          in: path\n          type: string\n          required: true\n          description: The portfolio identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n      description: Product management operations\n      operations:\n      - name: search-products\n        method: GET\n        description: Gets information about products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-product\n        method: POST\n        description: Creates a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: provisioned-products\n      path: /provisioned-products\n\
  \      description: Provisioned product management\n      operations:\n      - name: provision-product\n        method: POST\n        description: Provisions a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-provisioned-product\n        method: GET\n        description: Gets information about a provisioned product\n        inputParameters:\n        - name: ProvisionedProductId\n          in: path\n          type: string\n          required: true\n          description: The provisioned product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: terminate-provisioned-product\n        method: DELETE\n        description: Terminates a provisioned product\n        inputParameters:\n        - name: ProvisionedProductId\n          in: path\n          type: string\n          required:\
  \ true\n          description: The provisioned product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: it-service-governance-api\n    description: Unified REST API for Amazon Service Catalog IT service governance.\n    resources:\n    - path: /v1/portfolios\n      name: portfolios\n      description: IT service portfolio management\n      operations:\n      - method: GET\n        name: list-portfolios\n        description: List all IT service portfolios\n        call: amazon-service-catalog.list-portfolios\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-portfolio\n        description: Create an IT service portfolio\n        call: amazon-service-catalog.create-portfolio\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n\
  \      name: products\n      description: Approved product catalog\n      operations:\n      - method: GET\n        name: search-products\n        description: Browse approved products\n        call: amazon-service-catalog.search-products\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-product\n        description: Add a product to the catalog\n        call: amazon-service-catalog.create-product\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provisioned-products\n      name: provisioned-products\n      description: Self-service product provisioning\n      operations:\n      - method: POST\n        name: provision-product\n        description: Provision an approved product\n        call: amazon-service-catalog.provision-product\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: it-service-governance-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted Amazon Service Catalog IT service governance.\n    tools:\n    - name: list-portfolios\n      description: List all IT service catalog portfolios\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amazon-service-catalog.list-portfolios\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-portfolio\n      description: Create a new IT service catalog portfolio\n      hints:\n        readOnly: false\n        idempotent: false\n      call: amazon-service-catalog.create-portfolio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-portfolio\n      description: Get details about an IT service portfolio\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amazon-service-catalog.describe-portfolio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-products\n      description:\
  \ Browse and search approved IT products\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amazon-service-catalog.search-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-product\n      description: Add a new product to the IT service catalog\n      hints:\n        readOnly: false\n        idempotent: false\n      call: amazon-service-catalog.create-product\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provision-product\n      description: Self-service provision an approved IT product\n      hints:\n        readOnly: false\n        idempotent: false\n      call: amazon-service-catalog.provision-product\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-provisioned-product\n      description: Check the status of a provisioned product\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amazon-service-catalog.describe-provisioned-product\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: terminate-provisioned-product\n      description: Terminate and decommission a provisioned product\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amazon-service-catalog.terminate-provisioned-product\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-service-catalog/refs/heads/main/capabilities/it-service-governance.yaml
tags:
- Amazon Service Catalog
- IT Governance
- Cloud Governance
- Self-Service
- Compliance
tools:
- description: List all IT service catalog portfolios
  hints:
    idempotent: true
    readOnly: true
  name: list-portfolios
- description: Create a new IT service catalog portfolio
  hints:
    idempotent: false
    readOnly: false
  name: create-portfolio
- description: Get details about an IT service portfolio
  hints:
    idempotent: true
    readOnly: true
  name: describe-portfolio
- description: Browse and search approved IT products
  hints:
    idempotent: true
    readOnly: true
  name: search-products
- description: Add a new product to the IT service catalog
  hints:
    idempotent: false
    readOnly: false
  name: create-product
- description: Self-service provision an approved IT product
  hints:
    idempotent: false
    readOnly: false
  name: provision-product
- description: Check the status of a provisioned product
  hints:
    idempotent: true
    readOnly: true
  name: describe-provisioned-product
- description: Terminate and decommission a provisioned product
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: terminate-provisioned-product
---
