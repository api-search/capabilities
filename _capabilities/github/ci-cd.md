---
categories:
- ci-cd
consumed_apis:
- github-actions
- github-repos
description: Unified workflow for continuous integration and deployment combining GitHub Actions workflows, runs, jobs, artifacts, and repository management. Used by DevOps engineers for pipeline management, build monitoring, and deployment automation.
layout: capability
name: GitHub CI/CD
operations:
- description: List workflows
  method: GET
  name: listRepositoryWorkflows
  path: /v1/repositories/{owner}/{repo}/workflows
- description: Get a workflow
  method: GET
  name: getWorkflow
  path: /v1/repositories/{owner}/{repo}/workflows/{workflow_id}
- description: Dispatch a workflow
  method: POST
  name: createWorkflowDispatchEvent
  path: /v1/repositories/{owner}/{repo}/workflows/{workflow_id}/dispatches
- description: List workflow runs
  method: GET
  name: listWorkflowRunsForRepository
  path: /v1/repositories/{owner}/{repo}/runs
- description: Get a workflow run
  method: GET
  name: getWorkflowRun
  path: /v1/repositories/{owner}/{repo}/runs/{run_id}
- description: Cancel a workflow run
  method: POST
  name: cancelWorkflowRun
  path: /v1/repositories/{owner}/{repo}/runs/{run_id}/cancel
- description: List jobs
  method: GET
  name: listJobsForWorkflowRun
  path: /v1/repositories/{owner}/{repo}/runs/{run_id}/jobs
- description: List artifacts
  method: GET
  name: listArtifactsForRepository
  path: /v1/repositories/{owner}/{repo}/artifacts
- description: List secrets
  method: GET
  name: listRepositorySecrets
  path: /v1/repositories/{owner}/{repo}/secrets
- description: List deployments
  method: GET
  name: listDeployments
  path: /v1/repositories/{owner}/{repo}/deployments
- description: List environments
  method: GET
  name: listEnvironments
  path: /v1/repositories/{owner}/{repo}/environments
personas: []
provider_name: GitHub
provider_slug: github
search_terms:
- trigger a workflow dispatch event
- list self-hosted runners
- devops
- list workflows
- create a release
- list environments
- listRepositorySecrets
- listJobsForWorkflowRun
- list repository secrets
- workflow run management
- t1
- cancel a workflow run
- get job
- list runs
- environment management
- github
- listArtifactsForRepository
- create or update secret
- individual run operations
- download job logs
- create or update a secret
- re-run failed jobs
- cancel run
- listRepositoryWorkflows
- create release
- get run
- enable workflow
- source control
- actions
- rerun failed jobs
- deployments
- re-run a workflow
- platform
- get a job
- list runners
- trigger workflow runs
- software development
- listDeployments
- list github actions caches
- workflows
- getWorkflow
- list repository variables
- list jobs
- list releases
- get repository
- listWorkflowRunsForRepository
- code
- deployment management
- list artifacts
- download artifact
- get a repository
- dispatch a workflow
- listEnvironments
- secret management
- list caches
- createWorkflowDispatchEvent
- list repository workflows
- disable workflow
- cancelWorkflowRun
- disable a workflow
- list variables
- artifact management
- individual workflow operations
- list secrets
- list jobs for a workflow run
- getWorkflowRun
- ci/cd
- workflow listing and dispatch
- enable a workflow
- rerun workflow
- workflow run jobs
- list deployments
- get a workflow
- download an artifact
- get a workflow run
- list workflow runs
- get workflow
- pipelines
- dispatch workflow
slug: ci-cd
tags:
- GitHub
- CI/CD
- Actions
- Workflows
- DevOps
- Deployments
tools:
- description: List repository workflows
  hints:
    readOnly: true
  name: list-workflows
- description: Get a workflow
  hints:
    readOnly: true
  name: get-workflow
- description: Trigger a workflow dispatch event
  hints: {}
  name: dispatch-workflow
- description: Enable a workflow
  hints: {}
  name: enable-workflow
- description: Disable a workflow
  hints: {}
  name: disable-workflow
- description: List workflow runs
  hints:
    readOnly: true
  name: list-runs
- description: Get a workflow run
  hints:
    readOnly: true
  name: get-run
- description: Cancel a workflow run
  hints: {}
  name: cancel-run
- description: Re-run a workflow
  hints: {}
  name: rerun-workflow
- description: Re-run failed jobs
  hints: {}
  name: rerun-failed-jobs
- description: List jobs for a workflow run
  hints:
    readOnly: true
  name: list-jobs
- description: Get a job
  hints:
    readOnly: true
  name: get-job
- description: Download job logs
  hints:
    readOnly: true
  name: download-job-logs
- description: List artifacts
  hints:
    readOnly: true
  name: list-artifacts
- description: Download an artifact
  hints:
    readOnly: true
  name: download-artifact
- description: List repository secrets
  hints:
    readOnly: true
  name: list-secrets
- description: Create or update a secret
  hints:
    idempotent: true
  name: create-or-update-secret
- description: List repository variables
  hints:
    readOnly: true
  name: list-variables
- description: List self-hosted runners
  hints:
    readOnly: true
  name: list-runners
- description: List GitHub Actions caches
  hints:
    readOnly: true
  name: list-caches
- description: Get a repository
  hints:
    readOnly: true
  name: get-repository
- description: List releases
  hints:
    readOnly: true
  name: list-releases
- description: Create a release
  hints: {}
  name: create-release
---
