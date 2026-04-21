---
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
- get a specific blog post by id
- create a new blog post
- get a blog author by id
- list all blog authors
- clone blog post
- get blog post
- update a blog post
- create blog author
- event type definitions
- retrieve analytics events
- crm
- cms
- analytics events
- push a draft blog post to live
- list available analytics event types
- get blog author
- get revision history for a blog post
- marketing automation
- archive a blog post
- get a blog post
- blog author management
- clone an existing blog post
- operations
- list blog authors
- customer service
- archive blog post
- get blog post revisions
- create a new blog author
- list all blog posts in hubspot
- schedule blog post
- blog
- get analytics events
- create blog post
- push blog post live
- sales
- commerce
- list blog posts
- update an existing blog post
- blog post management
- list available event types
- individual blog post
- retrieve analytics event data for crm objects
- email marketing
- content
- create a blog post
- update blog post
- hubspot
- list all blog posts
- analytics
- list events
- marketing
- schedule a blog post for publication
- list event types
- get event types
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
