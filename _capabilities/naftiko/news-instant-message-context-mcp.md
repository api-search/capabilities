---
categories: []
consumed_apis: []
description: A capability composing news headlines (Bloomberg, Reuters) with Slack/Teams instant messages into one shaped market-news context.
layout: capability
name: News Instant Message Context Mcp
operations:
- description: ''
  method: GET
  name: get-market-news-context
  path: /market-news-context
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- news
- get market news context
- api integration
- im
- get news headlines
- governance
- ai
- spec-driven integration
- context
- mcp
- capabilities
- get channel history
slug: news-instant-message-context-mcp
source_filename: news-instant-message-context-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: News Instant Message Context Mcp\n  description: A capability composing news headlines (Bloomberg, Reuters) with Slack/Teams instant messages into one shaped market-news context.\n  tags: [Naftiko, News, IM, Context]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: bloomberg-env\n  keys: {BLOOMBERG_TOKEN: BLOOMBERG_TOKEN}\n- namespace: slack-env\n  keys: {SLACK_TOKEN: SLACK_TOKEN}\ncapability:\n  consumes:\n  - namespace: bloomberg-news\n    type: http\n    baseUri: https://api.bloomberg.com\n    authentication: {type: bearer, token: '{{BLOOMBERG_TOKEN}}'}\n    resources:\n    - {name: news, path: /eap/news/v1/headlines, operations: [{name: get-news-headlines, method: GET}]}\n  - namespace: slack\n    type: http\n    baseUri: https://slack.com\n    authentication: {type: bearer, token: '{{SLACK_TOKEN}}'}\n    resources:\n    - name: conversation-history\n      path: /api/conversations.history\n      operations:\n\
  \      - {name: get-channel-history, method: GET, inputParameters: [{name: channel, in: query}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: news-instant-message-context-mcp-rest\n    description: REST surface for news + IM context.\n    resources:\n    - {name: market-news-context, path: /market-news-context, operations: [{method: GET, name: get-market-news-context, call: bloomberg-news.get-news-headlines}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: news-instant-message-context-mcp-mcp\n    description: MCP for news + IM context.\n    tools:\n    - {name: get-news-headlines, hints: {readOnly: true}, call: bloomberg-news.get-news-headlines}\n    - name: get-channel-history\n      hints: {readOnly: true}\n      inputParameters: [{name: channel, type: string, required: true}]\n      call: slack.get-channel-history\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: news-instant-message-context-mcp-skills\n\
  \    description: Skill for news + IM context.\n    skills:\n    - name: news-instant-message-context-mcp\n      description: News + IM market context.\n      location: file:///opt/naftiko/skills/news-instant-message-context-mcp\n      allowed-tools: get-news-headlines,get-channel-history\n      tools:\n      - {name: get-news-headlines, from: {sourceNamespace: news-instant-message-context-mcp-mcp, action: get-news-headlines}}\n      - {name: get-channel-history, from: {sourceNamespace: news-instant-message-context-mcp-mcp, action: get-channel-history}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/news-instant-message-context-mcp.yaml
tags:
- Naftiko
- News
- IM
- Context
tools:
- description: ''
  hints:
    readOnly: true
  name: get-news-headlines
- description: ''
  hints:
    readOnly: true
  name: get-channel-history
---
