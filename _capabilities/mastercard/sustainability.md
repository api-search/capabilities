---
consumed_apis:
- carbon-calculator
- doconomy-aland
- donate
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
- open banking
- create a donation to environmental causes
- create environmental donation
- get the environmental impact score for a transaction using the aland index
- fraud detection
- get impact score
- payments
- credit cards
- financial services
- carbon footprint
- environmental impact scoring
- environmental cause donations
- donate to environment
- get environmental impact score
- sustainability
- digital identity
- environmental impact
- mastercard
- esg
- carbon footprint calculations
- calculate the carbon footprint of payment transactions
- create a donation to support environmental causes
- calculate carbon footprint from transactions
- calculate carbon footprint
slug: sustainability
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
