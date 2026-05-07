---
categories:
- content-management
consumed_apis: []
description: Unified workflow for managing YouTube video content lifecycle including uploading, updating, organizing into playlists, managing captions, and moderating comments. Designed for content creators, media teams, and platform administrators.
layout: capability
name: YouTube Content Management
operations:
- description: List videos matching criteria
  method: GET
  name: list-videos
  path: /v1/videos
- description: Upload a new video
  method: POST
  name: upload-video
  path: /v1/videos
- description: Update video metadata
  method: PUT
  name: update-video
  path: /v1/videos
- description: Delete a video
  method: DELETE
  name: delete-video
  path: /v1/videos
- description: List playlists
  method: GET
  name: list-playlists
  path: /v1/playlists
- description: Create a new playlist
  method: POST
  name: create-playlist
  path: /v1/playlists
- description: Update playlist details
  method: PUT
  name: update-playlist
  path: /v1/playlists
- description: Delete a playlist
  method: DELETE
  name: delete-playlist
  path: /v1/playlists
- description: List items in a playlist
  method: GET
  name: list-playlist-items
  path: /v1/playlist-items
- description: Add a video to a playlist
  method: POST
  name: add-playlist-item
  path: /v1/playlist-items
- description: Remove a video from a playlist
  method: DELETE
  name: remove-playlist-item
  path: /v1/playlist-items
- description: List caption tracks for a video
  method: GET
  name: list-captions
  path: /v1/captions
- description: Upload a caption track
  method: POST
  name: upload-caption
  path: /v1/captions
- description: Update a caption track
  method: PUT
  name: update-caption
  path: /v1/captions
- description: Delete a caption track
  method: DELETE
  name: delete-caption
  path: /v1/captions
personas: []
provider_name: Youtube
provider_slug: youtube
search_terms:
- upload a new video to youtube
- streaming
- video
- remove a video from a playlist
- list captions
- update playlist
- list youtube playlists
- delete a video from youtube
- remove playlist item
- delete caption
- create playlist
- youtube
- update playlist details
- delete a playlist
- delete video
- list playlist items
- google
- upload a new video
- update caption
- list playlists
- manage youtube videos
- add playlist item
- delete a video
- add a video to a playlist
- list caption tracks for a video
- list items in a playlist
- manage youtube playlists
- list youtube videos matching criteria
- upload caption
- manage video captions
- media
- content management
- playlists
- captions
- list videos
- update video metadata
- manage items within playlists
- upload a caption track
- videos
- social
- update a caption track
- delete a caption track
- list videos matching criteria
- delete playlist
- upload video
- update video
- upload a new caption track
- create a new playlist
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: YouTube Content Management\n  description: Unified workflow for managing YouTube video content lifecycle including uploading, updating, organizing into\n    playlists, managing captions, and moderating comments. Designed for content creators, media teams, and platform administrators.\n  tags:\n  - YouTube\n  - Content Management\n  - Video\n  - Playlists\n  - Captions\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    YOUTUBE_API_KEY: YOUTUBE_API_KEY\n    YOUTUBE_OAUTH_TOKEN: YOUTUBE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: youtube-data-api\n    baseUri: https://www.googleapis.com/youtube/v3\n    description: YouTube Data API v3 providing access to YouTube videos, channels, playlists, comments, subscriptions, captions,\n      and other resources.\n    authentication:\n      type: bearer\n      token: '{{YOUTUBE_OAUTH_TOKEN}}'\n    resources:\n    - name: videos\n    \
  \  path: /videos\n      description: Operations related to YouTube video resources\n      operations:\n      - name: list-videos\n        method: GET\n        description: Returns a list of videos that match the API request parameters\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties that the API response will include.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of YouTube video IDs for the resources being retrieved.\n        - name: chart\n          in: query\n          type: string\n          required: false\n          description: Identifies the chart that the API returns chart data for.\n        - name: myRating\n          in: query\n          type: string\n          required: false\n          description: Set this parameter to like\
  \ or dislike to instruct the API to return only videos liked or disliked by\n            the authenticated user.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned in the result set.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set that should be returned.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-video\n        method:\
  \ POST\n        description: Uploads a video to YouTube and optionally sets the video's metadata\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-video\n        method: PUT\n        description: Updates a video's metadata\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n      \
  \    description: Specifies a comma-separated list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-video\n        method: DELETE\n        description: Deletes a YouTube video\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the video to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: video-ratings\n      path: /videos/rate\n      description: Operations related to YouTube video ratings\n      operations:\n      - name: rate-video\n        method: POST\n        description: Adds a like or dislike rating to a video or removes a rating from a video\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the video to rate.\n        - name: rating\n          in: query\n          type: string\n          required: true\n          description: The rating to record. Valid values are like, dislike, and none.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: channels\n      path: /channels\n      description: Operations related to YouTube channel resources\n      operations:\n      - name: list-channels\n        method: GET\n        description: Returns a collection of zero or more channel resources that match the request criteria\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of YouTube channel IDs for the resources being retrieved.\n        - name: mine\n          in: query\n          type: boolean\n          required: false\n          description: Set to true to return channels owned by the authenticated user.\n        - name: forUsername\n          in: query\n          type: string\n          required: false\n     \
  \     description: A YouTube username identifying a channel.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-channel\n        method: PUT\n        description: Updates a channel's metadata\n        inputParameters:\n   \
  \     - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: playlists\n      path: /playlists\n      description: Operations related to YouTube playlist resources\n      operations:\n      - name: list-playlists\n        method: GET\n        description: Returns a collection of playlists that match the API request parameters\n        inputParameters:\n        - name: part\n          in: query\n\
  \          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of YouTube playlist IDs.\n        - name: channelId\n          in: query\n          type: string\n          required: false\n          description: Indicates that the API response should only contain resources created by the channel.\n        - name: mine\n          in: query\n          type: boolean\n          required: false\n          description: Set to true to return playlists owned by the authenticated user.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description:\
  \ Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-playlist\n        method: POST\n        description: Creates a playlist on behalf of the authenticated user\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which\
  \ fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-playlist\n        method: PUT\n        description: Modifies a playlist\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-playlist\n        method: DELETE\n        description: Deletes a playlist\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the playlist to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: playlist-items\n      path: /playlistItems\n      description: Operations related to items within YouTube playlists\n      operations:\n      - name: list-playlist-items\n        method: GET\n        description: Returns a collection of playlist items that match the API request parameters\n        inputParameters:\n        - name: part\n          in:\
  \ query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: playlistId\n          in: query\n          type: string\n          required: false\n          description: Identifies the playlist whose items are being listed.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of playlist item IDs.\n        - name: videoId\n          in: query\n          type: string\n          required: false\n          description: Specifies that the request should return only items containing the given video.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description:\
  \ Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-playlist-item\n        method: POST\n        description: Adds a resource to a playlist\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include\
  \ in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-playlist-item\n        method: DELETE\n        description: Deletes a playlist item\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the playlist item to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Operations for searching YouTube content\n      operations:\n      - name: search-list\n\
  \        method: GET\n        description: Returns a collection of search results that match the query parameters\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: The query term to search for.\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Restricts a search query to only retrieve a particular type of resource.\n        - name: channelId\n          in: query\n          type: string\n          required: false\n          description: Indicates that the API response should only contain resources created by the channel.\n        - name: order\n          in: query\n          type: string\n          required: false\n          description:\
  \ Specifies the method that will be used to order resources in the API response.\n        - name: publishedAfter\n          in: query\n          type: string\n          required: false\n          description: Restricts results to only include resources created at or after the specified time.\n        - name: publishedBefore\n          in: query\n          type: string\n          required: false\n          description: Restricts results to only include resources created before or at the specified time.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which\
  \ fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /subscriptions\n      description: Operations related to YouTube channel subscriptions\n      operations:\n      - name: list-subscriptions\n        method: GET\n        description: Returns subscription resources that match the API request criteria\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of YouTube subscription IDs.\n    \
  \    - name: mine\n          in: query\n          type: boolean\n          required: false\n          description: Set to true to retrieve the subscriptions of the authenticated user.\n        - name: channelId\n          in: query\n          type: string\n          required: false\n          description: Retrieves subscriptions for the channel with the specified YouTube channel ID.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required:\
  \ false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-subscription\n        method: POST\n        description: Adds a subscription for the authenticated user\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: delete-subscription\n        method: DELETE\n        description: Deletes a subscription\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the subscription to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments\n      path: /comments\n      description: Operations related to individual YouTube comments\n      operations:\n      - name: list-comments\n        method: GET\n        description: Returns a list of comments that match the API request parameters\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one\
  \ or more resource properties to include.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of comment IDs.\n        - name: parentId\n          in: query\n          type: string\n          required: false\n          description: Identifies the comment thread whose comments are being listed.\n        - name: textFormat\n          in: query\n          type: string\n          required: false\n          description: Specifies whether the API should return comments formatted as HTML or plain text.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n\
  \          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-comment\n        method: POST\n        description: Creates a reply to an existing comment\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n\
  \          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-comment\n        method: PUT\n        description: Modifies a comment\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-comment\n        method: DELETE\n\
  \        description: Deletes a comment\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the comment to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comment-moderation\n      path: /comments/setModerationStatus\n      description: Operations related to YouTube comment moderation\n      operations:\n      - name: set-comment-moderation-status\n        method: POST\n        description: Sets the moderation status of one or more comments\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of comment IDs to set moderation status for.\n  \
  \      - name: moderationStatus\n          in: query\n          type: string\n          required: true\n          description: Identifies the new moderation status. Acceptable values are heldForReview, published, and rejected.\n        - name: banAuthor\n          in: query\n          type: boolean\n          required: false\n          description: Set to true to ban the comment author from making future comments.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comment-threads\n      path: /commentThreads\n      description: Operations related to YouTube comment threads\n      operations:\n      - name: list-comment-threads\n        method: GET\n        description: Returns a list of comment threads that match the API request parameters\n        inputParameters:\n\
  \        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of comment thread IDs.\n        - name: videoId\n          in: query\n          type: string\n          required: false\n          description: Instructs the API to return comment threads for the video with the specified ID.\n        - name: channelId\n          in: query\n          type: string\n          required: false\n          description: Instructs the API to return comment threads for the channel with the specified ID.\n        - name: moderationStatus\n          in: query\n          type: string\n          required: false\n          description: Set this parameter to limit the returned comment threads to only those with the specified moderation\n  \
  \          status.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of items that should be returned.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Identifies a specific page in the result set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-comment-thread\n        method: POST\n        description: Creates a new top-level comment\n        inputParameters:\n        - name: part\n          in:\
  \ query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-comment-thread\n        method: PUT\n        description: Modifies the top-level comment in a comment thread\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to update.\n        - name: fields\n    \
  \      in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: captions\n      path: /captions\n      description: Operations related to YouTube video caption tracks\n      operations:\n      - name: list-captions\n        method: GET\n        description: Returns a list of caption tracks that are associated with a specified video\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to include.\n        - name: videoId\n          in: query\n          type:\
  \ string\n          required: true\n          description: The ID of the video for which the API should return caption tracks.\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of caption track IDs to retrieve.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insert-caption\n        method: POST\n        description: Uploads a caption track\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies\
  \ a comma-separated list of one or more resource properties to set.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-caption\n        method: PUT\n        description: Updates a caption track\n        inputParameters:\n        - name: part\n          in: query\n          type: string\n          required: true\n          description: Specifies a comma-separated list of one or more resource properties to update.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Selector specifying which fields to\
  \ include in a partial response.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-caption\n        method: DELETE\n        description: Deletes a specified caption track\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: The ID of the caption track to delete.\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: API key for authentication.\n        outputR\n\n# --- truncated at 32 KB (43 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/youtube/refs/heads/main/capabilities/content-management.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/youtube/refs/heads/main/capabilities/content-management.yaml
tags:
- YouTube
- Content Management
- Video
- Playlists
- Captions
tools:
- description: List YouTube videos matching criteria
  hints:
    idempotent: true
    readOnly: true
  name: list-videos
- description: Upload a new video to YouTube
  hints:
    idempotent: false
    readOnly: false
  name: upload-video
- description: Update video metadata
  hints:
    idempotent: true
    readOnly: false
  name: update-video
- description: Delete a video from YouTube
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-video
- description: List YouTube playlists
  hints:
    idempotent: true
    readOnly: true
  name: list-playlists
- description: Create a new playlist
  hints:
    idempotent: false
    readOnly: false
  name: create-playlist
- description: Update playlist details
  hints:
    idempotent: true
    readOnly: false
  name: update-playlist
- description: Delete a playlist
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-playlist
- description: List items in a playlist
  hints:
    idempotent: true
    readOnly: true
  name: list-playlist-items
- description: Add a video to a playlist
  hints:
    idempotent: false
    readOnly: false
  name: add-playlist-item
- description: Remove a video from a playlist
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-playlist-item
- description: List caption tracks for a video
  hints:
    idempotent: true
    readOnly: true
  name: list-captions
- description: Upload a new caption track
  hints:
    idempotent: false
    readOnly: false
  name: upload-caption
- description: Update a caption track
  hints:
    idempotent: true
    readOnly: false
  name: update-caption
- description: Delete a caption track
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-caption
---
