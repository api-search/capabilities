---
categories: []
consumed_apis: []
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
- organization webhooks
- update organization
- list organization packages
- listTeams
- github
- get an installation
- installation access tokens
- create installation token
- list organization members
- team management
- list teams
- packages
- suspend installation
- remove an organization member
- add or update team repository permissions
- apps
- list repositories accessible to the installation
- list team repos
- get an organization
- listInstallationsForTheAuthenticatedApp
- authenticated app
- organizations
- add team member
- app installations
- create an installation access token
- get the authenticated app
- list installations
- remove member
- teams
- list org repos
- pipelines
- member management
- individual team operations
- get app webhook configuration
- update an organization
- create an organization webhook
- unsuspend installation
- create an organization repository
- list installation repos
- delete a team
- deleteAnInstallationForTheAuthenticatedApp
- listOrganizationWebhooks
- get app
- get an organization package
- list organization repositories
- list team members
- listPackagesForAnOrganization
- list org packages
- individual installation
- unsuspend an app installation
- set membership
- create webhook
- organization management
- source control
- createAnInstallationAccessTokenForAnApp
- list organization package versions
- getAnInstallationForTheAuthenticatedApp
- add team repo
- get installation
- code
- platform administration
- listOrganizationRepositories
- get team
- delete an installation
- organization repositories
- create an access token
- listOrganizationMembers
- list org package versions
- createTeam
- list packages
- getTeamByName
- getAnOrganization
- updateTeam
- update webhook config
- organization packages
- list team repositories
- get a team
- get an app installation
- update app webhook configuration
- list repositories
- delete an organization package
- delete team
- update team
- add or update team membership
- create org repo
- get webhook config
- get organization
- software development
- create team
- getTheAuthenticatedApp
- t1
- update a team
- get authenticated app
- deleteTeam
- get an app by slug
- create a team
- delete org package
- platform
- updateAnOrganization
- list app installations
- list organization webhooks
- list members
- list webhooks
- get org package
- set organization membership
- suspend an app installation
slug: platform-administration
source_filename: platform-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: GitHub Platform Administration\n  description: Unified workflow for platform administration combining GitHub Apps, organizations, teams, and packages. Used\n    by platform administrators for managing app integrations, organization governance, team access control, and package registry\n    operations.\n  tags:\n  - GitHub\n  - Platform Administration\n  - Apps\n  - Organizations\n  - Teams\n  - Packages\n  personas:\n  - platform administrators\n  - IT administrators\n  - github org owners\n  created: '2026-04-17'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GITHUB_TOKEN: GITHUB_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: github-apps\n    baseUri: https://api.github.com\n    description: GitHub REST API for GitHub Apps, installations, tokens, and webhooks.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: apps\n      path: /app\n      description:\
  \ GitHub App management.\n      operations:\n      - name: getTheAuthenticatedApp\n        method: GET\n        description: Get the authenticated app.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategithubAppFrommanifest\n        method: POST\n        path: /app-manifests/{code}/conversions\n        description: Create a GitHub App from a manifest.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAnApp\n        method: GET\n        path: /apps/{app_slug}\n        description: Get an app.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: app-webhooks\n      path: /app/hook\n      description: App webhook configuration and delivery.\n      operations:\n      - name: getwebhookConfigurationForAnApp\n      \
  \  method: GET\n        path: /app/hook/config\n        description: Get webhook configuration for an app.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatewebhookConfigurationForAnApp\n        method: PATCH\n        path: /app/hook/config\n        description: Update webhook configuration for an app.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listDeliveriesForAnAppWebhook\n        method: GET\n        path: /app/hook/deliveries\n        description: List deliveries for an app webhook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdeliveryForAnAppWebhook\n        method: GET\n        path: /app/hook/deliveries/{delivery_id}\n        description: Get a delivery\
  \ for an app webhook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: redeliverdeliveryForAnAppWebhook\n        method: POST\n        path: /app/hook/deliveries/{delivery_id}/attempts\n        description: Redeliver a delivery for an app webhook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: installations\n      path: /app/installations\n      description: App installation management.\n      operations:\n      - name: listInstallationRequestsForTheAuthenticatedApp\n        method: GET\n        path: /app/installation-requests\n        description: List installation requests.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listInstallationsForTheAuthenticatedApp\n        method: GET\n        description: List\
  \ installations for the authenticated app.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAnInstallationForTheAuthenticatedApp\n        method: GET\n        path: /app/installations/{installation_id}\n        description: Get an installation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteAnInstallationForTheAuthenticatedApp\n        method: DELETE\n        path: /app/installations/{installation_id}\n        description: Delete an installation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createAnInstallationAccessTokenForAnApp\n        method: POST\n        path: /app/installations/{installation_id}/access_tokens\n        description: Create an installation access token.\n        body:\n      \
  \    type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: suspendAnAppInstallation\n        method: PUT\n        path: /app/installations/{installation_id}/suspended\n        description: Suspend an app installation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unsuspendAnAppInstallation\n        method: DELETE\n        path: /app/installations/{installation_id}/suspended\n        description: Unsuspend an app installation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: installation-repos\n      path: /installation/repositories\n      description: Installation repository access management.\n      operations:\n      - name: listRepositoriesAccessibleToTheAppInstallation\n        method: GET\n        description:\
  \ List repositories accessible to the app installation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revokeAnInstallationAccessToken\n        method: DELETE\n        path: /installation/token\n        description: Revoke an installation access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth\n      path: /applications\n      description: OAuth token management.\n      operations:\n      - name: deleteAnAppAuthorization\n        method: DELETE\n        path: /applications/{client_id}/grant\n        description: Delete an app authorization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: checktoken\n        method: POST\n        path: /applications/{client_id}/token\n        description: Check a token.\n\
  \        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resetToken\n        method: PATCH\n        path: /applications/{client_id}/token\n        description: Reset a token.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteAnAppToken\n        method: DELETE\n        path: /applications/{client_id}/token\n        description: Delete an app token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createscopedAccessToken\n        method: POST\n        path: /applications/{client_id}/token/scoped\n        description: Create a scoped access token.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: user-installations\n      path: /user/installations\n      description: User installation access management.\n      operations:\n      - name: listAppInstallationsAccessibleToTheUserAccessToken\n        method: GET\n        description: List app installations accessible to the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listRepositoriesAccessibleToTheUserAccessToken\n        method: GET\n        path: /user/installations/{installation_id}/repositories\n        description: List repositories accessible to the user access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addrepositoryToAnAppInstallation\n        method: PUT\n        path: /user/installations/{installation_id}/repositories/{repository_id}\n   \
  \     description: Add a repository to an app installation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removerepositoryFromAnAppInstallation\n        method: DELETE\n        path: /user/installations/{installation_id}/repositories/{repository_id}\n        description: Remove a repository from an app installation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: github-orgs\n    baseUri: https://api.github.com\n    description: GitHub REST API for organizations, teams, members, and organization-level management.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: organizations\n      path: /orgs/{org}\n      description: Organization CRUD and listing.\n      operations:\n      - name: listOrganizations\n        method: GET\n      \
  \  path: /organizations\n        description: List organizations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAnOrganization\n        method: GET\n        description: Get an organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateAnOrganization\n        method: PATCH\n        description: Update an organization.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteAnOrganization\n        method: DELETE\n        description: Delete an organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listOrganizationsForTheAuthenticatedUser\n        method: GET\n  \
  \      path: /user/orgs\n        description: List organizations for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: members\n      path: /orgs/{org}/members\n      description: Organization member management.\n      operations:\n      - name: listOrganizationMembers\n        method: GET\n        description: List organization members.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: checkOrganizationMembershipForUser\n        method: GET\n        path: /orgs/{org}/members/{username}\n        description: Check organization membership for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeAnOrganizationMember\n        method: DELETE\n        path: /orgs/{org}/members/{username}\n\
  \        description: Remove an organization member.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getOrganizationMembershipForUser\n        method: GET\n        path: /orgs/{org}/memberships/{username}\n        description: Get organization membership for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setOrganizationMembershipForUser\n        method: PUT\n        path: /orgs/{org}/memberships/{username}\n        description: Set organization membership for a user.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeOrganizationMembershipForUser\n        method: DELETE\n        path: /orgs/{org}/memberships/{username}\n        description: Remove organization\
  \ membership for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listOutsideCollaboratorsForAnOrganization\n        method: GET\n        path: /orgs/{org}/outside_collaborators\n        description: List outside collaborators.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listPublicOrganizationMembers\n        method: GET\n        path: /orgs/{org}/public_members\n        description: List public organization members.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /orgs/{org}/teams\n      description: Team CRUD and management.\n      operations:\n      - name: listTeams\n        method: GET\n        description: List teams.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createTeam\n        method: POST\n        description: Create a team.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getTeamByName\n        method: GET\n        path: /orgs/{org}/teams/{team_slug}\n        description: Get a team by name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateTeam\n        method: PATCH\n        path: /orgs/{org}/teams/{team_slug}\n        description: Update a team.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteTeam\n        method: DELETE\n        path: /orgs/{org}/teams/{team_slug}\n        description: Delete\
  \ a team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listTeamMembers\n        method: GET\n        path: /orgs/{org}/teams/{team_slug}/members\n        description: List team members.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getTeamMembershipForUser\n        method: GET\n        path: /orgs/{org}/teams/{team_slug}/memberships/{username}\n        description: Get team membership for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addOrUpdateTeamMembershipForUser\n        method: PUT\n        path: /orgs/{org}/teams/{team_slug}/memberships/{username}\n        description: Add or update team membership for a user.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: removeTeamMembershipForUser\n        method: DELETE\n        path: /orgs/{org}/teams/{team_slug}/memberships/{username}\n        description: Remove team membership for a user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listChildTeams\n        method: GET\n        path: /orgs/{org}/teams/{team_slug}/teams\n        description: List child teams.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listTeamRepositories\n        method: GET\n        path: /orgs/{org}/teams/{team_slug}/repos\n        description: List team repositories.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addOrUpdateTeamRepositoryPermissions\n        method:\
  \ PUT\n        path: /orgs/{org}/teams/{team_slug}/repos/{owner}/{repo}\n        description: Add or update team repository permissions.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeRepositoryFromTeam\n        method: DELETE\n        path: /orgs/{org}/teams/{team_slug}/repos/{owner}/{repo}\n        description: Remove a repository from a team.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: team-discussions\n      path: /orgs/{org}/teams/{team_slug}/discussions\n      description: Team discussion management.\n      operations:\n      - name: listDiscussions\n        method: GET\n        description: List discussions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createDiscussion\n\
  \        method: POST\n        description: Create a discussion.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getDiscussion\n        method: GET\n        path: /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}\n        description: Get a discussion.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateDiscussion\n        method: PATCH\n        path: /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}\n        description: Update a discussion.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteDiscussion\n        method: DELETE\n        path: /orgs/{org}/teams/{team_slug}/discussions/{discussion_number}\n   \
  \     description: Delete a discussion.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /orgs/{org}/hooks\n      description: Organization webhook management.\n      operations:\n      - name: listOrganizationWebhooks\n        method: GET\n        description: List organization webhooks.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createAnOrganizationWebhook\n        method: POST\n        description: Create an organization webhook.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getAnOrganizationWebhook\n        method: GET\n        path: /orgs/{org}/hooks/{hook_id}\n        description: Get an organization webhook.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateAnOrganizationWebhook\n        method: PATCH\n        path: /orgs/{org}/hooks/{hook_id}\n        description: Update an organization webhook.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteAnOrganizationWebhook\n        method: DELETE\n        path: /orgs/{org}/hooks/{hook_id}\n        description: Delete an organization webhook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: org-repos\n      path: /orgs/{org}/repos\n      description: Organization repository management.\n      operations:\n      - name: listOrganizationRepositories\n        method: GET\n        description: List organization repositories.\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createAnOrganizationRepository\n        method: POST\n        description: Create an organization repository.\n        body:\n          type: json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: github-packages\n    baseUri: https://api.github.com\n    description: GitHub REST API for packages and package versions management.\n    authentication:\n      type: bearer\n      token: '{{GITHUB_TOKEN}}'\n    resources:\n    - name: org-packages\n      path: /orgs/{org}/packages\n      description: Organization package management.\n      operations:\n      - name: listPackagesForAnOrganization\n        method: GET\n        description: List packages for an organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: getPackageForAnOrganization\n        method: GET\n        path: /orgs/{org}/packages/{package_type}/{package_name}\n        description: Get a package for an organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletePackageForAnOrganization\n        method: DELETE\n        path: /orgs/{org}/packages/{package_type}/{package_name}\n        description: Delete a package for an organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: restorePackageForAnOrganization\n        method: POST\n        path: /orgs/{org}/packages/{package_type}/{package_name}/restore\n        description: Restore a package for an organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ listPackageVersionsForPackageOwnedByAnOrganization\n        method: GET\n        path: /orgs/{org}/packages/{package_type}/{package_name}/versions\n        description: List package versions for an organization package.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPackageVersionForAnOrganization\n        method: GET\n        path: /orgs/{org}/packages/{package_type}/{package_name}/versions/{package_version_id}\n        description: Get a package version for an organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletePackageVersionForAnOrganization\n        method: DELETE\n        path: /orgs/{org}/packages/{package_type}/{package_name}/versions/{package_version_id}\n        description: Delete a package version for an organization.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: restorePackageVersionForAnOrganization\n        method: POST\n        path: /orgs/{org}/packages/{package_type}/{package_name}/versions/{package_version_id}/restore\n        description: Restore a package version for an organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-packages\n      path: /user/packages\n      description: Authenticated user package management.\n      operations:\n      - name: listPackagesForTheAuthenticatedUsersNamespace\n        method: GET\n        description: List packages for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPackageForTheAuthenticatedUser\n        method: GET\n        path: /user/packages/{package_type}/{package_name}\n        description:\
  \ Get a package for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletePackageForTheAuthenticatedUser\n        method: DELETE\n        path: /user/packages/{package_type}/{package_name}\n        description: Delete a package for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: restorePackageForTheAuthenticatedUser\n        method: POST\n        path: /user/packages/{package_type}/{package_name}/restore\n        description: Restore a package for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listPackageVersionsForPackageOwnedByTheAuthenticatedUser\n        method: GET\n        path: /user/packages/{package_type}/{package_name}/versions\n\
  \        description: List package versions for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getPackageVersionForTheAuthenticatedUser\n        method: GET\n        path: /user/packages/{package_type}/{package_name}/versions/{package_version_id}\n        description: Get a package version for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletePackageVersionForTheAuthenticatedUser\n        method: DELETE\n        path: /user/packages/{package_type}/{package_name}/versions/{package_version_id}\n        description: Delete a package version for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: restorePackageVersionForTheAuthenticatedUser\n\
  \        method: POST\n        path: /user/packages/{package_type}/{package_name}/versions/{package_version_id}/restore\n        description: Restore a package version for the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8085\n    namespace: github-platform-admin-api\n    description: Unified REST API for platform administration combining apps, organizations, teams, and packages.\n    resources:\n    - path: /v1/app\n      name: app\n      description: Authenticated app\n      operations:\n      - method: GET\n        name: getTheAuthenticatedApp\n        description: Get the authenticated app\n        call: github-apps.getTheAuthenticatedApp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/app/installations\n      name: installations\n      description: App installations\n      operations:\n      - method:\
  \ GET\n        name: listInstallationsForTheAuthenticatedApp\n        description: List installations\n        call: github-apps.listInstallationsForTheAuthenticatedApp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/app/installations/{installation_id}\n      name: installation\n      description: Individual installation\n      operations:\n      - method: GET\n        name: getAnInstallationForTheAuthenticatedApp\n        description: Get an installation\n        call: github-apps.getAnInstallationForTheAuthenticatedApp\n        with:\n          installation_id: rest.installation_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: deleteAnInstallationForTheAuthenticatedApp\n        description: Delete an installation\n        call: github-apps.deleteAnInstallationForTheAuthenticatedApp\n        with:\n          installation_id: rest.installation_id\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n    - path: /v1/app/installations/{installation_id}/access-tokens\n      name: installation-tokens\n      description: Installation access tokens\n      operations:\n      - method: POST\n        name: createAnInstallationAccessTokenForAnApp\n        description: Create an access token\n        call: github-apps.createAnInstallationAccessTokenForAnApp\n        with:\n          installation_id: rest.installation_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{org}\n      name: organization\n      description: Organization management\n      operations:\n      - method: GET\n        name: getAnOrganization\n        description: Get an organization\n        call: github-orgs.getAnOrganization\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: updateAnOrganization\n        description:\
  \ Update an organization\n        call: github-orgs.updateAnOrganization\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{org}/members\n      name: members\n      description: Member management\n      operations:\n      - method: GET\n        name: listOrganizationMembers\n        description: List members\n        call: github-orgs.listOrganizationMembers\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{org}/teams\n      name: teams\n      description: Team management\n      operations:\n      - method: GET\n        name: listTeams\n        description: List teams\n        call: github-orgs.listTeams\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: createTeam\n        description: Create a team\n\
  \        call: github-orgs.createTeam\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{org}/teams/{team_slug}\n      name: team\n      description: Individual team operations\n      operations:\n      - method: GET\n        name: getTeamByName\n        description: Get a team\n        call: github-orgs.getTeamByName\n        with:\n          org: rest.org\n          team_slug: rest.team_slug\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: updateTeam\n        description: Update a team\n        call: github-orgs.updateTeam\n        with:\n          org: rest.org\n          team_slug: rest.team_slug\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: deleteTeam\n        description: Delete a team\n        call: github-orgs.deleteTeam\n        with:\n          org: rest.org\n\
  \          team_slug: rest.team_slug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{org}/packages\n      name: org-packages\n      description: Organization packages\n      operations:\n      - method: GET\n        name: listPackagesForAnOrganization\n        description: List packages\n        call: github-packages.listPackagesForAnOrganization\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{org}/webhooks\n      name: webhooks\n      description: Organization webhooks\n      operations:\n      - method: GET\n        name: listOrganizationWebhooks\n        description: List webhooks\n        call: github-orgs.listOrganizationWebhooks\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{org}/repos\n      name: org-repos\n      description: Organization\
  \ repositories\n      operations:\n      - method: GET\n        name: listOrganizationRepositories\n        description: List repositories\n        call: github-orgs.listOrganizationRepositories\n        with:\n          org: rest.org\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9085\n    namespace: github-platform-admin-mcp\n    transport: http\n    description: MCP server for AI-assisted platform administration.\n    tools:\n    - name: get-authenticated-app\n      description: Get the authenticated app\n      call: github-apps.getTheAuthenticatedApp\n      hints:\n        readOnly: true\n    - name: get-app\n      description: Get an app by slug\n      call: github-apps.getAnApp\n      hints:\n        readOn\n\n# --- truncated at 32 KB (36 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/github/refs/heads/main/capabilities/platform-administration.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/github/refs/heads/main/capabilities/platform-administration.yaml
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
