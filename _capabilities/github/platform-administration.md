---
consumed_apis:
- github-apps
- github-orgs
- github-packages
description: Unified workflow for platform administration combining GitHub Apps, organizations, teams, and packages. Used by platform administrators for managing app integrations, organization governance, team access control, and package registry operations.
layout: capability
name: GitHub Platform Administration
operations:
- description: Get the authenticated app
  method: GET
  name: getTheAuthenticatedApp
  path: /v1/app
- description: List installations
  method: GET
  name: listInstallationsForTheAuthenticatedApp
  path: /v1/app/installations
- description: Get an installation
  method: GET
  name: getAnInstallationForTheAuthenticatedApp
  path: /v1/app/installations/{installation_id}
- description: Delete an installation
  method: DELETE
  name: deleteAnInstallationForTheAuthenticatedApp
  path: /v1/app/installations/{installation_id}
- description: Create an access token
  method: POST
  name: createAnInstallationAccessTokenForAnApp
  path: /v1/app/installations/{installation_id}/access-tokens
- description: Get an organization
  method: GET
  name: getAnOrganization
  path: /v1/organizations/{org}
- description: Update an organization
  method: PATCH
  name: updateAnOrganization
  path: /v1/organizations/{org}
- description: List members
  method: GET
  name: listOrganizationMembers
  path: /v1/organizations/{org}/members
- description: List teams
  method: GET
  name: listTeams
  path: /v1/organizations/{org}/teams
- description: Create a team
  method: POST
  name: createTeam
  path: /v1/organizations/{org}/teams
- description: Get a team
  method: GET
  name: getTeamByName
  path: /v1/organizations/{org}/teams/{team_slug}
- description: Update a team
  method: PATCH
  name: updateTeam
  path: /v1/organizations/{org}/teams/{team_slug}
- description: Delete a team
  method: DELETE
  name: deleteTeam
  path: /v1/organizations/{org}/teams/{team_slug}
- description: List packages
  method: GET
  name: listPackagesForAnOrganization
  path: /v1/organizations/{org}/packages
- description: List webhooks
  method: GET
  name: listOrganizationWebhooks
  path: /v1/organizations/{org}/webhooks
- description: List repositories
  method: GET
  name: listOrganizationRepositories
  path: /v1/organizations/{org}/repos
personas: []
provider_name: GitHub
provider_slug: github
search_terms:
- get a team
- create a team
- list organization webhooks
- createAnInstallationAccessTokenForAnApp
- list organization packages
- listOrganizationWebhooks
- list org repos
- getTheAuthenticatedApp
- organization repositories
- delete an organization package
- list team repos
- platform
- create an organization webhook
- pipelines
- organization management
- get team
- create an access token
- get webhook config
- add team repo
- get an installation
- apps
- list repositories
- getTeamByName
- create org repo
- update a team
- set membership
- list webhooks
- delete an installation
- get authenticated app
- getAnInstallationForTheAuthenticatedApp
- deleteTeam
- get installation
- remove member
- teams
- list teams
- list team members
- list organization repositories
- individual installation
- add or update team membership
- packages
- create an installation access token
- app installations
- list installations
- suspend an app installation
- list org package versions
- list app installations
- platform administration
- update an organization
- add team member
- github
- delete org package
- get app webhook configuration
- organization packages
- get an organization package
- list organization package versions
- code
- installation access tokens
- createTeam
- delete team
- get organization
- set organization membership
- team management
- list packages
- update organization
- create team
- listTeams
- listOrganizationRepositories
- remove an organization member
- updateAnOrganization
- get org package
- unsuspend installation
- authenticated app
- software development
- get the authenticated app
- list organization members
- member management
- organization webhooks
- list members
- update webhook config
- delete a team
- get an app installation
- deleteAnInstallationForTheAuthenticatedApp
- get an app by slug
- create an organization repository
- suspend installation
- getAnOrganization
- update app webhook configuration
- organizations
- listOrganizationMembers
- listInstallationsForTheAuthenticatedApp
- source control
- updateTeam
- get app
- individual team operations
- listPackagesForAnOrganization
- create webhook
- unsuspend an app installation
- add or update team repository permissions
- get an organization
- update team
- list team repositories
- list org packages
- list installation repos
- list repositories accessible to the installation
- create installation token
- t1
slug: platform-administration
tags:
- GitHub
- Platform Administration
- Apps
- Organizations
- Teams
- Packages
tools:
- description: Get the authenticated app
  hints:
    readOnly: true
  name: get-authenticated-app
- description: Get an app by slug
  hints:
    readOnly: true
  name: get-app
- description: List app installations
  hints:
    readOnly: true
  name: list-installations
- description: Get an app installation
  hints:
    readOnly: true
  name: get-installation
- description: Create an installation access token
  hints: {}
  name: create-installation-token
- description: Suspend an app installation
  hints: {}
  name: suspend-installation
- description: Unsuspend an app installation
  hints: {}
  name: unsuspend-installation
- description: List repositories accessible to the installation
  hints:
    readOnly: true
  name: list-installation-repos
- description: Get app webhook configuration
  hints:
    readOnly: true
  name: get-webhook-config
- description: Update app webhook configuration
  hints:
    idempotent: true
  name: update-webhook-config
- description: Get an organization
  hints:
    readOnly: true
  name: get-organization
- description: Update an organization
  hints:
    idempotent: true
  name: update-organization
- description: List organization members
  hints:
    readOnly: true
  name: list-members
- description: Set organization membership
  hints:
    idempotent: true
  name: set-membership
- description: Remove an organization member
  hints:
    destructive: true
  name: remove-member
- description: List teams
  hints:
    readOnly: true
  name: list-teams
- description: Create a team
  hints: {}
  name: create-team
- description: Get a team
  hints:
    readOnly: true
  name: get-team
- description: Update a team
  hints:
    idempotent: true
  name: update-team
- description: Delete a team
  hints:
    destructive: true
  name: delete-team
- description: List team members
  hints:
    readOnly: true
  name: list-team-members
- description: Add or update team membership
  hints:
    idempotent: true
  name: add-team-member
- description: List team repositories
  hints:
    readOnly: true
  name: list-team-repos
- description: Add or update team repository permissions
  hints:
    idempotent: true
  name: add-team-repo
- description: List organization packages
  hints:
    readOnly: true
  name: list-org-packages
- description: Get an organization package
  hints:
    readOnly: true
  name: get-org-package
- description: Delete an organization package
  hints:
    destructive: true
  name: delete-org-package
- description: List organization package versions
  hints:
    readOnly: true
  name: list-org-package-versions
- description: List organization repositories
  hints:
    readOnly: true
  name: list-org-repos
- description: Create an organization repository
  hints: {}
  name: create-org-repo
- description: List organization webhooks
  hints:
    readOnly: true
  name: list-webhooks
- description: Create an organization webhook
  hints: {}
  name: create-webhook
---
