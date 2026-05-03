---
categories: []
consumed_apis:
- github-gists
- github-users
- github-orgs
description: Unified workflow for community engagement combining gists, user profiles, organizations, and team discussions. Used by community managers, developer advocates, and open source maintainers for community management and engagement.
layout: capability
name: GitHub Community
operations:
- description: List public gists
  method: GET
  name: listPublicGists
  path: /v1/gists
- description: List starred gists
  method: GET
  name: listStarredGists
  path: /v1/gists/starred
- description: Get a gist
  method: GET
  name: getgist
  path: /v1/gists/{gist_id}
- description: Update a gist
  method: PATCH
  name: updategist
  path: /v1/gists/{gist_id}
- description: List users
  method: GET
  name: listUsers
  path: /v1/users
- description: Get a user
  method: GET
  name: getUser
  path: /v1/users/{username}
- description: List followers
  method: GET
  name: listFollowersOfUser
  path: /v1/users/{username}/followers
- description: Get an organization
  method: GET
  name: getAnOrganization
  path: /v1/organizations/{org}
- description: List organization members
  method: GET
  name: listOrganizationMembers
  path: /v1/organizations/{org}/members
- description: List team discussions
  method: GET
  name: listDiscussions
  path: /v1/organizations/{org}/teams/{team_slug}/discussions
- description: Create a team discussion
  method: POST
  name: createDiscussion
  path: /v1/organizations/{org}/teams/{team_slug}/discussions
personas: []
provider_name: GitHub
provider_slug: github
search_terms:
- fork a gist
- update a gist
- team discussions
- search users
- follow user
- source control
- organization profile
- github
- get gist
- user listing
- starred gists
- list starred gists
- listOrganizationMembers
- unfollow a user
- users
- star gist
- listStarredGists
- updategist
- discussions
- community
- getUser
- get a user profile
- platform
- gist management
- create a gist comment
- get discussion
- star a repository
- list starred
- gists
- individual gist operations
- get a user
- code
- software development
- listPublicGists
- unfollow user
- fork gist
- getAnOrganization
- get organization
- create gist comment
- listUsers
- create discussion
- get a team discussion
- getgist
- organization members
- list followers
- follow a user
- user profile
- star repository
- list discussions
- listFollowersOfUser
- list team discussions
- create a team discussion
- t1
- list users
- list organization members
- list gist comments
- user followers
- pipelines
- organizations
- get a gist
- list public gists
- get user
- list org members
- listDiscussions
- list starred repositories
- get an organization
- update gist
- star a gist
- list followers of a user
- createDiscussion
slug: community
source_filename: community.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"GitHub Community\"\n  description: \"Unified workflow for community engagement combining gists, user profiles, organizations, and team discussions. Used by community managers, developer advocates, and open source maintainers for community management and engagement.\"\n  tags:\n    - GitHub\n    - Community\n    - Gists\n    - Users\n    - Organizations\n    - Discussions\n  personas:\n    - community managers\n    - developer advocates\n    - open source maintainers\n  created: \"2026-04-17\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GITHUB_TOKEN: GITHUB_TOKEN\n\ncapability:\n  consumes:\n    - import: github-gists\n      location: \"./shared/gists.yaml\"\n    - import: github-users\n      location: \"./shared/users.yaml\"\n    - import: github-orgs\n      location: \"./shared/orgs.yaml\"\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: github-community-api\n      description:\
  \ \"Unified REST API for community engagement combining gists, users, organizations, and discussions.\"\n      resources:\n        - path: /v1/gists\n          name: gists\n          description: \"Gist management\"\n          operations:\n            - method: GET\n              name: listPublicGists\n              description: \"List public gists\"\n              call: \"github-gists.listPublicGists\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/gists/starred\n          name: starred-gists\n          description: \"Starred gists\"\n          operations:\n            - method: GET\n              name: listStarredGists\n              description: \"List starred gists\"\n              call: \"github-gists.listStarredGists\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/gists/{gist_id}\n          name: gist\n          description: \"Individual\
  \ gist operations\"\n          operations:\n            - method: GET\n              name: getgist\n              description: \"Get a gist\"\n              call: \"github-gists.getgist\"\n              with:\n                gist_id: \"rest.gist_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: updategist\n              description: \"Update a gist\"\n              call: \"github-gists.updategist\"\n              with:\n                gist_id: \"rest.gist_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User listing\"\n          operations:\n            - method: GET\n              name: listUsers\n              description: \"List users\"\n              call: \"github-users.listUsers\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/users/{username}\n          name: user\n          description: \"User profile\"\n          operations:\n            - method: GET\n              name: getUser\n              description: \"Get a user\"\n              call: \"github-users.getUser\"\n              with:\n                username: \"rest.username\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{username}/followers\n          name: followers\n          description: \"User followers\"\n          operations:\n            - method: GET\n              name: listFollowersOfUser\n              description: \"List followers\"\n              call: \"github-users.listFollowersOfUser\"\n              with:\n                username: \"rest.username\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{org}\n       \
  \   name: organization\n          description: \"Organization profile\"\n          operations:\n            - method: GET\n              name: getAnOrganization\n              description: \"Get an organization\"\n              call: \"github-orgs.getAnOrganization\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{org}/members\n          name: members\n          description: \"Organization members\"\n          operations:\n            - method: GET\n              name: listOrganizationMembers\n              description: \"List organization members\"\n              call: \"github-orgs.listOrganizationMembers\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{org}/teams/{team_slug}/discussions\n          name:\
  \ discussions\n          description: \"Team discussions\"\n          operations:\n            - method: GET\n              name: listDiscussions\n              description: \"List team discussions\"\n              call: \"github-orgs.listDiscussions\"\n              with:\n                org: \"rest.org\"\n                team_slug: \"rest.team_slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createDiscussion\n              description: \"Create a team discussion\"\n              call: \"github-orgs.createDiscussion\"\n              with:\n                org: \"rest.org\"\n                team_slug: \"rest.team_slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9084\n      namespace: github-community-mcp\n      transport: http\n      description: \"MCP server for AI-assisted community engagement.\"\
  \n      tools:\n        - name: list-public-gists\n          description: \"List public gists\"\n          call: \"github-gists.listPublicGists\"\n          hints:\n            readOnly: true\n        - name: list-starred-gists\n          description: \"List starred gists\"\n          call: \"github-gists.listStarredGists\"\n          hints:\n            readOnly: true\n        - name: get-gist\n          description: \"Get a gist\"\n          call: \"github-gists.getgist\"\n          hints:\n            readOnly: true\n        - name: update-gist\n          description: \"Update a gist\"\n          call: \"github-gists.updategist\"\n          hints:\n            idempotent: true\n        - name: fork-gist\n          description: \"Fork a gist\"\n          call: \"github-gists.forkgist\"\n        - name: star-gist\n          description: \"Star a gist\"\n          call: \"github-gists.stargist\"\n        - name: list-gist-comments\n          description: \"List gist comments\"\n      \
  \    call: \"github-gists.listGistComments\"\n          hints:\n            readOnly: true\n        - name: create-gist-comment\n          description: \"Create a gist comment\"\n          call: \"github-gists.creategistComment\"\n        - name: get-user\n          description: \"Get a user profile\"\n          call: \"github-users.getUser\"\n          hints:\n            readOnly: true\n        - name: search-users\n          description: \"Search users\"\n          call: \"github-users.searchUsers\"\n          hints:\n            readOnly: true\n        - name: list-followers\n          description: \"List followers of a user\"\n          call: \"github-users.listFollowersOfUser\"\n          hints:\n            readOnly: true\n        - name: follow-user\n          description: \"Follow a user\"\n          call: \"github-users.followUser\"\n        - name: unfollow-user\n          description: \"Unfollow a user\"\n          call: \"github-users.unfollowUser\"\n        - name: list-starred\n\
  \          description: \"List starred repositories\"\n          call: \"github-users.listRepositoriesStarredByTheAuthenticatedUser\"\n          hints:\n            readOnly: true\n        - name: star-repository\n          description: \"Star a repository\"\n          call: \"github-users.starRepositoryForTheAuthenticatedUser\"\n        - name: get-organization\n          description: \"Get an organization\"\n          call: \"github-orgs.getAnOrganization\"\n          hints:\n            readOnly: true\n        - name: list-org-members\n          description: \"List organization members\"\n          call: \"github-orgs.listOrganizationMembers\"\n          hints:\n            readOnly: true\n        - name: list-discussions\n          description: \"List team discussions\"\n          call: \"github-orgs.listDiscussions\"\n          hints:\n            readOnly: true\n        - name: create-discussion\n          description: \"Create a team discussion\"\n          call: \"github-orgs.createDiscussion\"\
  \n        - name: get-discussion\n          description: \"Get a team discussion\"\n          call: \"github-orgs.getDiscussion\"\n          hints:\n            readOnly: true\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/github/refs/heads/main/capabilities/community.yaml
tags:
- GitHub
- Community
- Gists
- Users
- Organizations
- Discussions
tools:
- description: List public gists
  hints:
    readOnly: true
  name: list-public-gists
- description: List starred gists
  hints:
    readOnly: true
  name: list-starred-gists
- description: Get a gist
  hints:
    readOnly: true
  name: get-gist
- description: Update a gist
  hints:
    idempotent: true
  name: update-gist
- description: Fork a gist
  hints: {}
  name: fork-gist
- description: Star a gist
  hints: {}
  name: star-gist
- description: List gist comments
  hints:
    readOnly: true
  name: list-gist-comments
- description: Create a gist comment
  hints: {}
  name: create-gist-comment
- description: Get a user profile
  hints:
    readOnly: true
  name: get-user
- description: Search users
  hints:
    readOnly: true
  name: search-users
- description: List followers of a user
  hints:
    readOnly: true
  name: list-followers
- description: Follow a user
  hints: {}
  name: follow-user
- description: Unfollow a user
  hints: {}
  name: unfollow-user
- description: List starred repositories
  hints:
    readOnly: true
  name: list-starred
- description: Star a repository
  hints: {}
  name: star-repository
- description: Get an organization
  hints:
    readOnly: true
  name: get-organization
- description: List organization members
  hints:
    readOnly: true
  name: list-org-members
- description: List team discussions
  hints:
    readOnly: true
  name: list-discussions
- description: Create a team discussion
  hints: {}
  name: create-discussion
- description: Get a team discussion
  hints:
    readOnly: true
  name: get-discussion
---
