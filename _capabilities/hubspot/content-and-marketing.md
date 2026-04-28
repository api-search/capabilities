---
categories:
- content-management
consumed_apis:
- blog-posts
- blog-authors
- analytics-events
- cms-pages
- domains
- marketing-email
description: Unified workflow for marketing managers to manage blog content, authors, landing pages, site pages, domains, analytics events, and transactional email. Combines CMS and marketing APIs into a single content operations interface.
layout: capability
name: HubSpot Content And Marketing
operations:
- description: List all blog posts
  method: GET
  name: list-blog-posts
  path: /v1/blog-posts
- description: Create a blog post
  method: POST
  name: create-blog-post
  path: /v1/blog-posts
- description: Get a blog post
  method: GET
  name: get-blog-post
  path: /v1/blog-posts/{objectId}
- description: Update a blog post
  method: PATCH
  name: update-blog-post
  path: /v1/blog-posts/{objectId}
- description: Archive a blog post
  method: DELETE
  name: archive-blog-post
  path: /v1/blog-posts/{objectId}
- description: List all blog authors
  method: GET
  name: list-blog-authors
  path: /v1/blog-authors
- description: Retrieve analytics events
  method: GET
  name: list-events
  path: /v1/events
- description: List available event types
  method: GET
  name: list-event-types
  path: /v1/event-types
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- create a new blog author
- list all blog posts
- list blog authors
- get a specific blog post by id
- blog author management
- create a new blog post
- blog post management
- get blog post
- event type definitions
- clone blog post
- list available event types
- clone an existing blog post
- schedule blog post
- push blog post live
- archive a blog post
- list all blog authors
- create blog author
- operations
- list available analytics event types
- update an existing blog post
- hubspot
- get event types
- schedule a blog post for publication
- crm
- blog
- list event types
- individual blog post
- push a draft blog post to live
- get blog post revisions
- marketing automation
- content
- marketing
- list all blog posts in hubspot
- analytics events
- create blog post
- retrieve analytics events
- get a blog author by id
- list blog posts
- update blog post
- sales
- list events
- cms
- get a blog post
- get analytics events
- customer service
- analytics
- retrieve analytics event data for crm objects
- commerce
- create a blog post
- email marketing
- update a blog post
- archive blog post
- get revision history for a blog post
- get blog author
slug: content-and-marketing
tags:
- HubSpot
- Marketing
- Content
- CMS
- Blog
- Analytics
tools:
- description: List all blog posts in HubSpot
  hints:
    idempotent: true
    readOnly: true
  name: list-blog-posts
- description: Get a specific blog post by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-blog-post
- description: Create a new blog post
  hints:
    readOnly: false
  name: create-blog-post
- description: Update an existing blog post
  hints:
    idempotent: true
    readOnly: false
  name: update-blog-post
- description: Schedule a blog post for publication
  hints:
    readOnly: false
  name: schedule-blog-post
- description: Clone an existing blog post
  hints:
    readOnly: false
  name: clone-blog-post
- description: Push a draft blog post to live
  hints:
    readOnly: false
  name: push-blog-post-live
- description: List all blog authors
  hints:
    idempotent: true
    readOnly: true
  name: list-blog-authors
- description: Get a blog author by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-blog-author
- description: Create a new blog author
  hints:
    readOnly: false
  name: create-blog-author
- description: Retrieve analytics event data for CRM objects
  hints:
    idempotent: true
    readOnly: true
  name: get-analytics-events
- description: List available analytics event types
  hints:
    idempotent: true
    readOnly: true
  name: get-event-types
- description: Archive a blog post
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: archive-blog-post
- description: Get revision history for a blog post
  hints:
    idempotent: true
    readOnly: true
  name: get-blog-post-revisions
---
