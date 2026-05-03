---
categories: []
consumed_apis:
- uniswap-trading
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
- check the status of a submitted swap or bridge transaction
- check if a wallet has sufficient token approval for a swap transaction
- limit order quotes and execution
- get pool information
- claim accumulated fees from an lp position
- get the best available quote for swapping one token for another, including gas estimates and price impact
- liquidity provider position lifecycle management
- cryptocurrency
- decrease lp position
- list gasless orders
- add more liquidity to an existing lp position
- claim accumulated trading fees from a liquidity position
- get swap quote
- unified defi trading workflow combining swap quotes, execution, gasless orders, lp management, and token discovery for developers building on uniswap.
- swaps
- remove liquidity from an existing position
- list all tokens available for swapping or bridging from a given token
- exchange tokens at best available price via amm routing
- developers building dapps, wallets, and defi protocols that embed uniswap swap functionality. primarily uses the trading api for quotes and swap execution.
- get the status of a swap or bridge transaction
- provide and manage concentrated liquidity in uniswap pools
- defi
- list swappable tokens
- create a new v3 or v4 liquidity position
- DeFi Developer
- liquidity pool discovery and information
- claim lp fees
- list uniswapx gasless orders for a wallet with optional status filtering
- Trading Bot Engineer
- get quotes for token swaps and bridges
- trading
- check token approval status before executing swaps
- uniswap
- get a quote for a limit order that executes when price conditions are met
- liquidity
- create swap transaction
- get a limit order quote for a token pair
- execute token swaps
- LP Manager
- get limit order quote
- liquidity providers managing concentrated lp positions on v3/v4, optimizing fee income through active position management (create, rebalance, close).
- get detailed information about a uniswap liquidity pool including tvl, fees, and tick data
- get the best quote for a token swap or cross-chain bridge
- generate calldata for executing a token swap
- add liquidity to an existing position
- sign-and-submit intent orders filled by competing fillers
- list tokens available for swapping or bridging
- submit a gasless uniswapx intent order where fillers compete to fill it
- get swap status
- remove liquidity from an lp position
- submit a gasless uniswapx intent order
- gasless uniswapx order management
- increase lp position
- decentralized exchange
- generate the calldata needed to execute a token swap on-chain
- liquidity provider
- check token approval
- check if token approval is required for a swap
- create a new concentrated liquidity position in a uniswap v3 or v4 pool
- engineers building automated trading systems, arbitrage bots, and mev strategies using uniswap's liquidity. uses gasless uniswapx orders and limit orders for automated execution.
- token discovery for swaps and bridges
- create gasless order
- list gasless orders with optional filtering
- fetch information about a uniswap pool
- blockchain
- create lp position
slug: defi-trading
source_filename: defi-trading.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Uniswap DeFi Trading\"\n  description: >-\n    Unified DeFi trading workflow for swap execution, gasless orders, liquidity management,\n    and token discovery. Used by DeFi developers, trading bots, and portfolio managers\n    building on the Uniswap protocol. Combines quote generation, swap execution,\n    UniswapX gasless orders, LP position management, and execution planning into a\n    single capability surface.\n  tags:\n    - Uniswap\n    - DeFi\n    - Blockchain\n    - Swaps\n    - Liquidity Provider\n    - Trading\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNISWAP_API_KEY: UNISWAP_API_KEY\n\ncapability:\n  consumes:\n    - import: uniswap-trading\n      location: ./shared/trading-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: uniswap-defi-trading-api\n      description: \"Unified REST API for DeFi trading via the Uniswap protocol.\"\
  \n      resources:\n        - path: /v1/approvals\n          name: approvals\n          description: \"Check token approval status before executing swaps\"\n          operations:\n            - method: POST\n              name: check-token-approval\n              description: \"Check if token approval is required for a swap\"\n              call: \"uniswap-trading.check-token-approval\"\n              with:\n                walletAddress: \"rest.walletAddress\"\n                token: \"rest.token\"\n                amount: \"rest.amount\"\n                chainId: \"rest.chainId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/quotes\n          name: quotes\n          description: \"Get quotes for token swaps and bridges\"\n          operations:\n            - method: POST\n              name: get-swap-quote\n              description: \"Get the best quote for a token swap or cross-chain bridge\"\n           \
  \   call: \"uniswap-trading.get-swap-quote\"\n              with:\n                type: \"rest.type\"\n                tokenInChainId: \"rest.tokenInChainId\"\n                tokenOutChainId: \"rest.tokenOutChainId\"\n                tokenIn: \"rest.tokenIn\"\n                tokenOut: \"rest.tokenOut\"\n                amount: \"rest.amount\"\n                slippageTolerance: \"rest.slippageTolerance\"\n                swapper: \"rest.swapper\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/swaps\n          name: swaps\n          description: \"Execute token swaps\"\n          operations:\n            - method: POST\n              name: create-swap-transaction\n              description: \"Generate calldata for executing a token swap\"\n              call: \"uniswap-trading.create-swap-transaction\"\n              with:\n                type: \"rest.type\"\n                tokenIn: \"rest.tokenIn\"\n     \
  \           tokenOut: \"rest.tokenOut\"\n                amount: \"rest.amount\"\n                swapper: \"rest.swapper\"\n                slippageTolerance: \"rest.slippageTolerance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-swap-status\n              description: \"Get the status of a swap or bridge transaction\"\n              call: \"uniswap-trading.get-swap-status\"\n              with:\n                txHash: \"rest.txHash\"\n                chainId: \"rest.chainId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders\n          name: orders\n          description: \"Gasless UniswapX order management\"\n          operations:\n            - method: POST\n              name: create-gasless-order\n              description: \"Submit a gasless UniswapX intent order\"\n              call: \"uniswap-trading.create-gasless-order\"\
  \n              with:\n                encodedOrder: \"rest.encodedOrder\"\n                orderType: \"rest.orderType\"\n                signature: \"rest.signature\"\n                chainId: \"rest.chainId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-gasless-orders\n              description: \"List gasless orders with optional filtering\"\n              call: \"uniswap-trading.list-gasless-orders\"\n              with:\n                swapper: \"rest.swapper\"\n                chainId: \"rest.chainId\"\n                orderStatus: \"rest.orderStatus\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/limit-orders\n          name: limit-orders\n          description: \"Limit order quotes and execution\"\n          operations:\n            - method: POST\n              name: get-limit-order-quote\n  \
  \            description: \"Get a limit order quote for a token pair\"\n              call: \"uniswap-trading.get-limit-order-quote\"\n              with:\n                chainId: \"rest.chainId\"\n                tokenIn: \"rest.tokenIn\"\n                tokenOut: \"rest.tokenOut\"\n                amount: \"rest.amount\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/lp-positions\n          name: lp-positions\n          description: \"Liquidity provider position lifecycle management\"\n          operations:\n            - method: POST\n              name: create-lp-position\n              description: \"Create a new V3 or V4 liquidity position\"\n              call: \"uniswap-trading.create-lp-position\"\n              with:\n                chainId: \"rest.chainId\"\n                walletAddress: \"rest.walletAddress\"\n                token0: \"rest.token0\"\n                token1: \"rest.token1\"\n   \
  \             fee: \"rest.fee\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: increase-lp-position\n              description: \"Add liquidity to an existing position\"\n              call: \"uniswap-trading.increase-lp-position\"\n              with:\n                chainId: \"rest.chainId\"\n                positionId: \"rest.positionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: decrease-lp-position\n              description: \"Remove liquidity from an existing position\"\n              call: \"uniswap-trading.decrease-lp-position\"\n              with:\n                chainId: \"rest.chainId\"\n                positionId: \"rest.positionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n  \
  \            name: claim-lp-fees\n              description: \"Claim accumulated fees from an LP position\"\n              call: \"uniswap-trading.claim-lp-fees\"\n              with:\n                chainId: \"rest.chainId\"\n                positionId: \"rest.positionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pools\n          name: pools\n          description: \"Liquidity pool discovery and information\"\n          operations:\n            - method: POST\n              name: get-pool-information\n              description: \"Fetch information about a Uniswap pool\"\n              call: \"uniswap-trading.get-pool-information\"\n              with:\n                chainId: \"rest.chainId\"\n                token0: \"rest.token0\"\n                token1: \"rest.token1\"\n                fee: \"rest.fee\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n\n        - path: /v1/tokens\n          name: tokens\n          description: \"Token discovery for swaps and bridges\"\n          operations:\n            - method: GET\n              name: list-swappable-tokens\n              description: \"List tokens available for swapping or bridging\"\n              call: \"uniswap-trading.list-swappable-tokens\"\n              with:\n                token: \"rest.token\"\n                chainId: \"rest.chainId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: uniswap-defi-trading-mcp\n      transport: http\n      description: \"MCP server for AI-assisted DeFi trading on Uniswap.\"\n      tools:\n        - name: check-token-approval\n          description: \"Check if a wallet has sufficient token approval for a swap transaction\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uniswap-trading.check-token-approval\"\
  \n          with:\n            walletAddress: \"tools.walletAddress\"\n            token: \"tools.token\"\n            amount: \"tools.amount\"\n            chainId: \"tools.chainId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-swap-quote\n          description: \"Get the best available quote for swapping one token for another, including gas estimates and price impact\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uniswap-trading.get-swap-quote\"\n          with:\n            type: \"tools.type\"\n            tokenInChainId: \"tools.tokenInChainId\"\n            tokenOutChainId: \"tools.tokenOutChainId\"\n            tokenIn: \"tools.tokenIn\"\n            tokenOut: \"tools.tokenOut\"\n            amount: \"tools.amount\"\n            slippageTolerance: \"tools.slippageTolerance\"\n            swapper: \"tools.swapper\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: create-swap-transaction\n          description: \"Generate the calldata needed to execute a token swap on-chain\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"uniswap-trading.create-swap-transaction\"\n          with:\n            type: \"tools.type\"\n            tokenIn: \"tools.tokenIn\"\n            tokenOut: \"tools.tokenOut\"\n            amount: \"tools.amount\"\n            swapper: \"tools.swapper\"\n            slippageTolerance: \"tools.slippageTolerance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-swap-status\n          description: \"Check the status of a submitted swap or bridge transaction\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uniswap-trading.get-swap-status\"\n          with:\n            txHash: \"tools.txHash\"\n\
  \            chainId: \"tools.chainId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-gasless-order\n          description: \"Submit a gasless UniswapX intent order where fillers compete to fill it\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"uniswap-trading.create-gasless-order\"\n          with:\n            encodedOrder: \"tools.encodedOrder\"\n            orderType: \"tools.orderType\"\n            signature: \"tools.signature\"\n            chainId: \"tools.chainId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-gasless-orders\n          description: \"List UniswapX gasless orders for a wallet with optional status filtering\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uniswap-trading.list-gasless-orders\"\n      \
  \    with:\n            swapper: \"tools.swapper\"\n            chainId: \"tools.chainId\"\n            orderStatus: \"tools.orderStatus\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-limit-order-quote\n          description: \"Get a quote for a limit order that executes when price conditions are met\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"uniswap-trading.get-limit-order-quote\"\n          with:\n            chainId: \"tools.chainId\"\n            tokenIn: \"tools.tokenIn\"\n            tokenOut: \"tools.tokenOut\"\n            amount: \"tools.amount\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-swappable-tokens\n          description: \"List all tokens available for swapping or bridging from a given token\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"uniswap-trading.list-swappable-tokens\"\n          with:\n            token: \"tools.token\"\n            chainId: \"tools.chainId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-pool-information\n          description: \"Get detailed information about a Uniswap liquidity pool including TVL, fees, and tick data\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uniswap-trading.get-pool-information\"\n          with:\n            chainId: \"tools.chainId\"\n            token0: \"tools.token0\"\n            token1: \"tools.token1\"\n            fee: \"tools.fee\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-lp-position\n          description: \"Create a new concentrated liquidity position in a Uniswap V3 or V4 pool\"\n          hints:\n            readOnly: false\n            destructive: false\n          \
  \  idempotent: false\n          call: \"uniswap-trading.create-lp-position\"\n          with:\n            chainId: \"tools.chainId\"\n            walletAddress: \"tools.walletAddress\"\n            token0: \"tools.token0\"\n            token1: \"tools.token1\"\n            fee: \"tools.fee\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: increase-lp-position\n          description: \"Add more liquidity to an existing LP position\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"uniswap-trading.increase-lp-position\"\n          with:\n            chainId: \"tools.chainId\"\n            positionId: \"tools.positionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: decrease-lp-position\n          description: \"Remove liquidity from an LP position\"\n          hints:\n            readOnly:\
  \ false\n            destructive: true\n            idempotent: true\n          call: \"uniswap-trading.decrease-lp-position\"\n          with:\n            chainId: \"tools.chainId\"\n            positionId: \"tools.positionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: claim-lp-fees\n          description: \"Claim accumulated trading fees from a liquidity position\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"uniswap-trading.claim-lp-fees\"\n          with:\n            chainId: \"tools.chainId\"\n            positionId: \"tools.positionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
