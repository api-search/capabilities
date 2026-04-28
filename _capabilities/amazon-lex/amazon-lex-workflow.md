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
- creates an amazon lex conversational bot.
- gets a list of available bots.
- workflow
- aws
- Administrator
- Developer
- manages resources and configurations
- bots create bot
- bots list bots
- integrates api into applications
- amazon lex
- provides metadata information about a bot.
- bots describe bot
- unified workflow for amazon lex resource management
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
