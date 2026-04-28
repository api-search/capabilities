---
categories:
- evidence
- messaging
consumed_apis:
- slack-web-api
description: Search Slack messages and threads in API-eng, api-changes, and release channels for early signal that a backend team shipped an API change before the docs catch up. One of the five enterprise systems where evidence of API change already lives — and usually the earliest one a technical writer can mine.
layout: capability
name: Slack API Change Evidence
operations:
- description: Search Slack messages across workspaces for API change keywords
  method: GET
  name: search-messages
  path: /api/search.messages
- description: Get message history for a specific channel
  method: GET
  name: get-channel-history
  path: /api/conversations.history
- description: Get all replies in a thread for full context on an API change discussion
  method: GET
  name: get-thread-replies
  path: /api/conversations.replies
- description: List channels matching a name pattern such as api-* or release-*
  method: GET
  name: list-api-channels
  path: /api/conversations.list
- description: List bookmarks and saved canvas items in an API channel
  method: GET
  name: list-channel-bookmarks
  path: /api/bookmarks.list
- description: Get information about a specific channel
  method: GET
  name: get-channel-info
  path: /api/conversations.info
personas:
- Technical Writer
- API Program Manager
provider_name: Slack
provider_slug: slack
search_terms:
- search slack messages
- evidence of api change in slack
- get channel history
- get thread replies
- list api channels
- list channel bookmarks
- mine slack for api signal
- five places api change evidence lives
- early signal backend team shipped
- technical writer slack review
- api-eng channel mining
- api-changes channel
- release channel scan
- canvas saved items
- pre-docs api change discovery
- thread context retrieval
- api program manager messaging
- channel name pattern search
- slack api truth
- before docs catch up
slug: api-change-evidence
tags:
- Slack
- API Change
- Evidence
- Messaging
- Channels
tools:
- description: Search Slack messages across workspaces for API change keywords and endpoint mentions
  hints:
    openWorld: false
    readOnly: true
  name: search-messages
- description: Get message history for a specific channel like api-eng or api-changes
  hints:
    openWorld: false
    readOnly: true
  name: get-channel-history
- description: Get all replies in a thread for full context on an API change discussion
  hints:
    openWorld: false
    readOnly: true
  name: get-thread-replies
- description: List channels matching a name pattern such as api-* or release-* to scope a writer's search
  hints:
    openWorld: false
    readOnly: true
  name: list-api-channels
- description: List bookmarks and saved canvas items in an API channel where teams pin spec links
  hints:
    openWorld: false
    readOnly: true
  name: list-channel-bookmarks
- description: Get information about a specific channel including topic and purpose
  hints:
    openWorld: false
    readOnly: true
  name: get-channel-info
---
