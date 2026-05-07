---
categories: []
consumed_apis: []
description: 'The Bloomberg API (BLPAPI) is the official client-side library for accessing Bloomberg market data, reference data, news, and analytics services across Desktop API, Server API, and B-PIPE delivery models. > **Important — protocol shape**: The native BLPAPI is **NOT** an HTTP/REST > API. It is a binary, session-oriented, message-passing API delivered over > the Bloomberg Network using the BLPAPI client SDK (C, C++, Java, .NET, Python). > It uses a request/response paradigm and a subscription paradigm rather than > stateless HTTP verbs. > > This OpenAPI document is a **logical mapping** of the B'
layout: capability
name: Bloomberg API (BLPAPI)
operations:
- description: Request reference data for one or more securities
  method: POST
  name: referencedatarequest
  path: /refdata/ReferenceDataRequest
- description: Request end-of-day historical data over a date range
  method: POST
  name: historicaldatarequest
  path: /refdata/HistoricalDataRequest
- description: Request tick-by-tick history for a single security
  method: POST
  name: intradaytickrequest
  path: /refdata/IntradayTickRequest
- description: Request intraday bar (OHLCV) history for a single security
  method: POST
  name: intradaybarrequest
  path: /refdata/IntradayBarRequest
- description: Request portfolio positions and member data
  method: POST
  name: portfoliodatarequest
  path: /refdata/PortfolioDataRequest
- description: Request data for a Bloomberg Equity Screening (EQS) screen
  method: POST
  name: beqsrequest
  path: /refdata/BeqsRequest
- description: Subscribe to streaming market data for one or more securities
  method: POST
  name: marketdatasubscribe
  path: /mktdata/subscribe
- description: Subscribe to streaming intraday bar data
  method: POST
  name: marketbarsubscribe
  path: /mktbar/subscribe
- description: Subscribe to streaming Custom VWAP for an equity
  method: POST
  name: customvwapsubscribe
  path: /mktvwap/subscribe
- description: Get field metadata by id (mnemonic or alpha-numeric identifier)
  method: POST
  name: fieldinforequest
  path: /apiflds/FieldInfoRequest
- description: Full-text search Bloomberg fields by mnemonic / description
  method: POST
  name: fieldsearchrequest
  path: /apiflds/FieldSearchRequest
- description: Search Bloomberg fields with results grouped by category tree
  method: POST
  name: categorizedfieldsearchrequest
  path: /apiflds/CategorizedFieldSearchRequest
- description: Subscribe to a Bloomberg GPGX page
  method: POST
  name: pagedatasubscribe
  path: /pagedata/subscribe
- description: Request a technical analysis study (historical, intraday, or real-time)
  method: POST
  name: studyrequest
  path: /tasvc/StudyRequest
- description: Authorize a Bloomberg user against an IP address (Server API) or token (B-PIPE)
  method: POST
  name: authorizationrequest
  path: /apiauth/AuthorizationRequest
- description: Check whether a UUID is logged into Bloomberg Anywhere at an IP
  method: POST
  name: logonstatusrequest
  path: /apiauth/LogonStatusRequest
- description: List exchange entitlements for a Bloomberg user
  method: POST
  name: userentitlementsrequest
  path: /apiauth/UserEntitlementsRequest
- description: Get exchange entitlements for one or more securities
  method: POST
  name: securityentitlementsrequest
  path: /apiauth/SecurityEntitlementsRequest
- description: Request an authorization token for a Server API application (B-PIPE)
  method: POST
  name: authorizationtokenrequest
  path: /apiauth/AuthorizationTokenRequest
- description: Look up securities by free-text query
  method: POST
  name: securitylookuprequest
  path: /instruments/SecurityLookupRequest
- description: Look up Bloomberg yield curves
  method: POST
  name: curvelookuprequest
  path: /instruments/CurveLookupRequest
- description: Look up government securities
  method: POST
  name: govtlookuprequest
  path: /instruments/GovtLookupRequest
personas: []
provider_name: Bloomberg APIs
provider_slug: bloomberg-apis
search_terms:
- analytics
- check whether a uuid is logged into bloomberg anywhere at an ip
- bloomberg
- fieldinforequest
- get field metadata by id (mnemonic or alpha-numeric identifier)
- search bloomberg fields with results grouped by category tree
- apis
- list exchange entitlements for a bloomberg user
- look up government securities
- request data for a bloomberg equity screening (eqs) screen
- subscribe to a bloomberg gpgx page
- look up securities by free-text query
- studyrequest
- request reference data for one or more securities
- request tick-by-tick history for a single security
- request portfolio positions and member data
- request a technical analysis study (historical, intraday, or real-time)
- api
- curvelookuprequest
- terminal
- securityentitlementsrequest
- beqsrequest
- get exchange entitlements for one or more securities
- logonstatusrequest
- fieldsearchrequest
- referencedatarequest
- request intraday bar (ohlcv) history for a single security
- userentitlementsrequest
- authorizationtokenrequest
- authorizationrequest
- financial data
- pagedatasubscribe
- request an authorization token for a server api application (b-pipe)
- full-text search bloomberg fields by mnemonic / description
- subscribe to streaming market data for one or more securities
- subscribe to streaming intraday bar data
- authorize a bloomberg user against an ip address (server api) or token (b-pipe)
- historicaldatarequest
- look up bloomberg yield curves
- intradaybarrequest
- marketbarsubscribe
- securitylookuprequest
- portfoliodatarequest
- subscribe to streaming custom vwap for an equity
- marketdatasubscribe
- customvwapsubscribe
- govtlookuprequest
- market data
- categorizedfieldsearchrequest
- intradaytickrequest
- request end-of-day historical data over a date range
- news
slug: bloomberg-apis-capability
source_filename: bloomberg-apis-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bloomberg API (BLPAPI)\n  description: 'The Bloomberg API (BLPAPI) is the official client-side library for accessing Bloomberg market data, reference\n    data, news, and analytics services across Desktop API, Server API, and B-PIPE delivery models. > **Important — protocol\n    shape**: The native BLPAPI is **NOT** an HTTP/REST > API. It is a binary, session-oriented, message-passing API delivered\n    over > the Bloomberg Network using the BLPAPI client SDK (C, C++, Java, .NET, Python). > It uses a request/response paradigm\n    and a subscription paradigm rather than > stateless HTTP verbs. > > This OpenAPI document is a **logical mapping** of\n    the B'\n  tags:\n  - Bloomberg\n  - Apis\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bloomberg-apis\n    baseUri: blpapi+session://localhost\n    description: Bloomberg API (BLPAPI) HTTP API.\n    authentication:\n\
  \      type: apikey\n      in: header\n      name: X-BLPAPI-Session\n      value: '{{BLOOMBERG_APIS_TOKEN}}'\n    resources:\n    - name: refdata-referencedatarequest\n      path: /refdata/ReferenceDataRequest\n      operations:\n      - name: referencedatarequest\n        method: POST\n        description: Request reference data for one or more securities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refdata-historicaldatarequest\n      path: /refdata/HistoricalDataRequest\n      operations:\n      - name: historicaldatarequest\n        method: POST\n        description: Request end-of-day historical data over a date range\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refdata-intradaytickrequest\n      path: /refdata/IntradayTickRequest\n      operations:\n      - name: intradaytickrequest\n        method:\
  \ POST\n        description: Request tick-by-tick history for a single security\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refdata-intradaybarrequest\n      path: /refdata/IntradayBarRequest\n      operations:\n      - name: intradaybarrequest\n        method: POST\n        description: Request intraday bar (OHLCV) history for a single security\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refdata-portfoliodatarequest\n      path: /refdata/PortfolioDataRequest\n      operations:\n      - name: portfoliodatarequest\n        method: POST\n        description: Request portfolio positions and member data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refdata-beqsrequest\n      path: /refdata/BeqsRequest\n     \
  \ operations:\n      - name: beqsrequest\n        method: POST\n        description: Request data for a Bloomberg Equity Screening (EQS) screen\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mktdata-subscribe\n      path: /mktdata/subscribe\n      operations:\n      - name: marketdatasubscribe\n        method: POST\n        description: Subscribe to streaming market data for one or more securities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mktbar-subscribe\n      path: /mktbar/subscribe\n      operations:\n      - name: marketbarsubscribe\n        method: POST\n        description: Subscribe to streaming intraday bar data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mktvwap-subscribe\n      path: /mktvwap/subscribe\n\
  \      operations:\n      - name: customvwapsubscribe\n        method: POST\n        description: Subscribe to streaming Custom VWAP for an equity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apiflds-fieldinforequest\n      path: /apiflds/FieldInfoRequest\n      operations:\n      - name: fieldinforequest\n        method: POST\n        description: Get field metadata by id (mnemonic or alpha-numeric identifier)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apiflds-fieldsearchrequest\n      path: /apiflds/FieldSearchRequest\n      operations:\n      - name: fieldsearchrequest\n        method: POST\n        description: Full-text search Bloomberg fields by mnemonic / description\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: apiflds-categorizedfieldsearchrequest\n      path: /apiflds/CategorizedFieldSearchRequest\n      operations:\n      - name: categorizedfieldsearchrequest\n        method: POST\n        description: Search Bloomberg fields with results grouped by category tree\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pagedata-subscribe\n      path: /pagedata/subscribe\n      operations:\n      - name: pagedatasubscribe\n        method: POST\n        description: Subscribe to a Bloomberg GPGX page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasvc-studyrequest\n      path: /tasvc/StudyRequest\n      operations:\n      - name: studyrequest\n        method: POST\n        description: Request a technical analysis study (historical, intraday, or real-time)\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: apiauth-authorizationrequest\n      path: /apiauth/AuthorizationRequest\n      operations:\n      - name: authorizationrequest\n        method: POST\n        description: Authorize a Bloomberg user against an IP address (Server API) or token (B-PIPE)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apiauth-logonstatusrequest\n      path: /apiauth/LogonStatusRequest\n      operations:\n      - name: logonstatusrequest\n        method: POST\n        description: Check whether a UUID is logged into Bloomberg Anywhere at an IP\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apiauth-userentitlementsrequest\n      path: /apiauth/UserEntitlementsRequest\n      operations:\n      - name: userentitlementsrequest\n        method: POST\n\
  \        description: List exchange entitlements for a Bloomberg user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apiauth-securityentitlementsrequest\n      path: /apiauth/SecurityEntitlementsRequest\n      operations:\n      - name: securityentitlementsrequest\n        method: POST\n        description: Get exchange entitlements for one or more securities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apiauth-authorizationtokenrequest\n      path: /apiauth/AuthorizationTokenRequest\n      operations:\n      - name: authorizationtokenrequest\n        method: POST\n        description: Request an authorization token for a Server API application (B-PIPE)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instruments-securitylookuprequest\n\
  \      path: /instruments/SecurityLookupRequest\n      operations:\n      - name: securitylookuprequest\n        method: POST\n        description: Look up securities by free-text query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instruments-curvelookuprequest\n      path: /instruments/CurveLookupRequest\n      operations:\n      - name: curvelookuprequest\n        method: POST\n        description: Look up Bloomberg yield curves\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instruments-govtlookuprequest\n      path: /instruments/GovtLookupRequest\n      operations:\n      - name: govtlookuprequest\n        method: POST\n        description: Look up government securities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \ exposes:\n  - type: rest\n    port: 8080\n    namespace: bloomberg-apis-rest\n    description: REST adapter for Bloomberg API (BLPAPI).\n    resources:\n    - path: /refdata/ReferenceDataRequest\n      name: referencedatarequest\n      operations:\n      - method: POST\n        name: referencedatarequest\n        description: Request reference data for one or more securities\n        call: bloomberg-apis.referencedatarequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /refdata/HistoricalDataRequest\n      name: historicaldatarequest\n      operations:\n      - method: POST\n        name: historicaldatarequest\n        description: Request end-of-day historical data over a date range\n        call: bloomberg-apis.historicaldatarequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /refdata/IntradayTickRequest\n      name: intradaytickrequest\n      operations:\n      - method: POST\n        name: intradaytickrequest\n\
  \        description: Request tick-by-tick history for a single security\n        call: bloomberg-apis.intradaytickrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /refdata/IntradayBarRequest\n      name: intradaybarrequest\n      operations:\n      - method: POST\n        name: intradaybarrequest\n        description: Request intraday bar (OHLCV) history for a single security\n        call: bloomberg-apis.intradaybarrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /refdata/PortfolioDataRequest\n      name: portfoliodatarequest\n      operations:\n      - method: POST\n        name: portfoliodatarequest\n        description: Request portfolio positions and member data\n        call: bloomberg-apis.portfoliodatarequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /refdata/BeqsRequest\n      name: beqsrequest\n      operations:\n      - method: POST\n    \
  \    name: beqsrequest\n        description: Request data for a Bloomberg Equity Screening (EQS) screen\n        call: bloomberg-apis.beqsrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mktdata/subscribe\n      name: marketdatasubscribe\n      operations:\n      - method: POST\n        name: marketdatasubscribe\n        description: Subscribe to streaming market data for one or more securities\n        call: bloomberg-apis.marketdatasubscribe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mktbar/subscribe\n      name: marketbarsubscribe\n      operations:\n      - method: POST\n        name: marketbarsubscribe\n        description: Subscribe to streaming intraday bar data\n        call: bloomberg-apis.marketbarsubscribe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mktvwap/subscribe\n      name: customvwapsubscribe\n      operations:\n      - method: POST\n\
  \        name: customvwapsubscribe\n        description: Subscribe to streaming Custom VWAP for an equity\n        call: bloomberg-apis.customvwapsubscribe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apiflds/FieldInfoRequest\n      name: fieldinforequest\n      operations:\n      - method: POST\n        name: fieldinforequest\n        description: Get field metadata by id (mnemonic or alpha-numeric identifier)\n        call: bloomberg-apis.fieldinforequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apiflds/FieldSearchRequest\n      name: fieldsearchrequest\n      operations:\n      - method: POST\n        name: fieldsearchrequest\n        description: Full-text search Bloomberg fields by mnemonic / description\n        call: bloomberg-apis.fieldsearchrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apiflds/CategorizedFieldSearchRequest\n      name: categorizedfieldsearchrequest\n\
  \      operations:\n      - method: POST\n        name: categorizedfieldsearchrequest\n        description: Search Bloomberg fields with results grouped by category tree\n        call: bloomberg-apis.categorizedfieldsearchrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pagedata/subscribe\n      name: pagedatasubscribe\n      operations:\n      - method: POST\n        name: pagedatasubscribe\n        description: Subscribe to a Bloomberg GPGX page\n        call: bloomberg-apis.pagedatasubscribe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tasvc/StudyRequest\n      name: studyrequest\n      operations:\n      - method: POST\n        name: studyrequest\n        description: Request a technical analysis study (historical, intraday, or real-time)\n        call: bloomberg-apis.studyrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apiauth/AuthorizationRequest\n\
  \      name: authorizationrequest\n      operations:\n      - method: POST\n        name: authorizationrequest\n        description: Authorize a Bloomberg user against an IP address (Server API) or token (B-PIPE)\n        call: bloomberg-apis.authorizationrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apiauth/LogonStatusRequest\n      name: logonstatusrequest\n      operations:\n      - method: POST\n        name: logonstatusrequest\n        description: Check whether a UUID is logged into Bloomberg Anywhere at an IP\n        call: bloomberg-apis.logonstatusrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apiauth/UserEntitlementsRequest\n      name: userentitlementsrequest\n      operations:\n      - method: POST\n        name: userentitlementsrequest\n        description: List exchange entitlements for a Bloomberg user\n        call: bloomberg-apis.userentitlementsrequest\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /apiauth/SecurityEntitlementsRequest\n      name: securityentitlementsrequest\n      operations:\n      - method: POST\n        name: securityentitlementsrequest\n        description: Get exchange entitlements for one or more securities\n        call: bloomberg-apis.securityentitlementsrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apiauth/AuthorizationTokenRequest\n      name: authorizationtokenrequest\n      operations:\n      - method: POST\n        name: authorizationtokenrequest\n        description: Request an authorization token for a Server API application (B-PIPE)\n        call: bloomberg-apis.authorizationtokenrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instruments/SecurityLookupRequest\n      name: securitylookuprequest\n      operations:\n      - method: POST\n        name: securitylookuprequest\n        description:\
  \ Look up securities by free-text query\n        call: bloomberg-apis.securitylookuprequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instruments/CurveLookupRequest\n      name: curvelookuprequest\n      operations:\n      - method: POST\n        name: curvelookuprequest\n        description: Look up Bloomberg yield curves\n        call: bloomberg-apis.curvelookuprequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instruments/GovtLookupRequest\n      name: govtlookuprequest\n      operations:\n      - method: POST\n        name: govtlookuprequest\n        description: Look up government securities\n        call: bloomberg-apis.govtlookuprequest\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bloomberg-apis-mcp\n    transport: http\n    description: MCP adapter for Bloomberg API (BLPAPI) for AI agent use.\n    tools:\n    - name:\
  \ referencedatarequest\n      description: Request reference data for one or more securities\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.referencedatarequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: historicaldatarequest\n      description: Request end-of-day historical data over a date range\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.historicaldatarequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: intradaytickrequest\n      description: Request tick-by-tick history for a single security\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.intradaytickrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: intradaybarrequest\n      description: Request intraday\
  \ bar (OHLCV) history for a single security\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.intradaybarrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: portfoliodatarequest\n      description: Request portfolio positions and member data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.portfoliodatarequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: beqsrequest\n      description: Request data for a Bloomberg Equity Screening (EQS) screen\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.beqsrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketdatasubscribe\n      description: Subscribe to streaming market data for one or more securities\n      hints:\n \
  \       readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.marketdatasubscribe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: marketbarsubscribe\n      description: Subscribe to streaming intraday bar data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.marketbarsubscribe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: customvwapsubscribe\n      description: Subscribe to streaming Custom VWAP for an equity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.customvwapsubscribe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fieldinforequest\n      description: Get field metadata by id (mnemonic or alpha-numeric identifier)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: bloomberg-apis.fieldinforequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fieldsearchrequest\n      description: Full-text search Bloomberg fields by mnemonic / description\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.fieldsearchrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: categorizedfieldsearchrequest\n      description: Search Bloomberg fields with results grouped by category tree\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.categorizedfieldsearchrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pagedatasubscribe\n      description: Subscribe to a Bloomberg GPGX page\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.pagedatasubscribe\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: studyrequest\n      description: Request a technical analysis study (historical, intraday, or real-time)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.studyrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authorizationrequest\n      description: Authorize a Bloomberg user against an IP address (Server API) or token (B-PIPE)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.authorizationrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: logonstatusrequest\n      description: Check whether a UUID is logged into Bloomberg Anywhere at an IP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.logonstatusrequest\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: userentitlementsrequest\n      description: List exchange entitlements for a Bloomberg user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.userentitlementsrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: securityentitlementsrequest\n      description: Get exchange entitlements for one or more securities\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.securityentitlementsrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authorizationtokenrequest\n      description: Request an authorization token for a Server API application (B-PIPE)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.authorizationtokenrequest\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: securitylookuprequest\n      description: Look up securities by free-text query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.securitylookuprequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: curvelookuprequest\n      description: Look up Bloomberg yield curves\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.curvelookuprequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: govtlookuprequest\n      description: Look up government securities\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-apis.govtlookuprequest\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BLOOMBERG_APIS_TOKEN: BLOOMBERG_APIS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bloomberg-apis/refs/heads/main/capabilities/bloomberg-apis-capability.yaml
tags:
- Bloomberg
- Apis
- API
tools:
- description: Request reference data for one or more securities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: referencedatarequest
- description: Request end-of-day historical data over a date range
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: historicaldatarequest
- description: Request tick-by-tick history for a single security
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: intradaytickrequest
- description: Request intraday bar (OHLCV) history for a single security
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: intradaybarrequest
- description: Request portfolio positions and member data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: portfoliodatarequest
- description: Request data for a Bloomberg Equity Screening (EQS) screen
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: beqsrequest
- description: Subscribe to streaming market data for one or more securities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: marketdatasubscribe
- description: Subscribe to streaming intraday bar data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: marketbarsubscribe
- description: Subscribe to streaming Custom VWAP for an equity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: customvwapsubscribe
- description: Get field metadata by id (mnemonic or alpha-numeric identifier)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fieldinforequest
- description: Full-text search Bloomberg fields by mnemonic / description
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fieldsearchrequest
- description: Search Bloomberg fields with results grouped by category tree
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: categorizedfieldsearchrequest
- description: Subscribe to a Bloomberg GPGX page
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pagedatasubscribe
- description: Request a technical analysis study (historical, intraday, or real-time)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: studyrequest
- description: Authorize a Bloomberg user against an IP address (Server API) or token (B-PIPE)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authorizationrequest
- description: Check whether a UUID is logged into Bloomberg Anywhere at an IP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: logonstatusrequest
- description: List exchange entitlements for a Bloomberg user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: userentitlementsrequest
- description: Get exchange entitlements for one or more securities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: securityentitlementsrequest
- description: Request an authorization token for a Server API application (B-PIPE)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authorizationtokenrequest
- description: Look up securities by free-text query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: securitylookuprequest
- description: Look up Bloomberg yield curves
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: curvelookuprequest
- description: Look up government securities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: govtlookuprequest
---
