---
categories: []
consumed_apis: []
description: The MongoDB Atlas Administration API allows developers to manage all components in MongoDB Atlas. The Atlas Administration API supports OAuth2 Service Accounts and HTTP Digest-based API keys. Service accounts are the recommended authentication method and API keys are considered a legacy option. To authenticate with a Service Account, first exchange its client ID and secret for an access token using the OAuth 2.0 Client Credentials flow. Atlas provides a token endpoint at `POST https://cloud.mongodb.com/api/oauth/token`, which returns a Bearer token that is reusable and valid for 1 hour (3600 s
layout: capability
name: MongoDB Atlas Administration API
operations:
- description: Return the Status of This MongoDB Application
  method: GET
  name: getsystemstatus
  path: /api/atlas/v2
- description: Return All Alert Configuration Matchers Field Names
  method: GET
  name: listalertconfigmatcherfieldnames
  path: /api/atlas/v2/alertConfigs/matchers/fieldNames
- description: Return All Authorized Clusters in All Projects
  method: GET
  name: listclusterdetails
  path: /api/atlas/v2/clusters
- description: Return All Event Types
  method: GET
  name: listeventtypes
  path: /api/atlas/v2/eventTypes
- description: Delete One Federation Settings Instance
  method: DELETE
  name: deletefederationsetting
  path: /api/atlas/v2/federationSettings/{federationSettingsId}
- description: Return All Organization Configurations from One Federation
  method: GET
  name: listfederationsettingconnectedorgconfigs
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs
- description: Remove One Organization Configuration from One Federation
  method: DELETE
  name: removefederationsettingconnectedorgconfig
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}
- description: Return One Organization Configuration from One Federation
  method: GET
  name: getfederationsettingconnectedorgconfig
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}
- description: Update One Organization Configuration in One Federation
  method: PATCH
  name: updatefederationsettingconnectedorgconfig
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}
- description: Return All Role Mappings from One Organization
  method: GET
  name: listfederationsettingconnectedorgconfigrolemappi
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}/roleMappings
- description: Create One Role Mapping in One Organization Configuration
  method: POST
  name: createfederationsettingconnectedorgconfigrolemap
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}/roleMappings
- description: Remove One Role Mapping from One Organization
  method: DELETE
  name: deletefederationsettingconnectedorgconfigrolemap
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}/roleMappings/{id}
- description: Return One Role Mapping from One Organization
  method: GET
  name: getfederationsettingconnectedorgconfigrolemappin
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}/roleMappings/{id}
- description: Update One Role Mapping in One Organization
  method: PUT
  name: updatefederationsettingconnectedorgconfigrolemap
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}/roleMappings/{id}
- description: Return All Identity Providers in One Federation
  method: GET
  name: listfederationsettingidentityproviders
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/identityProviders
- description: Create One Identity Provider
  method: POST
  name: createfederationsettingidentityprovider
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/identityProviders
- description: Delete One Identity Provider
  method: DELETE
  name: deletefederationsettingidentityprovider
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/identityProviders/{identityProviderId}
- description: Return One Identity Provider by ID
  method: GET
  name: getfederationsettingidentityprovider
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/identityProviders/{identityProviderId}
- description: Update One Identity Provider
  method: PATCH
  name: updatefederationsettingidentityprovider
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/identityProviders/{identityProviderId}
- description: Revoke JWKS from One OIDC Identity Provider
  method: DELETE
  name: revokefederationsettingidentityproviderjwks
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/identityProviders/{identityProviderId}/jwks
- description: Return Metadata of One Identity Provider
  method: GET
  name: getfederationsettingidentityprovidermetadata
  path: /api/atlas/v2/federationSettings/{federationSettingsId}/identityProviders/{identityProviderId}/metadata.xml
- description: Return All Projects
  method: GET
  name: listgroups
  path: /api/atlas/v2/groups
- description: Create One Project
  method: POST
  name: creategroup
  path: /api/atlas/v2/groups
- description: Return One Project by Name
  method: GET
  name: getgroupbyname
  path: /api/atlas/v2/groups/byName/{groupName}
- description: Remove One Project
  method: DELETE
  name: deletegroup
  path: /api/atlas/v2/groups/{groupId}
- description: Return One Project
  method: GET
  name: getgroup
  path: /api/atlas/v2/groups/{groupId}
- description: Update One Project
  method: PATCH
  name: updategroup
  path: /api/atlas/v2/groups/{groupId}
- description: Add One MongoDB Cloud User to One Project
  method: POST
  name: addgroupaccessuser
  path: /api/atlas/v2/groups/{groupId}/access
- description: Return All Project IP Access List Entries
  method: GET
  name: listgroupaccesslistentries
  path: /api/atlas/v2/groups/{groupId}/accessList
- description: Add Entries to Project IP Access List
  method: POST
  name: creategroupaccesslistentry
  path: /api/atlas/v2/groups/{groupId}/accessList
- description: Remove One Entry from One Project IP Access List
  method: DELETE
  name: deletegroupaccesslistentry
  path: /api/atlas/v2/groups/{groupId}/accessList/{entryValue}
- description: Return One Project IP Access List Entry
  method: GET
  name: getgroupaccesslistentry
  path: /api/atlas/v2/groups/{groupId}/accessList/{entryValue}
- description: Return Status of One Project IP Access List Entry
  method: GET
  name: getgroupaccessliststatus
  path: /api/atlas/v2/groups/{groupId}/accessList/{entryValue}/status
- description: Return Pre-Filtered Activity Feed Link for One Project
  method: GET
  name: getgroupactivityfeed
  path: /api/atlas/v2/groups/{groupId}/activityFeed
- description: Return All Alert Configurations in One Project
  method: GET
  name: listgroupalertconfigs
  path: /api/atlas/v2/groups/{groupId}/alertConfigs
- description: Create One Alert Configuration in One Project
  method: POST
  name: creategroupalertconfig
  path: /api/atlas/v2/groups/{groupId}/alertConfigs
- description: Remove One Alert Configuration from One Project
  method: DELETE
  name: deletegroupalertconfig
  path: /api/atlas/v2/groups/{groupId}/alertConfigs/{alertConfigId}
- description: Return One Alert Configuration from One Project
  method: GET
  name: getgroupalertconfig
  path: /api/atlas/v2/groups/{groupId}/alertConfigs/{alertConfigId}
- description: Toggle State of One Alert Configuration in One Project
  method: PATCH
  name: togglegroupalertconfig
  path: /api/atlas/v2/groups/{groupId}/alertConfigs/{alertConfigId}
- description: Update One Alert Configuration in One Project
  method: PUT
  name: updategroupalertconfig
  path: /api/atlas/v2/groups/{groupId}/alertConfigs/{alertConfigId}
- description: Return All Open Alerts for One Alert Configuration
  method: GET
  name: getgroupalertconfigalerts
  path: /api/atlas/v2/groups/{groupId}/alertConfigs/{alertConfigId}/alerts
- description: Return All Alerts from One Project
  method: GET
  name: listgroupalerts
  path: /api/atlas/v2/groups/{groupId}/alerts
- description: Return One Alert from One Project
  method: GET
  name: getgroupalert
  path: /api/atlas/v2/groups/{groupId}/alerts/{alertId}
- description: Acknowledge One Alert from One Project
  method: PATCH
  name: acknowledgegroupalert
  path: /api/atlas/v2/groups/{groupId}/alerts/{alertId}
- description: Return All Alert Configurations Set for One Alert
  method: GET
  name: getgroupalertalertconfigs
  path: /api/atlas/v2/groups/{groupId}/alerts/{alertId}/alertConfigs
- description: Return All Organization API Keys Assigned to One Project
  method: GET
  name: listgroupapikeys
  path: /api/atlas/v2/groups/{groupId}/apiKeys
- description: Create and Assign One Organization API Key to One Project
  method: POST
  name: creategroupapikey
  path: /api/atlas/v2/groups/{groupId}/apiKeys
- description: Unassign One Organization API Key from One Project
  method: DELETE
  name: removegroupapikey
  path: /api/atlas/v2/groups/{groupId}/apiKeys/{apiUserId}
- description: Update Organization API Key Roles for One Project
  method: PATCH
  name: updategroupapikeyroles
  path: /api/atlas/v2/groups/{groupId}/apiKeys/{apiUserId}
- description: Assign One Organization API Key to One Project
  method: POST
  name: addgroupapikey
  path: /api/atlas/v2/groups/{groupId}/apiKeys/{apiUserId}
- description: Return Auditing Configuration for One Project
  method: GET
  name: getgroupauditlog
  path: /api/atlas/v2/groups/{groupId}/auditLog
- description: Update Auditing Configuration for One Project
  method: PATCH
  name: updategroupauditlog
  path: /api/atlas/v2/groups/{groupId}/auditLog
- description: Return One Custom DNS Configuration for Atlas Clusters on AWS
  method: GET
  name: getgroupawscustomdns
  path: /api/atlas/v2/groups/{groupId}/awsCustomDNS
- description: Update State of One Custom DNS Configuration for Atlas Clusters on AWS
  method: PATCH
  name: togglegroupawscustomdns
  path: /api/atlas/v2/groups/{groupId}/awsCustomDNS
- description: Return All Snapshot Export Buckets
  method: GET
  name: listgroupbackupexportbuckets
  path: /api/atlas/v2/groups/{groupId}/backup/exportBuckets
- description: Create One Snapshot Export Bucket
  method: POST
  name: creategroupbackupexportbucket
  path: /api/atlas/v2/groups/{groupId}/backup/exportBuckets
- description: Delete One Snapshot Export Bucket
  method: DELETE
  name: deletegroupbackupexportbucket
  path: /api/atlas/v2/groups/{groupId}/backup/exportBuckets/{exportBucketId}
- description: Return One Snapshot Export Bucket
  method: GET
  name: getgroupbackupexportbucket
  path: /api/atlas/v2/groups/{groupId}/backup/exportBuckets/{exportBucketId}
- description: Update One Export Bucket Private Networking Settings
  method: PATCH
  name: updategroupbackupexportbucket
  path: /api/atlas/v2/groups/{groupId}/backup/exportBuckets/{exportBucketId}
- description: Return Object Storage Private Endpoints for Cloud Backups for One Cloud Provider in One Project
  method: GET
  name: listgroupbackupprivateendpoints
  path: /api/atlas/v2/groups/{groupId}/backup/{cloudProvider}/privateEndpoints
personas: []
provider_name: MongoDB
provider_slug: mongodb
search_terms:
- update one export bucket private networking settings
- return all authorized clusters in all projects
- delete one identity provider
- listeventtypes
- listalertconfigmatcherfieldnames
- creategroupbackupexportbucket
- add entries to project ip access list
- listgroupapikeys
- createfederationsettingidentityprovider
- unassign one organization api key from one project
- acknowledge one alert from one project
- remove one role mapping from one organization
- return all project ip access list entries
- getgroupalertconfig
- return one project by name
- listgroupbackupprivateendpoints
- getfederationsettingidentityprovider
- return pre-filtered activity feed link for one project
- return status of one project ip access list entry
- deletegroupalertconfig
- listgroupaccesslistentries
- getgroupactivityfeed
- cloud database
- api
- create one project
- remove one organization configuration from one federation
- updatefederationsettingconnectedorgconfigrolemap
- delete one federation settings instance
- getgroupawscustomdns
- return one project
- create one snapshot export bucket
- document database
- getgroupbyname
- revoke jwks from one oidc identity provider
- return metadata of one identity provider
- return all alert configurations in one project
- return one role mapping from one organization
- return all identity providers in one federation
- create one alert configuration in one project
- creategroup
- return all alert configuration matchers field names
- updategroupalertconfig
- deletefederationsetting
- revokefederationsettingidentityproviderjwks
- return one alert from one project
- return one project ip access list entry
- return all alerts from one project
- listgroupalertconfigs
- deletegroupaccesslistentry
- return object storage private endpoints for cloud backups for one cloud provider in one project
- createfederationsettingconnectedorgconfigrolemap
- update one identity provider
- return all event types
- deletegroupbackupexportbucket
- return all organization api keys assigned to one project
- return one identity provider by id
- update one alert configuration in one project
- update one role mapping in one organization
- listgroups
- database
- togglegroupawscustomdns
- create and assign one organization api key to one project
- creategroupalertconfig
- updategroupbackupexportbucket
- getgroup
- remove one project
- listfederationsettingconnectedorgconfigrolemappi
- update auditing configuration for one project
- updategroup
- updategroupapikeyroles
- return all open alerts for one alert configuration
- update one project
- updatefederationsettingidentityprovider
- return all alert configurations set for one alert
- getgroupaccesslistentry
- update state of one custom dns configuration for atlas clusters on aws
- addgroupapikey
- getgroupalertalertconfigs
- removefederationsettingconnectedorgconfig
- creategroupaccesslistentry
- getgroupauditlog
- delete one snapshot export bucket
- getgroupaccessliststatus
- nosql
- remove one entry from one project ip access list
- update organization api key roles for one project
- getfederationsettingidentityprovidermetadata
- return one alert configuration from one project
- return all snapshot export buckets
- return one snapshot export bucket
- togglegroupalertconfig
- getgroupalert
- listfederationsettingidentityproviders
- updategroupauditlog
- return the status of this mongodb application
- listgroupbackupexportbuckets
- getgroupbackupexportbucket
- listfederationsettingconnectedorgconfigs
- add one mongodb cloud user to one project
- assign one organization api key to one project
- deletegroup
- update one organization configuration in one federation
- getfederationsettingconnectedorgconfigrolemappin
- addgroupaccessuser
- getfederationsettingconnectedorgconfig
- removegroupapikey
- creategroupapikey
- return all role mappings from one organization
- return all projects
- return one custom dns configuration for atlas clusters on aws
- getsystemstatus
- mongodb
- create one role mapping in one organization configuration
- return one organization configuration from one federation
- updatefederationsettingconnectedorgconfig
- listclusterdetails
- acknowledgegroupalert
- toggle state of one alert configuration in one project
- deletefederationsettingconnectedorgconfigrolemap
- return all organization configurations from one federation
- listgroupalerts
- create one identity provider
- deletefederationsettingidentityprovider
- return auditing configuration for one project
- remove one alert configuration from one project
- getgroupalertconfigalerts
slug: mongodb-capability
source_filename: mongodb-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: MongoDB Atlas Administration API\n  description: The MongoDB Atlas Administration API allows developers to manage all components in MongoDB Atlas. The Atlas\n    Administration API supports OAuth2 Service Accounts and HTTP Digest-based API keys. Service accounts are the recommended\n    authentication method and API keys are considered a legacy option. To authenticate with a Service Account, first exchange\n    its client ID and secret for an access token using the OAuth 2.0 Client Credentials flow. Atlas provides a token endpoint\n    at `POST https://cloud.mongodb.com/api/oauth/token`, which returns a Bearer token that is reusable and valid for 1 hour\n    (3600 s\n  tags:\n  - Mongodb\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: mongodb\n    baseUri: https://cloud.mongodb.com\n    description: MongoDB Atlas Administration API HTTP API.\n    resources:\n    - name:\
  \ api-atlas-v2\n      path: /api/atlas/v2\n      operations:\n      - name: getsystemstatus\n        method: GET\n        description: Return the Status of This MongoDB Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-alertconfigs-matchers-fieldnames\n      path: /api/atlas/v2/alertConfigs/matchers/fieldNames\n      operations:\n      - name: listalertconfigmatcherfieldnames\n        method: GET\n        description: Return All Alert Configuration Matchers Field Names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-clusters\n      path: /api/atlas/v2/clusters\n      operations:\n      - name: listclusterdetails\n        method: GET\n        description: Return All Authorized Clusters in All Projects\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: api-atlas-v2-eventtypes\n      path: /api/atlas/v2/eventTypes\n      operations:\n      - name: listeventtypes\n        method: GET\n        description: Return All Event Types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-federationsettings-federationsettin\n      path: /api/atlas/v2/federationSettings/{federationSettingsId}\n      operations:\n      - name: deletefederationsetting\n        method: DELETE\n        description: Delete One Federation Settings Instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-federationsettings-federationsettin\n      path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs\n      operations:\n      - name: listfederationsettingconnectedorgconfigs\n\
  \        method: GET\n        description: Return All Organization Configurations from One Federation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-federationsettings-federationsettin\n      path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}\n      operations:\n      - name: removefederationsettingconnectedorgconfig\n        method: DELETE\n        description: Remove One Organization Configuration from One Federation\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the connected organization configuration to remove.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getfederationsettingconnectedorgconfig\n   \
  \     method: GET\n        description: Return One Organization Configuration from One Federation\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the connected organization configuration to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefederationsettingconnectedorgconfig\n        method: PATCH\n        description: Update One Organization Configuration in One Federation\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the connected organization configuration to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: api-atlas-v2-federationsettings-federationsettin\n      path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}/roleMappings\n      operations:\n      - name: listfederationsettingconnectedorgconfigrolemappi\n        method: GET\n        description: Return All Role Mappings from One Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfederationsettingconnectedorgconfigrolemap\n        method: POST\n        description: Create One Role Mapping in One Organization Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-federationsettings-federationsettin\n      path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}/roleMappings/{id}\n      operations:\n      - name: deletefederationsettingconnectedorgconfigrolemap\n\
  \        method: DELETE\n        description: Remove One Role Mapping from One Organization\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the role mapping that you want to remove.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getfederationsettingconnectedorgconfigrolemappin\n        method: GET\n        description: Return One Role Mapping from One Organization\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the role mapping that you want to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefederationsettingconnectedorgconfigrolemap\n\
  \        method: PUT\n        description: Update One Role Mapping in One Organization\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the role mapping that you want to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-federationsettings-federationsettin\n      path: /api/atlas/v2/federationSettings/{federationSettingsId}/identityProviders\n      operations:\n      - name: listfederationsettingidentityproviders\n        method: GET\n        description: Return All Identity Providers in One Federation\n        inputParameters:\n        - name: protocol\n          in: query\n          type: array\n          description: The protocols of the target identity providers.\n        - name: idpType\n          in: query\n          type: array\n \
  \         description: The types of the target identity providers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfederationsettingidentityprovider\n        method: POST\n        description: Create One Identity Provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-federationsettings-federationsettin\n      path: /api/atlas/v2/federationSettings/{federationSettingsId}/identityProviders/{identityProviderId}\n      operations:\n      - name: deletefederationsettingidentityprovider\n        method: DELETE\n        description: Delete One Identity Provider\n        inputParameters:\n        - name: identityProviderId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the identity provider to\
  \ connect.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getfederationsettingidentityprovider\n        method: GET\n        description: Return One Identity Provider by ID\n        inputParameters:\n        - name: identityProviderId\n          in: path\n          type: string\n          required: true\n          description: Unique string that identifies the identity provider to connect. If using an API version before 11-15-2023,\n            use the legacy 20-hexadecimal digit id. This id can b\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefederationsettingidentityprovider\n        method: PATCH\n        description: Update One Identity Provider\n        inputParameters:\n        - name: identityProviderId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Unique string that identifies the identity provider to connect. If using an API version before 11-15-2023,\n            use the legacy 20-hexadecimal digit id. This id can b\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-federationsettings-federationsettin\n      path: /api/atlas/v2/federationSettings/{federationSettingsId}/identityProviders/{identityProviderId}/jwks\n      operations:\n      - name: revokefederationsettingidentityproviderjwks\n        method: DELETE\n        description: Revoke JWKS from One OIDC Identity Provider\n        inputParameters:\n        - name: identityProviderId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the identity provider to connect.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: api-atlas-v2-federationsettings-federationsettin\n      path: /api/atlas/v2/federationSettings/{federationSettingsId}/identityProviders/{identityProviderId}/metadata.xml\n      operations:\n      - name: getfederationsettingidentityprovidermetadata\n        method: GET\n        description: Return Metadata of One Identity Provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups\n      path: /api/atlas/v2/groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: Return All Projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: Create One Project\n        inputParameters:\n        - name: projectOwnerId\n          in: query\n          type: string\n          description:\
  \ Unique 24-hexadecimal digit string that identifies the MongoDB Cloud user to whom to grant the Project\n            Owner role on the specified project. If you set this para\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-byname-groupname\n      path: /api/atlas/v2/groups/byName/{groupName}\n      operations:\n      - name: getgroupbyname\n        method: GET\n        description: Return One Project by Name\n        inputParameters:\n        - name: groupName\n          in: path\n          type: string\n          required: true\n          description: Human-readable label that identifies this project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid\n      path: /api/atlas/v2/groups/{groupId}\n      operations:\n      - name: deletegroup\n        method: DELETE\n\
  \        description: Remove One Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getgroup\n        method: GET\n        description: Return One Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroup\n        method: PATCH\n        description: Update One Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-access\n      path: /api/atlas/v2/groups/{groupId}/access\n      operations:\n      - name: addgroupaccessuser\n        method: POST\n        description: Add One MongoDB Cloud User to One Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-accesslist\n\
  \      path: /api/atlas/v2/groups/{groupId}/accessList\n      operations:\n      - name: listgroupaccesslistentries\n        method: GET\n        description: Return All Project IP Access List Entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroupaccesslistentry\n        method: POST\n        description: Add Entries to Project IP Access List\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-accesslist-entryvalu\n      path: /api/atlas/v2/groups/{groupId}/accessList/{entryValue}\n      operations:\n      - name: deletegroupaccesslistentry\n        method: DELETE\n        description: Remove One Entry from One Project IP Access List\n        inputParameters:\n        - name: entryValue\n          in: path\n          type: string\n          required: true\n         \
  \ description: 'Access list entry that you want to remove from the project''s IP access list. This value can use one\n            of the following: one AWS security group ID, one IP address,'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getgroupaccesslistentry\n        method: GET\n        description: Return One Project IP Access List Entry\n        inputParameters:\n        - name: entryValue\n          in: path\n          type: string\n          required: true\n          description: 'Access list entry that you want to return from the project''s IP access list. This value can use one\n            of the following: one AWS security group ID, one IP address,'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-accesslist-entryvalu\n      path: /api/atlas/v2/groups/{groupId}/accessList/{entryValue}/status\n\
  \      operations:\n      - name: getgroupaccessliststatus\n        method: GET\n        description: Return Status of One Project IP Access List Entry\n        inputParameters:\n        - name: entryValue\n          in: path\n          type: string\n          required: true\n          description: Network address or cloud provider security construct that identifies which project access list entry\n            to be verified.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-activityfeed\n      path: /api/atlas/v2/groups/{groupId}/activityFeed\n      operations:\n      - name: getgroupactivityfeed\n        method: GET\n        description: Return Pre-Filtered Activity Feed Link for One Project\n        inputParameters:\n        - name: eventType\n          in: query\n          type: array\n          description: 'Category of incident recorded at this moment in time. **IMPORTANT**:\
  \ The complete list of event type\n            values changes frequently.'\n        - name: maxDate\n          in: query\n          type: string\n          description: End date and time for events to include in the activity feed link. ISO 8601 timestamp format in UTC.\n        - name: minDate\n          in: query\n          type: string\n          description: Start date and time for events to include in the activity feed link. ISO 8601 timestamp format in UTC.\n        - name: clusterName\n          in: query\n          type: array\n          description: Human-readable label that identifies the cluster.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-alertconfigs\n      path: /api/atlas/v2/groups/{groupId}/alertConfigs\n      operations:\n      - name: listgroupalertconfigs\n        method: GET\n        description: Return All Alert Configurations in One Project\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroupalertconfig\n        method: POST\n        description: Create One Alert Configuration in One Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-alertconfigs-alertco\n      path: /api/atlas/v2/groups/{groupId}/alertConfigs/{alertConfigId}\n      operations:\n      - name: deletegroupalertconfig\n        method: DELETE\n        description: Remove One Alert Configuration from One Project\n        inputParameters:\n        - name: alertConfigId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the alert configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: getgroupalertconfig\n        method: GET\n        description: Return One Alert Configuration from One Project\n        inputParameters:\n        - name: alertConfigId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the alert configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: togglegroupalertconfig\n        method: PATCH\n        description: Toggle State of One Alert Configuration in One Project\n        inputParameters:\n        - name: alertConfigId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the alert configuration that triggered this alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: updategroupalertconfig\n        method: PUT\n        description: Update One Alert Configuration in One Project\n        inputParameters:\n        - name: alertConfigId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the alert configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-alertconfigs-alertco\n      path: /api/atlas/v2/groups/{groupId}/alertConfigs/{alertConfigId}/alerts\n      operations:\n      - name: getgroupalertconfigalerts\n        method: GET\n        description: Return All Open Alerts for One Alert Configuration\n        inputParameters:\n        - name: alertConfigId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies\
  \ the alert configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-alerts\n      path: /api/atlas/v2/groups/{groupId}/alerts\n      operations:\n      - name: listgroupalerts\n        method: GET\n        description: Return All Alerts from One Project\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Status of the alerts to return. Omit this parameter to return all alerts in all statuses. TRACKING\n            indicates the alert condition exists but has not persisted fo\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-alerts-alertid\n      path: /api/atlas/v2/groups/{groupId}/alerts/{alertId}\n      operations:\n      - name: getgroupalert\n        method: GET\n        description:\
  \ Return One Alert from One Project\n        inputParameters:\n        - name: alertId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: acknowledgegroupalert\n        method: PATCH\n        description: Acknowledge One Alert from One Project\n        inputParameters:\n        - name: alertId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-alerts-alertid-alert\n      path: /api/atlas/v2/groups/{groupId}/alerts/{alertId}/alertConfigs\n      operations:\n      - name: getgroupalertalertconfigs\n\
  \        method: GET\n        description: Return All Alert Configurations Set for One Alert\n        inputParameters:\n        - name: alertId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies the alert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-apikeys\n      path: /api/atlas/v2/groups/{groupId}/apiKeys\n      operations:\n      - name: listgroupapikeys\n        method: GET\n        description: Return All Organization API Keys Assigned to One Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroupapikey\n        method: POST\n        description: Create and Assign One Organization API Key to One Project\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-apikeys-apiuserid\n      path: /api/atlas/v2/groups/{groupId}/apiKeys/{apiUserId}\n      operations:\n      - name: removegroupapikey\n        method: DELETE\n        description: Unassign One Organization API Key from One Project\n        inputParameters:\n        - name: apiUserId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies this organization API key that you want to unassign\n            from one project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroupapikeyroles\n        method: PATCH\n        description: Update Organization API Key Roles for One Project\n        inputParameters:\n        - name: apiUserId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Unique 24-hexadecimal digit string that identifies this organization API key that you want to unassign\n            from one project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addgroupapikey\n        method: POST\n        description: Assign One Organization API Key to One Project\n        inputParameters:\n        - name: apiUserId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal digit string that identifies this organization API key that you want to assign\n            to one project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-auditlog\n      path: /api/atlas/v2/groups/{groupId}/auditLog\n      operations:\n      - name: getgroupauditlog\n        method: GET\n      \
  \  description: Return Auditing Configuration for One Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroupauditlog\n        method: PATCH\n        description: Update Auditing Configuration for One Project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-awscustomdns\n      path: /api/atlas/v2/groups/{groupId}/awsCustomDNS\n      operations:\n      - name: getgroupawscustomdns\n        method: GET\n        description: Return One Custom DNS Configuration for Atlas Clusters on AWS\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: togglegroupawscustomdns\n        method: PATCH\n        description: Update State of One Custom DNS Configuration for Atlas Clusters on AWS\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-backup-exportbuckets\n      path: /api/atlas/v2/groups/{groupId}/backup/exportBuckets\n      operations:\n      - name: listgroupbackupexportbuckets\n        method: GET\n        description: Return All Snapshot Export Buckets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroupbackupexportbucket\n        method: POST\n        description: Create One Snapshot Export Bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-backup-exportbuckets\n      path: /api/atlas/v2/groups/{groupId}/backup/exportBuckets/{exportBucketId}\n      operations:\n      - name: deletegroupbackupexportbucket\n        method: DELETE\n\
  \        description: Delete One Snapshot Export Bucket\n        inputParameters:\n        - name: exportBucketId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal character string that identifies the Export Bucket.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getgroupbackupexportbucket\n        method: GET\n        description: Return One Snapshot Export Bucket\n        inputParameters:\n        - name: exportBucketId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal character string that identifies the Export Bucket.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroupbackupexportbucket\n        method: PATCH\n        description: Update One Export Bucket Private\
  \ Networking Settings\n        inputParameters:\n        - name: exportBucketId\n          in: path\n          type: string\n          required: true\n          description: Unique 24-hexadecimal character string that identifies the snapshot export bucket.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-atlas-v2-groups-groupid-backup-cloudprovider\n      path: /api/atlas/v2/groups/{groupId}/backup/{cloudProvider}/privateEndpoints\n      operations:\n      - name: listgroupbackupprivateendpoints\n        method: GET\n        description: Return Object Storage Private Endpoints for Cloud Backups for One Cloud Provider in One Project\n        inputParameters:\n        - name: cloudProvider\n          in: path\n          type: string\n          required: true\n          description: Human-readable label that identifies the cloud provider for the private endpoints to return.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mongodb-rest\n    description: REST adapter for MongoDB Atlas Administration API.\n    resources:\n    - path: /api/atlas/v2\n      name: getsystemstatus\n      operations:\n      - method: GET\n        name: getsystemstatus\n        description: Return the Status of This MongoDB Application\n        call: mongodb.getsystemstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/atlas/v2/alertConfigs/matchers/fieldNames\n      name: listalertconfigmatcherfieldnames\n      operations:\n      - method: GET\n        name: listalertconfigmatcherfieldnames\n        description: Return All Alert Configuration Matchers Field Names\n        call: mongodb.listalertconfigmatcherfieldnames\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/atlas/v2/clusters\n\
  \      name: listclusterdetails\n      operations:\n      - method: GET\n        name: listclusterdetails\n        description: Return All Authorized Clusters in All Projects\n        call: mongodb.listclusterdetails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/atlas/v2/eventTypes\n      name: listeventtypes\n      operations:\n      - method: GET\n        name: listeventtypes\n        description: Return All Event Types\n        call: mongodb.listeventtypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/atlas/v2/federationSettings/{federationSettingsId}\n      name: deletefederationsetting\n      operations:\n      - method: DELETE\n        name: deletefederationsetting\n        description: Delete One Federation Settings Instance\n        call: mongodb.deletefederationsetting\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs\n\
  \      name: listfederationsettingconnectedorgconfigs\n      operations:\n      - method: GET\n        name: listfederationsettingconnectedorgconfigs\n        description: Return All Organization Configurations from One Federation\n        call: mongodb.listfederationsettingconnectedorgconfigs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}\n      name: removefederationsettingconnectedorgconfig\n      operations:\n      - method: DELETE\n        name: removefederationsettingconnectedorgconfig\n        description: Remove One Organization Configuration from One Federation\n        call: mongodb.removefederationsettingconnectedorgconfig\n        with:\n          orgId: rest.orgId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}\n      name: getfederationsettingconnectedorgconfig\n\
  \      operations:\n      - method: GET\n        name: getfederationsettingconnectedorgconfig\n        description: Return One Organization Configuration from One Federation\n        call: mongodb.getfederationsettingconnectedorgconfig\n        with:\n          orgId: rest.orgId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/atlas/v2/federationSettings/{federationSettingsId}/connectedOrgConfigs/{orgId}\n      name: upda\n\n# --- truncated at 32 KB (79 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/mongodb/refs/heads/main/capabilities/mongodb-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mongodb/refs/heads/main/capabilities/mongodb-capability.yaml
tags:
- Mongodb
- API
tools:
- description: Return the Status of This MongoDB Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsystemstatus
- description: Return All Alert Configuration Matchers Field Names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalertconfigmatcherfieldnames
- description: Return All Authorized Clusters in All Projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusterdetails
- description: Return All Event Types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listeventtypes
- description: Delete One Federation Settings Instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefederationsetting
- description: Return All Organization Configurations from One Federation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfederationsettingconnectedorgconfigs
- description: Remove One Organization Configuration from One Federation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removefederationsettingconnectedorgconfig
- description: Return One Organization Configuration from One Federation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfederationsettingconnectedorgconfig
- description: Update One Organization Configuration in One Federation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatefederationsettingconnectedorgconfig
- description: Return All Role Mappings from One Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfederationsettingconnectedorgconfigrolemappi
- description: Create One Role Mapping in One Organization Configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfederationsettingconnectedorgconfigrolemap
- description: Remove One Role Mapping from One Organization
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefederationsettingconnectedorgconfigrolemap
- description: Return One Role Mapping from One Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfederationsettingconnectedorgconfigrolemappin
- description: Update One Role Mapping in One Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatefederationsettingconnectedorgconfigrolemap
- description: Return All Identity Providers in One Federation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfederationsettingidentityproviders
- description: Create One Identity Provider
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfederationsettingidentityprovider
- description: Delete One Identity Provider
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefederationsettingidentityprovider
- description: Return One Identity Provider by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfederationsettingidentityprovider
- description: Update One Identity Provider
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatefederationsettingidentityprovider
- description: Revoke JWKS from One OIDC Identity Provider
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revokefederationsettingidentityproviderjwks
- description: Return Metadata of One Identity Provider
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfederationsettingidentityprovidermetadata
- description: Return All Projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: Create One Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: Return One Project by Name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupbyname
- description: Remove One Project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: Return One Project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: Update One Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updategroup
- description: Add One MongoDB Cloud User to One Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addgroupaccessuser
- description: Return All Project IP Access List Entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroupaccesslistentries
- description: Add Entries to Project IP Access List
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroupaccesslistentry
- description: Remove One Entry from One Project IP Access List
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroupaccesslistentry
- description: Return One Project IP Access List Entry
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupaccesslistentry
- description: Return Status of One Project IP Access List Entry
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupaccessliststatus
- description: Return Pre-Filtered Activity Feed Link for One Project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupactivityfeed
- description: Return All Alert Configurations in One Project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroupalertconfigs
- description: Create One Alert Configuration in One Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroupalertconfig
- description: Remove One Alert Configuration from One Project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroupalertconfig
- description: Return One Alert Configuration from One Project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupalertconfig
- description: Toggle State of One Alert Configuration in One Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: togglegroupalertconfig
- description: Update One Alert Configuration in One Project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updategroupalertconfig
- description: Return All Open Alerts for One Alert Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupalertconfigalerts
- description: Return All Alerts from One Project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroupalerts
- description: Return One Alert from One Project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupalert
- description: Acknowledge One Alert from One Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: acknowledgegroupalert
- description: Return All Alert Configurations Set for One Alert
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupalertalertconfigs
- description: Return All Organization API Keys Assigned to One Project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroupapikeys
- description: Create and Assign One Organization API Key to One Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroupapikey
- description: Unassign One Organization API Key from One Project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removegroupapikey
- description: Update Organization API Key Roles for One Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updategroupapikeyroles
- description: Assign One Organization API Key to One Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addgroupapikey
- description: Return Auditing Configuration for One Project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupauditlog
- description: Update Auditing Configuration for One Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updategroupauditlog
- description: Return One Custom DNS Configuration for Atlas Clusters on AWS
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupawscustomdns
- description: Update State of One Custom DNS Configuration for Atlas Clusters on AWS
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: togglegroupawscustomdns
- description: Return All Snapshot Export Buckets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroupbackupexportbuckets
- description: Create One Snapshot Export Bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroupbackupexportbucket
- description: Delete One Snapshot Export Bucket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroupbackupexportbucket
- description: Return One Snapshot Export Bucket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupbackupexportbucket
- description: Update One Export Bucket Private Networking Settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updategroupbackupexportbucket
- description: Return Object Storage Private Endpoints for Cloud Backups for One Cloud Provider in One Project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroupbackupprivateendpoints
---
