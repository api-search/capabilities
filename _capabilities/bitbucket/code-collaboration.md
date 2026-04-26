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
- code review
- trigger pipeline
- ci/cd pipeline management
- list pipelines
- repository management
- merge pullrequest
- repository management, pull requests, code reviews, and ci/cd pipelines
- create a new git repository
- list repositories
- create a pull request
- atlassian
- git
- bitbucket
- list ci/cd pipelines
- get pullrequest
- trigger a new ci/cd pipeline
- get pull request details
- code collaboration
- continuous integration and deployment pipelines
- create pullrequest
- repository hosting
- manages ci/cd pipelines, deployments, and repository settings
- merge a pull request
- pull requests
- managing git repositories, branches, and commits
- stop a running pipeline
- get repository
- get repository details
- list pullrequests
- pull request management
- stop pipeline
- create a repository
- version control
- decline a pull request
- devops
- pull request workflows and code reviews
- list pull requests
- list pull requests for a repository
- trigger a pipeline
- list repositories in a workspace
- create a new pull request
- get pipeline
- delete a repository
- decline pullrequest
- Developer
- DevOps Engineer
- get pipeline execution details
- create repository
- delete repository
- writes code, creates pull requests, and reviews code
- ci/cd
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
