---
categories: []
consumed_apis: []
description: '- Qovery is the fastest way to deploy your full-stack apps on any Cloud provider. - ℹ️ The API is stable and still in development.'
layout: capability
name: Qovery API
operations:
- description: List user organizations
  method: GET
  name: listorganization
  path: /organization
- description: Create an organization
  method: POST
  name: createorganization
  path: /organization
- description: Get organization by ID
  method: GET
  name: getorganization
  path: /organization/{organizationId}
- description: Edit an organization
  method: PUT
  name: editorganization
  path: /organization/{organizationId}
- description: Delete an organization
  method: DELETE
  name: deleteorganization
  path: /organization/{organizationId}
- description: List organization api tokens
  method: GET
  name: listorganizationapitokens
  path: /organization/{organizationId}/apiToken
- description: Create an organization api token
  method: POST
  name: createorganizationapitoken
  path: /organization/{organizationId}/apiToken
- description: Delete organization api token
  method: DELETE
  name: deleteorganizationapitoken
  path: /organization/{organizationId}/apiToken/{apiTokenId}
- description: List organization available roles
  method: GET
  name: listorganizationavailableroles
  path: /organization/{organizationId}/availableRole
- description: List organization git tokens
  method: GET
  name: listorganizationgittokens
  path: /organization/{organizationId}/gitToken
- description: Create a git token
  method: POST
  name: creategittoken
  path: /organization/{organizationId}/gitToken
- description: Get organization git token
  method: GET
  name: getorganizationgittoken
  path: /organization/{organizationId}/gitToken/{gitTokenId}
- description: Edit a git token
  method: PUT
  name: editgittoken
  path: /organization/{organizationId}/gitToken/{gitTokenId}
- description: Delete a git token
  method: DELETE
  name: deletegittoken
  path: /organization/{organizationId}/gitToken/{gitTokenId}
- description: Get organization git token associated services
  method: GET
  name: getgittokenassociatedservices
  path: /organization/{organizationId}/gitToken/{gitTokenId}/associatedServices
- description: List directories from a git repository
  method: POST
  name: listdirectoriesfromgitrepository
  path: /organization/{organizationId}/listDirectoriesFromGitRepository
- description: Get organization members
  method: GET
  name: getorganizationmembers
  path: /organization/{organizationId}/member
- description: Edit an organization member role
  method: PUT
  name: editorganizationmemberrole
  path: /organization/{organizationId}/member
- description: Remove a member
  method: DELETE
  name: deletemember
  path: /organization/{organizationId}/member
- description: Get invited members
  method: GET
  name: getorganizationinvitedmembers
  path: /organization/{organizationId}/inviteMember
- description: Invite someone in the organization
  method: POST
  name: postinvitemember
  path: /organization/{organizationId}/inviteMember
- description: Get member invitation
  method: GET
  name: getmemberinvitation
  path: /organization/{organizationId}/inviteMember/{inviteId}
- description: Accept Invite in the organization
  method: POST
  name: postacceptinvitemember
  path: /organization/{organizationId}/inviteMember/{inviteId}
- description: Remove an invited member
  method: DELETE
  name: deleteinvitemember
  path: /organization/{organizationId}/inviteMember/{inviteId}
- description: Transfer organization ownership to another user
  method: POST
  name: postorganizationtransferownership
  path: /organization/{organizationId}/transferOwnership
- description: Get organization current cost
  method: GET
  name: getorganizationcurrentcost
  path: /organization/{organizationId}/currentCost
- description: Add credit code
  method: POST
  name: addcreditcode
  path: /organization/{organizationId}/creditCode
- description: Change organization plan
  method: POST
  name: changeplan
  path: /organization/{organizationId}/changePlan
- description: Get cluster current cost
  method: GET
  name: getclustercurrentcost
  path: /organization/{organizationId}/cluster/{clusterId}/currentCost
- description: Get organization billing info
  method: GET
  name: getorganizationbillinginfo
  path: /organization/{organizationId}/billingInfo
- description: Edit Organization Billing Info
  method: PUT
  name: editorganizationbillinginfo
  path: /organization/{organizationId}/billingInfo
- description: Get organization billing status
  method: GET
  name: getorganizationbillingstatus
  path: /organization/{organizationId}/billingStatus
- description: Generate organization billing usage report
  method: POST
  name: generatebillingusagereport
  path: /organization/{organizationId}/billingUsageReport
- description: Get organization billing external ID
  method: GET
  name: getorganizationbillingexternalid
  path: /organization/{organizationId}/billingExternalId
- description: List organization invoices
  method: GET
  name: listorganizationinvoice
  path: /organization/{organizationId}/invoice
- description: Get organization invoice
  method: GET
  name: getorganizationinvoice
  path: /organization/{organizationId}/invoice/{invoiceId}
- description: Get invoice link
  method: GET
  name: getorganizationinvoicepdf
  path: /organization/{organizationId}/invoice/{invoiceId}/download
- description: Download all invoices
  method: POST
  name: organizationdownloadallinvoices
  path: /organization/{organizationId}/downloadInvoices
- description: List organization credit cards
  method: GET
  name: listorganizationcreditcards
  path: /organization/{organizationId}/creditCard
- description: Add credit card
  method: POST
  name: addcreditcard
  path: /organization/{organizationId}/creditCard
- description: Delete credit card
  method: DELETE
  name: deletecreditcard
  path: /organization/{organizationId}/creditCard/{creditCardId}
- description: List projects
  method: GET
  name: listproject
  path: /organization/{organizationId}/project
- description: Create a project
  method: POST
  name: createproject
  path: /organization/{organizationId}/project
- description: List total number of services and environments for each project of the organization
  method: GET
  name: getorganizationprojectstats
  path: /organization/{organizationId}/project/stats
- description: List organization clusters
  method: GET
  name: listorganizationcluster
  path: /organization/{organizationId}/cluster
- description: Create a cluster
  method: POST
  name: createcluster
  path: /organization/{organizationId}/cluster
- description: List all clusters statuses
  method: GET
  name: getorganizationclusterstatus
  path: /organization/{organizationId}/cluster/status
- description: Delete a cluster
  method: DELETE
  name: deletecluster
  path: /organization/{organizationId}/cluster/{clusterId}
- description: Edit a cluster
  method: PUT
  name: editcluster
  path: /organization/{organizationId}/cluster/{clusterId}
- description: Get cluster status
  method: GET
  name: getclusterstatus
  path: /organization/{organizationId}/cluster/{clusterId}/status
- description: Get cluster helm values for self managed installation
  method: GET
  name: getinstallationhelmvalues
  path: /organization/{organizationId}/cluster/{clusterId}/installationHelmValues
- description: Get cluster kubeconfig
  method: GET
  name: getclusterkubeconfig
  path: /organization/{organizationId}/cluster/{clusterId}/kubeconfig
- description: Edit cluster kubeconfig
  method: PUT
  name: editclusterkubeconfig
  path: /organization/{organizationId}/cluster/{clusterId}/kubeconfig
- description: Get advanced settings
  method: GET
  name: getclusteradvancedsettings
  path: /organization/{organizationId}/cluster/{clusterId}/advancedSettings
- description: Edit advanced settings
  method: PUT
  name: editclusteradvancedsettings
  path: /organization/{organizationId}/cluster/{clusterId}/advancedSettings
- description: Get routing table
  method: GET
  name: getroutingtable
  path: /organization/{organizationId}/cluster/{clusterId}/routingTable
- description: Edit routing table
  method: PUT
  name: editroutingtable
  path: /organization/{organizationId}/cluster/{clusterId}/routingTable
- description: List Cluster Logs
  method: GET
  name: listclusterlogs
  path: /organization/{organizationId}/cluster/{clusterId}/logs
- description: List AWS credentials
  method: GET
  name: listawscredentials
  path: /organization/{organizationId}/aws/credentials
- description: Create AWS credentials set
  method: POST
  name: createawscredentials
  path: /organization/{organizationId}/aws/credentials
personas: []
provider_name: Qovery
provider_slug: qovery
search_terms:
- developer experience
- edit a cluster
- editcluster
- listorganization
- editorganizationbillinginfo
- addcreditcode
- api
- listorganizationcreditcards
- delete a git token
- list all clusters statuses
- list organization api tokens
- get advanced settings
- list cluster logs
- getinstallationhelmvalues
- delete credit card
- invite someone in the organization
- get cluster current cost
- create a cluster
- getorganizationgittoken
- editclusteradvancedsettings
- deleteinvitemember
- postorganizationtransferownership
- getorganizationmembers
- get member invitation
- get organization git token associated services
- getorganization
- get routing table
- edit advanced settings
- change organization plan
- create an organization api token
- create a project
- edit an organization member role
- edit routing table
- list aws credentials
- accept invite in the organization
- list directories from a git repository
- get organization invoice
- list projects
- remove an invited member
- deletecreditcard
- getroutingtable
- list organization available roles
- download all invoices
- generate organization billing usage report
- getorganizationprojectstats
- create aws credentials set
- listorganizationgittokens
- get organization billing external id
- internal developer platform
- creategittoken
- getclusterstatus
- getgittokenassociatedservices
- add credit code
- get organization current cost
- deletemember
- deletegittoken
- get organization billing status
- list organization clusters
- getorganizationbillingexternalid
- get cluster helm values for self managed installation
- get invited members
- getorganizationcurrentcost
- delete an organization
- cloud deployment
- addcreditcard
- organizationdownloadallinvoices
- createorganization
- delete organization api token
- transfer organization ownership to another user
- editclusterkubeconfig
- listorganizationapitokens
- createcluster
- getorganizationclusterstatus
- createawscredentials
- create a git token
- edit a git token
- get invoice link
- get organization members
- listproject
- delete a cluster
- listawscredentials
- create an organization
- get cluster status
- listorganizationavailableroles
- listdirectoriesfromgitrepository
- list user organizations
- getorganizationinvitedmembers
- changeplan
- get organization billing info
- getorganizationinvoicepdf
- getorganizationbillinginfo
- listorganizationcluster
- list organization git tokens
- listclusterlogs
- deleteorganization
- createproject
- getmemberinvitation
- deletecluster
- generatebillingusagereport
- add credit card
- createorganizationapitoken
- editorganization
- getclustercurrentcost
- editorganizationmemberrole
- list organization invoices
- listorganizationinvoice
- get cluster kubeconfig
- edit organization billing info
- qovery
- get organization git token
- remove a member
- postacceptinvitemember
- edit an organization
- edit cluster kubeconfig
- editgittoken
- list total number of services and environments for each project of the organization
- getclusteradvancedsettings
- editroutingtable
- getclusterkubeconfig
- postinvitemember
- getorganizationinvoice
- get organization by id
- getorganizationbillingstatus
- list organization credit cards
- deleteorganizationapitoken
slug: qovery-capability
source_filename: qovery-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Qovery API\n  description: '- Qovery is the fastest way to deploy your full-stack apps on any Cloud provider. - ℹ️ The API is stable and\n    still in development.'\n  tags:\n  - Qovery\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: qovery\n    baseUri: https://api.qovery.com\n    description: Qovery API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{QOVERY_TOKEN}}'\n    resources:\n    - name: organization\n      path: /organization\n      operations:\n      - name: listorganization\n        method: GET\n        description: List user organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorganization\n        method: POST\n        description: Create an organization\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: organization-organizationid\n      path: /organization/{organizationId}\n      operations:\n      - name: getorganization\n        method: GET\n        description: Get organization by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editorganization\n        method: PUT\n        description: Edit an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteorganization\n        method: DELETE\n        description: Delete an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-apitoken\n      path: /organization/{organizationId}/apiToken\n      operations:\n      - name: listorganizationapitokens\n\
  \        method: GET\n        description: List organization api tokens\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Name of the token to filter results by.\n        - name: creatorName\n          in: query\n          type: string\n          description: Name of the token creator to filter results by.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorganizationapitoken\n        method: POST\n        description: Create an organization api token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-apitoken-apitokenid\n      path: /organization/{organizationId}/apiToken/{apiTokenId}\n      operations:\n      - name: deleteorganizationapitoken\n        method: DELETE\n        description: Delete organization\
  \ api token\n        inputParameters:\n        - name: apiTokenId\n          in: path\n          type: string\n          required: true\n          description: Organization Api Token ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-availablerole\n      path: /organization/{organizationId}/availableRole\n      operations:\n      - name: listorganizationavailableroles\n        method: GET\n        description: List organization available roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-gittoken\n      path: /organization/{organizationId}/gitToken\n      operations:\n      - name: listorganizationgittokens\n        method: GET\n        description: List organization git tokens\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: creategittoken\n        method: POST\n        description: Create a git token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-gittoken-gittokenid\n      path: /organization/{organizationId}/gitToken/{gitTokenId}\n      operations:\n      - name: getorganizationgittoken\n        method: GET\n        description: Get organization git token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editgittoken\n        method: PUT\n        description: Edit a git token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegittoken\n        method: DELETE\n        description: Delete a git token\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-gittoken-gittokenid-\n      path: /organization/{organizationId}/gitToken/{gitTokenId}/associatedServices\n      operations:\n      - name: getgittokenassociatedservices\n        method: GET\n        description: Get organization git token associated services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-listdirectoriesfromg\n      path: /organization/{organizationId}/listDirectoriesFromGitRepository\n      operations:\n      - name: listdirectoriesfromgitrepository\n        method: POST\n        description: List directories from a git repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-member\n      path:\
  \ /organization/{organizationId}/member\n      operations:\n      - name: getorganizationmembers\n        method: GET\n        description: Get organization members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editorganizationmemberrole\n        method: PUT\n        description: Edit an organization member role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemember\n        method: DELETE\n        description: Remove a member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-invitemember\n      path: /organization/{organizationId}/inviteMember\n      operations:\n      - name: getorganizationinvitedmembers\n        method: GET\n        description: Get invited members\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postinvitemember\n        method: POST\n        description: Invite someone in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-invitemember-invitei\n      path: /organization/{organizationId}/inviteMember/{inviteId}\n      operations:\n      - name: getmemberinvitation\n        method: GET\n        description: Get member invitation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postacceptinvitemember\n        method: POST\n        description: Accept Invite in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinvitemember\n\
  \        method: DELETE\n        description: Remove an invited member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-transferownership\n      path: /organization/{organizationId}/transferOwnership\n      operations:\n      - name: postorganizationtransferownership\n        method: POST\n        description: Transfer organization ownership to another user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-currentcost\n      path: /organization/{organizationId}/currentCost\n      operations:\n      - name: getorganizationcurrentcost\n        method: GET\n        description: Get organization current cost\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-creditcode\n\
  \      path: /organization/{organizationId}/creditCode\n      operations:\n      - name: addcreditcode\n        method: POST\n        description: Add credit code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-changeplan\n      path: /organization/{organizationId}/changePlan\n      operations:\n      - name: changeplan\n        method: POST\n        description: Change organization plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-cluster-clusterid-cu\n      path: /organization/{organizationId}/cluster/{clusterId}/currentCost\n      operations:\n      - name: getclustercurrentcost\n        method: GET\n        description: Get cluster current cost\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: organization-organizationid-billinginfo\n      path: /organization/{organizationId}/billingInfo\n      operations:\n      - name: getorganizationbillinginfo\n        method: GET\n        description: Get organization billing info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editorganizationbillinginfo\n        method: PUT\n        description: Edit Organization Billing Info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-billingstatus\n      path: /organization/{organizationId}/billingStatus\n      operations:\n      - name: getorganizationbillingstatus\n        method: GET\n        description: Get organization billing status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n    - name: organization-organizationid-billingusagereport\n      path: /organization/{organizationId}/billingUsageReport\n      operations:\n      - name: generatebillingusagereport\n        method: POST\n        description: Generate organization billing usage report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-billingexternalid\n      path: /organization/{organizationId}/billingExternalId\n      operations:\n      - name: getorganizationbillingexternalid\n        method: GET\n        description: Get organization billing external ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-invoice\n      path: /organization/{organizationId}/invoice\n      operations:\n      - name: listorganizationinvoice\n        method: GET\n        description:\
  \ List organization invoices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-invoice-invoiceid\n      path: /organization/{organizationId}/invoice/{invoiceId}\n      operations:\n      - name: getorganizationinvoice\n        method: GET\n        description: Get organization invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-invoice-invoiceid-do\n      path: /organization/{organizationId}/invoice/{invoiceId}/download\n      operations:\n      - name: getorganizationinvoicepdf\n        method: GET\n        description: Get invoice link\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-downloadinvoices\n      path: /organization/{organizationId}/downloadInvoices\n\
  \      operations:\n      - name: organizationdownloadallinvoices\n        method: POST\n        description: Download all invoices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-creditcard\n      path: /organization/{organizationId}/creditCard\n      operations:\n      - name: listorganizationcreditcards\n        method: GET\n        description: List organization credit cards\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addcreditcard\n        method: POST\n        description: Add credit card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-creditcard-creditcar\n      path: /organization/{organizationId}/creditCard/{creditCardId}\n      operations:\n  \
  \    - name: deletecreditcard\n        method: DELETE\n        description: Delete credit card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-project\n      path: /organization/{organizationId}/project\n      operations:\n      - name: listproject\n        method: GET\n        description: List projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Create a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-project-stats\n      path: /organization/{organizationId}/project/stats\n      operations:\n      - name: getorganizationprojectstats\n        method: GET\n        description: List total number\
  \ of services and environments for each project of the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-cluster\n      path: /organization/{organizationId}/cluster\n      operations:\n      - name: listorganizationcluster\n        method: GET\n        description: List organization clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcluster\n        method: POST\n        description: Create a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-cluster-status\n      path: /organization/{organizationId}/cluster/status\n      operations:\n      - name: getorganizationclusterstatus\n        method: GET\n        description: List all clusters\
  \ statuses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-cluster-clusterid\n      path: /organization/{organizationId}/cluster/{clusterId}\n      operations:\n      - name: deletecluster\n        method: DELETE\n        description: Delete a cluster\n        inputParameters:\n        - name: deleteMode\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editcluster\n        method: PUT\n        description: Edit a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-cluster-clusterid-st\n      path: /organization/{organizationId}/cluster/{clusterId}/status\n      operations:\n      - name: getclusterstatus\n    \
  \    method: GET\n        description: Get cluster status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-cluster-clusterid-in\n      path: /organization/{organizationId}/cluster/{clusterId}/installationHelmValues\n      operations:\n      - name: getinstallationhelmvalues\n        method: GET\n        description: Get cluster helm values for self managed installation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-cluster-clusterid-ku\n      path: /organization/{organizationId}/cluster/{clusterId}/kubeconfig\n      operations:\n      - name: getclusterkubeconfig\n        method: GET\n        description: Get cluster kubeconfig\n        inputParameters:\n        - name: with_token_from_cli\n          in: query\n          type: boolean\n          description:\
  \ If true, the user auth part will have an exec command with qovery cli\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editclusterkubeconfig\n        method: PUT\n        description: Edit cluster kubeconfig\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-cluster-clusterid-ad\n      path: /organization/{organizationId}/cluster/{clusterId}/advancedSettings\n      operations:\n      - name: getclusteradvancedsettings\n        method: GET\n        description: Get advanced settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editclusteradvancedsettings\n        method: PUT\n        description: Edit advanced settings\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-cluster-clusterid-ro\n      path: /organization/{organizationId}/cluster/{clusterId}/routingTable\n      operations:\n      - name: getroutingtable\n        method: GET\n        description: Get routing table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editroutingtable\n        method: PUT\n        description: Edit routing table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-organizationid-cluster-clusterid-lo\n      path: /organization/{organizationId}/cluster/{clusterId}/logs\n      operations:\n      - name: listclusterlogs\n        method: GET\n        description: List Cluster Logs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: organization-organizationid-aws-credentials\n      path: /organization/{organizationId}/aws/credentials\n      operations:\n      - name: listawscredentials\n        method: GET\n        description: List AWS credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createawscredentials\n        method: POST\n        description: Create AWS credentials set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: qovery-rest\n    description: REST adapter for Qovery API.\n    resources:\n    - path: /organization\n      name: listorganization\n      operations:\n      - method: GET\n        name: listorganization\n        description: List user organizations\n        call: qovery.listorganization\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /organization\n      name: createorganization\n      operations:\n      - method: POST\n        name: createorganization\n        description: Create an organization\n        call: qovery.createorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}\n      name: getorganization\n      operations:\n      - method: GET\n        name: getorganization\n        description: Get organization by ID\n        call: qovery.getorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}\n      name: editorganization\n      operations:\n      - method: PUT\n        name: editorganization\n        description: Edit an organization\n        call: qovery.editorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}\n      name:\
  \ deleteorganization\n      operations:\n      - method: DELETE\n        name: deleteorganization\n        description: Delete an organization\n        call: qovery.deleteorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/apiToken\n      name: listorganizationapitokens\n      operations:\n      - method: GET\n        name: listorganizationapitokens\n        description: List organization api tokens\n        call: qovery.listorganizationapitokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/apiToken\n      name: createorganizationapitoken\n      operations:\n      - method: POST\n        name: createorganizationapitoken\n        description: Create an organization api token\n        call: qovery.createorganizationapitoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/apiToken/{apiTokenId}\n\
  \      name: deleteorganizationapitoken\n      operations:\n      - method: DELETE\n        name: deleteorganizationapitoken\n        description: Delete organization api token\n        call: qovery.deleteorganizationapitoken\n        with:\n          apiTokenId: rest.apiTokenId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/availableRole\n      name: listorganizationavailableroles\n      operations:\n      - method: GET\n        name: listorganizationavailableroles\n        description: List organization available roles\n        call: qovery.listorganizationavailableroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/gitToken\n      name: listorganizationgittokens\n      operations:\n      - method: GET\n        name: listorganizationgittokens\n        description: List organization git tokens\n        call: qovery.listorganizationgittokens\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/gitToken\n      name: creategittoken\n      operations:\n      - method: POST\n        name: creategittoken\n        description: Create a git token\n        call: qovery.creategittoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/gitToken/{gitTokenId}\n      name: getorganizationgittoken\n      operations:\n      - method: GET\n        name: getorganizationgittoken\n        description: Get organization git token\n        call: qovery.getorganizationgittoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/gitToken/{gitTokenId}\n      name: editgittoken\n      operations:\n      - method: PUT\n        name: editgittoken\n        description: Edit a git token\n        call: qovery.editgittoken\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /organization/{organizationId}/gitToken/{gitTokenId}\n      name: deletegittoken\n      operations:\n      - method: DELETE\n        name: deletegittoken\n        description: Delete a git token\n        call: qovery.deletegittoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/gitToken/{gitTokenId}/associatedServices\n      name: getgittokenassociatedservices\n      operations:\n      - method: GET\n        name: getgittokenassociatedservices\n        description: Get organization git token associated services\n        call: qovery.getgittokenassociatedservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/listDirectoriesFromGitRepository\n      name: listdirectoriesfromgitrepository\n      operations:\n      - method: POST\n        name: listdirectoriesfromgitrepository\n        description: List\
  \ directories from a git repository\n        call: qovery.listdirectoriesfromgitrepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/member\n      name: getorganizationmembers\n      operations:\n      - method: GET\n        name: getorganizationmembers\n        description: Get organization members\n        call: qovery.getorganizationmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/member\n      name: editorganizationmemberrole\n      operations:\n      - method: PUT\n        name: editorganizationmemberrole\n        description: Edit an organization member role\n        call: qovery.editorganizationmemberrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/member\n      name: deletemember\n      operations:\n      - method: DELETE\n        name: deletemember\n   \
  \     description: Remove a member\n        call: qovery.deletemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/inviteMember\n      name: getorganizationinvitedmembers\n      operations:\n      - method: GET\n        name: getorganizationinvitedmembers\n        description: Get invited members\n        call: qovery.getorganizationinvitedmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/inviteMember\n      name: postinvitemember\n      operations:\n      - method: POST\n        name: postinvitemember\n        description: Invite someone in the organization\n        call: qovery.postinvitemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/inviteMember/{inviteId}\n      name: getmemberinvitation\n      operations:\n      - method: GET\n        name: getmemberinvitation\n\
  \        description: Get member invitation\n        call: qovery.getmemberinvitation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/inviteMember/{inviteId}\n      name: postacceptinvitemember\n      operations:\n      - method: POST\n        name: postacceptinvitemember\n        description: Accept Invite in the organization\n        call: qovery.postacceptinvitemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/inviteMember/{inviteId}\n      name: deleteinvitemember\n      operations:\n      - method: DELETE\n        name: deleteinvitemember\n        description: Remove an invited member\n        call: qovery.deleteinvitemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/transferOwnership\n      name: postorganizationtransferownership\n      operations:\n      - method:\
  \ POST\n        name: postorganizationtransferownership\n        description: Transfer organization ownership to another user\n        call: qovery.postorganizationtransferownership\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/currentCost\n      name: getorganizationcurrentcost\n      operations:\n      - method: GET\n        name: getorganizationcurrentcost\n        description: Get organization current cost\n        call: qovery.getorganizationcurrentcost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/creditCode\n      name: addcreditcode\n      operations:\n      - method: POST\n        name: addcreditcode\n        description: Add credit code\n        call: qovery.addcreditcode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/changePlan\n      name: changeplan\n      operations:\n\
  \      - method: POST\n        name: changeplan\n        description: Change organization plan\n        call: qovery.changeplan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/cluster/{clusterId}/currentCost\n      name: getclustercurrentcost\n      operations:\n      - method: GET\n        name: getclustercurrentcost\n        description: Get cluster current cost\n        call: qovery.getclustercurrentcost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/billingInfo\n      name: getorganizationbillinginfo\n      operations:\n      - method: GET\n        name: getorganizationbillinginfo\n        description: Get organization billing info\n        call: qovery.getorganizationbillinginfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/billingInfo\n      name: editorganizationbillinginfo\n\
  \      operations:\n      - method: PUT\n        name: editorganizationbillinginfo\n        description: Edit Organization Billing Info\n        call: qovery.editorganizationbillinginfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/billingStatus\n      name: getorganizationbillingstatus\n      operations:\n      - method: GET\n        name: getorganizationbillingstatus\n        description: Get organization billing status\n        call: qovery.getorganizationbillingstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/billingUsageReport\n      name: generatebillingusagereport\n      operations:\n      - method: POST\n        name: generatebillingusagereport\n        description: Generate organization billing usage report\n        call: qovery.generatebillingusagereport\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /organization/{organizationId}/billingExternalId\n      name: getorganizationbillingexternalid\n      operations:\n      - method: GET\n        name: getorganizationbillingexternalid\n        description: Get organization billing external ID\n        call: qovery.getorganizationbillingexternalid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/invoice\n      name: listorganizationinvoice\n      operations:\n      - method: GET\n        name: listorganizationinvoice\n        description: List organization invoices\n        call: qovery.listorganizationinvoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/invoice/{invoiceId}\n      name: getorganizationinvoice\n      operations:\n      - method: GET\n        name: getorganizationinvoice\n        description: Get organization invoice\n        call: qovery.getorganizationinvoice\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/invoice/{invoiceId}/download\n      name: getorganizationinvoicepdf\n      operations:\n      - method: GET\n        name: getorganizationinvoicepdf\n        description: Get invoice link\n        call: qovery.getorganizationinvoicepdf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organization/{organizationId}/downloadInvoices\n      name: organizationdownloadallinvoices\n      operations:\n      - method: POST\n        name: organizationdownloadallinvoices\n        description: Download all invoices\n        call: qovery.\n\n# --- truncated at 32 KB (56 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/qovery/refs/heads/main/capabilities/qovery-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/qovery/refs/heads/main/capabilities/qovery-capability.yaml
tags:
- Qovery
- API
tools:
- description: List user organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganization
- description: Create an organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorganization
- description: Get organization by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganization
- description: Edit an organization
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editorganization
- description: Delete an organization
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteorganization
- description: List organization api tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationapitokens
- description: Create an organization api token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorganizationapitoken
- description: Delete organization api token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteorganizationapitoken
- description: List organization available roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationavailableroles
- description: List organization git tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationgittokens
- description: Create a git token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategittoken
- description: Get organization git token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationgittoken
- description: Edit a git token
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editgittoken
- description: Delete a git token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegittoken
- description: Get organization git token associated services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgittokenassociatedservices
- description: List directories from a git repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listdirectoriesfromgitrepository
- description: Get organization members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationmembers
- description: Edit an organization member role
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editorganizationmemberrole
- description: Remove a member
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemember
- description: Get invited members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationinvitedmembers
- description: Invite someone in the organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postinvitemember
- description: Get member invitation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmemberinvitation
- description: Accept Invite in the organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postacceptinvitemember
- description: Remove an invited member
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinvitemember
- description: Transfer organization ownership to another user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postorganizationtransferownership
- description: Get organization current cost
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationcurrentcost
- description: Add credit code
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addcreditcode
- description: Change organization plan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: changeplan
- description: Get cluster current cost
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclustercurrentcost
- description: Get organization billing info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationbillinginfo
- description: Edit Organization Billing Info
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editorganizationbillinginfo
- description: Get organization billing status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationbillingstatus
- description: Generate organization billing usage report
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatebillingusagereport
- description: Get organization billing external ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationbillingexternalid
- description: List organization invoices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationinvoice
- description: Get organization invoice
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationinvoice
- description: Get invoice link
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationinvoicepdf
- description: Download all invoices
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: organizationdownloadallinvoices
- description: List organization credit cards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationcreditcards
- description: Add credit card
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addcreditcard
- description: Delete credit card
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecreditcard
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproject
- description: Create a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: List total number of services and environments for each project of the organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationprojectstats
- description: List organization clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationcluster
- description: Create a cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcluster
- description: List all clusters statuses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationclusterstatus
- description: Delete a cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecluster
- description: Edit a cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editcluster
- description: Get cluster status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusterstatus
- description: Get cluster helm values for self managed installation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstallationhelmvalues
- description: Get cluster kubeconfig
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusterkubeconfig
- description: Edit cluster kubeconfig
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editclusterkubeconfig
- description: Get advanced settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusteradvancedsettings
- description: Edit advanced settings
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editclusteradvancedsettings
- description: Get routing table
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroutingtable
- description: Edit routing table
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editroutingtable
- description: List Cluster Logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusterlogs
- description: List AWS credentials
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listawscredentials
- description: Create AWS credentials set
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createawscredentials
---
