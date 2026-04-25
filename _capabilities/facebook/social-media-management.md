---
consumed_apis:
- graph-api
- instagram-api
- threads-api
description: Workflow capability for managing content across Facebook, Instagram, and Threads. Combines Graph API for Facebook posts, Instagram API for visual content, and Threads API for text-based publishing. Used by social media managers and content creators.
layout: capability
name: Facebook Social Media Management
operations:
- description: Get posts from a user's feed.
  method: GET
  name: list-posts
  path: /v1/posts
- description: Create a new Facebook post.
  method: POST
  name: create-post
  path: /v1/posts
- description: List Instagram media.
  method: GET
  name: list-instagram-media
  path: /v1/instagram-media
- description: Publish Instagram media.
  method: POST
  name: publish-instagram-media
  path: /v1/instagram-media
- description: Create a Threads post.
  method: POST
  name: create-threads-post
  path: /v1/threads
personas: []
provider_name: Facebook
provider_slug: facebook
search_terms:
- list instagram media.
- performance tracking and insights.
- manage content across facebook, instagram, and threads.
- content publishing
- creates and publishes visual and text content.
- instagram content management.
- get posts from a facebook user's feed.
- list instagram media for an account.
- Conversational Commerce
- create a new facebook post.
- social media
- get instagram performance insights.
- get threads insights
- manages day-to-day ad campaign optimization.
- social networking
- Customer Support
- get posts from a user's feed.
- create facebook post
- Marketing Manager
- Ad Operations
- manages content and engagement across meta platforms.
- direct messaging and customer communication.
- threads content management.
- get facebook feed
- publish instagram media.
- create a new threads post.
- manage advertising campaigns and performance.
- publishing
- create threads post
- Content Creator
- publish instagram media
- get threads performance insights.
- campaign management and audience targeting.
- create post
- messaging
- create instagram media
- facebook
- facebook post management.
- create and publish instagram content.
- list instagram media
- advertising
- publishing and managing content across platforms.
- customer messaging across messenger and whatsapp.
- handles customer inquiries via messaging channels.
- content management
- Social Media Manager
- create a threads post.
- get instagram insights
- list posts
- plans and executes advertising campaigns.
slug: social-media-management
tags:
- Facebook
- Social Media
- Content Management
- Publishing
tools:
- description: Get posts from a Facebook user's feed.
  hints:
    readOnly: true
  name: get-facebook-feed
- description: Create a new Facebook post.
  hints:
    readOnly: false
  name: create-facebook-post
- description: List Instagram media for an account.
  hints:
    readOnly: true
  name: list-instagram-media
- description: Create and publish Instagram content.
  hints:
    readOnly: false
  name: create-instagram-media
- description: Get Instagram performance insights.
  hints:
    readOnly: true
  name: get-instagram-insights
- description: Create a new Threads post.
  hints:
    readOnly: false
  name: create-threads-post
- description: Get Threads performance insights.
  hints:
    readOnly: true
  name: get-threads-insights
---
