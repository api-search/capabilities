---
categories: []
consumed_apis: []
description: The GitBook REST API enables you to programmatically manage your GitBook content, organizations, spaces, collections, and integrations. It supports creating, updating, and deleting organizations, spaces, collections, and published docs sites; managing users, teams, and access permissions; importing and exporting content; creating, listing, reviewing, merging, and updating change requests; managing comments; configuring custom hostnames and URLs; and managing integrations and OpenAPI documentation.
layout: capability
name: GitBook API
operations:
- description: GitBook Get the authenticated user
  method: GET
  name: getcurrentuser
  path: /user
- description: GitBook Get a user by ID
  method: GET
  name: getuserbyid
  path: /users/{userId}
- description: GitBook List organizations
  method: GET
  name: listorganizations
  path: /orgs
- description: GitBook Get an organization
  method: GET
  name: getorganization
  path: /orgs/{organizationId}
- description: GitBook Update an organization
  method: PATCH
  name: updateorganization
  path: /orgs/{organizationId}
- description: GitBook List organization members
  method: GET
  name: listorganizationmembers
  path: /orgs/{organizationId}/members
- description: GitBook Get an organization member
  method: GET
  name: getorganizationmember
  path: /orgs/{organizationId}/members/{userId}
- description: GitBook Update an organization member
  method: PATCH
  name: updateorganizationmember
  path: /orgs/{organizationId}/members/{userId}
- description: GitBook Remove an organization member
  method: DELETE
  name: removeorganizationmember
  path: /orgs/{organizationId}/members/{userId}
- description: GitBook List organization teams
  method: GET
  name: listorganizationteams
  path: /orgs/{organizationId}/teams
- description: GitBook Get a team
  method: GET
  name: getorganizationteam
  path: /orgs/{organizationId}/teams/{teamId}
- description: GitBook List spaces in an organization
  method: GET
  name: listspacesinorganization
  path: /orgs/{organizationId}/spaces
- description: GitBook Create a space in an organization
  method: POST
  name: createspaceinorganization
  path: /orgs/{organizationId}/spaces
- description: GitBook Get a space
  method: GET
  name: getspace
  path: /spaces/{spaceId}
- description: GitBook Update a space
  method: PATCH
  name: updatespace
  path: /spaces/{spaceId}
- description: GitBook Delete a space
  method: DELETE
  name: deletespace
  path: /spaces/{spaceId}
- description: GitBook Duplicate a space
  method: POST
  name: duplicatespace
  path: /spaces/{spaceId}/duplicate
- description: GitBook Move a space
  method: POST
  name: movespace
  path: /spaces/{spaceId}/move
- description: GitBook Transfer a space
  method: POST
  name: transferspace
  path: /spaces/{spaceId}/transfer
- description: GitBook Restore a deleted space
  method: POST
  name: restorespace
  path: /spaces/{spaceId}/restore
- description: GitBook List space user permissions
  method: GET
  name: listspaceusers
  path: /spaces/{spaceId}/permissions/users
- description: GitBook Update space user permissions
  method: PATCH
  name: updatespaceuser
  path: /spaces/{spaceId}/permissions/users/{userId}
- description: GitBook Remove a space user
  method: DELETE
  name: removespaceuser
  path: /spaces/{spaceId}/permissions/users/{userId}
- description: GitBook Get space content
  method: GET
  name: getspacecontent
  path: /spaces/{spaceId}/content
- description: GitBook Get a page in a space
  method: GET
  name: getpageinspace
  path: /spaces/{spaceId}/content/page/{pageId}
- description: GitBook Update a page in a space
  method: PUT
  name: updatepageinspace
  path: /spaces/{spaceId}/content/page/{pageId}
- description: GitBook List files in a space
  method: GET
  name: listfilesinspace
  path: /spaces/{spaceId}/content/files
- description: GitBook List collections
  method: GET
  name: listcollectionsinorganization
  path: /orgs/{organizationId}/collections
- description: GitBook Create a collection
  method: POST
  name: createcollection
  path: /orgs/{organizationId}/collections
- description: GitBook Get a collection
  method: GET
  name: getcollection
  path: /collections/{collectionId}
- description: GitBook Delete a collection
  method: DELETE
  name: deletecollection
  path: /collections/{collectionId}
- description: GitBook List change requests
  method: GET
  name: listchangerequests
  path: /spaces/{spaceId}/change-requests
- description: GitBook Create a change request
  method: POST
  name: createchangerequest
  path: /spaces/{spaceId}/change-requests
- description: GitBook Get a change request
  method: GET
  name: getchangerequest
  path: /spaces/{spaceId}/change-requests/{changeRequestId}
- description: GitBook Update a change request
  method: PATCH
  name: updatechangerequest
  path: /spaces/{spaceId}/change-requests/{changeRequestId}
- description: GitBook Merge a change request
  method: POST
  name: mergechangerequest
  path: /spaces/{spaceId}/change-requests/{changeRequestId}/merge
- description: GitBook Get change request content
  method: GET
  name: getchangerequestcontent
  path: /spaces/{spaceId}/change-requests/{changeRequestId}/content
- description: GitBook Get a page in a change request
  method: GET
  name: getpageinchangerequest
  path: /spaces/{spaceId}/change-requests/{changeRequestId}/content/page/{pageId}
- description: GitBook Update a page in a change request
  method: PUT
  name: updatepageinchangerequest
  path: /spaces/{spaceId}/change-requests/{changeRequestId}/content/page/{pageId}
- description: GitBook List change request reviewers
  method: GET
  name: listchangerequestreviewers
  path: /spaces/{spaceId}/change-requests/{changeRequestId}/reviewers
- description: GitBook Request a review
  method: POST
  name: requestchangerequestreview
  path: /spaces/{spaceId}/change-requests/{changeRequestId}/reviewers
- description: GitBook List docs sites
  method: GET
  name: listdocssites
  path: /orgs/{organizationId}/sites
- description: GitBook Create a docs site
  method: POST
  name: createdocssite
  path: /orgs/{organizationId}/sites
- description: GitBook Get a docs site
  method: GET
  name: getdocssite
  path: /orgs/{organizationId}/sites/{siteId}
- description: GitBook Update a docs site
  method: PATCH
  name: updatedocssite
  path: /orgs/{organizationId}/sites/{siteId}
- description: GitBook Delete a docs site
  method: DELETE
  name: deletedocssite
  path: /orgs/{organizationId}/sites/{siteId}
- description: GitBook List site spaces
  method: GET
  name: listsitespaces
  path: /orgs/{organizationId}/sites/{siteId}/site-spaces
- description: GitBook Add a space to a docs site
  method: POST
  name: addsitespace
  path: /orgs/{organizationId}/sites/{siteId}/site-spaces
- description: GitBook Update a site space
  method: PATCH
  name: updatesitespace
  path: /orgs/{organizationId}/sites/{siteId}/site-spaces/{siteSpaceId}
- description: GitBook Remove a space from a docs site
  method: DELETE
  name: removesitespace
  path: /orgs/{organizationId}/sites/{siteId}/site-spaces/{siteSpaceId}
- description: GitBook Move a site space
  method: POST
  name: movesitespace
  path: /orgs/{organizationId}/sites/{siteId}/site-spaces/{siteSpaceId}/move
- description: GitBook Ask a question to a site
  method: POST
  name: asksiteai
  path: /orgs/{organizationId}/sites/{siteId}/ask
- description: GitBook Search content in an organization
  method: GET
  name: searchorganizationcontent
  path: /orgs/{organizationId}/search
- description: GitBook List OpenAPI specifications
  method: GET
  name: listopenapispecs
  path: /orgs/{organizationId}/openapi
- description: GitBook Upload an OpenAPI specification
  method: POST
  name: uploadopenapispec
  path: /orgs/{organizationId}/openapi
- description: GitBook Get an OpenAPI specification
  method: GET
  name: getopenapispec
  path: /orgs/{organizationId}/openapi/{specSlug}
- description: GitBook List integrations
  method: GET
  name: listintegrations
  path: /orgs/{organizationId}/integrations
- description: GitBook Get an integration
  method: GET
  name: getintegration
  path: /orgs/{organizationId}/integrations/{integrationId}
- description: GitBook Import content to a space
  method: POST
  name: importcontenttospace
  path: /spaces/{spaceId}/import/content
- description: GitBook Resolve a content URL
  method: GET
  name: resolvecontenturl
  path: /urls/content
personas: []
provider_name: GitBook
provider_slug: gitbook
search_terms:
- updatesitespace
- gitbook request a review
- gitbook remove a space user
- transferspace
- gitbook list spaces in an organization
- gitbook list files in a space
- sdks
- gitbook list site spaces
- addsitespace
- content
- listchangerequestreviewers
- gitbook move a site space
- gitbook update a space
- deletespace
- getuserbyid
- listintegrations
- listsitespaces
- listspacesinorganization
- gitbook list organization teams
- createspaceinorganization
- gitbook upload an openapi specification
- api
- updatespaceuser
- gitbook transfer a space
- gitbook update a page in a space
- gitbook update a docs site
- gitbook create a change request
- gitbook get an integration
- updateorganization
- gitbook restore a deleted space
- gitbook list space user permissions
- removespaceuser
- gitbook update space user permissions
- getopenapispec
- movesitespace
- removeorganizationmember
- restorespace
- gitbook search content in an organization
- gitbook duplicate a space
- updatedocssite
- getcollection
- gitbook get the authenticated user
- gitbook get a collection
- getorganization
- importcontenttospace
- gitbook get a user by id
- gitbook delete a collection
- createchangerequest
- listorganizationmembers
- deletecollection
- gitbook delete a docs site
- gitbook update a change request
- gitbook get an openapi specification
- listspaceusers
- gitbook update a page in a change request
- gitbook remove an organization member
- getspace
- updatechangerequest
- resolvecontenturl
- gitbook create a space in an organization
- listorganizationteams
- gitbook update an organization member
- createcollection
- gitbook get a page in a space
- gitbook ask a question to a site
- gitbook list collections
- listfilesinspace
- gitbook remove a space from a docs site
- gitbook create a docs site
- gitbook list docs sites
- searchorganizationcontent
- gitbook list organization members
- listchangerequests
- gitbook list openapi specifications
- gitbook update an organization
- gitbook resolve a content url
- listcollectionsinorganization
- gitbook get change request content
- mergechangerequest
- gitbook update a site space
- getspacecontent
- gitbook get a docs site
- documentation
- integrations
- gitbook get an organization member
- getorganizationteam
- asksiteai
- removesitespace
- listopenapispecs
- gitbook
- gitbook get space content
- movespace
- updatepageinspace
- getchangerequestcontent
- deletedocssite
- gitbook delete a space
- gitbook get a space
- gitbook get a team
- gitbook get an organization
- getcurrentuser
- getpageinchangerequest
- getdocssite
- gitbook list organizations
- listdocssites
- updatepageinchangerequest
- getintegration
- gitbook move a space
- gitbook import content to a space
- gitbook create a collection
- gitbook get a page in a change request
- gitbook add a space to a docs site
- uploadopenapispec
- updatespace
- getchangerequest
- listorganizations
- gitbook merge a change request
- getorganizationmember
- getpageinspace
- gitbook list change request reviewers
- platform
- gitbook list integrations
- createdocssite
- duplicatespace
- gitbook get a change request
- experience
- updateorganizationmember
- gitbook list change requests
- requestchangerequestreview
slug: gitbook-capability
source_filename: gitbook-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: GitBook API\n  description: The GitBook REST API enables you to programmatically manage your GitBook content, organizations, spaces, collections,\n    and integrations. It supports creating, updating, and deleting organizations, spaces, collections, and published docs\n    sites; managing users, teams, and access permissions; importing and exporting content; creating, listing, reviewing, merging,\n    and updating change requests; managing comments; configuring custom hostnames and URLs; and managing integrations and\n    OpenAPI documentation.\n  tags:\n  - Gitbook\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: gitbook\n    baseUri: https://api.gitbook.com/v1\n    description: GitBook API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GITBOOK_TOKEN}}'\n    resources:\n    - name: user\n      path: /user\n      operations:\n      - name: getcurrentuser\n\
  \        method: GET\n        description: GitBook Get the authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid\n      path: /users/{userId}\n      operations:\n      - name: getuserbyid\n        method: GET\n        description: GitBook Get a user by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs\n      path: /orgs\n      operations:\n      - name: listorganizations\n        method: GET\n        description: GitBook List organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid\n      path: /orgs/{organizationId}\n      operations:\n      - name: getorganization\n        method: GET\n        description: GitBook Get an organization\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateorganization\n        method: PATCH\n        description: GitBook Update an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-members\n      path: /orgs/{organizationId}/members\n      operations:\n      - name: listorganizationmembers\n        method: GET\n        description: GitBook List organization members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-members-userid\n      path: /orgs/{organizationId}/members/{userId}\n      operations:\n      - name: getorganizationmember\n        method: GET\n        description: GitBook Get an organization member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: updateorganizationmember\n        method: PATCH\n        description: GitBook Update an organization member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeorganizationmember\n        method: DELETE\n        description: GitBook Remove an organization member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-teams\n      path: /orgs/{organizationId}/teams\n      operations:\n      - name: listorganizationteams\n        method: GET\n        description: GitBook List organization teams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-teams-teamid\n      path: /orgs/{organizationId}/teams/{teamId}\n      operations:\n\
  \      - name: getorganizationteam\n        method: GET\n        description: GitBook Get a team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-spaces\n      path: /orgs/{organizationId}/spaces\n      operations:\n      - name: listspacesinorganization\n        method: GET\n        description: GitBook List spaces in an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createspaceinorganization\n        method: POST\n        description: GitBook Create a space in an organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid\n      path: /spaces/{spaceId}\n      operations:\n      - name: getspace\n        method: GET\n        description: GitBook Get a space\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatespace\n        method: PATCH\n        description: GitBook Update a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletespace\n        method: DELETE\n        description: GitBook Delete a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-duplicate\n      path: /spaces/{spaceId}/duplicate\n      operations:\n      - name: duplicatespace\n        method: POST\n        description: GitBook Duplicate a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-move\n      path: /spaces/{spaceId}/move\n      operations:\n      - name: movespace\n\
  \        method: POST\n        description: GitBook Move a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-transfer\n      path: /spaces/{spaceId}/transfer\n      operations:\n      - name: transferspace\n        method: POST\n        description: GitBook Transfer a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-restore\n      path: /spaces/{spaceId}/restore\n      operations:\n      - name: restorespace\n        method: POST\n        description: GitBook Restore a deleted space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-permissions-users\n      path: /spaces/{spaceId}/permissions/users\n      operations:\n      - name: listspaceusers\n        method: GET\n\
  \        description: GitBook List space user permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-permissions-users-userid\n      path: /spaces/{spaceId}/permissions/users/{userId}\n      operations:\n      - name: updatespaceuser\n        method: PATCH\n        description: GitBook Update space user permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removespaceuser\n        method: DELETE\n        description: GitBook Remove a space user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-content\n      path: /spaces/{spaceId}/content\n      operations:\n      - name: getspacecontent\n        method: GET\n        description: GitBook Get space content\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-content-page-pageid\n      path: /spaces/{spaceId}/content/page/{pageId}\n      operations:\n      - name: getpageinspace\n        method: GET\n        description: GitBook Get a page in a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepageinspace\n        method: PUT\n        description: GitBook Update a page in a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-content-files\n      path: /spaces/{spaceId}/content/files\n      operations:\n      - name: listfilesinspace\n        method: GET\n        description: GitBook List files in a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: orgs-organizationid-collections\n      path: /orgs/{organizationId}/collections\n      operations:\n      - name: listcollectionsinorganization\n        method: GET\n        description: GitBook List collections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcollection\n        method: POST\n        description: GitBook Create a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: collections-collectionid\n      path: /collections/{collectionId}\n      operations:\n      - name: getcollection\n        method: GET\n        description: GitBook Get a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecollection\n        method: DELETE\n        description:\
  \ GitBook Delete a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-change-requests\n      path: /spaces/{spaceId}/change-requests\n      operations:\n      - name: listchangerequests\n        method: GET\n        description: GitBook List change requests\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by change request status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createchangerequest\n        method: POST\n        description: GitBook Create a change request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-change-requests-changerequestid\n      path: /spaces/{spaceId}/change-requests/{changeRequestId}\n\
  \      operations:\n      - name: getchangerequest\n        method: GET\n        description: GitBook Get a change request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatechangerequest\n        method: PATCH\n        description: GitBook Update a change request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-change-requests-changerequestid-m\n      path: /spaces/{spaceId}/change-requests/{changeRequestId}/merge\n      operations:\n      - name: mergechangerequest\n        method: POST\n        description: GitBook Merge a change request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-change-requests-changerequestid-c\n      path: /spaces/{spaceId}/change-requests/{changeRequestId}/content\n\
  \      operations:\n      - name: getchangerequestcontent\n        method: GET\n        description: GitBook Get change request content\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-change-requests-changerequestid-c\n      path: /spaces/{spaceId}/change-requests/{changeRequestId}/content/page/{pageId}\n      operations:\n      - name: getpageinchangerequest\n        method: GET\n        description: GitBook Get a page in a change request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepageinchangerequest\n        method: PUT\n        description: GitBook Update a page in a change request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-change-requests-changerequestid-r\n     \
  \ path: /spaces/{spaceId}/change-requests/{changeRequestId}/reviewers\n      operations:\n      - name: listchangerequestreviewers\n        method: GET\n        description: GitBook List change request reviewers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: requestchangerequestreview\n        method: POST\n        description: GitBook Request a review\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-sites\n      path: /orgs/{organizationId}/sites\n      operations:\n      - name: listdocssites\n        method: GET\n        description: GitBook List docs sites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdocssite\n        method: POST\n        description: GitBook Create a docs site\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-sites-siteid\n      path: /orgs/{organizationId}/sites/{siteId}\n      operations:\n      - name: getdocssite\n        method: GET\n        description: GitBook Get a docs site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedocssite\n        method: PATCH\n        description: GitBook Update a docs site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedocssite\n        method: DELETE\n        description: GitBook Delete a docs site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-sites-siteid-site-spaces\n      path: /orgs/{organizationId}/sites/{siteId}/site-spaces\n\
  \      operations:\n      - name: listsitespaces\n        method: GET\n        description: GitBook List site spaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addsitespace\n        method: POST\n        description: GitBook Add a space to a docs site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-sites-siteid-site-spaces-sit\n      path: /orgs/{organizationId}/sites/{siteId}/site-spaces/{siteSpaceId}\n      operations:\n      - name: updatesitespace\n        method: PATCH\n        description: GitBook Update a site space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removesitespace\n        method: DELETE\n        description: GitBook Remove a space from a docs site\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-sites-siteid-site-spaces-sit\n      path: /orgs/{organizationId}/sites/{siteId}/site-spaces/{siteSpaceId}/move\n      operations:\n      - name: movesitespace\n        method: POST\n        description: GitBook Move a site space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-sites-siteid-ask\n      path: /orgs/{organizationId}/sites/{siteId}/ask\n      operations:\n      - name: asksiteai\n        method: POST\n        description: GitBook Ask a question to a site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-search\n      path: /orgs/{organizationId}/search\n      operations:\n      - name: searchorganizationcontent\n        method:\
  \ GET\n        description: GitBook Search content in an organization\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: The search query.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-openapi\n      path: /orgs/{organizationId}/openapi\n      operations:\n      - name: listopenapispecs\n        method: GET\n        description: GitBook List OpenAPI specifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadopenapispec\n        method: POST\n        description: GitBook Upload an OpenAPI specification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-openapi-specslug\n   \
  \   path: /orgs/{organizationId}/openapi/{specSlug}\n      operations:\n      - name: getopenapispec\n        method: GET\n        description: GitBook Get an OpenAPI specification\n        inputParameters:\n        - name: specSlug\n          in: path\n          type: string\n          required: true\n          description: The slug of the OpenAPI specification.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-integrations\n      path: /orgs/{organizationId}/integrations\n      operations:\n      - name: listintegrations\n        method: GET\n        description: GitBook List integrations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-organizationid-integrations-integrationid\n      path: /orgs/{organizationId}/integrations/{integrationId}\n      operations:\n      - name: getintegration\n\
  \        method: GET\n        description: GitBook Get an integration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-import-content\n      path: /spaces/{spaceId}/import/content\n      operations:\n      - name: importcontenttospace\n        method: POST\n        description: GitBook Import content to a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: urls-content\n      path: /urls/content\n      operations:\n      - name: resolvecontenturl\n        method: GET\n        description: GitBook Resolve a content URL\n        inputParameters:\n        - name: url\n          in: query\n          type: string\n          required: true\n          description: The URL to resolve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gitbook-rest\n    description: REST adapter for GitBook API.\n    resources:\n    - path: /user\n      name: getcurrentuser\n      operations:\n      - method: GET\n        name: getcurrentuser\n        description: GitBook Get the authenticated user\n        call: gitbook.getcurrentuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}\n      name: getuserbyid\n      operations:\n      - method: GET\n        name: getuserbyid\n        description: GitBook Get a user by ID\n        call: gitbook.getuserbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs\n      name: listorganizations\n      operations:\n      - method: GET\n        name: listorganizations\n        description: GitBook List organizations\n        call: gitbook.listorganizations\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /orgs/{organizationId}\n      name: getorganization\n      operations:\n      - method: GET\n        name: getorganization\n        description: GitBook Get an organization\n        call: gitbook.getorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{organizationId}\n      name: updateorganization\n      operations:\n      - method: PATCH\n        name: updateorganization\n        description: GitBook Update an organization\n        call: gitbook.updateorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{organizationId}/members\n      name: listorganizationmembers\n      operations:\n      - method: GET\n        name: listorganizationmembers\n        description: GitBook List organization members\n        call: gitbook.listorganizationmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{organizationId}/members/{userId}\n\
  \      name: getorganizationmember\n      operations:\n      - method: GET\n        name: getorganizationmember\n        description: GitBook Get an organization member\n        call: gitbook.getorganizationmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{organizationId}/members/{userId}\n      name: updateorganizationmember\n      operations:\n      - method: PATCH\n        name: updateorganizationmember\n        description: GitBook Update an organization member\n        call: gitbook.updateorganizationmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{organizationId}/members/{userId}\n      name: removeorganizationmember\n      operations:\n      - method: DELETE\n        name: removeorganizationmember\n        description: GitBook Remove an organization member\n        call: gitbook.removeorganizationmember\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /orgs/{organizationId}/teams\n      name: listorganizationteams\n      operations:\n      - method: GET\n        name: listorganizationteams\n        description: GitBook List organization teams\n        call: gitbook.listorganizationteams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{organizationId}/teams/{teamId}\n      name: getorganizationteam\n      operations:\n      - method: GET\n        name: getorganizationteam\n        description: GitBook Get a team\n        call: gitbook.getorganizationteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{organizationId}/spaces\n      name: listspacesinorganization\n      operations:\n      - method: GET\n        name: listspacesinorganization\n        description: GitBook List spaces in an organization\n        call: gitbook.listspacesinorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /orgs/{organizationId}/spaces\n      name: createspaceinorganization\n      operations:\n      - method: POST\n        name: createspaceinorganization\n        description: GitBook Create a space in an organization\n        call: gitbook.createspaceinorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}\n      name: getspace\n      operations:\n      - method: GET\n        name: getspace\n        description: GitBook Get a space\n        call: gitbook.getspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}\n      name: updatespace\n      operations:\n      - method: PATCH\n        name: updatespace\n        description: GitBook Update a space\n        call: gitbook.updatespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}\n      name: deletespace\n      operations:\n      - method: DELETE\n        name: deletespace\n\
  \        description: GitBook Delete a space\n        call: gitbook.deletespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/duplicate\n      name: duplicatespace\n      operations:\n      - method: POST\n        name: duplicatespace\n        description: GitBook Duplicate a space\n        call: gitbook.duplicatespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/move\n      name: movespace\n      operations:\n      - method: POST\n        name: movespace\n        description: GitBook Move a space\n        call: gitbook.movespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/transfer\n      name: transferspace\n      operations:\n      - method: POST\n        name: transferspace\n        description: GitBook Transfer a space\n        call: gitbook.transferspace\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /spaces/{spaceId}/restore\n      name: restorespace\n      operations:\n      - method: POST\n        name: restorespace\n        description: GitBook Restore a deleted space\n        call: gitbook.restorespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/permissions/users\n      name: listspaceusers\n      operations:\n      - method: GET\n        name: listspaceusers\n        description: GitBook List space user permissions\n        call: gitbook.listspaceusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/permissions/users/{userId}\n      name: updatespaceuser\n      operations:\n      - method: PATCH\n        name: updatespaceuser\n        description: GitBook Update space user permissions\n        call: gitbook.updatespaceuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/permissions/users/{userId}\n\
  \      name: removespaceuser\n      operations:\n      - method: DELETE\n        name: removespaceuser\n        description: GitBook Remove a space user\n        call: gitbook.removespaceuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/content\n      name: getspacecontent\n      operations:\n      - method: GET\n        name: getspacecontent\n        description: GitBook Get space content\n        call: gitbook.getspacecontent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/content/page/{pageId}\n      name: getpageinspace\n      operations:\n      - method: GET\n        name: getpageinspace\n        description: GitBook Get a page in a space\n        call: gitbook.getpageinspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/content/page/{pageId}\n      name: updatepageinspace\n      operations:\n      - method:\
  \ PUT\n        name: updatepageinspace\n        description: GitBook Update a page in a space\n        call: gitbook.updatepageinspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/content/files\n      name: listfilesinspace\n      operations:\n      - method: GET\n        name: listfilesinspace\n        description: GitBook List files in a space\n        call: gitbook.listfilesinspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{organizationId}/collections\n      name: listcollectionsinorganization\n      operations:\n      - method: GET\n        name: listcollectionsinorganization\n        description: GitBook List collections\n        call: gitbook.listcollectionsinorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{organizationId}/collections\n      name: createcollection\n      operations:\n      - method: POST\n       \
  \ name: createcollection\n        description: GitBook Create a collection\n        call: gitbook.createcollection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collections/{collectionId}\n      name: getcollection\n      operations:\n      - method: GET\n        name: getcollection\n        description: GitBook Get a collection\n        call: gitbook.getcollection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collections/{collectionId}\n      name: deletecollection\n      operations:\n      - method: DELETE\n        name: deletecollection\n        description: GitBook Delete a collection\n        call: gitbook.deletecollection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/change-requests\n      name: listchangerequests\n      operations:\n      - method: GET\n        name: listchangerequests\n        description: GitBook List change requests\n\
  \        call: gitbook.listchangerequests\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/change-requests\n      name: createchangerequest\n      operations:\n      - method: POST\n        name: createchangerequest\n        description: GitBook Create a change request\n        call: gitbook.createchangerequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/change-requests/{changeRequestId}\n      name: getchangerequest\n      operations:\n      - method: GET\n        name: getchangerequest\n        description: GitBook Get a change request\n        call: gitbook.getchangerequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/change-requests/{changeRequestId}\n      name: updatechangerequest\n      operations:\n      - method: PATCH\n        name: updatechangerequest\n        description: GitBook Update a change request\n\
  \        call: gitbook.updatechangerequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/change-requests/{changeRequestId}/merge\n      name: mergechangerequest\n      operations:\n      - method: POST\n        name: mergechangerequest\n        description: GitBook Merge a change request\n        call: gitbook.mergechangerequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/change-requests/{changeRequestId}/content\n      name: getchangerequestcontent\n      operations:\n      - method: GET\n        name: getchangerequestcontent\n        description: GitBook Get change request content\n        call: gitbook.getchangerequestcontent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/change-requests/{changeRequestId}/content/page/{pageId}\n      name: getpageinchangerequest\n      operations:\n      - method: GET\n    \
  \    name: getpageinchangerequest\n        description: GitBook Get a page in a change request\n        call: gitbook.getpageinchangerequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/change-requests/{changeRequestId}/content/page/{pageId}\n      name: updatepageinchangerequest\n      operations:\n      - method: PUT\n        name: updatepageinchangerequest\n        description: GitBook Update a page in a change request\n        call: gitbook.updatepageinchangerequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/change-requests/{changeRequestId}/reviewers\n      name: listchangerequestreviewers\n      operations:\n      - method: GET\n        name: listchangerequestreviewers\n        description: GitBook List change request reviewers\n        call: gitbook.listchangerequestreviewers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /spaces/{spaceId}/change-requests/{changeRequestId}/reviewers\n      name: requestchangerequestreview\n      operations:\n      - method: POST\n        name: requestchangerequestreview\n        description: GitBook Request a review\n        call: gitbook.requestchangerequestreview\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{organizationId}/sites\n      name: listdocssites\n      operations:\n      - method: GET\n        name: listdocssites\n        description: GitBook List docs sites\n        call: gitbook.listdocssites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{organizationId}/si\n\n# --- truncated at 32 KB (54 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/gitbook/refs/heads/main/capabilities/gitbook-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/gitbook/refs/heads/main/capabilities/gitbook-capability.yaml
tags:
- Gitbook
- API
tools:
- description: GitBook Get the authenticated user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentuser
- description: GitBook Get a user by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserbyid
- description: GitBook List organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizations
- description: GitBook Get an organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganization
- description: GitBook Update an organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateorganization
- description: GitBook List organization members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationmembers
- description: GitBook Get an organization member
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationmember
- description: GitBook Update an organization member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateorganizationmember
- description: GitBook Remove an organization member
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeorganizationmember
- description: GitBook List organization teams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationteams
- description: GitBook Get a team
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationteam
- description: GitBook List spaces in an organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listspacesinorganization
- description: GitBook Create a space in an organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createspaceinorganization
- description: GitBook Get a space
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getspace
- description: GitBook Update a space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatespace
- description: GitBook Delete a space
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletespace
- description: GitBook Duplicate a space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: duplicatespace
- description: GitBook Move a space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: movespace
- description: GitBook Transfer a space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: transferspace
- description: GitBook Restore a deleted space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restorespace
- description: GitBook List space user permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listspaceusers
- description: GitBook Update space user permissions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatespaceuser
- description: GitBook Remove a space user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removespaceuser
- description: GitBook Get space content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getspacecontent
- description: GitBook Get a page in a space
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpageinspace
- description: GitBook Update a page in a space
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepageinspace
- description: GitBook List files in a space
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfilesinspace
- description: GitBook List collections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcollectionsinorganization
- description: GitBook Create a collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcollection
- description: GitBook Get a collection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcollection
- description: GitBook Delete a collection
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecollection
- description: GitBook List change requests
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchangerequests
- description: GitBook Create a change request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchangerequest
- description: GitBook Get a change request
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchangerequest
- description: GitBook Update a change request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatechangerequest
- description: GitBook Merge a change request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: mergechangerequest
- description: GitBook Get change request content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchangerequestcontent
- description: GitBook Get a page in a change request
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpageinchangerequest
- description: GitBook Update a page in a change request
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepageinchangerequest
- description: GitBook List change request reviewers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchangerequestreviewers
- description: GitBook Request a review
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: requestchangerequestreview
- description: GitBook List docs sites
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdocssites
- description: GitBook Create a docs site
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdocssite
- description: GitBook Get a docs site
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocssite
- description: GitBook Update a docs site
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedocssite
- description: GitBook Delete a docs site
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedocssite
- description: GitBook List site spaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsitespaces
- description: GitBook Add a space to a docs site
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addsitespace
- description: GitBook Update a site space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesitespace
- description: GitBook Remove a space from a docs site
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removesitespace
- description: GitBook Move a site space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: movesitespace
- description: GitBook Ask a question to a site
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: asksiteai
- description: GitBook Search content in an organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchorganizationcontent
- description: GitBook List OpenAPI specifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listopenapispecs
- description: GitBook Upload an OpenAPI specification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadopenapispec
- description: GitBook Get an OpenAPI specification
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getopenapispec
- description: GitBook List integrations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listintegrations
- description: GitBook Get an integration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getintegration
- description: GitBook Import content to a space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: importcontenttospace
- description: GitBook Resolve a content URL
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: resolvecontenturl
---
