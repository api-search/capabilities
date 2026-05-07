---
categories: []
consumed_apis: []
description: The Zendit API provides programmatic access to a global prepaid ecosystem, enabling mobile credit top-ups, data packages, digital gift cards, prepaid utility bill payments, and eSIM products through a unified integration.
layout: capability
name: Zendit API
operations:
- description: Zendit Get Balance
  method: GET
  name: getbalance
  path: /balance
- description: Zendit List Brands
  method: GET
  name: listbrands
  path: /brands
- description: Zendit Get Brand
  method: GET
  name: getbrand
  path: /brands/{brand}
- description: Zendit Get Brand Redemption Instructions
  method: GET
  name: getbrandredemptioninstructions
  path: /brands/{brand}/redemptionInstructions
- description: Zendit List Topup Offers
  method: GET
  name: listtopupoffers
  path: /topups/offers
- description: Zendit Get Topup Offer
  method: GET
  name: gettopupoffer
  path: /topups/offers/{offerId}
- description: Zendit List Topup Purchases
  method: GET
  name: listtopuppurchases
  path: /topups/purchases
- description: Zendit Create Topup Purchase
  method: POST
  name: createtopuppurchase
  path: /topups/purchases
- description: Zendit Get Topup Purchase
  method: GET
  name: gettopuppurchase
  path: /topups/purchases/{transactionId}
- description: Zendit List ESIM Offers
  method: GET
  name: listesimoffers
  path: /esim/offers
- description: Zendit Get ESIM Offer
  method: GET
  name: getesimoffer
  path: /esim/offers/{offerId}
- description: Zendit List ESIM Purchases
  method: GET
  name: listesimpurchases
  path: /esim/purchases
- description: Zendit Create ESIM Purchase
  method: POST
  name: createesimpurchase
  path: /esim/purchases
- description: Zendit Get ESIM Purchase
  method: GET
  name: getesimpurchase
  path: /esim/purchases/{transactionId}
- description: Zendit Get ESIM QR Code
  method: GET
  name: getesimqrcode
  path: /esim/purchases/{transactionId}/qrcode
- description: Zendit Get ESIM Plans
  method: GET
  name: getesimplans
  path: /esim/{iccId}/plans
- description: Zendit Get ESIM Refund
  method: GET
  name: getesimrefund
  path: /esim/purchases/{transactionId}/refund
- description: Zendit Create ESIM Refund
  method: POST
  name: createesimrefund
  path: /esim/purchases/{transactionId}/refund
- description: Zendit List Voucher Offers
  method: GET
  name: listvoucheroffers
  path: /vouchers/offers
- description: Zendit Get Voucher Offer
  method: GET
  name: getvoucheroffer
  path: /vouchers/offers/{offerId}
- description: Zendit List Voucher Purchases
  method: GET
  name: listvoucherpurchases
  path: /vouchers/purchases
- description: Zendit Create Voucher Purchase
  method: POST
  name: createvoucherpurchase
  path: /vouchers/purchases
- description: Zendit Get Voucher Purchase
  method: GET
  name: getvoucherpurchase
  path: /vouchers/purchases/{transactionId}
- description: Zendit List Transactions
  method: GET
  name: listtransactions
  path: /transactions
- description: Zendit Get Transaction
  method: GET
  name: gettransaction
  path: /transactions/{transactionId}
- description: Zendit Lookup Phone Number
  method: GET
  name: lookupphonenumber
  path: /tools/phonenumberlookup/{msisdn}
- description: Zendit Create Report
  method: POST
  name: createreport
  path: /reports
- description: Zendit Get Report
  method: GET
  name: getreport
  path: /reports/{reportId}
- description: Zendit Download Report
  method: GET
  name: downloadreport
  path: /reports/{reportId}/download
personas: []
provider_name: Zendit
provider_slug: zendit
search_terms:
- zendit get voucher purchase
- getreport
- zendit list voucher offers
- zendit list esim offers
- listbrands
- zendit create esim refund
- zendit get topup purchase
- zendit create report
- zendit get balance
- zendit create topup purchase
- api
- zendit get esim offer
- createvoucherpurchase
- createesimpurchase
- zendit get transaction
- gettopuppurchase
- zendit
- zendit get voucher offer
- listesimoffers
- zendit list brands
- zendit download report
- zendit create voucher purchase
- getesimoffer
- zendit list topup purchases
- zendit get esim plans
- zendit list esim purchases
- getesimrefund
- prepaid
- createtopuppurchase
- listtransactions
- gift cards
- listvoucheroffers
- getesimpurchase
- zendit get report
- createesimrefund
- zendit list topup offers
- getesimplans
- zendit list voucher purchases
- listtopupoffers
- zendit get esim refund
- createreport
- zendit create esim purchase
- downloadreport
- gettransaction
- zendit get topup offer
- getvoucherpurchase
- esim
- mobile top-up
- listesimpurchases
- getesimqrcode
- zendit list transactions
- zendit get brand redemption instructions
- listtopuppurchases
- listvoucherpurchases
- getbrandredemptioninstructions
- gettopupoffer
- payments
- getbalance
- zendit get esim qr code
- getvoucheroffer
- lookupphonenumber
- zendit lookup phone number
- getbrand
- zendit get esim purchase
- zendit get brand
slug: zendit-capability
source_filename: zendit-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Zendit API\n  description: The Zendit API provides programmatic access to a global prepaid ecosystem, enabling mobile credit top-ups,\n    data packages, digital gift cards, prepaid utility bill payments, and eSIM products through a unified integration.\n  tags:\n  - Zendit\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: zendit\n    baseUri: https://api.zendit.io/v1\n    description: Zendit API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ZENDIT_TOKEN}}'\n    resources:\n    - name: balance\n      path: /balance\n      operations:\n      - name: getbalance\n        method: GET\n        description: Zendit Get Balance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: brands\n      path: /brands\n      operations:\n      - name: listbrands\n        method: GET\n\
  \        description: Zendit List Brands\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: brands-brand\n      path: /brands/{brand}\n      operations:\n      - name: getbrand\n        method: GET\n        description: Zendit Get Brand\n        inputParameters:\n        - name: brand\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: brands-brand-redemptioninstructions\n      path: /brands/{brand}/redemptionInstructions\n      operations:\n      - name: getbrandredemptioninstructions\n        method: GET\n        description: Zendit Get Brand Redemption Instructions\n        inputParameters:\n        - name: brand\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: topups-offers\n      path: /topups/offers\n      operations:\n      - name: listtopupoffers\n        method: GET\n        description: Zendit List Topup Offers\n        inputParameters:\n        - name: brand\n          in: query\n          type: string\n        - name: subType\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topups-offers-offerid\n      path: /topups/offers/{offerId}\n      operations:\n      - name: gettopupoffer\n        method: GET\n        description: Zendit Get Topup Offer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topups-purchases\n      path: /topups/purchases\n      operations:\n      - name: listtopuppurchases\n        method: GET\n        description:\
  \ Zendit List Topup Purchases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtopuppurchase\n        method: POST\n        description: Zendit Create Topup Purchase\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topups-purchases-transactionid\n      path: /topups/purchases/{transactionId}\n      operations:\n      - name: gettopuppurchase\n        method: GET\n        description: Zendit Get Topup Purchase\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: esim-offers\n      path: /esim/offers\n      operations:\n      - name: listesimoffers\n        method: GET\n        description: Zendit List ESIM Offers\n        inputParameters:\n        - name: regions\n          in: query\n          type: string\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: esim-offers-offerid\n      path: /esim/offers/{offerId}\n      operations:\n      - name: getesimoffer\n        method: GET\n        description: Zendit Get ESIM Offer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: esim-purchases\n      path: /esim/purchases\n      operations:\n      - name: listesimpurchases\n        method: GET\n        description: Zendit List ESIM Purchases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createesimpurchase\n        method: POST\n        description: Zendit Create ESIM Purchase\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: esim-purchases-transactionid\n\
  \      path: /esim/purchases/{transactionId}\n      operations:\n      - name: getesimpurchase\n        method: GET\n        description: Zendit Get ESIM Purchase\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: esim-purchases-transactionid-qrcode\n      path: /esim/purchases/{transactionId}/qrcode\n      operations:\n      - name: getesimqrcode\n        method: GET\n        description: Zendit Get ESIM QR Code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: esim-iccid-plans\n      path: /esim/{iccId}/plans\n      operations:\n      - name: getesimplans\n        method: GET\n        description: Zendit Get ESIM Plans\n        inputParameters:\n        - name: iccId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: esim-purchases-transactionid-refund\n      path: /esim/purchases/{transactionId}/refund\n      operations:\n      - name: getesimrefund\n        method: GET\n        description: Zendit Get ESIM Refund\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createesimrefund\n        method: POST\n        description: Zendit Create ESIM Refund\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vouchers-offers\n      path: /vouchers/offers\n      operations:\n      - name: listvoucheroffers\n        method: GET\n        description: Zendit List Voucher Offers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vouchers-offers-offerid\n      path: /vouchers/offers/{offerId}\n\
  \      operations:\n      - name: getvoucheroffer\n        method: GET\n        description: Zendit Get Voucher Offer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vouchers-purchases\n      path: /vouchers/purchases\n      operations:\n      - name: listvoucherpurchases\n        method: GET\n        description: Zendit List Voucher Purchases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvoucherpurchase\n        method: POST\n        description: Zendit Create Voucher Purchase\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vouchers-purchases-transactionid\n      path: /vouchers/purchases/{transactionId}\n      operations:\n      - name: getvoucherpurchase\n        method: GET\n        description: Zendit\
  \ Get Voucher Purchase\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /transactions\n      operations:\n      - name: listtransactions\n        method: GET\n        description: Zendit List Transactions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-transactionid\n      path: /transactions/{transactionId}\n      operations:\n      - name: gettransaction\n        method: GET\n        description: Zendit Get Transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tools-phonenumberlookup-msisdn\n      path: /tools/phonenumberlookup/{msisdn}\n      operations:\n      - name: lookupphonenumber\n        method: GET\n        description: Zendit Lookup Phone Number\n        inputParameters:\n\
  \        - name: msisdn\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /reports\n      operations:\n      - name: createreport\n        method: POST\n        description: Zendit Create Report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports-reportid\n      path: /reports/{reportId}\n      operations:\n      - name: getreport\n        method: GET\n        description: Zendit Get Report\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports-reportid-download\n      path: /reports/{reportId}/download\n\
  \      operations:\n      - name: downloadreport\n        method: GET\n        description: Zendit Download Report\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: zendit-rest\n    description: REST adapter for Zendit API.\n    resources:\n    - path: /balance\n      name: getbalance\n      operations:\n      - method: GET\n        name: getbalance\n        description: Zendit Get Balance\n        call: zendit.getbalance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /brands\n      name: listbrands\n      operations:\n      - method: GET\n        name: listbrands\n        description: Zendit List Brands\n        call: zendit.listbrands\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /brands/{brand}\n      name: getbrand\n      operations:\n      - method: GET\n        name: getbrand\n        description: Zendit Get Brand\n        call: zendit.getbrand\n        with:\n          brand: rest.brand\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /brands/{brand}/redemptionInstructions\n      name: getbrandredemptioninstructions\n      operations:\n      - method: GET\n        name: getbrandredemptioninstructions\n        description: Zendit Get Brand Redemption Instructions\n        call: zendit.getbrandredemptioninstructions\n        with:\n          brand: rest.brand\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /topups/offers\n      name: listtopupoffers\n      operations:\n      - method: GET\n        name: listtopupoffers\n        description: Zendit List Topup Offers\n        call: zendit.listtopupoffers\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /topups/offers/{offerId}\n      name: gettopupoffer\n      operations:\n      - method: GET\n        name: gettopupoffer\n        description: Zendit Get Topup Offer\n        call: zendit.gettopupoffer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /topups/purchases\n      name: listtopuppurchases\n      operations:\n      - method: GET\n        name: listtopuppurchases\n        description: Zendit List Topup Purchases\n        call: zendit.listtopuppurchases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /topups/purchases\n      name: createtopuppurchase\n      operations:\n      - method: POST\n        name: createtopuppurchase\n        description: Zendit Create Topup Purchase\n        call: zendit.createtopuppurchase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /topups/purchases/{transactionId}\n      name: gettopuppurchase\n\
  \      operations:\n      - method: GET\n        name: gettopuppurchase\n        description: Zendit Get Topup Purchase\n        call: zendit.gettopuppurchase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /esim/offers\n      name: listesimoffers\n      operations:\n      - method: GET\n        name: listesimoffers\n        description: Zendit List ESIM Offers\n        call: zendit.listesimoffers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /esim/offers/{offerId}\n      name: getesimoffer\n      operations:\n      - method: GET\n        name: getesimoffer\n        description: Zendit Get ESIM Offer\n        call: zendit.getesimoffer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /esim/purchases\n      name: listesimpurchases\n      operations:\n      - method: GET\n        name: listesimpurchases\n        description: Zendit List ESIM Purchases\n        call: zendit.listesimpurchases\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /esim/purchases\n      name: createesimpurchase\n      operations:\n      - method: POST\n        name: createesimpurchase\n        description: Zendit Create ESIM Purchase\n        call: zendit.createesimpurchase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /esim/purchases/{transactionId}\n      name: getesimpurchase\n      operations:\n      - method: GET\n        name: getesimpurchase\n        description: Zendit Get ESIM Purchase\n        call: zendit.getesimpurchase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /esim/purchases/{transactionId}/qrcode\n      name: getesimqrcode\n      operations:\n      - method: GET\n        name: getesimqrcode\n        description: Zendit Get ESIM QR Code\n        call: zendit.getesimqrcode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /esim/{iccId}/plans\n\
  \      name: getesimplans\n      operations:\n      - method: GET\n        name: getesimplans\n        description: Zendit Get ESIM Plans\n        call: zendit.getesimplans\n        with:\n          iccId: rest.iccId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /esim/purchases/{transactionId}/refund\n      name: getesimrefund\n      operations:\n      - method: GET\n        name: getesimrefund\n        description: Zendit Get ESIM Refund\n        call: zendit.getesimrefund\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /esim/purchases/{transactionId}/refund\n      name: createesimrefund\n      operations:\n      - method: POST\n        name: createesimrefund\n        description: Zendit Create ESIM Refund\n        call: zendit.createesimrefund\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vouchers/offers\n      name: listvoucheroffers\n      operations:\n      - method:\
  \ GET\n        name: listvoucheroffers\n        description: Zendit List Voucher Offers\n        call: zendit.listvoucheroffers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vouchers/offers/{offerId}\n      name: getvoucheroffer\n      operations:\n      - method: GET\n        name: getvoucheroffer\n        description: Zendit Get Voucher Offer\n        call: zendit.getvoucheroffer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vouchers/purchases\n      name: listvoucherpurchases\n      operations:\n      - method: GET\n        name: listvoucherpurchases\n        description: Zendit List Voucher Purchases\n        call: zendit.listvoucherpurchases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vouchers/purchases\n      name: createvoucherpurchase\n      operations:\n      - method: POST\n        name: createvoucherpurchase\n        description: Zendit Create Voucher\
  \ Purchase\n        call: zendit.createvoucherpurchase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vouchers/purchases/{transactionId}\n      name: getvoucherpurchase\n      operations:\n      - method: GET\n        name: getvoucherpurchase\n        description: Zendit Get Voucher Purchase\n        call: zendit.getvoucherpurchase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transactions\n      name: listtransactions\n      operations:\n      - method: GET\n        name: listtransactions\n        description: Zendit List Transactions\n        call: zendit.listtransactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transactions/{transactionId}\n      name: gettransaction\n      operations:\n      - method: GET\n        name: gettransaction\n        description: Zendit Get Transaction\n        call: zendit.gettransaction\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /tools/phonenumberlookup/{msisdn}\n      name: lookupphonenumber\n      operations:\n      - method: GET\n        name: lookupphonenumber\n        description: Zendit Lookup Phone Number\n        call: zendit.lookupphonenumber\n        with:\n          msisdn: rest.msisdn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports\n      name: createreport\n      operations:\n      - method: POST\n        name: createreport\n        description: Zendit Create Report\n        call: zendit.createreport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports/{reportId}\n      name: getreport\n      operations:\n      - method: GET\n        name: getreport\n        description: Zendit Get Report\n        call: zendit.getreport\n        with:\n          reportId: rest.reportId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports/{reportId}/download\n\
  \      name: downloadreport\n      operations:\n      - method: GET\n        name: downloadreport\n        description: Zendit Download Report\n        call: zendit.downloadreport\n        with:\n          reportId: rest.reportId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: zendit-mcp\n    transport: http\n    description: MCP adapter for Zendit API for AI agent use.\n    tools:\n    - name: getbalance\n      description: Zendit Get Balance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.getbalance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbrands\n      description: Zendit List Brands\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.listbrands\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbrand\n      description:\
  \ Zendit Get Brand\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.getbrand\n      with:\n        brand: tools.brand\n      inputParameters:\n      - name: brand\n        type: string\n        description: brand\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbrandredemptioninstructions\n      description: Zendit Get Brand Redemption Instructions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.getbrandredemptioninstructions\n      with:\n        brand: tools.brand\n      inputParameters:\n      - name: brand\n        type: string\n        description: brand\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtopupoffers\n      description: Zendit List Topup Offers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: zendit.listtopupoffers\n      with:\n        brand: tools.brand\n        subType: tools.subType\n      inputParameters:\n      - name: brand\n        type: string\n        description: brand\n      - name: subType\n        type: string\n        description: subType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettopupoffer\n      description: Zendit Get Topup Offer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.gettopupoffer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtopuppurchases\n      description: Zendit List Topup Purchases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.listtopuppurchases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtopuppurchase\n      description: Zendit Create Topup Purchase\n      hints:\n     \
  \   readOnly: false\n        destructive: false\n        idempotent: false\n      call: zendit.createtopuppurchase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettopuppurchase\n      description: Zendit Get Topup Purchase\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.gettopuppurchase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listesimoffers\n      description: Zendit List ESIM Offers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.listesimoffers\n      with:\n        regions: tools.regions\n      inputParameters:\n      - name: regions\n        type: string\n        description: regions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getesimoffer\n      description: Zendit Get ESIM Offer\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: zendit.getesimoffer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listesimpurchases\n      description: Zendit List ESIM Purchases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.listesimpurchases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createesimpurchase\n      description: Zendit Create ESIM Purchase\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zendit.createesimpurchase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getesimpurchase\n      description: Zendit Get ESIM Purchase\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.getesimpurchase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getesimqrcode\n      description:\
  \ Zendit Get ESIM QR Code\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.getesimqrcode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getesimplans\n      description: Zendit Get ESIM Plans\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.getesimplans\n      with:\n        iccId: tools.iccId\n      inputParameters:\n      - name: iccId\n        type: string\n        description: iccId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getesimrefund\n      description: Zendit Get ESIM Refund\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.getesimrefund\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createesimrefund\n      description: Zendit Create ESIM Refund\n      hints:\n   \
  \     readOnly: false\n        destructive: false\n        idempotent: false\n      call: zendit.createesimrefund\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvoucheroffers\n      description: Zendit List Voucher Offers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.listvoucheroffers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvoucheroffer\n      description: Zendit Get Voucher Offer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.getvoucheroffer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvoucherpurchases\n      description: Zendit List Voucher Purchases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.listvoucherpurchases\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: createvoucherpurchase\n      description: Zendit Create Voucher Purchase\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zendit.createvoucherpurchase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvoucherpurchase\n      description: Zendit Get Voucher Purchase\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.getvoucherpurchase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtransactions\n      description: Zendit List Transactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.listtransactions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettransaction\n      description: Zendit Get Transaction\n      hints:\n        readOnly: true\n        destructive: false\n     \
  \   idempotent: true\n      call: zendit.gettransaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookupphonenumber\n      description: Zendit Lookup Phone Number\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.lookupphonenumber\n      with:\n        msisdn: tools.msisdn\n      inputParameters:\n      - name: msisdn\n        type: string\n        description: msisdn\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createreport\n      description: Zendit Create Report\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zendit.createreport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreport\n      description: Zendit Get Report\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.getreport\n\
  \      with:\n        reportId: tools.reportId\n      inputParameters:\n      - name: reportId\n        type: string\n        description: reportId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: downloadreport\n      description: Zendit Download Report\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zendit.downloadreport\n      with:\n        reportId: tools.reportId\n      inputParameters:\n      - name: reportId\n        type: string\n        description: reportId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ZENDIT_TOKEN: ZENDIT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zendit/refs/heads/main/capabilities/zendit-capability.yaml
tags:
- Zendit
- API
tools:
- description: Zendit Get Balance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbalance
- description: Zendit List Brands
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbrands
- description: Zendit Get Brand
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbrand
- description: Zendit Get Brand Redemption Instructions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbrandredemptioninstructions
- description: Zendit List Topup Offers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtopupoffers
- description: Zendit Get Topup Offer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopupoffer
- description: Zendit List Topup Purchases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtopuppurchases
- description: Zendit Create Topup Purchase
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtopuppurchase
- description: Zendit Get Topup Purchase
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopuppurchase
- description: Zendit List ESIM Offers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listesimoffers
- description: Zendit Get ESIM Offer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getesimoffer
- description: Zendit List ESIM Purchases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listesimpurchases
- description: Zendit Create ESIM Purchase
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createesimpurchase
- description: Zendit Get ESIM Purchase
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getesimpurchase
- description: Zendit Get ESIM QR Code
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getesimqrcode
- description: Zendit Get ESIM Plans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getesimplans
- description: Zendit Get ESIM Refund
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getesimrefund
- description: Zendit Create ESIM Refund
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createesimrefund
- description: Zendit List Voucher Offers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvoucheroffers
- description: Zendit Get Voucher Offer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvoucheroffer
- description: Zendit List Voucher Purchases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvoucherpurchases
- description: Zendit Create Voucher Purchase
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvoucherpurchase
- description: Zendit Get Voucher Purchase
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvoucherpurchase
- description: Zendit List Transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtransactions
- description: Zendit Get Transaction
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransaction
- description: Zendit Lookup Phone Number
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: lookupphonenumber
- description: Zendit Create Report
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createreport
- description: Zendit Get Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreport
- description: Zendit Download Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadreport
---
