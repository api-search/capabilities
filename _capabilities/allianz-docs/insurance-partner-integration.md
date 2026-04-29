---
categories: []
consumed_apis:
- allianz-api-connect
description: Workflow capability for financial institutions and retail partners embedding Allianz Australian insurance products into their customer journeys. Combines quoting, lead referral, policy completion, and certificate retrieval into a unified integration layer.
layout: capability
name: Allianz Insurance Partner Integration
operations:
- description: Create a staff-assisted insurance quote for a customer
  method: POST
  name: create-assisted-quote
  path: /v1/quotes
- description: Email a quote to a customer for their review
  method: POST
  name: send-quote-email
  path: /v1/quotes
- description: Get the current status and details of a quote
  method: GET
  name: get-quote-summary
  path: /v1/quotes/{estimate_id}
- description: Get the rating factors behind a quote premium
  method: GET
  name: get-quote-rating-factors
  path: /v1/quotes/{estimate_id}
- description: Submit a customer lead to the Allianz sales team
  method: POST
  name: submit-lead
  path: /v1/leads
- description: Complete a policy application via staff-assisted workflow
  method: POST
  name: complete-policy-assisted
  path: /v1/policies
- description: Retrieve a Certificate of Currency for a policy
  method: GET
  name: get-certificate
  path: /v1/certificates/{policy_number}
personas: []
provider_name: Allianz
provider_slug: allianz-docs
search_terms:
- quoting
- partner integration
- price estimation and quote generation for end customers
- insurance quoting and estimation resources
- submit lead referral
- get quote summary
- insurance certificate retrieval resources
- create a self-service policy completion session for customer
- create a staff-assisted insurance quote for a customer
- submit a customer lead to the allianz sales team
- create a self-service quote session for a customer to complete via internet banking
- embedded insurance product distribution through partner apis
- financial services
- get the current status and details of a quote
- retrieve the status and summary of an existing insurance quote
- create a staff-assisted insurance price estimate for home, landlord, or car insurance
- complete a policy application via staff-assisted workflow
- unified workflow for partners embedding allianz insurance into customer journeys
- Partner Developer
- get certificate
- developer at a financial institution, broker, or retailer integrating allianz insurance products into their platform
- create self service quote
- submit lead
- policy completion and certificate management
- technical team at banks or lenders embedding insurance offers at the point of sale for mortgages or vehicle loans
- get the detailed premium breakdown and rating factors for an insurance quote
- retrieve an insurance certificate of currency for a bound policy
- create self service policy
- complete policy assisted
- complete an insurance policy application on behalf of a customer
- get quote rating factors
- email an insurance quote to a customer for asynchronous review
- asset management
- insurance lead referral resources
- send quote email
- get certificate of currency
- email a quote to a customer for their review
- create assisted quote
- get the rating factors behind a quote premium
- australia
- retrieve a certificate of currency for a policy
- embedded insurance
- submit a customer insurance lead to the allianz sales team for follow-up
- insurance
- Financial Institution Integration Team
- insurance policy completion resources
- individual quote detail and rating factor resources
slug: insurance-partner-integration
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Allianz Insurance Partner Integration\"\n  description: \"Workflow capability for financial institutions and retail partners embedding Allianz Australian insurance products into their customer journeys. Combines quoting, lead referral, policy completion, and certificate retrieval into a unified integration layer.\"\n  tags:\n    - Insurance\n    - Australia\n    - Partner Integration\n    - Embedded Insurance\n    - Quoting\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ALLIANZ_CLIENT_ID: ALLIANZ_CLIENT_ID\n      ALLIANZ_CLIENT_SECRET: ALLIANZ_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: allianz-api-connect\n      location: ./shared/api-connect.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: allianz-partner-integration-api\n      description: \"Unified REST API for Allianz insurance partner integration workflows.\"\n      resources:\n \
  \       - path: /v1/quotes\n          name: quotes\n          description: \"Insurance quoting and estimation resources\"\n          operations:\n            - method: POST\n              name: create-assisted-quote\n              description: \"Create a staff-assisted insurance quote for a customer\"\n              call: \"allianz-api-connect.create-price-estimate-assisted\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: send-quote-email\n              description: \"Email a quote to a customer for their review\"\n              call: \"allianz-api-connect.send-price-estimate-email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/quotes/{estimate_id}\n          name: quote-detail\n          description: \"Individual quote detail and rating factor resources\"\n          operations:\n            - method: GET\n\
  \              name: get-quote-summary\n              description: \"Get the current status and details of a quote\"\n              call: \"allianz-api-connect.get-price-estimate-summary\"\n              with:\n                estimate_id: \"rest.estimate_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: GET\n              name: get-quote-rating-factors\n              description: \"Get the rating factors behind a quote premium\"\n              call: \"allianz-api-connect.get-price-estimate-rating-factors\"\n              with:\n                estimate_id: \"rest.estimate_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/leads\n          name: leads\n          description: \"Insurance lead referral resources\"\n          operations:\n            - method: POST\n              name: submit-lead\n              description: \"Submit\
  \ a customer lead to the Allianz sales team\"\n              call: \"allianz-api-connect.create-instant-lead-referral\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/policies\n          name: policies\n          description: \"Insurance policy completion resources\"\n          operations:\n            - method: POST\n              name: complete-policy-assisted\n              description: \"Complete a policy application via staff-assisted workflow\"\n              call: \"allianz-api-connect.get-policy-details-assisted\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/certificates/{policy_number}\n          name: certificates\n          description: \"Insurance certificate retrieval resources\"\n          operations:\n            - method: GET\n              name: get-certificate\n              description: \"Retrieve a Certificate of Currency\
  \ for a policy\"\n              call: \"allianz-api-connect.get-certificate-of-currency\"\n              with:\n                policy_number: \"rest.policy_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: allianz-partner-integration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Allianz insurance partner integration workflows.\"\n      tools:\n        - name: create-assisted-quote\n          description: \"Create a staff-assisted insurance price estimate for home, landlord, or car insurance\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"allianz-api-connect.create-price-estimate-assisted\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: send-quote-email\n          description: \"Email an insurance quote to a customer for asynchronous review\"\
  \n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"allianz-api-connect.send-price-estimate-email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-self-service-quote\n          description: \"Create a self-service quote session for a customer to complete via internet banking\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"allianz-api-connect.create-price-estimate-self-service\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-quote-summary\n          description: \"Retrieve the status and summary of an existing insurance quote\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-api-connect.get-price-estimate-summary\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n     \
  \   - name: get-quote-rating-factors\n          description: \"Get the detailed premium breakdown and rating factors for an insurance quote\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-api-connect.get-price-estimate-rating-factors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: submit-lead-referral\n          description: \"Submit a customer insurance lead to the Allianz sales team for follow-up\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"allianz-api-connect.create-instant-lead-referral\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: complete-policy-assisted\n          description: \"Complete an insurance policy application on behalf of a customer\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"allianz-api-connect.get-policy-details-assisted\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-self-service-policy\n          description: \"Create a self-service policy completion session for customer\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"allianz-api-connect.create-policy-details-self-service\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-certificate-of-currency\n          description: \"Retrieve an insurance Certificate of Currency for a bound policy\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"allianz-api-connect.get-certificate-of-currency\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/allianz-docs/refs/heads/main/capabilities/insurance-partner-integration.yaml
tags:
- Insurance
- Australia
- Partner Integration
- Embedded Insurance
- Quoting
tools:
- description: Create a staff-assisted insurance price estimate for home, landlord, or car insurance
  hints:
    openWorld: false
    readOnly: false
  name: create-assisted-quote
- description: Email an insurance quote to a customer for asynchronous review
  hints:
    openWorld: false
    readOnly: false
  name: send-quote-email
- description: Create a self-service quote session for a customer to complete via internet banking
  hints:
    openWorld: false
    readOnly: false
  name: create-self-service-quote
- description: Retrieve the status and summary of an existing insurance quote
  hints:
    openWorld: false
    readOnly: true
  name: get-quote-summary
- description: Get the detailed premium breakdown and rating factors for an insurance quote
  hints:
    openWorld: false
    readOnly: true
  name: get-quote-rating-factors
- description: Submit a customer insurance lead to the Allianz sales team for follow-up
  hints:
    openWorld: false
    readOnly: false
  name: submit-lead-referral
- description: Complete an insurance policy application on behalf of a customer
  hints:
    openWorld: false
    readOnly: false
  name: complete-policy-assisted
- description: Create a self-service policy completion session for customer
  hints:
    openWorld: false
    readOnly: false
  name: create-self-service-policy
- description: Retrieve an insurance Certificate of Currency for a bound policy
  hints:
    openWorld: false
    readOnly: true
  name: get-certificate-of-currency
---
