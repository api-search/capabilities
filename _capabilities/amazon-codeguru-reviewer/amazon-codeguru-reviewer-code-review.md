---
categories: []
consumed_apis:
- codegurureviewer
description: Unified workflow for DevOps teams to manage repository associations, trigger code reviews, retrieve recommendations, and track code quality metrics using Amazon CodeGuru Reviewer.
layout: capability
name: Amazon CodeGuru Reviewer Automated Code Review
operations: []
personas: []
provider_name: Amazon CodeGuru Reviewer
provider_slug: amazon-codeguru-reviewer
search_terms:
- list repositories associated with codeguru reviewer
- describe repository association
- get details about a code review
- create code review
- unified workflow for devops teams to manage repository associations, trigger code reviews, retrieve
- submit feedback on a code review recommendation
- list recommendations
- devops engineer persona.
- amazon
- get details about a repository association
- list recommendations from a code review
- developer persona.
- Security Engineer
- put recommendation feedback
- devops
- describe code review
- unified workflow for devops teams to manage repository associations, trigger code reviews, retrieve recommendations, and track code quality metrics us
- DevOps Engineer
- list code reviews for a repository
- security engineer persona.
- associate a repository for code review
- developer tools
- associate repository
- code review
- security
- list repository associations
- aws
- Developer
- create a code review
- list code reviews
- machine learning
slug: amazon-codeguru-reviewer-code-review
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon CodeGuru Reviewer Automated Code Review\n  description: Unified workflow for DevOps teams to manage repository associations, trigger code reviews, retrieve recommendations, and track code quality metrics using Amazon CodeGuru Reviewer.\n  tags:\n  - Amazon\n  - AWS\n  - Code Review\n  - Security\n  - DevOps\n  - Machine Learning\n  - Developer Tools\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: codegurureviewer\n    location: ./shared/codegurureviewer.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: codegurureviewer-code-review-api\n    description: Unified REST API for Automated Code Review.\n    resources:\n    - path: /v1/listRepositoryAssociations\n      name: list-repository-associations\n      description: List\
  \ repositories associated with CodeGuru Reviewer\n    - path: /v1/associateRepository\n      name: associate-repository\n      description: Associate a repository for code review\n    - path: /v1/describeRepositoryAssociation\n      name: describe-repository-association\n      description: Get details about a repository association\n    - path: /v1/listCodeReviews\n      name: list-code-reviews\n      description: List code reviews for a repository\n  - type: mcp\n    port: 9090\n    namespace: codegurureviewer-code-review-mcp\n    transport: http\n    description: MCP server for AI-assisted Automated Code Review.\n    tools:\n    - name: list-repository-associations\n      description: List repositories associated with CodeGuru Reviewer\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codegurureviewer.listRepositoryAssociations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: associate-repository\n      description: Associate\
  \ a repository for code review\n      hints:\n        readOnly: false\n        openWorld: true\n      call: codegurureviewer.associateRepository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-repository-association\n      description: Get details about a repository association\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codegurureviewer.describeRepositoryAssociation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-code-reviews\n      description: List code reviews for a repository\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codegurureviewer.listCodeReviews\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-code-review\n      description: Create a code review\n      hints:\n        readOnly: false\n        openWorld: true\n      call: codegurureviewer.createCodeReview\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: describe-code-review\n      description: Get details about a code review\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codegurureviewer.describeCodeReview\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-recommendations\n      description: List recommendations from a code review\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codegurureviewer.listRecommendations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-recommendation-feedback\n      description: Submit feedback on a code review recommendation\n      hints:\n        readOnly: false\n        openWorld: true\n      call: codegurureviewer.putRecommendationFeedback\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-codeguru-reviewer/refs/heads/main/capabilities/amazon-codeguru-reviewer-code-review.yaml
tags:
- Amazon
- AWS
- Code Review
- Security
- DevOps
- Machine Learning
- Developer Tools
tools:
- description: List repositories associated with CodeGuru Reviewer
  hints:
    openWorld: true
    readOnly: true
  name: list-repository-associations
- description: Associate a repository for code review
  hints:
    openWorld: true
    readOnly: false
  name: associate-repository
- description: Get details about a repository association
  hints:
    openWorld: true
    readOnly: true
  name: describe-repository-association
- description: List code reviews for a repository
  hints:
    openWorld: true
    readOnly: true
  name: list-code-reviews
- description: Create a code review
  hints:
    openWorld: true
    readOnly: false
  name: create-code-review
- description: Get details about a code review
  hints:
    openWorld: true
    readOnly: true
  name: describe-code-review
- description: List recommendations from a code review
  hints:
    openWorld: true
    readOnly: true
  name: list-recommendations
- description: Submit feedback on a code review recommendation
  hints:
    openWorld: true
    readOnly: false
  name: put-recommendation-feedback
---
