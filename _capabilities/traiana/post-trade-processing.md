---
categories: []
consumed_apis: []
description: Unified workflow capability for post-trade lifecycle management combining Harmony Trade Processing, CreditLink, and NetLink APIs. Designed for back-office teams, risk managers, and operations staff managing cross-asset trade processing across FX, equities, equity derivatives, and ETD markets.
layout: capability
name: Traiana Post-Trade Processing
operations:
- description: List trades processed through the Harmony network.
  method: GET
  name: list-trades
  path: /v1/trades
- description: Submit a trade for post-trade processing.
  method: POST
  name: submit-trade
  path: /v1/trades
- description: List trade allocations.
  method: GET
  name: list-allocations
  path: /v1/allocations
- description: Submit a trade allocation.
  method: POST
  name: submit-allocation
  path: /v1/allocations
- description: List trade matching results.
  method: GET
  name: list-match-results
  path: /v1/match-results
- description: List credit limits.
  method: GET
  name: list-credit-limits
  path: /v1/credit-limits
- description: Create a new credit limit.
  method: POST
  name: create-credit-limit
  path: /v1/credit-limits
- description: Get current credit utilization.
  method: GET
  name: get-credit-utilization
  path: /v1/credit-utilization
- description: List netting sessions.
  method: GET
  name: list-netting-sessions
  path: /v1/netting-sessions
- description: Create a netting session.
  method: POST
  name: create-netting-session
  path: /v1/netting-sessions
- description: List settlement instructions.
  method: GET
  name: list-settlements
  path: /v1/settlements
- description: List compression runs.
  method: GET
  name: list-compression-runs
  path: /v1/compression-runs
- description: Create a new compression run.
  method: POST
  name: create-compression-run
  path: /v1/compression-runs
personas: []
provider_name: Traiana
provider_slug: traiana
search_terms:
- foreign exchange
- list trades processed through the harmony network with filtering by asset class and status.
- post-trade processing
- submit a trade for post-trade processing.
- submit trade
- list settlement instructions for payment and delivery scheduling.
- trade matching
- credit limit management and monitoring.
- list netting sessions
- list allocations
- get credit utilization
- settlement
- list netting sessions.
- create an intraday netting session to reduce bilateral settlement obligations.
- list match results
- list trade matching results.
- current credit utilization.
- get current credit utilization.
- trade compression
- fintech
- credit risk
- settlement instruction management.
- list compression runs.
- submit allocation
- list all credit limits across prime-brokered, cleared, and bilateral counterparty relationships.
- list credit limits
- trade matching results.
- create credit limit
- create a new compression run.
- create compression run
- get details of a specific trade including its matching status and lifecycle state.
- confirm a matched trade to complete the confirmation workflow.
- confirm trade
- list credit limit breach events for risk oversight.
- get results of a completed netting session showing net positions and settlement obligations.
- list credit breaches
- netting
- list trade matching results to monitor confirmation status.
- get netting results
- list trade allocations for block trade splitting and reporting.
- create netting session
- list trades
- intraday netting sessions.
- trade submission and lifecycle management.
- get trade
- list settlements
- list settlement instructions.
- list compression runs
- create a new credit limit.
- create a netting session.
- initiate a trade compression run to reduce notional exposure and counterparty count.
- submit a trade allocation.
- list trade allocations.
- trade compression runs.
- submit a new trade for post-trade processing through the harmony network.
- risk management
- trade allocation management.
- list trades processed through the harmony network.
- list credit limits.
- get current credit utilization showing available headroom across all counterparties.
slug: post-trade-processing
source_filename: post-trade-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Traiana Post-Trade Processing\n  description: Unified workflow capability for post-trade lifecycle management combining Harmony Trade Processing, CreditLink,\n    and NetLink APIs. Designed for back-office teams, risk managers, and operations staff managing cross-asset trade processing\n    across FX, equities, equity derivatives, and ETD markets.\n  tags:\n  - Credit Risk\n  - Fintech\n  - Foreign Exchange\n  - Netting\n  - Post-Trade Processing\n  - Settlement\n  - Trade Compression\n  - Trade Matching\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRAIANA_API_KEY: TRAIANA_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: traiana-trade-processing\n    baseUri: https://api.traiana.com/harmony/v1\n    description: Traiana Harmony Trade Processing API for post-trade workflows.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{env.TRAIANA_API_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: trades\n      path: /trades\n      description: Trade submission, retrieval, and confirmation.\n      operations:\n      - name: list-trades\n        method: GET\n        description: List trades processed through the Harmony network.\n        inputParameters:\n        - name: assetClass\n          in: query\n          type: string\n          required: false\n          description: Filter by asset class.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by trade status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: submit-trade\n        method: POST\n        description: Submit a new trade for processing.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-trade\n       \
  \ method: GET\n        description: Get details of a specific trade.\n        inputParameters:\n        - name: tradeId\n          in: path\n          type: string\n          required: true\n          description: Trade identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: confirm-trade\n        method: POST\n        description: Confirm a matched trade.\n        inputParameters:\n        - name: tradeId\n          in: path\n          type: string\n          required: true\n          description: Trade identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allocations\n      path: /allocations\n      description: Trade allocation management.\n      operations:\n      - name: list-allocations\n        method: GET\n        description: List trade allocations.\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: submit-allocation\n        method: POST\n        description: Submit a new trade allocation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: give-ups\n      path: /give-ups\n      description: Give-up message management.\n      operations:\n      - name: list-give-ups\n        method: GET\n        description: List give-up messages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: submit-give-up\n        method: POST\n        description: Submit a give-up message.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: match-results\n      path: /match-results\n      description: Trade matching results.\n      operations:\n\
  \      - name: list-match-results\n        method: GET\n        description: List trade matching results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  - type: http\n    namespace: traiana-creditlink\n    baseUri: https://api.traiana.com/creditlink/v1\n    description: Traiana Harmony CreditLink API for real-time credit risk management.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{env.TRAIANA_API_KEY}}'\n      placement: header\n    resources:\n    - name: credit-limits\n      path: /credit-limits\n      description: Credit limit management.\n      operations:\n      - name: list-credit-limits\n        method: GET\n        description: List all credit limits.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-credit-limit\n        method: POST\n        description: Create a\
  \ new credit limit.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-credit-limit\n        method: GET\n        description: Get details of a specific credit limit.\n        inputParameters:\n        - name: limitId\n          in: path\n          type: string\n          required: true\n          description: Credit limit identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-credit-limit\n        method: PUT\n        description: Update an existing credit limit.\n        inputParameters:\n        - name: limitId\n          in: path\n          type: string\n          required: true\n          description: Credit limit identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: breaches\n      path:\
  \ /breaches\n      description: Credit limit breach reporting and monitoring.\n      operations:\n      - name: report-limit-breach\n        method: POST\n        description: Report a credit limit breach.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-credit-limit-breaches\n        method: GET\n        description: List credit limit breach events.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: designation-notices\n      path: /designation-notices\n      description: Designation notice management.\n      operations:\n      - name: list-designation-notices\n        method: GET\n        description: List designation notices.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-designation-notice\n        method:\
  \ POST\n        description: Create a designation notice.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: utilization\n      path: /utilization\n      description: Credit utilization monitoring.\n      operations:\n      - name: get-credit-utilization\n        method: GET\n        description: Get current credit utilization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: traiana-netlink\n    baseUri: https://api.traiana.com/netlink/v1\n    description: Traiana Harmony NetLink API for netting and settlement.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{env.TRAIANA_API_KEY}}'\n      placement: header\n    resources:\n    - name: netting-sessions\n      path: /netting-sessions\n      description: Netting session management.\n      operations:\n      - name:\
  \ list-netting-sessions\n        method: GET\n        description: List netting sessions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-netting-session\n        method: POST\n        description: Create a new netting session.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-netting-session\n        method: GET\n        description: Get netting session details.\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n          description: Netting session identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-netting-results\n        method: GET\n        description: Get results from a netting session.\n        inputParameters:\n\
  \        - name: sessionId\n          in: path\n          type: string\n          required: true\n          description: Netting session identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: settlements\n      path: /settlements\n      description: Settlement instruction management.\n      operations:\n      - name: list-settlements\n        method: GET\n        description: List settlement instructions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-settlement\n        method: GET\n        description: Get settlement instruction details.\n        inputParameters:\n        - name: settlementId\n          in: path\n          type: string\n          required: true\n          description: Settlement identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: compression\n      path: /compression-runs\n      description: Trade compression run management.\n      operations:\n      - name: list-compression-runs\n        method: GET\n        description: List trade compression runs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-compression-run\n        method: POST\n        description: Create a new trade compression run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: traiana-post-trade-api\n    description: Unified REST API for Traiana post-trade processing, credit risk, netting, and settlement operations.\n    resources:\n    - path: /v1/trades\n      name: trades\n      description: Trade submission and lifecycle management.\n      operations:\n  \
  \    - method: GET\n        name: list-trades\n        description: List trades processed through the Harmony network.\n        call: traiana-trade-processing.list-trades\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: submit-trade\n        description: Submit a trade for post-trade processing.\n        call: traiana-trade-processing.submit-trade\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/allocations\n      name: allocations\n      description: Trade allocation management.\n      operations:\n      - method: GET\n        name: list-allocations\n        description: List trade allocations.\n        call: traiana-trade-processing.list-allocations\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: submit-allocation\n        description: Submit a trade allocation.\n        call: traiana-trade-processing.submit-allocation\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/match-results\n      name: match-results\n      description: Trade matching results.\n      operations:\n      - method: GET\n        name: list-match-results\n        description: List trade matching results.\n        call: traiana-trade-processing.list-match-results\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/credit-limits\n      name: credit-limits\n      description: Credit limit management and monitoring.\n      operations:\n      - method: GET\n        name: list-credit-limits\n        description: List credit limits.\n        call: traiana-creditlink.list-credit-limits\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-credit-limit\n        description: Create a new credit limit.\n        call: traiana-creditlink.create-credit-limit\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/credit-utilization\n      name: credit-utilization\n      description: Current credit utilization.\n      operations:\n      - method: GET\n        name: get-credit-utilization\n        description: Get current credit utilization.\n        call: traiana-creditlink.get-credit-utilization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/netting-sessions\n      name: netting-sessions\n      description: Intraday netting sessions.\n      operations:\n      - method: GET\n        name: list-netting-sessions\n        description: List netting sessions.\n        call: traiana-netlink.list-netting-sessions\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-netting-session\n        description: Create a netting session.\n        call: traiana-netlink.create-netting-session\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /v1/settlements\n      name: settlements\n      description: Settlement instruction management.\n      operations:\n      - method: GET\n        name: list-settlements\n        description: List settlement instructions.\n        call: traiana-netlink.list-settlements\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/compression-runs\n      name: compression-runs\n      description: Trade compression runs.\n      operations:\n      - method: GET\n        name: list-compression-runs\n        description: List compression runs.\n        call: traiana-netlink.list-compression-runs\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-compression-run\n        description: Create a new compression run.\n        call: traiana-netlink.create-compression-run\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: traiana-post-trade-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted Traiana post-trade processing, risk management, and settlement operations.\n    tools:\n    - name: list-trades\n      description: List trades processed through the Harmony network with filtering by asset class and status.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traiana-trade-processing.list-trades\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: submit-trade\n      description: Submit a new trade for post-trade processing through the Harmony network.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: traiana-trade-processing.submit-trade\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trade\n      description: Get details of a specific trade including its matching status and lifecycle state.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traiana-trade-processing.get-trade\n\
  \      with:\n        tradeId: tools.tradeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: confirm-trade\n      description: Confirm a matched trade to complete the confirmation workflow.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: traiana-trade-processing.confirm-trade\n      with:\n        tradeId: tools.tradeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-allocations\n      description: List trade allocations for block trade splitting and reporting.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traiana-trade-processing.list-allocations\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-match-results\n      description: List trade matching results to monitor confirmation status.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traiana-trade-processing.list-match-results\n      outputParameters:\n\
  \      - type: array\n        mapping: $.\n    - name: list-credit-limits\n      description: List all credit limits across prime-brokered, cleared, and bilateral counterparty relationships.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traiana-creditlink.list-credit-limits\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-credit-utilization\n      description: Get current credit utilization showing available headroom across all counterparties.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traiana-creditlink.get-credit-utilization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-credit-breaches\n      description: List credit limit breach events for risk oversight.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traiana-creditlink.list-credit-limit-breaches\n      outputParameters:\n      - type: array\n        mapping: $.\n \
  \   - name: create-netting-session\n      description: Create an intraday netting session to reduce bilateral settlement obligations.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: traiana-netlink.create-netting-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-netting-results\n      description: Get results of a completed netting session showing net positions and settlement obligations.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traiana-netlink.get-netting-results\n      with:\n        sessionId: tools.sessionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-settlements\n      description: List settlement instructions for payment and delivery scheduling.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traiana-netlink.list-settlements\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name:\
  \ create-compression-run\n      description: Initiate a trade compression run to reduce notional exposure and counterparty count.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: traiana-netlink.create-compression-run\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/traiana/refs/heads/main/capabilities/post-trade-processing.yaml
tags:
- Credit Risk
- Fintech
- Foreign Exchange
- Netting
- Post-Trade Processing
- Settlement
- Trade Compression
- Trade Matching
tools:
- description: List trades processed through the Harmony network with filtering by asset class and status.
  hints:
    idempotent: true
    readOnly: true
  name: list-trades
- description: Submit a new trade for post-trade processing through the Harmony network.
  hints:
    idempotent: false
    readOnly: false
  name: submit-trade
- description: Get details of a specific trade including its matching status and lifecycle state.
  hints:
    idempotent: true
    readOnly: true
  name: get-trade
- description: Confirm a matched trade to complete the confirmation workflow.
  hints:
    idempotent: false
    readOnly: false
  name: confirm-trade
- description: List trade allocations for block trade splitting and reporting.
  hints:
    idempotent: true
    readOnly: true
  name: list-allocations
- description: List trade matching results to monitor confirmation status.
  hints:
    idempotent: true
    readOnly: true
  name: list-match-results
- description: List all credit limits across prime-brokered, cleared, and bilateral counterparty relationships.
  hints:
    idempotent: true
    readOnly: true
  name: list-credit-limits
- description: Get current credit utilization showing available headroom across all counterparties.
  hints:
    idempotent: true
    readOnly: true
  name: get-credit-utilization
- description: List credit limit breach events for risk oversight.
  hints:
    idempotent: true
    readOnly: true
  name: list-credit-breaches
- description: Create an intraday netting session to reduce bilateral settlement obligations.
  hints:
    idempotent: false
    readOnly: false
  name: create-netting-session
- description: Get results of a completed netting session showing net positions and settlement obligations.
  hints:
    idempotent: true
    readOnly: true
  name: get-netting-results
- description: List settlement instructions for payment and delivery scheduling.
  hints:
    idempotent: true
    readOnly: true
  name: list-settlements
- description: Initiate a trade compression run to reduce notional exposure and counterparty count.
  hints:
    idempotent: false
    readOnly: false
  name: create-compression-run
---
