---
categories: []
consumed_apis: []
description: Unified workflow for ESG and sustainability teams to calculate carbon footprints, measure environmental impact, and enable cardholders to support environmental causes through their spending data.
layout: capability
name: Mastercard Sustainability
operations:
- description: Calculate carbon footprint from transactions
  method: POST
  name: calculate-carbon-footprint
  path: /v1/carbon-footprint
- description: Get environmental impact score
  method: POST
  name: get-impact-score
  path: /v1/environmental-impact
- description: Create a donation to environmental causes
  method: POST
  name: create-environmental-donation
  path: /v1/environmental-donations
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- environmental impact scoring
- carbon footprint
- carbon footprint calculations
- create a donation to environmental causes
- fraud detection
- create a donation to support environmental causes
- get environmental impact score
- calculate the carbon footprint of payment transactions
- financial services
- get impact score
- get the environmental impact score for a transaction using the aland index
- credit cards
- create environmental donation
- esg
- calculate carbon footprint
- calculate carbon footprint from transactions
- environmental cause donations
- sustainability
- open banking
- payments
- donate to environment
- environmental impact
- digital identity
- mastercard
slug: sustainability
source_filename: sustainability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Sustainability\n  description: Unified workflow for ESG and sustainability teams to calculate carbon footprints, measure environmental impact,\n    and enable cardholders to support environmental causes through their spending data.\n  tags:\n  - Mastercard\n  - Sustainability\n  - Carbon Footprint\n  - ESG\n  - Environmental Impact\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: carbon-calculator\n    baseUri: https://api.mastercard.com/carbon-calculator\n    description: Mastercard Carbon Calculator API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: calculations\n      path: /calculations\n      description:\
  \ Carbon footprint calculations\n      operations:\n      - name: calculate-footprint\n        method: POST\n        description: Calculate carbon footprint from transactions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            transactions: '{{tools.transactions}}'\n  - type: http\n    namespace: doconomy-aland\n    baseUri: https://api.mastercard.com/doconomy/aland-index\n    description: Mastercard Doconomy Aland Index API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: index\n      path: /index\n      description: Aland Index operations\n      operations:\n      - name: get-impact-score\n        method: POST\n        description: Get environmental impact score for a transaction\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            transaction: '{{tools.transaction}}'\n  - type: http\n    namespace: donate\n    baseUri: https://api.mastercard.com/donate\n    description: Mastercard Donate API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: donations\n      path: /donations\n      description: Donation operations\n      operations:\n      - name: create-donation\n        method: POST\n        description: Create a donation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            donation: '{{tools.donation}}'\n  exposes:\n  - type: rest\n    port: 8090\n    namespace: sustainability-api\n    description: Unified REST API for sustainability\
  \ and environmental impact.\n    resources:\n    - path: /v1/carbon-footprint\n      name: carbon-footprint\n      description: Carbon footprint calculations\n      operations:\n      - method: POST\n        name: calculate-carbon-footprint\n        description: Calculate carbon footprint from transactions\n        call: carbon-calculator.calculate-footprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/environmental-impact\n      name: environmental-impact\n      description: Environmental impact scoring\n      operations:\n      - method: POST\n        name: get-impact-score\n        description: Get environmental impact score\n        call: doconomy-aland.get-impact-score\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/environmental-donations\n      name: environmental-donations\n      description: Environmental cause donations\n      operations:\n      - method: POST\n        name: create-environmental-donation\n\
  \        description: Create a donation to environmental causes\n        call: donate.create-donation\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9100\n    namespace: sustainability-mcp\n    transport: http\n    description: MCP server for AI-assisted sustainability and environmental impact analysis.\n    tools:\n    - name: calculate-carbon-footprint\n      description: Calculate the carbon footprint of payment transactions\n      hints:\n        readOnly: true\n      call: carbon-calculator.calculate-footprint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-environmental-impact-score\n      description: Get the environmental impact score for a transaction using the Aland Index\n      hints:\n        readOnly: true\n      call: doconomy-aland.get-impact-score\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: donate-to-environment\n      description: Create a donation\
  \ to support environmental causes\n      hints:\n        readOnly: false\n      call: donate.create-donation\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/sustainability.yaml
tags:
- Mastercard
- Sustainability
- Carbon Footprint
- ESG
- Environmental Impact
tools:
- description: Calculate the carbon footprint of payment transactions
  hints:
    readOnly: true
  name: calculate-carbon-footprint
- description: Get the environmental impact score for a transaction using the Aland Index
  hints:
    readOnly: true
  name: get-environmental-impact-score
- description: Create a donation to support environmental causes
  hints:
    readOnly: false
  name: donate-to-environment
---
