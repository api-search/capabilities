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
- manages day-to-day ad campaign optimization.
- social media
- facebook
- get posts from a user's feed.
- threads content management.
- create facebook post
- get threads performance insights.
- advertising
- handles customer inquiries via messaging channels.
- campaign management and audience targeting.
- Customer Support
- instagram content management.
- direct messaging and customer communication.
- list instagram media
- publish instagram media
- manage content across facebook, instagram, and threads.
- plans and executes advertising campaigns.
- content publishing
- create and publish instagram content.
- messaging
- get threads insights
- customer messaging across messenger and whatsapp.
- Marketing Manager
- create post
- create a threads post.
- content management
- publish instagram media.
- list posts
- list instagram media.
- Social Media Manager
- manages content and engagement across meta platforms.
- get posts from a facebook user's feed.
- Ad Operations
- get instagram insights
- Content Creator
- create a new facebook post.
- list instagram media for an account.
- create a new threads post.
- get instagram performance insights.
- social networking
- create instagram media
- performance tracking and insights.
- creates and publishes visual and text content.
- publishing and managing content across platforms.
- Conversational Commerce
- facebook post management.
- get facebook feed
- publishing
- manage advertising campaigns and performance.
- create threads post
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
