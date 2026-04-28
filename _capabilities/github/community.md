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
- listStarredGists
- list starred gists
- get a gist
- discussions
- list users
- listPublicGists
- list organization members
- listFollowersOfUser
- list public gists
- createDiscussion
- update gist
- update a gist
- follow user
- create gist comment
- unfollow a user
- unfollow user
- list discussions
- star a repository
- list followers of a user
- create a gist comment
- user listing
- user profile
- get a user profile
- search users
- platform
- organization members
- list team discussions
- fork gist
- list gist comments
- get organization
- fork a gist
- get an organization
- star a gist
- get user
- follow a user
- list starred repositories
- github
- star gist
- star repository
- list followers
- getUser
- list starred
- starred gists
- software development
- individual gist operations
- get a team discussion
- code
- getAnOrganization
- gists
- get discussion
- listDiscussions
- t1
- gist management
- listUsers
- getgist
- create a team discussion
- get gist
- community
- listOrganizationMembers
- get a user
- users
- organizations
- user followers
- pipelines
- team discussions
- updategist
- organization profile
- source control
- list org members
- create discussion
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
