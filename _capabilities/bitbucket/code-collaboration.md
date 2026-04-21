---
consumed_apis:
- cloud-rest-api
description: Workflow capability for code collaboration using Bitbucket - managing repositories, pull requests, code reviews, and CI/CD pipelines. Used by developers and DevOps engineers.
layout: capability
name: Bitbucket Code Collaboration
operations:
- description: List repositories
  method: GET
  name: list-repositories
  path: /v1/repositories
- description: Create a repository
  method: POST
  name: create-repository
  path: /v1/repositories
- description: Get repository details
  method: GET
  name: get-repository
  path: /v1/repositories
- description: List pull requests
  method: GET
  name: list-pullrequests
  path: /v1/pullrequests
- description: Create a pull request
  method: POST
  name: create-pullrequest
  path: /v1/pullrequests
- description: Merge a pull request
  method: POST
  name: merge-pullrequest
  path: /v1/pullrequests
- description: List pipelines
  method: GET
  name: list-pipelines
  path: /v1/pipelines
- description: Trigger a pipeline
  method: POST
  name: trigger-pipeline
  path: /v1/pipelines
personas: []
provider_name: Bitbucket
provider_slug: bitbucket
search_terms:
- create a new git repository
- ci/cd
- get pull request details
- get repository
- list repositories in a workspace
- managing git repositories, branches, and commits
- trigger pipeline
- pull requests
- merge pullrequest
- get pipeline
- continuous integration and deployment pipelines
- list repositories
- create a new pull request
- code collaboration
- DevOps Engineer
- trigger a pipeline
- create a pull request
- repository hosting
- delete a repository
- pull request management
- merge a pull request
- manages ci/cd pipelines, deployments, and repository settings
- version control
- code review
- create a repository
- get pipeline execution details
- create pullrequest
- pull request workflows and code reviews
- repository management, pull requests, code reviews, and ci/cd pipelines
- git
- list pipelines
- decline pullrequest
- create repository
- writes code, creates pull requests, and reviews code
- devops
- repository management
- trigger a new ci/cd pipeline
- list pull requests for a repository
- get pullrequest
- atlassian
- stop pipeline
- list pull requests
- Developer
- ci/cd pipeline management
- list ci/cd pipelines
- get repository details
- list pullrequests
- decline a pull request
- stop a running pipeline
- delete repository
- bitbucket
slug: code-collaboration
tags:
- Bitbucket
- Code Collaboration
- CI/CD
- DevOps
- Pull Requests
tools:
- description: List repositories in a workspace
  hints:
    openWorld: true
    readOnly: true
  name: list-repositories
- description: Get repository details
  hints:
    readOnly: true
  name: get-repository
- description: Create a new Git repository
  hints:
    readOnly: false
  name: create-repository
- description: Delete a repository
  hints:
    destructive: true
  name: delete-repository
- description: List pull requests for a repository
  hints:
    openWorld: true
    readOnly: true
  name: list-pullrequests
- description: Create a new pull request
  hints:
    readOnly: false
  name: create-pullrequest
- description: Get pull request details
  hints:
    readOnly: true
  name: get-pullrequest
- description: Merge a pull request
  hints:
    readOnly: false
  name: merge-pullrequest
- description: Decline a pull request
  hints:
    readOnly: false
  name: decline-pullrequest
- description: List CI/CD pipelines
  hints:
    openWorld: true
    readOnly: true
  name: list-pipelines
- description: Trigger a new CI/CD pipeline
  hints:
    readOnly: false
  name: trigger-pipeline
- description: Get pipeline execution details
  hints:
    readOnly: true
  name: get-pipeline
- description: Stop a running pipeline
  hints:
    destructive: true
  name: stop-pipeline
---
