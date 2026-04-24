---
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
- manages resources and configurations
- bots describe bot
- integrates api into applications
- provides metadata information about a bot.
- bots create bot
- gets a list of available bots.
- Developer
- Administrator
- amazon lex
- bots list bots
- unified workflow for amazon lex resource management
- aws
- creates an amazon lex conversational bot.
- workflow
slug: amazon-lex-workflow
tags:
- Amazon Lex
- AWS
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
