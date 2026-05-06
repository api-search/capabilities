---
categories: []
consumed_apis: []
description: Unified DeFi trading workflow for swap execution, gasless orders, liquidity management, and token discovery. Used by DeFi developers, trading bots, and portfolio managers building on the Uniswap protocol. Combines quote generation, swap execution, UniswapX gasless orders, LP position management, and execution planning into a single capability surface.
layout: capability
name: Uniswap DeFi Trading
operations:
- description: Check if token approval is required for a swap
  method: POST
  name: check-token-approval
  path: /v1/approvals
- description: Get the best quote for a token swap or cross-chain bridge
  method: POST
  name: get-swap-quote
  path: /v1/quotes
- description: Generate calldata for executing a token swap
  method: POST
  name: create-swap-transaction
  path: /v1/swaps
- description: Get the status of a swap or bridge transaction
  method: GET
  name: get-swap-status
  path: /v1/swaps
- description: Submit a gasless UniswapX intent order
  method: POST
  name: create-gasless-order
  path: /v1/orders
- description: List gasless orders with optional filtering
  method: GET
  name: list-gasless-orders
  path: /v1/orders
- description: Get a limit order quote for a token pair
  method: POST
  name: get-limit-order-quote
  path: /v1/limit-orders
- description: Create a new V3 or V4 liquidity position
  method: POST
  name: create-lp-position
  path: /v1/lp-positions
- description: Add liquidity to an existing position
  method: PUT
  name: increase-lp-position
  path: /v1/lp-positions
- description: Remove liquidity from an existing position
  method: DELETE
  name: decrease-lp-position
  path: /v1/lp-positions
- description: Claim accumulated fees from an LP position
  method: POST
  name: claim-lp-fees
  path: /v1/lp-positions
- description: Fetch information about a Uniswap pool
  method: POST
  name: get-pool-information
  path: /v1/pools
- description: List tokens available for swapping or bridging
  method: GET
  name: list-swappable-tokens
  path: /v1/tokens
personas: []
provider_name: Uniswap
provider_slug: uniswap
search_terms:
- token discovery for swaps and bridges
- get quotes for token swaps and bridges
- provide and manage concentrated liquidity in uniswap pools
- unified defi trading workflow combining swap quotes, execution, gasless orders, lp management, and token discovery for developers building on uniswap.
- add more liquidity to an existing lp position
- liquidity provider position lifecycle management
- blockchain
- decrease lp position
- gasless uniswapx order management
- limit order quotes and execution
- get swap quote
- generate the calldata needed to execute a token swap on-chain
- list gasless orders with optional filtering
- submit a gasless uniswapx intent order where fillers compete to fill it
- liquidity providers managing concentrated lp positions on v3/v4, optimizing fee income through active position management (create, rebalance, close).
- claim accumulated trading fees from a liquidity position
- check token approval
- list tokens available for swapping or bridging
- check if token approval is required for a swap
- remove liquidity from an existing position
- get limit order quote
- create a new concentrated liquidity position in a uniswap v3 or v4 pool
- list gasless orders
- remove liquidity from an lp position
- create gasless order
- list uniswapx gasless orders for a wallet with optional status filtering
- trading
- check the status of a submitted swap or bridge transaction
- liquidity provider
- get the best quote for a token swap or cross-chain bridge
- create swap transaction
- check token approval status before executing swaps
- execute token swaps
- submit a gasless uniswapx intent order
- get pool information
- get the best available quote for swapping one token for another, including gas estimates and price impact
- Trading Bot Engineer
- get detailed information about a uniswap liquidity pool including tvl, fees, and tick data
- DeFi Developer
- add liquidity to an existing position
- list all tokens available for swapping or bridging from a given token
- engineers building automated trading systems, arbitrage bots, and mev strategies using uniswap's liquidity. uses gasless uniswapx orders and limit orders for automated execution.
- create lp position
- liquidity pool discovery and information
- LP Manager
- create a new v3 or v4 liquidity position
- decentralized exchange
- generate calldata for executing a token swap
- fetch information about a uniswap pool
- check if a wallet has sufficient token approval for a swap transaction
- cryptocurrency
- get a quote for a limit order that executes when price conditions are met
- exchange tokens at best available price via amm routing
- uniswap
- claim lp fees
- sign-and-submit intent orders filled by competing fillers
- list swappable tokens
- defi
- swaps
- increase lp position
- liquidity
- get a limit order quote for a token pair
- developers building dapps, wallets, and defi protocols that embed uniswap swap functionality. primarily uses the trading api for quotes and swap execution.
- get the status of a swap or bridge transaction
- get swap status
- claim accumulated fees from an lp position
slug: defi-trading
source_filename: defi-trading.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Uniswap DeFi Trading\n  description: Unified DeFi trading workflow for swap execution, gasless orders, liquidity management, and token discovery.\n    Used by DeFi developers, trading bots, and portfolio managers building on the Uniswap protocol. Combines quote generation,\n    swap execution, UniswapX gasless orders, LP position management, and execution planning into a single capability surface.\n  tags:\n  - Uniswap\n  - DeFi\n  - Blockchain\n  - Swaps\n  - Liquidity Provider\n  - Trading\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UNISWAP_API_KEY: UNISWAP_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: uniswap-trading\n    baseUri: https://trade-api.gateway.uniswap.org/v1\n    description: Uniswap Labs trading API for token swaps, bridging, and LP management.\n    authentication:\n      type: apikey\n      key: x-api-key\n      value: '{{UNISWAP_API_KEY}}'\n      placement:\
  \ header\n    resources:\n    - name: approvals\n      path: /check_approval\n      description: Token approval management\n      operations:\n      - name: check-token-approval\n        method: POST\n        description: Check if token approval is required for a transaction\n        inputParameters:\n        - name: walletAddress\n          in: body\n          type: string\n          required: true\n          description: Ethereum address initiating the transaction\n        - name: token\n          in: body\n          type: string\n          required: true\n          description: Token contract address\n        - name: amount\n          in: body\n          type: string\n          required: true\n          description: Token amount in base units\n        - name: chainId\n          in: body\n          type: integer\n          required: false\n          description: 'Blockchain chain ID (default: 1 for Ethereum)'\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: quotes\n      path: /quote\n      description: Swap quote generation\n      operations:\n      - name: get-swap-quote\n        method: POST\n        description: Get a quote for a swap, bridge, or wrap/unwrap\n        inputParameters:\n        - name: type\n          in: body\n          type: string\n          required: true\n          description: 'Quote type: EXACT_INPUT or EXACT_OUTPUT'\n        - name: tokenInChainId\n          in: body\n          type: integer\n          required: true\n          description: Source chain ID\n        - name: tokenOutChainId\n          in: body\n          type: integer\n          required: true\n          description: Destination chain ID\n        - name: tokenIn\n          in: body\n          type: string\n          required: true\n          description: Input token contract address\n        - name: tokenOut\n          in: body\n          type: string\n          required: true\n  \
  \        description: Output token contract address\n        - name: amount\n          in: body\n          type: string\n          required: true\n          description: Token amount in base units\n        - name: slippageTolerance\n          in: body\n          type: string\n          required: false\n          description: Slippage tolerance as a percentage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: swaps\n      path: /swap\n      description: Swap transaction execution\n      operations:\n      - name: create-swap-transaction\n        method: POST\n        description: Generate calldata for a swap transaction\n        inputParameters:\n        - name: type\n          in: body\n          type: string\n          required: true\n          description: 'Swap type: EXACT_INPUT or EXACT_OUTPUT'\n        - name: tokenIn\n          in: body\n          type: string\n          required: true\n   \
  \       description: Input token address\n        - name: tokenOut\n          in: body\n          type: string\n          required: true\n          description: Output token address\n        - name: amount\n          in: body\n          type: string\n          required: true\n          description: Token amount in base units\n        - name: swapper\n          in: body\n          type: string\n          required: true\n          description: Swapper wallet address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-swap-status\n        method: GET\n        description: Get the status of a swap or bridge transaction\n        inputParameters:\n        - name: txHash\n          in: query\n          type: string\n          required: false\n          description: Transaction hash to look up\n        - name: chainId\n          in: query\n          type: integer\n          required: false\n         \
  \ description: Chain ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /order\n      description: Gasless UniswapX order management\n      operations:\n      - name: create-gasless-order\n        method: POST\n        description: Submit a gasless UniswapX intent order\n        inputParameters:\n        - name: encodedOrder\n          in: body\n          type: string\n          required: true\n          description: ABI-encoded signed order\n        - name: orderType\n          in: body\n          type: string\n          required: true\n          description: Order type (e.g., Dutch_V2)\n        - name: signature\n          in: body\n          type: string\n          required: true\n          description: EIP-712 signature over the order\n        - name: chainId\n          in: body\n          type: integer\n          required: true\n          description: Chain ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-gasless-orders\n        method: GET\n        description: Retrieve gasless orders\n        inputParameters:\n        - name: swapper\n          in: query\n          type: string\n          required: false\n          description: Filter by swapper address\n        - name: chainId\n          in: query\n          type: integer\n          required: false\n          description: Filter by chain ID\n        - name: orderStatus\n          in: query\n          type: string\n          required: false\n          description: Filter by order status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: limit-orders\n      path: /limit_order_quote\n      description: Limit order quotes\n      operations:\n      - name: get-limit-order-quote\n        method: POST\n        description: Get a limit\
  \ order quote\n        inputParameters:\n        - name: chainId\n          in: body\n          type: integer\n          required: true\n          description: Chain ID\n        - name: tokenIn\n          in: body\n          type: string\n          required: true\n          description: Input token address\n        - name: tokenOut\n          in: body\n          type: string\n          required: true\n          description: Output token address\n        - name: amount\n          in: body\n          type: string\n          required: true\n          description: Input amount in base units\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lp-positions\n      path: /lp\n      description: Liquidity provider position management\n      operations:\n      - name: check-lp-approval\n        method: POST\n        description: Check LP token approval requirements\n        inputParameters:\n        - name: walletAddress\n\
  \          in: body\n          type: string\n          required: true\n          description: LP wallet address\n        - name: token\n          in: body\n          type: string\n          required: true\n          description: Token address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-lp-position\n        method: POST\n        description: Create a V3 or V4 LP position\n        inputParameters:\n        - name: chainId\n          in: body\n          type: integer\n          required: true\n          description: Chain ID\n        - name: walletAddress\n          in: body\n          type: string\n          required: true\n          description: LP wallet address\n        - name: token0\n          in: body\n          type: string\n          required: true\n          description: First token address\n        - name: token1\n          in: body\n          type: string\n          required:\
  \ true\n          description: Second token address\n        - name: fee\n          in: body\n          type: integer\n          required: true\n          description: Fee tier (e.g., 500 = 0.05%)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: increase-lp-position\n        method: POST\n        description: Increase liquidity in an LP position\n        inputParameters:\n        - name: chainId\n          in: body\n          type: integer\n          required: true\n          description: Chain ID\n        - name: positionId\n          in: body\n          type: string\n          required: true\n          description: LP position token ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: decrease-lp-position\n        method: POST\n        description: Decrease liquidity in an LP position\n        inputParameters:\n\
  \        - name: chainId\n          in: body\n          type: integer\n          required: true\n          description: Chain ID\n        - name: positionId\n          in: body\n          type: string\n          required: true\n          description: LP position token ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: claim-lp-fees\n        method: POST\n        description: Claim accumulated fees from an LP position\n        inputParameters:\n        - name: chainId\n          in: body\n          type: integer\n          required: true\n          description: Chain ID\n        - name: positionId\n          in: body\n          type: string\n          required: true\n          description: LP position token ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-pool-information\n        method: POST\n\
  \        description: Fetch pool information\n        inputParameters:\n        - name: chainId\n          in: body\n          type: integer\n          required: true\n          description: Chain ID\n        - name: token0\n          in: body\n          type: string\n          required: true\n          description: First token address\n        - name: token1\n          in: body\n          type: string\n          required: true\n          description: Second token address\n        - name: fee\n          in: body\n          type: integer\n          required: false\n          description: Fee tier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens\n      path: /swappable_tokens\n      description: Token discovery\n      operations:\n      - name: list-swappable-tokens\n        method: GET\n        description: List bridgable tokens for a given token and chain\n        inputParameters:\n      \
  \  - name: token\n          in: query\n          type: string\n          required: false\n          description: Token address to find bridgable pairs for\n        - name: chainId\n          in: query\n          type: integer\n          required: false\n          description: Source chain ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: execution-plans\n      path: /plan\n      description: Multi-step execution plans\n      operations:\n      - name: create-execution-plan\n        method: POST\n        description: Create a multi-step execution plan\n        inputParameters:\n        - name: chainId\n          in: body\n          type: integer\n          required: true\n          description: Chain ID\n        - name: steps\n          in: body\n          type: array\n          required: true\n          description: Array of steps in the plan\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-execution-plan\n        method: GET\n        description: Retrieve an execution plan by ID\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: Execution plan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: uniswap-defi-trading-api\n    description: Unified REST API for DeFi trading via the Uniswap protocol.\n    resources:\n    - path: /v1/approvals\n      name: approvals\n      description: Check token approval status before executing swaps\n      operations:\n      - method: POST\n        name: check-token-approval\n        description: Check if token approval is required for a swap\n        call: uniswap-trading.check-token-approval\n        with:\n          walletAddress:\
  \ rest.walletAddress\n          token: rest.token\n          amount: rest.amount\n          chainId: rest.chainId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/quotes\n      name: quotes\n      description: Get quotes for token swaps and bridges\n      operations:\n      - method: POST\n        name: get-swap-quote\n        description: Get the best quote for a token swap or cross-chain bridge\n        call: uniswap-trading.get-swap-quote\n        with:\n          type: rest.type\n          tokenInChainId: rest.tokenInChainId\n          tokenOutChainId: rest.tokenOutChainId\n          tokenIn: rest.tokenIn\n          tokenOut: rest.tokenOut\n          amount: rest.amount\n          slippageTolerance: rest.slippageTolerance\n          swapper: rest.swapper\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/swaps\n      name: swaps\n      description: Execute token swaps\n      operations:\n      - method:\
  \ POST\n        name: create-swap-transaction\n        description: Generate calldata for executing a token swap\n        call: uniswap-trading.create-swap-transaction\n        with:\n          type: rest.type\n          tokenIn: rest.tokenIn\n          tokenOut: rest.tokenOut\n          amount: rest.amount\n          swapper: rest.swapper\n          slippageTolerance: rest.slippageTolerance\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-swap-status\n        description: Get the status of a swap or bridge transaction\n        call: uniswap-trading.get-swap-status\n        with:\n          txHash: rest.txHash\n          chainId: rest.chainId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Gasless UniswapX order management\n      operations:\n      - method: POST\n        name: create-gasless-order\n        description: Submit a gasless\
  \ UniswapX intent order\n        call: uniswap-trading.create-gasless-order\n        with:\n          encodedOrder: rest.encodedOrder\n          orderType: rest.orderType\n          signature: rest.signature\n          chainId: rest.chainId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-gasless-orders\n        description: List gasless orders with optional filtering\n        call: uniswap-trading.list-gasless-orders\n        with:\n          swapper: rest.swapper\n          chainId: rest.chainId\n          orderStatus: rest.orderStatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/limit-orders\n      name: limit-orders\n      description: Limit order quotes and execution\n      operations:\n      - method: POST\n        name: get-limit-order-quote\n        description: Get a limit order quote for a token pair\n        call: uniswap-trading.get-limit-order-quote\n        with:\n\
  \          chainId: rest.chainId\n          tokenIn: rest.tokenIn\n          tokenOut: rest.tokenOut\n          amount: rest.amount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lp-positions\n      name: lp-positions\n      description: Liquidity provider position lifecycle management\n      operations:\n      - method: POST\n        name: create-lp-position\n        description: Create a new V3 or V4 liquidity position\n        call: uniswap-trading.create-lp-position\n        with:\n          chainId: rest.chainId\n          walletAddress: rest.walletAddress\n          token0: rest.token0\n          token1: rest.token1\n          fee: rest.fee\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: increase-lp-position\n        description: Add liquidity to an existing position\n        call: uniswap-trading.increase-lp-position\n        with:\n          chainId: rest.chainId\n        \
  \  positionId: rest.positionId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: decrease-lp-position\n        description: Remove liquidity from an existing position\n        call: uniswap-trading.decrease-lp-position\n        with:\n          chainId: rest.chainId\n          positionId: rest.positionId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: claim-lp-fees\n        description: Claim accumulated fees from an LP position\n        call: uniswap-trading.claim-lp-fees\n        with:\n          chainId: rest.chainId\n          positionId: rest.positionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pools\n      name: pools\n      description: Liquidity pool discovery and information\n      operations:\n      - method: POST\n        name: get-pool-information\n        description: Fetch information about a Uniswap\
  \ pool\n        call: uniswap-trading.get-pool-information\n        with:\n          chainId: rest.chainId\n          token0: rest.token0\n          token1: rest.token1\n          fee: rest.fee\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tokens\n      name: tokens\n      description: Token discovery for swaps and bridges\n      operations:\n      - method: GET\n        name: list-swappable-tokens\n        description: List tokens available for swapping or bridging\n        call: uniswap-trading.list-swappable-tokens\n        with:\n          token: rest.token\n          chainId: rest.chainId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: uniswap-defi-trading-mcp\n    transport: http\n    description: MCP server for AI-assisted DeFi trading on Uniswap.\n    tools:\n    - name: check-token-approval\n      description: Check if a wallet has sufficient token approval for\
  \ a swap transaction\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uniswap-trading.check-token-approval\n      with:\n        walletAddress: tools.walletAddress\n        token: tools.token\n        amount: tools.amount\n        chainId: tools.chainId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-swap-quote\n      description: Get the best available quote for swapping one token for another, including gas estimates and price impact\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uniswap-trading.get-swap-quote\n      with:\n        type: tools.type\n        tokenInChainId: tools.tokenInChainId\n        tokenOutChainId: tools.tokenOutChainId\n        tokenIn: tools.tokenIn\n        tokenOut: tools.tokenOut\n        amount: tools.amount\n        slippageTolerance: tools.slippageTolerance\n        swapper: tools.swapper\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ create-swap-transaction\n      description: Generate the calldata needed to execute a token swap on-chain\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: uniswap-trading.create-swap-transaction\n      with:\n        type: tools.type\n        tokenIn: tools.tokenIn\n        tokenOut: tools.tokenOut\n        amount: tools.amount\n        swapper: tools.swapper\n        slippageTolerance: tools.slippageTolerance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-swap-status\n      description: Check the status of a submitted swap or bridge transaction\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uniswap-trading.get-swap-status\n      with:\n        txHash: tools.txHash\n        chainId: tools.chainId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-gasless-order\n      description: Submit a gasless UniswapX intent order where\
  \ fillers compete to fill it\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: uniswap-trading.create-gasless-order\n      with:\n        encodedOrder: tools.encodedOrder\n        orderType: tools.orderType\n        signature: tools.signature\n        chainId: tools.chainId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-gasless-orders\n      description: List UniswapX gasless orders for a wallet with optional status filtering\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uniswap-trading.list-gasless-orders\n      with:\n        swapper: tools.swapper\n        chainId: tools.chainId\n        orderStatus: tools.orderStatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-limit-order-quote\n      description: Get a quote for a limit order that executes when price conditions are met\n      hints:\n        readOnly: true\n       \
  \ openWorld: true\n      call: uniswap-trading.get-limit-order-quote\n      with:\n        chainId: tools.chainId\n        tokenIn: tools.tokenIn\n        tokenOut: tools.tokenOut\n        amount: tools.amount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-swappable-tokens\n      description: List all tokens available for swapping or bridging from a given token\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uniswap-trading.list-swappable-tokens\n      with:\n        token: tools.token\n        chainId: tools.chainId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pool-information\n      description: Get detailed information about a Uniswap liquidity pool including TVL, fees, and tick data\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uniswap-trading.get-pool-information\n      with:\n        chainId: tools.chainId\n        token0: tools.token0\n      \
  \  token1: tools.token1\n        fee: tools.fee\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-lp-position\n      description: Create a new concentrated liquidity position in a Uniswap V3 or V4 pool\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: uniswap-trading.create-lp-position\n      with:\n        chainId: tools.chainId\n        walletAddress: tools.walletAddress\n        token0: tools.token0\n        token1: tools.token1\n        fee: tools.fee\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: increase-lp-position\n      description: Add more liquidity to an existing LP position\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: uniswap-trading.increase-lp-position\n      with:\n        chainId: tools.chainId\n        positionId: tools.positionId\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: decrease-lp-position\n      description: Remove liquidity from an LP position\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: uniswap-trading.decrease-lp-position\n      with:\n        chainId: tools.chainId\n        positionId: tools.positionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: claim-lp-fees\n      description: Claim accumulated trading fees from a liquidity position\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: uniswap-trading.claim-lp-fees\n      with:\n        chainId: tools.chainId\n        positionId: tools.positionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/uniswap/refs/heads/main/capabilities/defi-trading.yaml
tags:
- Uniswap
- DeFi
- Blockchain
- Swaps
- Liquidity Provider
- Trading
tools:
- description: Check if a wallet has sufficient token approval for a swap transaction
  hints:
    openWorld: false
    readOnly: true
  name: check-token-approval
- description: Get the best available quote for swapping one token for another, including gas estimates and price impact
  hints:
    openWorld: true
    readOnly: true
  name: get-swap-quote
- description: Generate the calldata needed to execute a token swap on-chain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-swap-transaction
- description: Check the status of a submitted swap or bridge transaction
  hints:
    openWorld: false
    readOnly: true
  name: get-swap-status
- description: Submit a gasless UniswapX intent order where fillers compete to fill it
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-gasless-order
- description: List UniswapX gasless orders for a wallet with optional status filtering
  hints:
    openWorld: false
    readOnly: true
  name: list-gasless-orders
- description: Get a quote for a limit order that executes when price conditions are met
  hints:
    openWorld: true
    readOnly: true
  name: get-limit-order-quote
- description: List all tokens available for swapping or bridging from a given token
  hints:
    openWorld: true
    readOnly: true
  name: list-swappable-tokens
- description: Get detailed information about a Uniswap liquidity pool including TVL, fees, and tick data
  hints:
    openWorld: false
    readOnly: true
  name: get-pool-information
- description: Create a new concentrated liquidity position in a Uniswap V3 or V4 pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-lp-position
- description: Add more liquidity to an existing LP position
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: increase-lp-position
- description: Remove liquidity from an LP position
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: decrease-lp-position
- description: Claim accumulated trading fees from a liquidity position
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: claim-lp-fees
---
