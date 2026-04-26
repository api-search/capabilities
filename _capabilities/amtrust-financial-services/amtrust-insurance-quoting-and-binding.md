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
- workers compensation
- developer integrating amtrust api into agent or broker platform
- small business
- amtrust financial services
- createQuote
- end-to-end insurance quoting and binding workflow
- get policy
- generate a commercial lines quote
- list all quotes for the agent account
- check coverage appetite
- bind an approved quote to issue a policy
- check appetite
- check amtrust coverage appetite for a business risk
- list quotes
- agent checking appetite and generating quotes for clients
- getPolicy
- insurance technology
- insurance
- checkAppetite
- create quote
- retrieve policy details by policy number
- commercial lines
- property and casualty
- bind policy
- commercial insurance
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
