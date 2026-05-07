---
categories: []
consumed_apis: []
description: The PartnerStack API allows you to integrate with the PartnerStack platform to manage partnerships, customers, deals, transactions, rewards, and more.
layout: capability
name: PartnerStack API
operations:
- description: List partnerships
  method: GET
  name: listpartnerships
  path: /partnerships
- description: List customers
  method: GET
  name: listcustomers
  path: /customers
- description: Create a customer
  method: POST
  name: createcustomer
  path: /customers
- description: List deals
  method: GET
  name: listdeals
  path: /deals
- description: List transactions
  method: GET
  name: listtransactions
  path: /transactions
- description: List rewards
  method: GET
  name: listrewards
  path: /rewards
personas: []
provider_name: PartnerStack
provider_slug: partnerstack
search_terms:
- listtransactions
- affiliate
- saas
- create a customer
- listrewards
- listcustomers
- list rewards
- partnerships
- createcustomer
- list deals
- listdeals
- list transactions
- list partnerships
- api
- list customers
- listpartnerships
- partnerstack
slug: partnerstack-capability
source_filename: partnerstack-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PartnerStack API\n  description: The PartnerStack API allows you to integrate with the PartnerStack platform to manage partnerships, customers,\n    deals, transactions, rewards, and more.\n  tags:\n  - Partnerstack\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: partnerstack\n    baseUri: https://api.partnerstack.com/api/v2\n    description: PartnerStack API HTTP API.\n    authentication:\n      type: basic\n      username: '{{PARTNERSTACK_USERNAME}}'\n      password: '{{PARTNERSTACK_PASSWORD}}'\n    resources:\n    - name: partnerships\n      path: /partnerships\n      operations:\n      - name: listpartnerships\n        method: GET\n        description: List partnerships\n        inputParameters:\n        - name: order_by\n          in: query\n          type: string\n        - name: has_sub_id\n          in: query\n          type: boolean\n        - name: include_offers\n\
  \          in: query\n          type: boolean\n        - name: include_archived\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /customers\n      operations:\n      - name: listcustomers\n        method: GET\n        description: List customers\n        inputParameters:\n        - name: group\n          in: query\n          type: string\n        - name: partner_key\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcustomer\n        method: POST\n        description: Create a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deals\n      path: /deals\n      operations:\n      - name: listdeals\n\
  \        method: GET\n        description: List deals\n        inputParameters:\n        - name: group\n          in: query\n          type: string\n        - name: partner_key\n          in: query\n          type: string\n        - name: customer_key\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /transactions\n      operations:\n      - name: listtransactions\n        method: GET\n        description: List transactions\n        inputParameters:\n        - name: order_by\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rewards\n      path: /rewards\n      operations:\n      - name: listrewards\n        method: GET\n        description: List rewards\n        inputParameters:\n        - name:\
  \ payment_status\n          in: query\n          type: string\n        - name: order_by\n          in: query\n          type: string\n        - name: company_key\n          in: query\n          type: string\n        - name: group_key\n          in: query\n          type: string\n        - name: customer_key\n          in: query\n          type: string\n        - name: invoice_key\n          in: query\n          type: string\n        - name: keywords\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: partnerstack-rest\n    description: REST adapter for PartnerStack API.\n    resources:\n    - path: /partnerships\n      name: listpartnerships\n      operations:\n      - method: GET\n        name: listpartnerships\n        description: List partnerships\n        call: partnerstack.listpartnerships\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /customers\n      name: listcustomers\n      operations:\n      - method: GET\n        name: listcustomers\n        description: List customers\n        call: partnerstack.listcustomers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers\n      name: createcustomer\n      operations:\n      - method: POST\n        name: createcustomer\n        description: Create a customer\n        call: partnerstack.createcustomer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deals\n      name: listdeals\n      operations:\n      - method: GET\n        name: listdeals\n        description: List deals\n        call: partnerstack.listdeals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transactions\n      name: listtransactions\n      operations:\n      - method: GET\n        name: listtransactions\n        description:\
  \ List transactions\n        call: partnerstack.listtransactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /rewards\n      name: listrewards\n      operations:\n      - method: GET\n        name: listrewards\n        description: List rewards\n        call: partnerstack.listrewards\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: partnerstack-mcp\n    transport: http\n    description: MCP adapter for PartnerStack API for AI agent use.\n    tools:\n    - name: listpartnerships\n      description: List partnerships\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: partnerstack.listpartnerships\n      with:\n        order_by: tools.order_by\n        has_sub_id: tools.has_sub_id\n        include_offers: tools.include_offers\n        include_archived: tools.include_archived\n      inputParameters:\n      - name: order_by\n\
  \        type: string\n        description: order_by\n      - name: has_sub_id\n        type: boolean\n        description: has_sub_id\n      - name: include_offers\n        type: boolean\n        description: include_offers\n      - name: include_archived\n        type: boolean\n        description: include_archived\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcustomers\n      description: List customers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: partnerstack.listcustomers\n      with:\n        group: tools.group\n        partner_key: tools.partner_key\n      inputParameters:\n      - name: group\n        type: string\n        description: group\n      - name: partner_key\n        type: string\n        description: partner_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcustomer\n      description: Create a customer\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: partnerstack.createcustomer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdeals\n      description: List deals\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: partnerstack.listdeals\n      with:\n        group: tools.group\n        partner_key: tools.partner_key\n        customer_key: tools.customer_key\n      inputParameters:\n      - name: group\n        type: string\n        description: group\n      - name: partner_key\n        type: string\n        description: partner_key\n      - name: customer_key\n        type: array\n        description: customer_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtransactions\n      description: List transactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: partnerstack.listtransactions\n\
  \      with:\n        order_by: tools.order_by\n      inputParameters:\n      - name: order_by\n        type: string\n        description: order_by\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrewards\n      description: List rewards\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: partnerstack.listrewards\n      with:\n        payment_status: tools.payment_status\n        order_by: tools.order_by\n        company_key: tools.company_key\n        group_key: tools.group_key\n        customer_key: tools.customer_key\n        invoice_key: tools.invoice_key\n        keywords: tools.keywords\n      inputParameters:\n      - name: payment_status\n        type: string\n        description: payment_status\n      - name: order_by\n        type: string\n        description: order_by\n      - name: company_key\n        type: string\n        description: company_key\n      - name: group_key\n        type:\
  \ string\n        description: group_key\n      - name: customer_key\n        type: string\n        description: customer_key\n      - name: invoice_key\n        type: string\n        description: invoice_key\n      - name: keywords\n        type: string\n        description: keywords\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PARTNERSTACK_USERNAME: PARTNERSTACK_USERNAME\n    PARTNERSTACK_PASSWORD: PARTNERSTACK_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/partnerstack/refs/heads/main/capabilities/partnerstack-capability.yaml
tags:
- Partnerstack
- API
tools:
- description: List partnerships
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpartnerships
- description: List customers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcustomers
- description: Create a customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcustomer
- description: List deals
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeals
- description: List transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtransactions
- description: List rewards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrewards
---
