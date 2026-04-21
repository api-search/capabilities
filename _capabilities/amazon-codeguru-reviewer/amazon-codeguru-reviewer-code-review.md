---
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
- devops
- put recommendation feedback
- unified workflow for devops teams to manage repository associations, trigger code reviews, retrieve recommendations, and track code quality metrics us
- devops engineer persona.
- create a code review
- associate a repository for code review
- list recommendations
- unified workflow for devops teams to manage repository associations, trigger code reviews, retrieve
- describe repository association
- submit feedback on a code review recommendation
- Developer
- machine learning
- DevOps Engineer
- list code reviews for a repository
- list repository associations
- list repositories associated with codeguru reviewer
- associate repository
- list code reviews
- get details about a repository association
- security
- security engineer persona.
- Security Engineer
- amazon
- create code review
- aws
- code review
- list recommendations from a code review
- get details about a code review
- developer tools
- describe code review
- developer persona.
slug: amazon-codeguru-reviewer-code-review
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
