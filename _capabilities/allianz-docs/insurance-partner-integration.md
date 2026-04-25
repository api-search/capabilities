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
- price estimation and quote generation for end customers
- insurance lead referral resources
- create a self-service quote session for a customer to complete via internet banking
- create self service quote
- embedded insurance product distribution through partner apis
- email an insurance quote to a customer for asynchronous review
- create a staff-assisted insurance price estimate for home, landlord, or car insurance
- create self service policy
- send quote email
- submit a customer insurance lead to the allianz sales team for follow-up
- insurance certificate retrieval resources
- partner integration
- create a staff-assisted insurance quote for a customer
- complete a policy application via staff-assisted workflow
- get certificate of currency
- developer at a financial institution, broker, or retailer integrating allianz insurance products into their platform
- Partner Developer
- email a quote to a customer for their review
- asset management
- get certificate
- insurance policy completion resources
- insurance
- create assisted quote
- policy completion and certificate management
- retrieve an insurance certificate of currency for a bound policy
- get the detailed premium breakdown and rating factors for an insurance quote
- technical team at banks or lenders embedding insurance offers at the point of sale for mortgages or vehicle loans
- quoting
- australia
- create a self-service policy completion session for customer
- submit lead
- financial services
- retrieve a certificate of currency for a policy
- insurance quoting and estimation resources
- complete policy assisted
- unified workflow for partners embedding allianz insurance into customer journeys
- get the rating factors behind a quote premium
- individual quote detail and rating factor resources
- complete an insurance policy application on behalf of a customer
- embedded insurance
- submit lead referral
- retrieve the status and summary of an existing insurance quote
- get the current status and details of a quote
- get quote summary
- get quote rating factors
- submit a customer lead to the allianz sales team
- Financial Institution Integration Team
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
