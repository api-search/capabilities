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
- checkAppetite
- end-to-end insurance quoting and binding workflow
- check amtrust coverage appetite for a business risk
- agent checking appetite and generating quotes for clients
- create quote
- small business
- commercial lines
- amtrust financial services
- generate a commercial lines quote
- bind policy
- bind an approved quote to issue a policy
- developer integrating amtrust api into agent or broker platform
- commercial insurance
- property and casualty
- insurance
- list quotes
- get policy
- getPolicy
- check appetite
- insurance technology
- retrieve policy details by policy number
- workers compensation
- list all quotes for the agent account
- createQuote
- check coverage appetite
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
