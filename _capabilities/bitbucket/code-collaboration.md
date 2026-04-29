---
categories:
- ci-cd
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
- get repository
- pull requests
- delete repository
- stop pipeline
- version control
- trigger pipeline
- get pull request details
- create a new git repository
- trigger a new ci/cd pipeline
- continuous integration and deployment pipelines
- get pipeline
- merge a pull request
- pull request workflows and code reviews
- create repository
- get pipeline execution details
- writes code, creates pull requests, and reviews code
- code review
- Developer
- DevOps Engineer
- list pull requests
- managing git repositories, branches, and commits
- list repositories in a workspace
- list ci/cd pipelines
- manages ci/cd pipelines, deployments, and repository settings
- repository hosting
- devops
- repository management, pull requests, code reviews, and ci/cd pipelines
- list pull requests for a repository
- list repositories
- atlassian
- repository management
- code collaboration
- create pullrequest
- stop a running pipeline
- ci/cd pipeline management
- merge pullrequest
- pull request management
- decline pullrequest
- list pullrequests
- ci/cd
- decline a pull request
- get pullrequest
- trigger a pipeline
- create a new pull request
- delete a repository
- list pipelines
- create a pull request
- bitbucket
- get repository details
- create a repository
- git
slug: code-collaboration
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Bitbucket Code Collaboration\"\n  description: \"Workflow capability for code collaboration using Bitbucket - managing repositories, pull requests, code reviews, and CI/CD pipelines. Used by developers and DevOps engineers.\"\n  tags:\n    - Bitbucket\n    - Code Collaboration\n    - CI/CD\n    - DevOps\n    - Pull Requests\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      BITBUCKET_TOKEN: BITBUCKET_TOKEN\n\ncapability:\n  consumes:\n    - import: cloud-rest-api\n      location: ./shared/cloud-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: code-collaboration-api\n      description: \"Unified REST API for Bitbucket code collaboration workflows.\"\n      resources:\n        - path: /v1/repositories\n          name: repositories\n          description: \"Repository management\"\n          operations:\n            - method: GET\n              name:\
  \ list-repositories\n              description: \"List repositories\"\n              call: \"cloud-rest-api.list-repositories\"\n            - method: POST\n              name: create-repository\n              description: \"Create a repository\"\n              call: \"cloud-rest-api.create-repository\"\n            - method: GET\n              name: get-repository\n              description: \"Get repository details\"\n              call: \"cloud-rest-api.get-repository\"\n        - path: /v1/pullrequests\n          name: pullrequests\n          description: \"Pull request management\"\n          operations:\n            - method: GET\n              name: list-pullrequests\n              description: \"List pull requests\"\n              call: \"cloud-rest-api.list-pullrequests\"\n            - method: POST\n              name: create-pullrequest\n              description: \"Create a pull request\"\n              call: \"cloud-rest-api.create-pullrequest\"\n            - method: POST\n\
  \              name: merge-pullrequest\n              description: \"Merge a pull request\"\n              call: \"cloud-rest-api.merge-pullrequest\"\n        - path: /v1/pipelines\n          name: pipelines\n          description: \"CI/CD pipeline management\"\n          operations:\n            - method: GET\n              name: list-pipelines\n              description: \"List pipelines\"\n              call: \"cloud-rest-api.list-pipelines\"\n            - method: POST\n              name: trigger-pipeline\n              description: \"Trigger a pipeline\"\n              call: \"cloud-rest-api.trigger-pipeline\"\n\n    - type: mcp\n      port: 9090\n      namespace: code-collaboration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Bitbucket code collaboration.\"\n      tools:\n        - name: list-repositories\n          description: \"List repositories in a workspace\"\n          hints:\n            readOnly: true\n            openWorld: true\n       \
  \   call: \"cloud-rest-api.list-repositories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-repository\n          description: \"Get repository details\"\n          hints:\n            readOnly: true\n          call: \"cloud-rest-api.get-repository\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-repository\n          description: \"Create a new Git repository\"\n          hints:\n            readOnly: false\n          call: \"cloud-rest-api.create-repository\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-repository\n          description: \"Delete a repository\"\n          hints:\n            destructive: true\n          call: \"cloud-rest-api.delete-repository\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pullrequests\n      \
  \    description: \"List pull requests for a repository\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloud-rest-api.list-pullrequests\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-pullrequest\n          description: \"Create a new pull request\"\n          hints:\n            readOnly: false\n          call: \"cloud-rest-api.create-pullrequest\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pullrequest\n          description: \"Get pull request details\"\n          hints:\n            readOnly: true\n          call: \"cloud-rest-api.get-pullrequest\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: merge-pullrequest\n          description: \"Merge a pull request\"\n          hints:\n            readOnly: false\n          call: \"cloud-rest-api.merge-pullrequest\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: decline-pullrequest\n          description: \"Decline a pull request\"\n          hints:\n            readOnly: false\n          call: \"cloud-rest-api.decline-pullrequest\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pipelines\n          description: \"List CI/CD pipelines\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cloud-rest-api.list-pipelines\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: trigger-pipeline\n          description: \"Trigger a new CI/CD pipeline\"\n          hints:\n            readOnly: false\n          call: \"cloud-rest-api.trigger-pipeline\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pipeline\n          description: \"Get\
  \ pipeline execution details\"\n          hints:\n            readOnly: true\n          call: \"cloud-rest-api.get-pipeline\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-pipeline\n          description: \"Stop a running pipeline\"\n          hints:\n            destructive: true\n          call: \"cloud-rest-api.stop-pipeline\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bitbucket/refs/heads/main/capabilities/code-collaboration.yaml
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
