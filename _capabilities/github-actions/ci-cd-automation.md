---
categories:
- ci-cd
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
- cancel
- list artifacts
- workflow runs
- repository secrets
- delete cache
- disable a workflow
- remove a self-hosted runner from a repository
- devops
- list workflows
- action caches
- re-run only the failed jobs from a workflow run
- trigger a workflow
- ci/cd
- list workflow artifacts for a repository
- get details of a specific artifact
- list self-hosted runners for a repository
- jobs for a workflow run
- trigger a workflow dispatch
- list repository secrets
- enable a workflow
- list runs
- automation
- list secrets
- get a specific workflow by id or filename
- get a specific job from a workflow run
- list workflow runs for a repository
- delete artifact
- repository variables
- delete secret
- delete a specific cache entry
- get artifact
- delete runner
- cancel a workflow run
- delete run
- cancel a running workflow
- get workflow
- rerun
- create or update secret
- list variables
- get an artifact
- single workflow
- delete a workflow artifact
- rerun workflow
- get run
- list repository workflows
- workflow artifacts
- list repository variables
- list workflow runs
- get a specific workflow
- create or update a repository secret
- rerun failed jobs
- list runners
- get details of a specific workflow run
- delete a workflow run
- trigger a workflow dispatch event
- delete a repository secret
- enable workflow
- list actions caches for a repository
- delete an artifact
- trigger workflow
- get a specific self-hosted runner
- actions
- list self-hosted runners
- create variable
- delete a repository variable
- list jobs for a workflow run
- self-hosted runners
- workflows
- list jobs
- cancel run
- delete variable
- re-run a workflow
- list repository secrets (names only, not values)
- github
- list caches
- single artifact
- dispatch
- get job
- get a workflow run
- single workflow run
- get runner
- create a repository variable
- disable workflow
slug: ci-cd-automation
source_filename: ci-cd-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"GitHub Actions CI/CD Automation\"\n  description: \"Unified capability for GitHub Actions CI/CD automation combining workflow management, run monitoring, artifact handling, secrets/variables management, and runner administration. Used by DevOps engineers, platform teams, and release managers.\"\n  tags:\n    - GitHub\n    - Actions\n    - CI/CD\n    - Automation\n    - DevOps\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GITHUB_TOKEN: GITHUB_TOKEN\n\ncapability:\n  consumes:\n    - import: actions\n      location: ./shared/actions.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ci-cd-automation-api\n      description: \"Unified REST API for GitHub Actions CI/CD automation.\"\n      resources:\n        - path: /v1/workflows\n          name: workflows\n          description: \"Workflows\"\n          operations:\n            - method: GET\n         \
  \     name: list-workflows\n              description: \"List repository workflows\"\n              call: \"actions.list-repo-workflows\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows/{workflow_id}\n          name: workflow\n          description: \"Single workflow\"\n          operations:\n            - method: GET\n              name: get-workflow\n              description: \"Get a specific workflow\"\n              call: \"actions.get-workflow\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n                workflow_id: \"rest.workflow_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows/{workflow_id}/dispatch\n          name: workflow-dispatch\n          description: \"\
  Trigger a workflow\"\n          operations:\n            - method: POST\n              name: dispatch\n              description: \"Trigger a workflow dispatch\"\n              call: \"actions.create-workflow-dispatch\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n                workflow_id: \"rest.workflow_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/runs\n          name: runs\n          description: \"Workflow runs\"\n          operations:\n            - method: GET\n              name: list-runs\n              description: \"List workflow runs\"\n              call: \"actions.list-workflow-runs-for-repo\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/runs/{run_id}\n          name:\
  \ run\n          description: \"Single workflow run\"\n          operations:\n            - method: GET\n              name: get-run\n              description: \"Get a workflow run\"\n              call: \"actions.get-workflow-run\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n                run_id: \"rest.run_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-run\n              description: \"Delete a workflow run\"\n              call: \"actions.delete-workflow-run\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n                run_id: \"rest.run_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/runs/{run_id}/cancel\n          name: cancel-run\n          description: \"Cancel a workflow run\"\n\
  \          operations:\n            - method: POST\n              name: cancel\n              description: \"Cancel a workflow run\"\n              call: \"actions.cancel-workflow-run\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n                run_id: \"rest.run_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/runs/{run_id}/rerun\n          name: rerun\n          description: \"Re-run a workflow\"\n          operations:\n            - method: POST\n              name: rerun\n              description: \"Re-run a workflow\"\n              call: \"actions.rerun-workflow-run\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n                run_id: \"rest.run_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/runs/{run_id}/jobs\n      \
  \    name: jobs\n          description: \"Jobs for a workflow run\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List jobs for a workflow run\"\n              call: \"actions.list-jobs-for-workflow-run\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n                run_id: \"rest.run_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/artifacts\n          name: artifacts\n          description: \"Workflow artifacts\"\n          operations:\n            - method: GET\n              name: list-artifacts\n              description: \"List artifacts\"\n              call: \"actions.list-artifacts-for-repo\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \        - path: /v1/artifacts/{artifact_id}\n          name: artifact\n          description: \"Single artifact\"\n          operations:\n            - method: GET\n              name: get-artifact\n              description: \"Get an artifact\"\n              call: \"actions.get-artifact\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n                artifact_id: \"rest.artifact_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-artifact\n              description: \"Delete an artifact\"\n              call: \"actions.delete-artifact\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n                artifact_id: \"rest.artifact_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/secrets\n          name:\
  \ secrets\n          description: \"Repository secrets\"\n          operations:\n            - method: GET\n              name: list-secrets\n              description: \"List repository secrets\"\n              call: \"actions.list-repo-secrets\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/variables\n          name: variables\n          description: \"Repository variables\"\n          operations:\n            - method: GET\n              name: list-variables\n              description: \"List repository variables\"\n              call: \"actions.list-repo-variables\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/caches\n          name: caches\n\
  \          description: \"Action caches\"\n          operations:\n            - method: GET\n              name: list-caches\n              description: \"List caches\"\n              call: \"actions.list-actions-caches\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/runners\n          name: runners\n          description: \"Self-hosted runners\"\n          operations:\n            - method: GET\n              name: list-runners\n              description: \"List self-hosted runners\"\n              call: \"actions.list-self-hosted-runners-for-repo\"\n              with:\n                owner: \"rest.owner\"\n                repo: \"rest.repo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ci-cd-automation-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted GitHub Actions CI/CD automation.\"\n      tools:\n        - name: list-workflows\n          description: \"List repository workflows\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"actions.list-repo-workflows\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workflow\n          description: \"Get a specific workflow by ID or filename\"\n          hints:\n            readOnly: true\n          call: \"actions.get-workflow\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            workflow_id: \"tools.workflow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: trigger-workflow\n          description: \"Trigger a workflow dispatch\
  \ event\"\n          hints:\n            readOnly: false\n          call: \"actions.create-workflow-dispatch\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            workflow_id: \"tools.workflow_id\"\n            ref: \"tools.ref\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: disable-workflow\n          description: \"Disable a workflow\"\n          hints:\n            readOnly: false\n          call: \"actions.disable-workflow\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            workflow_id: \"tools.workflow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enable-workflow\n          description: \"Enable a workflow\"\n          hints:\n            readOnly: false\n          call: \"actions.enable-workflow\"\n          with:\n            owner: \"tools.owner\"\n           \
  \ repo: \"tools.repo\"\n            workflow_id: \"tools.workflow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-runs\n          description: \"List workflow runs for a repository\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"actions.list-workflow-runs-for-repo\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-run\n          description: \"Get details of a specific workflow run\"\n          hints:\n            readOnly: true\n          call: \"actions.get-workflow-run\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            run_id: \"tools.run_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-run\n          description:\
  \ \"Cancel a running workflow\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"actions.cancel-workflow-run\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            run_id: \"tools.run_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: rerun-workflow\n          description: \"Re-run a workflow\"\n          hints:\n            readOnly: false\n          call: \"actions.rerun-workflow-run\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            run_id: \"tools.run_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: rerun-failed-jobs\n          description: \"Re-run only the failed jobs from a workflow run\"\n          hints:\n            readOnly: false\n          call: \"actions.rerun-failed-jobs\"\n          with:\n            owner:\
  \ \"tools.owner\"\n            repo: \"tools.repo\"\n            run_id: \"tools.run_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-run\n          description: \"Delete a workflow run\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"actions.delete-workflow-run\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            run_id: \"tools.run_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-jobs\n          description: \"List jobs for a workflow run\"\n          hints:\n            readOnly: true\n          call: \"actions.list-jobs-for-workflow-run\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            run_id: \"tools.run_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n   \
  \     - name: get-job\n          description: \"Get a specific job from a workflow run\"\n          hints:\n            readOnly: true\n          call: \"actions.get-job-for-workflow-run\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            job_id: \"tools.job_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-artifacts\n          description: \"List workflow artifacts for a repository\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"actions.list-artifacts-for-repo\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-artifact\n          description: \"Get details of a specific artifact\"\n          hints:\n            readOnly: true\n          call: \"actions.get-artifact\"\n          with:\n\
  \            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            artifact_id: \"tools.artifact_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-artifact\n          description: \"Delete a workflow artifact\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"actions.delete-artifact\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            artifact_id: \"tools.artifact_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-secrets\n          description: \"List repository secrets (names only, not values)\"\n          hints:\n            readOnly: true\n          call: \"actions.list-repo-secrets\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: create-or-update-secret\n          description: \"Create or update a repository secret\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"actions.create-or-update-repo-secret\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            secret_name: \"tools.secret_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-secret\n          description: \"Delete a repository secret\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"actions.delete-repo-secret\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            secret_name: \"tools.secret_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-variables\n          description: \"List repository variables\"\n    \
  \      hints:\n            readOnly: true\n          call: \"actions.list-repo-variables\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-variable\n          description: \"Create a repository variable\"\n          hints:\n            readOnly: false\n          call: \"actions.create-repo-variable\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            name: \"tools.name\"\n            value: \"tools.value\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-variable\n          description: \"Delete a repository variable\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"actions.delete-repo-variable\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\
  \n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-caches\n          description: \"List Actions caches for a repository\"\n          hints:\n            readOnly: true\n          call: \"actions.list-actions-caches\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-cache\n          description: \"Delete a specific cache entry\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"actions.delete-actions-cache-by-id\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            cache_id: \"tools.cache_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-runners\n          description: \"List self-hosted runners\
  \ for a repository\"\n          hints:\n            readOnly: true\n          call: \"actions.list-self-hosted-runners-for-repo\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-runner\n          description: \"Get a specific self-hosted runner\"\n          hints:\n            readOnly: true\n          call: \"actions.get-self-hosted-runner-for-repo\"\n          with:\n            owner: \"tools.owner\"\n            repo: \"tools.repo\"\n            runner_id: \"tools.runner_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-runner\n          description: \"Remove a self-hosted runner from a repository\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"actions.delete-self-hosted-runner-from-repo\"\n          with:\n            owner:\
  \ \"tools.owner\"\n            repo: \"tools.repo\"\n            runner_id: \"tools.runner_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/github-actions/refs/heads/main/capabilities/ci-cd-automation.yaml
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
