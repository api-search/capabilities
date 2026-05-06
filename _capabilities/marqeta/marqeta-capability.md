---
categories: []
consumed_apis: []
description: The Marqeta Core API is a RESTful interface that enables developers to build and manage card payment programs programmatically. It provides endpoints for creating and managing users (cardholders) and businesses, issuing physical and virtual payment cards, defining spending controls via authorization controls and velocity controls, processing and retrieving transactions, managing funding sources, and configuring webhooks for real-time event notifications. The API supports use cases including prepaid cards, expense management, earned wage access, buy now pay later programs, and credit card issua
layout: capability
name: Marqeta Core API
operations:
- description: List users
  method: GET
  name: listusers
  path: /users
- description: Create a user
  method: POST
  name: createuser
  path: /users
- description: Retrieve a user
  method: GET
  name: getuser
  path: /users/{token}
- description: Update a user
  method: PUT
  name: updateuser
  path: /users/{token}
- description: Create a user transition
  method: POST
  name: createusertransition
  path: /usertransitions
- description: List user transitions
  method: GET
  name: listusertransitions
  path: /usertransitions/user/{user_token}
- description: List cards for a user
  method: GET
  name: listcards
  path: /cards
- description: Create a card
  method: POST
  name: createcard
  path: /cards
- description: Retrieve a card
  method: GET
  name: getcard
  path: /cards/{token}
- description: Update a card
  method: PUT
  name: updatecard
  path: /cards/{token}
- description: Create a card transition
  method: POST
  name: createcardtransition
  path: /cardtransitions
- description: List card transitions
  method: GET
  name: listcardtransitions
  path: /cardtransitions/card/{card_token}
- description: List card products
  method: GET
  name: listcardproducts
  path: /cardproducts
- description: Create a card product
  method: POST
  name: createcardproduct
  path: /cardproducts
- description: Retrieve a card product
  method: GET
  name: getcardproduct
  path: /cardproducts/{token}
- description: Update a card product
  method: PUT
  name: updatecardproduct
  path: /cardproducts/{token}
- description: List transactions
  method: GET
  name: listtransactions
  path: /transactions
- description: Retrieve a transaction
  method: GET
  name: gettransaction
  path: /transactions/{token}
- description: Retrieve GPA balance
  method: GET
  name: getbalance
  path: /balances/{token}
- description: List GPA orders
  method: GET
  name: listgpaorders
  path: /gpaorders
- description: Create a GPA order
  method: POST
  name: creategpaorder
  path: /gpaorders
- description: Retrieve a GPA order
  method: GET
  name: getgpaorder
  path: /gpaorders/{token}
- description: List authorization controls
  method: GET
  name: listauthcontrols
  path: /authcontrols
- description: Create an authorization control
  method: POST
  name: createauthcontrol
  path: /authcontrols
- description: Retrieve an authorization control
  method: GET
  name: getauthcontrol
  path: /authcontrols/{token}
- description: Update an authorization control
  method: PUT
  name: updateauthcontrol
  path: /authcontrols/{token}
- description: List velocity controls
  method: GET
  name: listvelocitycontrols
  path: /velocitycontrols
- description: Create a velocity control
  method: POST
  name: createvelocitycontrol
  path: /velocitycontrols
- description: Retrieve a velocity control
  method: GET
  name: getvelocitycontrol
  path: /velocitycontrols/{token}
- description: Update a velocity control
  method: PUT
  name: updatevelocitycontrol
  path: /velocitycontrols/{token}
- description: List webhooks
  method: GET
  name: listwebhooks
  path: /webhooks
- description: Create a webhook
  method: POST
  name: createwebhook
  path: /webhooks
- description: Retrieve a webhook
  method: GET
  name: getwebhook
  path: /webhooks/{token}
- description: Update a webhook
  method: PUT
  name: updatewebhook
  path: /webhooks/{token}
- description: Resend a webhook event
  method: POST
  name: resendwebhookevent
  path: /webhooks/{token}/resend/{event_type}/{resource_token}
- description: Create a KYC verification
  method: POST
  name: createkycverification
  path: /kyc
- description: List KYC verifications for a user
  method: GET
  name: listkycforuser
  path: /kyc/user/{user_token}
- description: Create an ACH funding source
  method: POST
  name: createachfundingsource
  path: /fundingsources/ach
- description: Retrieve an ACH funding source
  method: GET
  name: getachfundingsource
  path: /fundingsources/ach/{funding_source_token}
- description: Create a program ACH funding source
  method: POST
  name: createprogramachfundingsource
  path: /fundingsources/program/ach
- description: Retrieve program reserve balance
  method: GET
  name: getprogramreservebalance
  path: /programreserve/balances
- description: List businesses
  method: GET
  name: listbusinesses
  path: /businesses
- description: Create a business
  method: POST
  name: createbusiness
  path: /businesses
- description: Retrieve a business
  method: GET
  name: getbusiness
  path: /businesses/{token}
- description: Update a business
  method: PUT
  name: updatebusiness
  path: /businesses/{token}
personas: []
provider_name: marqeta
provider_slug: marqeta
search_terms:
- update a velocity control
- update a card
- resendwebhookevent
- createvelocitycontrol
- createauthcontrol
- update an authorization control
- create a business
- updatecard
- listgpaorders
- listwebhooks
- api
- retrieve a webhook
- create a card transition
- createprogramachfundingsource
- create a user
- createwebhook
- getcardproduct
- create a program ach funding source
- getuser
- retrieve program reserve balance
- update a card product
- create a gpa order
- getcard
- updateuser
- updatebusiness
- create a card
- retrieve a user
- createuser
- listcardtransitions
- create an ach funding source
- create a webhook
- list cards for a user
- list authorization controls
- list kyc verifications for a user
- createbusiness
- list card products
- retrieve an ach funding source
- createcard
- getprogramreservebalance
- listusers
- list transactions
- createcardproduct
- retrieve a card
- retrieve gpa balance
- updatevelocitycontrol
- getachfundingsource
- listusertransitions
- updatecardproduct
- createcardtransition
- list card transitions
- create a kyc verification
- retrieve an authorization control
- retrieve a card product
- retrieve a business
- getauthcontrol
- getwebhook
- create a velocity control
- listkycforuser
- marqeta
- create a user transition
- creategpaorder
- list user transitions
- listbusinesses
- retrieve a velocity control
- getbusiness
- listcardproducts
- getvelocitycontrol
- gettransaction
- retrieve a gpa order
- retrieve a transaction
- updatewebhook
- listtransactions
- updateauthcontrol
- listcards
- createkycverification
- list velocity controls
- listvelocitycontrols
- resend a webhook event
- list gpa orders
- list businesses
- update a webhook
- getbalance
- createachfundingsource
- getgpaorder
- createusertransition
- create an authorization control
- update a business
- list users
- update a user
- list webhooks
- listauthcontrols
- create a card product
slug: marqeta-capability
source_filename: marqeta-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Marqeta Core API\n  description: The Marqeta Core API is a RESTful interface that enables developers to build and manage card payment programs\n    programmatically. It provides endpoints for creating and managing users (cardholders) and businesses, issuing physical\n    and virtual payment cards, defining spending controls via authorization controls and velocity controls, processing and\n    retrieving transactions, managing funding sources, and configuring webhooks for real-time event notifications. The API\n    supports use cases including prepaid cards, expense management, earned wage access, buy now pay later programs, and credit\n    card issua\n  tags:\n  - Marqeta\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: marqeta\n    baseUri: https://sandbox-api.marqeta.com/v3\n    description: Marqeta Core API HTTP API.\n    authentication:\n      type: basic\n      username:\
  \ '{{MARQETA_USERNAME}}'\n      password: '{{MARQETA_PASSWORD}}'\n    resources:\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: List users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Create a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-token\n      path: /users/{token}\n      operations:\n      - name: getuser\n        method: GET\n        description: Retrieve a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PUT\n        description: Update a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: usertransitions\n      path: /usertransitions\n      operations:\n      - name: createusertransition\n        method: POST\n        description: Create a user transition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: usertransitions-user-user-token\n      path: /usertransitions/user/{user_token}\n      operations:\n      - name: listusertransitions\n        method: GET\n        description: List user transitions\n        inputParameters:\n        - name: user_token\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cards\n      path: /cards\n      operations:\n      - name: listcards\n        method: GET\n        description: List\
  \ cards for a user\n        inputParameters:\n        - name: user_token\n          in: query\n          type: string\n          description: Filter cards by user token.\n        - name: business_token\n          in: query\n          type: string\n          description: Filter cards by business token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcard\n        method: POST\n        description: Create a card\n        inputParameters:\n        - name: show_cvv_number\n          in: query\n          type: boolean\n          description: If true, the response includes the card CVV2 value. This is only returned once at card creation.\n        - name: show_pan\n          in: query\n          type: boolean\n          description: If true, the response includes the full 16-digit PAN. This is only returned once at card creation.\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: cards-token\n      path: /cards/{token}\n      operations:\n      - name: getcard\n        method: GET\n        description: Retrieve a card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecard\n        method: PUT\n        description: Update a card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cardtransitions\n      path: /cardtransitions\n      operations:\n      - name: createcardtransition\n        method: POST\n        description: Create a card transition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cardtransitions-card-card-token\n      path: /cardtransitions/card/{card_token}\n      operations:\n      - name: listcardtransitions\n\
  \        method: GET\n        description: List card transitions\n        inputParameters:\n        - name: card_token\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the card.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cardproducts\n      path: /cardproducts\n      operations:\n      - name: listcardproducts\n        method: GET\n        description: List card products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcardproduct\n        method: POST\n        description: Create a card product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cardproducts-token\n      path: /cardproducts/{token}\n      operations:\n      - name: getcardproduct\n\
  \        method: GET\n        description: Retrieve a card product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecardproduct\n        method: PUT\n        description: Update a card product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /transactions\n      operations:\n      - name: listtransactions\n        method: GET\n        description: List transactions\n        inputParameters:\n        - name: user_token\n          in: query\n          type: string\n          description: Filter transactions by user token.\n        - name: business_token\n          in: query\n          type: string\n          description: Filter transactions by business token.\n        - name: card_token\n          in: query\n          type: string\n          description: Filter transactions by\
  \ card token.\n        - name: type\n          in: query\n          type: string\n          description: Filter transactions by type (e.g., authorization, clearing).\n        - name: state\n          in: query\n          type: string\n          description: Filter transactions by state (e.g., PENDING, COMPLETION).\n        - name: start_date\n          in: query\n          type: string\n          description: Return transactions on or after this date (format YYYY-MM-DD).\n        - name: end_date\n          in: query\n          type: string\n          description: Return transactions on or before this date (format YYYY-MM-DD).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-token\n      path: /transactions/{token}\n      operations:\n      - name: gettransaction\n        method: GET\n        description: Retrieve a transaction\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: balances-token\n      path: /balances/{token}\n      operations:\n      - name: getbalance\n        method: GET\n        description: Retrieve GPA balance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gpaorders\n      path: /gpaorders\n      operations:\n      - name: listgpaorders\n        method: GET\n        description: List GPA orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategpaorder\n        method: POST\n        description: Create a GPA order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gpaorders-token\n      path: /gpaorders/{token}\n      operations:\n      - name: getgpaorder\n        method: GET\n     \
  \   description: Retrieve a GPA order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authcontrols\n      path: /authcontrols\n      operations:\n      - name: listauthcontrols\n        method: GET\n        description: List authorization controls\n        inputParameters:\n        - name: card_product_token\n          in: query\n          type: string\n          description: Filter authorization controls by card product token.\n        - name: user_token\n          in: query\n          type: string\n          description: Filter authorization controls by user token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createauthcontrol\n        method: POST\n        description: Create an authorization control\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: authcontrols-token\n      path: /authcontrols/{token}\n      operations:\n      - name: getauthcontrol\n        method: GET\n        description: Retrieve an authorization control\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateauthcontrol\n        method: PUT\n        description: Update an authorization control\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: velocitycontrols\n      path: /velocitycontrols\n      operations:\n      - name: listvelocitycontrols\n        method: GET\n        description: List velocity controls\n        inputParameters:\n        - name: card_product_token\n          in: query\n          type: string\n          description: Filter velocity controls by card product token.\n        - name: user_token\n          in: query\n   \
  \       type: string\n          description: Filter velocity controls by user token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvelocitycontrol\n        method: POST\n        description: Create a velocity control\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: velocitycontrols-token\n      path: /velocitycontrols/{token}\n      operations:\n      - name: getvelocitycontrol\n        method: GET\n        description: Retrieve a velocity control\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatevelocitycontrol\n        method: PUT\n        description: Update a velocity control\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: webhooks\n      path: /webhooks\n      operations:\n      - name: listwebhooks\n        method: GET\n        description: List webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createwebhook\n        method: POST\n        description: Create a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-token\n      path: /webhooks/{token}\n      operations:\n      - name: getwebhook\n        method: GET\n        description: Retrieve a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatewebhook\n        method: PUT\n        description: Update a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: webhooks-token-resend-event-type-resource-token\n      path: /webhooks/{token}/resend/{event_type}/{resource_token}\n      operations:\n      - name: resendwebhookevent\n        method: POST\n        description: Resend a webhook event\n        inputParameters:\n        - name: event_type\n          in: path\n          type: string\n          required: true\n          description: The event type to resend (e.g., transaction.clearing).\n        - name: resource_token\n          in: path\n          type: string\n          required: true\n          description: Token of the resource associated with the event.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kyc\n      path: /kyc\n      operations:\n      - name: createkycverification\n        method: POST\n        description: Create a KYC verification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: kyc-user-user-token\n      path: /kyc/user/{user_token}\n      operations:\n      - name: listkycforuser\n        method: GET\n        description: List KYC verifications for a user\n        inputParameters:\n        - name: user_token\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fundingsources-ach\n      path: /fundingsources/ach\n      operations:\n      - name: createachfundingsource\n        method: POST\n        description: Create an ACH funding source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fundingsources-ach-funding-source-token\n      path: /fundingsources/ach/{funding_source_token}\n      operations:\n  \
  \    - name: getachfundingsource\n        method: GET\n        description: Retrieve an ACH funding source\n        inputParameters:\n        - name: funding_source_token\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the ACH funding source.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fundingsources-program-ach\n      path: /fundingsources/program/ach\n      operations:\n      - name: createprogramachfundingsource\n        method: POST\n        description: Create a program ACH funding source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: programreserve-balances\n      path: /programreserve/balances\n      operations:\n      - name: getprogramreservebalance\n        method: GET\n        description: Retrieve program reserve balance\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: businesses\n      path: /businesses\n      operations:\n      - name: listbusinesses\n        method: GET\n        description: List businesses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbusiness\n        method: POST\n        description: Create a business\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: businesses-token\n      path: /businesses/{token}\n      operations:\n      - name: getbusiness\n        method: GET\n        description: Retrieve a business\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebusiness\n        method: PUT\n        description:\
  \ Update a business\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: marqeta-rest\n    description: REST adapter for Marqeta Core API.\n    resources:\n    - path: /users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: List users\n        call: marqeta.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Create a user\n        call: marqeta.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{token}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Retrieve a user\n        call: marqeta.getuser\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /users/{token}\n      name: updateuser\n      operations:\n      - method: PUT\n        name: updateuser\n        description: Update a user\n        call: marqeta.updateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /usertransitions\n      name: createusertransition\n      operations:\n      - method: POST\n        name: createusertransition\n        description: Create a user transition\n        call: marqeta.createusertransition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /usertransitions/user/{user_token}\n      name: listusertransitions\n      operations:\n      - method: GET\n        name: listusertransitions\n        description: List user transitions\n        call: marqeta.listusertransitions\n        with:\n          user_token: rest.user_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cards\n\
  \      name: listcards\n      operations:\n      - method: GET\n        name: listcards\n        description: List cards for a user\n        call: marqeta.listcards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cards\n      name: createcard\n      operations:\n      - method: POST\n        name: createcard\n        description: Create a card\n        call: marqeta.createcard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cards/{token}\n      name: getcard\n      operations:\n      - method: GET\n        name: getcard\n        description: Retrieve a card\n        call: marqeta.getcard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cards/{token}\n      name: updatecard\n      operations:\n      - method: PUT\n        name: updatecard\n        description: Update a card\n        call: marqeta.updatecard\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /cardtransitions\n      name: createcardtransition\n      operations:\n      - method: POST\n        name: createcardtransition\n        description: Create a card transition\n        call: marqeta.createcardtransition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cardtransitions/card/{card_token}\n      name: listcardtransitions\n      operations:\n      - method: GET\n        name: listcardtransitions\n        description: List card transitions\n        call: marqeta.listcardtransitions\n        with:\n          card_token: rest.card_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cardproducts\n      name: listcardproducts\n      operations:\n      - method: GET\n        name: listcardproducts\n        description: List card products\n        call: marqeta.listcardproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cardproducts\n     \
  \ name: createcardproduct\n      operations:\n      - method: POST\n        name: createcardproduct\n        description: Create a card product\n        call: marqeta.createcardproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cardproducts/{token}\n      name: getcardproduct\n      operations:\n      - method: GET\n        name: getcardproduct\n        description: Retrieve a card product\n        call: marqeta.getcardproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cardproducts/{token}\n      name: updatecardproduct\n      operations:\n      - method: PUT\n        name: updatecardproduct\n        description: Update a card product\n        call: marqeta.updatecardproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transactions\n      name: listtransactions\n      operations:\n      - method: GET\n        name: listtransactions\n        description: List\
  \ transactions\n        call: marqeta.listtransactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transactions/{token}\n      name: gettransaction\n      operations:\n      - method: GET\n        name: gettransaction\n        description: Retrieve a transaction\n        call: marqeta.gettransaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /balances/{token}\n      name: getbalance\n      operations:\n      - method: GET\n        name: getbalance\n        description: Retrieve GPA balance\n        call: marqeta.getbalance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gpaorders\n      name: listgpaorders\n      operations:\n      - method: GET\n        name: listgpaorders\n        description: List GPA orders\n        call: marqeta.listgpaorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gpaorders\n      name: creategpaorder\n\
  \      operations:\n      - method: POST\n        name: creategpaorder\n        description: Create a GPA order\n        call: marqeta.creategpaorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gpaorders/{token}\n      name: getgpaorder\n      operations:\n      - method: GET\n        name: getgpaorder\n        description: Retrieve a GPA order\n        call: marqeta.getgpaorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /authcontrols\n      name: listauthcontrols\n      operations:\n      - method: GET\n        name: listauthcontrols\n        description: List authorization controls\n        call: marqeta.listauthcontrols\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /authcontrols\n      name: createauthcontrol\n      operations:\n      - method: POST\n        name: createauthcontrol\n        description: Create an authorization control\n        call: marqeta.createauthcontrol\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /authcontrols/{token}\n      name: getauthcontrol\n      operations:\n      - method: GET\n        name: getauthcontrol\n        description: Retrieve an authorization control\n        call: marqeta.getauthcontrol\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /authcontrols/{token}\n      name: updateauthcontrol\n      operations:\n      - method: PUT\n        name: updateauthcontrol\n        description: Update an authorization control\n        call: marqeta.updateauthcontrol\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /velocitycontrols\n      name: listvelocitycontrols\n      operations:\n      - method: GET\n        name: listvelocitycontrols\n        description: List velocity controls\n        call: marqeta.listvelocitycontrols\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /velocitycontrols\n      name: createvelocitycontrol\n      operations:\n      - method: POST\n        name: createvelocitycontrol\n        description: Create a velocity control\n        call: marqeta.createvelocitycontrol\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /velocitycontrols/{token}\n      name: getvelocitycontrol\n      operations:\n      - method: GET\n        name: getvelocitycontrol\n        description: Retrieve a velocity control\n        call: marqeta.getvelocitycontrol\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /velocitycontrols/{token}\n      name: updatevelocitycontrol\n      operations:\n      - method: PUT\n        name: updatevelocitycontrol\n        description: Update a velocity control\n        call: marqeta.updatevelocitycontrol\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks\n      name: listwebhooks\n      operations:\n \
  \     - method: GET\n        name: listwebhooks\n        description: List webhooks\n        call: marqeta.listwebhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks\n      name: createwebhook\n      operations:\n      - method: POST\n        name: createwebhook\n        description: Create a webhook\n        call: marqeta.createwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{token}\n      name: getwebhook\n      operations:\n      - method: GET\n        name: getwebhook\n        description: Retrieve a webhook\n        call: marqeta.getwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{token}\n      name: updatewebhook\n      operations:\n      - method: PUT\n        name: updatewebhook\n        description: Update a webhook\n        call: marqeta.updatewebhook\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /webhooks/{token}/resend/{event_type}/{resource_token}\n      name: resendwebhookevent\n      operations:\n      - method: POST\n        name: resendwebhookevent\n        description: Resend a webhook event\n        call: marqeta.resendwebhookevent\n        with:\n          event_type: rest.event_type\n          resource_token: rest.resource_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kyc\n      name: createkycverification\n      operations:\n      - method: POST\n        name: createkycverification\n        description: Create a KYC verification\n        call: marqeta.createkycverification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kyc/user/{user_token}\n      name: listkycforuser\n      operations:\n      - method: GET\n        name: listkycforuser\n        description: List KYC verifications for a user\n        call: marqeta.listkycforuser\n        with:\n          user_token:\
  \ rest.user_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fundingsources/ach\n      name: createachfundingsource\n      operations:\n      - method: POST\n        name: createachfundingsource\n        description: Create an ACH funding source\n        call: marqeta.createachfundingsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fundingsources/ach/{funding_source_token}\n      name: getachfundingsource\n      operations:\n      - method: GET\n        name: getachfundingsource\n        description: Retrieve an ACH funding source\n        call: marqeta.getachfundingsource\n        with:\n          funding_source_token: rest.funding_source_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fundingsources/program/ach\n      name: createprogramachfundingsource\n      operations:\n      - method: POST\n        name: createprogramachfundingsource\n        description:\
  \ Create a program ACH funding source\n        call: marqeta.createprogramachfundingsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /programreserve/balances\n      name: getprogramreservebalance\n      operations:\n      - method: GET\n        name: getprogramreservebalance\n        description: Retrieve program reserve balance\n        call: marqeta.getprogramreservebalance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /businesses\n      name: listbusinesses\n      operations:\n      - method: GET\n        name: listbusinesses\n        description: List businesses\n        call: marqeta.listbusinesses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /businesses\n      name: createbusiness\n      operations:\n      - method: POST\n        name: createbusiness\n        description: Create a business\n        call: marqeta.createbusiness\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /businesses/{token}\n      name: getbusiness\n      operations:\n      - method: GET\n        name: getbusiness\n        description: Retrieve a business\n        call: marqeta.getbusiness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /businesses/{token}\n      name: updatebusiness\n      operations:\n      - method: PUT\n        name: updatebusiness\n        description: Update a business\n        call: marqeta.updatebusiness\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: marqeta-mcp\n    transport: http\n    description: MCP adapter for Marqeta Core API for AI agent use.\n    tools:\n    - name: listusers\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marqeta.listusers\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n    - name: createuser\n      description: Create a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marqeta.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Retrieve a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marqeta.getuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n      description: Update a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: marqeta.updateuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createusertransition\n      description: Create a user transition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marqeta.createusertransition\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listusertransitions\n      description: List user transitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marqeta.listusertransitions\n      with:\n        user_token: tools.user_token\n      inputParameters:\n      - name: user_token\n        type: string\n        description: Unique identifier of the user.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcards\n      description: List cards for a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marqeta.listcards\n      with:\n        user_token: tools.user_token\n        business_token: tools.business_token\n      inputParameters:\n      - name: user_token\n        type: string\n        description: Filter cards by user token.\n      - name: business_token\n        type: string\n        description:\
  \ Filter cards by business token.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcard\n      description: Create a card\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marqeta.createcard\n      with:\n        show_cvv_number: tools.show_cvv_number\n        show_pan: tools.show_pan\n      inputParameters:\n      - name: show_cvv_number\n        type: boolean\n        description: If true, the response includes the card CVV2 value. This is only returned once at card creation.\n      - name: show_pan\n        type: boolean\n        description: If true, the response includes the full 16-digit PAN. This is only returned once at card creation.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcard\n      description\n\n# --- truncated at 32 KB (44 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/marqeta/refs/heads/main/capabilities/marqeta-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/marqeta/refs/heads/main/capabilities/marqeta-capability.yaml
tags:
- Marqeta
- API
tools:
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Create a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Retrieve a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Update a user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Create a user transition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createusertransition
- description: List user transitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusertransitions
- description: List cards for a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcards
- description: Create a card
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcard
- description: Retrieve a card
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcard
- description: Update a card
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecard
- description: Create a card transition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcardtransition
- description: List card transitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcardtransitions
- description: List card products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcardproducts
- description: Create a card product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcardproduct
- description: Retrieve a card product
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcardproduct
- description: Update a card product
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecardproduct
- description: List transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtransactions
- description: Retrieve a transaction
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransaction
- description: Retrieve GPA balance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbalance
- description: List GPA orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgpaorders
- description: Create a GPA order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategpaorder
- description: Retrieve a GPA order
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgpaorder
- description: List authorization controls
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauthcontrols
- description: Create an authorization control
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createauthcontrol
- description: Retrieve an authorization control
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthcontrol
- description: Update an authorization control
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateauthcontrol
- description: List velocity controls
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvelocitycontrols
- description: Create a velocity control
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvelocitycontrol
- description: Retrieve a velocity control
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvelocitycontrol
- description: Update a velocity control
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatevelocitycontrol
- description: List webhooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwebhooks
- description: Create a webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwebhook
- description: Retrieve a webhook
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebhook
- description: Update a webhook
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatewebhook
- description: Resend a webhook event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resendwebhookevent
- description: Create a KYC verification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createkycverification
- description: List KYC verifications for a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listkycforuser
- description: Create an ACH funding source
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createachfundingsource
- description: Retrieve an ACH funding source
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getachfundingsource
- description: Create a program ACH funding source
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprogramachfundingsource
- description: Retrieve program reserve balance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprogramreservebalance
- description: List businesses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbusinesses
- description: Create a business
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbusiness
- description: Retrieve a business
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbusiness
- description: Update a business
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatebusiness
---
