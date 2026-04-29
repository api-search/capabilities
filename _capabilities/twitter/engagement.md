---
categories: []
consumed_apis:
- x-users
- x-direct-messages
- x-spaces
description: Unified workflow for managing user relationships, direct messages, spaces, and community interactions on X. Used by community managers, customer support teams, and engagement specialists.
layout: capability
name: X Engagement and Community Management
operations:
- description: Follow a user
  method: POST
  name: followUser
  path: /v1/engagement/users/{id}/following
- description: Unfollow a user
  method: DELETE
  name: unfollowUser
  path: /v1/engagement/users/{source_user_id}/following/{target_user_id}
- description: Block a user
  method: POST
  name: blockUsers
  path: /v1/engagement/users/{id}/blocking
- description: Unblock a user
  method: DELETE
  name: unblockUsers
  path: /v1/engagement/users/{source_user_id}/blocking/{target_user_id}
- description: Mute a user
  method: POST
  name: muteUser
  path: /v1/engagement/users/{id}/muting
- description: Unmute a user
  method: DELETE
  name: unmuteUser
  path: /v1/engagement/users/{source_user_id}/muting/{target_user_id}
- description: Create a new group DM conversation
  method: POST
  name: createDirectMessagesConversation
  path: /v1/engagement/dm/conversations
- description: Send a DM to an existing conversation
  method: POST
  name: createDirectMessagesByConversationId
  path: /v1/engagement/dm/conversations/{dm_conversation_id}/messages
- description: Get recent DM events
  method: GET
  name: getDirectMessagesEvents
  path: /v1/engagement/dm/events
- description: Search for Spaces by keyword
  method: GET
  name: searchSpaces
  path: /v1/engagement/spaces/search
- description: Get multiple Spaces by IDs
  method: GET
  name: getSpacesByIds
  path: /v1/engagement/spaces
personas:
- description: Builds and maintains communities through engagement and moderation.
  id: community-manager
  name: Community Manager
- description: Handles customer inquiries and issues via direct messages and replies.
  id: customer-support
  name: Customer Support
- description: Manages user relationships, follows, and interaction strategies.
  id: engagement-specialist
  name: Engagement Specialist
provider_name: X (Twitter)
provider_slug: twitter
search_terms:
- createDirectMessagesByConversationId
- retrieve spaces by ids
- post creation, editing, media management, and content analytics.
- create a new group dm conversation
- social media manager
- platform operations
- block a user
- direct messages
- content
- researcher
- manage mutes
- manage following
- unfollowUser
- monitor conversations, search posts, analyze trends, and extract insights.
- follow a user
- community manager
- mute a user
- getDirectMessagesEvents
- conducts academic or market research using x data archives.
- social media
- produces original posts, threads, and media content on x.
- getBlockedUsers
- unfollow a user
- blockUsers
- unmute a user
- ensures data handling meets regulatory and platform compliance requirements.
- advertising
- compliance officer
- get posts shared in a space
- create dm conversations
- creates, schedules, and analyzes social media content across platforms.
- getSpacesPosts
- engagement
- data analyst
- user relationships, direct messaging, spaces, and community interaction.
- get users muted by the authenticated user
- muteUser
- manage blocks
- content creator
- social monitoring, search, trending topics, and sentiment analysis.
- real-time data
- extracts insights from social data through search, streaming, and analytics.
- getDirectMessagesEventsByConversationId
- unblockUsers
- community
- engagement specialist
- searchSpaces
- handles customer inquiries and issues via direct messages and replies.
- data compliance, deletion tracking, and regulatory event monitoring.
- send dm to a conversation
- manages brand presence, campaigns, and content strategy.
- manages data pipelines, streaming ingestion, and compliance data flows.
- get multiple spaces by ids
- get users blocked by the authenticated user
- marketing team
- get dm events
- get recent dm events for the authenticated user
- customer support
- streaming
- search for spaces by keyword
- search spaces
- create, manage, and analyze posts, media, bookmarks, and lists.
- builds and maintains communities through engagement and moderation.
- get recent dm events
- followUser
- x api
- getSpacesByIds
- getMutedUsers
- get dm events for a specific conversation
- send a direct message to an existing conversation
- send a direct message to a user by participant id
- manages user relationships, follows, and interaction strategies.
- manage user relationships, direct messages, spaces, and community interactions.
- data engineer
- microblogging
- retrieve multiple spaces by their ids
- monitors brand mentions, sentiment, and competitive landscape.
- createDirectMessagesByParticipantId
- unblock a user
- spaces
- manage compliance jobs, data streams, and real-time compliance monitoring.
- send a dm to an existing conversation
- createDirectMessagesConversation
- brand manager
- unmuteUser
slug: engagement
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"X Engagement and Community Management\"\n  description: \"Unified workflow for managing user relationships, direct messages, spaces, and community interactions on X. Used by community managers, customer support teams, and engagement specialists.\"\n  tags:\n    - X API\n    - Engagement\n    - Community\n    - Direct Messages\n    - Spaces\n  personas:\n    - community managers\n    - customer support\n    - engagement specialists\n  created: \"2026-04-17\"\n  modified: \"2026-04-17\"\n\nbinds:\n  - namespace: env\n    keys:\n      X_API_BEARER_TOKEN: X_API_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: x-users\n      location: \"./shared/users.yaml\"\n    - import: x-direct-messages\n      location: \"./shared/direct-messages.yaml\"\n    - import: x-spaces\n      location: \"./shared/spaces.yaml\"\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: x-engagement-api\n      resources:\n        - path: /v1/engagement/users/{id}/following\n\
  \          name: following\n          description: \"Manage following\"\n          operations:\n            - method: POST\n              name: followUser\n              description: \"Follow a user\"\n              call: \"x-engagement-api.followUser\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/engagement/users/{source_user_id}/following/{target_user_id}\n          name: unfollow\n          description: \"Unfollow a user\"\n          operations:\n            - method: DELETE\n              name: unfollowUser\n              description: \"Unfollow a user\"\n              call: \"x-engagement-api.unfollowUser\"\n              with:\n                source_user_id: \"rest.source_user_id\"\n                target_user_id: \"rest.target_user_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/engagement/users/{id}/blocking\n          name: blocking\n          description: \"Manage blocks\"\n          operations:\n            - method: POST\n              name: blockUsers\n              description: \"Block a user\"\n              call: \"x-engagement-api.blockUsers\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/engagement/users/{source_user_id}/blocking/{target_user_id}\n          name: unblock\n          description: \"Unblock a user\"\n          operations:\n            - method: DELETE\n              name: unblockUsers\n              description: \"Unblock a user\"\n              call: \"x-engagement-api.unblockUsers\"\n              with:\n                source_user_id: \"rest.source_user_id\"\n                target_user_id: \"rest.target_user_id\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/engagement/users/{id}/muting\n          name: muting\n          description: \"Manage mutes\"\n          operations:\n            - method: POST\n              name: muteUser\n              description: \"Mute a user\"\n              call: \"x-engagement-api.muteUser\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/engagement/users/{source_user_id}/muting/{target_user_id}\n          name: unmute\n          description: \"Unmute a user\"\n          operations:\n            - method: DELETE\n              name: unmuteUser\n              description: \"Unmute a user\"\n              call: \"x-engagement-api.unmuteUser\"\n              with:\n                source_user_id: \"rest.source_user_id\"\n                target_user_id: \"rest.target_user_id\"\n              outputParameters:\n                - type: object\n               \
  \   mapping: \"$.\"\n        - path: /v1/engagement/dm/conversations\n          name: dm-conversations\n          description: \"Create DM conversations\"\n          operations:\n            - method: POST\n              name: createDirectMessagesConversation\n              description: \"Create a new group DM conversation\"\n              call: \"x-engagement-api.createDirectMessagesConversation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/engagement/dm/conversations/{dm_conversation_id}/messages\n          name: dm-by-conversation\n          description: \"Send DM to a conversation\"\n          operations:\n            - method: POST\n              name: createDirectMessagesByConversationId\n              description: \"Send a DM to an existing conversation\"\n              call: \"x-engagement-api.createDirectMessagesByConversationId\"\n              with:\n                dm_conversation_id: \"rest.dm_conversation_id\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/engagement/dm/events\n          name: dm-events\n          description: \"Get DM events\"\n          operations:\n            - method: GET\n              name: getDirectMessagesEvents\n              description: \"Get recent DM events\"\n              call: \"x-engagement-api.getDirectMessagesEvents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/engagement/spaces/search\n          name: spaces-search\n          description: \"Search Spaces\"\n          operations:\n            - method: GET\n              name: searchSpaces\n              description: \"Search for Spaces by keyword\"\n              call: \"x-engagement-api.searchSpaces\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n        - path: /v1/engagement/spaces\n          name: spaces\n          description: \"Retrieve Spaces by IDs\"\n          operations:\n            - method: GET\n              name: getSpacesByIds\n              description: \"Get multiple Spaces by IDs\"\n              call: \"x-engagement-api.getSpacesByIds\"\n              with:\n                ids: \"rest.ids\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: x-engagement-mcp\n      transport: http\n      tools:\n        - name: followUser\n          description: \"Follow a user\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-engagement-mcp.followUser\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: unfollowUser\n          description: \"Unfollow a user\"\n      \
  \    hints:\n            readOnly: false\n            destructive: true\n          call: \"x-engagement-mcp.unfollowUser\"\n          with:\n            source_user_id: \"tools.source_user_id\"\n            target_user_id: \"tools.target_user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: blockUsers\n          description: \"Block a user\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-engagement-mcp.blockUsers\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: unblockUsers\n          description: \"Unblock a user\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"x-engagement-mcp.unblockUsers\"\n          with:\n            source_user_id: \"tools.source_user_id\"\n            target_user_id: \"tools.target_user_id\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getBlockedUsers\n          description: \"Get users blocked by the authenticated user\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-engagement-mcp.getBlockedUsers\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: muteUser\n          description: \"Mute a user\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-engagement-mcp.muteUser\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: unmuteUser\n          description: \"Unmute a user\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"x-engagement-mcp.unmuteUser\"\n          with:\n    \
  \        source_user_id: \"tools.source_user_id\"\n            target_user_id: \"tools.target_user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getMutedUsers\n          description: \"Get users muted by the authenticated user\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-engagement-mcp.getMutedUsers\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: createDirectMessagesConversation\n          description: \"Create a new group DM conversation\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-engagement-mcp.createDirectMessagesConversation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: createDirectMessagesByParticipantId\n          description: \"Send a direct message\
  \ to a user by participant ID\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-engagement-mcp.createDirectMessagesByParticipantId\"\n          with:\n            participant_id: \"tools.participant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: createDirectMessagesByConversationId\n          description: \"Send a direct message to an existing conversation\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"x-engagement-mcp.createDirectMessagesByConversationId\"\n          with:\n            dm_conversation_id: \"tools.dm_conversation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getDirectMessagesEvents\n          description: \"Get recent DM events for the authenticated user\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call:\
  \ \"x-engagement-mcp.getDirectMessagesEvents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getDirectMessagesEventsByConversationId\n          description: \"Get DM events for a specific conversation\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-engagement-mcp.getDirectMessagesEventsByConversationId\"\n          with:\n            dm_conversation_id: \"tools.dm_conversation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: searchSpaces\n          description: \"Search for Spaces by keyword\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-engagement-mcp.searchSpaces\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getSpacesByIds\n          description: \"Retrieve\
  \ multiple Spaces by their IDs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-engagement-mcp.getSpacesByIds\"\n          with:\n            ids: \"tools.ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: getSpacesPosts\n          description: \"Get posts shared in a Space\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"x-engagement-mcp.getSpacesPosts\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/twitter/refs/heads/main/capabilities/engagement.yaml
tags:
- X API
- Engagement
- Community
- Direct Messages
- Spaces
tools:
- description: Follow a user
  hints:
    idempotent: false
    readOnly: false
  name: followUser
- description: Unfollow a user
  hints:
    destructive: true
    readOnly: false
  name: unfollowUser
- description: Block a user
  hints:
    idempotent: false
    readOnly: false
  name: blockUsers
- description: Unblock a user
  hints:
    destructive: true
    readOnly: false
  name: unblockUsers
- description: Get users blocked by the authenticated user
  hints:
    idempotent: true
    readOnly: true
  name: getBlockedUsers
- description: Mute a user
  hints:
    idempotent: false
    readOnly: false
  name: muteUser
- description: Unmute a user
  hints:
    destructive: true
    readOnly: false
  name: unmuteUser
- description: Get users muted by the authenticated user
  hints:
    idempotent: true
    readOnly: true
  name: getMutedUsers
- description: Create a new group DM conversation
  hints:
    idempotent: false
    readOnly: false
  name: createDirectMessagesConversation
- description: Send a direct message to a user by participant ID
  hints:
    idempotent: false
    readOnly: false
  name: createDirectMessagesByParticipantId
- description: Send a direct message to an existing conversation
  hints:
    idempotent: false
    readOnly: false
  name: createDirectMessagesByConversationId
- description: Get recent DM events for the authenticated user
  hints:
    idempotent: true
    readOnly: true
  name: getDirectMessagesEvents
- description: Get DM events for a specific conversation
  hints:
    idempotent: true
    readOnly: true
  name: getDirectMessagesEventsByConversationId
- description: Search for Spaces by keyword
  hints:
    idempotent: true
    readOnly: true
  name: searchSpaces
- description: Retrieve multiple Spaces by their IDs
  hints:
    idempotent: true
    readOnly: true
  name: getSpacesByIds
- description: Get posts shared in a Space
  hints:
    idempotent: true
    readOnly: true
  name: getSpacesPosts
---
