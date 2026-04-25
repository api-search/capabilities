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
- content management
- get threads insights
- manages content and engagement across meta platforms.
- Content Creator
- create instagram media
- Social Media Manager
- Marketing Manager
- create threads post
- social media
- list instagram media.
- plans and executes advertising campaigns.
- performance tracking and insights.
- create post
- facebook
- content publishing
- direct messaging and customer communication.
- messaging
- publishing
- manage content across facebook, instagram, and threads.
- manage advertising campaigns and performance.
- customer messaging across messenger and whatsapp.
- creates and publishes visual and text content.
- manages day-to-day ad campaign optimization.
- list posts
- create a new threads post.
- facebook post management.
- publish instagram media.
- publishing and managing content across platforms.
- social networking
- get posts from a facebook user's feed.
- create and publish instagram content.
- instagram content management.
- list instagram media for an account.
- get facebook feed
- create facebook post
- Ad Operations
- create a new facebook post.
- publish instagram media
- campaign management and audience targeting.
- get instagram performance insights.
- create a threads post.
- threads content management.
- advertising
- get instagram insights
- get posts from a user's feed.
- handles customer inquiries via messaging channels.
- Customer Support
- Conversational Commerce
- list instagram media
- get threads performance insights.
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
