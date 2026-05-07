---
categories:
- ci-cd
consumed_apis: []
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
- list runners
- listEnvironments
- pipelines
- getWorkflow
- rerun workflow
- deployment management
- software development
- workflow run management
- dispatch a workflow
- download job logs
- cancel run
- listRepositoryWorkflows
- download artifact
- list self-hosted runners
- ci/cd
- cancel a workflow run
- list repository secrets
- get job
- get a workflow run
- download an artifact
- disable workflow
- dispatch workflow
- list runs
- list environments
- get a repository
- enable a workflow
- list repository workflows
- list github actions caches
- individual run operations
- rerun failed jobs
- listJobsForWorkflowRun
- get a job
- workflows
- workflow listing and dispatch
- disable a workflow
- get run
- create a release
- list deployments
- github
- re-run failed jobs
- create or update a secret
- platform
- list jobs for a workflow run
- createWorkflowDispatchEvent
- get workflow
- listDeployments
- source control
- cancelWorkflowRun
- get a workflow
- list jobs
- listArtifactsForRepository
- create or update secret
- list caches
- individual workflow operations
- list workflow runs
- devops
- workflow run jobs
- list workflows
- getWorkflowRun
- listWorkflowRunsForRepository
- list artifacts
- re-run a workflow
- list secrets
- get repository
- list releases
- list variables
- secret management
- list repository variables
- t1
- deployments
- create release
- actions
- artifact management
- enable workflow
- trigger workflow runs
- code
- environment management
- trigger a workflow dispatch event
- listRepositorySecrets
slug: ci-cd
source_filename: ci-cd.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: GitHub CI/CD\n  description: Unified workflow for continuous integration and deployment combining GitHub Actions workflows, runs, jobs,\n    artifacts, and repository management. Used by DevOps engineers for pipeline management, build monitoring, and deployment\n    automation.\n  tags:\n  - GitHub\n  - CI/CD\n  - Actions\n  - Workflows\n  - DevOps\n  - Deployments\n  personas:\n  - devops engineers\n  - release managers\n  - platform engineers\n  created: '2026-04-17'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GITHUB_TOKEN: GITHUB_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: github-actions\n    baseUri: https://api.github.com\n    description: GitHub REST API for Actions workflows, runs, jobs, artifacts, secrets, variables, and runners.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: workflows\n      path: /repos/{owner}/{repo}/actions/workflows\n\
  \      description: Workflow listing and management.\n      operations:\n      - name: listRepositoryWorkflows\n        method: GET\n        description: List repository workflows.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getWorkflow\n        method: GET\n        path: /repos/{owner}/{repo}/actions/workflows/{workflow_id}\n        description: Get a workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disableWorkflow\n        method: PUT\n        path: /repos/{owner}/{repo}/actions/workflows/{workflow_id}/disable\n        description: Disable a workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: enableWorkflow\n        method: PUT\n        path: /repos/{owner}/{repo}/actions/workflows/{workflow_id}/enable\n\
  \        description: Enable a workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createWorkflowDispatchEvent\n        method: POST\n        path: /repos/{owner}/{repo}/actions/workflows/{workflow_id}/dispatches\n        description: Create a workflow dispatch event.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listWorkflowRunsForWorkflow\n        method: GET\n        path: /repos/{owner}/{repo}/actions/workflows/{workflow_id}/runs\n        description: List workflow runs for a workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runs\n      path: /repos/{owner}/{repo}/actions/runs\n      description: Workflow run management.\n      operations:\n      - name:\
  \ listWorkflowRunsForRepository\n        method: GET\n        description: List workflow runs for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getWorkflowRun\n        method: GET\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}\n        description: Get a workflow run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteWorkflowRun\n        method: DELETE\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}\n        description: Delete a workflow run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancelWorkflowRun\n        method: POST\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}/cancel\n        description: Cancel a workflow run.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: rerunWorkflow\n        method: POST\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}/rerun\n        description: Re-run a workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: rerunFailedJobsFromWorkflowRun\n        method: POST\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}/rerun-failed-jobs\n        description: Re-run failed jobs from a workflow run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getWorkflowRunAttempt\n        method: GET\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}/attempts/{attempt_number}\n        description: Get a workflow run attempt.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n      - name: downloadWorkflowRunLogs\n        method: GET\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}/logs\n        description: Download workflow run logs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteWorkflowRunLogs\n        method: DELETE\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}/logs\n        description: Delete workflow run logs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getTheReviewHistoryForWorkflowRun\n        method: GET\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}/approvals\n        description: Get the review history for a workflow run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPendingDeploymentsForWorkflowRun\n\
  \        method: GET\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}/pending_deployments\n        description: Get pending deployments for a workflow run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reviewPendingDeploymentsForWorkflowRun\n        method: POST\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}/pending_deployments\n        description: Review pending deployments for a workflow run.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /repos/{owner}/{repo}/actions\n      description: Workflow job operations.\n      operations:\n      - name: getJobForWorkflowRun\n        method: GET\n        path: /repos/{owner}/{repo}/actions/jobs/{job_id}\n        description: Get a job for a workflow run.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: downloadJobLogsForWorkflowRun\n        method: GET\n        path: /repos/{owner}/{repo}/actions/jobs/{job_id}/logs\n        description: Download job logs for a workflow run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: rerunJobFromWorkflowRun\n        method: POST\n        path: /repos/{owner}/{repo}/actions/jobs/{job_id}/rerun\n        description: Re-run a job from a workflow run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listJobsForWorkflowRun\n        method: GET\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}/jobs\n        description: List jobs for a workflow run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: artifacts\n      path: /repos/{owner}/{repo}/actions/artifacts\n      description: Workflow artifact management.\n      operations:\n      - name: listArtifactsForRepository\n        method: GET\n        description: List artifacts for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAnArtifact\n        method: GET\n        path: /repos/{owner}/{repo}/actions/artifacts/{artifact_id}\n        description: Get an artifact.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteAnArtifact\n        method: DELETE\n        path: /repos/{owner}/{repo}/actions/artifacts/{artifact_id}\n        description: Delete an artifact.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: downloadAnArtifact\n        method: GET\n        path: /repos/{owner}/{repo}/actions/artifacts/{artifact_id}/{archive_format}\n        description: Download an artifact.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listWorkflowRunArtifacts\n        method: GET\n        path: /repos/{owner}/{repo}/actions/runs/{run_id}/artifacts\n        description: List workflow run artifacts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secrets\n      path: /repos/{owner}/{repo}/actions/secrets\n      description: Repository Actions secrets management.\n      operations:\n      - name: listRepositorySecrets\n        method: GET\n        description: List repository secrets.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: getRepositoryPublicKey\n        method: GET\n        path: /repos/{owner}/{repo}/actions/secrets/public-key\n        description: Get a repository public key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getRepositorySecret\n        method: GET\n        path: /repos/{owner}/{repo}/actions/secrets/{secret_name}\n        description: Get a repository secret.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createOrUpdateRepositorySecret\n        method: PUT\n        path: /repos/{owner}/{repo}/actions/secrets/{secret_name}\n        description: Create or update a repository secret.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteRepositorySecret\n    \
  \    method: DELETE\n        path: /repos/{owner}/{repo}/actions/secrets/{secret_name}\n        description: Delete a repository secret.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: variables\n      path: /repos/{owner}/{repo}/actions/variables\n      description: Repository Actions variables management.\n      operations:\n      - name: listRepositoryVariables\n        method: GET\n        description: List repository variables.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createRepositoryVariable\n        method: POST\n        description: Create a repository variable.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getRepositoryVariable\n        method: GET\n      \
  \  path: /repos/{owner}/{repo}/actions/variables/{name}\n        description: Get a repository variable.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateRepositoryVariable\n        method: PATCH\n        path: /repos/{owner}/{repo}/actions/variables/{name}\n        description: Update a repository variable.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteRepositoryVariable\n        method: DELETE\n        path: /repos/{owner}/{repo}/actions/variables/{name}\n        description: Delete a repository variable.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runners\n      path: /repos/{owner}/{repo}/actions/runners\n      description: Self-hosted runner management.\n\
  \      operations:\n      - name: listSelfhostedRunnersForRepository\n        method: GET\n        description: List self-hosted runners for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getSelfhostedRunnerForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/actions/runners/{runner_id}\n        description: Get a self-hosted runner for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteSelfhostedRunnerFromRepository\n        method: DELETE\n        path: /repos/{owner}/{repo}/actions/runners/{runner_id}\n        description: Delete a self-hosted runner from a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createRegistrationTokenForRepository\n \
  \       method: POST\n        path: /repos/{owner}/{repo}/actions/runners/registration-token\n        description: Create a registration token for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createRemoveTokenForRepository\n        method: POST\n        path: /repos/{owner}/{repo}/actions/runners/remove-token\n        description: Create a remove token for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: caches\n      path: /repos/{owner}/{repo}/actions/caches\n      description: GitHub Actions cache management.\n      operations:\n      - name: listGithubActionsCachesForRepository\n        method: GET\n        description: List GitHub Actions caches for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: deleteGithubActionsCachesForRepositoryUsingCacheKey\n        method: DELETE\n        description: Delete GitHub Actions caches by key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteGithubActionsCacheForRepositoryUsingCacheId\n        method: DELETE\n        path: /repos/{owner}/{repo}/actions/caches/{cache_id}\n        description: Delete GitHub Actions cache by ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getGithubActionsCacheUsageForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/actions/cache/usage\n        description: Get GitHub Actions cache usage for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: permissions\n      path:\
  \ /repos/{owner}/{repo}/actions/permissions\n      description: GitHub Actions permissions management.\n      operations:\n      - name: getGithubActionsPermissionsForRepository\n        method: GET\n        description: Get GitHub Actions permissions for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setGithubActionsPermissionsForRepository\n        method: PUT\n        description: Set GitHub Actions permissions for a repository.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAllowedActionsForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/actions/permissions/selected-actions\n        description: Get allowed actions for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: setAllowedActionsForRepository\n        method: PUT\n        path: /repos/{owner}/{repo}/actions/permissions/selected-actions\n        description: Set allowed actions for a repository.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: github-repos\n    baseUri: https://api.github.com\n    description: GitHub REST API for repositories, branches, commits, tags, and releases management. Sourced from github-repos-api\n      (153 operations), github-repo-branches-api (35 operations), and github-repo-tags-api (158 operations including overlapping\n      repo operations).\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: repositories\n      path: /repos/{owner}/{repo}\n      description: Core repository management operations.\n      operations:\n\
  \      - name: getRepository\n        method: GET\n        description: Get a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateRepository\n        method: PATCH\n        description: Update a repository.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteRepository\n        method: DELETE\n        description: Delete a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listPublicRepositories\n        method: GET\n        path: /repositories\n        description: List all public repositories.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createRepositoryUsingTemplate\n\
  \        method: POST\n        path: /repos/{template_owner}/{template_repo}/generate\n        description: Create a repository using a template.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: transferRepository\n        method: POST\n        description: Transfer a repository.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listForks\n        method: GET\n        path: /repos/{owner}/{repo}/forks\n        description: List forks.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createFork\n        method: POST\n        path: /repos/{owner}/{repo}/forks\n        description: Create a fork.\n        body:\n          type: json\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listRepositoryContributors\n        method: GET\n        path: /repos/{owner}/{repo}/contributors\n        description: List repository contributors.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listRepositoryLanguages\n        method: GET\n        path: /repos/{owner}/{repo}/languages\n        description: List repository languages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listRepositoryTeams\n        method: GET\n        path: /repos/{owner}/{repo}/teams\n        description: List repository teams.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAllRepositoryTopics\n        method:\
  \ GET\n        path: /repos/{owner}/{repo}/topics\n        description: Get all repository topics.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replaceAllRepositoryTopics\n        method: PUT\n        path: /repos/{owner}/{repo}/topics\n        description: Replace all repository topics.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchRepositories\n        method: GET\n        path: /search/repositories\n        description: Search repositories.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: branches\n      path: /repos/{owner}/{repo}/branches\n      description: Branch management and protection rules.\n      operations:\n      - name: getBranch\n        method: GET\n\
  \        path: /repos/{owner}/{repo}/branches/{branch}\n        description: Get a branch.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: renameBranch\n        method: POST\n        path: /repos/{owner}/{repo}/branches/{branch}/rename\n        description: Rename a branch.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getBranchProtection\n        method: GET\n        path: /repos/{owner}/{repo}/branches/{branch}/protection\n        description: Get branch protection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateBranchProtection\n        method: PUT\n        path: /repos/{owner}/{repo}/branches/{branch}/protection\n        description: Update branch protection.\n\
  \        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteBranchProtection\n        method: DELETE\n        path: /repos/{owner}/{repo}/branches/{branch}/protection\n        description: Delete branch protection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setAdminBranchProtection\n        method: POST\n        path: /repos/{owner}/{repo}/branches/{branch}/protection/enforce_admins\n        description: Set admin branch protection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteAdminBranchProtection\n        method: DELETE\n        path: /repos/{owner}/{repo}/branches/{branch}/protection/enforce_admins\n        description: Delete admin branch protection.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getStatusChecksProtection\n        method: GET\n        path: /repos/{owner}/{repo}/branches/{branch}/protection/required_status_checks\n        description: Get status checks protection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateStatusCheckProtection\n        method: PATCH\n        path: /repos/{owner}/{repo}/branches/{branch}/protection/required_status_checks\n        description: Update status check protection.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: syncForkBranchWithTheUpstreamRepository\n        method: POST\n        path: /repos/{owner}/{repo}/merge-upstream\n        description: Sync a fork branch with the upstream repository.\n\
  \        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: mergeBranch\n        method: POST\n        path: /repos/{owner}/{repo}/merges\n        description: Merge a branch.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commits\n      path: /repos/{owner}/{repo}/commits\n      description: Commit listing, comparison, and status operations.\n      operations:\n      - name: listCommits\n        method: GET\n        description: List commits.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getCommit\n        method: GET\n        path: /repos/{owner}/{repo}/commits/{ref}\n        description: Get a commit.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: compareTwoCommits\n        method: GET\n        path: /repos/{owner}/{repo}/compare/{basehead}\n        description: Compare two commits.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listBranchesForHeadCommit\n        method: GET\n        path: /repos/{owner}/{repo}/commits/{commit_sha}/branches-where-head\n        description: List branches for HEAD commit.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listCommitComments\n        method: GET\n        path: /repos/{owner}/{repo}/commits/{commit_sha}/comments\n        description: List commit comments.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createCommitComment\n \
  \       method: POST\n        path: /repos/{owner}/{repo}/commits/{commit_sha}/comments\n        description: Create a commit comment.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listCommitCommentsForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/comments\n        description: List commit comments for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getCommitComment\n        method: GET\n        path: /repos/{owner}/{repo}/comments/{comment_id}\n        description: Get a commit comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateCommitComment\n        method: PATCH\n        path: /repos/{owner}/{repo}/comments/{comment_id}\n\
  \        description: Update a commit comment.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteCommitComment\n        method: DELETE\n        path: /repos/{owner}/{repo}/comments/{comment_id}\n        description: Delete a commit comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createCommitStatus\n        method: POST\n        path: /repos/{owner}/{repo}/statuses/{sha}\n        description: Create a commit status.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getTheCombinedStatusForSpecificReference\n        method: GET\n        path: /repos/{owner}/{repo}/commits/{ref}/status\n        description: Get the combined status\
  \ for a specific reference.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listCommitStatusesForReference\n        method: GET\n        path: /repos/{owner}/{repo}/commits/{ref}/statuses\n        description: List commit statuses for a reference.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /repos/{owner}/{repo}/tags\n      description: Tag listing and protection.\n      operations:\n      - name: listRepositoryTags\n        method: GET\n        description: List repository tags.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listTagProtectionStatesForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/tags/protection\n        description: List tag protection states for a\
  \ repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createTagProtectionStateForRepository\n        method: POST\n        path: /repos/{owner}/{repo}/tags/protection\n        description: Create a tag protection state for a repository.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteTagProtectionStateForRepository\n        method: DELETE\n        path: /repos/{owner}/{repo}/tags/protection/{tag_protection_id}\n        description: Delete a tag protection state for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: releases\n      path: /repos/{owner}/{repo}/releases\n      description: Release creation, management, and assets.\n      operations:\n \
  \     - name: listReleases\n        method: GET\n        description: List releases.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createRelease\n        method: POST\n        description: Create a release.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getRelease\n        method: GET\n        path: /repos/{owner}/{repo}/releases/{release_id}\n        description: Get a release.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateRelease\n        method: PATCH\n        path: /repos/{owner}/{repo}/releases/{release_id}\n        description: Update a release.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: deleteRelease\n        method: DELETE\n        path: /repos/{owner}/{repo}/releases/{release_id}\n        description: Delete a release.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getTheLatestRelease\n        method: GET\n        path: /repos/{owner}/{repo}/releases/latest\n        description: Get the latest release.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getReleaseByTagName\n        method: GET\n        path: /repos/{owner}/{repo}/releases/tags/{tag}\n        description: Get a release by tag name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: generateReleaseNotesContentForRelease\n        method: POST\n        path: /repos/{owner}/{repo}/releases/generate-notes\n\
  \        description: Generate release notes content for a release.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listReleaseAssets\n        method: GET\n        path: /repos/{owner}/{repo}/releases/{release_id}/assets\n        description: List release assets.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadReleaseAsset\n        method: POST\n        path: /repos/{owner}/{repo}/releases/{release_id}/assets\n        description: Upload a releas\n\n# --- truncated at 32 KB (45 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/github/refs/heads/main/capabilities/ci-cd.yaml\n"
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
