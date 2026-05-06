---
categories: []
consumed_apis: []
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
- getMutedUsers
- community manager
- data engineer
- community
- content
- create dm conversations
- followUser
- manage compliance jobs, data streams, and real-time compliance monitoring.
- getSpacesByIds
- send a direct message to a user by participant id
- retrieve spaces by ids
- getDirectMessagesEvents
- manages user relationships, follows, and interaction strategies.
- researcher
- conducts academic or market research using x data archives.
- x api
- platform operations
- advertising
- createDirectMessagesConversation
- getBlockedUsers
- streaming
- manage mutes
- get dm events
- post creation, editing, media management, and content analytics.
- follow a user
- direct messages
- getDirectMessagesEventsByConversationId
- send a direct message to an existing conversation
- manage following
- unblock a user
- getSpacesPosts
- get users muted by the authenticated user
- send dm to a conversation
- extracts insights from social data through search, streaming, and analytics.
- user relationships, direct messaging, spaces, and community interaction.
- blockUsers
- social monitoring, search, trending topics, and sentiment analysis.
- brand manager
- handles customer inquiries and issues via direct messages and replies.
- unfollowUser
- real-time data
- engagement
- send a dm to an existing conversation
- get recent dm events
- content creator
- data compliance, deletion tracking, and regulatory event monitoring.
- get dm events for a specific conversation
- monitor conversations, search posts, analyze trends, and extract insights.
- create a new group dm conversation
- search spaces
- mute a user
- produces original posts, threads, and media content on x.
- create, manage, and analyze posts, media, bookmarks, and lists.
- social media manager
- manage blocks
- get recent dm events for the authenticated user
- unfollow a user
- ensures data handling meets regulatory and platform compliance requirements.
- manages data pipelines, streaming ingestion, and compliance data flows.
- manages brand presence, campaigns, and content strategy.
- unmuteUser
- get multiple spaces by ids
- block a user
- builds and maintains communities through engagement and moderation.
- data analyst
- compliance officer
- get users blocked by the authenticated user
- muteUser
- unblockUsers
- marketing team
- creates, schedules, and analyzes social media content across platforms.
- searchSpaces
- retrieve multiple spaces by their ids
- unmute a user
- search for spaces by keyword
- createDirectMessagesByParticipantId
- engagement specialist
- spaces
- microblogging
- monitors brand mentions, sentiment, and competitive landscape.
- customer support
- manage user relationships, direct messages, spaces, and community interactions.
- get posts shared in a space
- social media
- createDirectMessagesByConversationId
slug: engagement
source_filename: engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: X Engagement and Community Management\n  description: Unified workflow for managing user relationships, direct messages, spaces, and community interactions on X.\n    Used by community managers, customer support teams, and engagement specialists.\n  tags:\n  - X API\n  - Engagement\n  - Community\n  - Direct Messages\n  - Spaces\n  personas:\n  - community managers\n  - customer support\n  - engagement specialists\n  created: '2026-04-17'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    X_API_BEARER_TOKEN: X_API_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: x-users\n    baseUri: https://api.x.com\n    description: X API v2 endpoints for user management, follows, blocks, and mutes.\n    authentication:\n      type: bearer\n      token: '{{X_API_BEARER_TOKEN}}'\n    resources:\n    - name: users\n      path: /2\n      description: Look up users by ID, username, or authenticated user.\n      operations:\n\
  \      - name: getUsersByIds\n        method: GET\n        path: /users\n        description: Retrieve multiple users by their IDs.\n        inputParameters:\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of user IDs\n        - name: user.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of user fields to return\n        - name: expansions\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of expansions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUsersByUsernames\n        method: GET\n        path: /users/by\n        description: Retrieve multiple users by their usernames.\n        inputParameters:\n        - name: usernames\n          in: query\n          type:\
  \ string\n          required: true\n          description: Comma-separated list of usernames\n        - name: user.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of user fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUsersByUsername\n        method: GET\n        path: /users/by/username/{username}\n        description: Retrieve a single user by username.\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: The username to look up\n        - name: user.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of user fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: getUsersMe\n        method: GET\n        path: /users/me\n        description: Retrieve the authenticated user's profile.\n        inputParameters:\n        - name: user.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of user fields to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: follows\n      path: /2\n      description: Manage follow relationships.\n      operations:\n      - name: followUser\n        method: POST\n        path: /users/{id}/following\n        description: Follow a user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: unfollowUser\n        method: DELETE\n        path: /users/{source_user_id}/following/{target_user_id}\n        description: Unfollow a user.\n        inputParameters:\n        - name: source_user_id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: target_user_id\n          in: path\n          type: string\n          required: true\n          description: The user ID to unfollow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getFollowers\n        method: GET\n        path: /users/{id}/followers\n        description: Get followers of a user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        - name: max_results\n          in: query\n          type:\
  \ integer\n          required: false\n          description: Maximum number of results (1-1000)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getFollowing\n        method: GET\n        path: /users/{id}/following\n        description: Get users that a user is following.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-1000)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blocks\n      path: /2\n      description: Manage block relationships.\n      operations:\n      - name: blockUsers\n        method: POST\n        path: /users/{id}/blocking\n        description: Block a user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unblockUsers\n        method: DELETE\n        path: /users/{source_user_id}/blocking/{target_user_id}\n        description: Unblock a user.\n        inputParameters:\n        - name: source_user_id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        -\
  \ name: target_user_id\n          in: path\n          type: string\n          required: true\n          description: The user ID to unblock\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getBlockedUsers\n        method: GET\n        path: /users/{id}/blocking\n        description: Get users blocked by the authenticated user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n    - name: mutes\n      path: /2\n      description: Manage mute relationships.\n      operations:\n      - name: muteUser\n        method: POST\n        path: /users/{id}/muting\n        description: Mute a user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unmuteUser\n        method: DELETE\n        path: /users/{source_user_id}/muting/{target_user_id}\n        description: Unmute a user.\n        inputParameters:\n        - name: source_user_id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: target_user_id\n          in: path\n          type: string\n          required: true\n  \
  \        description: The user ID to unmute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getMutedUsers\n        method: GET\n        path: /users/{id}/muting\n        description: Get users muted by the authenticated user.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The authenticated user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: x-direct-messages\n    baseUri: https://api.x.com\n\
  \    description: X API v2 endpoints for direct messages and conversations.\n    authentication:\n      type: bearer\n      token: '{{X_API_BEARER_TOKEN}}'\n    resources:\n    - name: conversations\n      path: /2\n      description: Create and manage direct message conversations.\n      operations:\n      - name: createDirectMessagesConversation\n        method: POST\n        path: /dm_conversations\n        description: Create a new group DM conversation.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createDirectMessagesByParticipantId\n        method: POST\n        path: /dm_conversations/with/{participant_id}/messages\n        description: Send a direct message to a user by participant ID, creating a 1-1 conversation if needed.\n        inputParameters:\n        - name: participant_id\n          in: path\n          type: string\n          required: true\n\
  \          description: The participant user ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createDirectMessagesByConversationId\n        method: POST\n        path: /dm_conversations/{dm_conversation_id}/messages\n        description: Send a direct message to an existing conversation.\n        inputParameters:\n        - name: dm_conversation_id\n          in: path\n          type: string\n          required: true\n          description: The DM conversation ID\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /2\n      description: Retrieve direct message events.\n      operations:\n      - name: getDirectMessagesEvents\n        method: GET\n        path: /dm_events\n        description: Get recent DM events\
  \ for the authenticated user.\n        inputParameters:\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-100)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        - name: dm_event.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of DM event fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getDirectMessagesEventsByConversationId\n        method: GET\n        path: /dm_conversations/{dm_conversation_id}/dm_events\n        description: Get DM events for a specific conversation.\n        inputParameters:\n        - name: dm_conversation_id\n          in: path\n          type: string\n          required: true\n\
  \          description: The DM conversation ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (1-100)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getDirectMessagesEventsByParticipantId\n        method: GET\n        path: /dm_conversations/with/{participant_id}/dm_events\n        description: Get DM events for a 1-1 conversation with a specific user.\n        inputParameters:\n        - name: participant_id\n          in: path\n          type: string\n          required: true\n          description: The participant user ID\n        - name: max_results\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Maximum number of results (1-100)\n        - name: pagination_token\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getDirectMessagesEventsById\n        method: GET\n        path: /dm_events/{event_id}\n        description: Get a specific DM event by its ID.\n        inputParameters:\n        - name: event_id\n          in: path\n          type: string\n          required: true\n          description: The DM event ID\n        - name: dm_event.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of DM event fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: media\n      path: /2\n      description: Download media\
  \ from DM conversations.\n      operations:\n      - name: dmConversationsMediaDownload\n        method: GET\n        path: /dm_conversations/{dm_conversation_id}/media/{media_id}\n        description: Download media from a DM conversation.\n        inputParameters:\n        - name: dm_conversation_id\n          in: path\n          type: string\n          required: true\n          description: The DM conversation ID\n        - name: media_id\n          in: path\n          type: string\n          required: true\n          description: The media ID to download\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: delete\n      path: /2\n      description: Delete direct messages.\n      operations:\n      - name: deleteDirectMessageById\n        method: DELETE\n        path: /dm_events/{event_id}\n        description: Delete a direct message event by its ID.\n        inputParameters:\n        - name: event_id\n\
  \          in: path\n          type: string\n          required: true\n          description: The DM event ID to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: x-spaces\n    baseUri: https://api.x.com\n    description: X API v2 endpoints for Spaces.\n    authentication:\n      type: bearer\n      token: '{{X_API_BEARER_TOKEN}}'\n    resources:\n    - name: spaces\n      path: /2\n      description: Retrieve and search Spaces.\n      operations:\n      - name: getSpacesByIds\n        method: GET\n        path: /spaces\n        description: Retrieve multiple Spaces by their IDs.\n        inputParameters:\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of Space IDs\n        - name: space.fields\n          in: query\n          type: string\n          required: false\n          description:\
  \ Comma-separated list of Space fields\n        - name: expansions\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of expansions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getSpacesById\n        method: GET\n        path: /spaces/{id}\n        description: Retrieve a single Space by its ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Space ID\n        - name: space.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of Space fields\n        - name: expansions\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of expansions\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n      - name: getSpacesByCreatorIds\n        method: GET\n        path: /spaces/by/creator_ids\n        description: Retrieve Spaces created by specific user IDs.\n        inputParameters:\n        - name: user_ids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of user IDs\n        - name: space.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of Space fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchSpaces\n        method: GET\n        path: /spaces/search\n        description: Search for Spaces by keyword.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query for Spaces\n \
  \       - name: state\n          in: query\n          type: string\n          required: false\n          description: Filter by Space state (live, scheduled, all)\n        - name: space.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of Space fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: space-details\n      path: /2\n      description: Get buyers and posts associated with a Space.\n      operations:\n      - name: getSpacesBuyers\n        method: GET\n        path: /spaces/{id}/buyers\n        description: Get users who purchased a ticket to a Space.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Space ID\n        - name: user.fields\n          in: query\n          type: string\n          required: false\n         \
  \ description: Comma-separated list of user fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getSpacesPosts\n        method: GET\n        path: /spaces/{id}/tweets\n        description: Get posts shared in a Space.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The Space ID\n        - name: tweet.fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of tweet fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: x-engagement-api\n    resources:\n    - path: /v1/engagement/users/{id}/following\n      name: following\n      description: Manage following\n      operations:\n      - method: POST\n\
  \        name: followUser\n        description: Follow a user\n        call: x-engagement-api.followUser\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/engagement/users/{source_user_id}/following/{target_user_id}\n      name: unfollow\n      description: Unfollow a user\n      operations:\n      - method: DELETE\n        name: unfollowUser\n        description: Unfollow a user\n        call: x-engagement-api.unfollowUser\n        with:\n          source_user_id: rest.source_user_id\n          target_user_id: rest.target_user_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/engagement/users/{id}/blocking\n      name: blocking\n      description: Manage blocks\n      operations:\n      - method: POST\n        name: blockUsers\n        description: Block a user\n        call: x-engagement-api.blockUsers\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/engagement/users/{source_user_id}/blocking/{target_user_id}\n      name: unblock\n      description: Unblock a user\n      operations:\n      - method: DELETE\n        name: unblockUsers\n        description: Unblock a user\n        call: x-engagement-api.unblockUsers\n        with:\n          source_user_id: rest.source_user_id\n          target_user_id: rest.target_user_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/engagement/users/{id}/muting\n      name: muting\n      description: Manage mutes\n      operations:\n      - method: POST\n        name: muteUser\n        description: Mute a user\n        call: x-engagement-api.muteUser\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/engagement/users/{source_user_id}/muting/{target_user_id}\n      name: unmute\n      description: Unmute a user\n  \
  \    operations:\n      - method: DELETE\n        name: unmuteUser\n        description: Unmute a user\n        call: x-engagement-api.unmuteUser\n        with:\n          source_user_id: rest.source_user_id\n          target_user_id: rest.target_user_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/engagement/dm/conversations\n      name: dm-conversations\n      description: Create DM conversations\n      operations:\n      - method: POST\n        name: createDirectMessagesConversation\n        description: Create a new group DM conversation\n        call: x-engagement-api.createDirectMessagesConversation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/engagement/dm/conversations/{dm_conversation_id}/messages\n      name: dm-by-conversation\n      description: Send DM to a conversation\n      operations:\n      - method: POST\n        name: createDirectMessagesByConversationId\n        description:\
  \ Send a DM to an existing conversation\n        call: x-engagement-api.createDirectMessagesByConversationId\n        with:\n          dm_conversation_id: rest.dm_conversation_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/engagement/dm/events\n      name: dm-events\n      description: Get DM events\n      operations:\n      - method: GET\n        name: getDirectMessagesEvents\n        description: Get recent DM events\n        call: x-engagement-api.getDirectMessagesEvents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/engagement/spaces/search\n      name: spaces-search\n      description: Search Spaces\n      operations:\n      - method: GET\n        name: searchSpaces\n        description: Search for Spaces by keyword\n        call: x-engagement-api.searchSpaces\n        with:\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/engagement/spaces\n\
  \      name: spaces\n      description: Retrieve Spaces by IDs\n      operations:\n      - method: GET\n        name: getSpacesByIds\n        description: Get multiple Spaces by IDs\n        call: x-engagement-api.getSpacesByIds\n        with:\n          ids: rest.ids\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: x-engagement-mcp\n    transport: http\n    tools:\n    - name: followUser\n      description: Follow a user\n      hints:\n        readOnly: false\n        idempotent: false\n      call: x-engagement-mcp.followUser\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unfollowUser\n      description: Unfollow a user\n      hints:\n        readOnly: false\n        destructive: true\n      call: x-engagement-mcp.unfollowUser\n      with:\n        source_user_id: tools.source_user_id\n        target_user_id: tools.target_user_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: blockUsers\n      description: Block a user\n      hints:\n        readOnly: false\n        idempotent: false\n      call: x-engagement-mcp.blockUsers\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unblockUsers\n      description: Unblock a user\n      hints:\n        readOnly: false\n        destructive: true\n      call: x-engagement-mcp.unblockUsers\n      with:\n        source_user_id: tools.source_user_id\n        target_user_id: tools.target_user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getBlockedUsers\n      description: Get users blocked by the authenticated user\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-engagement-mcp.getBlockedUsers\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: muteUser\n      description:\
  \ Mute a user\n      hints:\n        readOnly: false\n        idempotent: false\n      call: x-engagement-mcp.muteUser\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unmuteUser\n      description: Unmute a user\n      hints:\n        readOnly: false\n        destructive: true\n      call: x-engagement-mcp.unmuteUser\n      with:\n        source_user_id: tools.source_user_id\n        target_user_id: tools.target_user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getMutedUsers\n      description: Get users muted by the authenticated user\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-engagement-mcp.getMutedUsers\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createDirectMessagesConversation\n      description: Create a new group DM conversation\n      hints:\n        readOnly: false\n\
  \        idempotent: false\n      call: x-engagement-mcp.createDirectMessagesConversation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createDirectMessagesByParticipantId\n      description: Send a direct message to a user by participant ID\n      hints:\n        readOnly: false\n        idempotent: false\n      call: x-engagement-mcp.createDirectMessagesByParticipantId\n      with:\n        participant_id: tools.participant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createDirectMessagesByConversationId\n      description: Send a direct message to an existing conversation\n      hints:\n        readOnly: false\n        idempotent: false\n      call: x-engagement-mcp.createDirectMessagesByConversationId\n      with:\n        dm_conversation_id: tools.dm_conversation_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getDirectMessagesEvents\n      description: Get recent DM events\
  \ for the authenticated user\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-engagement-mcp.getDirectMessagesEvents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getDirectMessagesEventsByConversationId\n      description: Get DM events for a specific conversation\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-engagement-mcp.getDirectMessagesEventsByConversationId\n      with:\n        dm_conversation_id: tools.dm_conversation_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchSpaces\n      description: Search for Spaces by keyword\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-engagement-mcp.searchSpaces\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getSpacesByIds\n      description: Retrieve multiple Spaces by their IDs\n      hints:\n        readOnly:\
  \ true\n        idempotent: true\n      call: x-engagement-mcp.getSpacesByIds\n      with:\n        ids: tools.ids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getSpacesPosts\n      description: Get posts shared in a Space\n      hints:\n        readOnly: true\n        idempotent: true\n      call: x-engagement-mcp.getSpacesPosts\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
