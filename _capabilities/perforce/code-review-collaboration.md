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
- list code reviews
- transition review state
- create comment
- list comments
- add a comment to a review or changelist
- review details
- code reviews
- delete project
- get review
- create review
- get details of a specific swarm project
- get version
- get details of a specific code review
- collaboration
- get review details
- update review
- list reviews
- list swarm projects
- delete a swarm project
- list activity stream entries
- devops
- get project
- create a new code review from a changelist
- code review
- create a new code review
- list comments on reviews and changelists
- list activity entries
- get swarm server version information
- update a review description or author
- list code reviews in helix swarm
- perforce
- list activity
- review comments
- swarm projects
- list projects
- activity stream
- transition a review to a new state (approve, reject, etc.)
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
