---
consumed_apis:
- github-repos
- github-pull-requests
description: Unified workflow for source code management combining repositories, branches, pull requests, and commits. Used by developers for day-to-day code collaboration, branch management, code review, and merging.
layout: capability
name: GitHub Source Control
operations:
- description: List public repositories
  method: GET
  name: listPublicRepositories
  path: /v1/repositories
- description: Search repositories
  method: GET
  name: searchRepositories
  path: /v1/repositories
- description: Get a repository
  method: GET
  name: getRepository
  path: /v1/repositories/{owner}/{repo}
- description: Update a repository
  method: PATCH
  name: updateRepository
  path: /v1/repositories/{owner}/{repo}
- description: Get a branch
  method: GET
  name: getBranch
  path: /v1/repositories/{owner}/{repo}/branches/{branch}
- description: List commits
  method: GET
  name: listCommits
  path: /v1/repositories/{owner}/{repo}/commits
- description: Compare two commits
  method: GET
  name: compareTwoCommits
  path: /v1/repositories/{owner}/{repo}/compare/{basehead}
- description: List pull requests
  method: GET
  name: listPullRequests
  path: /v1/repositories/{owner}/{repo}/pulls
- description: Create a pull request
  method: POST
  name: createPullRequest
  path: /v1/repositories/{owner}/{repo}/pulls
- description: Get a pull request
  method: GET
  name: getPullRequest
  path: /v1/repositories/{owner}/{repo}/pulls/{pull_number}
- description: Update a pull request
  method: PATCH
  name: updatePullRequest
  path: /v1/repositories/{owner}/{repo}/pulls/{pull_number}
- description: Merge a pull request
  method: PUT
  name: mergePullRequest
  path: /v1/repositories/{owner}/{repo}/pulls/{pull_number}/merge
- description: List reviews
  method: GET
  name: listReviewsForPullRequest
  path: /v1/repositories/{owner}/{repo}/pulls/{pull_number}/reviews
- description: Create a review
  method: POST
  name: createReviewForPullRequest
  path: /v1/repositories/{owner}/{repo}/pulls/{pull_number}/reviews
- description: List releases
  method: GET
  name: listReleases
  path: /v1/repositories/{owner}/{repo}/releases
- description: Create a release
  method: POST
  name: createRelease
  path: /v1/repositories/{owner}/{repo}/releases
- description: Get repository content
  method: GET
  name: getRepositoryContent
  path: /v1/repositories/{owner}/{repo}/contents/{path}
- description: Create or update file contents
  method: PUT
  name: createOrUpdateFileContents
  path: /v1/repositories/{owner}/{repo}/contents/{path}
personas: []
provider_name: GitHub
provider_slug: github
search_terms:
- createPullRequest
- get repository content
- get commit
- list reviews for a pull request
- compareTwoCommits
- list tags
- merge a branch
- platform
- merge pull request
- create review
- repository content management
- update a repository
- list pull requests
- getPullRequest
- getBranch
- individual pull request operations
- submit review
- pull request merge
- list pull request files
- source control
- branches
- compare two commits
- update branch protection
- getRepository
- commit operations
- listCommits
- list pr files
- updatePullRequest
- github
- release management
- branch operations
- repository listing and search
- createOrUpdateFileContents
- get a repository
- pull request management
- code review management
- createRelease
- list releases
- create or update file contents
- code review
- getRepositoryContent
- get a pull request
- create or update file
- update a pull request
- get repository
- create a release
- get branch
- searchRepositories
- search repositories
- get a commit
- compare commits
- listPullRequests
- create a review for a pull request
- mergePullRequest
- list repository tags
- t1
- submit a review for a pull request
- create release
- updateRepository
- get content
- createReviewForPullRequest
- pipelines
- create a pull request
- repository management
- merge a pull request
- request reviewers
- software development
- repositories
- listReviewsForPullRequest
- get pull request
- get a branch
- list reviews
- list commits
- update pull request
- list public repositories
- pull requests
- listReleases
- create pull request
- merge branch
- code
- request reviewers for a pull request
- create a review
- listPublicRepositories
slug: source-control
tags:
- GitHub
- Source Control
- Repositories
- Pull Requests
- Code Review
- Branches
tools:
- description: Get a repository
  hints:
    readOnly: true
  name: get-repository
- description: Search repositories
  hints:
    readOnly: true
  name: search-repositories
- description: Get a branch
  hints:
    readOnly: true
  name: get-branch
- description: List commits
  hints:
    readOnly: true
  name: list-commits
- description: Get a commit
  hints:
    readOnly: true
  name: get-commit
- description: Compare two commits
  hints:
    readOnly: true
  name: compare-commits
- description: Get repository content
  hints:
    readOnly: true
  name: get-content
- description: Create or update file contents
  hints:
    idempotent: true
  name: create-or-update-file
- description: Merge a branch
  hints: {}
  name: merge-branch
- description: List pull requests
  hints:
    readOnly: true
  name: list-pull-requests
- description: Create a pull request
  hints: {}
  name: create-pull-request
- description: Get a pull request
  hints:
    readOnly: true
  name: get-pull-request
- description: Update a pull request
  hints:
    idempotent: true
  name: update-pull-request
- description: Merge a pull request
  hints: {}
  name: merge-pull-request
- description: List reviews for a pull request
  hints:
    readOnly: true
  name: list-reviews
- description: Create a review for a pull request
  hints: {}
  name: create-review
- description: Submit a review for a pull request
  hints: {}
  name: submit-review
- description: Request reviewers for a pull request
  hints: {}
  name: request-reviewers
- description: List pull request files
  hints:
    readOnly: true
  name: list-pr-files
- description: List releases
  hints:
    readOnly: true
  name: list-releases
- description: Create a release
  hints: {}
  name: create-release
- description: List repository tags
  hints:
    readOnly: true
  name: list-tags
- description: Update branch protection
  hints:
    idempotent: true
  name: update-branch-protection
---
