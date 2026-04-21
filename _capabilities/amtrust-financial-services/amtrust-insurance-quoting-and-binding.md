---
consumed_apis:
- amtrust-commercial-lines
description: Workflow capability for reviewing appetite, generating quotes, and binding commercial lines policies. Used by insurance agents and broker platforms.
layout: capability
name: AmTrust Insurance Quoting and Binding
operations:
- description: Check coverage appetite
  method: POST
  name: checkAppetite
  path: /v1/appetite
- description: Create quote
  method: POST
  name: createQuote
  path: /v1/quotes
- description: Get policy
  method: GET
  name: getPolicy
  path: /v1/policies
personas: []
provider_name: AmTrust Financial Services
provider_slug: amtrust-financial-services
search_terms:
- agent checking appetite and generating quotes for clients
- retrieve policy details by policy number
- list quotes
- developer integrating amtrust api into agent or broker platform
- createQuote
- bind an approved quote to issue a policy
- commercial insurance
- check amtrust coverage appetite for a business risk
- insurance
- insurance technology
- property and casualty
- create quote
- checkAppetite
- commercial lines
- list all quotes for the agent account
- check coverage appetite
- getPolicy
- bind policy
- generate a commercial lines quote
- end-to-end insurance quoting and binding workflow
- get policy
- amtrust financial services
- check appetite
- workers compensation
- small business
slug: amtrust-insurance-quoting-and-binding
tags:
- AmTrust Financial Services
- Insurance
- Commercial Lines
- Workers Compensation
tools:
- description: Check AmTrust coverage appetite for a business risk
  hints:
    readOnly: false
  name: check-appetite
- description: Generate a commercial lines quote
  hints:
    readOnly: false
  name: create-quote
- description: List all quotes for the agent account
  hints:
    readOnly: true
  name: list-quotes
- description: Bind an approved quote to issue a policy
  hints:
    readOnly: false
  name: bind-policy
- description: Retrieve policy details by policy number
  hints:
    readOnly: true
  name: get-policy
---
