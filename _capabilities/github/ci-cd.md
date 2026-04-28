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
- getWorkflowRun
- createWorkflowDispatchEvent
- list caches
- get a workflow
- cancelWorkflowRun
- listArtifactsForRepository
- get job
- devops
- list jobs for a workflow run
- list workflow runs
- list secrets
- download artifact
- source control
- list artifacts
- create or update a secret
- workflow listing and dispatch
- t1
- create or update secret
- cancel run
- list variables
- getWorkflow
- rerun workflow
- list deployments
- get a repository
- create release
- list environments
- rerun failed jobs
- workflow run jobs
- listDeployments
- disable a workflow
- trigger a workflow dispatch event
- listWorkflowRunsForRepository
- secret management
- get workflow
- dispatch a workflow
- list releases
- workflow run management
- list repository variables
- re-run a workflow
- trigger workflow runs
- create a release
- download job logs
- list repository workflows
- get repository
- list github actions caches
- deployment management
- listRepositoryWorkflows
- list runners
- disable workflow
- list jobs
- list self-hosted runners
- deployments
- code
- platform
- listEnvironments
- listJobsForWorkflowRun
- software development
- workflows
- list repository secrets
- get a job
- github
- get a workflow run
- pipelines
- dispatch workflow
- artifact management
- environment management
- listRepositorySecrets
- enable a workflow
- actions
- individual run operations
- download an artifact
- list workflows
- individual workflow operations
- cancel a workflow run
- list runs
- enable workflow
- ci/cd
- re-run failed jobs
- get run
slug: ci-cd
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"GitHub CI/CD\"\n  description: \"Unified workflow for continuous integration and deployment combining GitHub Actions workflows, runs, jobs, artifacts, and repository management. Used by DevOps engineers for pipeline management, build monitoring, and deployment automation.\"\n  tags:\n    - GitHub\n    - CI/CD\n    - Actions\n    - Workflows\n    - DevOps\n    - Deployments\n  personas:\n    - devops engineers\n    - release managers\n    - platform engineers\n  created: \"2026-04-17\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GITHUB_TOKEN: GITHUB_TOKEN\n\ncapability:\n  consumes:\n    - import: github-actions\n      location: \"./shared/actions.yaml\"\n    - import: github-repos\n      location: \"./shared/repos.yaml\"\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: github-ci-cd-api\n      description: \"Unified REST API for CI/CD workflows combining Actions and repository management.\"\
  \n      resources:\n        - path: /v1/repositories/{owner}/{repo}/workflows\n          name: workflows\n          description: \"Workflow listing and dispatch\"\n          operations:\n            - method: GET\n              name: listRepositoryWorkflows\n              description: \"List workflows\"\n              call: \"github-actions.listRepositoryWorkflows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/workflows/{workflow_id}\n          name: workflow\n          description: \"Individual workflow operations\"\n          operations:\n            - method: GET\n              name: getWorkflow\n              description: \"Get a workflow\"\n              call: \"github-actions.getWorkflow\"\n              with:\n                workflow_id: \"rest.workflow_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/workflows/{workflow_id}/dispatches\n\
  \          name: workflow-dispatch\n          description: \"Trigger workflow runs\"\n          operations:\n            - method: POST\n              name: createWorkflowDispatchEvent\n              description: \"Dispatch a workflow\"\n              call: \"github-actions.createWorkflowDispatchEvent\"\n              with:\n                workflow_id: \"rest.workflow_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/runs\n          name: runs\n          description: \"Workflow run management\"\n          operations:\n            - method: GET\n              name: listWorkflowRunsForRepository\n              description: \"List workflow runs\"\n              call: \"github-actions.listWorkflowRunsForRepository\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/runs/{run_id}\n        \
  \  name: run\n          description: \"Individual run operations\"\n          operations:\n            - method: GET\n              name: getWorkflowRun\n              description: \"Get a workflow run\"\n              call: \"github-actions.getWorkflowRun\"\n              with:\n                run_id: \"rest.run_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/runs/{run_id}/cancel\n          name: run-cancel\n          description: \"Cancel a workflow run\"\n          operations:\n            - method: POST\n              name: cancelWorkflowRun\n              description: \"Cancel a workflow run\"\n              call: \"github-actions.cancelWorkflowRun\"\n              with:\n                run_id: \"rest.run_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/runs/{run_id}/jobs\n\
  \          name: jobs\n          description: \"Workflow run jobs\"\n          operations:\n            - method: GET\n              name: listJobsForWorkflowRun\n              description: \"List jobs\"\n              call: \"github-actions.listJobsForWorkflowRun\"\n              with:\n                run_id: \"rest.run_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/artifacts\n          name: artifacts\n          description: \"Artifact management\"\n          operations:\n            - method: GET\n              name: listArtifactsForRepository\n              description: \"List artifacts\"\n              call: \"github-actions.listArtifactsForRepository\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/secrets\n          name: secrets\n          description: \"Secret management\"\
  \n          operations:\n            - method: GET\n              name: listRepositorySecrets\n              description: \"List secrets\"\n              call: \"github-actions.listRepositorySecrets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/deployments\n          name: deployments\n          description: \"Deployment management\"\n          operations:\n            - method: GET\n              name: listDeployments\n              description: \"List deployments\"\n              call: \"github-repos.listDeployments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/environments\n          name: environments\n          description: \"Environment management\"\n          operations:\n            - method: GET\n              name: listEnvironments\n              description: \"List environments\"\
  \n              call: \"github-repos.listEnvironments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: github-ci-cd-mcp\n      transport: http\n      description: \"MCP server for AI-assisted CI/CD workflows.\"\n      tools:\n        - name: list-workflows\n          description: \"List repository workflows\"\n          call: \"github-actions.listRepositoryWorkflows\"\n          hints:\n            readOnly: true\n        - name: get-workflow\n          description: \"Get a workflow\"\n          call: \"github-actions.getWorkflow\"\n          hints:\n            readOnly: true\n        - name: dispatch-workflow\n          description: \"Trigger a workflow dispatch event\"\n          call: \"github-actions.createWorkflowDispatchEvent\"\n        - name: enable-workflow\n          description: \"Enable a workflow\"\n          call: \"github-actions.enableWorkflow\"\n        - name:\
  \ disable-workflow\n          description: \"Disable a workflow\"\n          call: \"github-actions.disableWorkflow\"\n        - name: list-runs\n          description: \"List workflow runs\"\n          call: \"github-actions.listWorkflowRunsForRepository\"\n          hints:\n            readOnly: true\n        - name: get-run\n          description: \"Get a workflow run\"\n          call: \"github-actions.getWorkflowRun\"\n          hints:\n            readOnly: true\n        - name: cancel-run\n          description: \"Cancel a workflow run\"\n          call: \"github-actions.cancelWorkflowRun\"\n        - name: rerun-workflow\n          description: \"Re-run a workflow\"\n          call: \"github-actions.rerunWorkflow\"\n        - name: rerun-failed-jobs\n          description: \"Re-run failed jobs\"\n          call: \"github-actions.rerunFailedJobsFromWorkflowRun\"\n        - name: list-jobs\n          description: \"List jobs for a workflow run\"\n          call: \"github-actions.listJobsForWorkflowRun\"\
  \n          hints:\n            readOnly: true\n        - name: get-job\n          description: \"Get a job\"\n          call: \"github-actions.getJobForWorkflowRun\"\n          hints:\n            readOnly: true\n        - name: download-job-logs\n          description: \"Download job logs\"\n          call: \"github-actions.downloadJobLogsForWorkflowRun\"\n          hints:\n            readOnly: true\n        - name: list-artifacts\n          description: \"List artifacts\"\n          call: \"github-actions.listArtifactsForRepository\"\n          hints:\n            readOnly: true\n        - name: download-artifact\n          description: \"Download an artifact\"\n          call: \"github-actions.downloadAnArtifact\"\n          hints:\n            readOnly: true\n        - name: list-secrets\n          description: \"List repository secrets\"\n          call: \"github-actions.listRepositorySecrets\"\n          hints:\n            readOnly: true\n        - name: create-or-update-secret\n\
  \          description: \"Create or update a secret\"\n          call: \"github-actions.createOrUpdateRepositorySecret\"\n          hints:\n            idempotent: true\n        - name: list-variables\n          description: \"List repository variables\"\n          call: \"github-actions.listRepositoryVariables\"\n          hints:\n            readOnly: true\n        - name: list-runners\n          description: \"List self-hosted runners\"\n          call: \"github-actions.listSelfhostedRunnersForRepository\"\n          hints:\n            readOnly: true\n        - name: list-caches\n          description: \"List GitHub Actions caches\"\n          call: \"github-actions.listGithubActionsCachesForRepository\"\n          hints:\n            readOnly: true\n        - name: get-repository\n          description: \"Get a repository\"\n          call: \"github-repos.getRepository\"\n          hints:\n            readOnly: true\n        - name: list-releases\n          description: \"List releases\"\
  \n          call: \"github-repos.listReleases\"\n          hints:\n            readOnly: true\n        - name: create-release\n          description: \"Create a release\"\n          call: \"github-repos.createRelease\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/github/refs/heads/main/capabilities/ci-cd.yaml
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
