---
categories: []
consumed_apis: []
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
- github
- unfollow user
- list gist comments
- listStarredGists
- follow user
- users
- listPublicGists
- gist management
- createDiscussion
- list organization members
- create a team discussion
- pipelines
- user profile
- list team discussions
- create discussion
- platform
- individual gist operations
- create a gist comment
- get an organization
- list followers
- user followers
- organization profile
- listFollowersOfUser
- starred gists
- listDiscussions
- star a gist
- community
- organization members
- list followers of a user
- getAnOrganization
- follow a user
- get a user
- star repository
- get a team discussion
- update gist
- star a repository
- search users
- getgist
- software development
- list users
- t1
- updategist
- discussions
- get discussion
- get gist
- list starred gists
- create gist comment
- user listing
- team discussions
- getUser
- source control
- listUsers
- list starred repositories
- gists
- unfollow a user
- list org members
- get user
- list discussions
- get a user profile
- listOrganizationMembers
- fork a gist
- update a gist
- list starred
- fork gist
- list public gists
- get a gist
- code
- get organization
- organizations
- star gist
slug: community
source_filename: community.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: GitHub Community\n  description: Unified workflow for community engagement combining gists, user profiles, organizations, and team discussions.\n    Used by community managers, developer advocates, and open source maintainers for community management and engagement.\n  tags:\n  - GitHub\n  - Community\n  - Gists\n  - Users\n  - Organizations\n  - Discussions\n  personas:\n  - community managers\n  - developer advocates\n  - open source maintainers\n  created: '2026-04-17'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GITHUB_TOKEN: GITHUB_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: github-gists\n    baseUri: https://api.github.com\n    description: GitHub REST API for gists, gist comments, forks, and stars.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: gists\n      path: /gists\n      description: Gist CRUD and listing.\n      operations:\n\
  \      - name: listPublicGists\n        method: GET\n        description: List public gists.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listStarredGists\n        method: GET\n        path: /gists/starred\n        description: List starred gists.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getgist\n        method: GET\n        path: /gists/{gist_id}\n        description: Get a gist.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategist\n        method: PATCH\n        path: /gists/{gist_id}\n        description: Update a gist.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: deletegist\n        method: DELETE\n        path: /gists/{gist_id}\n        description: Delete a gist.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getgistRevision\n        method: GET\n        path: /gists/{gist_id}/{sha}\n        description: Get a gist revision.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gist-comments\n      path: /gists/{gist_id}/comments\n      description: Gist comment management.\n      operations:\n      - name: listGistComments\n        method: GET\n        description: List gist comments.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategistComment\n        method: POST\n        description: Create a gist comment.\n        body:\n          type: json\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getgistComment\n        method: GET\n        path: /gists/{gist_id}/comments/{comment_id}\n        description: Get a gist comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategistComment\n        method: PATCH\n        path: /gists/{gist_id}/comments/{comment_id}\n        description: Update a gist comment.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegistComment\n        method: DELETE\n        path: /gists/{gist_id}/comments/{comment_id}\n        description: Delete a gist comment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gist-forks\n\
  \      path: /gists/{gist_id}/forks\n      description: Gist fork management.\n      operations:\n      - name: listGistForks\n        method: GET\n        description: List gist forks.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: forkgist\n        method: POST\n        description: Fork a gist.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gist-stars\n      path: /gists/{gist_id}/star\n      description: Gist star management.\n      operations:\n      - name: checkIfgistIsStarred\n        method: GET\n        description: Check if a gist is starred.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stargist\n        method: PUT\n        description: Star a gist.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: unstargist\n        method: DELETE\n        description: Unstar a gist.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gist-commits\n      path: /gists/{gist_id}/commits\n      description: Gist commit history.\n      operations:\n      - name: listGistCommits\n        method: GET\n        description: List gist commits.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: github-users\n    baseUri: https://api.github.com\n    description: GitHub REST API for users, emails, SSH keys, GPG keys, and profile management.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: authenticated-user\n      path: /user\n      description: Authenticated user profile management.\n\
  \      operations:\n      - name: getTheAuthenticatedUser\n        method: GET\n        description: Get the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateTheAuthenticatedUser\n        method: PATCH\n        description: Update the authenticated user.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: emails\n      path: /user/emails\n      description: Email address management for the authenticated user.\n      operations:\n      - name: listEmailAddressesForTheAuthenticatedUser\n        method: GET\n        description: List email addresses.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addAnEmailAddressForTheAuthenticatedUser\n        method: POST\n\
  \        description: Add an email address.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteAnEmailAddressForTheAuthenticatedUser\n        method: DELETE\n        description: Delete an email address.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listPublicEmailAddressesForTheAuthenticatedUser\n        method: GET\n        path: /user/public_emails\n        description: List public email addresses.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ssh-keys\n      path: /user/keys\n      description: SSH key management for the authenticated user.\n      operations:\n      - name: listPublicSshKeysForTheAuthenticatedUser\n        method: GET\n        description: List public\
  \ SSH keys.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createPublicSshKeyForTheAuthenticatedUser\n        method: POST\n        description: Create a public SSH key.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPublicSshKeyForTheAuthenticatedUser\n        method: GET\n        path: /user/keys/{key_id}\n        description: Get a public SSH key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletePublicSshKeyForTheAuthenticatedUser\n        method: DELETE\n        path: /user/keys/{key_id}\n        description: Delete a public SSH key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: gpg-keys\n      path: /user/gpg_keys\n      description: GPG key management for the authenticated user.\n      operations:\n      - name: listGpgKeysForTheAuthenticatedUser\n        method: GET\n        description: List GPG keys.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createGpgKeyForTheAuthenticatedUser\n        method: POST\n        description: Create a GPG key.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getGpgKeyForTheAuthenticatedUser\n        method: GET\n        path: /user/gpg_keys/{gpg_key_id}\n        description: Get a GPG key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteGpgKeyForTheAuthenticatedUser\n        method: DELETE\n\
  \        path: /user/gpg_keys/{gpg_key_id}\n        description: Delete a GPG key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ssh-signing-keys\n      path: /user/ssh_signing_keys\n      description: SSH signing key management.\n      operations:\n      - name: listSshSigningKeysForTheAuthenticatedUser\n        method: GET\n        description: List SSH signing keys.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createSshSigningKeyForTheAuthenticatedUser\n        method: POST\n        description: Create an SSH signing key.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAnSshSigningKeyForTheAuthenticatedUser\n        method: GET\n        path: /user/ssh_signing_keys/{ssh_signing_key_id}\n\
  \        description: Get an SSH signing key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteAnSshSigningKeyForTheAuthenticatedUser\n        method: DELETE\n        path: /user/ssh_signing_keys/{ssh_signing_key_id}\n        description: Delete an SSH signing key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: followers\n      path: /user/followers\n      description: Follower management.\n      operations:\n      - name: listFollowersOfTheAuthenticatedUser\n        method: GET\n        description: List followers of the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listThePeopleTheAuthenticatedUserFollows\n        method: GET\n        path: /user/following\n        description: List\
  \ the people the authenticated user follows.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: checkIfPersonIsFollowedByTheAuthenticatedUser\n        method: GET\n        path: /user/following/{username}\n        description: Check if a person is followed.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: followUser\n        method: PUT\n        path: /user/following/{username}\n        description: Follow a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unfollowUser\n        method: DELETE\n        path: /user/following/{username}\n        description: Unfollow a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ public-users\n      path: /users\n      description: Public user lookup and listing.\n      operations:\n      - name: listUsers\n        method: GET\n        description: List users.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getUser\n        method: GET\n        path: /users/{username}\n        description: Get a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listFollowersOfUser\n        method: GET\n        path: /users/{username}/followers\n        description: List followers of a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listThePeopleUserFollows\n        method: GET\n        path: /users/{username}/following\n        description: List the people a user follows.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listPublicKeysForUser\n        method: GET\n        path: /users/{username}/keys\n        description: List public keys for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listGpgKeysForUser\n        method: GET\n        path: /users/{username}/gpg_keys\n        description: List GPG keys for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listOrganizationsForUser\n        method: GET\n        path: /users/{username}/orgs\n        description: List organizations for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listRepositoriesForUser\n        method: GET\n        path:\
  \ /users/{username}/repos\n        description: List repositories for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: searchUsers\n        method: GET\n        path: /search/users\n        description: Search users.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: social-accounts\n      path: /user/social_accounts\n      description: Social account management.\n      operations:\n      - name: listSocialAccountsForTheAuthenticatedUser\n        method: GET\n        description: List social accounts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addSocialAccountsForTheAuthenticatedUser\n        method: POST\n        description: Add social accounts.\n        body:\n          type: json\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteSocialAccountsForTheAuthenticatedUser\n        method: DELETE\n        description: Delete social accounts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: starred\n      path: /user/starred\n      description: Starred repository management.\n      operations:\n      - name: listRepositoriesStarredByTheAuthenticatedUser\n        method: GET\n        description: List repositories starred by the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: starRepositoryForTheAuthenticatedUser\n        method: PUT\n        path: /user/starred/{owner}/{repo}\n        description: Star a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: unstarRepositoryForTheAuthenticatedUser\n        method: DELETE\n        path: /user/starred/{owner}/{repo}\n        description: Unstar a repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: github-orgs\n    baseUri: https://api.github.com\n    description: GitHub REST API for organizations, teams, members, and organization-level management.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: organizations\n      path: /orgs/{org}\n      description: Organization CRUD and listing.\n      operations:\n      - name: listOrganizations\n        method: GET\n        path: /organizations\n        description: List organizations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ getAnOrganization\n        method: GET\n        description: Get an organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateAnOrganization\n        method: PATCH\n        description: Update an organization.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteAnOrganization\n        method: DELETE\n        description: Delete an organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listOrganizationsForTheAuthenticatedUser\n        method: GET\n        path: /user/orgs\n        description: List organizations for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: members\n      path: /orgs/{org}/members\n      description: Organization member management.\n      operations:\n      - name: listOrganizationMembers\n        method: GET\n        description: List organization members.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: checkOrganizationMembershipForUser\n        method: GET\n        path: /orgs/{org}/members/{username}\n        description: Check organization membership for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeAnOrganizationMember\n        method: DELETE\n        path: /orgs/{org}/members/{username}\n        description: Remove an organization member.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getOrganizationMembershipForUser\n\
  \        method: GET\n        path: /orgs/{org}/memberships/{username}\n        description: Get organization membership for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setOrganizationMembershipForUser\n        method: PUT\n        path: /orgs/{org}/memberships/{username}\n        description: Set organization membership for a user.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeOrganizationMembershipForUser\n        method: DELETE\n        path: /orgs/{org}/memberships/{username}\n        description: Remove organization membership for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listOutsideCollaboratorsForAnOrganization\n        method: GET\n\
  \        path: /orgs/{org}/outside_collaborators\n        description: List outside collaborators.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listPublicOrganizationMembers\n        method: GET\n        path: /orgs/{org}/public_members\n        description: List public organization members.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /orgs/{org}/teams\n      description: Team CRUD and management.\n      operations:\n      - name: listTeams\n        method: GET\n        description: List teams.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createTeam\n        method: POST\n        description: Create a team.\n        body:\n          type: json\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getTeamByName\n        method: GET\n        path: /orgs/{org}/teams/{team_slug}\n        description: Get a team by name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateTeam\n        method: PATCH\n        path: /orgs/{org}/teams/{team_slug}\n        description: Update a team.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteTeam\n        method: DELETE\n        path: /orgs/{org}/teams/{team_slug}\n        description: Delete a team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listTeamMembers\n        method: GET\n        path: /orgs/{org}/teams/{team_slug}/members\n\
  \        description: List team members.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getTeamMembershipForUser\n        method: GET\n        path: /orgs/{org}/teams/{team_slug}/memberships/{username}\n        description: Get team membership for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addOrUpdateTeamMembershipForUser\n        method: PUT\n        path: /orgs/{org}/teams/{team_slug}/memberships/{username}\n        description: Add or update team membership for a user.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeTeamMembershipForUser\n        method: DELETE\n        path: /orgs/{org}/teams/{team_slug}/memberships/{username}\n        description:\
  \ Remove team membership for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listChildTeams\n        method: GET\n        path: /orgs/{org}/teams/{team_slug}/teams\n        description: List child teams.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listTeamRepositories\n        method: GET\n        path: /orgs/{org}/teams/{team_slug}/repos\n        description: List team repositories.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addOrUpdateTeamRepositoryPermissions\n        method: PUT\n        path: /orgs/{org}/teams/{team_slug}/repos/{owner}/{repo}\n        description: Add or update team repository permissions.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: removeRepositoryFromTeam\n        method: DELETE\n        path: /orgs/{org}/teams/{team_slug}/repos/{owner}/{repo}\n        description: Remove a repository from a team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: team-discussions\n      path: /orgs/{org}/teams/{team_slug}/discussions\n      description: Team discussion management.\n      operations:\n      - name: listDiscussions\n        method: GET\n        description: List discussions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createDiscussion\n        method: POST\n        description: Create a discussion.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: getDiscussion\n        method: GET\n        path: /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}\n        description: Get a discussion.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateDiscussion\n        method: PATCH\n        path: /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}\n        description: Update a discussion.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteDiscussion\n        method: DELETE\n        path: /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}\n        description: Delete a discussion.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /orgs/{org}/hooks\n\
  \      description: Organization webhook management.\n      operations:\n      - name: listOrganizationWebhooks\n        method: GET\n        description: List organization webhooks.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createAnOrganizationWebhook\n        method: POST\n        description: Create an organization webhook.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAnOrganizationWebhook\n        method: GET\n        path: /orgs/{org}/hooks/{hook_id}\n        description: Get an organization webhook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateAnOrganizationWebhook\n        method: PATCH\n        path: /orgs/{org}/hooks/{hook_id}\n        description:\
  \ Update an organization webhook.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteAnOrganizationWebhook\n        method: DELETE\n        path: /orgs/{org}/hooks/{hook_id}\n        description: Delete an organization webhook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: org-repos\n      path: /orgs/{org}/repos\n      description: Organization repository management.\n      operations:\n      - name: listOrganizationRepositories\n        method: GET\n        description: List organization repositories.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createAnOrganizationRepository\n        method: POST\n        description: Create an organization repository.\n        body:\n\
  \          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: github-community-api\n    description: Unified REST API for community engagement combining gists, users, organizations, and discussions.\n    resources:\n    - path: /v1/gists\n      name: gists\n      description: Gist management\n      operations:\n      - method: GET\n        name: listPublicGists\n        description: List public gists\n        call: github-gists.listPublicGists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gists/starred\n      name: starred-gists\n      description: Starred gists\n      operations:\n      - method: GET\n        name: listStarredGists\n        description: List starred gists\n        call: github-gists.listStarredGists\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/gists/{gist_id}\n      name: gist\n      description: Individual gist operations\n      operations:\n      - method: GET\n        name: getgist\n        description: Get a gist\n        call: github-gists.getgist\n        with:\n          gist_id: rest.gist_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: updategist\n        description: Update a gist\n        call: github-gists.updategist\n        with:\n          gist_id: rest.gist_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User listing\n      operations:\n      - method: GET\n        name: listUsers\n        description: List users\n        call: github-users.listUsers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{username}\n      name: user\n      description: User profile\n      operations:\n      - method: GET\n\
  \        name: getUser\n        description: Get a user\n        call: github-users.getUser\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{username}/followers\n      name: followers\n      description: User followers\n      operations:\n      - method: GET\n        name: listFollowersOfUser\n        description: List followers\n        call: github-users.listFollowersOfUser\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{org}\n      name: organization\n      description: Organization profile\n      operations:\n      - method: GET\n        name: getAnOrganization\n        description: Get an organization\n        call: github-orgs.getAnOrganization\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{org}/members\n\
  \      name: members\n      description: Organization members\n      operations:\n      - method: GET\n        name: listOrganizationMembers\n        description: List organization members\n        call: github-orgs.listOrganizationMembers\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{org}/teams/{team_slug}/discussions\n      name: discussions\n      description: Team discussions\n      operations:\n      - method: GET\n        name: listDiscussions\n        description: List team discussions\n        call: github-orgs.listDiscussions\n        with:\n          org: rest.org\n          team_slug: rest.team_slug\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: createDiscussion\n        description: Create a team discussion\n        call: github-orgs.createDiscussion\n        with:\n          org: rest.org\n          team_slug: rest.team_slug\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9084\n    namespace: github-community-mcp\n    transport: http\n    description: MCP server for AI-assisted community engagement.\n    tools:\n    - name: list-public-gists\n      description: List public gists\n      call: github-gists.listPublicGists\n      hints:\n        readOnly: true\n    - name: list-starred-gists\n      description: List starred gists\n      call: github-gists.listStarredGists\n      hints:\n        readOnly: true\n    - name: get-gist\n      description: Get a gist\n      call: github-gists.getgist\n      hints:\n        readOnly: true\n    - name: update-gist\n      description: Update a gist\n      call:\n\n# --- truncated at 32 KB (34 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/github/refs/heads/main/capabilities/community.yaml\n"
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
