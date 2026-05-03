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
- insurance
- commercial insurance
- get policy
- workers compensation
- retrieve policy details by policy number
- insurance technology
- property and casualty
- check coverage appetite
- list all quotes for the agent account
- checkAppetite
- generate a commercial lines quote
- amtrust financial services
- developer integrating amtrust api into agent or broker platform
- bind an approved quote to issue a policy
- check amtrust coverage appetite for a business risk
- getPolicy
- small business
- check appetite
- createQuote
- commercial lines
- list quotes
- agent checking appetite and generating quotes for clients
- end-to-end insurance quoting and binding workflow
- create quote
- bind policy
slug: amtrust-insurance-quoting-and-binding
source_filename: amtrust-insurance-quoting-and-binding.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: AmTrust Insurance Quoting and Binding\n  description: Workflow capability for reviewing appetite, generating quotes, and binding commercial lines policies. Used by insurance agents and broker platforms.\n  tags:\n  - AmTrust Financial Services\n  - Insurance\n  - Commercial Lines\n  - Workers Compensation\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AMTRUST_CLIENT_ID: AMTRUST_CLIENT_ID\n    AMTRUST_CLIENT_SECRET: AMTRUST_CLIENT_SECRET\ncapability:\n  consumes:\n  - import: amtrust-commercial-lines\n    location: ./shared/commercial-lines-api.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amtrust-quoting-api\n    description: REST API for insurance quoting and binding\n    resources:\n    - path: /v1/appetite\n      name: appetite\n      operations:\n      - method: POST\n        name: checkAppetite\n        description: Check coverage appetite\n        call: amtrust-commercial-lines.checkAppetite\n\
  \        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/quotes\n      name: quotes\n      operations:\n      - method: POST\n        name: createQuote\n        description: Create quote\n        call: amtrust-commercial-lines.createQuote\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies\n      name: policies\n      operations:\n      - method: GET\n        name: getPolicy\n        description: Get policy\n        call: amtrust-commercial-lines.getPolicy\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amtrust-quoting-mcp\n    transport: http\n    description: MCP server for AI-assisted insurance quoting and binding\n    tools:\n    - name: check-appetite\n      description: Check AmTrust coverage appetite for a business risk\n      hints:\n        readOnly: false\n      call: amtrust-commercial-lines.checkAppetite\n\
  \      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-quote\n      description: Generate a commercial lines quote\n      hints:\n        readOnly: false\n      call: amtrust-commercial-lines.createQuote\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-quotes\n      description: List all quotes for the agent account\n      hints:\n        readOnly: true\n      call: amtrust-commercial-lines.listQuotes\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bind-policy\n      description: Bind an approved quote to issue a policy\n      hints:\n        readOnly: false\n      call: amtrust-commercial-lines.bindPolicy\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-policy\n      description: Retrieve policy details by policy number\n      hints:\n        readOnly: true\n      call: amtrust-commercial-lines.getPolicy\n\
  \      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amtrust-financial-services/refs/heads/main/capabilities/amtrust-insurance-quoting-and-binding.yaml
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
