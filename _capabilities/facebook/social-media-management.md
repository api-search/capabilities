---
categories:
- content-management
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
- get instagram performance insights.
- list posts
- creates and publishes visual and text content.
- create post
- manage content across facebook, instagram, and threads.
- get threads insights
- get facebook feed
- instagram content management.
- create a threads post.
- list instagram media for an account.
- Ad Operations
- list instagram media.
- get posts from a facebook user's feed.
- messaging
- create a new threads post.
- direct messaging and customer communication.
- manages day-to-day ad campaign optimization.
- get instagram insights
- publish instagram media
- content management
- create facebook post
- get threads performance insights.
- publishing
- Conversational Commerce
- performance tracking and insights.
- create and publish instagram content.
- facebook
- publish instagram media.
- Social Media Manager
- content publishing
- Customer Support
- social networking
- customer messaging across messenger and whatsapp.
- facebook post management.
- Marketing Manager
- create threads post
- handles customer inquiries via messaging channels.
- advertising
- create instagram media
- manage advertising campaigns and performance.
- publishing and managing content across platforms.
- get posts from a user's feed.
- manages content and engagement across meta platforms.
- threads content management.
- create a new facebook post.
- plans and executes advertising campaigns.
- campaign management and audience targeting.
- list instagram media
- social media
- Content Creator
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
