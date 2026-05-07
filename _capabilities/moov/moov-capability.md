---
categories: []
consumed_apis: []
description: The Moov API is a RESTful financial infrastructure platform that enables developers to integrate money movement capabilities into their applications. The API supports a full range of financial operations including account management, payment method onboarding, transfers, sweeps, refunds, dispute resolution, card issuing, and payment links. It provides capabilities for accepting payments, storing funds in digital wallets, sending money between accounts, and issuing cards for spend management. Authentication uses OAuth2 access tokens with permission scopes, and the API returns JSON responses usi
layout: capability
name: Moov API
operations:
- description: Create an access token
  method: POST
  name: createaccesstoken
  path: /oauth2/token
- description: Revoke an access token
  method: POST
  name: revokeaccesstoken
  path: /oauth2/revoke
- description: Generate a terms of service token
  method: GET
  name: generatetostoken
  path: /tos-token
- description: Create an account
  method: POST
  name: createaccount
  path: /accounts
- description: List accounts
  method: GET
  name: listaccounts
  path: /accounts
- description: Retrieve an account
  method: GET
  name: getaccount
  path: /accounts/{accountID}
- description: Update an account
  method: PATCH
  name: updateaccount
  path: /accounts/{accountID}
- description: Delete an account
  method: DELETE
  name: deleteaccount
  path: /accounts/{accountID}
- description: Share an account connection
  method: POST
  name: shareaccountconnection
  path: /accounts/{accountID}/connections
- description: List connected accounts
  method: GET
  name: listconnectedaccounts
  path: /accounts/{accountID}/connected-accounts
- description: Request capabilities
  method: POST
  name: requestcapabilities
  path: /accounts/{accountID}/capabilities
- description: List capabilities
  method: GET
  name: listcapabilities
  path: /accounts/{accountID}/capabilities
- description: Retrieve a capability
  method: GET
  name: getcapability
  path: /accounts/{accountID}/capabilities/{capabilityID}
- description: Disable a capability
  method: DELETE
  name: disablecapability
  path: /accounts/{accountID}/capabilities/{capabilityID}
- description: Add a representative
  method: POST
  name: addrepresentative
  path: /accounts/{accountID}/representatives
- description: List representatives
  method: GET
  name: listrepresentatives
  path: /accounts/{accountID}/representatives
- description: Retrieve a representative
  method: GET
  name: getrepresentative
  path: /accounts/{accountID}/representatives/{representativeID}
- description: Update a representative
  method: PATCH
  name: updaterepresentative
  path: /accounts/{accountID}/representatives/{representativeID}
- description: Remove a representative
  method: DELETE
  name: removerepresentative
  path: /accounts/{accountID}/representatives/{representativeID}
- description: Link a bank account
  method: POST
  name: linkbankaccount
  path: /accounts/{accountID}/bank-accounts
- description: List bank accounts
  method: GET
  name: listbankaccounts
  path: /accounts/{accountID}/bank-accounts
- description: Retrieve a bank account
  method: GET
  name: getbankaccount
  path: /accounts/{accountID}/bank-accounts/{bankAccountID}
- description: Delete a bank account
  method: DELETE
  name: deletebankaccount
  path: /accounts/{accountID}/bank-accounts/{bankAccountID}
- description: Initiate bank account verification
  method: POST
  name: initiatebankaccountverification
  path: /accounts/{accountID}/bank-accounts/{bankAccountID}/verify
- description: Complete bank account verification
  method: PUT
  name: completebankaccountverification
  path: /accounts/{accountID}/bank-accounts/{bankAccountID}/verify
- description: Get verification status
  method: GET
  name: getbankaccountverificationstatus
  path: /accounts/{accountID}/bank-accounts/{bankAccountID}/verify
- description: Initiate micro-deposits
  method: POST
  name: initiatemicrodeposits
  path: /accounts/{accountID}/bank-accounts/{bankAccountID}/micro-deposits
- description: Complete micro-deposit verification
  method: PUT
  name: completemicrodeposits
  path: /accounts/{accountID}/bank-accounts/{bankAccountID}/micro-deposits
- description: Link a card
  method: POST
  name: linkcard
  path: /accounts/{accountID}/cards
- description: List cards
  method: GET
  name: listcards
  path: /accounts/{accountID}/cards
- description: Retrieve a card
  method: GET
  name: getcard
  path: /accounts/{accountID}/cards/{cardID}
- description: Update a card
  method: PATCH
  name: updatecard
  path: /accounts/{accountID}/cards/{cardID}
- description: Disable a card
  method: DELETE
  name: disablecard
  path: /accounts/{accountID}/cards/{cardID}
- description: Create a wallet
  method: POST
  name: createwallet
  path: /accounts/{accountID}/wallets
- description: List wallets
  method: GET
  name: listwallets
  path: /accounts/{accountID}/wallets
- description: Retrieve a wallet
  method: GET
  name: getwallet
  path: /accounts/{accountID}/wallets/{walletID}
- description: Update a wallet
  method: PATCH
  name: updatewallet
  path: /accounts/{accountID}/wallets/{walletID}
- description: List wallet transactions
  method: GET
  name: listwallettransactions
  path: /accounts/{accountID}/wallets/{walletID}/transactions
- description: Retrieve a wallet transaction
  method: GET
  name: getwallettransaction
  path: /accounts/{accountID}/wallets/{walletID}/transactions/{transactionID}
- description: List payment methods
  method: GET
  name: listpaymentmethods
  path: /accounts/{accountID}/payment-methods
- description: Retrieve a payment method
  method: GET
  name: getpaymentmethod
  path: /accounts/{accountID}/payment-methods/{paymentMethodID}
- description: Create a transfer
  method: POST
  name: createtransfer
  path: /accounts/{accountID}/transfers
- description: List transfers
  method: GET
  name: listtransfers
  path: /accounts/{accountID}/transfers
- description: Retrieve a transfer
  method: GET
  name: gettransfer
  path: /accounts/{accountID}/transfers/{transferID}
- description: Update transfer metadata
  method: PATCH
  name: updatetransfermetadata
  path: /accounts/{accountID}/transfers/{transferID}
- description: Retrieve transfer options
  method: POST
  name: gettransferoptions
  path: /accounts/{accountID}/transfer-options
- description: Cancel a transfer
  method: POST
  name: canceltransfer
  path: /accounts/{accountID}/transfers/{transferID}/cancellations
- description: Create a refund
  method: POST
  name: createrefund
  path: /accounts/{accountID}/transfers/{transferID}/refunds
- description: List refunds
  method: GET
  name: listrefunds
  path: /accounts/{accountID}/transfers/{transferID}/refunds
- description: Retrieve a refund
  method: GET
  name: getrefund
  path: /accounts/{accountID}/transfers/{transferID}/refunds/{refundID}
- description: Create a sweep config
  method: POST
  name: createsweepconfig
  path: /accounts/{accountID}/sweep-configs
- description: List sweep configs
  method: GET
  name: listsweepconfigs
  path: /accounts/{accountID}/sweep-configs
- description: Get a sweep config
  method: GET
  name: getsweepconfig
  path: /accounts/{accountID}/sweep-configs/{sweepConfigID}
- description: Update a sweep config
  method: PATCH
  name: updatesweepconfig
  path: /accounts/{accountID}/sweep-configs/{sweepConfigID}
- description: List sweeps
  method: GET
  name: listsweeps
  path: /accounts/{accountID}/wallets/{walletID}/sweeps
- description: Get a sweep
  method: GET
  name: getsweep
  path: /accounts/{accountID}/wallets/{walletID}/sweeps/{sweepID}
- description: List disputes
  method: GET
  name: listdisputes
  path: /accounts/{accountID}/disputes
- description: Retrieve a dispute
  method: GET
  name: getdispute
  path: /accounts/{accountID}/disputes/{disputeID}
- description: Accept a dispute
  method: POST
  name: acceptdispute
  path: /accounts/{accountID}/disputes/{disputeID}/accept
- description: Upload evidence file
  method: POST
  name: uploaddisputeevidencefile
  path: /accounts/{accountID}/disputes/{disputeID}/evidence-file
personas: []
provider_name: Moov
provider_slug: moov
search_terms:
- retrieve transfer options
- list sweeps
- getaccount
- create an account
- list cards
- updateaccount
- api
- retrieve a card
- list accounts
- accept a dispute
- list wallet transactions
- getsweepconfig
- remove a representative
- listcapabilities
- create a refund
- update transfer metadata
- uploaddisputeevidencefile
- createtransfer
- initiate micro-deposits
- listrepresentatives
- list disputes
- listpaymentmethods
- updaterepresentative
- link a bank account
- getwallet
- completebankaccountverification
- updatecard
- create a wallet
- revoke an access token
- getbankaccount
- create an access token
- cancel a transfer
- retrieve a wallet
- upload evidence file
- list refunds
- createaccount
- share an account connection
- get a sweep config
- retrieve a transfer
- createaccesstoken
- retrieve a wallet transaction
- listwallets
- get a sweep
- list connected accounts
- getcard
- listcards
- getsweep
- delete an account
- initiate bank account verification
- updatewallet
- listwallettransactions
- createwallet
- complete bank account verification
- getcapability
- gettransfer
- update a sweep config
- initiatebankaccountverification
- acceptdispute
- removerepresentative
- delete a bank account
- getrepresentative
- listaccounts
- banking
- updatetransfermetadata
- payments
- disable a capability
- getrefund
- list wallets
- transfers
- listtransfers
- getbankaccountverificationstatus
- list bank accounts
- listsweeps
- get verification status
- initiatemicrodeposits
- create a transfer
- update a wallet
- addrepresentative
- retrieve a refund
- generate a terms of service token
- createsweepconfig
- complete micro-deposit verification
- listsweepconfigs
- financial infrastructure
- linkcard
- moov
- request capabilities
- add a representative
- canceltransfer
- disable a card
- list representatives
- listdisputes
- getwallettransaction
- link a card
- update a representative
- create a sweep config
- disablecard
- retrieve a representative
- retrieve an account
- getdispute
- deletebankaccount
- embedded finance
- createrefund
- completemicrodeposits
- listbankaccounts
- getpaymentmethod
- linkbankaccount
- retrieve a dispute
- shareaccountconnection
- listconnectedaccounts
- list payment methods
- updatesweepconfig
- retrieve a bank account
- list sweep configs
- money movement
- list transfers
- requestcapabilities
- listrefunds
- generatetostoken
- deleteaccount
- disablecapability
- update a card
- update an account
- revokeaccesstoken
- retrieve a payment method
- gettransferoptions
- list capabilities
- retrieve a capability
slug: moov-capability
source_filename: moov-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Moov API\n  description: The Moov API is a RESTful financial infrastructure platform that enables developers to integrate money movement\n    capabilities into their applications. The API supports a full range of financial operations including account management,\n    payment method onboarding, transfers, sweeps, refunds, dispute resolution, card issuing, and payment links. It provides\n    capabilities for accepting payments, storing funds in digital wallets, sending money between accounts, and issuing cards\n    for spend management. Authentication uses OAuth2 access tokens with permission scopes, and the API returns JSON responses\n    usi\n  tags:\n  - Moov\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: moov\n    baseUri: https://api.moov.io\n    description: Moov API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MOOV_TOKEN}}'\n    resources:\n\
  \    - name: oauth2-token\n      path: /oauth2/token\n      operations:\n      - name: createaccesstoken\n        method: POST\n        description: Create an access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-revoke\n      path: /oauth2/revoke\n      operations:\n      - name: revokeaccesstoken\n        method: POST\n        description: Revoke an access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tos-token\n      path: /tos-token\n      operations:\n      - name: generatetostoken\n        method: GET\n        description: Generate a terms of service token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /accounts\n      operations:\n      - name: createaccount\n   \
  \     method: POST\n        description: Create an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listaccounts\n        method: GET\n        description: List accounts\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter accounts by display name.\n        - name: email\n          in: query\n          type: string\n          description: Filter accounts by email address.\n        - name: type\n          in: query\n          type: string\n          description: Filter by account type (individual or business).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid\n      path: /accounts/{accountID}\n      operations:\n      - name: getaccount\n        method: GET\n        description: Retrieve an account\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccount\n        method: PATCH\n        description: Update an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteaccount\n        method: DELETE\n        description: Delete an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-connections\n      path: /accounts/{accountID}/connections\n      operations:\n      - name: shareaccountconnection\n        method: POST\n        description: Share an account connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-connected-accounts\n      path: /accounts/{accountID}/connected-accounts\n    \
  \  operations:\n      - name: listconnectedaccounts\n        method: GET\n        description: List connected accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-capabilities\n      path: /accounts/{accountID}/capabilities\n      operations:\n      - name: requestcapabilities\n        method: POST\n        description: Request capabilities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listcapabilities\n        method: GET\n        description: List capabilities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-capabilities-capabilityid\n      path: /accounts/{accountID}/capabilities/{capabilityID}\n      operations:\n      - name: getcapability\n        method: GET\n   \
  \     description: Retrieve a capability\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disablecapability\n        method: DELETE\n        description: Disable a capability\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-representatives\n      path: /accounts/{accountID}/representatives\n      operations:\n      - name: addrepresentative\n        method: POST\n        description: Add a representative\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listrepresentatives\n        method: GET\n        description: List representatives\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-representatives-representativ\n\
  \      path: /accounts/{accountID}/representatives/{representativeID}\n      operations:\n      - name: getrepresentative\n        method: GET\n        description: Retrieve a representative\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterepresentative\n        method: PATCH\n        description: Update a representative\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removerepresentative\n        method: DELETE\n        description: Remove a representative\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-bank-accounts\n      path: /accounts/{accountID}/bank-accounts\n      operations:\n      - name: linkbankaccount\n        method: POST\n        description: Link a bank account\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listbankaccounts\n        method: GET\n        description: List bank accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-bank-accounts-bankaccountid\n      path: /accounts/{accountID}/bank-accounts/{bankAccountID}\n      operations:\n      - name: getbankaccount\n        method: GET\n        description: Retrieve a bank account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebankaccount\n        method: DELETE\n        description: Delete a bank account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-bank-accounts-bankaccountid-v\n\
  \      path: /accounts/{accountID}/bank-accounts/{bankAccountID}/verify\n      operations:\n      - name: initiatebankaccountverification\n        method: POST\n        description: Initiate bank account verification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: completebankaccountverification\n        method: PUT\n        description: Complete bank account verification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getbankaccountverificationstatus\n        method: GET\n        description: Get verification status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-bank-accounts-bankaccountid-m\n      path: /accounts/{accountID}/bank-accounts/{bankAccountID}/micro-deposits\n      operations:\n\
  \      - name: initiatemicrodeposits\n        method: POST\n        description: Initiate micro-deposits\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: completemicrodeposits\n        method: PUT\n        description: Complete micro-deposit verification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-cards\n      path: /accounts/{accountID}/cards\n      operations:\n      - name: linkcard\n        method: POST\n        description: Link a card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listcards\n        method: GET\n        description: List cards\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-cards-cardid\n\
  \      path: /accounts/{accountID}/cards/{cardID}\n      operations:\n      - name: getcard\n        method: GET\n        description: Retrieve a card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecard\n        method: PATCH\n        description: Update a card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disablecard\n        method: DELETE\n        description: Disable a card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-wallets\n      path: /accounts/{accountID}/wallets\n      operations:\n      - name: createwallet\n        method: POST\n        description: Create a wallet\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: listwallets\n        method: GET\n        description: List wallets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-wallets-walletid\n      path: /accounts/{accountID}/wallets/{walletID}\n      operations:\n      - name: getwallet\n        method: GET\n        description: Retrieve a wallet\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatewallet\n        method: PATCH\n        description: Update a wallet\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-wallets-walletid-transactions\n      path: /accounts/{accountID}/wallets/{walletID}/transactions\n      operations:\n      - name: listwallettransactions\n        method: GET\n        description:\
  \ List wallet transactions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-wallets-walletid-transactions\n      path: /accounts/{accountID}/wallets/{walletID}/transactions/{transactionID}\n      operations:\n      - name: getwallettransaction\n        method: GET\n        description: Retrieve a wallet transaction\n        inputParameters:\n        - name: transactionID\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the wallet transaction.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-payment-methods\n      path: /accounts/{accountID}/payment-methods\n      operations:\n      - name: listpaymentmethods\n        method: GET\n        description: List payment methods\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-payment-methods-paymentmethod\n      path: /accounts/{accountID}/payment-methods/{paymentMethodID}\n      operations:\n      - name: getpaymentmethod\n        method: GET\n        description: Retrieve a payment method\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-transfers\n      path: /accounts/{accountID}/transfers\n      operations:\n      - name: createtransfer\n        method: POST\n        description: Create a transfer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listtransfers\n        method: GET\n        description: List transfers\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description:\
  \ Filter transfers by their current status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-transfers-transferid\n      path: /accounts/{accountID}/transfers/{transferID}\n      operations:\n      - name: gettransfer\n        method: GET\n        description: Retrieve a transfer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetransfermetadata\n        method: PATCH\n        description: Update transfer metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-transfer-options\n      path: /accounts/{accountID}/transfer-options\n      operations:\n      - name: gettransferoptions\n        method: POST\n        description: Retrieve transfer options\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-transfers-transferid-cancella\n      path: /accounts/{accountID}/transfers/{transferID}/cancellations\n      operations:\n      - name: canceltransfer\n        method: POST\n        description: Cancel a transfer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-transfers-transferid-refunds\n      path: /accounts/{accountID}/transfers/{transferID}/refunds\n      operations:\n      - name: createrefund\n        method: POST\n        description: Create a refund\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listrefunds\n        method: GET\n        description: List refunds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: accounts-accountid-transfers-transferid-refunds-\n      path: /accounts/{accountID}/transfers/{transferID}/refunds/{refundID}\n      operations:\n      - name: getrefund\n        method: GET\n        description: Retrieve a refund\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-sweep-configs\n      path: /accounts/{accountID}/sweep-configs\n      operations:\n      - name: createsweepconfig\n        method: POST\n        description: Create a sweep config\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listsweepconfigs\n        method: GET\n        description: List sweep configs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-sweep-configs-sweepconfigid\n\
  \      path: /accounts/{accountID}/sweep-configs/{sweepConfigID}\n      operations:\n      - name: getsweepconfig\n        method: GET\n        description: Get a sweep config\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesweepconfig\n        method: PATCH\n        description: Update a sweep config\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-wallets-walletid-sweeps\n      path: /accounts/{accountID}/wallets/{walletID}/sweeps\n      operations:\n      - name: listsweeps\n        method: GET\n        description: List sweeps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-wallets-walletid-sweeps-sweep\n      path: /accounts/{accountID}/wallets/{walletID}/sweeps/{sweepID}\n\
  \      operations:\n      - name: getsweep\n        method: GET\n        description: Get a sweep\n        inputParameters:\n        - name: sweepID\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the sweep execution.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-disputes\n      path: /accounts/{accountID}/disputes\n      operations:\n      - name: listdisputes\n        method: GET\n        description: List disputes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-disputes-disputeid\n      path: /accounts/{accountID}/disputes/{disputeID}\n      operations:\n      - name: getdispute\n        method: GET\n        description: Retrieve a dispute\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-disputes-disputeid-accept\n      path: /accounts/{accountID}/disputes/{disputeID}/accept\n      operations:\n      - name: acceptdispute\n        method: POST\n        description: Accept a dispute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-disputes-disputeid-evidence-f\n      path: /accounts/{accountID}/disputes/{disputeID}/evidence-file\n      operations:\n      - name: uploaddisputeevidencefile\n        method: POST\n        description: Upload evidence file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: moov-rest\n    description: REST adapter for Moov API.\n    resources:\n    - path: /oauth2/token\n      name: createaccesstoken\n\
  \      operations:\n      - method: POST\n        name: createaccesstoken\n        description: Create an access token\n        call: moov.createaccesstoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/revoke\n      name: revokeaccesstoken\n      operations:\n      - method: POST\n        name: revokeaccesstoken\n        description: Revoke an access token\n        call: moov.revokeaccesstoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tos-token\n      name: generatetostoken\n      operations:\n      - method: GET\n        name: generatetostoken\n        description: Generate a terms of service token\n        call: moov.generatetostoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts\n      name: createaccount\n      operations:\n      - method: POST\n        name: createaccount\n        description: Create an account\n        call: moov.createaccount\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts\n      name: listaccounts\n      operations:\n      - method: GET\n        name: listaccounts\n        description: List accounts\n        call: moov.listaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}\n      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Retrieve an account\n        call: moov.getaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}\n      name: updateaccount\n      operations:\n      - method: PATCH\n        name: updateaccount\n        description: Update an account\n        call: moov.updateaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}\n      name: deleteaccount\n      operations:\n      - method: DELETE\n      \
  \  name: deleteaccount\n        description: Delete an account\n        call: moov.deleteaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/connections\n      name: shareaccountconnection\n      operations:\n      - method: POST\n        name: shareaccountconnection\n        description: Share an account connection\n        call: moov.shareaccountconnection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/connected-accounts\n      name: listconnectedaccounts\n      operations:\n      - method: GET\n        name: listconnectedaccounts\n        description: List connected accounts\n        call: moov.listconnectedaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/capabilities\n      name: requestcapabilities\n      operations:\n      - method: POST\n        name: requestcapabilities\n        description:\
  \ Request capabilities\n        call: moov.requestcapabilities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/capabilities\n      name: listcapabilities\n      operations:\n      - method: GET\n        name: listcapabilities\n        description: List capabilities\n        call: moov.listcapabilities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/capabilities/{capabilityID}\n      name: getcapability\n      operations:\n      - method: GET\n        name: getcapability\n        description: Retrieve a capability\n        call: moov.getcapability\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/capabilities/{capabilityID}\n      name: disablecapability\n      operations:\n      - method: DELETE\n        name: disablecapability\n        description: Disable a capability\n        call: moov.disablecapability\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/representatives\n      name: addrepresentative\n      operations:\n      - method: POST\n        name: addrepresentative\n        description: Add a representative\n        call: moov.addrepresentative\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/representatives\n      name: listrepresentatives\n      operations:\n      - method: GET\n        name: listrepresentatives\n        description: List representatives\n        call: moov.listrepresentatives\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/representatives/{representativeID}\n      name: getrepresentative\n      operations:\n      - method: GET\n        name: getrepresentative\n        description: Retrieve a representative\n        call: moov.getrepresentative\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /accounts/{accountID}/representatives/{representativeID}\n      name: updaterepresentative\n      operations:\n      - method: PATCH\n        name: updaterepresentative\n        description: Update a representative\n        call: moov.updaterepresentative\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/representatives/{representativeID}\n      name: removerepresentative\n      operations:\n      - method: DELETE\n        name: removerepresentative\n        description: Remove a representative\n        call: moov.removerepresentative\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/bank-accounts\n      name: linkbankaccount\n      operations:\n      - method: POST\n        name: linkbankaccount\n        description: Link a bank account\n        call: moov.linkbankaccount\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /accounts/{accountID}/bank-accounts\n      name: listbankaccounts\n      operations:\n      - method: GET\n        name: listbankaccounts\n        description: List bank accounts\n        call: moov.listbankaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/bank-accounts/{bankAccountID}\n      name: getbankaccount\n      operations:\n      - method: GET\n        name: getbankaccount\n        description: Retrieve a bank account\n        call: moov.getbankaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/bank-accounts/{bankAccountID}\n      name: deletebankaccount\n      operations:\n      - method: DELETE\n        name: deletebankaccount\n        description: Delete a bank account\n        call: moov.deletebankaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/bank-accounts/{bankAccountID}/verify\n\
  \      name: initiatebankaccountverification\n      operations:\n      - method: POST\n        name: initiatebankaccountverification\n        description: Initiate bank account verification\n        call: moov.initiatebankaccountverification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/bank-accounts/{bankAccountID}/verify\n      name: completebankaccountverification\n      operations:\n      - method: PUT\n        name: completebankaccountverification\n        description: Complete bank account verification\n        call: moov.completebankaccountverification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/bank-accounts/{bankAccountID}/verify\n      name: getbankaccountverificationstatus\n      operations:\n      - method: GET\n        name: getbankaccountverificationstatus\n        description: Get verification status\n        call: moov.getbankaccountverificationstatus\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/bank-accounts/{bankAccountID}/micro-deposits\n      name: initiatemicrodeposits\n      operations:\n      - method: POST\n        name: initiatemicrodeposits\n        description: Initiate micro-deposits\n        call: moov.initiatemicrodeposits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/bank-accounts/{bankAccountID}/micro-deposits\n      name: completemicrodeposits\n      operations:\n      - method: PUT\n        name: completemicrodeposits\n        description: Complete micro-deposit verification\n        call: moov.completemicrodeposits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/cards\n      name: linkcard\n      operations:\n      - method: POST\n        name: linkcard\n        description: Link a card\n        call: moov.linkcard\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/cards\n      name: listcards\n      operations:\n      - method: GET\n        name: listcards\n        description: List cards\n        call: moov.listcards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/cards/{cardID}\n      name: getcard\n      operations:\n      - method: GET\n        name: getcard\n        description: Retrieve a card\n        call: moov.getcard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/cards/{cardID}\n      name: updatecard\n      operations:\n      - method: PATCH\n        name: updatecard\n        description: Update a card\n        call: moov.updatecard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/cards/{cardID}\n      name: disablecard\n      operations:\n      - method: DELETE\n        name:\
  \ disablecard\n        description: Disable a card\n        call: moov.disablecard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/wallets\n      name: createwallet\n      operations:\n      - method: POST\n        name: createwallet\n        description: Create a wallet\n        call: moov.createwallet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/wallets\n      name: listwallets\n      operations:\n      - method: GET\n        name: listwallets\n        description: List wallets\n        call: moov.listwallets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/wallets/{walletID}\n      name: getwallet\n      operations:\n      - method: GET\n        name: getwallet\n        description: Retrieve a wallet\n        call: moov.getwallet\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /accounts/{accountID}/wallets/{walletID}\n      name: updatewallet\n      operations:\n      - method: PATCH\n        name: updatewallet\n        description: Update a wallet\n        call: moov.updatewallet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/wallets/{walletID}/transactions\n      name: listwallettransactions\n      operations:\n      - method: GET\n        name: listwallettransactions\n        description: List wallet transactions\n        call: moov.listwallettransactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/wallets/{walletID}/transactions/{transactionID}\n      name: getwallettransaction\n      operations:\n      - method: GET\n        name: getwallettransaction\n        description: Retrieve a wallet transaction\n        call: moov.getwallettransaction\n        with:\n          transactionID: rest.transactionID\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/payment-methods\n      name: listpaymentmethods\n      operations:\n      - method: GET\n        name: listpaymentmethods\n        description: List payment methods\n        call: moov.listpaymentmethods\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/payment-methods/{paymentMethodID}\n      name: getpaymentmethod\n      operations:\n      - method: GET\n        name: getpaymentmethod\n        description: Retrieve a payment method\n        call: moov.getpaymentmethod\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/transfers\n      name: createtransfer\n      operations:\n      - method: POST\n        name: createtransfer\n        description: Create a transfer\n        call: moov.createtransfer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/transfers\n\
  \      name: listtransfers\n      operations:\n      - method: GET\n        name: listtransfers\n        description: List transfers\n        call: moov.listtransfers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/transfers/{transferID}\n      name: gettransfer\n      operations:\n      - method: GET\n        name: gettransfer\n        description: Retrieve a transfer\n        call: moov.gettransfer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountID}/transfers/{transferID}\n      name: updatetransfermetadata\n\n# --- truncated at 32 KB (52 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/moov/refs/heads/main/capabilities/moov-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/moov/refs/heads/main/capabilities/moov-capability.yaml
tags:
- Moov
- API
tools:
- description: Create an access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaccesstoken
- description: Revoke an access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revokeaccesstoken
- description: Generate a terms of service token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: generatetostoken
- description: Create an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaccount
- description: List accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Retrieve an account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Update an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateaccount
- description: Delete an account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaccount
- description: Share an account connection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: shareaccountconnection
- description: List connected accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconnectedaccounts
- description: Request capabilities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: requestcapabilities
- description: List capabilities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcapabilities
- description: Retrieve a capability
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcapability
- description: Disable a capability
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: disablecapability
- description: Add a representative
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addrepresentative
- description: List representatives
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrepresentatives
- description: Retrieve a representative
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrepresentative
- description: Update a representative
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updaterepresentative
- description: Remove a representative
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removerepresentative
- description: Link a bank account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: linkbankaccount
- description: List bank accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbankaccounts
- description: Retrieve a bank account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbankaccount
- description: Delete a bank account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebankaccount
- description: Initiate bank account verification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initiatebankaccountverification
- description: Complete bank account verification
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: completebankaccountverification
- description: Get verification status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbankaccountverificationstatus
- description: Initiate micro-deposits
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initiatemicrodeposits
- description: Complete micro-deposit verification
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: completemicrodeposits
- description: Link a card
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: linkcard
- description: List cards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcards
- description: Retrieve a card
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcard
- description: Update a card
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecard
- description: Disable a card
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: disablecard
- description: Create a wallet
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwallet
- description: List wallets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwallets
- description: Retrieve a wallet
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwallet
- description: Update a wallet
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatewallet
- description: List wallet transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwallettransactions
- description: Retrieve a wallet transaction
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwallettransaction
- description: List payment methods
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpaymentmethods
- description: Retrieve a payment method
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpaymentmethod
- description: Create a transfer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtransfer
- description: List transfers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtransfers
- description: Retrieve a transfer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransfer
- description: Update transfer metadata
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetransfermetadata
- description: Retrieve transfer options
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: gettransferoptions
- description: Cancel a transfer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: canceltransfer
- description: Create a refund
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrefund
- description: List refunds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrefunds
- description: Retrieve a refund
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrefund
- description: Create a sweep config
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsweepconfig
- description: List sweep configs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsweepconfigs
- description: Get a sweep config
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsweepconfig
- description: Update a sweep config
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesweepconfig
- description: List sweeps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsweeps
- description: Get a sweep
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsweep
- description: List disputes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdisputes
- description: Retrieve a dispute
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdispute
- description: Accept a dispute
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: acceptdispute
- description: Upload evidence file
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploaddisputeevidencefile
---
