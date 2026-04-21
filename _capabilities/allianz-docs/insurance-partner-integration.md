---
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
- get certificate of currency
- quoting
- get quote rating factors
- submit lead
- submit lead referral
- complete a policy application via staff-assisted workflow
- insurance quoting and estimation resources
- technical team at banks or lenders embedding insurance offers at the point of sale for mortgages or vehicle loans
- insurance policy completion resources
- insurance lead referral resources
- partner integration
- create a self-service quote session for a customer to complete via internet banking
- submit a customer insurance lead to the allianz sales team for follow-up
- financial services
- complete policy assisted
- Financial Institution Integration Team
- Partner Developer
- create a staff-assisted insurance quote for a customer
- policy completion and certificate management
- create a self-service policy completion session for customer
- get the rating factors behind a quote premium
- individual quote detail and rating factor resources
- retrieve the status and summary of an existing insurance quote
- developer at a financial institution, broker, or retailer integrating allianz insurance products into their platform
- create self service policy
- asset management
- embedded insurance
- email a quote to a customer for their review
- unified workflow for partners embedding allianz insurance into customer journeys
- australia
- price estimation and quote generation for end customers
- get the current status and details of a quote
- create a staff-assisted insurance price estimate for home, landlord, or car insurance
- send quote email
- create assisted quote
- email an insurance quote to a customer for asynchronous review
- submit a customer lead to the allianz sales team
- get the detailed premium breakdown and rating factors for an insurance quote
- retrieve a certificate of currency for a policy
- insurance certificate retrieval resources
- create self service quote
- retrieve an insurance certificate of currency for a bound policy
- embedded insurance product distribution through partner apis
- get certificate
- insurance
- get quote summary
- complete an insurance policy application on behalf of a customer
slug: insurance-partner-integration
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
