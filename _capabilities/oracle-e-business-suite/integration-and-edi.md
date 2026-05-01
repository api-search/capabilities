---
categories: []
consumed_apis:
- oracle-isg-rest
- oracle-ecommerce-gateway
description: Integration capabilities combining ISG REST API for service management and e-Commerce Gateway for EDI document exchange with trading partners. Used by integration architects and B2B teams.
layout: capability
name: Oracle EBS Integration and EDI
operations:
- description: Authenticate.
  method: POST
  name: login
  path: /v1/auth
- description: List trading partners.
  method: GET
  name: get-trading-partners
  path: /v1/trading-partners
- description: List inbound transactions.
  method: GET
  name: get-inbound-transactions
  path: /v1/inbound-transactions
- description: List outbound transactions.
  method: GET
  name: get-outbound-transactions
  path: /v1/outbound-transactions
personas: []
provider_name: Oracle E-Business Suite
provider_slug: oracle-e-business-suite
search_terms:
- retrieve trading partners.
- edi get outbound transactions
- list outbound transactions.
- initialize responsibility context.
- list inbound transactions.
- list trading partners.
- isg login
- edi get inbound transactions
- get inbound transactions
- edi get trading partner by id
- edi get trading partners
- extract an outbound edi transaction.
- get trading partner by id.
- retrieve inbound edi transactions.
- edi import inbound transaction
- edi extract outbound transaction
- integration
- outbound edi transactions.
- get wadl for a rest service.
- soa gateway
- end the current session.
- login
- get trading partners
- business applications
- import an inbound edi transaction.
- isg invoke rest method
- trading partner management.
- invoke a rest method on a service.
- retrieve code conversion mappings.
- e-business suite
- enterprise
- edi
- isg logout
- get outbound transactions
- authenticate and obtain session token.
- authenticate.
- retrieve outbound edi transactions.
- edi get code conversions
- authentication.
- erp
- isg initialize
- inbound edi transactions.
- isg get service wadl
- oracle
slug: integration-and-edi
source_filename: integration-and-edi.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Oracle EBS Integration and EDI\"\n  description: \"Integration capabilities combining ISG REST API for service management and e-Commerce Gateway for EDI document exchange with trading partners. Used by integration architects and B2B teams.\"\n  tags:\n    - Oracle\n    - Integration\n    - EDI\n    - SOA Gateway\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ORACLE_EBS_TOKEN: ORACLE_EBS_TOKEN\n      ORACLE_EBS_USERNAME: ORACLE_EBS_USERNAME\n      ORACLE_EBS_PASSWORD: ORACLE_EBS_PASSWORD\n\ncapability:\n  consumes:\n    - import: oracle-isg-rest\n      location: ./shared/isg-rest.yaml\n    - import: oracle-ecommerce-gateway\n      location: ./shared/ecommerce-gateway.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: integration-edi-api\n      description: \"Unified REST API for Oracle EBS integration and EDI.\"\n      resources:\n        - path: /v1/auth\n\
  \          name: auth\n          description: \"Authentication.\"\n          operations:\n            - method: POST\n              name: login\n              description: \"Authenticate.\"\n              call: \"oracle-isg-rest.login\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/trading-partners\n          name: trading-partners\n          description: \"Trading partner management.\"\n          operations:\n            - method: GET\n              name: get-trading-partners\n              description: \"List trading partners.\"\n              call: \"oracle-ecommerce-gateway.get-trading-partners\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/inbound-transactions\n          name: inbound-transactions\n          description: \"Inbound EDI transactions.\"\n          operations:\n            - method: GET\n              name: get-inbound-transactions\n\
  \              description: \"List inbound transactions.\"\n              call: \"oracle-ecommerce-gateway.get-inbound-transactions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/outbound-transactions\n          name: outbound-transactions\n          description: \"Outbound EDI transactions.\"\n          operations:\n            - method: GET\n              name: get-outbound-transactions\n              description: \"List outbound transactions.\"\n              call: \"oracle-ecommerce-gateway.get-outbound-transactions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9083\n      namespace: integration-edi-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Oracle EBS integration and EDI.\"\n      tools:\n        - name: isg-login\n          description: \"Authenticate and obtain session token.\"\n     \
  \     hints:\n            readOnly: false\n          call: \"oracle-isg-rest.login\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: isg-logout\n          description: \"End the current session.\"\n          hints:\n            readOnly: false\n          call: \"oracle-isg-rest.logout\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: isg-initialize\n          description: \"Initialize responsibility context.\"\n          hints:\n            readOnly: false\n          call: \"oracle-isg-rest.initialize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: isg-get-service-wadl\n          description: \"Get WADL for a REST service.\"\n          hints:\n            readOnly: true\n          call: \"oracle-isg-rest.get-service-wadl\"\n          with:\n            service: \"tools.service\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n        - name: isg-invoke-rest-method\n          description: \"Invoke a REST method on a service.\"\n          hints:\n            readOnly: false\n          call: \"oracle-isg-rest.invoke-rest-method\"\n          with:\n            service: \"tools.service\"\n            method: \"tools.method\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edi-get-trading-partners\n          description: \"Retrieve trading partners.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"oracle-ecommerce-gateway.get-trading-partners\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edi-get-trading-partner-by-id\n          description: \"Get trading partner by ID.\"\n          hints:\n            readOnly: true\n          call: \"oracle-ecommerce-gateway.get-trading-partner-by-id\"\n         \
  \ with:\n            tradingPartnerId: \"tools.trading_partner_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edi-get-inbound-transactions\n          description: \"Retrieve inbound EDI transactions.\"\n          hints:\n            readOnly: true\n          call: \"oracle-ecommerce-gateway.get-inbound-transactions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edi-import-inbound-transaction\n          description: \"Import an inbound EDI transaction.\"\n          hints:\n            readOnly: false\n          call: \"oracle-ecommerce-gateway.import-inbound-transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edi-get-outbound-transactions\n          description: \"Retrieve outbound EDI transactions.\"\n          hints:\n            readOnly: true\n          call: \"oracle-ecommerce-gateway.get-outbound-transactions\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edi-extract-outbound-transaction\n          description: \"Extract an outbound EDI transaction.\"\n          hints:\n            readOnly: false\n          call: \"oracle-ecommerce-gateway.extract-outbound-transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edi-get-code-conversions\n          description: \"Retrieve code conversion mappings.\"\n          hints:\n            readOnly: true\n          call: \"oracle-ecommerce-gateway.get-code-conversions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-e-business-suite/refs/heads/main/capabilities/integration-and-edi.yaml
tags:
- Oracle
- Integration
- EDI
- SOA Gateway
tools:
- description: Authenticate and obtain session token.
  hints:
    readOnly: false
  name: isg-login
- description: End the current session.
  hints:
    readOnly: false
  name: isg-logout
- description: Initialize responsibility context.
  hints:
    readOnly: false
  name: isg-initialize
- description: Get WADL for a REST service.
  hints:
    readOnly: true
  name: isg-get-service-wadl
- description: Invoke a REST method on a service.
  hints:
    readOnly: false
  name: isg-invoke-rest-method
- description: Retrieve trading partners.
  hints:
    openWorld: true
    readOnly: true
  name: edi-get-trading-partners
- description: Get trading partner by ID.
  hints:
    readOnly: true
  name: edi-get-trading-partner-by-id
- description: Retrieve inbound EDI transactions.
  hints:
    readOnly: true
  name: edi-get-inbound-transactions
- description: Import an inbound EDI transaction.
  hints:
    readOnly: false
  name: edi-import-inbound-transaction
- description: Retrieve outbound EDI transactions.
  hints:
    readOnly: true
  name: edi-get-outbound-transactions
- description: Extract an outbound EDI transaction.
  hints:
    readOnly: false
  name: edi-extract-outbound-transaction
- description: Retrieve code conversion mappings.
  hints:
    readOnly: true
  name: edi-get-code-conversions
---
