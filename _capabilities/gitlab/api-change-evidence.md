---
categories:
- evidence
- api-governance
consumed_apis:
- gitlab-rest
description: Mine GitLab merge requests, commits, and project files for evidence of API change across an enterprise org. Surfaces OpenAPI spec edits, route additions, and API-impacting diffs so a technical writer can assemble a current view of API truth before a release — one of the five enterprise systems where evidence of API change already lives.
layout: capability
name: GitLab API Change Evidence
operations:
- description: Search merge requests across the org by label such as api-change or breaking-change
  method: GET
  name: search-merge-requests
  path: /api/v4/merge_requests
- description: List merge requests in a project that touch openapi.yaml or openapi.json
  method: GET
  name: list-spec-touching-mrs
  path: /api/v4/projects/{id}/merge_requests
- description: Get the diff for a specific commit to inspect API-impacting changes
  method: GET
  name: get-commit-diff
  path: /api/v4/projects/{id}/repository/commits/{sha}/diff
- description: Search project files matching openapi.* or swagger.* patterns
  method: GET
  name: search-spec-files
  path: /api/v4/projects/{id}/search
- description: Get the raw OpenAPI spec file from a project at a specific ref
  method: GET
  name: get-raw-spec
  path: /api/v4/projects/{id}/repository/files/{file_path}/raw
- description: List recent commits that mention api or openapi in the message
  method: GET
  name: list-api-commits
  path: /api/v4/projects/{id}/repository/commits
personas:
- Technical Writer
- API Program Manager
provider_name: GitLab
provider_slug: gitlab
search_terms:
- search merge requests by label api-change
- evidence of api change in gitlab
- list merge requests touching openapi yaml
- get commit diff for api change
- search openapi spec files
- get raw openapi from ref
- list api commits
- breaking change label
- api governance from source control
- five places api change evidence lives
- mine gitlab for api diffs
- technical writer release prep
- openapi yaml history
- swagger json changes
- route additions detection
- api program manager evidence
- pre-release api inventory
- merge request label search
- spec file discovery
- gitlab api truth
slug: api-change-evidence
tags:
- GitLab
- API Change
- Evidence
- OpenAPI
- Merge Requests
tools:
- description: Search merge requests across the org by label such as api-change or breaking-change to surface tickets a writer must know about
  hints:
    openWorld: false
    readOnly: true
  name: search-merge-requests
- description: List merge requests in a project that touch openapi.yaml or openapi.json files
  hints:
    openWorld: false
    readOnly: true
  name: list-spec-touching-mrs
- description: Get the diff for a specific commit to inspect API-impacting changes line by line
  hints:
    openWorld: false
    readOnly: true
  name: get-commit-diff
- description: Search project files matching openapi.* or swagger.* patterns to locate API spec source of truth
  hints:
    openWorld: false
    readOnly: true
  name: search-spec-files
- description: Fetch the raw OpenAPI spec file from a project at a specific ref or branch for downstream diffing
  hints:
    openWorld: false
    readOnly: true
  name: get-raw-spec
- description: List recent commits that mention api or openapi in the commit message to triage changes since last release
  hints:
    openWorld: false
    readOnly: true
  name: list-api-commits
---
