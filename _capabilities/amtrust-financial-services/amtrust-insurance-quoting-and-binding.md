---
categories: []
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
- createQuote
- agent checking appetite and generating quotes for clients
- insurance technology
- workers compensation
- insurance
- amtrust financial services
- getPolicy
- list all quotes for the agent account
- list quotes
- generate a commercial lines quote
- end-to-end insurance quoting and binding workflow
- commercial insurance
- get policy
- checkAppetite
- check amtrust coverage appetite for a business risk
- check coverage appetite
- retrieve policy details by policy number
- property and casualty
- small business
- developer integrating amtrust api into agent or broker platform
- commercial lines
- bind an approved quote to issue a policy
- check appetite
- bind policy
- create quote
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
