---
consumed_apis:
- x-posts
- x-media
- x-bookmarks
- x-lists
description: Unified workflow for creating, managing, and analyzing posts, media, bookmarks, and lists on X. Used by social media managers, content creators, and marketing teams.
layout: capability
name: X Content Publishing and Management
operations:
- description: Create a new post
  method: POST
  name: createPosts
  path: /v1/content/posts
- description: Retrieve posts by IDs
  method: GET
  name: getPostsByIds
  path: /v1/content/posts
- description: Delete a post
  method: DELETE
  name: deletePostById
  path: /v1/content/posts/{id}
- description: Get analytics for a post
  method: GET
  name: getPostsAnalytics
  path: /v1/content/posts/{id}/analytics
- description: Upload media for posts
  method: POST
  name: mediaUpload
  path: /v1/content/media/upload
- description: Initialize a chunked media upload
  method: POST
  name: initializeMediaUpload
  path: /v1/content/media/upload/initialize
- description: Finalize a chunked media upload
  method: POST
  name: finalizeMediaUpload
  path: /v1/content/media/upload/finalize
- description: Bookmark a post
  method: POST
  name: createUsersBookmark
  path: /v1/content/users/{id}/bookmarks
- description: Get bookmarked posts
  method: GET
  name: getUsersBookmarks
  path: /v1/content/users/{id}/bookmarks
- description: Create a new list
  method: POST
  name: createLists
  path: /v1/content/lists
- description: Add a member to a list
  method: POST
  name: addListsMember
  path: /v1/content/lists/{id}/members
- description: Get posts from a list timeline
  method: GET
  name: getListsPosts
  path: /v1/content/lists/{id}/posts
personas:
- description: Creates, schedules, and analyzes social media content across platforms.
  id: social-media-manager
  name: Social Media Manager
- description: Produces original posts, threads, and media content on X.
  id: content-creator
  name: Content Creator
- description: Manages brand presence, campaigns, and content strategy.
  id: marketing-team
  name: Marketing Team
provider_name: X (Twitter)
provider_slug: twitter
search_terms:
- compliance officer
- bookmark a post
- remove a bookmark
- creates, schedules, and analyzes social media content across platforms.
- extracts insights from social data through search, streaming, and analytics.
- getListsPosts
- manages user relationships, follows, and interaction strategies.
- posts
- publishing
- append a chunk to an in-progress media upload
- platform operations
- get the members of a list
- manage list members
- get posts from a list's timeline
- streaming
- mediaUpload
- marketing team
- ensures data handling meets regulatory and platform compliance requirements.
- create a new post
- finalize chunked upload
- update a list's name or description
- createPosts
- manages brand presence, campaigns, and content strategy.
- getUsersBookmarks
- marketing
- get post analytics
- upload media for posts
- engagement specialist
- add a member to a list
- create a new post (tweet) on x
- media
- manage user relationships, direct messages, spaces, and community interactions.
- get list posts
- get analytics for a post
- appendMediaUpload
- content
- initialize a chunked media upload
- get analytics data for a specific post
- social media
- create lists
- manages data pipelines, streaming ingestion, and compliance data flows.
- get bookmarked posts
- createLists
- getMediaUploadStatus
- get posts from a list timeline
- monitors brand mentions, sentiment, and competitive landscape.
- get the processing status of an uploaded media
- delete a post
- social media manager
- microblogging
- create and retrieve posts
- real-time data
- post creation, editing, media management, and content analytics.
- deleteLists
- customer support
- deletePostById
- upload media
- initialize chunked upload
- create a new list
- researcher
- advertising
- initializeMediaUpload
- getPostsAnalytics
- user relationships, direct messaging, spaces, and community interaction.
- manage user bookmarks
- getListsById
- retrieve posts by ids
- content creator
- addListsMember
- finalizeMediaUpload
- x api
- monitor conversations, search posts, analyze trends, and extract insights.
- social monitoring, search, trending topics, and sentiment analysis.
- create or update metadata (alt text) for uploaded media
- data analyst
- getListsMembers
- manage a specific post
- brand manager
- getPostsByIds
- retrieve multiple posts by their ids
- create a new list on x
- manage compliance jobs, data streams, and real-time compliance monitoring.
- createUsersBookmark
- create, manage, and analyze posts, media, bookmarks, and lists.
- handles customer inquiries and issues via direct messages and replies.
- conducts academic or market research using x data archives.
- data compliance, deletion tracking, and regulatory event monitoring.
- get bookmarked posts for the authenticated user
- delete a post by its id
- get a list by its id
- deleteUsersBookmark
- data engineer
- produces original posts, threads, and media content on x.
- upload media for posts (simple upload for small files)
- updateLists
- delete a list
- finalize a chunked media upload
- createMediaMetadata
- community manager
- builds and maintains communities through engagement and moderation.
slug: content-publishing
tags:
- X API
- Content
- Publishing
- Posts
- Media
- Marketing
tools:
- description: Create a new post (tweet) on X
  hints:
    idempotent: false
    readOnly: false
  name: createPosts
- description: Retrieve multiple posts by their IDs
  hints:
    idempotent: true
    readOnly: true
  name: getPostsByIds
- description: Delete a post by its ID
  hints:
    destructive: true
    readOnly: false
  name: deletePostById
- description: Get analytics data for a specific post
  hints:
    idempotent: true
    readOnly: true
  name: getPostsAnalytics
- description: Upload media for posts (simple upload for small files)
  hints:
    idempotent: false
    readOnly: false
  name: mediaUpload
- description: Initialize a chunked media upload
  hints:
    idempotent: false
    readOnly: false
  name: initializeMediaUpload
- description: Append a chunk to an in-progress media upload
  hints:
    idempotent: true
    readOnly: false
  name: appendMediaUpload
- description: Finalize a chunked media upload
  hints:
    idempotent: false
    readOnly: false
  name: finalizeMediaUpload
- description: Get the processing status of an uploaded media
  hints:
    idempotent: true
    readOnly: true
  name: getMediaUploadStatus
- description: Create or update metadata (alt text) for uploaded media
  hints:
    idempotent: true
    readOnly: false
  name: createMediaMetadata
- description: Bookmark a post
  hints:
    idempotent: false
    readOnly: false
  name: createUsersBookmark
- description: Get bookmarked posts for the authenticated user
  hints:
    idempotent: true
    readOnly: true
  name: getUsersBookmarks
- description: Remove a bookmark
  hints:
    destructive: true
    readOnly: false
  name: deleteUsersBookmark
- description: Create a new list on X
  hints:
    idempotent: false
    readOnly: false
  name: createLists
- description: Get a list by its ID
  hints:
    idempotent: true
    readOnly: true
  name: getListsById
- description: Update a list's name or description
  hints:
    idempotent: true
    readOnly: false
  name: updateLists
- description: Add a member to a list
  hints:
    idempotent: false
    readOnly: false
  name: addListsMember
- description: Get the members of a list
  hints:
    idempotent: true
    readOnly: true
  name: getListsMembers
- description: Get posts from a list's timeline
  hints:
    idempotent: true
    readOnly: true
  name: getListsPosts
- description: Delete a list
  hints:
    destructive: true
    readOnly: false
  name: deleteLists
---
