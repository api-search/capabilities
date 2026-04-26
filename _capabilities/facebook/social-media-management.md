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
- get threads insights
- Marketing Manager
- list instagram media
- Ad Operations
- get posts from a user's feed.
- manages content and engagement across meta platforms.
- social networking
- facebook
- create facebook post
- create and publish instagram content.
- create instagram media
- content management
- social media
- publishing
- Conversational Commerce
- threads content management.
- manage advertising campaigns and performance.
- create post
- list instagram media.
- get instagram performance insights.
- customer messaging across messenger and whatsapp.
- publish instagram media.
- manages day-to-day ad campaign optimization.
- advertising
- list posts
- get posts from a facebook user's feed.
- manage content across facebook, instagram, and threads.
- Social Media Manager
- facebook post management.
- instagram content management.
- messaging
- get facebook feed
- create a threads post.
- get instagram insights
- get threads performance insights.
- performance tracking and insights.
- direct messaging and customer communication.
- content publishing
- Content Creator
- plans and executes advertising campaigns.
- create a new facebook post.
- Customer Support
- create a new threads post.
- creates and publishes visual and text content.
- handles customer inquiries via messaging channels.
- create threads post
- publish instagram media
- list instagram media for an account.
- publishing and managing content across platforms.
- campaign management and audience targeting.
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
