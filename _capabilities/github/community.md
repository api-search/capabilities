---
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
- star repository
- create a team discussion
- search users
- t1
- user listing
- updategist
- list team discussions
- get organization
- user followers
- create gist comment
- get discussion
- list followers
- fork a gist
- get gist
- software development
- community
- listUsers
- listFollowersOfUser
- list organization members
- createDiscussion
- code
- discussions
- star a gist
- list starred gists
- create a gist comment
- get user
- unfollow user
- gist management
- listPublicGists
- organizations
- list starred
- create discussion
- pipelines
- github
- organization members
- listOrganizationMembers
- get a user profile
- get a team discussion
- platform
- getAnOrganization
- update a gist
- star gist
- gists
- list users
- follow user
- listStarredGists
- team discussions
- getgist
- star a repository
- list followers of a user
- update gist
- user profile
- get a gist
- listDiscussions
- list gist comments
- follow a user
- individual gist operations
- list public gists
- list org members
- users
- getUser
- list discussions
- list starred repositories
- source control
- get a user
- unfollow a user
- fork gist
- starred gists
- get an organization
- organization profile
slug: community
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
