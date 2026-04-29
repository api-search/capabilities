---
categories: []
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
- create a pull request
- repository listing and search
- compareTwoCommits
- list reviews
- list commits
- listCommits
- create review
- search repositories
- list pr files
- merge pull request
- submit a review for a pull request
- get a branch
- getRepositoryContent
- repository content management
- searchRepositories
- get a pull request
- compare commits
- request reviewers
- repositories
- updatePullRequest
- updateRepository
- compare two commits
- update branch protection
- software development
- create a release
- mergePullRequest
- list reviews for a pull request
- get pull request
- create a review
- get a commit
- request reviewers for a pull request
- t1
- update a pull request
- platform
- pull request management
- code
- submit review
- get a repository
- list tags
- create or update file contents
- pull request merge
- list pull requests
- branch operations
- release management
- create or update file
- repository management
- pipelines
- listReviewsForPullRequest
- list public repositories
- getBranch
- getPullRequest
- merge a pull request
- code review
- list pull request files
- get branch
- get commit
- create release
- update a repository
- listPublicRepositories
- listReleases
- createReviewForPullRequest
- get repository
- github
- listPullRequests
- list releases
- code review management
- get content
- merge a branch
- update pull request
- merge branch
- get repository content
- createOrUpdateFileContents
- create pull request
- createPullRequest
- createRelease
- create a review for a pull request
- pull requests
- list repository tags
- source control
- branches
- commit operations
- getRepository
- individual pull request operations
slug: source-control
source_filename: source-control.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"GitHub Source Control\"\n  description: \"Unified workflow for source code management combining repositories, branches, pull requests, and commits. Used by developers for day-to-day code collaboration, branch management, code review, and merging.\"\n  tags:\n    - GitHub\n    - Source Control\n    - Repositories\n    - Pull Requests\n    - Code Review\n    - Branches\n  personas:\n    - developers\n    - software engineers\n    - tech leads\n  created: \"2026-04-17\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GITHUB_TOKEN: GITHUB_TOKEN\n\ncapability:\n  consumes:\n    - import: github-repos\n      location: \"./shared/repos.yaml\"\n    - import: github-pull-requests\n      location: \"./shared/pull-requests.yaml\"\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: github-source-control-api\n      description: \"Unified REST API for source control workflows combining repos, branches,\
  \ commits, and pull requests.\"\n      resources:\n        - path: /v1/repositories\n          name: repositories\n          description: \"Repository listing and search\"\n          operations:\n            - method: GET\n              name: listPublicRepositories\n              description: \"List public repositories\"\n              call: \"github-repos.listPublicRepositories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: searchRepositories\n              description: \"Search repositories\"\n              call: \"github-repos.searchRepositories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}\n          name: repository\n          description: \"Repository management\"\n          operations:\n            - method: GET\n              name: getRepository\n              description:\
  \ \"Get a repository\"\n              call: \"github-repos.getRepository\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: updateRepository\n              description: \"Update a repository\"\n              call: \"github-repos.updateRepository\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/branches/{branch}\n          name: branch\n          description: \"Branch operations\"\n          operations:\n            - method: GET\n              name: getBranch\n              description: \"Get a branch\"\n              call: \"github-repos.getBranch\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/commits\n          name: commits\n          description: \"Commit operations\"\n          operations:\n\
  \            - method: GET\n              name: listCommits\n              description: \"List commits\"\n              call: \"github-repos.listCommits\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/compare/{basehead}\n          name: compare\n          description: \"Compare commits\"\n          operations:\n            - method: GET\n              name: compareTwoCommits\n              description: \"Compare two commits\"\n              call: \"github-repos.compareTwoCommits\"\n              with:\n                basehead: \"rest.basehead\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/pulls\n          name: pull-requests\n          description: \"Pull request management\"\n          operations:\n            - method: GET\n              name: listPullRequests\n              description:\
  \ \"List pull requests\"\n              call: \"github-pull-requests.listPullRequests\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createPullRequest\n              description: \"Create a pull request\"\n              call: \"github-pull-requests.createPullRequest\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/pulls/{pull_number}\n          name: pull-request\n          description: \"Individual pull request operations\"\n          operations:\n            - method: GET\n              name: getPullRequest\n              description: \"Get a pull request\"\n              call: \"github-pull-requests.getPullRequest\"\n              with:\n                pull_number: \"rest.pull_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n            - method: PATCH\n              name: updatePullRequest\n              description: \"Update a pull request\"\n              call: \"github-pull-requests.updatePullRequest\"\n              with:\n                pull_number: \"rest.pull_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/pulls/{pull_number}/merge\n          name: merge\n          description: \"Pull request merge\"\n          operations:\n            - method: PUT\n              name: mergePullRequest\n              description: \"Merge a pull request\"\n              call: \"github-pull-requests.mergePullRequest\"\n              with:\n                pull_number: \"rest.pull_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/pulls/{pull_number}/reviews\n          name: reviews\n          description:\
  \ \"Code review management\"\n          operations:\n            - method: GET\n              name: listReviewsForPullRequest\n              description: \"List reviews\"\n              call: \"github-pull-requests.listReviewsForPullRequest\"\n              with:\n                pull_number: \"rest.pull_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createReviewForPullRequest\n              description: \"Create a review\"\n              call: \"github-pull-requests.createReviewForPullRequest\"\n              with:\n                pull_number: \"rest.pull_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/releases\n          name: releases\n          description: \"Release management\"\n          operations:\n            - method: GET\n              name: listReleases\n\
  \              description: \"List releases\"\n              call: \"github-repos.listReleases\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createRelease\n              description: \"Create a release\"\n              call: \"github-repos.createRelease\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories/{owner}/{repo}/contents/{path}\n          name: contents\n          description: \"Repository content management\"\n          operations:\n            - method: GET\n              name: getRepositoryContent\n              description: \"Get repository content\"\n              call: \"github-repos.getRepositoryContent\"\n              with:\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n\
  \              name: createOrUpdateFileContents\n              description: \"Create or update file contents\"\n              call: \"github-repos.createOrUpdateFileContents\"\n              with:\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: github-source-control-mcp\n      transport: http\n      description: \"MCP server for AI-assisted source control workflows.\"\n      tools:\n        - name: get-repository\n          description: \"Get a repository\"\n          call: \"github-repos.getRepository\"\n          hints:\n            readOnly: true\n        - name: search-repositories\n          description: \"Search repositories\"\n          call: \"github-repos.searchRepositories\"\n          hints:\n            readOnly: true\n        - name: get-branch\n          description: \"Get a branch\"\n          call: \"github-repos.getBranch\"\n \
  \         hints:\n            readOnly: true\n        - name: list-commits\n          description: \"List commits\"\n          call: \"github-repos.listCommits\"\n          hints:\n            readOnly: true\n        - name: get-commit\n          description: \"Get a commit\"\n          call: \"github-repos.getCommit\"\n          hints:\n            readOnly: true\n        - name: compare-commits\n          description: \"Compare two commits\"\n          call: \"github-repos.compareTwoCommits\"\n          hints:\n            readOnly: true\n        - name: get-content\n          description: \"Get repository content\"\n          call: \"github-repos.getRepositoryContent\"\n          hints:\n            readOnly: true\n        - name: create-or-update-file\n          description: \"Create or update file contents\"\n          call: \"github-repos.createOrUpdateFileContents\"\n          hints:\n            idempotent: true\n        - name: merge-branch\n          description: \"Merge a branch\"\
  \n          call: \"github-repos.mergeBranch\"\n        - name: list-pull-requests\n          description: \"List pull requests\"\n          call: \"github-pull-requests.listPullRequests\"\n          hints:\n            readOnly: true\n        - name: create-pull-request\n          description: \"Create a pull request\"\n          call: \"github-pull-requests.createPullRequest\"\n        - name: get-pull-request\n          description: \"Get a pull request\"\n          call: \"github-pull-requests.getPullRequest\"\n          hints:\n            readOnly: true\n        - name: update-pull-request\n          description: \"Update a pull request\"\n          call: \"github-pull-requests.updatePullRequest\"\n          hints:\n            idempotent: true\n        - name: merge-pull-request\n          description: \"Merge a pull request\"\n          call: \"github-pull-requests.mergePullRequest\"\n        - name: list-reviews\n          description: \"List reviews for a pull request\"\n   \
  \       call: \"github-pull-requests.listReviewsForPullRequest\"\n          hints:\n            readOnly: true\n        - name: create-review\n          description: \"Create a review for a pull request\"\n          call: \"github-pull-requests.createReviewForPullRequest\"\n        - name: submit-review\n          description: \"Submit a review for a pull request\"\n          call: \"github-pull-requests.submitReviewForPullRequest\"\n        - name: request-reviewers\n          description: \"Request reviewers for a pull request\"\n          call: \"github-pull-requests.requestReviewersForPullRequest\"\n        - name: list-pr-files\n          description: \"List pull request files\"\n          call: \"github-pull-requests.listPullRequestsFiles\"\n          hints:\n            readOnly: true\n        - name: list-releases\n          description: \"List releases\"\n          call: \"github-repos.listReleases\"\n          hints:\n            readOnly: true\n        - name: create-release\n\
  \          description: \"Create a release\"\n          call: \"github-repos.createRelease\"\n        - name: list-tags\n          description: \"List repository tags\"\n          call: \"github-repos.listRepositoryTags\"\n          hints:\n            readOnly: true\n        - name: update-branch-protection\n          description: \"Update branch protection\"\n          call: \"github-repos.updateBranchProtection\"\n          hints:\n            idempotent: true\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/github/refs/heads/main/capabilities/source-control.yaml
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
