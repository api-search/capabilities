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
- Developer
- Administrator
- gets a list of available bots.
- bots describe bot
- aws
- workflow
- amazon lex
- provides metadata information about a bot.
- unified workflow for amazon lex resource management
- bots create bot
- creates an amazon lex conversational bot.
- bots list bots
- manages resources and configurations
- integrates api into applications
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
