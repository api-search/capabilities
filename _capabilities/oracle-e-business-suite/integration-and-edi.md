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
- inbound edi transactions.
- edi get outbound transactions
- isg initialize
- isg invoke rest method
- isg logout
- retrieve outbound edi transactions.
- retrieve code conversion mappings.
- soa gateway
- retrieve trading partners.
- business applications
- e-business suite
- extract an outbound edi transaction.
- edi import inbound transaction
- outbound edi transactions.
- enterprise
- authenticate and obtain session token.
- isg login
- integration
- erp
- authenticate.
- invoke a rest method on a service.
- end the current session.
- edi get code conversions
- login
- list inbound transactions.
- trading partner management.
- list outbound transactions.
- edi get inbound transactions
- retrieve inbound edi transactions.
- get trading partners
- get outbound transactions
- get wadl for a rest service.
- edi get trading partner by id
- edi get trading partners
- import an inbound edi transaction.
- isg get service wadl
- edi extract outbound transaction
- initialize responsibility context.
- edi
- authentication.
- get inbound transactions
- list trading partners.
- get trading partner by id.
- oracle
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
