---
categories: []
consumed_apis: []
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
- authentication.
- retrieve inbound edi transactions.
- authenticate and obtain session token.
- extract an outbound edi transaction.
- e-business suite
- retrieve code conversion mappings.
- outbound edi transactions.
- list outbound transactions.
- retrieve trading partners.
- get trading partner by id.
- edi
- edi get trading partner by id
- authenticate.
- end the current session.
- soa gateway
- get inbound transactions
- integration
- business applications
- login
- invoke a rest method on a service.
- isg logout
- edi get code conversions
- edi get inbound transactions
- retrieve outbound edi transactions.
- isg initialize
- edi import inbound transaction
- get outbound transactions
- isg invoke rest method
- import an inbound edi transaction.
- edi extract outbound transaction
- edi get outbound transactions
- enterprise
- initialize responsibility context.
- list trading partners.
- edi get trading partners
- get trading partners
- isg get service wadl
- erp
- isg login
- get wadl for a rest service.
- inbound edi transactions.
- list inbound transactions.
- oracle
- trading partner management.
slug: integration-and-edi
source_filename: integration-and-edi.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle EBS Integration and EDI\n  description: Integration capabilities combining ISG REST API for service management and e-Commerce Gateway for EDI document\n    exchange with trading partners. Used by integration architects and B2B teams.\n  tags:\n  - Oracle\n  - Integration\n  - EDI\n  - SOA Gateway\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ORACLE_EBS_TOKEN: ORACLE_EBS_TOKEN\n    ORACLE_EBS_USERNAME: ORACLE_EBS_USERNAME\n    ORACLE_EBS_PASSWORD: ORACLE_EBS_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-isg-rest\n    baseUri: https://{instance}.oracle.com/webservices/rest\n    description: Oracle EBS ISG REST API for session management and service discovery.\n    authentication:\n      type: basic\n      username: '{{ORACLE_EBS_USERNAME}}'\n      password: '{{ORACLE_EBS_PASSWORD}}'\n    resources:\n    - name: auth\n      path: /auth\n      description: Authentication\
  \ and session management.\n      operations:\n      - name: login\n        method: POST\n        description: Authenticate and obtain a session token.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: logout\n        method: POST\n        description: End the current session.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: initialize\n      path: /initialize\n      description: Initialize responsibility context.\n      operations:\n      - name: initialize\n        method: POST\n        description: Initialize the EBS responsibility context.\n        body:\n          type: json\n          data:\n            responsibilityId: '{{tools.responsibility_id}}'\n         \
  \   applicationId: '{{tools.application_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wadl\n      path: /{service}/wadl\n      description: Service WADL discovery.\n      operations:\n      - name: get-service-wadl\n        method: GET\n        description: Get WADL for a deployed REST service.\n        inputParameters:\n        - name: service\n          in: path\n          type: string\n          required: true\n          description: Service name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-method\n      path: /{service}/{method}\n      description: Invoke a generic REST method.\n      operations:\n      - name: invoke-rest-method\n        method: POST\n        description: Invoke a REST method on a deployed service.\n        inputParameters:\n        - name: service\n          in: path\n\
  \          type: string\n          required: true\n          description: Service name.\n        - name: method\n          in: path\n          type: string\n          required: true\n          description: Method name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: oracle-ecommerce-gateway\n    baseUri: https://{instance}.oracle.com/webservices/rest\n    description: Oracle EBS e-Commerce Gateway API for EDI transactions.\n    authentication:\n      type: bearer\n      token: '{{ORACLE_EBS_TOKEN}}'\n    resources:\n    - name: trading-partners\n      path: /ecx/trading-partners\n      description: Trading partner management.\n      operations:\n      - name: get-trading-partners\n        method: GET\n        description: Retrieve trading partners.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \   - name: trading-partner\n      path: /ecx/trading-partners/{tradingPartnerId}\n      description: Specific trading partner.\n      operations:\n      - name: get-trading-partner-by-id\n        method: GET\n        description: Get trading partner by ID.\n        inputParameters:\n        - name: tradingPartnerId\n          in: path\n          type: integer\n          required: true\n          description: Trading partner identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inbound-transactions\n      path: /ecx/inbound-transactions\n      description: Inbound EDI transactions.\n      operations:\n      - name: get-inbound-transactions\n        method: GET\n        description: Retrieve inbound transactions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: import-inbound-transaction\n        method:\
  \ POST\n        description: Import an inbound EDI transaction.\n        body:\n          type: json\n          data:\n            tradingPartnerId: '{{tools.trading_partner_id}}'\n            transactionType: '{{tools.transaction_type}}'\n            data: '{{tools.data}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: outbound-transactions\n      path: /ecx/outbound-transactions\n      description: Outbound EDI transactions.\n      operations:\n      - name: get-outbound-transactions\n        method: GET\n        description: Retrieve outbound transactions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: extract-outbound-transaction\n        method: POST\n        description: Extract an outbound EDI transaction.\n        body:\n          type: json\n          data:\n            transactionType: '{{tools.transaction_type}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: code-conversions\n      path: /ecx/code-conversions\n      description: EDI code conversions.\n      operations:\n      - name: get-code-conversions\n        method: GET\n        description: Retrieve code conversion mappings.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: integration-edi-api\n    description: Unified REST API for Oracle EBS integration and EDI.\n    resources:\n    - path: /v1/auth\n      name: auth\n      description: Authentication.\n      operations:\n      - method: POST\n        name: login\n        description: Authenticate.\n        call: oracle-isg-rest.login\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trading-partners\n      name: trading-partners\n\
  \      description: Trading partner management.\n      operations:\n      - method: GET\n        name: get-trading-partners\n        description: List trading partners.\n        call: oracle-ecommerce-gateway.get-trading-partners\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inbound-transactions\n      name: inbound-transactions\n      description: Inbound EDI transactions.\n      operations:\n      - method: GET\n        name: get-inbound-transactions\n        description: List inbound transactions.\n        call: oracle-ecommerce-gateway.get-inbound-transactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/outbound-transactions\n      name: outbound-transactions\n      description: Outbound EDI transactions.\n      operations:\n      - method: GET\n        name: get-outbound-transactions\n        description: List outbound transactions.\n        call: oracle-ecommerce-gateway.get-outbound-transactions\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9083\n    namespace: integration-edi-mcp\n    transport: http\n    description: MCP server for AI-assisted Oracle EBS integration and EDI.\n    tools:\n    - name: isg-login\n      description: Authenticate and obtain session token.\n      hints:\n        readOnly: false\n      call: oracle-isg-rest.login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: isg-logout\n      description: End the current session.\n      hints:\n        readOnly: false\n      call: oracle-isg-rest.logout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: isg-initialize\n      description: Initialize responsibility context.\n      hints:\n        readOnly: false\n      call: oracle-isg-rest.initialize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: isg-get-service-wadl\n      description: Get WADL for a REST service.\n\
  \      hints:\n        readOnly: true\n      call: oracle-isg-rest.get-service-wadl\n      with:\n        service: tools.service\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: isg-invoke-rest-method\n      description: Invoke a REST method on a service.\n      hints:\n        readOnly: false\n      call: oracle-isg-rest.invoke-rest-method\n      with:\n        service: tools.service\n        method: tools.method\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: edi-get-trading-partners\n      description: Retrieve trading partners.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: oracle-ecommerce-gateway.get-trading-partners\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: edi-get-trading-partner-by-id\n      description: Get trading partner by ID.\n      hints:\n        readOnly: true\n      call: oracle-ecommerce-gateway.get-trading-partner-by-id\n      with:\n\
  \        tradingPartnerId: tools.trading_partner_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: edi-get-inbound-transactions\n      description: Retrieve inbound EDI transactions.\n      hints:\n        readOnly: true\n      call: oracle-ecommerce-gateway.get-inbound-transactions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: edi-import-inbound-transaction\n      description: Import an inbound EDI transaction.\n      hints:\n        readOnly: false\n      call: oracle-ecommerce-gateway.import-inbound-transaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: edi-get-outbound-transactions\n      description: Retrieve outbound EDI transactions.\n      hints:\n        readOnly: true\n      call: oracle-ecommerce-gateway.get-outbound-transactions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: edi-extract-outbound-transaction\n      description: Extract\
  \ an outbound EDI transaction.\n      hints:\n        readOnly: false\n      call: oracle-ecommerce-gateway.extract-outbound-transaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: edi-get-code-conversions\n      description: Retrieve code conversion mappings.\n      hints:\n        readOnly: true\n      call: oracle-ecommerce-gateway.get-code-conversions\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
