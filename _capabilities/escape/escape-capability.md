---
categories: []
consumed_apis: []
description: 'This API enables you to operate [Escape](https://escape.tech/) programmatically. All requests must be authenticated with a valid API key, provided in the `X-ESCAPE-API-KEY` header. For example: `X-ESCAPE-API-KEY: YOUR_API_KEY`. You can find your API key in the [Escape dashboard](https://app.escape.tech/user/).'
layout: capability
name: Escape Public API
operations:
- description: List profiles
  method: GET
  name: listprofiles
  path: /profiles
- description: List all scan statuses and problems
  method: GET
  name: problems
  path: /profiles/problems
- description: Get a profile
  method: GET
  name: getprofile
  path: /profiles/{profileId}
- description: Update a profile
  method: PUT
  name: updateprofile
  path: /profiles/{profileId}
- description: Delete a profile
  method: DELETE
  name: deleteprofile
  path: /profiles/{profileId}
- description: Update profile configuration
  method: PUT
  name: updateprofileconfiguration
  path: /profiles/{profileId}/configuration
- description: Update profile schema
  method: PUT
  name: updateprofileschema
  path: /profiles/{profileId}/schema
- description: Create a DAST REST profile
  method: POST
  name: createdastrestprofile
  path: /profiles/rest
- description: Create a DAST GraphQL profile
  method: POST
  name: createdastgraphqlprofile
  path: /profiles/graphql
- description: Create a DAST WebApp profile
  method: POST
  name: createdastwebappprofile
  path: /profiles/webapp
- description: Create an Automated Pentest REST profile
  method: POST
  name: createpentestrestprofile
  path: /profiles/ai-pentesting/rest
- description: Create an Automated Pentest GraphQL profile
  method: POST
  name: createpentestgraphqlprofile
  path: /profiles/ai-pentesting/graphql
- description: Create an Automated Pentest WebApp profile
  method: POST
  name: createpentestwebappprofile
  path: /profiles/ai-pentesting/webapp
- description: Start an authentication configuration check
  method: POST
  name: startauthentication
  path: /authentications
- description: Get authentication configuration check status
  method: GET
  name: getauthentication
  path: /authentications/{authenticationId}
- description: List assets
  method: GET
  name: listassets
  path: /assets
- description: Bulk update assets
  method: POST
  name: bulkupdateassets
  path: /assets/bulk-update
- description: Bulk delete assets
  method: POST
  name: bulkdeleteassets
  path: /assets/bulk-delete
- description: Get an asset
  method: GET
  name: getasset
  path: /assets/{assetId}
- description: Update an asset
  method: PUT
  name: updateasset
  path: /assets/{assetId}
- description: Delete an asset
  method: DELETE
  name: deleteasset
  path: /assets/{assetId}
- description: List activities of an asset
  method: GET
  name: listassetactivities
  path: /assets/{assetId}/activities
- description: Comment on an asset
  method: POST
  name: createassetcomment
  path: /assets/{assetId}/activities
- description: Create asset dns
  method: POST
  name: createasset-dns
  path: /assets/dns
- description: Create asset ipv4
  method: POST
  name: createasset-ipv4
  path: /assets/ipv4
- description: Create asset ipv6
  method: POST
  name: createasset-ipv6
  path: /assets/ipv6
- description: Create asset graphql
  method: POST
  name: createasset-graphql
  path: /assets/graphql
- description: Create asset rest
  method: POST
  name: createasset-rest
  path: /assets/rest
- description: Create asset grpc
  method: POST
  name: createasset-grpc
  path: /assets/grpc
- description: Create asset websocket
  method: POST
  name: createasset-websocket
  path: /assets/websocket
- description: Create asset mcp
  method: POST
  name: createasset-mcp
  path: /assets/mcp
- description: Create asset soap
  method: POST
  name: createasset-soap
  path: /assets/soap
- description: Create asset webapp
  method: POST
  name: createasset-webapp
  path: /assets/webapp
- description: Create asset azure-tenant
  method: POST
  name: createasset-azure-tenant
  path: /assets/azure-tenant
- description: Create asset ipv4-range
  method: POST
  name: createasset-ipv4-range
  path: /assets/ipv4-range
- description: Create asset gitlab-repository
  method: POST
  name: createasset-gitlab-repository
  path: /assets/gitlab-repository
- description: Create asset github-repository
  method: POST
  name: createasset-github-repository
  path: /assets/github-repository
- description: Create asset bitbucket-repository
  method: POST
  name: createasset-bitbucket-repository
  path: /assets/bitbucket-repository
- description: Create asset code-project
  method: POST
  name: createasset-code-project
  path: /assets/code-project
- description: Create asset aws-lambda
  method: POST
  name: createasset-aws-lambda
  path: /assets/aws-lambda
- description: Create asset package
  method: POST
  name: createasset-package
  path: /assets/package
- description: Create asset software
  method: POST
  name: createasset-software
  path: /assets/software
- description: Create asset schema
  method: POST
  name: createasset-schema
  path: /assets/schema
- description: List scans
  method: GET
  name: listscans
  path: /scans
- description: Start a new scan
  method: POST
  name: startscan
  path: /scans
- description: List scans with their problems
  method: GET
  name: scansproblems
  path: /scans/problems
- description: List inbox emails
  method: GET
  name: listinboxemails
  path: /scans/emails
- description: Read inbox email content
  method: GET
  name: readinboxemail
  path: /scans/emails/{id}
- description: Get a scan
  method: GET
  name: getscan
  path: /scans/{scanId}
- description: Cancel a scan
  method: PUT
  name: cancelscan
  path: /scans/{scanId}/cancel
- description: Ignore a scan
  method: PUT
  name: ignorescan
  path: /scans/{scanId}/ignore
- description: List scan targets and API coverage
  method: GET
  name: listscantargets
  path: /scans/{scanId}/targets
- description: List issues
  method: GET
  name: listissues
  path: /issues
- description: Get issue funnel
  method: GET
  name: getissuefunnel
  path: /issues/funnel
- description: Get issue severity trends
  method: GET
  name: getissuetrends
  path: /issues/trends
- description: Bulk update issues
  method: POST
  name: bulkupdateissues
  path: /issues/bulk-update
- description: Get an issue
  method: GET
  name: getissue
  path: /issues/{issueId}
- description: Update an issue
  method: PUT
  name: updateissue
  path: /issues/{issueId}
- description: List activities of an issue
  method: GET
  name: listissueactivities
  path: /issues/{issueId}/activities
- description: Comment on an issue
  method: POST
  name: createissuecomment
  path: /issues/{issueId}/activities
personas: []
provider_name: Escape
provider_slug: escape
search_terms:
- list issues
- createasset code project
- list scan targets and api coverage
- getissue
- update a profile
- getauthentication
- updateprofileschema
- create asset ipv6
- api
- comment on an issue
- create asset schema
- listissueactivities
- list profiles
- createasset webapp
- listissues
- scansproblems
- createasset mcp
- get issue severity trends
- startauthentication
- delete a profile
- create asset package
- getscan
- updateissue
- delete an asset
- create a dast webapp profile
- comment on an asset
- bulk delete assets
- list activities of an issue
- createasset bitbucket repository
- update profile schema
- getasset
- create an automated pentest rest profile
- get a scan
- list inbox emails
- problems
- get a profile
- create asset aws-lambda
- ignore a scan
- createasset ipv4
- deleteprofile
- createasset azure tenant
- createasset ipv4 range
- deleteasset
- createasset schema
- createdastgraphqlprofile
- create asset graphql
- create asset code-project
- create asset websocket
- create a dast graphql profile
- create asset dns
- escape
- createpentestwebappprofile
- bulkdeleteassets
- bulkupdateassets
- listassetactivities
- listscantargets
- updateasset
- createasset graphql
- create asset webapp
- createpentestgraphqlprofile
- create an automated pentest graphql profile
- listassets
- updateprofile
- create asset azure-tenant
- createasset dns
- security
- createassetcomment
- create asset mcp
- get issue funnel
- ignorescan
- createasset ipv6
- list activities of an asset
- create a dast rest profile
- update an asset
- getissuetrends
- platform
- start a new scan
- createasset software
- update profile configuration
- listinboxemails
- create asset soap
- cancelscan
- listprofiles
- get authentication configuration check status
- list scans with their problems
- updateprofileconfiguration
- getprofile
- createasset websocket
- listscans
- bulk update issues
- get an issue
- create an automated pentest webapp profile
- createasset aws lambda
- get an asset
- create asset software
- createpentestrestprofile
- bulk update assets
- create asset bitbucket-repository
- read inbox email content
- createasset rest
- create asset github-repository
- createissuecomment
- createdastwebappprofile
- create asset grpc
- list all scan statuses and problems
- readinboxemail
- createasset soap
- list scans
- create asset ipv4-range
- update an issue
- create asset gitlab-repository
- createasset grpc
- getissuefunnel
- createasset gitlab repository
- create asset ipv4
- startscan
- createdastrestprofile
- bulkupdateissues
- createasset github repository
- create asset rest
- start an authentication configuration check
- cancel a scan
- createasset package
- list assets
slug: escape-capability
source_filename: escape-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Escape Public API\n  description: 'This API enables you to operate [Escape](https://escape.tech/) programmatically. All requests must be authenticated\n    with a valid API key, provided in the `X-ESCAPE-API-KEY` header. For example: `X-ESCAPE-API-KEY: YOUR_API_KEY`. You can\n    find your API key in the [Escape dashboard](https://app.escape.tech/user/).'\n  tags:\n  - Escape\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: escape\n    baseUri: https://public.escape.tech/v3\n    description: Escape Public API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-ESCAPE-API-KEY\n      value: '{{ESCAPE_TOKEN}}'\n    resources:\n    - name: profiles\n      path: /profiles\n      operations:\n      - name: listprofiles\n        method: GET\n        description: List profiles\n        inputParameters:\n        - name: cursor\n          in: query\n\
  \          type: string\n          description: The cursor to start the pagination from. Returned by the previous page response. If not provided, the\n            first page will be returned.\n        - name: size\n          in: query\n          type: integer\n          description: The number of items to return per page\n        - name: sortType\n          in: query\n          type: string\n          description: The type to sort by\n        - name: sortDirection\n          in: query\n          type: string\n          description: The direction to sort by\n        - name: assetIds\n          in: query\n          type: string\n          description: Filter by asset IDs\n        - name: domains\n          in: query\n          type: string\n          description: Filter by domain\n        - name: issueIds\n          in: query\n          type: string\n          description: Filter by issue IDs\n        - name: tagIds\n          in: query\n          type: string\n          description: Filter\
  \ by tag IDs\n        - name: search\n          in: query\n          type: string\n          description: Search term to filter profiles by name or description\n        - name: initiators\n          in: query\n          type: array\n          description: Filter by initiator\n        - name: kinds\n          in: query\n          type: array\n          description: Filter by kind\n        - name: risks\n          in: query\n          type: array\n          description: Filter by risk\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles-problems\n      path: /profiles/problems\n      operations:\n      - name: problems\n        method: GET\n        description: List all scan statuses and problems\n        inputParameters:\n        - name: cursor\n          in: query\n          type: string\n          description: The cursor to start the pagination from. Returned by the previous page response.\
  \ If not provided, the\n            first page will be returned.\n        - name: size\n          in: query\n          type: integer\n          description: The number of items to return per page\n        - name: sortType\n          in: query\n          type: string\n          description: The type to sort by\n        - name: sortDirection\n          in: query\n          type: string\n          description: The direction to sort by\n        - name: assetIds\n          in: query\n          type: string\n          description: Filter by asset IDs\n        - name: domains\n          in: query\n          type: string\n          description: Filter by domain\n        - name: issueIds\n          in: query\n          type: string\n          description: Filter by issue IDs\n        - name: tagIds\n          in: query\n          type: string\n          description: Filter by tag IDs\n        - name: search\n          in: query\n          type: string\n          description: Search term to filter\
  \ profiles by name or description\n        - name: initiators\n          in: query\n          type: array\n          description: Filter by initiator\n        - name: kinds\n          in: query\n          type: array\n          description: Filter by kind\n        - name: risks\n          in: query\n          type: array\n          description: Filter by risk\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles-profileid\n      path: /profiles/{profileId}\n      operations:\n      - name: getprofile\n        method: GET\n        description: Get a profile\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: The profile ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateprofile\n        method: PUT\n \
  \       description: Update a profile\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: The profile ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteprofile\n        method: DELETE\n        description: Delete a profile\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: The profile ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles-profileid-configuration\n      path: /profiles/{profileId}/configuration\n      operations:\n      - name: updateprofileconfiguration\n        method: PUT\n        description: Update profile configuration\n        inputParameters:\n        - name: profileId\n         \
  \ in: path\n          type: string\n          required: true\n          description: The profile ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles-profileid-schema\n      path: /profiles/{profileId}/schema\n      operations:\n      - name: updateprofileschema\n        method: PUT\n        description: Update profile schema\n        inputParameters:\n        - name: profileId\n          in: path\n          type: string\n          required: true\n          description: The profile ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles-rest\n      path: /profiles/rest\n      operations:\n      - name: createdastrestprofile\n        method: POST\n        description: Create a DAST REST profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: profiles-graphql\n      path: /profiles/graphql\n      operations:\n      - name: createdastgraphqlprofile\n        method: POST\n        description: Create a DAST GraphQL profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles-webapp\n      path: /profiles/webapp\n      operations:\n      - name: createdastwebappprofile\n        method: POST\n        description: Create a DAST WebApp profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles-ai-pentesting-rest\n      path: /profiles/ai-pentesting/rest\n      operations:\n      - name: createpentestrestprofile\n        method: POST\n        description: Create an Automated Pentest REST profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n    - name: profiles-ai-pentesting-graphql\n      path: /profiles/ai-pentesting/graphql\n      operations:\n      - name: createpentestgraphqlprofile\n        method: POST\n        description: Create an Automated Pentest GraphQL profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles-ai-pentesting-webapp\n      path: /profiles/ai-pentesting/webapp\n      operations:\n      - name: createpentestwebappprofile\n        method: POST\n        description: Create an Automated Pentest WebApp profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authentications\n      path: /authentications\n      operations:\n      - name: startauthentication\n        method: POST\n        description: Start an authentication configuration check\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: authentications-authenticationid\n      path: /authentications/{authenticationId}\n      operations:\n      - name: getauthentication\n        method: GET\n        description: Get authentication configuration check status\n        inputParameters:\n        - name: authenticationId\n          in: path\n          type: string\n          required: true\n          description: Identifier returned by the start endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /assets\n      operations:\n      - name: listassets\n        method: GET\n        description: List assets\n        inputParameters:\n        - name: cursor\n          in: query\n          type: string\n          description: The cursor to start the pagination from. Returned by the previous page response. If not provided, the\n        \
  \    first page will be returned.\n        - name: size\n          in: query\n          type: integer\n          description: The number of items to return per page\n        - name: sortType\n          in: query\n          type: string\n          description: The type to sort by\n        - name: sortDirection\n          in: query\n          type: string\n          description: The direction to sort by\n        - name: search\n          in: query\n          type: string\n          description: Search term to filter assets by name or description\n        - name: types\n          in: query\n          type: array\n          description: Filter by type\n        - name: statuses\n          in: query\n          type: array\n          description: Filter by status\n        - name: manuallyCreated\n          in: query\n          type: string\n          description: Filter by manually created\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: assets-bulk-update\n      path: /assets/bulk-update\n      operations:\n      - name: bulkupdateassets\n        method: POST\n        description: Bulk update assets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-bulk-delete\n      path: /assets/bulk-delete\n      operations:\n      - name: bulkdeleteassets\n        method: POST\n        description: Bulk delete assets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-assetid\n      path: /assets/{assetId}\n      operations:\n      - name: getasset\n        method: GET\n        description: Get an asset\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: The asset ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: updateasset\n        method: PUT\n        description: Update an asset\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: The asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteasset\n        method: DELETE\n        description: Delete an asset\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: The asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-assetid-activities\n      path: /assets/{assetId}/activities\n      operations:\n      - name: listassetactivities\n        method: GET\n        description: List activities\
  \ of an asset\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: The asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createassetcomment\n        method: POST\n        description: Comment on an asset\n        inputParameters:\n        - name: assetId\n          in: path\n          type: string\n          required: true\n          description: The asset ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-dns\n      path: /assets/dns\n      operations:\n      - name: createasset-dns\n        method: POST\n        description: Create asset dns\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-ipv4\n    \
  \  path: /assets/ipv4\n      operations:\n      - name: createasset-ipv4\n        method: POST\n        description: Create asset ipv4\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-ipv6\n      path: /assets/ipv6\n      operations:\n      - name: createasset-ipv6\n        method: POST\n        description: Create asset ipv6\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-graphql\n      path: /assets/graphql\n      operations:\n      - name: createasset-graphql\n        method: POST\n        description: Create asset graphql\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-rest\n      path: /assets/rest\n      operations:\n      - name: createasset-rest\n        method: POST\n        description:\
  \ Create asset rest\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-grpc\n      path: /assets/grpc\n      operations:\n      - name: createasset-grpc\n        method: POST\n        description: Create asset grpc\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-websocket\n      path: /assets/websocket\n      operations:\n      - name: createasset-websocket\n        method: POST\n        description: Create asset websocket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-mcp\n      path: /assets/mcp\n      operations:\n      - name: createasset-mcp\n        method: POST\n        description: Create asset mcp\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: assets-soap\n      path: /assets/soap\n      operations:\n      - name: createasset-soap\n        method: POST\n        description: Create asset soap\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-webapp\n      path: /assets/webapp\n      operations:\n      - name: createasset-webapp\n        method: POST\n        description: Create asset webapp\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-azure-tenant\n      path: /assets/azure-tenant\n      operations:\n      - name: createasset-azure-tenant\n        method: POST\n        description: Create asset azure-tenant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-ipv4-range\n      path: /assets/ipv4-range\n\
  \      operations:\n      - name: createasset-ipv4-range\n        method: POST\n        description: Create asset ipv4-range\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-gitlab-repository\n      path: /assets/gitlab-repository\n      operations:\n      - name: createasset-gitlab-repository\n        method: POST\n        description: Create asset gitlab-repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-github-repository\n      path: /assets/github-repository\n      operations:\n      - name: createasset-github-repository\n        method: POST\n        description: Create asset github-repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-bitbucket-repository\n      path: /assets/bitbucket-repository\n\
  \      operations:\n      - name: createasset-bitbucket-repository\n        method: POST\n        description: Create asset bitbucket-repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-code-project\n      path: /assets/code-project\n      operations:\n      - name: createasset-code-project\n        method: POST\n        description: Create asset code-project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-aws-lambda\n      path: /assets/aws-lambda\n      operations:\n      - name: createasset-aws-lambda\n        method: POST\n        description: Create asset aws-lambda\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-package\n      path: /assets/package\n      operations:\n      - name:\
  \ createasset-package\n        method: POST\n        description: Create asset package\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-software\n      path: /assets/software\n      operations:\n      - name: createasset-software\n        method: POST\n        description: Create asset software\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets-schema\n      path: /assets/schema\n      operations:\n      - name: createasset-schema\n        method: POST\n        description: Create asset schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scans\n      path: /scans\n      operations:\n      - name: listscans\n        method: GET\n        description: List scans\n        inputParameters:\n        - name:\
  \ cursor\n          in: query\n          type: string\n          description: The cursor to start the pagination from. Returned by the previous page response. If not provided, the\n            first page will be returned.\n        - name: size\n          in: query\n          type: integer\n          description: The number of items to return per page\n        - name: sortType\n          in: query\n          type: string\n          description: The type to sort by\n        - name: sortDirection\n          in: query\n          type: string\n          description: The direction to sort by\n        - name: after\n          in: query\n          type: string\n          description: Filter by after date\n        - name: before\n          in: query\n          type: string\n          description: Filter by before date\n        - name: assetIds\n          in: query\n          type: string\n          description: Filter by asset IDs\n        - name: profileIds\n          in: query\n          type:\
  \ string\n          description: Filter by profile IDs\n        - name: ignored\n          in: query\n          type: string\n          description: Filter by ignored status\n        - name: initiator\n          in: query\n          type: array\n          description: Filter by initiator\n        - name: kinds\n          in: query\n          type: array\n          description: Filter by kind\n        - name: status\n          in: query\n          type: array\n          description: Filter by status\n        - name: projectIds\n          in: query\n          type: string\n          description: Filter by project IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: startscan\n        method: POST\n        description: Start a new scan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scans-problems\n      path:\
  \ /scans/problems\n      operations:\n      - name: scansproblems\n        method: GET\n        description: List scans with their problems\n        inputParameters:\n        - name: cursor\n          in: query\n          type: string\n          description: The cursor to start the pagination from. Returned by the previous page response. If not provided, the\n            first page will be returned.\n        - name: size\n          in: query\n          type: integer\n          description: The number of items to return per page\n        - name: sortType\n          in: query\n          type: string\n          description: The type to sort by\n        - name: sortDirection\n          in: query\n          type: string\n          description: The direction to sort by\n        - name: after\n          in: query\n          type: string\n          description: Filter by after date\n        - name: before\n          in: query\n          type: string\n          description: Filter by before date\n\
  \        - name: assetIds\n          in: query\n          type: string\n          description: Filter by asset IDs\n        - name: profileIds\n          in: query\n          type: string\n          description: Filter by profile IDs\n        - name: projectIds\n          in: query\n          type: string\n          description: Filter by project IDs\n        - name: ignored\n          in: query\n          type: string\n          description: Filter by ignored status\n        - name: initiator\n          in: query\n          type: array\n          description: Filter by initiator\n        - name: kinds\n          in: query\n          type: array\n          description: Filter by kind\n        - name: status\n          in: query\n          type: array\n          description: Filter by status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scans-emails\n      path: /scans/emails\n      operations:\n\
  \      - name: listinboxemails\n        method: GET\n        description: List inbox emails\n        inputParameters:\n        - name: cursor\n          in: query\n          type: string\n          description: The cursor to start the pagination from. Returned by the previous page response. If not provided, the\n            first page will be returned.\n        - name: size\n          in: query\n          type: integer\n          description: The number of items to return per page\n        - name: ids\n          in: query\n          type: array\n          description: Filter by email IDs\n        - name: before\n          in: query\n          type: string\n          description: Filter by before date\n        - name: after\n          in: query\n          type: string\n          description: Filter by after date\n        - name: email\n          in: query\n          type: string\n          required: true\n          description: Inbox email address used as `to` filter\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scans-emails-id\n      path: /scans/emails/{id}\n      operations:\n      - name: readinboxemail\n        method: GET\n        description: Read inbox email content\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The inbox email ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scans-scanid\n      path: /scans/{scanId}\n      operations:\n      - name: getscan\n        method: GET\n        description: Get a scan\n        inputParameters:\n        - name: scanId\n          in: path\n          type: string\n          required: true\n          description: The scan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: scans-scanid-cancel\n      path: /scans/{scanId}/cancel\n      operations:\n      - name: cancelscan\n        method: PUT\n        description: Cancel a scan\n        inputParameters:\n        - name: scanId\n          in: path\n          type: string\n          required: true\n          description: The scan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scans-scanid-ignore\n      path: /scans/{scanId}/ignore\n      operations:\n      - name: ignorescan\n        method: PUT\n        description: Ignore a scan\n        inputParameters:\n        - name: scanId\n          in: path\n          type: string\n          required: true\n          description: The scan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scans-scanid-targets\n      path: /scans/{scanId}/targets\n      operations:\n\
  \      - name: listscantargets\n        method: GET\n        description: List scan targets and API coverage\n        inputParameters:\n        - name: scanId\n          in: path\n          type: string\n          required: true\n          description: The scan ID\n        - name: cursor\n          in: query\n          type: string\n          description: The cursor to start the pagination from. Returned by the previous page response. If not provided, the\n            first page will be returned.\n        - name: size\n          in: query\n          type: integer\n          description: The number of items to return per page\n        - name: sortType\n          in: query\n          type: string\n          description: The type to sort by\n        - name: sortDirection\n          in: query\n          type: string\n          description: The direction to sort by\n        - name: types\n          in: query\n          type: array\n          description: Optional filter by target kinds (comma-separated\
  \ or repeated), e.g. API_ROUTE or GRAPHQL_RESOLVER\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issues\n      path: /issues\n      operations:\n      - name: listissues\n        method: GET\n        description: List issues\n        inputParameters:\n        - name: cursor\n          in: query\n          type: string\n          description: The cursor to start the pagination from. Returned by the previous page response. If not provided, the\n            first page will be returned.\n        - name: size\n          in: query\n          type: integer\n          description: The number of items to return per page\n        - name: sortType\n          in: query\n          type: string\n          description: The type to sort by\n        - name: sortDirection\n          in: query\n          type: string\n          description: The direction to sort by\n        - name: profileIds\n          in: query\n\
  \          type: string\n          description: Filter by application IDs\n        - name: assetIds\n          in: query\n          type: string\n          description: Filter by asset IDs\n        - name: domains\n          in: query\n          type: string\n          description: Filter by domain\n        - name: ids\n          in: query\n          type: string\n          description: Filter by specific issue IDs\n        - name: names\n          in: query\n          type: string\n          description: Filter by issue names\n        - name: scanIds\n          in: query\n          type: string\n          description: Filter by scan IDs\n        - name: tagIds\n          in: query\n          type: string\n          description: Filter by tag IDs\n        - name: search\n          in: query\n          type: string\n          description: Search term to filter issues by name or description\n        - name: jiraTicket\n          in: query\n          type: string\n          description: Filter\
  \ by issues with Jira tickets\n        - name: risks\n          in: query\n          type: array\n          description: Filter by risk types\n        - name: assetClasses\n          in: query\n          type: array\n          description: Filter by asset classes\n        - name: scannerKinds\n          in: query\n          type: array\n          description: Filter by scanner kinds\n        - name: severities\n          in: query\n          type: array\n          description: Filter by issue severities\n        - name: status\n          in: query\n          type: array\n          description: Filter by issue status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issues-funnel\n      path: /issues/funnel\n      operations:\n      - name: getissuefunnel\n        method: GET\n        description: Get issue funnel\n        inputParameters:\n        - name: projectIds\n          in: query\n        \
  \  type: string\n          description: Filter by project IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issues-trends\n      path: /issues/trends\n      operations:\n      - name: getissuetrends\n        method: GET\n        description: Get issue severity trends\n        inputParameters:\n        - name: after\n          in: query\n          type: string\n          required: true\n          description: Start date (ISO 8601)\n        - name: before\n          in: query\n          type: string\n          required: true\n          description: End date (ISO 8601)\n        - name: interval\n          in: query\n          type: string\n          description: Time bucket interval (e.g. \"1 day\", \"1 week\")\n        - name: applicationIds\n          in: query\n          type: string\n          description: Filter by application IDs\n        - name: projectIds\n          in: query\n          type:\
  \ string\n          description: Filter by project IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issues-bulk-update\n      path: /issues/bulk-update\n      operations:\n      - name: bulkupdateissues\n        method: POST\n        description: Bulk update issues\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issues-issueid\n      path: /issues/{issueId}\n      operations:\n      - name: getissue\n        method: GET\n        description: Get an issue\n        inputParameters:\n        - name: issueId\n          in: path\n          type: string\n          required: true\n          description: The issue ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateissue\n        method: PUT\n        description:\
  \ Update an issue\n        inputParameters:\n        - name: issueId\n          in: path\n          type: string\n          required: true\n          description: The issue ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issues-issueid-activities\n      path: /issues/{issueId}/activities\n      operations:\n      - name: listissueactivities\n        method: GET\n        description: List activities of an issue\n        inputParameters:\n        - name: issueId\n          in: path\n          type: string\n          required: true\n          description: The issue ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createissuecomment\n        method: POST\n        description: \n\n# --- truncated at 32 KB (81 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/escape/refs/heads/main/capabilities/escape-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/escape/refs/heads/main/capabilities/escape-capability.yaml
tags:
- Escape
- API
tools:
- description: List profiles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprofiles
- description: List all scan statuses and problems
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: problems
- description: Get a profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprofile
- description: Update a profile
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateprofile
- description: Delete a profile
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprofile
- description: Update profile configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateprofileconfiguration
- description: Update profile schema
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateprofileschema
- description: Create a DAST REST profile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdastrestprofile
- description: Create a DAST GraphQL profile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdastgraphqlprofile
- description: Create a DAST WebApp profile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdastwebappprofile
- description: Create an Automated Pentest REST profile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpentestrestprofile
- description: Create an Automated Pentest GraphQL profile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpentestgraphqlprofile
- description: Create an Automated Pentest WebApp profile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpentestwebappprofile
- description: Start an authentication configuration check
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startauthentication
- description: Get authentication configuration check status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthentication
- description: List assets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listassets
- description: Bulk update assets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: bulkupdateassets
- description: Bulk delete assets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: bulkdeleteassets
- description: Get an asset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getasset
- description: Update an asset
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateasset
- description: Delete an asset
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteasset
- description: List activities of an asset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listassetactivities
- description: Comment on an asset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createassetcomment
- description: Create asset dns
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-dns
- description: Create asset ipv4
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-ipv4
- description: Create asset ipv6
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-ipv6
- description: Create asset graphql
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-graphql
- description: Create asset rest
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-rest
- description: Create asset grpc
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-grpc
- description: Create asset websocket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-websocket
- description: Create asset mcp
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-mcp
- description: Create asset soap
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-soap
- description: Create asset webapp
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-webapp
- description: Create asset azure-tenant
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-azure-tenant
- description: Create asset ipv4-range
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-ipv4-range
- description: Create asset gitlab-repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-gitlab-repository
- description: Create asset github-repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-github-repository
- description: Create asset bitbucket-repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-bitbucket-repository
- description: Create asset code-project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-code-project
- description: Create asset aws-lambda
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-aws-lambda
- description: Create asset package
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-package
- description: Create asset software
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-software
- description: Create asset schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createasset-schema
- description: List scans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscans
- description: Start a new scan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startscan
- description: List scans with their problems
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: scansproblems
- description: List inbox emails
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinboxemails
- description: Read inbox email content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readinboxemail
- description: Get a scan
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getscan
- description: Cancel a scan
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: cancelscan
- description: Ignore a scan
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: ignorescan
- description: List scan targets and API coverage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscantargets
- description: List issues
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listissues
- description: Get issue funnel
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getissuefunnel
- description: Get issue severity trends
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getissuetrends
- description: Bulk update issues
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: bulkupdateissues
- description: Get an issue
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getissue
- description: Update an issue
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateissue
- description: List activities of an issue
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listissueactivities
- description: Comment on an issue
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createissuecomment
---
