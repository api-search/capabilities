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
- get posts from a facebook user's feed.
- Customer Support
- create facebook post
- list instagram media
- get threads performance insights.
- list instagram media for an account.
- get instagram performance insights.
- advertising
- manage advertising campaigns and performance.
- publishing
- social networking
- publishing and managing content across platforms.
- instagram content management.
- create post
- get instagram insights
- manages day-to-day ad campaign optimization.
- create instagram media
- performance tracking and insights.
- create threads post
- Social Media Manager
- direct messaging and customer communication.
- facebook
- create a new facebook post.
- publish instagram media
- content management
- get facebook feed
- create a threads post.
- handles customer inquiries via messaging channels.
- threads content management.
- publish instagram media.
- Ad Operations
- content publishing
- list instagram media.
- create a new threads post.
- create and publish instagram content.
- get threads insights
- Marketing Manager
- Conversational Commerce
- manage content across facebook, instagram, and threads.
- Content Creator
- messaging
- customer messaging across messenger and whatsapp.
- plans and executes advertising campaigns.
- get posts from a user's feed.
- manages content and engagement across meta platforms.
- creates and publishes visual and text content.
- campaign management and audience targeting.
- social media
- list posts
- facebook post management.
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
