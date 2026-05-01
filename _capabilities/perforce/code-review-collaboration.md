---
categories:
- collaboration
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
- activity stream
- transition a review to a new state (approve, reject, etc.)
- code review
- get project
- review comments
- swarm projects
- create a new code review from a changelist
- list comments
- transition review state
- list activity stream entries
- create comment
- list activity entries
- get swarm server version information
- code reviews
- delete project
- perforce
- get details of a specific swarm project
- get version
- list projects
- list code reviews in helix swarm
- devops
- update review
- add a comment to a review or changelist
- collaboration
- delete a swarm project
- list code reviews
- create a new code review
- list comments on reviews and changelists
- create review
- list reviews
- update a review description or author
- list activity
- list swarm projects
- get details of a specific code review
- review details
- get review
- get review details
slug: code-review-collaboration
source_filename: code-review-collaboration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Perforce Code Review and Collaboration\"\n  description: \"Unified workflow for code review, commenting, and project management using Helix Swarm. Designed for development teams managing code review workflows integrated with Helix Core version control.\"\n  tags:\n    - Perforce\n    - Code Review\n    - Collaboration\n    - DevOps\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SWARM_USERNAME: SWARM_USERNAME\n      SWARM_PASSWORD: SWARM_PASSWORD\n\ncapability:\n  consumes:\n    - import: helix-swarm\n      location: ./shared/helix-swarm.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: code-review-api\n      description: \"Unified REST API for Perforce code review and collaboration.\"\n      resources:\n        - path: /v1/reviews\n          name: reviews\n          description: \"Code reviews\"\n          operations:\n            - method: GET\n   \
  \           name: list-reviews\n              description: \"List code reviews\"\n              call: \"helix-swarm.list-reviews\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-review\n              description: \"Create a new code review\"\n              call: \"helix-swarm.create-review\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reviews/{id}\n          name: review-details\n          description: \"Review details\"\n          operations:\n            - method: GET\n              name: get-review\n              description: \"Get review details\"\n              call: \"helix-swarm.get-review\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/comments\n          name: comments\n\
  \          description: \"Review comments\"\n          operations:\n            - method: GET\n              name: list-comments\n              description: \"List comments\"\n              call: \"helix-swarm.list-comments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects\n          name: projects\n          description: \"Swarm projects\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List projects\"\n              call: \"helix-swarm.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/activity\n          name: activity\n          description: \"Activity stream\"\n          operations:\n            - method: GET\n              name: list-activity\n              description: \"List activity entries\"\n              call: \"helix-swarm.list-activity\"\n \
  \             outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: code-review-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Perforce code review and collaboration.\"\n      tools:\n        - name: list-reviews\n          description: \"List code reviews in Helix Swarm\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"helix-swarm.list-reviews\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-review\n          description: \"Get details of a specific code review\"\n          hints:\n            readOnly: true\n          call: \"helix-swarm.get-review\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-review\n          description: \"Create a new code review from\
  \ a changelist\"\n          hints:\n            readOnly: false\n          call: \"helix-swarm.create-review\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-review\n          description: \"Update a review description or author\"\n          hints:\n            readOnly: false\n          call: \"helix-swarm.update-review\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: transition-review-state\n          description: \"Transition a review to a new state (approve, reject, etc.)\"\n          hints:\n            readOnly: false\n          call: \"helix-swarm.transition-review-state\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-comments\n          description: \"List comments on reviews and changelists\"\n      \
  \    hints:\n            readOnly: true\n          call: \"helix-swarm.list-comments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-comment\n          description: \"Add a comment to a review or changelist\"\n          hints:\n            readOnly: false\n          call: \"helix-swarm.create-comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-projects\n          description: \"List Swarm projects\"\n          hints:\n            readOnly: true\n          call: \"helix-swarm.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-project\n          description: \"Get details of a specific Swarm project\"\n          hints:\n            readOnly: true\n          call: \"helix-swarm.get-project\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: delete-project\n          description: \"Delete a Swarm project\"\n          hints:\n            destructive: true\n          call: \"helix-swarm.delete-project\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-activity\n          description: \"List activity stream entries\"\n          hints:\n            readOnly: true\n          call: \"helix-swarm.list-activity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-version\n          description: \"Get Swarm server version information\"\n          hints:\n            readOnly: true\n          call: \"helix-swarm.get-version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/perforce/refs/heads/main/capabilities/code-review-collaboration.yaml
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
