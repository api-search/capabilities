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
- get posts from a facebook user's feed.
- get facebook feed
- Marketing Manager
- manage advertising campaigns and performance.
- direct messaging and customer communication.
- facebook
- get threads insights
- list instagram media for an account.
- publishing and managing content across platforms.
- get instagram performance insights.
- advertising
- create facebook post
- create post
- threads content management.
- Content Creator
- content management
- create a new threads post.
- Social Media Manager
- Conversational Commerce
- create threads post
- list posts
- facebook post management.
- publish instagram media
- creates and publishes visual and text content.
- create a new facebook post.
- Customer Support
- get threads performance insights.
- create and publish instagram content.
- create a threads post.
- customer messaging across messenger and whatsapp.
- handles customer inquiries via messaging channels.
- messaging
- plans and executes advertising campaigns.
- instagram content management.
- get posts from a user's feed.
- list instagram media
- publishing
- manage content across facebook, instagram, and threads.
- create instagram media
- performance tracking and insights.
- campaign management and audience targeting.
- social networking
- social media
- publish instagram media.
- get instagram insights
- Ad Operations
- manages day-to-day ad campaign optimization.
- list instagram media.
- content publishing
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
