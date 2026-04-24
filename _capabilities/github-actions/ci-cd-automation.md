---
consumed_apis:
- actions
description: Unified capability for GitHub Actions CI/CD automation combining workflow management, run monitoring, artifact handling, secrets/variables management, and runner administration. Used by DevOps engineers, platform teams, and release managers.
layout: capability
name: GitHub Actions CI/CD Automation
operations:
- description: List repository workflows
  method: GET
  name: list-workflows
  path: /v1/workflows
- description: Get a specific workflow
  method: GET
  name: get-workflow
  path: /v1/workflows/{workflow_id}
- description: Trigger a workflow dispatch
  method: POST
  name: dispatch
  path: /v1/workflows/{workflow_id}/dispatch
- description: List workflow runs
  method: GET
  name: list-runs
  path: /v1/runs
- description: Get a workflow run
  method: GET
  name: get-run
  path: /v1/runs/{run_id}
- description: Delete a workflow run
  method: DELETE
  name: delete-run
  path: /v1/runs/{run_id}
- description: Cancel a workflow run
  method: POST
  name: cancel
  path: /v1/runs/{run_id}/cancel
- description: Re-run a workflow
  method: POST
  name: rerun
  path: /v1/runs/{run_id}/rerun
- description: List jobs for a workflow run
  method: GET
  name: list-jobs
  path: /v1/runs/{run_id}/jobs
- description: List artifacts
  method: GET
  name: list-artifacts
  path: /v1/artifacts
- description: Get an artifact
  method: GET
  name: get-artifact
  path: /v1/artifacts/{artifact_id}
- description: Delete an artifact
  method: DELETE
  name: delete-artifact
  path: /v1/artifacts/{artifact_id}
- description: List repository secrets
  method: GET
  name: list-secrets
  path: /v1/secrets
- description: List repository variables
  method: GET
  name: list-variables
  path: /v1/variables
- description: List caches
  method: GET
  name: list-caches
  path: /v1/caches
- description: List self-hosted runners
  method: GET
  name: list-runners
  path: /v1/runners
personas: []
provider_name: GitHub Actions
provider_slug: github-actions
search_terms:
- delete an artifact
- delete cache
- workflow runs
- single workflow run
- cancel
- list workflow runs for a repository
- get run
- delete secret
- workflow artifacts
- delete a workflow run
- devops
- list workflows
- get an artifact
- create or update secret
- delete a specific cache entry
- single workflow
- list repository secrets (names only, not values)
- create a repository variable
- cancel a workflow run
- github
- rerun
- list jobs for a workflow run
- get a specific workflow by id or filename
- list actions caches for a repository
- self-hosted runners
- actions
- jobs for a workflow run
- list artifacts
- get details of a specific workflow run
- disable workflow
- ci/cd
- delete runner
- list runs
- re-run only the failed jobs from a workflow run
- list repository workflows
- enable workflow
- get a workflow run
- list repository secrets
- delete a repository variable
- re-run a workflow
- get a specific job from a workflow run
- trigger a workflow
- rerun workflow
- get a specific self-hosted runner
- rerun failed jobs
- delete a repository secret
- repository variables
- list repository variables
- get job
- trigger a workflow dispatch event
- dispatch
- get details of a specific artifact
- list jobs
- list caches
- enable a workflow
- single artifact
- remove a self-hosted runner from a repository
- list variables
- list runners
- delete a workflow artifact
- get workflow
- delete variable
- create variable
- repository secrets
- list workflow runs
- delete run
- cancel run
- disable a workflow
- trigger workflow
- list secrets
- action caches
- get runner
- automation
- list self-hosted runners for a repository
- get artifact
- get a specific workflow
- trigger a workflow dispatch
- delete artifact
- list workflow artifacts for a repository
- create or update a repository secret
- list self-hosted runners
- workflows
- cancel a running workflow
slug: ci-cd-automation
tags:
- GitHub
- Actions
- CI/CD
- Automation
- DevOps
tools:
- description: List repository workflows
  hints:
    openWorld: true
    readOnly: true
  name: list-workflows
- description: Get a specific workflow by ID or filename
  hints:
    readOnly: true
  name: get-workflow
- description: Trigger a workflow dispatch event
  hints:
    readOnly: false
  name: trigger-workflow
- description: Disable a workflow
  hints:
    readOnly: false
  name: disable-workflow
- description: Enable a workflow
  hints:
    readOnly: false
  name: enable-workflow
- description: List workflow runs for a repository
  hints:
    openWorld: true
    readOnly: true
  name: list-runs
- description: Get details of a specific workflow run
  hints:
    readOnly: true
  name: get-run
- description: Cancel a running workflow
  hints:
    destructive: true
    readOnly: false
  name: cancel-run
- description: Re-run a workflow
  hints:
    readOnly: false
  name: rerun-workflow
- description: Re-run only the failed jobs from a workflow run
  hints:
    readOnly: false
  name: rerun-failed-jobs
- description: Delete a workflow run
  hints:
    destructive: true
    readOnly: false
  name: delete-run
- description: List jobs for a workflow run
  hints:
    readOnly: true
  name: list-jobs
- description: Get a specific job from a workflow run
  hints:
    readOnly: true
  name: get-job
- description: List workflow artifacts for a repository
  hints:
    openWorld: true
    readOnly: true
  name: list-artifacts
- description: Get details of a specific artifact
  hints:
    readOnly: true
  name: get-artifact
- description: Delete a workflow artifact
  hints:
    destructive: true
    readOnly: false
  name: delete-artifact
- description: List repository secrets (names only, not values)
  hints:
    readOnly: true
  name: list-secrets
- description: Create or update a repository secret
  hints:
    idempotent: true
    readOnly: false
  name: create-or-update-secret
- description: Delete a repository secret
  hints:
    destructive: true
    readOnly: false
  name: delete-secret
- description: List repository variables
  hints:
    readOnly: true
  name: list-variables
- description: Create a repository variable
  hints:
    readOnly: false
  name: create-variable
- description: Delete a repository variable
  hints:
    destructive: true
    readOnly: false
  name: delete-variable
- description: List Actions caches for a repository
  hints:
    readOnly: true
  name: list-caches
- description: Delete a specific cache entry
  hints:
    destructive: true
    readOnly: false
  name: delete-cache
- description: List self-hosted runners for a repository
  hints:
    readOnly: true
  name: list-runners
- description: Get a specific self-hosted runner
  hints:
    readOnly: true
  name: get-runner
- description: Remove a self-hosted runner from a repository
  hints:
    destructive: true
    readOnly: false
  name: delete-runner
---
