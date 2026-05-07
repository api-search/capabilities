---
categories: []
consumed_apis: []
description: 'The Bluesky Social API provides programmatic access to the Bluesky social network built on the AT Protocol. This API enables developers to: - Manage user profiles and preferences - Create, read, and interact with posts and feeds - Handle social graph operations (follows, blocks, mutes) - Process notifications and conversations - Moderate content and manage labels - Synchronize repository data Authentication is handled via Bearer tokens. Public endpoints can be accessed directly at https://public.api.bsky.app, while authenticated requests should be made to the user''s Personal Data Server (PDS).'
layout: capability
name: Bluesky Social API
operations:
- description: Bluesky Get private preferences attached to the current account.
  method: GET
  name: actorgetpreferences
  path: /xrpc/app.bsky.actor.getPreferences
- description: Bluesky Get detailed profile view of an actor.
  method: GET
  name: actorgetprofile
  path: /xrpc/app.bsky.actor.getProfile
- description: Bluesky Get detailed profile views of multiple actors.
  method: GET
  name: actorgetprofiles
  path: /xrpc/app.bsky.actor.getProfiles
- description: Bluesky Get a list of suggested actors.
  method: GET
  name: actorgetsuggestions
  path: /xrpc/app.bsky.actor.getSuggestions
- description: Bluesky Set the private preferences attached to the account.
  method: POST
  name: actorputpreferences
  path: /xrpc/app.bsky.actor.putPreferences
- description: Bluesky Find actors (profiles) matching search criteria.
  method: GET
  name: actorsearchactors
  path: /xrpc/app.bsky.actor.searchActors
- description: Bluesky Find actor suggestions for a prefix search term.
  method: GET
  name: actorsearchactorstypeahead
  path: /xrpc/app.bsky.actor.searchActorsTypeahead
- description: Bluesky Get information about a feed generator, including policies and offered feed URIs.
  method: GET
  name: feeddescribefeedgenerator
  path: /xrpc/app.bsky.feed.describeFeedGenerator
- description: Bluesky Get a list of feeds (feed generator records) created by the actor (in the actor's repo).
  method: GET
  name: feedgetactorfeeds
  path: /xrpc/app.bsky.feed.getActorFeeds
- description: Bluesky Get a list of posts liked by an actor.
  method: GET
  name: feedgetactorlikes
  path: /xrpc/app.bsky.feed.getActorLikes
- description: Bluesky Get a view of an actor's 'author feed' (post and reposts by the author).
  method: GET
  name: feedgetauthorfeed
  path: /xrpc/app.bsky.feed.getAuthorFeed
- description: Bluesky Get a hydrated feed from an actor's selected feed generator.
  method: GET
  name: feedgetfeed
  path: /xrpc/app.bsky.feed.getFeed
- description: Bluesky Get information about a feed generator.
  method: GET
  name: feedgetfeedgenerator
  path: /xrpc/app.bsky.feed.getFeedGenerator
- description: Bluesky Get information about a list of feed generators.
  method: GET
  name: feedgetfeedgenerators
  path: /xrpc/app.bsky.feed.getFeedGenerators
- description: Bluesky Get a skeleton of a feed provided by a feed generator.
  method: GET
  name: feedgetfeedskeleton
  path: /xrpc/app.bsky.feed.getFeedSkeleton
- description: Bluesky Get like records which reference a subject (by AT-URI and CID).
  method: GET
  name: feedgetlikes
  path: /xrpc/app.bsky.feed.getLikes
- description: Bluesky Get a feed of recent posts from a list (posts and reposts from any actors on the list).
  method: GET
  name: feedgetlistfeed
  path: /xrpc/app.bsky.feed.getListFeed
- description: Bluesky Get posts in a thread.
  method: GET
  name: feedgetpostthread
  path: /xrpc/app.bsky.feed.getPostThread
- description: Bluesky Gets post views for a specified list of posts (by AT-URI).
  method: GET
  name: feedgetposts
  path: /xrpc/app.bsky.feed.getPosts
- description: Bluesky Get a list of quotes for a given post.
  method: GET
  name: feedgetquotes
  path: /xrpc/app.bsky.feed.getQuotes
- description: Bluesky Get a list of reposts for a given post.
  method: GET
  name: feedgetrepostedby
  path: /xrpc/app.bsky.feed.getRepostedBy
- description: Bluesky Get a list of suggested feeds (feed generators) for the requesting account.
  method: GET
  name: feedgetsuggestedfeeds
  path: /xrpc/app.bsky.feed.getSuggestedFeeds
- description: Bluesky Get a view of the requesting account's home timeline.
  method: GET
  name: feedgettimeline
  path: /xrpc/app.bsky.feed.getTimeline
- description: Bluesky Find posts matching search criteria, returning views of those posts.
  method: GET
  name: feedsearchposts
  path: /xrpc/app.bsky.feed.searchPosts
- description: Bluesky Send information about interactions with feed items back to the feed generator that served them.
  method: POST
  name: feedsendinteractions
  path: /xrpc/app.bsky.feed.sendInteractions
- description: Bluesky Get a list of starter packs created by the actor.
  method: GET
  name: graphgetactorstarterpacks
  path: /xrpc/app.bsky.graph.getActorStarterPacks
- description: Bluesky Enumerates which accounts the requesting account is currently blocking.
  method: GET
  name: graphgetblocks
  path: /xrpc/app.bsky.graph.getBlocks
- description: Bluesky Enumerates accounts which follow a specified account (actor).
  method: GET
  name: graphgetfollowers
  path: /xrpc/app.bsky.graph.getFollowers
- description: Bluesky Enumerates accounts which a specified account (actor) follows.
  method: GET
  name: graphgetfollows
  path: /xrpc/app.bsky.graph.getFollows
- description: Bluesky Enumerates accounts which follow a specified account (actor) and are followed by the viewer.
  method: GET
  name: graphgetknownfollowers
  path: /xrpc/app.bsky.graph.getKnownFollowers
- description: Bluesky Gets a 'view' (with additional context) of a specified list.
  method: GET
  name: graphgetlist
  path: /xrpc/app.bsky.graph.getList
- description: Bluesky Get mod lists that the requesting account (actor) is blocking.
  method: GET
  name: graphgetlistblocks
  path: /xrpc/app.bsky.graph.getListBlocks
- description: Bluesky Enumerates mod lists that the requesting account (actor) currently has muted.
  method: GET
  name: graphgetlistmutes
  path: /xrpc/app.bsky.graph.getListMutes
- description: Bluesky Enumerates the lists created by a specified account (actor).
  method: GET
  name: graphgetlists
  path: /xrpc/app.bsky.graph.getLists
- description: Bluesky Enumerates accounts that the requesting account (actor) currently has muted.
  method: GET
  name: graphgetmutes
  path: /xrpc/app.bsky.graph.getMutes
- description: Bluesky Enumerates public relationships between one account, and a list of other accounts.
  method: GET
  name: graphgetrelationships
  path: /xrpc/app.bsky.graph.getRelationships
- description: Bluesky Gets a view of a starter pack.
  method: GET
  name: graphgetstarterpack
  path: /xrpc/app.bsky.graph.getStarterPack
- description: Bluesky Get views for a list of starter packs.
  method: GET
  name: graphgetstarterpacks
  path: /xrpc/app.bsky.graph.getStarterPacks
- description: Bluesky Enumerates follows similar to a given account (actor).
  method: GET
  name: graphgetsuggestedfollowsbyactor
  path: /xrpc/app.bsky.graph.getSuggestedFollowsByActor
- description: Bluesky Creates a mute relationship for the specified account.
  method: POST
  name: graphmuteactor
  path: /xrpc/app.bsky.graph.muteActor
- description: Bluesky Creates a mute relationship for the specified list of accounts.
  method: POST
  name: graphmuteactorlist
  path: /xrpc/app.bsky.graph.muteActorList
- description: Bluesky Mutes a thread preventing notifications from the thread and any of its children.
  method: POST
  name: graphmutethread
  path: /xrpc/app.bsky.graph.muteThread
- description: Bluesky Unmutes the specified account.
  method: POST
  name: graphunmuteactor
  path: /xrpc/app.bsky.graph.unmuteActor
- description: Bluesky Unmutes the specified list of accounts.
  method: POST
  name: graphunmuteactorlist
  path: /xrpc/app.bsky.graph.unmuteActorList
- description: Bluesky Unmutes the specified thread.
  method: POST
  name: graphunmutethread
  path: /xrpc/app.bsky.graph.unmuteThread
- description: Bluesky Get information about a list of labeler services.
  method: GET
  name: labelergetservices
  path: /xrpc/app.bsky.labeler.getServices
- description: Bluesky Count the number of unread notifications for the requesting account.
  method: GET
  name: notificationgetunreadcount
  path: /xrpc/app.bsky.notification.getUnreadCount
- description: Bluesky Enumerate notifications for the requesting account.
  method: GET
  name: notificationlistnotifications
  path: /xrpc/app.bsky.notification.listNotifications
- description: Bluesky Set notification-related preferences for an account.
  method: POST
  name: notificationputpreferences
  path: /xrpc/app.bsky.notification.putPreferences
- description: Bluesky Register to receive push notifications, via a specified service, for the requesting account.
  method: POST
  name: notificationregisterpush
  path: /xrpc/app.bsky.notification.registerPush
- description: Bluesky Notify server that the requesting account has seen notifications.
  method: POST
  name: notificationupdateseen
  path: /xrpc/app.bsky.notification.updateSeen
- description: Bluesky Get status details for a video processing job.
  method: GET
  name: videogetjobstatus
  path: /xrpc/app.bsky.video.getJobStatus
- description: Bluesky Get video upload limits for the authenticated user.
  method: GET
  name: videogetuploadlimits
  path: /xrpc/app.bsky.video.getUploadLimits
- description: Bluesky Upload a video to be processed then stored on the PDS.
  method: POST
  name: videouploadvideo
  path: /xrpc/app.bsky.video.uploadVideo
- description: Bluesky Operation
  method: POST
  name: chatactordeleteaccount
  path: /xrpc/chat.bsky.actor.deleteAccount
- description: Bluesky Operation
  method: GET
  name: chatactorexportaccountdata
  path: /xrpc/chat.bsky.actor.exportAccountData
- description: Bluesky Operation
  method: POST
  name: chatconvodeletemessageforself
  path: /xrpc/chat.bsky.convo.deleteMessageForSelf
- description: Bluesky Operation
  method: GET
  name: chatconvogetconvo
  path: /xrpc/chat.bsky.convo.getConvo
- description: Bluesky Operation
  method: GET
  name: chatconvogetconvoformembers
  path: /xrpc/chat.bsky.convo.getConvoForMembers
- description: Bluesky Operation
  method: GET
  name: chatconvogetlog
  path: /xrpc/chat.bsky.convo.getLog
personas: []
provider_name: Bluesky
provider_slug: bluesky
search_terms:
- feedgetfeedgenerator
- feedgetlistfeed
- bluesky get information about a feed generator, including policies and offered feed uris.
- bluesky get video upload limits for the authenticated user.
- api
- graphgetlist
- bluesky get a list of posts liked by an actor.
- bluesky count the number of unread notifications for the requesting account.
- chatconvodeletemessageforself
- bluesky unmutes the specified thread.
- feedgetfeed
- bluesky get a hydrated feed from an actor's selected feed generator.
- bluesky enumerates accounts which follow a specified account (actor).
- social-media
- decentralized
- feedgetauthorfeed
- bluesky gets post views for a specified list of posts (by at-uri).
- graphgetmutes
- graphgetlistblocks
- feedgetfeedgenerators
- bluesky find actors (profiles) matching search criteria.
- bluesky get a skeleton of a feed provided by a feed generator.
- bluesky enumerates accounts which follow a specified account (actor) and are followed by the viewer.
- graphmutethread
- bluesky upload a video to be processed then stored on the pds.
- graphmuteactor
- bluesky get a view of an actor's 'author feed' (post and reposts by the author).
- bluesky creates a mute relationship for the specified list of accounts.
- actorputpreferences
- bluesky get detailed profile view of an actor.
- chatconvogetlog
- graphmuteactorlist
- feedgetpostthread
- bluesky get a list of feeds (feed generator records) created by the actor (in the actor's repo).
- videogetuploadlimits
- actorsearchactorstypeahead
- graphgetblocks
- graphgetlists
- videogetjobstatus
- labelergetservices
- bluesky get a view of the requesting account's home timeline.
- bluesky mutes a thread preventing notifications from the thread and any of its children.
- feedgetactorfeeds
- feedgettimeline
- bluesky send information about interactions with feed items back to the feed generator that served them.
- graphgetstarterpack
- social networks
- bluesky enumerates accounts that the requesting account (actor) currently has muted.
- bluesky
- notificationputpreferences
- chatconvogetconvoformembers
- feedgetfeedskeleton
- actorgetprofiles
- graphgetstarterpacks
- bluesky enumerates accounts which a specified account (actor) follows.
- bluesky set the private preferences attached to the account.
- graphgetrelationships
- graphunmutethread
- feedgetlikes
- graphgetknownfollowers
- feedgetrepostedby
- bluesky get information about a list of feed generators.
- feedgetquotes
- graphgetsuggestedfollowsbyactor
- bluesky enumerates follows similar to a given account (actor).
- notificationgetunreadcount
- actorgetpreferences
- bluesky gets a view of a starter pack.
- feeddescribefeedgenerator
- notificationupdateseen
- bluesky get like records which reference a subject (by at-uri and cid).
- bluesky get a list of suggested actors.
- notificationregisterpush
- graphgetlistmutes
- chatconvogetconvo
- feedsendinteractions
- graphunmuteactorlist
- open-source
- bluesky get a list of reposts for a given post.
- bluesky get views for a list of starter packs.
- chatactordeleteaccount
- graphunmuteactor
- bluesky enumerates the lists created by a specified account (actor).
- bluesky get mod lists that the requesting account (actor) is blocking.
- bluesky get information about a feed generator.
- bluesky get posts in a thread.
- feedgetposts
- graphgetfollows
- bluesky notify server that the requesting account has seen notifications.
- bluesky get private preferences attached to the current account.
- bluesky enumerates mod lists that the requesting account (actor) currently has muted.
- graphgetactorstarterpacks
- bluesky get a list of quotes for a given post.
- federated
- bluesky get status details for a video processing job.
- at-protocol
- actorgetsuggestions
- bluesky unmutes the specified list of accounts.
- feedgetsuggestedfeeds
- bluesky get a feed of recent posts from a list (posts and reposts from any actors on the list).
- actorsearchactors
- bluesky creates a mute relationship for the specified account.
- bluesky gets a 'view' (with additional context) of a specified list.
- bluesky unmutes the specified account.
- feedgetactorlikes
- videouploadvideo
- bluesky get detailed profile views of multiple actors.
- bluesky find actor suggestions for a prefix search term.
- bluesky get a list of suggested feeds (feed generators) for the requesting account.
- bluesky operation
- notificationlistnotifications
- bluesky find posts matching search criteria, returning views of those posts.
- bluesky enumerate notifications for the requesting account.
- feedsearchposts
- bluesky enumerates which accounts the requesting account is currently blocking.
- bluesky get a list of starter packs created by the actor.
- graphgetfollowers
- bluesky enumerates public relationships between one account, and a list of other accounts.
- bluesky register to receive push notifications, via a specified service, for the requesting account.
- bluesky get information about a list of labeler services.
- chatactorexportaccountdata
- bluesky set notification-related preferences for an account.
- actorgetprofile
slug: bluesky-capability
source_filename: bluesky-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bluesky Social API\n  description: 'The Bluesky Social API provides programmatic access to the Bluesky social network built on the AT Protocol.\n    This API enables developers to: - Manage user profiles and preferences - Create, read, and interact with posts and feeds\n    - Handle social graph operations (follows, blocks, mutes) - Process notifications and conversations - Moderate content\n    and manage labels - Synchronize repository data Authentication is handled via Bearer tokens. Public endpoints can be accessed\n    directly at https://public.api.bsky.app, while authenticated requests should be made to the user''s Personal Data Server\n    (PDS).'\n  tags:\n  - Bluesky\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bluesky\n    baseUri: https://bsky.social/xrpc\n    description: Bluesky Social API HTTP API.\n    authentication:\n      type: bearer\n      token:\
  \ '{{BLUESKY_TOKEN}}'\n    resources:\n    - name: xrpc-app-bsky-actor-getpreferences\n      path: /xrpc/app.bsky.actor.getPreferences\n      operations:\n      - name: actorgetpreferences\n        method: GET\n        description: Bluesky Get private preferences attached to the current account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-actor-getprofile\n      path: /xrpc/app.bsky.actor.getProfile\n      operations:\n      - name: actorgetprofile\n        method: GET\n        description: Bluesky Get detailed profile view of an actor.\n        inputParameters:\n        - name: actor\n          in: query\n          type: string\n          required: true\n          description: Handle or DID of account to fetch profile of.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-actor-getprofiles\n\
  \      path: /xrpc/app.bsky.actor.getProfiles\n      operations:\n      - name: actorgetprofiles\n        method: GET\n        description: Bluesky Get detailed profile views of multiple actors.\n        inputParameters:\n        - name: actors\n          in: query\n          type: array\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-actor-getsuggestions\n      path: /xrpc/app.bsky.actor.getSuggestions\n      operations:\n      - name: actorgetsuggestions\n        method: GET\n        description: Bluesky Get a list of suggested actors.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-actor-putpreferences\n\
  \      path: /xrpc/app.bsky.actor.putPreferences\n      operations:\n      - name: actorputpreferences\n        method: POST\n        description: Bluesky Set the private preferences attached to the account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-actor-searchactors\n      path: /xrpc/app.bsky.actor.searchActors\n      operations:\n      - name: actorsearchactors\n        method: GET\n        description: Bluesky Find actors (profiles) matching search criteria.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Search query string. Syntax, phrase, boolean, and faceting is unspecified, but Lucene query syntax\n            is recommended.\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-actor-searchactorstypeahead\n      path: /xrpc/app.bsky.actor.searchActorsTypeahead\n      operations:\n      - name: actorsearchactorstypeahead\n        method: GET\n        description: Bluesky Find actor suggestions for a prefix search term.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Search query prefix; not a full query string.\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-describefeedgenerator\n      path: /xrpc/app.bsky.feed.describeFeedGenerator\n      operations:\n      - name: feeddescribefeedgenerator\n        method: GET\n        description: Bluesky Get information about a feed generator, including policies and\
  \ offered feed URIs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getactorfeeds\n      path: /xrpc/app.bsky.feed.getActorFeeds\n      operations:\n      - name: feedgetactorfeeds\n        method: GET\n        description: Bluesky Get a list of feeds (feed generator records) created by the actor (in the actor's repo).\n        inputParameters:\n        - name: actor\n          in: query\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getactorlikes\n      path: /xrpc/app.bsky.feed.getActorLikes\n      operations:\n      - name: feedgetactorlikes\n        method: GET\n        description:\
  \ Bluesky Get a list of posts liked by an actor.\n        inputParameters:\n        - name: actor\n          in: query\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getauthorfeed\n      path: /xrpc/app.bsky.feed.getAuthorFeed\n      operations:\n      - name: feedgetauthorfeed\n        method: GET\n        description: Bluesky Get a view of an actor's 'author feed' (post and reposts by the author).\n        inputParameters:\n        - name: actor\n          in: query\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        - name: filter\n          in:\
  \ query\n          type: string\n          description: Combinations of post/repost types to include in response.\n        - name: includePins\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getfeed\n      path: /xrpc/app.bsky.feed.getFeed\n      operations:\n      - name: feedgetfeed\n        method: GET\n        description: Bluesky Get a hydrated feed from an actor's selected feed generator.\n        inputParameters:\n        - name: feed\n          in: query\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getfeedgenerator\n      path:\
  \ /xrpc/app.bsky.feed.getFeedGenerator\n      operations:\n      - name: feedgetfeedgenerator\n        method: GET\n        description: Bluesky Get information about a feed generator.\n        inputParameters:\n        - name: feed\n          in: query\n          type: string\n          required: true\n          description: AT-URI of the feed generator record.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getfeedgenerators\n      path: /xrpc/app.bsky.feed.getFeedGenerators\n      operations:\n      - name: feedgetfeedgenerators\n        method: GET\n        description: Bluesky Get information about a list of feed generators.\n        inputParameters:\n        - name: feeds\n          in: query\n          type: array\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: xrpc-app-bsky-feed-getfeedskeleton\n      path: /xrpc/app.bsky.feed.getFeedSkeleton\n      operations:\n      - name: feedgetfeedskeleton\n        method: GET\n        description: Bluesky Get a skeleton of a feed provided by a feed generator.\n        inputParameters:\n        - name: feed\n          in: query\n          type: string\n          required: true\n          description: Reference to feed generator record describing the specific feed being requested.\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getlikes\n      path: /xrpc/app.bsky.feed.getLikes\n      operations:\n      - name: feedgetlikes\n        method: GET\n        description: Bluesky Get like records which reference a subject (by AT-URI and CID).\n        inputParameters:\n\
  \        - name: uri\n          in: query\n          type: string\n          required: true\n          description: AT-URI of the subject (eg, a post record).\n        - name: cid\n          in: query\n          type: string\n          description: CID of the subject record (aka, specific version of record), to filter likes.\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getlistfeed\n      path: /xrpc/app.bsky.feed.getListFeed\n      operations:\n      - name: feedgetlistfeed\n        method: GET\n        description: Bluesky Get a feed of recent posts from a list (posts and reposts from any actors on the list).\n        inputParameters:\n        - name: list\n          in: query\n          type: string\n          required: true\n         \
  \ description: Reference (AT-URI) to the list record.\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getpostthread\n      path: /xrpc/app.bsky.feed.getPostThread\n      operations:\n      - name: feedgetpostthread\n        method: GET\n        description: Bluesky Get posts in a thread.\n        inputParameters:\n        - name: uri\n          in: query\n          type: string\n          required: true\n          description: Reference (AT-URI) to post record.\n        - name: depth\n          in: query\n          type: integer\n          description: How many levels of reply depth should be included in response.\n        - name: parentHeight\n          in: query\n          type: integer\n          description: How many levels of parent (and\
  \ grandparent, etc) post to include.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getposts\n      path: /xrpc/app.bsky.feed.getPosts\n      operations:\n      - name: feedgetposts\n        method: GET\n        description: Bluesky Gets post views for a specified list of posts (by AT-URI).\n        inputParameters:\n        - name: uris\n          in: query\n          type: array\n          required: true\n          description: List of post AT-URIs to return hydrated views for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getquotes\n      path: /xrpc/app.bsky.feed.getQuotes\n      operations:\n      - name: feedgetquotes\n        method: GET\n        description: Bluesky Get a list of quotes for a given post.\n        inputParameters:\n        - name: uri\n    \
  \      in: query\n          type: string\n          required: true\n          description: Reference (AT-URI) of post record\n        - name: cid\n          in: query\n          type: string\n          description: If supplied, filters to quotes of specific version (by CID) of the post record.\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getrepostedby\n      path: /xrpc/app.bsky.feed.getRepostedBy\n      operations:\n      - name: feedgetrepostedby\n        method: GET\n        description: Bluesky Get a list of reposts for a given post.\n        inputParameters:\n        - name: uri\n          in: query\n          type: string\n          required: true\n          description: Reference (AT-URI) of post record\n        - name: cid\n     \
  \     in: query\n          type: string\n          description: If supplied, filters to reposts of specific version (by CID) of the post record.\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-getsuggestedfeeds\n      path: /xrpc/app.bsky.feed.getSuggestedFeeds\n      operations:\n      - name: feedgetsuggestedfeeds\n        method: GET\n        description: Bluesky Get a list of suggested feeds (feed generators) for the requesting account.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-gettimeline\n\
  \      path: /xrpc/app.bsky.feed.getTimeline\n      operations:\n      - name: feedgettimeline\n        method: GET\n        description: Bluesky Get a view of the requesting account's home timeline.\n        inputParameters:\n        - name: algorithm\n          in: query\n          type: string\n          description: 'Variant ''algorithm'' for timeline. Implementation-specific. NOTE: most feed flexibility has been\n            moved to feed generator mechanism.'\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-searchposts\n      path: /xrpc/app.bsky.feed.searchPosts\n      operations:\n      - name: feedsearchposts\n        method: GET\n        description: Bluesky Find posts matching search criteria, returning views of those posts.\n    \
  \    inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query string; syntax, phrase, boolean, and faceting is unspecified, but Lucene query syntax\n            is recommended.\n        - name: sort\n          in: query\n          type: string\n          description: Specifies the ranking order of results.\n        - name: since\n          in: query\n          type: string\n          description: Filter results for posts after the indicated datetime (inclusive). Expected to use 'sortAt' timestamp,\n            which may not match 'createdAt'. Can be a datetime, or ju\n        - name: until\n          in: query\n          type: string\n          description: 'Filter results for posts before the indicated datetime (not inclusive). Expected to use ''sortAt''\n            timestamp, which may not match ''createdAt''. Can be a datetime, '\n        - name: mentions\n          in: query\n          type: string\n\
  \          description: Filter to posts which mention the given account. Handles are resolved to DID before query-time. Only\n            matches rich-text facet mentions.\n        - name: author\n          in: query\n          type: string\n          description: Filter to posts by the given account. Handles are resolved to DID before query-time.\n        - name: lang\n          in: query\n          type: string\n          description: Filter to posts in the given language. Expected to be based on post language field, though server may\n            override language detection.\n        - name: domain\n          in: query\n          type: string\n          description: Filter to posts with URLs (facet links or embeds) linking to the given domain (hostname). Server may\n            apply hostname normalization.\n        - name: url\n          in: query\n          type: string\n          description: Filter to posts with links (facet links or embeds) pointing to this URL. Server may apply\
  \ URL normalization\n            or fuzzy matching.\n        - name: tag\n          in: query\n          type: array\n          description: Filter to posts with the given tag (hashtag), based on rich-text facet or tag field. Do not include\n            the hash (#) prefix. Multiple tags can be specified, with 'A\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n          description: Optional pagination mechanism; may not necessarily allow scrolling through entire result set.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-feed-sendinteractions\n      path: /xrpc/app.bsky.feed.sendInteractions\n      operations:\n      - name: feedsendinteractions\n        method: POST\n        description: Bluesky Send information about interactions with feed items back to the feed generator that served them.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getactorstarterpacks\n      path: /xrpc/app.bsky.graph.getActorStarterPacks\n      operations:\n      - name: graphgetactorstarterpacks\n        method: GET\n        description: Bluesky Get a list of starter packs created by the actor.\n        inputParameters:\n        - name: actor\n          in: query\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getblocks\n      path: /xrpc/app.bsky.graph.getBlocks\n      operations:\n      - name: graphgetblocks\n        method: GET\n        description: Bluesky Enumerates which accounts the requesting\
  \ account is currently blocking.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getfollowers\n      path: /xrpc/app.bsky.graph.getFollowers\n      operations:\n      - name: graphgetfollowers\n        method: GET\n        description: Bluesky Enumerates accounts which follow a specified account (actor).\n        inputParameters:\n        - name: actor\n          in: query\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getfollows\n\
  \      path: /xrpc/app.bsky.graph.getFollows\n      operations:\n      - name: graphgetfollows\n        method: GET\n        description: Bluesky Enumerates accounts which a specified account (actor) follows.\n        inputParameters:\n        - name: actor\n          in: query\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getknownfollowers\n      path: /xrpc/app.bsky.graph.getKnownFollowers\n      operations:\n      - name: graphgetknownfollowers\n        method: GET\n        description: Bluesky Enumerates accounts which follow a specified account (actor) and are followed by the viewer.\n        inputParameters:\n        - name: actor\n          in: query\n          type: string\n      \
  \    required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getlist\n      path: /xrpc/app.bsky.graph.getList\n      operations:\n      - name: graphgetlist\n        method: GET\n        description: Bluesky Gets a 'view' (with additional context) of a specified list.\n        inputParameters:\n        - name: list\n          in: query\n          type: string\n          required: true\n          description: Reference (AT-URI) of the list record to hydrate.\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getlistblocks\n\
  \      path: /xrpc/app.bsky.graph.getListBlocks\n      operations:\n      - name: graphgetlistblocks\n        method: GET\n        description: Bluesky Get mod lists that the requesting account (actor) is blocking.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getlistmutes\n      path: /xrpc/app.bsky.graph.getListMutes\n      operations:\n      - name: graphgetlistmutes\n        method: GET\n        description: Bluesky Enumerates mod lists that the requesting account (actor) currently has muted.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getlists\n      path: /xrpc/app.bsky.graph.getLists\n      operations:\n      - name: graphgetlists\n        method: GET\n        description: Bluesky Enumerates the lists created by a specified account (actor).\n        inputParameters:\n        - name: actor\n          in: query\n          type: string\n          required: true\n          description: The account (actor) to enumerate lists from.\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getmutes\n      path: /xrpc/app.bsky.graph.getMutes\n      operations:\n      - name: graphgetmutes\n        method: GET\n        description: Bluesky Enumerates accounts that the requesting account\
  \ (actor) currently has muted.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getrelationships\n      path: /xrpc/app.bsky.graph.getRelationships\n      operations:\n      - name: graphgetrelationships\n        method: GET\n        description: Bluesky Enumerates public relationships between one account, and a list of other accounts.\n        inputParameters:\n        - name: actor\n          in: query\n          type: string\n          required: true\n          description: Primary account requesting relationships for.\n        - name: others\n          in: query\n          type: array\n          description: List of 'other' accounts to be related back to the primary.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getstarterpack\n      path: /xrpc/app.bsky.graph.getStarterPack\n      operations:\n      - name: graphgetstarterpack\n        method: GET\n        description: Bluesky Gets a view of a starter pack.\n        inputParameters:\n        - name: starterPack\n          in: query\n          type: string\n          required: true\n          description: Reference (AT-URI) of the starter pack record.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getstarterpacks\n      path: /xrpc/app.bsky.graph.getStarterPacks\n      operations:\n      - name: graphgetstarterpacks\n        method: GET\n        description: Bluesky Get views for a list of starter packs.\n        inputParameters:\n        - name: uris\n          in: query\n          type: array\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-getsuggestedfollowsbyactor\n      path: /xrpc/app.bsky.graph.getSuggestedFollowsByActor\n      operations:\n      - name: graphgetsuggestedfollowsbyactor\n        method: GET\n        description: Bluesky Enumerates follows similar to a given account (actor).\n        inputParameters:\n        - name: actor\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-muteactor\n      path: /xrpc/app.bsky.graph.muteActor\n      operations:\n      - name: graphmuteactor\n        method: POST\n        description: Bluesky Creates a mute relationship for the specified account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n    - name: xrpc-app-bsky-graph-muteactorlist\n      path: /xrpc/app.bsky.graph.muteActorList\n      operations:\n      - name: graphmuteactorlist\n        method: POST\n        description: Bluesky Creates a mute relationship for the specified list of accounts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-mutethread\n      path: /xrpc/app.bsky.graph.muteThread\n      operations:\n      - name: graphmutethread\n        method: POST\n        description: Bluesky Mutes a thread preventing notifications from the thread and any of its children.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-unmuteactor\n      path: /xrpc/app.bsky.graph.unmuteActor\n      operations:\n      - name: graphunmuteactor\n        method: POST\n        description: Bluesky Unmutes\
  \ the specified account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-unmuteactorlist\n      path: /xrpc/app.bsky.graph.unmuteActorList\n      operations:\n      - name: graphunmuteactorlist\n        method: POST\n        description: Bluesky Unmutes the specified list of accounts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-graph-unmutethread\n      path: /xrpc/app.bsky.graph.unmuteThread\n      operations:\n      - name: graphunmutethread\n        method: POST\n        description: Bluesky Unmutes the specified thread.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-labeler-getservices\n      path: /xrpc/app.bsky.labeler.getServices\n      operations:\n     \
  \ - name: labelergetservices\n        method: GET\n        description: Bluesky Get information about a list of labeler services.\n        inputParameters:\n        - name: dids\n          in: query\n          type: array\n          required: true\n        - name: detailed\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-notification-getunreadcount\n      path: /xrpc/app.bsky.notification.getUnreadCount\n      operations:\n      - name: notificationgetunreadcount\n        method: GET\n        description: Bluesky Count the number of unread notifications for the requesting account.\n        inputParameters:\n        - name: priority\n          in: query\n          type: boolean\n        - name: seenAt\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: xrpc-app-bsky-notification-listnotifications\n      path: /xrpc/app.bsky.notification.listNotifications\n      operations:\n      - name: notificationlistnotifications\n        method: GET\n        description: Bluesky Enumerate notifications for the requesting account.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: priority\n          in: query\n          type: boolean\n        - name: cursor\n          in: query\n          type: string\n        - name: seenAt\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-notification-putpreferences\n      path: /xrpc/app.bsky.notification.putPreferences\n      operations:\n      - name: notificationputpreferences\n        method: POST\n        description: Bluesky Set notification-related preferences\
  \ for an account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-notification-registerpush\n      path: /xrpc/app.bsky.notification.registerPush\n      operations:\n      - name: notificationregisterpush\n        method: POST\n        description: Bluesky Register to receive push notifications, via a specified service, for the requesting account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-notification-updateseen\n      path: /xrpc/app.bsky.notification.updateSeen\n      operations:\n      - name: notificationupdateseen\n        method: POST\n        description: Bluesky Notify server that the requesting account has seen notifications.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ xrpc-app-bsky-video-getjobstatus\n      path: /xrpc/app.bsky.video.getJobStatus\n      operations:\n      - name: videogetjobstatus\n        method: GET\n        description: Bluesky Get status details for a video processing job.\n        inputParameters:\n        - name: jobId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: xrpc-app-bsky-video-getuploadlimits\n      path: /xrpc/app.bsky.video.getUploadLimits\n      operations:\n      - name: videogetuploadlimits\n        method: GET\n\n\n# --- truncated at 32 KB (88 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/bluesky/refs/heads/main/capabilities/bluesky-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bluesky/refs/heads/main/capabilities/bluesky-capability.yaml
tags:
- Bluesky
- API
tools:
- description: Bluesky Get private preferences attached to the current account.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: actorgetpreferences
- description: Bluesky Get detailed profile view of an actor.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: actorgetprofile
- description: Bluesky Get detailed profile views of multiple actors.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: actorgetprofiles
- description: Bluesky Get a list of suggested actors.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: actorgetsuggestions
- description: Bluesky Set the private preferences attached to the account.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: actorputpreferences
- description: Bluesky Find actors (profiles) matching search criteria.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: actorsearchactors
- description: Bluesky Find actor suggestions for a prefix search term.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: actorsearchactorstypeahead
- description: Bluesky Get information about a feed generator, including policies and offered feed URIs.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feeddescribefeedgenerator
- description: Bluesky Get a list of feeds (feed generator records) created by the actor (in the actor's repo).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetactorfeeds
- description: Bluesky Get a list of posts liked by an actor.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetactorlikes
- description: Bluesky Get a view of an actor's 'author feed' (post and reposts by the author).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetauthorfeed
- description: Bluesky Get a hydrated feed from an actor's selected feed generator.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetfeed
- description: Bluesky Get information about a feed generator.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetfeedgenerator
- description: Bluesky Get information about a list of feed generators.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetfeedgenerators
- description: Bluesky Get a skeleton of a feed provided by a feed generator.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetfeedskeleton
- description: Bluesky Get like records which reference a subject (by AT-URI and CID).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetlikes
- description: Bluesky Get a feed of recent posts from a list (posts and reposts from any actors on the list).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetlistfeed
- description: Bluesky Get posts in a thread.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetpostthread
- description: Bluesky Gets post views for a specified list of posts (by AT-URI).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetposts
- description: Bluesky Get a list of quotes for a given post.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetquotes
- description: Bluesky Get a list of reposts for a given post.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetrepostedby
- description: Bluesky Get a list of suggested feeds (feed generators) for the requesting account.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgetsuggestedfeeds
- description: Bluesky Get a view of the requesting account's home timeline.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedgettimeline
- description: Bluesky Find posts matching search criteria, returning views of those posts.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feedsearchposts
- description: Bluesky Send information about interactions with feed items back to the feed generator that served them.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: feedsendinteractions
- description: Bluesky Get a list of starter packs created by the actor.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetactorstarterpacks
- description: Bluesky Enumerates which accounts the requesting account is currently blocking.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetblocks
- description: Bluesky Enumerates accounts which follow a specified account (actor).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetfollowers
- description: Bluesky Enumerates accounts which a specified account (actor) follows.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetfollows
- description: Bluesky Enumerates accounts which follow a specified account (actor) and are followed by the viewer.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetknownfollowers
- description: Bluesky Gets a 'view' (with additional context) of a specified list.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetlist
- description: Bluesky Get mod lists that the requesting account (actor) is blocking.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetlistblocks
- description: Bluesky Enumerates mod lists that the requesting account (actor) currently has muted.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetlistmutes
- description: Bluesky Enumerates the lists created by a specified account (actor).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetlists
- description: Bluesky Enumerates accounts that the requesting account (actor) currently has muted.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetmutes
- description: Bluesky Enumerates public relationships between one account, and a list of other accounts.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetrelationships
- description: Bluesky Gets a view of a starter pack.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetstarterpack
- description: Bluesky Get views for a list of starter packs.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetstarterpacks
- description: Bluesky Enumerates follows similar to a given account (actor).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: graphgetsuggestedfollowsbyactor
- description: Bluesky Creates a mute relationship for the specified account.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: graphmuteactor
- description: Bluesky Creates a mute relationship for the specified list of accounts.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: graphmuteactorlist
- description: Bluesky Mutes a thread preventing notifications from the thread and any of its children.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: graphmutethread
- description: Bluesky Unmutes the specified account.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: graphunmuteactor
- description: Bluesky Unmutes the specified list of accounts.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: graphunmuteactorlist
- description: Bluesky Unmutes the specified thread.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: graphunmutethread
- description: Bluesky Get information about a list of labeler services.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: labelergetservices
- description: Bluesky Count the number of unread notifications for the requesting account.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: notificationgetunreadcount
- description: Bluesky Enumerate notifications for the requesting account.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: notificationlistnotifications
- description: Bluesky Set notification-related preferences for an account.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: notificationputpreferences
- description: Bluesky Register to receive push notifications, via a specified service, for the requesting account.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: notificationregisterpush
- description: Bluesky Notify server that the requesting account has seen notifications.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: notificationupdateseen
- description: Bluesky Get status details for a video processing job.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: videogetjobstatus
- description: Bluesky Get video upload limits for the authenticated user.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: videogetuploadlimits
- description: Bluesky Upload a video to be processed then stored on the PDS.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: videouploadvideo
- description: Bluesky Operation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: chatactordeleteaccount
- description: Bluesky Operation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: chatactorexportaccountdata
- description: Bluesky Operation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: chatconvodeletemessageforself
- description: Bluesky Operation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: chatconvogetconvo
- description: Bluesky Operation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: chatconvogetconvoformembers
- description: Bluesky Operation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: chatconvogetlog
---
