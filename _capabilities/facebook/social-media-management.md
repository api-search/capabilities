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
- get posts from a user's feed.
- publish instagram media.
- advertising
- list posts
- create and publish instagram content.
- manage advertising campaigns and performance.
- publish instagram media
- get facebook feed
- Marketing Manager
- get threads insights
- customer messaging across messenger and whatsapp.
- facebook post management.
- create threads post
- create a new threads post.
- threads content management.
- manage content across facebook, instagram, and threads.
- create facebook post
- Social Media Manager
- facebook
- handles customer inquiries via messaging channels.
- get instagram performance insights.
- performance tracking and insights.
- campaign management and audience targeting.
- direct messaging and customer communication.
- list instagram media for an account.
- plans and executes advertising campaigns.
- social networking
- publishing
- Conversational Commerce
- messaging
- list instagram media
- create a threads post.
- social media
- Customer Support
- manages day-to-day ad campaign optimization.
- create instagram media
- get threads performance insights.
- create a new facebook post.
- Ad Operations
- instagram content management.
- creates and publishes visual and text content.
- content management
- list instagram media.
- get posts from a facebook user's feed.
- content publishing
- publishing and managing content across platforms.
- create post
- get instagram insights
- Content Creator
- manages content and engagement across meta platforms.
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
