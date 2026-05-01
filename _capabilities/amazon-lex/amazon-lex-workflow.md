---
categories: []
consumed_apis:
- lex
description: Unified workflow capability for Amazon Lex combining resource management and operations.
layout: capability
name: Amazon Lex Workflow
operations: []
personas: []
provider_name: Amazon Lex
provider_slug: amazon-lex
search_terms:
- workflow
- gets a list of available bots.
- aws
- manages resources and configurations
- unified workflow for amazon lex resource management
- amazon lex
- bots list bots
- integrates api into applications
- bots create bot
- bots describe bot
- provides metadata information about a bot.
- Developer
- Administrator
- creates an amazon lex conversational bot.
slug: amazon-lex-workflow
source_filename: amazon-lex-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Lex Workflow\n  description: Unified workflow capability for Amazon Lex combining resource management and operations.\n  tags:\n  - Amazon Lex\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - import: lex\n    location: ./shared/lex.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lex-api\n    description: REST API for Amazon Lex workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: lex-mcp\n    transport: http\n    description: MCP server for Amazon Lex.\n    tools:\n    - name: bots-create-bot\n      description: Creates an Amazon Lex conversational bot.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: lex.createbot\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: bots-list-bots\n      description: Gets a list of available bots.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lex.listbots\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bots-describe-bot\n      description: Provides metadata information about a bot.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lex.describebot\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-lex/refs/heads/main/capabilities/amazon-lex-workflow.yaml
tags:
- Amazon Lex
- Workflow
tools:
- description: Creates an Amazon Lex conversational bot.
  hints:
    idempotent: false
    readOnly: false
  name: bots-create-bot
- description: Gets a list of available bots.
  hints:
    idempotent: true
    readOnly: true
  name: bots-list-bots
- description: Provides metadata information about a bot.
  hints:
    idempotent: true
    readOnly: true
  name: bots-describe-bot
---
