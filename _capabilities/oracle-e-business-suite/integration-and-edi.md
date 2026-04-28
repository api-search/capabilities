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
- list trading partners.
- isg login
- authenticate.
- get outbound transactions
- import an inbound edi transaction.
- erp
- edi get inbound transactions
- oracle
- soa gateway
- edi get trading partners
- end the current session.
- extract an outbound edi transaction.
- isg invoke rest method
- edi get trading partner by id
- business applications
- enterprise
- edi
- isg get service wadl
- outbound edi transactions.
- isg logout
- authentication.
- retrieve inbound edi transactions.
- inbound edi transactions.
- trading partner management.
- integration
- e-business suite
- edi import inbound transaction
- get inbound transactions
- isg initialize
- invoke a rest method on a service.
- retrieve trading partners.
- edi get outbound transactions
- login
- get trading partners
- authenticate and obtain session token.
- get wadl for a rest service.
- initialize responsibility context.
- edi get code conversions
- list inbound transactions.
- retrieve code conversion mappings.
- list outbound transactions.
- get trading partner by id.
- retrieve outbound edi transactions.
- edi extract outbound transaction
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
