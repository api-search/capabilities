---
categories: []
consumed_apis: []
description: Workflow for managing community interactions including comments, comment threads, subscriptions, and channel management. Designed for community managers, social media teams, and content moderators.
layout: capability
name: YouTube Community Engagement
operations:
- description: List comments
  method: GET
  name: list-comments
  path: /v1/comments
- description: Post a new comment
  method: POST
  name: create-comment
  path: /v1/comments
- description: Update a comment
  method: PUT
  name: update-comment
  path: /v1/comments
- description: Delete a comment
  method: DELETE
  name: delete-comment
  path: /v1/comments
- description: List comment threads
  method: GET
  name: list-comment-threads
  path: /v1/comment-threads
- description: Create a new comment thread
  method: POST
  name: create-comment-thread
  path: /v1/comment-threads
- description: Update a comment thread
  method: PUT
  name: update-comment-thread
  path: /v1/comment-threads
- description: List subscriptions
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: Subscribe to a channel
  method: POST
  name: subscribe
  path: /v1/subscriptions
- description: Unsubscribe from a channel
  method: DELETE
  name: unsubscribe
  path: /v1/subscriptions
- description: List channels
  method: GET
  name: list-channels
  path: /v1/channels
- description: Update channel settings
  method: PUT
  name: update-channel
  path: /v1/channels
personas: []
provider_name: Youtube
provider_slug: youtube
search_terms:
- streaming
- subscribe to a channel
- video
- update channel
- subscribe to channel
- manage channel information
- manage channel subscriptions
- list channels
- manage comment threads
- update a comment thread
- youtube
- subscriptions
- comments
- community
- subscribe
- google
- update comment thread
- unsubscribe from a youtube channel
- list comments
- set moderation status on comments
- unsubscribe from channel
- create comment
- create comment thread
- create a new comment thread
- update an existing comment
- delete a comment
- list comment threads
- subscribe to a youtube channel
- list subscriptions
- unsubscribe
- update channel settings
- list youtube channels
- media
- manage individual comments
- list comments on a video or channel
- videos
- social
- post a new comment
- set moderation status
- update comment
- moderation
- unsubscribe from a channel
- list channel subscriptions
- update a comment
- delete comment
slug: community-engagement
source_filename: community-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: YouTube Community Engagement\n  description: Workflow for managing community interactions including comments, comment threads, subscriptions, and channel\n    management. Designed for community managers, social media teams, and content moderators.\n  tags:\n  - YouTube\n  - Community\n  - Comments\n  - Subscriptions\n  - Moderation\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    YOUTUBE_API_KEY: YOUTUBE_API_KEY\n    YOUTUBE_OAUTH_TOKEN: YOUTUBE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: youtube-data-api\n    baseUri: https://www.googleapis.com/youtube/v3\n    description: YouTube Data API v3 providing access to YouTube videos, channels, playlists, comments, subscriptions, captions,\n      and other resources.\n    authentication:\n      type: bearer\n      token: '{{YOUTUBE_OAUTH_TOKEN}}'\n    resources:\n    - name: videos\n      path: /videos\n      description: Operations\
  \ related to YouTube video resources\n      operations:\n      - name: list-videos\n        method: GET\n        description: Returns a list of videos that match the API request parameters\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties that the API response will include.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of YouTube video IDs for the resources being retrieved.\n        - name: chart\n          in: query\n          type: string\n          required: false\n          description: Identifies the chart that the API returns chart data for.\n        - name: myRating\n          in: query\n          type: string\n          required: false\n          description: Set this parameter to like or dislike to instruct the API to return only\
  \ videos liked or disliked by\n            the authenticated user.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned in the result set.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set that should be returned.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-video\n        method: POST\n        description: Uploads a video\
  \ to YouTube and optionally sets the video's metadata\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-video\n        method: PUT\n        description: Updates a video's metadata\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated\
  \ list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-video\n        method: DELETE\n        description: Deletes a YouTube video\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the video to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: video-ratings\n      path: /videos/rate\n      description: Operations related to YouTube video ratings\n      operations:\n      - name: rate-video\n        method: POST\n        description: Adds a like or dislike rating to a video or removes a rating from a video\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the video to rate.\n        - name: rating\n          in: query\n          type: string\n          required: true\n          description: The rating to record. Valid values are like, dislike, and none.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: channels\n      path: /channels\n\
  \      description: Operations related to YouTube channel resources\n      operations:\n      - name: list-channels\n        method: GET\n        description: Returns a collection of zero or more channel resources that match the request criteria\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of YouTube channel IDs for the resources being retrieved.\n        - name: mine\n          in: query\n          type: boolean\n          required: false\n          description: Set to true to return channels owned by the authenticated user.\n        - name: forUsername\n          in: query\n          type: string\n          required: false\n          description: A YouTube username identifying\
  \ a channel.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-channel\n        method: PUT\n        description: Updates a channel's metadata\n        inputParameters:\n        - name: part\n          in: query\n        \
  \  type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: playlists\n      path: /playlists\n      description: Operations related to YouTube playlist resources\n      operations:\n      - name: list-playlists\n        method: GET\n        description: Returns a collection of playlists that match the API request parameters\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n\
  \          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of YouTube playlist IDs.\n        - name: channelId\n          in: query\n          type: string\n          required: false\n          description: Indicates that the API response should only contain resources created by the channel.\n        - name: mine\n          in: query\n          type: boolean\n          required: false\n          description: Set to true to return playlists owned by the authenticated user.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result\
  \ set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-playlist\n        method: POST\n        description: Creates a playlist on behalf of the authenticated user\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n\
  \        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-playlist\n        method: PUT\n        description: Modifies a playlist\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: delete-playlist\n        method: DELETE\n        description: Deletes a playlist\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the playlist to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: playlist-items\n      path: /playlistItems\n      description: Operations related to items within YouTube playlists\n      operations:\n      - name: list-playlist-items\n        method: GET\n        description: Returns a collection of playlist items that match the API request parameters\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required:\
  \ true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: playlistId\n          in: query\n          type: string\n          required: false\n          description: Identifies the playlist whose items are being listed.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of playlist item IDs.\n        - name: videoId\n          in: query\n          type: string\n          required: false\n          description: Specifies that the request should return only items containing the given video.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n  \
  \      - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-playlist-item\n        method: POST\n        description: Adds a resource to a playlist\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n    \
  \      in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-playlist-item\n        method: DELETE\n        description: Deletes a playlist item\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the playlist item to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Operations for searching YouTube content\n      operations:\n      - name: search-list\n        method: GET\n        description: Returns\
  \ a collection of search results that match the query parameters\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: The query term to search for.\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Restricts a search query to only retrieve a particular type of resource.\n        - name: channelId\n          in: query\n          type: string\n          required: false\n          description: Indicates that the API response should only contain resources created by the channel.\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: Specifies the method that will be used to order\
  \ resources in the API response.\n        - name: publishedAfter\n          in: query\n          type: string\n          required: false\n          description: Restricts results to only include resources created at or after the specified time.\n        - name: publishedBefore\n          in: query\n          type: string\n          required: false\n          description: Restricts results to only include resources created before or at the specified time.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n     \
  \   - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /subscriptions\n      description: Operations related to YouTube channel subscriptions\n      operations:\n      - name: list-subscriptions\n        method: GET\n        description: Returns subscription resources that match the API request criteria\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of YouTube subscription IDs.\n        - name: mine\n          in: query\n         \
  \ type: boolean\n          required: false\n          description: Set to true to retrieve the subscriptions of the authenticated user.\n        - name: channelId\n          in: query\n          type: string\n          required: false\n          description: Retrieves subscriptions for the channel with the specified YouTube channel ID.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for\
  \ authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-subscription\n        method: POST\n        description: Adds a subscription for the authenticated user\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-subscription\n        method:\
  \ DELETE\n        description: Deletes a subscription\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the subscription to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments\n      path: /comments\n      description: Operations related to individual YouTube comments\n      operations:\n      - name: list-comments\n        method: GET\n        description: Returns a list of comments that match the API request parameters\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n\
  \        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of comment IDs.\n        - name: parentId\n          in: query\n          type: string\n          required: false\n          description: Identifies the comment thread whose comments are being listed.\n        - name: textFormat\n          in: query\n          type: string\n          required: false\n          description: Specifies whether the API should return comments formatted as HTML or plain text.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description:\
  \ Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-comment\n        method: POST\n        description: Creates a reply to an existing comment\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-comment\n        method: PUT\n        description: Modifies a comment\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-comment\n        method: DELETE\n        description: Deletes a comment\n    \
  \    inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the comment to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comment-moderation\n      path: /comments/setModerationStatus\n      description: Operations related to YouTube comment moderation\n      operations:\n      - name: set-comment-moderation-status\n        method: POST\n        description: Sets the moderation status of one or more comments\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of comment IDs to set moderation status for.\n        - name: moderationStatus\n          in:\
  \ query\n          type: string\n          required: true\n          description: Identifies the new moderation status. Acceptable values are heldForReview, published, and rejected.\n        - name: banAuthor\n          in: query\n          type: boolean\n          required: false\n          description: Set to true to ban the comment author from making future comments.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comment-threads\n      path: /commentThreads\n      description: Operations related to YouTube comment threads\n      operations:\n      - name: list-comment-threads\n        method: GET\n        description: Returns a list of comment threads that match the API request parameters\n        inputParameters:\n        - name: part\n          in:\
  \ query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of comment thread IDs.\n        - name: videoId\n          in: query\n          type: string\n          required: false\n          description: Instructs the API to return comment threads for the video with the specified ID.\n        - name: channelId\n          in: query\n          type: string\n          required: false\n          description: Instructs the API to return comment threads for the channel with the specified ID.\n        - name: moderationStatus\n          in: query\n          type: string\n          required: false\n          description: Set this parameter to limit the returned comment threads to only those with the specified moderation\n            status.\n        - name: maxResults\n\
  \          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-comment-thread\n        method: POST\n        description: Creates a new top-level comment\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required:\
  \ true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-comment-thread\n        method: PUT\n        description: Modifies the top-level comment in a comment thread\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required:\
  \ false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: captions\n      path: /captions\n      description: Operations related to YouTube video caption tracks\n      operations:\n      - name: list-captions\n        method: GET\n        description: Returns a list of caption tracks that are associated with a specified video\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: videoId\n          in: query\n          type: string\n          required: true\n          description: The\
  \ ID of the video for which the API should return caption tracks.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of caption track IDs to retrieve.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-caption\n        method: POST\n        description: Uploads a caption track\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties\
  \ to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-caption\n        method: PUT\n        description: Updates a caption track\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n  \
  \        in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-caption\n        method: DELETE\n        description: Deletes a specified caption track\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the caption track to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParamete\n\n# --- truncated at 32 KB (41 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/youtube/refs/heads/main/capabilities/community-engagement.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/youtube/refs/heads/main/capabilities/community-engagement.yaml
tags:
- YouTube
- Community
- Comments
- Subscriptions
- Moderation
tools:
- description: List comments on a video or channel
  hints:
    idempotent: true
    readOnly: true
  name: list-comments
- description: Post a new comment
  hints:
    idempotent: false
    readOnly: false
  name: create-comment
- description: Update an existing comment
  hints:
    idempotent: true
    readOnly: false
  name: update-comment
- description: Delete a comment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-comment
- description: Set moderation status on comments
  hints:
    idempotent: true
    readOnly: false
  name: set-moderation-status
- description: List comment threads
  hints:
    idempotent: true
    readOnly: true
  name: list-comment-threads
- description: Create a new comment thread
  hints:
    idempotent: false
    readOnly: false
  name: create-comment-thread
- description: List channel subscriptions
  hints:
    idempotent: true
    readOnly: true
  name: list-subscriptions
- description: Subscribe to a YouTube channel
  hints:
    idempotent: false
    readOnly: false
  name: subscribe-to-channel
- description: Unsubscribe from a YouTube channel
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: unsubscribe-from-channel
- description: List YouTube channels
  hints:
    idempotent: true
    readOnly: true
  name: list-channels
- description: Update channel settings
  hints:
    idempotent: true
    readOnly: false
  name: update-channel
---
