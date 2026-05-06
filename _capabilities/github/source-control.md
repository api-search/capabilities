---
categories: []
consumed_apis: []
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
- create review
- createPullRequest
- repository management
- create pull request
- getRepository
- list pull request files
- request reviewers
- get commit
- pull request management
- repository content management
- create a pull request
- list commits
- compareTwoCommits
- createRelease
- update branch protection
- listReleases
- submit a review for a pull request
- repository listing and search
- updateRepository
- listPublicRepositories
- get repository content
- create or update file contents
- pipelines
- create a release
- get branch
- search repositories
- pull requests
- create release
- update a pull request
- list pr files
- list pull requests
- create a review
- list public repositories
- createReviewForPullRequest
- repositories
- code review
- code review management
- get content
- get pull request
- get a branch
- get a commit
- pull request merge
- update pull request
- branches
- source control
- createOrUpdateFileContents
- individual pull request operations
- get a pull request
- code
- submit review
- list reviews
- compare two commits
- listPullRequests
- merge a branch
- request reviewers for a pull request
- list releases
- list repository tags
- update a repository
- merge pull request
- updatePullRequest
- get repository
- searchRepositories
- merge a pull request
- software development
- t1
- branch operations
- list reviews for a pull request
- list tags
- get a repository
- merge branch
- getPullRequest
- release management
- listReviewsForPullRequest
- getBranch
- platform
- compare commits
- listCommits
- commit operations
- create a review for a pull request
- github
- mergePullRequest
- getRepositoryContent
- create or update file
slug: source-control
source_filename: source-control.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: GitHub Source Control\n  description: Unified workflow for source code management combining repositories, branches, pull requests, and commits. Used\n    by developers for day-to-day code collaboration, branch management, code review, and merging.\n  tags:\n  - GitHub\n  - Source Control\n  - Repositories\n  - Pull Requests\n  - Code Review\n  - Branches\n  personas:\n  - developers\n  - software engineers\n  - tech leads\n  created: '2026-04-17'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GITHUB_TOKEN: GITHUB_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: github-repos\n    baseUri: https://api.github.com\n    description: GitHub REST API for repositories, branches, commits, tags, and releases management. Sourced from github-repos-api\n      (153 operations), github-repo-branches-api (35 operations), and github-repo-tags-api (158 operations including overlapping\n      repo operations).\n    authentication:\n\
  \      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: repositories\n      path: /repos/{owner}/{repo}\n      description: Core repository management operations.\n      operations:\n      - name: getRepository\n        method: GET\n        description: Get a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateRepository\n        method: PATCH\n        description: Update a repository.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteRepository\n        method: DELETE\n        description: Delete a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listPublicRepositories\n        method: GET\n        path: /repositories\n\
  \        description: List all public repositories.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createRepositoryUsingTemplate\n        method: POST\n        path: /repos/{template_owner}/{template_repo}/generate\n        description: Create a repository using a template.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: transferRepository\n        method: POST\n        description: Transfer a repository.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listForks\n        method: GET\n        path: /repos/{owner}/{repo}/forks\n        description: List forks.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: createFork\n        method: POST\n        path: /repos/{owner}/{repo}/forks\n        description: Create a fork.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listRepositoryContributors\n        method: GET\n        path: /repos/{owner}/{repo}/contributors\n        description: List repository contributors.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listRepositoryLanguages\n        method: GET\n        path: /repos/{owner}/{repo}/languages\n        description: List repository languages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listRepositoryTeams\n        method: GET\n        path: /repos/{owner}/{repo}/teams\n\
  \        description: List repository teams.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAllRepositoryTopics\n        method: GET\n        path: /repos/{owner}/{repo}/topics\n        description: Get all repository topics.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replaceAllRepositoryTopics\n        method: PUT\n        path: /repos/{owner}/{repo}/topics\n        description: Replace all repository topics.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchRepositories\n        method: GET\n        path: /search/repositories\n        description: Search repositories.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: branches\n      path: /repos/{owner}/{repo}/branches\n      description: Branch management and protection rules.\n      operations:\n      - name: getBranch\n        method: GET\n        path: /repos/{owner}/{repo}/branches/{branch}\n        description: Get a branch.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: renameBranch\n        method: POST\n        path: /repos/{owner}/{repo}/branches/{branch}/rename\n        description: Rename a branch.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getBranchProtection\n        method: GET\n        path: /repos/{owner}/{repo}/branches/{branch}/protection\n        description: Get branch protection.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: updateBranchProtection\n        method: PUT\n        path: /repos/{owner}/{repo}/branches/{branch}/protection\n        description: Update branch protection.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteBranchProtection\n        method: DELETE\n        path: /repos/{owner}/{repo}/branches/{branch}/protection\n        description: Delete branch protection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setAdminBranchProtection\n        method: POST\n        path: /repos/{owner}/{repo}/branches/{branch}/protection/enforce_admins\n        description: Set admin branch protection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n      - name: deleteAdminBranchProtection\n        method: DELETE\n        path: /repos/{owner}/{repo}/branches/{branch}/protection/enforce_admins\n        description: Delete admin branch protection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getStatusChecksProtection\n        method: GET\n        path: /repos/{owner}/{repo}/branches/{branch}/protection/required_status_checks\n        description: Get status checks protection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateStatusCheckProtection\n        method: PATCH\n        path: /repos/{owner}/{repo}/branches/{branch}/protection/required_status_checks\n        description: Update status check protection.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: syncForkBranchWithTheUpstreamRepository\n        method: POST\n        path: /repos/{owner}/{repo}/merge-upstream\n        description: Sync a fork branch with the upstream repository.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: mergeBranch\n        method: POST\n        path: /repos/{owner}/{repo}/merges\n        description: Merge a branch.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commits\n      path: /repos/{owner}/{repo}/commits\n      description: Commit listing, comparison, and status operations.\n      operations:\n      - name: listCommits\n        method: GET\n        description: List commits.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: getCommit\n        method: GET\n        path: /repos/{owner}/{repo}/commits/{ref}\n        description: Get a commit.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: compareTwoCommits\n        method: GET\n        path: /repos/{owner}/{repo}/compare/{basehead}\n        description: Compare two commits.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listBranchesForHeadCommit\n        method: GET\n        path: /repos/{owner}/{repo}/commits/{commit_sha}/branches-where-head\n        description: List branches for HEAD commit.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listCommitComments\n        method: GET\n        path: /repos/{owner}/{repo}/commits/{commit_sha}/comments\n\
  \        description: List commit comments.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createCommitComment\n        method: POST\n        path: /repos/{owner}/{repo}/commits/{commit_sha}/comments\n        description: Create a commit comment.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listCommitCommentsForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/comments\n        description: List commit comments for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getCommitComment\n        method: GET\n        path: /repos/{owner}/{repo}/comments/{comment_id}\n        description: Get a commit comment.\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateCommitComment\n        method: PATCH\n        path: /repos/{owner}/{repo}/comments/{comment_id}\n        description: Update a commit comment.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteCommitComment\n        method: DELETE\n        path: /repos/{owner}/{repo}/comments/{comment_id}\n        description: Delete a commit comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createCommitStatus\n        method: POST\n        path: /repos/{owner}/{repo}/statuses/{sha}\n        description: Create a commit status.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: getTheCombinedStatusForSpecificReference\n        method: GET\n        path: /repos/{owner}/{repo}/commits/{ref}/status\n        description: Get the combined status for a specific reference.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listCommitStatusesForReference\n        method: GET\n        path: /repos/{owner}/{repo}/commits/{ref}/statuses\n        description: List commit statuses for a reference.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /repos/{owner}/{repo}/tags\n      description: Tag listing and protection.\n      operations:\n      - name: listRepositoryTags\n        method: GET\n        description: List repository tags.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: listTagProtectionStatesForRepository\n        method: GET\n        path: /repos/{owner}/{repo}/tags/protection\n        description: List tag protection states for a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createTagProtectionStateForRepository\n        method: POST\n        path: /repos/{owner}/{repo}/tags/protection\n        description: Create a tag protection state for a repository.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteTagProtectionStateForRepository\n        method: DELETE\n        path: /repos/{owner}/{repo}/tags/protection/{tag_protection_id}\n        description: Delete a tag protection state for a repository.\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: releases\n      path: /repos/{owner}/{repo}/releases\n      description: Release creation, management, and assets.\n      operations:\n      - name: listReleases\n        method: GET\n        description: List releases.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createRelease\n        method: POST\n        description: Create a release.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getRelease\n        method: GET\n        path: /repos/{owner}/{repo}/releases/{release_id}\n        description: Get a release.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateRelease\n        method: PATCH\n \
  \       path: /repos/{owner}/{repo}/releases/{release_id}\n        description: Update a release.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteRelease\n        method: DELETE\n        path: /repos/{owner}/{repo}/releases/{release_id}\n        description: Delete a release.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getTheLatestRelease\n        method: GET\n        path: /repos/{owner}/{repo}/releases/latest\n        description: Get the latest release.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getReleaseByTagName\n        method: GET\n        path: /repos/{owner}/{repo}/releases/tags/{tag}\n        description: Get a release by tag name.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: generateReleaseNotesContentForRelease\n        method: POST\n        path: /repos/{owner}/{repo}/releases/generate-notes\n        description: Generate release notes content for a release.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listReleaseAssets\n        method: GET\n        path: /repos/{owner}/{repo}/releases/{release_id}/assets\n        description: List release assets.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadReleaseAsset\n        method: POST\n        path: /repos/{owner}/{repo}/releases/{release_id}/assets\n        description: Upload a release asset.\n        body:\n          type: json\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getReleaseAsset\n        method: GET\n        path: /repos/{owner}/{repo}/releases/assets/{asset_id}\n        description: Get a release asset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateReleaseAsset\n        method: PATCH\n        path: /repos/{owner}/{repo}/releases/assets/{asset_id}\n        description: Update a release asset.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteReleaseAsset\n        method: DELETE\n        path: /repos/{owner}/{repo}/releases/assets/{asset_id}\n        description: Delete a release asset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: content\n      path: /repos/{owner}/{repo}/contents\n      description: Repository content and file management.\n      operations:\n      - name: getRepositoryContent\n        method: GET\n        path: /repos/{owner}/{repo}/contents/{path}\n        description: Get repository content.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createOrUpdateFileContents\n        method: PUT\n        path: /repos/{owner}/{repo}/contents/{path}\n        description: Create or update file contents.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteFile\n        method: DELETE\n        path: /repos/{owner}/{repo}/contents/{path}\n        description: Delete a file.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: getRepositoryReadme\n        method: GET\n        path: /repos/{owner}/{repo}/readme\n        description: Get a repository README.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: git-data\n      path: /repos/{owner}/{repo}/git\n      description: Low-level Git data operations for blobs, trees, commits, refs, and tags.\n      operations:\n      - name: createBlob\n        method: POST\n        path: /repos/{owner}/{repo}/git/blobs\n        description: Create a blob.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getBlob\n        method: GET\n        path: /repos/{owner}/{repo}/git/blobs/{file_sha}\n        description: Get a blob.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n      - name: createCommit\n        method: POST\n        path: /repos/{owner}/{repo}/git/commits\n        description: Create a commit.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getCommitObject\n        method: GET\n        path: /repos/{owner}/{repo}/git/commits/{commit_sha}\n        description: Get a commit object.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listMatchingReferences\n        method: GET\n        path: /repos/{owner}/{repo}/git/matching-refs/{ref}\n        description: List matching references.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getReference\n        method: GET\n        path: /repos/{owner}/{repo}/git/ref/{ref}\n\
  \        description: Get a reference.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createReference\n        method: POST\n        path: /repos/{owner}/{repo}/git/refs\n        description: Create a reference.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateReference\n        method: PATCH\n        path: /repos/{owner}/{repo}/git/refs/{ref}\n        description: Update a reference.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteReference\n        method: DELETE\n        path: /repos/{owner}/{repo}/git/refs/{ref}\n        description: Delete a reference.\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: createTagObject\n        method: POST\n        path: /repos/{owner}/{repo}/git/tags\n        description: Create a tag object.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getTag\n        method: GET\n        path: /repos/{owner}/{repo}/git/tags/{tag_sha}\n        description: Get a tag.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createTree\n        method: POST\n        path: /repos/{owner}/{repo}/git/trees\n        description: Create a tree.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getTree\n        method: GET\n        path: /repos/{owner}/{repo}/git/trees/{tree_sha}\n\
  \        description: Get a tree.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: github-pull-requests\n    baseUri: https://api.github.com\n    description: GitHub REST API for pull requests, reviews, and review comments.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: pull-requests\n      path: /repos/{owner}/{repo}/pulls\n      description: Pull request CRUD and listing.\n      operations:\n      - name: listPullRequests\n        method: GET\n        description: List pull requests.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createPullRequest\n        method: POST\n        description: Create a pull request.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: getPullRequest\n        method: GET\n        path: /repos/{owner}/{repo}/pulls/{pull_number}\n        description: Get a pull request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatePullRequest\n        method: PATCH\n        path: /repos/{owner}/{repo}/pulls/{pull_number}\n        description: Update a pull request.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listCommitsOnPullRequest\n        method: GET\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/commits\n        description: List commits on a pull request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listPullRequestsFiles\n        method:\
  \ GET\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/files\n        description: List pull request files.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: checkIfPullRequestHasBeenMerged\n        method: GET\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/merge\n        description: Check if a pull request has been merged.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: mergePullRequest\n        method: PUT\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/merge\n        description: Merge a pull request.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatePullRequestBranch\n        method: PUT\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/update-branch\n\
  \        description: Update a pull request branch.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: review-comments\n      path: /repos/{owner}/{repo}/pulls\n      description: Pull request review comment management.\n      operations:\n      - name: listReviewCommentsInRepository\n        method: GET\n        path: /repos/{owner}/{repo}/pulls/comments\n        description: List review comments in a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getReviewCommentForPullRequest\n        method: GET\n        path: /repos/{owner}/{repo}/pulls/comments/{comment_id}\n        description: Get a review comment for a pull request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n     \
  \ - name: updateReviewCommentForPullRequest\n        method: PATCH\n        path: /repos/{owner}/{repo}/pulls/comments/{comment_id}\n        description: Update a review comment.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteReviewCommentForPullRequest\n        method: DELETE\n        path: /repos/{owner}/{repo}/pulls/comments/{comment_id}\n        description: Delete a review comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listReviewCommentsOnPullRequest\n        method: GET\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/comments\n        description: List review comments on a pull request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createReviewCommentForPullRequest\n\
  \        method: POST\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/comments\n        description: Create a review comment for a pull request.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createReplyForReviewComment\n        method: POST\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/comments/{comment_id}/replies\n        description: Create a reply for a review comment.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reviews\n      path: /repos/{owner}/{repo}/pulls/{pull_number}/reviews\n      description: Pull request review management.\n      operations:\n      - name: listReviewsForPullRequest\n        method: GET\n        description: List reviews for a pull request.\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createReviewForPullRequest\n        method: POST\n        description: Create a review for a pull request.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getReviewForPullRequest\n        method: GET\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/reviews/{review_id}\n        description: Get a review for a pull request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateReviewForPullRequest\n        method: PUT\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/reviews/{review_id}\n        description: Update a review for a pull request.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n      - name: deletePendingReviewForPullRequest\n        method: DELETE\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/reviews/{review_id}\n        description: Delete a pending review for a pull request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: dismissReviewForPullRequest\n        method: PUT\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/reviews/{review_id}/dismissals\n        description: Dismiss a review for a pull request.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submitReviewForPullRequest\n        method: POST\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/reviews/{review_id}/events\n        description: Submit a review for a pull request.\n        body:\n\
  \          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listCommentsForPullRequestReview\n        method: GET\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/reviews/{review_id}/comments\n        description: List comments for a pull request review.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reviewers\n      path: /repos/{owner}/{repo}/pulls/{pull_number}\n      description: Pull request reviewer management.\n      operations:\n      - name: getAllRequestedReviewersForPullRequest\n        method: GET\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/requested_reviewers\n        description: Get all requested reviewers for a pull request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    \
  \  - name: requestReviewersForPullRequest\n        method: POST\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/requested_reviewers\n        description: Request reviewers for a pull request.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeRequestedReviewersFromPullRequest\n        method: DELETE\n        path: /repos/{owner}/{repo}/pulls/{pull_number}/requested_reviewers\n        description: Remove requested reviewers from a pull request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: github-source-control-api\n    description: Unified REST API for source control workflows combining repos, branches, commits, and pull requests.\n    resources:\n    - path: /v1/repositories\n      name: repositories\n   \
  \   description: Repository listing and search\n      operations:\n      - method: GET\n        name: listPublicRepositories\n        description: List public repositories\n        call: github-repos.listPublicRepositories\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: searchRepositories\n        description: Search repositories\n        call: github-repos.searchRepositories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories/{owner}/{repo}\n      name: repository\n      description: Repository management\n      operations:\n      - method: GET\n        name:\n\n# --- truncated at 32 KB (40 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/github/refs/heads/main/capabilities/source-control.yaml\n"
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
