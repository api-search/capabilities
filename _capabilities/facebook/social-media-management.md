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
- get threads performance insights.
- get posts from a user's feed.
- publish instagram media.
- manage advertising campaigns and performance.
- publishing and managing content across platforms.
- create post
- create instagram media
- Conversational Commerce
- instagram content management.
- create and publish instagram content.
- direct messaging and customer communication.
- get posts from a facebook user's feed.
- social networking
- facebook
- social media
- facebook post management.
- list instagram media
- publish instagram media
- create a new facebook post.
- create threads post
- campaign management and audience targeting.
- performance tracking and insights.
- get threads insights
- Marketing Manager
- advertising
- publishing
- Social Media Manager
- manages day-to-day ad campaign optimization.
- Customer Support
- content publishing
- get instagram performance insights.
- list posts
- get instagram insights
- create a new threads post.
- plans and executes advertising campaigns.
- content management
- customer messaging across messenger and whatsapp.
- create facebook post
- threads content management.
- get facebook feed
- create a threads post.
- list instagram media for an account.
- messaging
- manages content and engagement across meta platforms.
- Ad Operations
- list instagram media.
- creates and publishes visual and text content.
- manage content across facebook, instagram, and threads.
- Content Creator
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
