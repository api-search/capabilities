---
categories: []
consumed_apis: []
description: A bridge capability composing MuleSoft + Salesforce Marketing Cloud into a Customer 360 view for marketing-ops agents.
layout: capability
name: Mulesoft Marketing Cloud Customer 360 Bridge
operations:
- description: ''
  method: GET
  name: get-contact-360
  path: /customers/{{contact_key}}/360
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- customer 360
- spec-driven integration
- mulesoft
- mcp
- capabilities
- naftiko
- api integration
- governance
- get contact 360
- ai
- marketing cloud
slug: mulesoft-marketing-cloud-customer-360-bridge
source_filename: mulesoft-marketing-cloud-customer-360-bridge.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Mulesoft Marketing Cloud Customer 360 Bridge\n  description: A bridge capability composing MuleSoft + Salesforce Marketing Cloud into a Customer 360 view for marketing-ops agents.\n  tags: [Naftiko, MuleSoft, Marketing Cloud, Customer 360]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: salesforce-mc-env\n  keys: {SFMC_HOST: SFMC_HOST, SFMC_TOKEN: SFMC_TOKEN}\ncapability:\n  consumes:\n  - namespace: sfmc\n    type: http\n    baseUri: https://{{SFMC_HOST}}\n    authentication: {type: bearer, token: '{{SFMC_TOKEN}}'}\n    resources:\n    - name: contact\n      path: '/contacts/v1/contacts/{{contact_key}}'\n      operations:\n      - {name: get-mc-contact, method: GET, inputParameters: [{name: contact_key, in: path}]}\n    - {name: data-extensions, path: '/data/v1/customobjectdata/key/{{key}}/rowset', operations: [{name: get-data-extension-rows, method: GET, inputParameters: [{name: key, in: path}]}]}\n  exposes:\n\
  \  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: mulesoft-marketing-cloud-customer-360-bridge-rest\n    description: REST surface for Marketing Cloud Customer 360.\n    resources:\n    - {name: contact-360, path: '/customers/{{contact_key}}/360', operations: [{method: GET, name: get-contact-360, inputParameters: [{name: contact_key, in: path, type: string}], call: sfmc.get-mc-contact}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: mulesoft-marketing-cloud-customer-360-bridge-mcp\n    description: MCP for Marketing Cloud bridge.\n    tools:\n    - name: get-contact-360\n      hints: {readOnly: true}\n      inputParameters: [{name: contact_key, type: string, required: true}]\n      call: sfmc.get-mc-contact\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: mulesoft-marketing-cloud-customer-360-bridge-skills\n    description: Skill for Marketing Cloud bridge.\n    skills:\n    - name: mulesoft-marketing-cloud-customer-360-bridge\n\
  \      description: Marketing Cloud Customer 360.\n      location: file:///opt/naftiko/skills/mulesoft-marketing-cloud-customer-360-bridge\n      allowed-tools: get-contact-360\n      tools:\n      - {name: get-contact-360, from: {sourceNamespace: mulesoft-marketing-cloud-customer-360-bridge-mcp, action: get-contact-360}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/mulesoft-marketing-cloud-customer-360-bridge.yaml
tags:
- Naftiko
- MuleSoft
- Marketing Cloud
- Customer 360
tools:
- description: ''
  hints:
    readOnly: true
  name: get-contact-360
---
