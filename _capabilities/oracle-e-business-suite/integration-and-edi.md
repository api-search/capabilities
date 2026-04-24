---
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
- login
- integration
- initialize responsibility context.
- get wadl for a rest service.
- trading partner management.
- get trading partners
- list trading partners.
- get inbound transactions
- edi get code conversions
- retrieve trading partners.
- end the current session.
- isg login
- authenticate.
- edi get outbound transactions
- erp
- outbound edi transactions.
- edi get trading partner by id
- edi get trading partners
- inbound edi transactions.
- retrieve inbound edi transactions.
- list outbound transactions.
- isg logout
- soa gateway
- retrieve outbound edi transactions.
- get outbound transactions
- business applications
- e-business suite
- list inbound transactions.
- isg initialize
- edi get inbound transactions
- edi import inbound transaction
- edi extract outbound transaction
- extract an outbound edi transaction.
- oracle
- edi
- import an inbound edi transaction.
- invoke a rest method on a service.
- get trading partner by id.
- isg get service wadl
- authentication.
- retrieve code conversion mappings.
- authenticate and obtain session token.
- isg invoke rest method
- enterprise
slug: integration-and-edi
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
