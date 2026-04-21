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
- create a staff-assisted insurance quote for a customer
- retrieve the status and summary of an existing insurance quote
- partner integration
- create a self-service quote session for a customer to complete via internet banking
- asset management
- insurance quoting and estimation resources
- Financial Institution Integration Team
- complete an insurance policy application on behalf of a customer
- retrieve a certificate of currency for a policy
- retrieve an insurance certificate of currency for a bound policy
- individual quote detail and rating factor resources
- submit a customer insurance lead to the allianz sales team for follow-up
- submit a customer lead to the allianz sales team
- get quote rating factors
- create a self-service policy completion session for customer
- unified workflow for partners embedding allianz insurance into customer journeys
- get quote summary
- insurance
- embedded insurance
- create self service quote
- get the current status and details of a quote
- insurance certificate retrieval resources
- get the detailed premium breakdown and rating factors for an insurance quote
- send quote email
- insurance policy completion resources
- embedded insurance product distribution through partner apis
- financial services
- price estimation and quote generation for end customers
- complete policy assisted
- get certificate of currency
- Partner Developer
- submit lead referral
- create assisted quote
- quoting
- australia
- complete a policy application via staff-assisted workflow
- get certificate
- developer at a financial institution, broker, or retailer integrating allianz insurance products into their platform
- technical team at banks or lenders embedding insurance offers at the point of sale for mortgages or vehicle loans
- email a quote to a customer for their review
- create self service policy
- get the rating factors behind a quote premium
- insurance lead referral resources
- create a staff-assisted insurance price estimate for home, landlord, or car insurance
- email an insurance quote to a customer for asynchronous review
- submit lead
- policy completion and certificate management
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
