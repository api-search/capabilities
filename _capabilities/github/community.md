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
- discussions
- user followers
- list starred gists
- listFollowersOfUser
- get a user
- search users
- list organization members
- create gist comment
- listStarredGists
- organization members
- createDiscussion
- get organization
- list users
- fork gist
- unfollow a user
- user listing
- listDiscussions
- list gist comments
- community
- organization profile
- get a user profile
- create discussion
- users
- fork a gist
- listUsers
- getUser
- follow a user
- starred gists
- update gist
- getAnOrganization
- platform
- star gist
- pipelines
- star a repository
- star a gist
- get a team discussion
- organizations
- gists
- listOrganizationMembers
- individual gist operations
- list org members
- source control
- gist management
- list team discussions
- unfollow user
- team discussions
- follow user
- star repository
- create a gist comment
- software development
- github
- list discussions
- get user
- list followers of a user
- listPublicGists
- update a gist
- get gist
- updategist
- list starred repositories
- create a team discussion
- user profile
- list followers
- get a gist
- get an organization
- list starred
- get discussion
- list public gists
- getgist
- code
- t1
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
