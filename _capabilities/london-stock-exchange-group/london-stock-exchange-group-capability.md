---
categories: []
consumed_apis: []
description: 'The World-Check One API enables developers to integrate the next generation of LSEG screening capabilities into existing workflows and internal systems (such as CRMs) in order to help streamline the processes for on-boarding, KYC and third party due diligence. The API provides, among other features: - The ability to screen entity names, with or without secondary fields such as date of birth for individuals. These names are called “cases” within the World-Check One system. - The ability to retrieve results of the screening process from the World-Check database - The ability to flag cases for On'
layout: capability
name: London Stock Exchange Group LSEG World-Check One API
operations:
- description: London Stock Exchange Group Get information about the Public API.
  method: GET
  name: getapiinfo
  path: /apiInfo
- description: London Stock Exchange Group Get all the top-level groups with their immediate descendants
  method: GET
  name: getgroups
  path: /groups
- description: London Stock Exchange Group Get a specified group including its immediate descendants
  method: GET
  name: getgroupbyid
  path: /groups/{groupId}
- description: London Stock Exchange Group Get the CaseTemplate for the given Group
  method: GET
  name: getcasetemplateforgroup
  path: /groups/{groupId}/caseTemplate
- description: London Stock Exchange Group Get the ResolutionToolkit for the given Group.
  method: GET
  name: getresolutiontoolkitforgroup
  path: /groups/{groupId}/resolutionToolkit
- description: London Stock Exchange Group Get all the ResolutionToolkits for the given Group
  method: GET
  name: getresolutiontoolkitsforgroup
  path: /groups/{groupId}/resolutionToolkits
- description: London Stock Exchange Group Get the ResolutionToolkit for a specific provider type for the given Group
  method: GET
  name: getresolutiontoolkitforgroupwithprovidertype
  path: /groups/{groupId}/resolutionToolkits/{providerType}
- description: London Stock Exchange Group Return the CaseReference (caseId, caseSystemId) for a caseId
  method: GET
  name: getcasereference
  path: /caseReferences
- description: London Stock Exchange Group Create a new case
  method: POST
  name: savecase
  path: /cases
- description: London Stock Exchange Group Perform synchronous screening for a new case
  method: POST
  name: screen
  path: /cases/screeningRequest
- description: London Stock Exchange Group Update an existing Case by its caseSystemId
  method: PUT
  name: updateexistingcase
  path: /cases/{caseSystemId}
- description: London Stock Exchange Group Partial update an existing Case by its caseSystemId
  method: PATCH
  name: partialupdatecase
  path: /cases/{caseSystemId}
- description: London Stock Exchange Group Fetch Full Case Details
  method: GET
  name: getcase
  path: /cases/{caseSystemId}
- description: London Stock Exchange Group Delete a Case
  method: DELETE
  name: deletecase
  path: /cases/{caseSystemId}
- description: London Stock Exchange Group Request full or delta screening for an existing Case.
  method: POST
  name: screencase
  path: /cases/{caseSystemId}/screeningRequest
- description: London Stock Exchange Group Enable OGS for a Case.
  method: PUT
  name: enableongoingscreening
  path: /cases/{caseSystemId}/ongoingScreening
- description: London Stock Exchange Group Disable OGS for a Case.
  method: DELETE
  name: disableongoingscreening
  path: /cases/{caseSystemId}/ongoingScreening
- description: London Stock Exchange Group Archive a Case.
  method: PUT
  name: archivecase
  path: /cases/{caseSystemId}/archive
- description: London Stock Exchange Group Unarchive a Case
  method: DELETE
  name: unarchive
  path: /cases/{caseSystemId}/archive
- description: London Stock Exchange Group Bulk Update Archive States
  method: POST
  name: archivecases
  path: /cases/bulk/archive
- description: London Stock Exchange Group Bulk Update Case Assignments
  method: POST
  name: assigncases
  path: /cases/bulk/assign
- description: London Stock Exchange Group Bulk Delete Cases
  method: POST
  name: deletecases
  path: /cases/bulk/delete
- description: London Stock Exchange Group Bulk Move Cases Between Groups
  method: POST
  name: updatecasesowner
  path: /cases/bulk/move
- description: London Stock Exchange Group Bulk Update Ongoing Screening States
  method: POST
  name: toggleongoingscreeningbyprovidertypes
  path: /cases/bulk/ongoingScreening
- description: London Stock Exchange Group Bulk Update Case Links
  method: POST
  name: linkcases
  path: /cases/bulk/link
- description: London Stock Exchange Group Get collection of Results for a Case by its caseSystemId
  method: GET
  name: getresults
  path: /cases/{caseSystemId}/results
- description: London Stock Exchange Group Add a review remark to the specified result IDs for the given case
  method: PUT
  name: reviewresults
  path: /cases/{caseSystemId}/results/review
- description: London Stock Exchange Group Resolves a list of results.
  method: PUT
  name: resolveresults
  path: /cases/{caseSystemId}/results/resolution
- description: London Stock Exchange Group Get a filtered list of AuditEvents for a Case by its caseSystemId
  method: POST
  name: getcaseauditeventsbycasesystemid
  path: /cases/{caseSystemId}/auditEvents
- description: London Stock Exchange Group Retrieves the audit event with the given 'auditEventId' belonging to the case identified by the given 'caseSystemId'.
  method: GET
  name: retrievecaseauditevent
  path: /cases/{caseSystemId}/auditEvents/{auditEventId}
- description: London Stock Exchange Group Get ongoing screening updates.
  method: POST
  name: getongoingscreeningupdates
  path: /cases/ongoingScreeningUpdates
- description: London Stock Exchange Group Assign the Case to a User.
  method: PUT
  name: assigncase
  path: /cases/{caseSystemId}/assignee
- description: London Stock Exchange Group Unassign a Case.
  method: DELETE
  name: unassigncase
  path: /cases/{caseSystemId}/assignee
- description: London Stock Exchange Group Search for Cases based on specified criteria using filter or query parameters.
  method: POST
  name: searchcases
  path: /cases/search
- description: London Stock Exchange Group User activity monitoring. Initial request.
  method: POST
  name: retrievecasesummaries
  path: /cases/summaries
- description: London Stock Exchange Group User activity monitoring. Subsequent request.
  method: POST
  name: scrollcasesummaries
  path: /cases/summaries/cursor
- description: London Stock Exchange Group Retrieve MediaCheck results
  method: POST
  name: getmediacheckdetails
  path: /cases/{caseSystemId}/mediacheck/results
- description: London Stock Exchange Group Retrieve article metadata by the article IDs
  method: POST
  name: getmediacheckarticlesmetadata
  path: /cases/{caseSystemId}/mediacheck/results/metadata
- description: London Stock Exchange Group Retrieve article metadata by the article ID
  method: GET
  name: getmediachecksinglearticlemetadata
  path: /cases/{caseSystemId}/mediacheck/results/{articleId}/metadata
- description: London Stock Exchange Group Retrieve MediaCheck news articles content
  method: POST
  name: getmediacheckresultscontent
  path: /cases/{caseSystemId}/mediacheck/results/content
- description: London Stock Exchange Group Retrieve content of single MediaCheck news article.
  method: GET
  name: getsinglearticlemediacheckcontent
  path: /cases/{caseSystemId}/mediacheck/results/{articleId}/content
- description: London Stock Exchange Group Mark all MediaCheck news articles as reviewed for a case.
  method: PUT
  name: updatearticlesrevieweddate
  path: /cases/{caseSystemId}/mediacheck/results/review
- description: London Stock Exchange Group Attach articles to a case.
  method: PUT
  name: attacharticles
  path: /cases/{caseSystemId}/mediacheck/results/attach
- description: London Stock Exchange Group Retrieve all articles attached to the case.
  method: GET
  name: retrievearticles
  path: /cases/{caseSystemId}/mediacheck/results/attach
- description: London Stock Exchange Group Detach articles from a case.
  method: DELETE
  name: detacharticles
  path: /cases/{caseSystemId}/mediacheck/results/attach
- description: London Stock Exchange Group Detach single article from a case.
  method: DELETE
  name: detacharticle
  path: /cases/{caseSystemId}/mediacheck/results/{articleId}/attach
- description: London Stock Exchange Group Save and screen multiple cases.
  method: POST
  name: saveandscreencases
  path: /cases/saveAndScreen
- description: London Stock Exchange Group Retrieve case screening status and aggregated result for multiple cases.
  method: POST
  name: screeningstatus
  path: /cases/screeningStatus
- description: London Stock Exchange Group Get Map of country codes and country names
  method: GET
  name: getcountries
  path: /reference/countries
- description: London Stock Exchange Group Get Map of nationality codes and nationality names
  method: GET
  name: getnationalities
  path: /reference/nationalities
- description: London Stock Exchange Group Get a list of available providers and their sources.
  method: GET
  name: getproviders
  path: /reference/providers
- description: London Stock Exchange Group Get identity document location types data set definition.
  method: GET
  name: get-reference-identitydocumentlocationtypes
  path: /reference/identityDocumentLocationTypes
- description: London Stock Exchange Group Retrieves all search filters that are accessible to the User.
  method: GET
  name: getsearchfilters
  path: /reference/searchFilters
- description: London Stock Exchange Group Get a profile by its ID
  method: GET
  name: getprofile
  path: /reference/profile/{id}
- description: London Stock Exchange Group Get a record by its ID
  method: GET
  name: getrecord
  path: /reference/records/{id}
- description: London Stock Exchange Group Retrieves PEP details by the given profile ID
  method: POST
  name: retrieveprofilepepdetails
  path: /reference/profile/{id}/pep
- description: London Stock Exchange Group Retrieves PEP details by the given record ID
  method: POST
  name: retrievepepdetails
  path: /reference/records/{id}/pep
- description: London Stock Exchange Group Create or update a provider source
  method: PUT
  name: createorupdateprovidersource
  path: /reference/providers/sources/{identifier}
- description: London Stock Exchange Group Maintain your Watchlist data
  method: POST
  name: savewatchlist
  path: /reference/watchlist
- description: London Stock Exchange Group Get a list of active users in the client's account.
  method: GET
  name: getusers
  path: /users
personas: []
provider_name: London Stock Exchange Group
provider_slug: london-stock-exchange-group
search_terms:
- retrieveprofilepepdetails
- london stock exchange group retrieve case screening status and aggregated result for multiple cases.
- searchcases
- api
- deletecases
- london stock exchange group create or update a provider source
- london stock exchange group create a new case
- london stock exchange group enable ogs for a case.
- getresolutiontoolkitsforgroup
- london stock exchange group perform synchronous screening for a new case
- getmediacheckresultscontent
- archivecases
- exchange
- scrollcasesummaries
- london stock exchange group retrieves pep details by the given profile id
- updateexistingcase
- london stock exchange group request full or delta screening for an existing case.
- updatearticlesrevieweddate
- london stock exchange group get a filtered list of auditevents for a case by its casesystemid
- getnationalities
- london stock exchange group get map of nationality codes and nationality names
- savewatchlist
- get reference identitydocumentlocationtypes
- unassigncase
- enableongoingscreening
- london stock exchange group mark all mediacheck news articles as reviewed for a case.
- kyc
- london stock exchange group unarchive a case
- london stock exchange group attach articles to a case.
- getgroups
- london stock exchange group user activity monitoring. initial request.
- getresolutiontoolkitforgroup
- london stock exchange group bulk update case links
- london stock exchange group get all the resolutiontoolkits for the given group
- london stock exchange group get information about the public api.
- london stock exchange group get a specified group including its immediate descendants
- london stock exchange group retrieve article metadata by the article ids
- london stock exchange group bulk update archive states
- retrievecaseauditevent
- linkcases
- unarchive
- london stock exchange group bulk update case assignments
- london stock exchange group bulk delete cases
- getcase
- london stock exchange group search for cases based on specified criteria using filter or query parameters.
- london stock exchange group get identity document location types data set definition.
- london stock exchange group get the resolutiontoolkit for a specific provider type for the given group
- london stock exchange group archive a case.
- london stock exchange group detach articles from a case.
- london stock exchange group get a profile by its id
- getcaseauditeventsbycasesystemid
- getresolutiontoolkitforgroupwithprovidertype
- market data
- getmediacheckarticlesmetadata
- london stock exchange group retrieve mediacheck news articles content
- detacharticle
- london stock exchange group get map of country codes and country names
- retrievecasesummaries
- updatecasesowner
- london stock exchange group retrieve article metadata by the article id
- london stock exchange group get a record by its id
- getongoingscreeningupdates
- london stock exchange group retrieve content of single mediacheck news article.
- stock
- london stock exchange group disable ogs for a case.
- reviewresults
- screeningstatus
- group
- london stock exchange group add a review remark to the specified result ids for the given case
- disableongoingscreening
- assigncases
- london stock exchange group get a list of active users in the client's account.
- london stock exchange group detach single article from a case.
- getrecord
- saveandscreencases
- london stock exchange group get a list of available providers and their sources.
- archivecase
- london stock exchange group return the casereference (caseid, casesystemid) for a caseid
- partialupdatecase
- london stock exchange group fetch full case details
- getprofile
- london stock exchange group retrieves the audit event with the given 'auditeventid' belonging to the case identified by the given 'casesystemid'.
- getresults
- getgroupbyid
- london stock exchange group user activity monitoring. subsequent request.
- london stock exchange group maintain your watchlist data
- getproviders
- getcountries
- london stock exchange group unassign a case.
- london stock exchange group retrieve mediacheck results
- createorupdateprovidersource
- attacharticles
- london stock exchange group partial update an existing case by its casesystemid
- london stock exchange group get the casetemplate for the given group
- london stock exchange group get all the top-level groups with their immediate descendants
- stock exchange
- london stock exchange group assign the case to a user.
- london stock exchange group update an existing case by its casesystemid
- getusers
- screen
- getsearchfilters
- london stock exchange group delete a case
- london stock exchange group get the resolutiontoolkit for the given group.
- getcasetemplateforgroup
- london stock exchange group retrieve all articles attached to the case.
- deletecase
- savecase
- london stock exchange group retrieves pep details by the given record id
- compliance
- london stock exchange group save and screen multiple cases.
- london stock exchange group retrieves all search filters that are accessible to the user.
- london stock exchange group resolves a list of results.
- getmediacheckdetails
- london stock exchange group bulk update ongoing screening states
- getsinglearticlemediacheckcontent
- resolveresults
- retrievepepdetails
- getmediachecksinglearticlemetadata
- assigncase
- detacharticles
- london stock exchange group get ongoing screening updates.
- getapiinfo
- london stock exchange group get collection of results for a case by its casesystemid
- financial
- toggleongoingscreeningbyprovidertypes
- london
- retrievearticles
- london stock exchange group bulk move cases between groups
- screencase
- getcasereference
slug: london-stock-exchange-group-capability
source_filename: london-stock-exchange-group-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: London Stock Exchange Group LSEG World-Check One API\n  description: 'The World-Check One API enables developers to integrate the next generation of LSEG screening capabilities\n    into existing workflows and internal systems (such as CRMs) in order to help streamline the processes for on-boarding,\n    KYC and third party due diligence. The API provides, among other features: - The ability to screen entity names, with\n    or without secondary fields such as date of birth for individuals. These names are called “cases” within the World-Check\n    One system. - The ability to retrieve results of the screening process from the World-Check database - The ability to\n    flag cases for On'\n  tags:\n  - London\n  - Stock\n  - Exchange\n  - Group\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: london-stock-exchange-group\n    baseUri: https://api.example.com\n    description:\
  \ London Stock Exchange Group LSEG World-Check One API HTTP API.\n    resources:\n    - name: apiinfo\n      path: /apiInfo\n      operations:\n      - name: getapiinfo\n        method: GET\n        description: London Stock Exchange Group Get information about the Public API.\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      operations:\n      - name:\
  \ getgroups\n        method: GET\n        description: London Stock Exchange Group Get all the top-level groups with their immediate descendants\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-groupid\n      path: /groups/{groupId}\n      operations:\n      - name: getgroupbyid\n        method: GET\n        description: London Stock Exchange Group Get a specified group including\
  \ its immediate descendants\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID under which we wish to retrieve children groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-groupid-casetemplate\n      path: /groups/{groupId}/caseTemplate\n      operations:\n      - name: getcasetemplateforgroup\n    \
  \    method: GET\n        description: London Stock Exchange Group Get the CaseTemplate for the given Group\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID under which we wish to manage Cases and perform screening\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-groupid-resolutiontoolkit\n      path:\
  \ /groups/{groupId}/resolutionToolkit\n      operations:\n      - name: getresolutiontoolkitforgroup\n        method: GET\n        description: London Stock Exchange Group Get the ResolutionToolkit for the given Group.\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format.\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: ID of the Group to which the resolution toolkit belongs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: groups-groupid-resolutiontoolkits\n      path: /groups/{groupId}/resolutionToolkits\n      operations:\n      - name: getresolutiontoolkitsforgroup\n        method: GET\n        description: London Stock Exchange Group Get all the ResolutionToolkits for the given Group\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: ID of the Group to which the resolution\
  \ toolkits belong.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-groupid-resolutiontoolkits-providertype\n      path: /groups/{groupId}/resolutionToolkits/{providerType}\n      operations:\n      - name: getresolutiontoolkitforgroupwithprovidertype\n        method: GET\n        description: London Stock Exchange Group Get the ResolutionToolkit for a specific provider type for the given Group\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC\
  \ 1123' format\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: ID of the Group to which the resolution toolkit belongs.\n        - name: providerType\n          in: path\n          type: string\n          required: true\n          description: Provider type for which the resolution toolkit applies.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: casereferences\n      path: /caseReferences\n      operations:\n      - name: getcasereference\n        method: GET\n        description: London Stock Exchange Group Return the CaseReference (caseId, caseSystemId) for a caseId\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n       \
  \     and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: caseId\n          in: query\n          type: string\n          required: true\n          description: Case ID provided by the client or else generated by the system for the client\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases\n      path: /cases\n      operations:\n      - name: savecase\n        method: POST\n        description: London Stock Exchange Group Create a new case\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n\
  \            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json')\n        - name: Content-Length\n          in: header\n          type: string\n          required: true\n          description: The length of the request body in octets (8-bit bytes)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-screeningrequest\n      path: /cases/screeningRequest\n      operations:\n      - name: screen\n        method: POST\n        description: London Stock Exchange Group Perform synchronous screening for a new case\n       \
  \ inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json')\n        - name: Content-Length\n          in: header\n          type: string\n          required: true\n          description: The length of the request body in octets (8-bit bytes)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: cases-casesystemid\n      path: /cases/{caseSystemId}\n      operations:\n      - name: updateexistingcase\n        method: PUT\n        description: London Stock Exchange Group Update an existing Case by its caseSystemId\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json')\n        - name: Content-Length\n          in: header\n \
  \         type: string\n          required: true\n          description: The length of the request body in octets (8-bit bytes)\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: System generated ID for the Case\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: partialupdatecase\n        method: PATCH\n        description: London Stock Exchange Group Partial update an existing Case by its caseSystemId\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n       \
  \   description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json')\n        - name: Content-Length\n          in: header\n          type: string\n          required: true\n          description: The length of the request body in octets (8-bit bytes)\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: System generated ID for the Case\n        - name: screen\n          in: query\n          type: string\n          description: Screen mode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getcase\n        method: GET\n        description: London Stock Exchange Group Fetch Full Case Details\n        inputParameters:\n       \
  \ - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: System generated ID for the Case\n        - name: aggregatedSummary\n          in: query\n          type: string\n          description: Flag to enable aggregated summary for case\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecase\n        method: DELETE\n        description: London Stock\
  \ Exchange Group Delete a Case\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: System generated ID for the Case\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-casesystemid-screeningrequest\n      path: /cases/{caseSystemId}/screeningRequest\n      operations:\n      - name: screencase\n        method: POST\n\
  \        description: London Stock Exchange Group Request full or delta screening for an existing Case.\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format.\n        - name: Content-Type\n          in: header\n          type: string\n          description: The media type of the request (e.g., 'application/json').\n        - name: Content-Length\n          in: header\n          type: string\n          description: The length of the request body in octets (8-bit bytes).\n        - name: caseSystemId\n          in: path\n       \
  \   type: string\n          required: true\n          description: System generated ID for the Case.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-casesystemid-ongoingscreening\n      path: /cases/{caseSystemId}/ongoingScreening\n      operations:\n      - name: enableongoingscreening\n        method: PUT\n        description: London Stock Exchange Group Enable OGS for a Case.\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format.\n\
  \        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json').\n        - name: Content-Length\n          in: header\n          type: string\n          required: true\n          description: The length of the request body in octets (8-bit bytes).\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: System generated ID for the Case.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disableongoingscreening\n        method: DELETE\n        description: London Stock Exchange Group Disable OGS for a Case.\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm',\
  \ 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format.\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json').\n        - name: Content-Length\n          in: header\n          type: string\n          required: true\n          description: The length of the request body in octets (8-bit bytes).\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: System generated ID for the Case.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-casesystemid-archive\n\
  \      path: /cases/{caseSystemId}/archive\n      operations:\n      - name: archivecase\n        method: PUT\n        description: London Stock Exchange Group Archive a Case.\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format.\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: System generated ID for the Case\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unarchive\n\
  \        method: DELETE\n        description: London Stock Exchange Group Unarchive a Case\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: System generated ID for the Case\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-bulk-archive\n      path: /cases/bulk/archive\n      operations:\n      - name: archivecases\n\
  \        method: POST\n        description: London Stock Exchange Group Bulk Update Archive States\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json')\n        - name: Content-Length\n          in: header\n          type: string\n          required: true\n          description: The length of the request body in octets (8-bit bytes)\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-bulk-assign\n      path: /cases/bulk/assign\n      operations:\n      - name: assigncases\n        method: POST\n        description: London Stock Exchange Group Bulk Update Case Assignments\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json')\n\
  \        - name: Content-Length\n          in: header\n          type: string\n          required: true\n          description: The length of the request body in octets (8-bit bytes)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-bulk-delete\n      path: /cases/bulk/delete\n      operations:\n      - name: deletecases\n        method: POST\n        description: London Stock Exchange Group Bulk Delete Cases\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated\
  \ in 'RFC 1123' format\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json')\n        - name: Content-Length\n          in: header\n          type: string\n          required: true\n          description: The length of the request body in octets (8-bit bytes)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-bulk-move\n      path: /cases/bulk/move\n      operations:\n      - name: updatecasesowner\n        method: POST\n        description: London Stock Exchange Group Bulk Move Cases Between Groups\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication\
  \ details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json')\n        - name: Content-Length\n          in: header\n          type: string\n          required: true\n          description: The length of the request body in octets (8-bit bytes)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-bulk-ongoingscreening\n      path: /cases/bulk/ongoingScreening\n      operations:\n      - name: toggleongoingscreeningbyprovidertypes\n        method: POST\n        description: London Stock Exchange Group Bulk Update Ongoing Screening States\n    \
  \    inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json')\n        - name: Content-Length\n          in: header\n          type: string\n          required: true\n          description: The length of the request body in octets (8-bit bytes)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: cases-bulk-link\n      path: /cases/bulk/link\n      operations:\n      - name: linkcases\n        method: POST\n        description: London Stock Exchange Group Bulk Update Case Links\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json')\n        - name: Content-Length\n          in: header\n          type: string\n          required:\
  \ true\n          description: The length of the request body in octets (8-bit bytes)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-casesystemid-results\n      path: /cases/{caseSystemId}/results\n      operations:\n      - name: getresults\n        method: GET\n        description: London Stock Exchange Group Get collection of Results for a Case by its caseSystemId\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format\n        -\
  \ name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: System generated ID for a Case\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-casesystemid-results-review\n      path: /cases/{caseSystemId}/results/review\n      operations:\n      - name: reviewresults\n        method: PUT\n        description: London Stock Exchange Group Add a review remark to the specified result IDs for the given case\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description:\
  \ The date and time at which the message was originated in 'RFC 1123' format\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: The media type of the request (e.g., 'application/json')\n        - name: Content-Length\n          in: header\n          type: string\n          required: true\n          description: The length of the request body in octets (8-bit bytes)\n        - name: caseSystemId\n          in: path\n          type: string\n          required: true\n          description: System generated ID for the Case\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-casesystemid-results-resolution\n      path: /cases/{caseSystemId}/results/resolution\n      operations:\n      - name: resolveresults\n        method: PUT\n        description: London Stock Exchange Group Resolves a list of results.\n        inputParameters:\n\
  \        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: The authorization credentials including 'keyId', 'algorithm', 'headers', 'signature' (see 'Security\n            and Authentication details' documentation section for more d\n        - name: Date\n          in: header\n          type: string\n          required: true\n          description: The date and time at which the message was originated in 'RFC 1123' format.\n        - name: Content-Type\n          in: header\n          type: string\n          require\n\n# --- truncated at 32 KB (122 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/london-stock-exchange-group/refs/heads/main/capabilities/london-stock-exchange-group-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/london-stock-exchange-group/refs/heads/main/capabilities/london-stock-exchange-group-capability.yaml
tags:
- London
- Stock
- Exchange
- Group
- API
tools:
- description: London Stock Exchange Group Get information about the Public API.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapiinfo
- description: London Stock Exchange Group Get all the top-level groups with their immediate descendants
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroups
- description: London Stock Exchange Group Get a specified group including its immediate descendants
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupbyid
- description: London Stock Exchange Group Get the CaseTemplate for the given Group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcasetemplateforgroup
- description: London Stock Exchange Group Get the ResolutionToolkit for the given Group.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresolutiontoolkitforgroup
- description: London Stock Exchange Group Get all the ResolutionToolkits for the given Group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresolutiontoolkitsforgroup
- description: London Stock Exchange Group Get the ResolutionToolkit for a specific provider type for the given Group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresolutiontoolkitforgroupwithprovidertype
- description: London Stock Exchange Group Return the CaseReference (caseId, caseSystemId) for a caseId
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcasereference
- description: London Stock Exchange Group Create a new case
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: savecase
- description: London Stock Exchange Group Perform synchronous screening for a new case
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: screen
- description: London Stock Exchange Group Update an existing Case by its caseSystemId
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateexistingcase
- description: London Stock Exchange Group Partial update an existing Case by its caseSystemId
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: partialupdatecase
- description: London Stock Exchange Group Fetch Full Case Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcase
- description: London Stock Exchange Group Delete a Case
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecase
- description: London Stock Exchange Group Request full or delta screening for an existing Case.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: screencase
- description: London Stock Exchange Group Enable OGS for a Case.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: enableongoingscreening
- description: London Stock Exchange Group Disable OGS for a Case.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: disableongoingscreening
- description: London Stock Exchange Group Archive a Case.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: archivecase
- description: London Stock Exchange Group Unarchive a Case
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: unarchive
- description: London Stock Exchange Group Bulk Update Archive States
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: archivecases
- description: London Stock Exchange Group Bulk Update Case Assignments
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assigncases
- description: London Stock Exchange Group Bulk Delete Cases
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletecases
- description: London Stock Exchange Group Bulk Move Cases Between Groups
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecasesowner
- description: London Stock Exchange Group Bulk Update Ongoing Screening States
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: toggleongoingscreeningbyprovidertypes
- description: London Stock Exchange Group Bulk Update Case Links
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: linkcases
- description: London Stock Exchange Group Get collection of Results for a Case by its caseSystemId
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresults
- description: London Stock Exchange Group Add a review remark to the specified result IDs for the given case
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reviewresults
- description: London Stock Exchange Group Resolves a list of results.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resolveresults
- description: London Stock Exchange Group Get a filtered list of AuditEvents for a Case by its caseSystemId
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getcaseauditeventsbycasesystemid
- description: London Stock Exchange Group Retrieves the audit event with the given 'auditEventId' belonging to the case identified by the given 'caseSystemId'.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievecaseauditevent
- description: London Stock Exchange Group Get ongoing screening updates.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getongoingscreeningupdates
- description: London Stock Exchange Group Assign the Case to a User.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: assigncase
- description: London Stock Exchange Group Unassign a Case.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: unassigncase
- description: London Stock Exchange Group Search for Cases based on specified criteria using filter or query parameters.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchcases
- description: London Stock Exchange Group User activity monitoring. Initial request.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: retrievecasesummaries
- description: London Stock Exchange Group User activity monitoring. Subsequent request.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: scrollcasesummaries
- description: London Stock Exchange Group Retrieve MediaCheck results
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getmediacheckdetails
- description: London Stock Exchange Group Retrieve article metadata by the article IDs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getmediacheckarticlesmetadata
- description: London Stock Exchange Group Retrieve article metadata by the article ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmediachecksinglearticlemetadata
- description: London Stock Exchange Group Retrieve MediaCheck news articles content
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getmediacheckresultscontent
- description: London Stock Exchange Group Retrieve content of single MediaCheck news article.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsinglearticlemediacheckcontent
- description: London Stock Exchange Group Mark all MediaCheck news articles as reviewed for a case.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatearticlesrevieweddate
- description: London Stock Exchange Group Attach articles to a case.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: attacharticles
- description: London Stock Exchange Group Retrieve all articles attached to the case.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievearticles
- description: London Stock Exchange Group Detach articles from a case.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: detacharticles
- description: London Stock Exchange Group Detach single article from a case.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: detacharticle
- description: London Stock Exchange Group Save and screen multiple cases.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: saveandscreencases
- description: London Stock Exchange Group Retrieve case screening status and aggregated result for multiple cases.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: screeningstatus
- description: London Stock Exchange Group Get Map of country codes and country names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcountries
- description: London Stock Exchange Group Get Map of nationality codes and nationality names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnationalities
- description: London Stock Exchange Group Get a list of available providers and their sources.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproviders
- description: London Stock Exchange Group Get identity document location types data set definition.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-reference-identitydocumentlocationtypes
- description: London Stock Exchange Group Retrieves all search filters that are accessible to the User.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsearchfilters
- description: London Stock Exchange Group Get a profile by its ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprofile
- description: London Stock Exchange Group Get a record by its ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrecord
- description: London Stock Exchange Group Retrieves PEP details by the given profile ID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: retrieveprofilepepdetails
- description: London Stock Exchange Group Retrieves PEP details by the given record ID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: retrievepepdetails
- description: London Stock Exchange Group Create or update a provider source
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createorupdateprovidersource
- description: London Stock Exchange Group Maintain your Watchlist data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: savewatchlist
- description: London Stock Exchange Group Get a list of active users in the client's account.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusers
---
