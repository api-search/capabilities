---
categories: []
consumed_apis: []
description: Chainlens provides a robust and intuitive platform combining user-friendly exploration with powerful analytics and advanced features. Whether monitoring real-time blockchain transactions, verifying smart contracts, or tracking NFTs, Chainlens ensures you have all the necessary tools at your fingertips.
layout: capability
name: Chainlens
operations:
- description: Chainlens Retrieve transactions by address or block.
  method: GET
  name: findtransactions
  path: /transactions
- description: Chainlens Retrieve a transaction by its hash.
  method: GET
  name: gettransaction
  path: /transactions/{transactionHash}
- description: Chainlens Retrieve all internal transactions for this transaction.
  method: GET
  name: getinternalsbytx
  path: /transactions/{transactionHash}/internal-transactions
- description: Chainlens Retrieve all events for this transaction.
  method: GET
  name: gettransactionevents
  path: /transactions/{transactionHash}/events
- description: Chainlens Retrieve token contracts.
  method: GET
  name: findtokens
  path: /tokens
- description: Chainlens Retrieve a token by its address hash.
  method: GET
  name: gettoken
  path: /tokens/{addressHash}
- description: Chainlens Retrieve token contracts by tokenId.
  method: GET
  name: findtokensbytokenid
  path: /tokens/{addressHash}/{tokenId}
- description: Chainlens Retrieve token transactions by token address hash.
  method: GET
  name: findcontracttransactions
  path: /tokens/{addressHash}/transactions
- description: Chainlens Retrieve a list of token holders by token contract address hash.
  method: GET
  name: gettokenholders
  path: /tokens/{addressHash}/holders
- description: Chainlens Retrieve all token events using token address.
  method: GET
  name: gettokenevents
  path: /tokens/{addressHash}/events
- description: Chainlens Retrieve transfers of an ERC777 Token.
  method: GET
  name: finderc777transfers
  path: /tokens/{addressHash}/erc777/transfers
- description: Chainlens Retrieve transfers of an ERC721 Token.
  method: GET
  name: finderc721transfers
  path: /tokens/{addressHash}/erc721/transfers
- description: Chainlens Retrieve transfers of an ERC721 Token.
  method: GET
  name: finderc721transfers-1
  path: /tokens/{addressHash}/erc721/transfers/{tokenId}
- description: Chainlens Retrieve transfers of an ERC223 Token.
  method: GET
  name: finderc20transfers
  path: /tokens/{addressHash}/erc223/transfers
- description: Chainlens Retrieve transfers of an ERC20 Token.
  method: GET
  name: finderc20transfers-1
  path: /tokens/{addressHash}/erc20/transfers
- description: Chainlens Retrieve transfers of an ERC1155 Token.
  method: GET
  name: finderc1155transfers
  path: /tokens/{addressHash}/erc1155/transfers
- description: Chainlens Retrieve transfers of an ERC1155 Token.
  method: GET
  name: finderc1155transfers-1
  path: /tokens/{addressHash}/erc1155/transfers/{tokenId}
- description: GET /token/{addressHash}
  method: GET
  name: gettoken-1
  path: /token/{addressHash}
- description: GET /token-type/{addressHash}
  method: GET
  name: gettokentype
  path: /token-type/{addressHash}
- description: Chainlens Retrieve blocks, transactions, accounts by hash.
  method: GET
  name: search
  path: /search/
- description: Chainlens Retrieve blocks, transactions, accounts by hash.
  method: GET
  name: search-1
  path: /search
- description: Chainlens Retrieve ERC3643 tokens.
  method: GET
  name: findtokens-1
  path: /rwas
- description: Chainlens Retrieve a ERC3643 by its address hash.
  method: GET
  name: gettoken-2
  path: /rwas/{addressHash}
- description: Chainlens Retrieve token metadata for a given token contract address and token id.
  method: GET
  name: gettokenmetadata
  path: /rwas/{addressHash}/{tokenId}/metadata
- description: Chainlens Retrieve a list of token holders by token contract address hash.
  method: GET
  name: gettokenholders-1
  path: /rwas/{addressHash}/holders
- description: Chainlens Retrieve transfers of an ERC3643 Token.
  method: GET
  name: finderc3643transfers
  path: /rwas/{addressHash}/erc3643/transfers
- description: Chainlens Node details.
  method: GET
  name: details
  path: /node/details
- description: Chainlens Retrieve NFTs.
  method: GET
  name: findtokens-2
  path: /nfts
- description: Chainlens Retrieve a NFT by its address hash.
  method: GET
  name: gettoken-3
  path: /nfts/{addressHash}
- description: Chainlens Retrieve NFT contracts by tokenId.
  method: GET
  name: findtokensbytokenid-1
  path: /nfts/{addressHash}/{tokenId}
- description: Chainlens Retrieve token metadata for a given token contract address and token id.
  method: GET
  name: gettokenmetadata-1
  path: /nfts/{addressHash}/{tokenId}/metadata
- description: Chainlens Retrieve a list of token holders by token contract address hash.
  method: GET
  name: gettokenholders-2
  path: /nfts/{addressHash}/holders
- description: Chainlens Retrieve transfers of an ERC721 Token.
  method: GET
  name: finderc721transfers-2
  path: /nfts/{addressHash}/erc721/transfers
- description: Chainlens Retrieve transfers of an ERC1155 Token.
  method: GET
  name: finderc1155transfers-2
  path: /nfts/{addressHash}/erc1155/transfers
- description: Chainlens Retrieve all NFTs with Metadata.
  method: GET
  name: findnftcollections
  path: /nfts/{addressHash}/collections
- description: Chainlens Retrieve metadata.
  method: GET
  name: getmetadata
  path: /metadata/{swarmHash}
- description: Chainlens list contracts by swarmhash
  method: GET
  name: findcontractsbyswarmhash
  path: /metadata/{fileId}/contracts
- description: Chainlens Retrieve Accounts
  method: GET
  name: findaccounts
  path: /mappings
- description: GET /mappings/{id}
  method: GET
  name: getaccount
  path: /mappings/{id}
- description: Chainlens Retrieve internal transactions by address.
  method: GET
  name: findtransactions-1
  path: /internal-transactions
- description: Chainlens Gas price oracle.
  method: GET
  name: gaspriceinfo
  path: /gas/price
- description: Chainlens Retrieve all events.
  method: GET
  name: getevents
  path: /events
- description: Chainlens Download ABI for a verified contract
  method: GET
  name: downloadabi
  path: /download/abi/{contractAddress}
- description: Chainlens Retrieve total number of different transactions types
  method: GET
  name: gettotals
  path: /dashboard/transactions/totals
- description: Chainlens Retrieve total number of different transactions types
  method: GET
  name: gettotals-1
  path: /dashboard/transactions/totals/{period}
- description: Chainlens Retrieve total number of Contracts, Tokens and Transactions.
  method: GET
  name: getdashboardtotals
  path: /dashboard/totals
- description: Chainlens Retrieve total number of different token types
  method: GET
  name: gettokentotals
  path: /dashboard/tokens/totals
- description: Chainlens Retrieve contracts.
  method: GET
  name: findcontracts
  path: /contracts
- description: Chainlens Retrieve a contract by its address hash.
  method: GET
  name: getcontract
  path: /contracts/{addressHash}
- description: Chainlens Retrieve contract transactions by its address hash.
  method: GET
  name: findcontracttransactions-1
  path: /contracts/{addressHash}/transactions
- description: Chainlens Retrieve contract internal transactions by its address hash.
  method: GET
  name: findcontracttransactions-2
  path: /contracts/{addressHash}/internal-transactions
- description: Chainlens Retrieve all events for this contract.
  method: GET
  name: getcontractevents
  path: /contracts/{addressHash}/events
- description: Chainlens Retrieves bytecodes for a deployed contract.
  method: GET
  name: getcontractbytecode
  path: /contracts/{addressHash}/bytecode
- description: GET /content-type/get
  method: GET
  name: getcontenttype
  path: /content-type/get
- description: Chainlens frontend configuration.
  method: GET
  name: frontendconfiguration
  path: /configuration/frontend
- description: Chainlens Get a list of all recommended collections
  method: GET
  name: getrecommendedtokensbyprojects
  path: /collections/recommended
- description: Chainlens Retrieve blocks.
  method: GET
  name: findblocks
  path: /blocks
- description: Chainlens Retrieve a block by its hash or height.
  method: GET
  name: getblock
  path: /blocks/{blockHash}
- description: Chainlens Retrieve all transactions for this block.
  method: GET
  name: getblocktransactions
  path: /blocks/{blockHash}/transactions
- description: GET /address/{addressHash}
  method: GET
  name: getaddress
  path: /address/{addressHash}
personas: []
provider_name: Chainlens
provider_slug: chainlens
search_terms:
- findtokensbytokenid
- finderc721transfers 1
- chainlens retrieve contract internal transactions by its address hash.
- chainlens retrieve token transactions by token address hash.
- details
- analytics
- chainlens retrieve a list of token holders by token contract address hash.
- smart contracts
- getblock
- chainlens retrieve accounts
- gettokenevents
- findaccounts
- frontendconfiguration
- chainlens retrieve a token by its address hash.
- finderc20transfers
- findtokensbytokenid 1
- ethereum
- chainlens retrieve token contracts by tokenid.
- gettokenholders 1
- chainlens retrieve nfts.
- api
- findblocks
- search
- getcontract
- chainlens retrieve all internal transactions for this transaction.
- gettokentotals
- chainlens retrieve metadata.
- chainlens retrieve token metadata for a given token contract address and token id.
- chainlens retrieve erc3643 tokens.
- chainlens retrieve transactions by address or block.
- chainlens retrieve a transaction by its hash.
- chainlens retrieve all events for this transaction.
- gettokenholders
- web3
- finderc721transfers
- finderc1155transfers
- blockchain
- findcontracttransactions 1
- findtransactions 1
- chainlens retrieve all nfts with metadata.
- finderc3643transfers
- findtokens 2
- chainlens gas price oracle.
- chainlens retrieve all events.
- nfts
- getcontractevents
- chainlens node details.
- gettoken 3
- finderc721transfers 2
- gettransactionevents
- chainlens retrieve internal transactions by address.
- get /mappings/{id}
- chainlens retrieve transfers of an erc20 token.
- chainlens retrieve transfers of an erc223 token.
- chainlens retrieve a contract by its address hash.
- chainlens retrieve a erc3643 by its address hash.
- chainlens retrieve blocks.
- findtokens 1
- getcontenttype
- findcontracttransactions
- getaddress
- getinternalsbytx
- findnftcollections
- findcontractsbyswarmhash
- downloadabi
- chainlens retrieve a nft by its address hash.
- getmetadata
- chainlens retrieve nft contracts by tokenid.
- get /token/{addresshash}
- chainlens retrieve all transactions for this block.
- chainlens retrieve all token events using token address.
- chainlens retrieve transfers of an erc777 token.
- evm
- chainlens download abi for a verified contract
- gettokentype
- findcontracts
- chainlens retrieve total number of different transactions types
- getblocktransactions
- getevents
- chainlens retrieve transfers of an erc1155 token.
- chainlens retrieve transfers of an erc3643 token.
- chainlens list contracts by swarmhash
- chainlens frontend configuration.
- finderc1155transfers 2
- get /content-type/get
- chainlens retrieve all events for this contract.
- chainlens
- findcontracttransactions 2
- chainlens retrieve total number of different token types
- getcontractbytecode
- gettoken 2
- gettransaction
- chainlens retrieve a block by its hash or height.
- chainlens retrieve contract transactions by its address hash.
- chainlens retrieve blocks, transactions, accounts by hash.
- gettoken 1
- chainlens retrieves bytecodes for a deployed contract.
- chainlens get a list of all recommended collections
- gettokenholders 2
- block explorer
- get /address/{addresshash}
- get /token-type/{addresshash}
- search 1
- getaccount
- findtransactions
- gettotals 1
- gettotals
- finderc20transfers 1
- chainlens retrieve contracts.
- gettokenmetadata 1
- chainlens retrieve transfers of an erc721 token.
- getdashboardtotals
- chainlens retrieve token contracts.
- cryptocurrencies
- gettokenmetadata
- chainlens retrieve total number of contracts, tokens and transactions.
- finderc777transfers
- findtokens
- gaspriceinfo
- finderc1155transfers 1
- defi
- getrecommendedtokensbyprojects
- gettoken
slug: chainlens-capability
source_filename: chainlens-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Chainlens\n  description: Chainlens provides a robust and intuitive platform combining user-friendly exploration with powerful analytics\n    and advanced features. Whether monitoring real-time blockchain transactions, verifying smart contracts, or tracking NFTs,\n    Chainlens ensures you have all the necessary tools at your fingertips.\n  tags:\n  - Chainlens\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: chainlens\n    baseUri: https://api.example.com\n    description: Chainlens HTTP API.\n    resources:\n    - name: transactions\n      path: /transactions\n      operations:\n      - name: findtransactions\n        method: GET\n        description: Chainlens Retrieve transactions by address or block.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: transactions-transactionhash\n      path: /transactions/{transactionHash}\n      operations:\n      - name: gettransaction\n        method: GET\n        description: Chainlens Retrieve a transaction by its hash.\n        inputParameters:\n        - name: transactionHash\n          in: path\n          type: string\n          required: true\n          description: The hash identifying the transaction.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-transactionhash-internal-transactio\n      path: /transactions/{transactionHash}/internal-transactions\n      operations:\n      - name: getinternalsbytx\n        method: GET\n        description: Chainlens Retrieve all internal transactions for this transaction.\n        inputParameters:\n        - name: transactionHash\n          in: path\n          type: string\n\
  \          required: true\n          description: The transaction hash identifying the transaction that contains the events.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-transactionhash-events\n      path: /transactions/{transactionHash}/events\n      operations:\n      - name: gettransactionevents\n        method: GET\n        description: Chainlens Retrieve all events for this transaction.\n        inputParameters:\n        - name: transactionHash\n          in: path\n          type: string\n          required: true\n          description: The transaction hash identifying the transaction that contains the events.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: tokens\n      path: /tokens\n      operations:\n      - name: findtokens\n        method: GET\n        description: Chainlens Retrieve token contracts.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens-addresshash\n      path: /tokens/{addressHash}\n      operations:\n      - name: gettoken\n        method: GET\n        description: Chainlens Retrieve a token by its address hash.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens-addresshash-tokenid\n\
  \      path: /tokens/{addressHash}/{tokenId}\n      operations:\n      - name: findtokensbytokenid\n        method: GET\n        description: Chainlens Retrieve token contracts by tokenId.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        - name: tokenId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens-addresshash-transactions\n      path: /tokens/{addressHash}/transactions\n      operations:\n      - name: findcontracttransactions\n        method: GET\n        description: Chainlens Retrieve token transactions by token address hash.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description:\
  \ The address hash identifying the token.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens-addresshash-holders\n      path: /tokens/{addressHash}/holders\n      operations:\n      - name: gettokenholders\n        method: GET\n        description: Chainlens Retrieve a list of token holders by token contract address hash.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens-addresshash-events\n      path: /tokens/{addressHash}/events\n\
  \      operations:\n      - name: gettokenevents\n        method: GET\n        description: Chainlens Retrieve all token events using token address.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens-addresshash-erc777-transfers\n      path: /tokens/{addressHash}/erc777/transfers\n      operations:\n      - name: finderc777transfers\n        method: GET\n        description: Chainlens Retrieve transfers of an ERC777 Token.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token.\n   \
  \     - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens-addresshash-erc721-transfers\n      path: /tokens/{addressHash}/erc721/transfers\n      operations:\n      - name: finderc721transfers\n        method: GET\n        description: Chainlens Retrieve transfers of an ERC721 Token.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens-addresshash-erc721-transfers-tokenid\n      path: /tokens/{addressHash}/erc721/transfers/{tokenId}\n    \
  \  operations:\n      - name: finderc721transfers-1\n        method: GET\n        description: Chainlens Retrieve transfers of an ERC721 Token.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token.\n        - name: tokenId\n          in: path\n          type: string\n          required: true\n          description: The token id identifying the token.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens-addresshash-erc223-transfers\n      path: /tokens/{addressHash}/erc223/transfers\n      operations:\n      - name: finderc20transfers\n        method: GET\n        description: Chainlens Retrieve transfers of an ERC223 Token.\n        inputParameters:\n        - name: addressHash\n\
  \          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens-addresshash-erc20-transfers\n      path: /tokens/{addressHash}/erc20/transfers\n      operations:\n      - name: finderc20transfers-1\n        method: GET\n        description: Chainlens Retrieve transfers of an ERC20 Token.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: tokens-addresshash-erc1155-transfers\n      path: /tokens/{addressHash}/erc1155/transfers\n      operations:\n      - name: finderc1155transfers\n        method: GET\n        description: Chainlens Retrieve transfers of an ERC1155 Token.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens-addresshash-erc1155-transfers-tokenid\n      path: /tokens/{addressHash}/erc1155/transfers/{tokenId}\n      operations:\n      - name: finderc1155transfers-1\n        method: GET\n        description: Chainlens Retrieve transfers of an ERC1155 Token.\n        inputParameters:\n        - name: addressHash\n\
  \          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token.\n        - name: tokenId\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: token-addresshash\n      path: /token/{addressHash}\n      operations:\n      - name: gettoken-1\n        method: GET\n        description: GET /token/{addressHash}\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n    - name: token-type-addresshash\n      path: /token-type/{addressHash}\n      operations:\n      - name: gettokentype\n        method: GET\n        description: GET /token-type/{addressHash}\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search/\n      operations:\n      - name: search\n        method: GET\n        description: Chainlens Retrieve blocks, transactions, accounts by hash.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: The search query string.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: search\n      path: /search\n      operations:\n      - name: search-1\n        method: GET\n        description: Chainlens Retrieve blocks, transactions, accounts by hash.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: The search query string.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rwas\n      path: /rwas\n      operations:\n      - name: findtokens-1\n        method: GET\n        description: Chainlens Retrieve ERC3643 tokens.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rwas-addresshash\n      path: /rwas/{addressHash}\n      operations:\n      - name:\
  \ gettoken-2\n        method: GET\n        description: Chainlens Retrieve a ERC3643 by its address hash.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rwas-addresshash-tokenid-metadata\n      path: /rwas/{addressHash}/{tokenId}/metadata\n      operations:\n      - name: gettokenmetadata\n        method: GET\n        description: Chainlens Retrieve token metadata for a given token contract address and token id.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        - name: tokenId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rwas-addresshash-holders\n      path: /rwas/{addressHash}/holders\n      operations:\n      - name: gettokenholders-1\n        method: GET\n        description: Chainlens Retrieve a list of token holders by token contract address hash.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rwas-addresshash-erc3643-transfers\n      path: /rwas/{addressHash}/erc3643/transfers\n      operations:\n      - name: finderc3643transfers\n        method: GET\n        description: Chainlens Retrieve transfers of an ERC3643\
  \ Token.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-details\n      path: /node/details\n      operations:\n      - name: details\n        method: GET\n        description: Chainlens Node details.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nfts\n      path: /nfts\n      operations:\n      - name: findtokens-2\n        method: GET\n        description: Chainlens Retrieve NFTs.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nfts-addresshash\n      path: /nfts/{addressHash}\n      operations:\n      - name: gettoken-3\n        method: GET\n        description: Chainlens Retrieve a NFT by its address hash.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nfts-addresshash-tokenid\n      path: /nfts/{addressHash}/{tokenId}\n      operations:\n      - name: findtokensbytokenid-1\n        method: GET\n        description: Chainlens Retrieve NFT contracts by tokenId.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address\
  \ hash identifying the contract.\n        - name: tokenId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nfts-addresshash-tokenid-metadata\n      path: /nfts/{addressHash}/{tokenId}/metadata\n      operations:\n      - name: gettokenmetadata-1\n        method: GET\n        description: Chainlens Retrieve token metadata for a given token contract address and token id.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        - name: tokenId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nfts-addresshash-holders\n      path: /nfts/{addressHash}/holders\n\
  \      operations:\n      - name: gettokenholders-2\n        method: GET\n        description: Chainlens Retrieve a list of token holders by token contract address hash.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nfts-addresshash-erc721-transfers\n      path: /nfts/{addressHash}/erc721/transfers\n      operations:\n      - name: finderc721transfers-2\n        method: GET\n        description: Chainlens Retrieve transfers of an ERC721 Token.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying\
  \ the token.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nfts-addresshash-erc1155-transfers\n      path: /nfts/{addressHash}/erc1155/transfers\n      operations:\n      - name: finderc1155transfers-2\n        method: GET\n        description: Chainlens Retrieve transfers of an ERC1155 Token.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the token.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nfts-addresshash-collections\n      path: /nfts/{addressHash}/collections\n      operations:\n\
  \      - name: findnftcollections\n        method: GET\n        description: Chainlens Retrieve all NFTs with Metadata.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-swarmhash\n      path: /metadata/{swarmHash}\n      operations:\n      - name: getmetadata\n        method: GET\n        description: Chainlens Retrieve metadata.\n        inputParameters:\n        - name: swarmHash\n          in: path\n          type: string\n          required: true\n          description: The swarm hash of the metadata.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: metadata-fileid-contracts\n      path: /metadata/{fileId}/contracts\n      operations:\n      - name: findcontractsbyswarmhash\n        method: GET\n        description: Chainlens list contracts by swarmhash\n        inputParameters:\n        - name: fileId\n          in: path\n          type: string\n          required: true\n          description: The file id of the metadata.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mappings\n      path: /mappings\n      operations:\n      - name: findaccounts\n        method: GET\n        description: Chainlens Retrieve Accounts\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: mappings-id\n      path: /mappings/{id}\n      operations:\n      - name: getaccount\n        method: GET\n        description: GET /mappings/{id}\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: internal-transactions\n      path: /internal-transactions\n      operations:\n      - name: findtransactions-1\n        method: GET\n        description: Chainlens Retrieve internal transactions by address.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gas-price\n      path: /gas/price\n      operations:\n      - name: gaspriceinfo\n\
  \        method: GET\n        description: Chainlens Gas price oracle.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      operations:\n      - name: getevents\n        method: GET\n        description: Chainlens Retrieve all events.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: download-abi-contractaddress\n      path: /download/abi/{contractAddress}\n      operations:\n      - name: downloadabi\n        method: GET\n        description: Chainlens Download ABI for a verified contract\n        inputParameters:\n        - name: contractAddress\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: dashboard-transactions-totals\n      path: /dashboard/transactions/totals\n      operations:\n      - name: gettotals\n        method: GET\n        description: Chainlens Retrieve total number of different transactions types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboard-transactions-totals-period\n      path: /dashboard/transactions/totals/{period}\n      operations:\n      - name: gettotals-1\n        method: GET\n        description: Chainlens Retrieve total number of different transactions types\n        inputParameters:\n        - name: period\n          in: path\n          type: string\n          required: true\n        - name: from\n          in: query\n          type: integer\n        - name: to\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: dashboard-totals\n      path: /dashboard/totals\n      operations:\n      - name: getdashboardtotals\n        method: GET\n        description: Chainlens Retrieve total number of Contracts, Tokens and Transactions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboard-tokens-totals\n      path: /dashboard/tokens/totals\n      operations:\n      - name: gettokentotals\n        method: GET\n        description: Chainlens Retrieve total number of different token types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts\n      path: /contracts\n      operations:\n      - name: findcontracts\n        method: GET\n        description: Chainlens Retrieve contracts.\n        inputParameters:\n        - name: query\n      \
  \    in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts-addresshash\n      path: /contracts/{addressHash}\n      operations:\n      - name: getcontract\n        method: GET\n        description: Chainlens Retrieve a contract by its address hash.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts-addresshash-transactions\n      path: /contracts/{addressHash}/transactions\n      operations:\n      - name: findcontracttransactions-1\n        method: GET\n        description: Chainlens Retrieve contract transactions by its address hash.\n        inputParameters:\n\
  \        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts-addresshash-internal-transactions\n      path: /contracts/{addressHash}/internal-transactions\n      operations:\n      - name: findcontracttransactions-2\n        method: GET\n        description: Chainlens Retrieve contract internal transactions by its address hash.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts-addresshash-events\n      path: /contracts/{addressHash}/events\n      operations:\n      - name: getcontractevents\n        method: GET\n        description: Chainlens Retrieve all events for this contract.\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts-addresshash-bytecode\n      path: /contracts/{addressHash}/bytecode\n      operations:\n      - name: getcontractbytecode\n        method: GET\n        description: Chainlens Retrieves bytecodes for a deployed contract.\n        inputParameters:\n\
  \        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the contract.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-type-get\n      path: /content-type/get\n      operations:\n      - name: getcontenttype\n        method: GET\n        description: GET /content-type/get\n        inputParameters:\n        - name: url\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration-frontend\n      path: /configuration/frontend\n      operations:\n      - name: frontendconfiguration\n        method: GET\n        description: Chainlens frontend configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: collections-recommended\n      path: /collections/recommended\n      operations:\n      - name: getrecommendedtokensbyprojects\n        method: GET\n        description: Chainlens Get a list of all recommended collections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blocks\n      path: /blocks\n      operations:\n      - name: findblocks\n        method: GET\n        description: Chainlens Retrieve blocks.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blocks-blockhash\n      path: /blocks/{blockHash}\n      operations:\n      - name: getblock\n        method: GET\n        description: Chainlens Retrieve a block by its hash or\
  \ height.\n        inputParameters:\n        - name: blockHash\n          in: path\n          type: string\n          required: true\n          description: The hash or height identifying the block.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blocks-blockhash-transactions\n      path: /blocks/{blockHash}/transactions\n      operations:\n      - name: getblocktransactions\n        method: GET\n        description: Chainlens Retrieve all transactions for this block.\n        inputParameters:\n        - name: blockHash\n          in: path\n          type: string\n          required: true\n          description: The address hash or height identifying the block.\n        - name: query\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: address-addresshash\n\
  \      path: /address/{addressHash}\n      operations:\n      - name: getaddress\n        method: GET\n        description: GET /address/{addressHash}\n        inputParameters:\n        - name: addressHash\n          in: path\n          type: string\n          required: true\n          description: The address hash identifying the address type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: chainlens-rest\n    description: REST adapter for Chainlens.\n    resources:\n    - path: /transactions\n      name: findtransactions\n      operations:\n      - method: GET\n        name: findtransac\n\n# --- truncated at 32 KB (83 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/chainlens/refs/heads/main/capabilities/chainlens-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/chainlens/refs/heads/main/capabilities/chainlens-capability.yaml
tags:
- Chainlens
- API
tools:
- description: Chainlens Retrieve transactions by address or block.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findtransactions
- description: Chainlens Retrieve a transaction by its hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransaction
- description: Chainlens Retrieve all internal transactions for this transaction.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinternalsbytx
- description: Chainlens Retrieve all events for this transaction.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransactionevents
- description: Chainlens Retrieve token contracts.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findtokens
- description: Chainlens Retrieve a token by its address hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettoken
- description: Chainlens Retrieve token contracts by tokenId.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findtokensbytokenid
- description: Chainlens Retrieve token transactions by token address hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findcontracttransactions
- description: Chainlens Retrieve a list of token holders by token contract address hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettokenholders
- description: Chainlens Retrieve all token events using token address.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettokenevents
- description: Chainlens Retrieve transfers of an ERC777 Token.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: finderc777transfers
- description: Chainlens Retrieve transfers of an ERC721 Token.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: finderc721transfers
- description: Chainlens Retrieve transfers of an ERC721 Token.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: finderc721transfers-1
- description: Chainlens Retrieve transfers of an ERC223 Token.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: finderc20transfers
- description: Chainlens Retrieve transfers of an ERC20 Token.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: finderc20transfers-1
- description: Chainlens Retrieve transfers of an ERC1155 Token.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: finderc1155transfers
- description: Chainlens Retrieve transfers of an ERC1155 Token.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: finderc1155transfers-1
- description: GET /token/{addressHash}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettoken-1
- description: GET /token-type/{addressHash}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettokentype
- description: Chainlens Retrieve blocks, transactions, accounts by hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search
- description: Chainlens Retrieve blocks, transactions, accounts by hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search-1
- description: Chainlens Retrieve ERC3643 tokens.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findtokens-1
- description: Chainlens Retrieve a ERC3643 by its address hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettoken-2
- description: Chainlens Retrieve token metadata for a given token contract address and token id.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettokenmetadata
- description: Chainlens Retrieve a list of token holders by token contract address hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettokenholders-1
- description: Chainlens Retrieve transfers of an ERC3643 Token.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: finderc3643transfers
- description: Chainlens Node details.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: details
- description: Chainlens Retrieve NFTs.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findtokens-2
- description: Chainlens Retrieve a NFT by its address hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettoken-3
- description: Chainlens Retrieve NFT contracts by tokenId.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findtokensbytokenid-1
- description: Chainlens Retrieve token metadata for a given token contract address and token id.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettokenmetadata-1
- description: Chainlens Retrieve a list of token holders by token contract address hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettokenholders-2
- description: Chainlens Retrieve transfers of an ERC721 Token.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: finderc721transfers-2
- description: Chainlens Retrieve transfers of an ERC1155 Token.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: finderc1155transfers-2
- description: Chainlens Retrieve all NFTs with Metadata.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findnftcollections
- description: Chainlens Retrieve metadata.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmetadata
- description: Chainlens list contracts by swarmhash
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findcontractsbyswarmhash
- description: Chainlens Retrieve Accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findaccounts
- description: GET /mappings/{id}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Chainlens Retrieve internal transactions by address.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findtransactions-1
- description: Chainlens Gas price oracle.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gaspriceinfo
- description: Chainlens Retrieve all events.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevents
- description: Chainlens Download ABI for a verified contract
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadabi
- description: Chainlens Retrieve total number of different transactions types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettotals
- description: Chainlens Retrieve total number of different transactions types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettotals-1
- description: Chainlens Retrieve total number of Contracts, Tokens and Transactions.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboardtotals
- description: Chainlens Retrieve total number of different token types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettokentotals
- description: Chainlens Retrieve contracts.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findcontracts
- description: Chainlens Retrieve a contract by its address hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontract
- description: Chainlens Retrieve contract transactions by its address hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findcontracttransactions-1
- description: Chainlens Retrieve contract internal transactions by its address hash.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findcontracttransactions-2
- description: Chainlens Retrieve all events for this contract.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontractevents
- description: Chainlens Retrieves bytecodes for a deployed contract.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontractbytecode
- description: GET /content-type/get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontenttype
- description: Chainlens frontend configuration.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: frontendconfiguration
- description: Chainlens Get a list of all recommended collections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrecommendedtokensbyprojects
- description: Chainlens Retrieve blocks.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findblocks
- description: Chainlens Retrieve a block by its hash or height.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblock
- description: Chainlens Retrieve all transactions for this block.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getblocktransactions
- description: GET /address/{addressHash}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaddress
---
