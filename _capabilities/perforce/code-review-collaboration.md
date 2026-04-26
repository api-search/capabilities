---
consumed_apis:
- helix-swarm
description: Unified workflow for code review, commenting, and project management using Helix Swarm. Designed for development teams managing code review workflows integrated with Helix Core version control.
layout: capability
name: Perforce Code Review and Collaboration
operations:
- description: List code reviews
  method: GET
  name: list-reviews
  path: /v1/reviews
- description: Create a new code review
  method: POST
  name: create-review
  path: /v1/reviews
- description: Get review details
  method: GET
  name: get-review
  path: /v1/reviews/{id}
- description: List comments
  method: GET
  name: list-comments
  path: /v1/comments
- description: List projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: List activity entries
  method: GET
  name: list-activity
  path: /v1/activity
personas: []
provider_name: Perforce
provider_slug: perforce
search_terms:
- code review
- transition review state
- get version
- collaboration
- get details of a specific code review
- transition a review to a new state (approve, reject, etc.)
- list code reviews
- activity stream
- list activity entries
- list comments
- get project
- list swarm projects
- review comments
- get details of a specific swarm project
- code reviews
- list reviews
- list comments on reviews and changelists
- get review
- create a new code review
- create comment
- list projects
- devops
- list activity
- get review details
- create a new code review from a changelist
- list code reviews in helix swarm
- delete a swarm project
- review details
- perforce
- update review
- get swarm server version information
- list activity stream entries
- swarm projects
- create review
- add a comment to a review or changelist
- update a review description or author
- delete project
slug: code-review-collaboration
tags:
- Perforce
- Code Review
- Collaboration
- DevOps
tools:
- description: List code reviews in Helix Swarm
  hints:
    openWorld: true
    readOnly: true
  name: list-reviews
- description: Get details of a specific code review
  hints:
    readOnly: true
  name: get-review
- description: Create a new code review from a changelist
  hints:
    readOnly: false
  name: create-review
- description: Update a review description or author
  hints:
    readOnly: false
  name: update-review
- description: Transition a review to a new state (approve, reject, etc.)
  hints:
    readOnly: false
  name: transition-review-state
- description: List comments on reviews and changelists
  hints:
    readOnly: true
  name: list-comments
- description: Add a comment to a review or changelist
  hints:
    readOnly: false
  name: create-comment
- description: List Swarm projects
  hints:
    readOnly: true
  name: list-projects
- description: Get details of a specific Swarm project
  hints:
    readOnly: true
  name: get-project
- description: Delete a Swarm project
  hints:
    destructive: true
  name: delete-project
- description: List activity stream entries
  hints:
    readOnly: true
  name: list-activity
- description: Get Swarm server version information
  hints:
    readOnly: true
  name: get-version
---
