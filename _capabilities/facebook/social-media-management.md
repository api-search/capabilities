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
- publish instagram media.
- create threads post
- instagram content management.
- create facebook post
- publish instagram media
- create a new threads post.
- campaign management and audience targeting.
- content management
- get posts from a facebook user's feed.
- content publishing
- social media
- create and publish instagram content.
- Conversational Commerce
- publishing and managing content across platforms.
- create post
- get threads insights
- list instagram media for an account.
- list instagram media.
- manage content across facebook, instagram, and threads.
- get posts from a user's feed.
- messaging
- advertising
- facebook
- get threads performance insights.
- publishing
- creates and publishes visual and text content.
- Customer Support
- Marketing Manager
- Ad Operations
- create a new facebook post.
- get instagram insights
- create a threads post.
- customer messaging across messenger and whatsapp.
- create instagram media
- threads content management.
- direct messaging and customer communication.
- Social Media Manager
- plans and executes advertising campaigns.
- facebook post management.
- social networking
- get facebook feed
- manages day-to-day ad campaign optimization.
- Content Creator
- list instagram media
- list posts
- get instagram performance insights.
- manage advertising campaigns and performance.
- manages content and engagement across meta platforms.
- performance tracking and insights.
- handles customer inquiries via messaging channels.
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
