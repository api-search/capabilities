---
categories:
- content-management
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
- create, manage, and analyze posts, media, bookmarks, and lists.
- getPostsByIds
- marketing
- get a list by its id
- handles customer inquiries and issues via direct messages and replies.
- get posts from a list's timeline
- delete a post by its id
- publishing
- builds and maintains communities through engagement and moderation.
- initializeMediaUpload
- get post analytics
- addListsMember
- microblogging
- getPostsAnalytics
- posts
- get the processing status of an uploaded media
- create and retrieve posts
- extracts insights from social data through search, streaming, and analytics.
- createUsersBookmark
- create a new list on x
- engagement specialist
- manages data pipelines, streaming ingestion, and compliance data flows.
- get analytics data for a specific post
- createLists
- produces original posts, threads, and media content on x.
- finalize a chunked media upload
- user relationships, direct messaging, spaces, and community interaction.
- get bookmarked posts for the authenticated user
- deleteUsersBookmark
- streaming
- create a new post
- getMediaUploadStatus
- finalize chunked upload
- post creation, editing, media management, and content analytics.
- data engineer
- getListsPosts
- manages brand presence, campaigns, and content strategy.
- getUsersBookmarks
- real-time data
- upload media
- manage compliance jobs, data streams, and real-time compliance monitoring.
- upload media for posts
- ensures data handling meets regulatory and platform compliance requirements.
- initialize chunked upload
- create a new list
- manage list members
- mediaUpload
- platform operations
- retrieve multiple posts by their ids
- get posts from a list timeline
- bookmark a post
- finalizeMediaUpload
- community manager
- manages user relationships, follows, and interaction strategies.
- social monitoring, search, trending topics, and sentiment analysis.
- manage user relationships, direct messages, spaces, and community interactions.
- create or update metadata (alt text) for uploaded media
- append a chunk to an in-progress media upload
- getListsById
- x api
- retrieve posts by ids
- delete a post
- get bookmarked posts
- remove a bookmark
- customer support
- upload media for posts (simple upload for small files)
- updateLists
- data analyst
- compliance officer
- manage user bookmarks
- advertising
- creates, schedules, and analyzes social media content across platforms.
- deletePostById
- appendMediaUpload
- initialize a chunked media upload
- monitor conversations, search posts, analyze trends, and extract insights.
- social media
- conducts academic or market research using x data archives.
- getListsMembers
- data compliance, deletion tracking, and regulatory event monitoring.
- content
- update a list's name or description
- brand manager
- get the members of a list
- researcher
- monitors brand mentions, sentiment, and competitive landscape.
- get analytics for a post
- deleteLists
- delete a list
- social media manager
- create a new post (tweet) on x
- createPosts
- manage a specific post
- create lists
- content creator
- add a member to a list
- media
- marketing team
- createMediaMetadata
- get list posts
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
