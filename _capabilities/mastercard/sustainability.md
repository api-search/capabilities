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
- donate to environment
- create environmental donation
- fraud detection
- sustainability
- mastercard
- calculate carbon footprint from transactions
- financial services
- environmental impact scoring
- get impact score
- credit cards
- carbon footprint calculations
- get environmental impact score
- digital identity
- calculate the carbon footprint of payment transactions
- environmental impact
- payments
- create a donation to support environmental causes
- open banking
- carbon footprint
- environmental cause donations
- esg
- calculate carbon footprint
- get the environmental impact score for a transaction using the aland index
- create a donation to environmental causes
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
