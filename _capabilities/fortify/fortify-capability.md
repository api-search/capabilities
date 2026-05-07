---
categories: []
consumed_apis: []
description: REST API for Fortify on Demand (FoD), the cloud-based application security testing service from OpenText. Provides programmatic access to manage applications, releases, initiate static, dynamic, and mobile scans, retrieve vulnerability results, and manage tenant-level settings. Supports OAuth2 client credentials and resource owner password grant flows for authentication.
layout: capability
name: Fortify on Demand API
operations:
- description: Fortify List applications
  method: GET
  name: listapplications
  path: /api/v3/applications
- description: Fortify Create application
  method: POST
  name: createapplication
  path: /api/v3/applications
- description: Fortify Get application
  method: GET
  name: getapplication
  path: /api/v3/applications/{applicationId}
- description: Fortify Update application
  method: PUT
  name: updateapplication
  path: /api/v3/applications/{applicationId}
- description: Fortify Delete application
  method: DELETE
  name: deleteapplication
  path: /api/v3/applications/{applicationId}
- description: Fortify List application releases
  method: GET
  name: listapplicationreleases
  path: /api/v3/applications/{applicationId}/releases
- description: Fortify List application scans
  method: GET
  name: listapplicationscans
  path: /api/v3/applications/{applicationId}/scans
- description: Fortify Get issue count by severity
  method: GET
  name: getapplicationissuecountbyseverity
  path: /api/v3/applications/{applicationId}/issue-count-by-severity
- description: Fortify List application users
  method: GET
  name: listapplicationusers
  path: /api/v3/applications/{applicationId}/users
- description: Fortify List application microservices
  method: GET
  name: listapplicationmicroservices
  path: /api/v3/applications/{applicationId}/microservices
- description: Fortify Create application microservice
  method: POST
  name: createapplicationmicroservice
  path: /api/v3/applications/{applicationId}/microservices
- description: Fortify Get application vulnerability
  method: GET
  name: getapplicationvulnerability
  path: /api/v3/applications/{applicationId}/vulnerabilities/{vulnerabilityId}
- description: Fortify List application owners
  method: GET
  name: listapplicationowners
  path: /api/v3/applications/owners
- description: Fortify List open source components
  method: GET
  name: listopensourcecomponents
  path: /api/v3/applications/open-source-components
- description: Fortify List releases
  method: GET
  name: listreleases
  path: /api/v3/releases
- description: Fortify Create release
  method: POST
  name: createrelease
  path: /api/v3/releases
- description: Fortify Get release
  method: GET
  name: getrelease
  path: /api/v3/releases/{releaseId}
- description: Fortify Update release
  method: PUT
  name: updaterelease
  path: /api/v3/releases/{releaseId}
- description: Fortify Delete release
  method: DELETE
  name: deleterelease
  path: /api/v3/releases/{releaseId}
- description: Fortify List release scans
  method: GET
  name: listreleasescans
  path: /api/v3/releases/{releaseId}/scans
- description: Fortify Get release scan
  method: GET
  name: getreleasescan
  path: /api/v3/releases/{releaseId}/scans/{scanId}
- description: Fortify Get scan polling summary
  method: GET
  name: getreleasescanpollingsummary
  path: /api/v3/releases/{releaseId}/scans/{scanId}/polling-summary
- description: Fortify Download release FPR
  method: GET
  name: downloadreleasefpr
  path: /api/v3/releases/{releaseId}/fpr
- description: Fortify List vulnerability category rollups
  method: GET
  name: listreleasecategoryrollups
  path: /api/v3/releases/{releaseId}/category-rollups
- description: Fortify List assessment types
  method: GET
  name: listreleaseassessmenttypes
  path: /api/v3/releases/{releaseId}/assessment-types
- description: Fortify Get static scan options
  method: GET
  name: getreleasestaticscanoptions
  path: /api/v3/releases/{releaseId}/static-scan-options
- description: Fortify Set audit action
  method: POST
  name: setreleaseauditaction
  path: /api/v3/releases/{releaseId}/audit-action
- description: Fortify Get audit options
  method: GET
  name: getreleaseauditoptions
  path: /api/v3/releases/{releaseId}/audit-options
- description: Fortify Get DAST automated scan setup
  method: GET
  name: getdastautomatedscansetup
  path: /api/v3/releases/{releaseId}/dast-automated-scans/scan-setup
- description: Fortify Save DAST automated website scan setup
  method: PUT
  name: savedastautomatedwebsitescansetup
  path: /api/v3/releases/{releaseId}/dast-automated-scans/website-scan-setup
- description: Fortify Save DAST automated OpenAPI scan setup
  method: PUT
  name: savedastautomatedopenapiscansetup
  path: /api/v3/releases/{releaseId}/dast-automated-scans/openapi-scan-setup
- description: Fortify Start DAST automated scan
  method: POST
  name: startdastautomatedscan
  path: /api/v3/releases/{releaseId}/dast-automated-scans/start-scan
- description: Fortify Get dynamic scan setup
  method: GET
  name: getdynamicscansetup
  path: /api/v3/releases/{releaseId}/dynamic-scans/scan-setup
- description: Fortify Save dynamic scan setup
  method: PUT
  name: savedynamicscansetup
  path: /api/v3/releases/{releaseId}/dynamic-scans/scan-setup
- description: Fortify Start dynamic scan
  method: POST
  name: startdynamicscan
  path: /api/v3/releases/{releaseId}/dynamic-scans/start-scan
- description: Fortify Get mobile scan setup
  method: GET
  name: getmobilescansetup
  path: /api/v3/releases/{releaseId}/mobile-scans/scan-setup
- description: Fortify Save mobile scan setup
  method: PUT
  name: savemobilescansetup
  path: /api/v3/releases/{releaseId}/mobile-scans/scan-setup
- description: Fortify Start mobile scan
  method: POST
  name: startmobilescan
  path: /api/v3/releases/{releaseId}/mobile-scans/start-scan
- description: Fortify Start open source scan
  method: POST
  name: startopensourcescan
  path: /api/v3/releases/{releaseId}/open-source-scans/start-scan
- description: Fortify Get import scan session ID
  method: GET
  name: getreleaseimportscansessionid
  path: /api/v3/releases/{releaseId}/import-scan-session-id
- description: Fortify Download open source SBOM
  method: GET
  name: downloadopensourcesbom
  path: /api/v3/open-source-scans/{scanId}/sbom
- description: Fortify List API keys
  method: GET
  name: listapikeys
  path: /api/v3/api-keys
- description: Fortify Create API key
  method: POST
  name: createapikey
  path: /api/v3/api-keys
- description: Fortify Get API key
  method: GET
  name: getapikey
  path: /api/v3/api-keys/{apiKeyId}
- description: Fortify Update API key
  method: PUT
  name: updateapikey
  path: /api/v3/api-keys/{apiKeyId}
- description: Fortify Delete API key
  method: DELETE
  name: deleteapikey
  path: /api/v3/api-keys/{apiKeyId}
- description: Fortify List personal access tokens
  method: GET
  name: listpersonalaccesstokens
  path: /api/v3/personal-access-tokens
- description: Fortify Create personal access token
  method: POST
  name: createpersonalaccesstoken
  path: /api/v3/personal-access-tokens
- description: Fortify Get personal access token
  method: GET
  name: getpersonalaccesstoken
  path: /api/v3/personal-access-tokens/{personalAccessTokenId}
- description: Fortify Update personal access token
  method: PUT
  name: updatepersonalaccesstoken
  path: /api/v3/personal-access-tokens/{personalAccessTokenId}
- description: Fortify Delete personal access token
  method: DELETE
  name: deletepersonalaccesstoken
  path: /api/v3/personal-access-tokens/{personalAccessTokenId}
- description: Fortify List attributes
  method: GET
  name: listattributes
  path: /api/v3/attributes
- description: Fortify Create attribute
  method: POST
  name: createattribute
  path: /api/v3/attributes
- description: Fortify Update attribute
  method: PUT
  name: updateattribute
  path: /api/v3/attributes/{attributeId}
- description: Fortify Delete attribute
  method: DELETE
  name: deleteattribute
  path: /api/v3/attributes/{attributeId}
- description: Fortify List unread notifications
  method: GET
  name: listunreadnotifications
  path: /api/v3/notifications/unread
- description: Fortify List read notifications
  method: GET
  name: listreadnotifications
  path: /api/v3/notifications/read
- description: Fortify Mark notifications as read
  method: POST
  name: marknotificationsasread
  path: /api/v3/notifications/markasread
- description: Fortify List lookup items
  method: GET
  name: listlookupitems
  path: /api/v3/lookup-items
- description: Fortify Download event logs
  method: GET
  name: downloadeventlogs
  path: /api/v3/eventlogs/download
personas: []
provider_name: Fortify
provider_slug: fortify
search_terms:
- fortify list assessment types
- fortify list application microservices
- fortify save dynamic scan setup
- api
- fortify update personal access token
- updatepersonalaccesstoken
- listunreadnotifications
- fortify get dast automated scan setup
- fortify get application
- fortify list vulnerability category rollups
- fortify update release
- fortify list open source components
- listattributes
- listapplicationusers
- downloadeventlogs
- getapikey
- deletepersonalaccesstoken
- fortify save dast automated openapi scan setup
- getapplicationissuecountbyseverity
- getreleasestaticscanoptions
- listreleasescans
- fortify mark notifications as read
- savedastautomatedopenapiscansetup
- fortify delete personal access token
- fortify create api key
- getreleaseauditoptions
- getpersonalaccesstoken
- listlookupitems
- fortify create attribute
- downloadreleasefpr
- startmobilescan
- fortify list application releases
- downloadopensourcesbom
- getapplicationvulnerability
- deleterelease
- fortify get release
- listapikeys
- getreleasescan
- security testing
- fortify get release scan
- sca
- getapplication
- getdynamicscansetup
- fortify list applications
- fortify download open source sbom
- listapplicationmicroservices
- marknotificationsasread
- savedynamicscansetup
- updateapikey
- fortify download event logs
- savedastautomatedwebsitescansetup
- fortify list release scans
- fortify create application
- fortify
- fortify delete api key
- createpersonalaccesstoken
- listapplicationreleases
- listpersonalaccesstokens
- fortify start dynamic scan
- fortify list application scans
- deleteattribute
- fortify get audit options
- dast
- startopensourcescan
- devsecops
- fortify get dynamic scan setup
- fortify list personal access tokens
- deleteapplication
- setreleaseauditaction
- fortify get api key
- deleteapikey
- fortify delete application
- fortify list api keys
- fortify update application
- fortify get mobile scan setup
- listapplicationowners
- startdastautomatedscan
- getdastautomatedscansetup
- getrelease
- fortify set audit action
- fortify download release fpr
- fortify update attribute
- createrelease
- listreleaseassessmenttypes
- createapikey
- fortify create release
- getreleaseimportscansessionid
- fortify list application owners
- application security
- createattribute
- fortify get import scan session id
- fortify list application users
- fortify save mobile scan setup
- updateattribute
- vulnerability scanning
- fortify delete release
- fortify get personal access token
- startdynamicscan
- fortify get application vulnerability
- getreleasescanpollingsummary
- createapplication
- fortify list read notifications
- fortify start open source scan
- fortify start dast automated scan
- fortify get issue count by severity
- fortify save dast automated website scan setup
- fortify update api key
- listapplicationscans
- fortify get static scan options
- listreadnotifications
- fortify create application microservice
- fortify delete attribute
- savemobilescansetup
- createapplicationmicroservice
- fortify list attributes
- fortify list releases
- fortify list lookup items
- getmobilescansetup
- sast
- listapplications
- listopensourcecomponents
- updaterelease
- fortify get scan polling summary
- fortify create personal access token
- listreleases
- fortify list unread notifications
- listreleasecategoryrollups
- updateapplication
- fortify start mobile scan
slug: fortify-capability
source_filename: fortify-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Fortify on Demand API\n  description: REST API for Fortify on Demand (FoD), the cloud-based application security testing service from OpenText. Provides\n    programmatic access to manage applications, releases, initiate static, dynamic, and mobile scans, retrieve vulnerability\n    results, and manage tenant-level settings. Supports OAuth2 client credentials and resource owner password grant flows\n    for authentication.\n  tags:\n  - Fortify\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fortify\n    baseUri: https://api.ams.fortify.com\n    description: Fortify on Demand API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{FORTIFY_TOKEN}}'\n    resources:\n    - name: api-v3-applications\n      path: /api/v3/applications\n      operations:\n      - name: listapplications\n        method: GET\n        description: Fortify List applications\n  \
  \      inputParameters:\n        - name: modifiedStartDate\n          in: query\n          type: string\n          description: Filter applications modified after this date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapplication\n        method: POST\n        description: Fortify Create application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-applications-applicationid\n      path: /api/v3/applications/{applicationId}\n      operations:\n      - name: getapplication\n        method: GET\n        description: Fortify Get application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapplication\n        method: PUT\n        description: Fortify Update application\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapplication\n        method: DELETE\n        description: Fortify Delete application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-applications-applicationid-releases\n      path: /api/v3/applications/{applicationId}/releases\n      operations:\n      - name: listapplicationreleases\n        method: GET\n        description: Fortify List application releases\n        inputParameters:\n        - name: modifiedStartDate\n          in: query\n          type: string\n          description: Filter releases modified after this date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-applications-applicationid-scans\n      path: /api/v3/applications/{applicationId}/scans\n     \
  \ operations:\n      - name: listapplicationscans\n        method: GET\n        description: Fortify List application scans\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-applications-applicationid-issue-count-by\n      path: /api/v3/applications/{applicationId}/issue-count-by-severity\n      operations:\n      - name: getapplicationissuecountbyseverity\n        method: GET\n        description: Fortify Get issue count by severity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-applications-applicationid-users\n      path: /api/v3/applications/{applicationId}/users\n      operations:\n      - name: listapplicationusers\n        method: GET\n        description: Fortify List application users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: api-v3-applications-applicationid-microservices\n      path: /api/v3/applications/{applicationId}/microservices\n      operations:\n      - name: listapplicationmicroservices\n        method: GET\n        description: Fortify List application microservices\n        inputParameters:\n        - name: includeReleases\n          in: query\n          type: boolean\n          description: Whether to include release information for each microservice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapplicationmicroservice\n        method: POST\n        description: Fortify Create application microservice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-applications-applicationid-vulnerabilitie\n      path: /api/v3/applications/{applicationId}/vulnerabilities/{vulnerabilityId}\n\
  \      operations:\n      - name: getapplicationvulnerability\n        method: GET\n        description: Fortify Get application vulnerability\n        inputParameters:\n        - name: vulnerabilityId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the vulnerability\n        - name: includeFixed\n          in: query\n          type: boolean\n          description: Include fixed vulnerabilities in results\n        - name: includeSuppressed\n          in: query\n          type: boolean\n          description: Include suppressed vulnerabilities in results\n        - name: keywordSearch\n          in: query\n          type: string\n          description: Keyword search filter for vulnerabilities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-applications-owners\n      path: /api/v3/applications/owners\n      operations:\n \
  \     - name: listapplicationowners\n        method: GET\n        description: Fortify List application owners\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-applications-open-source-components\n      path: /api/v3/applications/open-source-components\n      operations:\n      - name: listopensourcecomponents\n        method: GET\n        description: Fortify List open source components\n        inputParameters:\n        - name: openSourceScanType\n          in: query\n          type: string\n          description: Type of open source scan engine\n        - name: returnTotalComponentCount\n          in: query\n          type: boolean\n          description: Whether to include total count in response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases\n      path: /api/v3/releases\n    \
  \  operations:\n      - name: listreleases\n        method: GET\n        description: Fortify List releases\n        inputParameters:\n        - name: modifiedStartDate\n          in: query\n          type: string\n          description: Filter releases modified after this date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrelease\n        method: POST\n        description: Fortify Create release\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid\n      path: /api/v3/releases/{releaseId}\n      operations:\n      - name: getrelease\n        method: GET\n        description: Fortify Get release\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterelease\n        method: PUT\n   \
  \     description: Fortify Update release\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterelease\n        method: DELETE\n        description: Fortify Delete release\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-scans\n      path: /api/v3/releases/{releaseId}/scans\n      operations:\n      - name: listreleasescans\n        method: GET\n        description: Fortify List release scans\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-scans-scanid\n      path: /api/v3/releases/{releaseId}/scans/{scanId}\n      operations:\n      - name: getreleasescan\n        method: GET\n        description: Fortify Get release scan\n        inputParameters:\n        - name:\
  \ scanId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the scan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-scans-scanid-polling-s\n      path: /api/v3/releases/{releaseId}/scans/{scanId}/polling-summary\n      operations:\n      - name: getreleasescanpollingsummary\n        method: GET\n        description: Fortify Get scan polling summary\n        inputParameters:\n        - name: scanId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the scan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-fpr\n      path: /api/v3/releases/{releaseId}/fpr\n      operations:\n      - name: downloadreleasefpr\n        method: GET\n\
  \        description: Fortify Download release FPR\n        inputParameters:\n        - name: scanType\n          in: query\n          type: string\n          description: Type of scan to download FPR for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-category-rollups\n      path: /api/v3/releases/{releaseId}/category-rollups\n      operations:\n      - name: listreleasecategoryrollups\n        method: GET\n        description: Fortify List vulnerability category rollups\n        inputParameters:\n        - name: showFixed\n          in: query\n          type: boolean\n          description: Include fixed vulnerabilities\n        - name: vulnerabilitiesSeverityType\n          in: query\n          type: string\n          description: Filter by severity type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n    - name: api-v3-releases-releaseid-assessment-types\n      path: /api/v3/releases/{releaseId}/assessment-types\n      operations:\n      - name: listreleaseassessmenttypes\n        method: GET\n        description: Fortify List assessment types\n        inputParameters:\n        - name: scanType\n          in: query\n          type: string\n          required: true\n          description: Type of scan to retrieve assessment types for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-static-scan-options\n      path: /api/v3/releases/{releaseId}/static-scan-options\n      operations:\n      - name: getreleasestaticscanoptions\n        method: GET\n        description: Fortify Get static scan options\n        inputParameters:\n        - name: technologyStack\n          in: query\n          type: string\n          description: Technology stack identifier\n\
  \        - name: languageLevel\n          in: query\n          type: string\n          description: Language level identifier\n        - name: assessmentTypeId\n          in: query\n          type: integer\n          description: Assessment type identifier\n        - name: entitlementFrequencyType\n          in: query\n          type: string\n          description: Entitlement frequency type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-audit-action\n      path: /api/v3/releases/{releaseId}/audit-action\n      operations:\n      - name: setreleaseauditaction\n        method: POST\n        description: Fortify Set audit action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-audit-options\n      path: /api/v3/releases/{releaseId}/audit-options\n      operations:\n\
  \      - name: getreleaseauditoptions\n        method: GET\n        description: Fortify Get audit options\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-dast-automated-scans-s\n      path: /api/v3/releases/{releaseId}/dast-automated-scans/scan-setup\n      operations:\n      - name: getdastautomatedscansetup\n        method: GET\n        description: Fortify Get DAST automated scan setup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-dast-automated-scans-w\n      path: /api/v3/releases/{releaseId}/dast-automated-scans/website-scan-setup\n      operations:\n      - name: savedastautomatedwebsitescansetup\n        method: PUT\n        description: Fortify Save DAST automated website scan setup\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-dast-automated-scans-o\n      path: /api/v3/releases/{releaseId}/dast-automated-scans/openapi-scan-setup\n      operations:\n      - name: savedastautomatedopenapiscansetup\n        method: PUT\n        description: Fortify Save DAST automated OpenAPI scan setup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-dast-automated-scans-s\n      path: /api/v3/releases/{releaseId}/dast-automated-scans/start-scan\n      operations:\n      - name: startdastautomatedscan\n        method: POST\n        description: Fortify Start DAST automated scan\n        inputParameters:\n        - name: networkName\n          in: query\n          type: string\n          description: Name of the Fortify on Demand Connect network to use for scanning\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-dynamic-scans-scan-set\n      path: /api/v3/releases/{releaseId}/dynamic-scans/scan-setup\n      operations:\n      - name: getdynamicscansetup\n        method: GET\n        description: Fortify Get dynamic scan setup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: savedynamicscansetup\n        method: PUT\n        description: Fortify Save dynamic scan setup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-dynamic-scans-start-sc\n      path: /api/v3/releases/{releaseId}/dynamic-scans/start-scan\n      operations:\n      - name: startdynamicscan\n        method: POST\n        description: Fortify Start dynamic scan\n        inputParameters:\n        - name: networkName\n \
  \         in: query\n          type: string\n          description: Name of the Fortify on Demand Connect network to use for scanning\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-mobile-scans-scan-setu\n      path: /api/v3/releases/{releaseId}/mobile-scans/scan-setup\n      operations:\n      - name: getmobilescansetup\n        method: GET\n        description: Fortify Get mobile scan setup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: savemobilescansetup\n        method: PUT\n        description: Fortify Save mobile scan setup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-mobile-scans-start-sca\n      path: /api/v3/releases/{releaseId}/mobile-scans/start-scan\n\
  \      operations:\n      - name: startmobilescan\n        method: POST\n        description: Fortify Start mobile scan\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          description: Scheduled start date for the scan\n        - name: assessmentTypeId\n          in: query\n          type: integer\n          description: Assessment type identifier\n        - name: frameworkType\n          in: query\n          type: string\n          description: Mobile framework type\n        - name: timeZone\n          in: query\n          type: string\n          description: Time zone for scheduled scans\n        - name: entitlementId\n          in: query\n          type: integer\n          description: Entitlement identifier\n        - name: entitlementFrequencyType\n          in: query\n          type: string\n          description: Entitlement frequency type\n        - name: isRemediationScan\n          in: query\n          type: boolean\n \
  \         description: Whether this is a remediation scan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-open-source-scans-star\n      path: /api/v3/releases/{releaseId}/open-source-scans/start-scan\n      operations:\n      - name: startopensourcescan\n        method: POST\n        description: Fortify Start open source scan\n        inputParameters:\n        - name: fragNo\n          in: query\n          type: integer\n          description: Fragment number for chunked upload\n        - name: offset\n          in: query\n          type: integer\n          description: Byte offset for chunked upload\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-releases-releaseid-import-scan-session-id\n      path: /api/v3/releases/{releaseId}/import-scan-session-id\n      operations:\n\
  \      - name: getreleaseimportscansessionid\n        method: GET\n        description: Fortify Get import scan session ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-open-source-scans-scanid-sbom\n      path: /api/v3/open-source-scans/{scanId}/sbom\n      operations:\n      - name: downloadopensourcesbom\n        method: GET\n        description: Fortify Download open source SBOM\n        inputParameters:\n        - name: scanId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the open source scan\n        - name: format\n          in: query\n          type: string\n          description: SBOM output format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-api-keys\n      path: /api/v3/api-keys\n      operations:\n      -\
  \ name: listapikeys\n        method: GET\n        description: Fortify List API keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapikey\n        method: POST\n        description: Fortify Create API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-api-keys-apikeyid\n      path: /api/v3/api-keys/{apiKeyId}\n      operations:\n      - name: getapikey\n        method: GET\n        description: Fortify Get API key\n        inputParameters:\n        - name: apiKeyId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapikey\n        method: PUT\n        description: Fortify\
  \ Update API key\n        inputParameters:\n        - name: apiKeyId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapikey\n        method: DELETE\n        description: Fortify Delete API key\n        inputParameters:\n        - name: apiKeyId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-personal-access-tokens\n      path: /api/v3/personal-access-tokens\n      operations:\n      - name: listpersonalaccesstokens\n        method: GET\n        description: Fortify List personal access tokens\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createpersonalaccesstoken\n        method: POST\n        description: Fortify Create personal access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-personal-access-tokens-personalaccesstoke\n      path: /api/v3/personal-access-tokens/{personalAccessTokenId}\n      operations:\n      - name: getpersonalaccesstoken\n        method: GET\n        description: Fortify Get personal access token\n        inputParameters:\n        - name: personalAccessTokenId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the personal access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepersonalaccesstoken\n        method: PUT\n        description:\
  \ Fortify Update personal access token\n        inputParameters:\n        - name: personalAccessTokenId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the personal access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepersonalaccesstoken\n        method: DELETE\n        description: Fortify Delete personal access token\n        inputParameters:\n        - name: personalAccessTokenId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the personal access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-attributes\n      path: /api/v3/attributes\n      operations:\n      - name: listattributes\n        method: GET\n        description: Fortify List attributes\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createattribute\n        method: POST\n        description: Fortify Create attribute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-attributes-attributeid\n      path: /api/v3/attributes/{attributeId}\n      operations:\n      - name: updateattribute\n        method: PUT\n        description: Fortify Update attribute\n        inputParameters:\n        - name: attributeId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the attribute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteattribute\n        method: DELETE\n        description: Fortify Delete attribute\n        inputParameters:\n\
  \        - name: attributeId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the attribute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-notifications-unread\n      path: /api/v3/notifications/unread\n      operations:\n      - name: listunreadnotifications\n        method: GET\n        description: Fortify List unread notifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-notifications-read\n      path: /api/v3/notifications/read\n      operations:\n      - name: listreadnotifications\n        method: GET\n        description: Fortify List read notifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-notifications-markasread\n\
  \      path: /api/v3/notifications/markasread\n      operations:\n      - name: marknotificationsasread\n        method: POST\n        description: Fortify Mark notifications as read\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-lookup-items\n      path: /api/v3/lookup-items\n      operations:\n      - name: listlookupitems\n        method: GET\n        description: Fortify List lookup items\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: true\n          description: The type of lookup items to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-eventlogs-download\n      path: /api/v3/eventlogs/download\n      operations:\n      - name: downloadeventlogs\n        method: GET\n        description: Fortify Download event\
  \ logs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fortify-rest\n    description: REST adapter for Fortify on Demand API.\n    resources:\n    - path: /api/v3/applications\n      name: listapplications\n      operations:\n      - method: GET\n        name: listapplications\n        description: Fortify List applications\n        call: fortify.listapplications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/applications\n      name: createapplication\n      operations:\n      - method: POST\n        name: createapplication\n        description: Fortify Create application\n        call: fortify.createapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/applications/{applicationId}\n      name: getapplication\n      operations:\n      - method: GET\n\
  \        name: getapplication\n        description: Fortify Get application\n        call: fortify.getapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/applications/{applicationId}\n      name: updateapplication\n      operations:\n      - method: PUT\n        name: updateapplication\n        description: Fortify Update application\n        call: fortify.updateapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/applications/{applicationId}\n      name: deleteapplication\n      operations:\n      - method: DELETE\n        name: deleteapplication\n        description: Fortify Delete application\n        call: fortify.deleteapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/applications/{applicationId}/releases\n      name: listapplicationreleases\n      operations:\n      - method: GET\n        name: listapplicationreleases\n\
  \        description: Fortify List application releases\n        call: fortify.listapplicationreleases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/applications/{applicationId}/scans\n      name: listapplicationscans\n      operations:\n      - method: GET\n        name: listapplicationscans\n        description: Fortify List application scans\n        call: fortify.listapplicationscans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/applications/{applicationId}/issue-count-by-severity\n      name: getapplicationissuecountbyseverity\n      operations:\n      - method: GET\n        name: getapplicationissuecountbyseverity\n        description: Fortify Get issue count by severity\n        call: fortify.getapplicationissuecountbyseverity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/applications/{applicationId}/users\n      name: listapplicationusers\n\
  \      operations:\n      - method: GET\n        name: listapplicationusers\n        description: Fortify List application users\n        call: fortify.listapplicationusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/applications/{applicationId}/microservices\n      name: listapplicationmicroservices\n      operations:\n      - method: GET\n        name: listapplicationmicroservices\n        description: Fortify List application microservices\n        call: fortify.listapplicationmicroservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/applications/{applicationId}/microservices\n      name: createapplicationmicroservice\n      operations:\n      - method: POST\n        name: createapplicationmicroservice\n        description: Fortify Create application microservice\n        call: fortify.createapplicationmicroservice\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /api/v3/applications/{applicationId}/vulnerabilities/{vulnerabilityId}\n      name: getapplicationvulnerability\n      operations:\n      - method: GET\n        name: getapplicationvulnerability\n        description: Fortify Get application vulnerability\n        call: fortify.getapplicationvulnerability\n        with:\n          vulnerabilityId: rest.vulnerabilityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/applications/owners\n      name: listapplicationowners\n      operations:\n      - method: GET\n        name: listapplicationowners\n        description: Fortify List application owners\n        call: fortify.listapplicationowners\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/applications/open-source-components\n      name: listopensourcecomponents\n      operations:\n      - method: GET\n        name: listopensourcecomponents\n        description: Fortify List open\
  \ source components\n        call: fortify.listopensourcecomponents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/releases\n      name: listreleases\n      operations:\n      - method: GET\n        name: listreleases\n        description: Fortify List releases\n        call: fortify.listreleases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/releases\n      name: createrelease\n      operations:\n      - method: POST\n        name: createrelease\n        description: Fortify Create release\n        call: fortify.createrelease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/releases/{releaseId}\n      name: getrelease\n      operations:\n      - method: GET\n        name: getrelease\n        description: Fortify Get release\n        call: fortify.getrelease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/releases/{releaseId}\n\
  \      name: updaterelease\n      operations:\n      - method: PUT\n        name: updaterelease\n        description: Fortify Update release\n        call: fortify.updaterelease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/releases/{releaseId}\n      name: deleterelease\n      operations:\n      - method: DELETE\n        name: deleterelease\n        description: Fortify Delete release\n        call: fortify.deleterelease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/releases/{releaseId}/scans\n      name: listreleasescans\n      operations:\n      - method: GET\n        name: listreleasescans\n        description: For\n\n# --- truncated at 32 KB (69 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/fortify/refs/heads/main/capabilities/fortify-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fortify/refs/heads/main/capabilities/fortify-capability.yaml
tags:
- Fortify
- API
tools:
- description: Fortify List applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplications
- description: Fortify Create application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplication
- description: Fortify Get application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplication
- description: Fortify Update application
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapplication
- description: Fortify Delete application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplication
- description: Fortify List application releases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationreleases
- description: Fortify List application scans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationscans
- description: Fortify Get issue count by severity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplicationissuecountbyseverity
- description: Fortify List application users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationusers
- description: Fortify List application microservices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationmicroservices
- description: Fortify Create application microservice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplicationmicroservice
- description: Fortify Get application vulnerability
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplicationvulnerability
- description: Fortify List application owners
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationowners
- description: Fortify List open source components
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listopensourcecomponents
- description: Fortify List releases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreleases
- description: Fortify Create release
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrelease
- description: Fortify Get release
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrelease
- description: Fortify Update release
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterelease
- description: Fortify Delete release
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterelease
- description: Fortify List release scans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreleasescans
- description: Fortify Get release scan
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreleasescan
- description: Fortify Get scan polling summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreleasescanpollingsummary
- description: Fortify Download release FPR
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadreleasefpr
- description: Fortify List vulnerability category rollups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreleasecategoryrollups
- description: Fortify List assessment types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreleaseassessmenttypes
- description: Fortify Get static scan options
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreleasestaticscanoptions
- description: Fortify Set audit action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setreleaseauditaction
- description: Fortify Get audit options
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreleaseauditoptions
- description: Fortify Get DAST automated scan setup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdastautomatedscansetup
- description: Fortify Save DAST automated website scan setup
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: savedastautomatedwebsitescansetup
- description: Fortify Save DAST automated OpenAPI scan setup
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: savedastautomatedopenapiscansetup
- description: Fortify Start DAST automated scan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startdastautomatedscan
- description: Fortify Get dynamic scan setup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdynamicscansetup
- description: Fortify Save dynamic scan setup
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: savedynamicscansetup
- description: Fortify Start dynamic scan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startdynamicscan
- description: Fortify Get mobile scan setup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmobilescansetup
- description: Fortify Save mobile scan setup
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: savemobilescansetup
- description: Fortify Start mobile scan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startmobilescan
- description: Fortify Start open source scan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startopensourcescan
- description: Fortify Get import scan session ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreleaseimportscansessionid
- description: Fortify Download open source SBOM
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadopensourcesbom
- description: Fortify List API keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapikeys
- description: Fortify Create API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapikey
- description: Fortify Get API key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapikey
- description: Fortify Update API key
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapikey
- description: Fortify Delete API key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapikey
- description: Fortify List personal access tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpersonalaccesstokens
- description: Fortify Create personal access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpersonalaccesstoken
- description: Fortify Get personal access token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpersonalaccesstoken
- description: Fortify Update personal access token
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepersonalaccesstoken
- description: Fortify Delete personal access token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepersonalaccesstoken
- description: Fortify List attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listattributes
- description: Fortify Create attribute
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createattribute
- description: Fortify Update attribute
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateattribute
- description: Fortify Delete attribute
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteattribute
- description: Fortify List unread notifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listunreadnotifications
- description: Fortify List read notifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreadnotifications
- description: Fortify Mark notifications as read
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: marknotificationsasread
- description: Fortify List lookup items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlookupitems
- description: Fortify Download event logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadeventlogs
---
