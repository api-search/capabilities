---
categories:
- ci-cd
consumed_apis: []
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
- devops
- DevOps Engineer
- trigger a new ci/cd pipeline
- atlassian
- trigger pipeline
- delete repository
- list pull requests for a repository
- manages ci/cd pipelines, deployments, and repository settings
- ci/cd
- decline a pull request
- merge pullrequest
- get pipeline
- decline pullrequest
- git
- repository hosting
- get pull request details
- bitbucket
- stop a running pipeline
- get pipeline execution details
- get repository
- list ci/cd pipelines
- pull request workflows and code reviews
- list pull requests
- repository management, pull requests, code reviews, and ci/cd pipelines
- writes code, creates pull requests, and reviews code
- code collaboration
- create a repository
- get pullrequest
- create a pull request
- list repositories in a workspace
- managing git repositories, branches, and commits
- delete a repository
- list pipelines
- repository management
- continuous integration and deployment pipelines
- create repository
- pull request management
- ci/cd pipeline management
- list pullrequests
- code review
- Developer
- version control
- stop pipeline
- merge a pull request
- trigger a pipeline
- create pullrequest
- get repository details
- create a new pull request
- pull requests
- list repositories
- create a new git repository
slug: code-collaboration
source_filename: code-collaboration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bitbucket Code Collaboration\n  description: Workflow capability for code collaboration using Bitbucket - managing repositories, pull requests, code reviews,\n    and CI/CD pipelines. Used by developers and DevOps engineers.\n  tags:\n  - Bitbucket\n  - Code Collaboration\n  - CI/CD\n  - DevOps\n  - Pull Requests\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BITBUCKET_TOKEN: BITBUCKET_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: cloud-rest-api\n    baseUri: https://api.bitbucket.org/2.0\n    description: Bitbucket Cloud REST API 2.0 for managing Git repositories and related resources.\n    authentication:\n      type: bearer\n      token: '{{BITBUCKET_TOKEN}}'\n    resources:\n    - name: repositories\n      path: /repositories\n      description: Repository management\n      operations:\n      - name: list-repositories\n        method: GET\n        description: List repositories\
  \ for a workspace\n        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n          description: The workspace slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-repository\n        method: GET\n        description: Get a repository\n        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n        - name: repo_slug\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-repository\n        method: POST\n        description: Create a new repository\n        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n        - name: repo_slug\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            scm: '{{tools.scm}}'\n            is_private: '{{tools.is_private}}'\n      - name: delete-repository\n        method: DELETE\n        description: Delete a repository\n        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n        - name: repo_slug\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pullrequests\n      path: /repositories/{workspace}/{repo_slug}/pullrequests\n      description: Pull request operations\n      operations:\n      - name: list-pullrequests\n        method: GET\n        description:\
  \ List pull requests\n        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n        - name: repo_slug\n          in: path\n          type: string\n          required: true\n        - name: state\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-pullrequest\n        method: POST\n        description: Create a pull request\n        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n        - name: repo_slug\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-pullrequest\n        method: GET\n        description: Get a pull request\n\
  \        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n        - name: repo_slug\n          in: path\n          type: string\n          required: true\n        - name: pull_request_id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: merge-pullrequest\n        method: POST\n        description: Merge a pull request\n        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n        - name: repo_slug\n          in: path\n          type: string\n          required: true\n        - name: pull_request_id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: decline-pullrequest\n        method: POST\n        description: Decline a pull request\n        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n        - name: repo_slug\n          in: path\n          type: string\n          required: true\n        - name: pull_request_id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines\n      path: /repositories/{workspace}/{repo_slug}/pipelines\n      description: Pipeline operations\n      operations:\n      - name: list-pipelines\n        method: GET\n        description: List pipelines\n        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n        - name: repo_slug\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: trigger-pipeline\n        method: POST\n        description: Trigger a pipeline\n        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n        - name: repo_slug\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-pipeline\n        method: GET\n        description: Get a pipeline\n        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n        - name: repo_slug\n          in: path\n          type: string\n          required: true\n        - name: pipeline_uuid\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-pipeline\n        method: POST\n        description: Stop a running pipeline\n        inputParameters:\n        - name: workspace\n          in: path\n          type: string\n          required: true\n        - name: repo_slug\n          in: path\n          type: string\n          required: true\n        - name: pipeline_uuid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: code-collaboration-api\n    description: Unified REST API for Bitbucket code collaboration workflows.\n    resources:\n    - path: /v1/repositories\n      name: repositories\n      description: Repository management\n      operations:\n      - method: GET\n        name: list-repositories\n \
  \       description: List repositories\n        call: cloud-rest-api.list-repositories\n      - method: POST\n        name: create-repository\n        description: Create a repository\n        call: cloud-rest-api.create-repository\n      - method: GET\n        name: get-repository\n        description: Get repository details\n        call: cloud-rest-api.get-repository\n    - path: /v1/pullrequests\n      name: pullrequests\n      description: Pull request management\n      operations:\n      - method: GET\n        name: list-pullrequests\n        description: List pull requests\n        call: cloud-rest-api.list-pullrequests\n      - method: POST\n        name: create-pullrequest\n        description: Create a pull request\n        call: cloud-rest-api.create-pullrequest\n      - method: POST\n        name: merge-pullrequest\n        description: Merge a pull request\n        call: cloud-rest-api.merge-pullrequest\n    - path: /v1/pipelines\n      name: pipelines\n      description:\
  \ CI/CD pipeline management\n      operations:\n      - method: GET\n        name: list-pipelines\n        description: List pipelines\n        call: cloud-rest-api.list-pipelines\n      - method: POST\n        name: trigger-pipeline\n        description: Trigger a pipeline\n        call: cloud-rest-api.trigger-pipeline\n  - type: mcp\n    port: 9090\n    namespace: code-collaboration-mcp\n    transport: http\n    description: MCP server for AI-assisted Bitbucket code collaboration.\n    tools:\n    - name: list-repositories\n      description: List repositories in a workspace\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloud-rest-api.list-repositories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-repository\n      description: Get repository details\n      hints:\n        readOnly: true\n      call: cloud-rest-api.get-repository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-repository\n\
  \      description: Create a new Git repository\n      hints:\n        readOnly: false\n      call: cloud-rest-api.create-repository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-repository\n      description: Delete a repository\n      hints:\n        destructive: true\n      call: cloud-rest-api.delete-repository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pullrequests\n      description: List pull requests for a repository\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloud-rest-api.list-pullrequests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-pullrequest\n      description: Create a new pull request\n      hints:\n        readOnly: false\n      call: cloud-rest-api.create-pullrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pullrequest\n      description: Get pull request details\n \
  \     hints:\n        readOnly: true\n      call: cloud-rest-api.get-pullrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: merge-pullrequest\n      description: Merge a pull request\n      hints:\n        readOnly: false\n      call: cloud-rest-api.merge-pullrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: decline-pullrequest\n      description: Decline a pull request\n      hints:\n        readOnly: false\n      call: cloud-rest-api.decline-pullrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pipelines\n      description: List CI/CD pipelines\n      hints:\n        readOnly: true\n        openWorld: true\n      call: cloud-rest-api.list-pipelines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trigger-pipeline\n      description: Trigger a new CI/CD pipeline\n      hints:\n        readOnly: false\n      call: cloud-rest-api.trigger-pipeline\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pipeline\n      description: Get pipeline execution details\n      hints:\n        readOnly: true\n      call: cloud-rest-api.get-pipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-pipeline\n      description: Stop a running pipeline\n      hints:\n        destructive: true\n      call: cloud-rest-api.stop-pipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
