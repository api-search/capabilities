---
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
- streaming
- real-time data
- manages data pipelines, streaming ingestion, and compliance data flows.
- get users blocked by the authenticated user
- getBlockedUsers
- microblogging
- get posts shared in a space
- manage compliance jobs, data streams, and real-time compliance monitoring.
- x api
- get multiple spaces by ids
- data engineer
- monitor conversations, search posts, analyze trends, and extract insights.
- followUser
- get users muted by the authenticated user
- content
- user relationships, direct messaging, spaces, and community interaction.
- brand manager
- send a direct message to a user by participant id
- createDirectMessagesByConversationId
- researcher
- customer support
- spaces
- data analyst
- getDirectMessagesEvents
- create a new group dm conversation
- builds and maintains communities through engagement and moderation.
- unfollow a user
- content creator
- follow a user
- engagement
- search for spaces by keyword
- community
- community manager
- platform operations
- post creation, editing, media management, and content analytics.
- social media manager
- search spaces
- data compliance, deletion tracking, and regulatory event monitoring.
- send a dm to an existing conversation
- unblock a user
- createDirectMessagesByParticipantId
- searchSpaces
- get recent dm events
- creates, schedules, and analyzes social media content across platforms.
- unblockUsers
- send dm to a conversation
- manage user relationships, direct messages, spaces, and community interactions.
- manage mutes
- marketing team
- manages brand presence, campaigns, and content strategy.
- get dm events for a specific conversation
- getSpacesPosts
- retrieve spaces by ids
- send a direct message to an existing conversation
- unfollowUser
- getMutedUsers
- social media
- get recent dm events for the authenticated user
- block a user
- createDirectMessagesConversation
- blockUsers
- getDirectMessagesEventsByConversationId
- handles customer inquiries and issues via direct messages and replies.
- getSpacesByIds
- social monitoring, search, trending topics, and sentiment analysis.
- extracts insights from social data through search, streaming, and analytics.
- monitors brand mentions, sentiment, and competitive landscape.
- advertising
- manage following
- manage blocks
- mute a user
- unmute a user
- produces original posts, threads, and media content on x.
- conducts academic or market research using x data archives.
- retrieve multiple spaces by their ids
- direct messages
- create dm conversations
- manages user relationships, follows, and interaction strategies.
- get dm events
- muteUser
- ensures data handling meets regulatory and platform compliance requirements.
- unmuteUser
- engagement specialist
- compliance officer
- create, manage, and analyze posts, media, bookmarks, and lists.
slug: engagement
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
