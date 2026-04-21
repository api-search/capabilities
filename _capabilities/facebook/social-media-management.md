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
- Conversational Commerce
- get posts from a user's feed.
- social networking
- create post
- direct messaging and customer communication.
- create a new threads post.
- list instagram media for an account.
- customer messaging across messenger and whatsapp.
- creates and publishes visual and text content.
- create a threads post.
- manage content across facebook, instagram, and threads.
- publish instagram media.
- campaign management and audience targeting.
- manages content and engagement across meta platforms.
- Ad Operations
- list posts
- get instagram performance insights.
- content publishing
- publishing
- create instagram media
- threads content management.
- create threads post
- get posts from a facebook user's feed.
- social media
- get threads performance insights.
- content management
- manage advertising campaigns and performance.
- Social Media Manager
- get facebook feed
- messaging
- create a new facebook post.
- get threads insights
- advertising
- instagram content management.
- publish instagram media
- manages day-to-day ad campaign optimization.
- facebook post management.
- Customer Support
- performance tracking and insights.
- plans and executes advertising campaigns.
- Content Creator
- publishing and managing content across platforms.
- facebook
- handles customer inquiries via messaging channels.
- Marketing Manager
- create facebook post
- get instagram insights
- list instagram media
- create and publish instagram content.
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
