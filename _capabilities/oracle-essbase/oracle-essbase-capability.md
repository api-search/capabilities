---
categories: []
consumed_apis: []
description: RESTful API for managing and interacting with Oracle Essbase applications, databases, and performing analytical operations. Enables automation of Essbase resource management with endpoints for applications, databases, calculations, data loads, user management, sessions, jobs, files, scripts, filters, partitions, connections, datasources, dimensions, outline viewer, locks, scenarios, server properties, and more. All communication occurs over secured HTTP.
layout: capability
name: Oracle Essbase REST API
operations:
- description: Oracle Essbase Get About Essbase
  method: GET
  name: getaboutessbase
  path: /about
- description: Oracle Essbase Get About Essbase Instance
  method: GET
  name: getaboutessbaseinstance
  path: /about/instance
- description: Oracle Essbase List Applications
  method: GET
  name: listapplications
  path: /applications
- description: Oracle Essbase Create Application and Database
  method: POST
  name: createapplication
  path: /applications
- description: Oracle Essbase Get Application
  method: GET
  name: getapplication
  path: /applications/{applicationName}
- description: Oracle Essbase Start or Stop Application
  method: PUT
  name: startstopapplication
  path: /applications/{applicationName}
- description: Oracle Essbase Delete Application
  method: DELETE
  name: deleteapplication
  path: /applications/{applicationName}
- description: Oracle Essbase Copy Application
  method: POST
  name: copyapplication
  path: /applications/actions/copy
- description: Oracle Essbase Rename Application
  method: POST
  name: renameapplication
  path: /applications/actions/rename
- description: Oracle Essbase Get Application Tree View
  method: GET
  name: getapplicationtreeview
  path: /applications/actions/tree
- description: Oracle Essbase List Application Names
  method: GET
  name: listapplicationnames
  path: /applications/actions/name/{appVisibility}
- description: Oracle Essbase Encrypt Application
  method: POST
  name: encryptapplication
  path: /applications/{applicationName}/encrypt
- description: Oracle Essbase Decrypt Application
  method: POST
  name: decryptapplication
  path: /applications/{applicationName}/decrypt
- description: Oracle Essbase Get Encryption Info
  method: GET
  name: getencryptioninfo
  path: /applications/{applicationName}/encryptionconfig
- description: Oracle Essbase Get Application Provisioning Report
  method: GET
  name: getapplicationprovisioningreport
  path: /applications/{applicationName}/provisionReport
- description: Oracle Essbase Create Shadow Application
  method: POST
  name: createshadowapplication
  path: /applications/actions/shadowCopy
- description: Oracle Essbase Promote Shadow Application
  method: POST
  name: promoteshadowapplication
  path: /applications/actions/shadowPromote
- description: Oracle Essbase Delete Shadow Application
  method: DELETE
  name: deleteshadowapplication
  path: /applications/actions/shadowDelete/{shadowAppName}
- description: Oracle Essbase List Databases
  method: GET
  name: listdatabases
  path: /applications/{applicationName}/databases
- description: Oracle Essbase Get Database
  method: GET
  name: getdatabase
  path: /applications/{applicationName}/databases/{databaseName}
- description: Oracle Essbase Start or Stop Database
  method: PUT
  name: startstopdatabase
  path: /applications/{applicationName}/databases/{databaseName}
- description: Oracle Essbase Delete Database
  method: DELETE
  name: deletedatabase
  path: /applications/{applicationName}/databases/{databaseName}
- description: Oracle Essbase Copy Database
  method: POST
  name: copydatabase
  path: /applications/{applicationName}/databases/actions/copy
- description: Oracle Essbase Rename Database
  method: POST
  name: renamedatabase
  path: /applications/{applicationName}/databases/actions/rename
- description: Oracle Essbase List Aliases
  method: GET
  name: listaliases
  path: /applications/{applicationName}/databases/{databaseName}/aliases
- description: Oracle Essbase Get Active Alias
  method: GET
  name: getactivealias
  path: /applications/{applicationName}/databases/{databaseName}/aliases/getActiveAlias
- description: Oracle Essbase Set Active Alias
  method: PUT
  name: setactivealias
  path: /applications/{applicationName}/databases/{databaseName}/aliases/setActiveAlias
- description: Oracle Essbase Get Currency Settings
  method: GET
  name: getcurrencysettings
  path: /applications/{applicationName}/databases/{databaseName}/currencySettings
- description: Oracle Essbase Set Currency Settings
  method: POST
  name: setcurrencysettings
  path: /applications/{applicationName}/databases/{databaseName}/currencySettings
- description: Oracle Essbase Get Calculation Functions
  method: GET
  name: getcalculationfunctions
  path: /applications/{applicationName}/databases/{databaseName}/calculationFunctions
- description: Oracle Essbase Get Formula Functions
  method: GET
  name: getformulafunctions
  path: /applications/{applicationName}/databases/{databaseName}/formulaFunctions
- description: Oracle Essbase Get MDX Functions
  method: GET
  name: getmdxfunctions
  path: /applications/{applicationName}/databases/{databaseName}/mdxFunctions
- description: Oracle Essbase Execute Report Script
  method: GET
  name: executereportscript
  path: /applications/{applicationName}/databases/{databaseName}/executeReport
- description: Oracle Essbase List Jobs
  method: GET
  name: listjobs
  path: /jobs
- description: Oracle Essbase Execute Job
  method: POST
  name: executejob
  path: /jobs
- description: Oracle Essbase Get Job
  method: GET
  name: getjob
  path: /jobs/{jobId}
- description: Oracle Essbase Delete Job Record
  method: DELETE
  name: deletejob
  path: /jobs/{jobId}
- description: Oracle Essbase Rerun Job
  method: POST
  name: rerunjob
  path: /jobs/{jobId}/actions/rerun
- description: Oracle Essbase List Sessions
  method: GET
  name: listsessions
  path: /sessions
- description: Oracle Essbase Delete Session
  method: DELETE
  name: deletesession
  path: /sessions/{sessionId}
- description: Oracle Essbase Login
  method: POST
  name: login
  path: /session/login
- description: Oracle Essbase Logout
  method: POST
  name: logout
  path: /session/logout
- description: Oracle Essbase Change Password
  method: PUT
  name: changepassword
  path: /session/password
- description: Oracle Essbase List Users
  method: GET
  name: listusers
  path: /users
- description: Oracle Essbase Create User
  method: POST
  name: createuser
  path: /users
- description: Oracle Essbase Get User
  method: GET
  name: getuser
  path: /users/{userId}
- description: Oracle Essbase Update User
  method: PUT
  name: updateuser
  path: /users/{userId}
- description: Oracle Essbase Delete User
  method: DELETE
  name: deleteuser
  path: /users/{userId}
- description: Oracle Essbase List Groups
  method: GET
  name: listgroups
  path: /groups
- description: Oracle Essbase Create Group
  method: POST
  name: creategroup
  path: /groups
- description: Oracle Essbase Get Group
  method: GET
  name: getgroup
  path: /groups/{groupId}
- description: Oracle Essbase Update Group
  method: PUT
  name: updategroup
  path: /groups/{groupId}
- description: Oracle Essbase Delete Group
  method: DELETE
  name: deletegroup
  path: /groups/{groupId}
- description: Oracle Essbase List Group Members
  method: GET
  name: listgroupmembers
  path: /groups/{groupId}/members
- description: Oracle Essbase List Scripts
  method: GET
  name: listscripts
  path: /applications/{applicationName}/databases/{databaseName}/scripts
- description: Oracle Essbase Create Script
  method: POST
  name: createscript
  path: /applications/{applicationName}/databases/{databaseName}/scripts
- description: Oracle Essbase Get Script
  method: GET
  name: getscript
  path: /applications/{applicationName}/databases/{databaseName}/scripts/{scriptName}
- description: Oracle Essbase Update Script
  method: PUT
  name: updatescript
  path: /applications/{applicationName}/databases/{databaseName}/scripts/{scriptName}
- description: Oracle Essbase Delete Script
  method: DELETE
  name: deletescript
  path: /applications/{applicationName}/databases/{databaseName}/scripts/{scriptName}
- description: Oracle Essbase List Root Folders
  method: GET
  name: listrootfolders
  path: /files
personas: []
provider_name: Oracle Essbase
provider_slug: oracle-essbase
search_terms:
- getencryptioninfo
- getaboutessbaseinstance
- oracle essbase execute job
- changepassword
- getapplicationprovisioningreport
- executereportscript
- oracle essbase update user
- analytics
- multi-dimensional database
- setcurrencysettings
- oracle essbase set active alias
- oracle essbase list sessions
- getdatabase
- listrootfolders
- oracle essbase copy application
- oracle essbase get mdx functions
- login
- oracle essbase list jobs
- api
- planning
- oracle essbase get script
- olap
- oracle essbase get application
- oracle essbase get formula functions
- getjob
- oracle essbase delete group
- getuser
- listdatabases
- logout
- oracle essbase list applications
- copydatabase
- updatescript
- getcurrencysettings
- updateuser
- deleteuser
- creategroup
- encryptapplication
- oracle essbase set currency settings
- createuser
- oracle essbase get currency settings
- oracle essbase start or stop database
- oracle essbase login
- oracle essbase get about essbase instance
- oracle essbase get user
- listscripts
- oracle essbase get database
- oracle essbase encrypt application
- oracle essbase get group
- oracle essbase create user
- deletedatabase
- renameapplication
- listgroups
- startstopdatabase
- renamedatabase
- oracle essbase rename database
- oracle essbase delete script
- oracle essbase promote shadow application
- budgeting
- listusers
- getgroup
- oracle essbase get calculation functions
- updategroup
- listapplications
- oracle essbase rerun job
- oracle essbase list application names
- oracle essbase delete application
- decryptapplication
- deletescript
- listjobs
- rerunjob
- promoteshadowapplication
- createscript
- oracle essbase create shadow application
- oracle essbase update script
- oracle essbase get application tree view
- financial consolidation
- getscript
- oracle essbase list databases
- listgroupmembers
- oracle essbase create application and database
- copyapplication
- listapplicationnames
- startstopapplication
- oracle
- deleteshadowapplication
- oracle essbase delete session
- setactivealias
- deleteapplication
- oracle essbase decrypt application
- oracle essbase create script
- listsessions
- oracle essbase get job
- oracle essbase delete job record
- executejob
- oracle essbase update group
- oracle essbase list scripts
- oracle essbase list aliases
- oracle essbase delete shadow application
- getformulafunctions
- deletesession
- oracle essbase list group members
- listaliases
- oracle essbase copy database
- getmdxfunctions
- deletegroup
- oracle essbase get application provisioning report
- createapplication
- oracle essbase list groups
- essbase
- oracle essbase start or stop application
- oracle essbase get encryption info
- oracle essbase rename application
- getcalculationfunctions
- oracle essbase delete user
- oracle essbase get active alias
- getapplicationtreeview
- oracle essbase execute report script
- oracle essbase delete database
- getapplication
- oracle essbase create group
- deletejob
- business intelligence
- oracle essbase get about essbase
- getaboutessbase
- oracle essbase list root folders
- oracle essbase change password
- oracle essbase list users
- createshadowapplication
- getactivealias
- oracle essbase logout
slug: oracle-essbase-capability
source_filename: oracle-essbase-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Essbase REST API\n  description: RESTful API for managing and interacting with Oracle Essbase applications, databases, and performing analytical\n    operations. Enables automation of Essbase resource management with endpoints for applications, databases, calculations,\n    data loads, user management, sessions, jobs, files, scripts, filters, partitions, connections, datasources, dimensions,\n    outline viewer, locks, scenarios, server properties, and more. All communication occurs over secured HTTP.\n  tags:\n  - Oracle\n  - Essbase\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-essbase\n    baseUri: https://localhost:9001/essbase/rest/v1\n    description: Oracle Essbase REST API HTTP API.\n    authentication:\n      type: basic\n      username: '{{ORACLE_ESSBASE_USERNAME}}'\n      password: '{{ORACLE_ESSBASE_PASSWORD}}'\n    resources:\n    - name:\
  \ about\n      path: /about\n      operations:\n      - name: getaboutessbase\n        method: GET\n        description: Oracle Essbase Get About Essbase\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: about-instance\n      path: /about/instance\n      operations:\n      - name: getaboutessbaseinstance\n        method: GET\n        description: Oracle Essbase Get About Essbase Instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /applications\n      operations:\n      - name: listapplications\n        method: GET\n        description: Oracle Essbase List Applications\n        inputParameters:\n        - name: applicationNameForConnection\n          in: query\n          type: string\n          description: Application name for connection filtering.\n        - name: connectionName\n\
  \          in: query\n          type: string\n          description: Filter applications by connection name.\n        - name: fields\n          in: query\n          type: string\n          description: Comma-separated list of fields to return. If omitted, all fields are returned.\n        - name: filter\n          in: query\n          type: string\n          description: Wildcard filter for application names.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of applications to return. Must be 100 or less if status is included.\n        - name: offset\n          in: query\n          type: integer\n          description: Number of applications to skip from the start of the result set.\n        - name: orderBy\n          in: query\n          type: string\n          description: Sort order in format column:direction (e.g., name:asc).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: createapplication\n        method: POST\n        description: Oracle Essbase Create Application and Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname\n      path: /applications/{applicationName}\n      operations:\n      - name: getapplication\n        method: GET\n        description: Oracle Essbase Get Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: startstopapplication\n        method: PUT\n        description: Oracle Essbase Start or Stop Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapplication\n        method: DELETE\n        description: Oracle Essbase Delete Application\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-actions-copy\n      path: /applications/actions/copy\n      operations:\n      - name: copyapplication\n        method: POST\n        description: Oracle Essbase Copy Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-actions-rename\n      path: /applications/actions/rename\n      operations:\n      - name: renameapplication\n        method: POST\n        description: Oracle Essbase Rename Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-actions-tree\n      path: /applications/actions/tree\n      operations:\n      - name: getapplicationtreeview\n        method: GET\n        description: Oracle Essbase Get Application Tree View\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-actions-name-appvisibility\n      path: /applications/actions/name/{appVisibility}\n      operations:\n      - name: listapplicationnames\n        method: GET\n        description: Oracle Essbase List Application Names\n        inputParameters:\n        - name: appVisibility\n          in: path\n          type: string\n          required: true\n          description: Application visibility filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-encrypt\n      path: /applications/{applicationName}/encrypt\n      operations:\n      - name: encryptapplication\n        method: POST\n        description: Oracle Essbase Encrypt Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: applications-applicationname-decrypt\n      path: /applications/{applicationName}/decrypt\n      operations:\n      - name: decryptapplication\n        method: POST\n        description: Oracle Essbase Decrypt Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-encryptionconfig\n      path: /applications/{applicationName}/encryptionconfig\n      operations:\n      - name: getencryptioninfo\n        method: GET\n        description: Oracle Essbase Get Encryption Info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-provisionreport\n      path: /applications/{applicationName}/provisionReport\n      operations:\n      - name: getapplicationprovisioningreport\n        method: GET\n        description: Oracle Essbase\
  \ Get Application Provisioning Report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-actions-shadowcopy\n      path: /applications/actions/shadowCopy\n      operations:\n      - name: createshadowapplication\n        method: POST\n        description: Oracle Essbase Create Shadow Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-actions-shadowpromote\n      path: /applications/actions/shadowPromote\n      operations:\n      - name: promoteshadowapplication\n        method: POST\n        description: Oracle Essbase Promote Shadow Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-actions-shadowdelete-shadowappname\n      path: /applications/actions/shadowDelete/{shadowAppName}\n\
  \      operations:\n      - name: deleteshadowapplication\n        method: DELETE\n        description: Oracle Essbase Delete Shadow Application\n        inputParameters:\n        - name: shadowAppName\n          in: path\n          type: string\n          required: true\n          description: Name of the shadow application to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases\n      path: /applications/{applicationName}/databases\n      operations:\n      - name: listdatabases\n        method: GET\n        description: Oracle Essbase List Databases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases-databasen\n      path: /applications/{applicationName}/databases/{databaseName}\n      operations:\n      - name: getdatabase\n\
  \        method: GET\n        description: Oracle Essbase Get Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: startstopdatabase\n        method: PUT\n        description: Oracle Essbase Start or Stop Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedatabase\n        method: DELETE\n        description: Oracle Essbase Delete Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases-actions-c\n      path: /applications/{applicationName}/databases/actions/copy\n      operations:\n      - name: copydatabase\n        method: POST\n        description: Oracle Essbase Copy Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: applications-applicationname-databases-actions-r\n      path: /applications/{applicationName}/databases/actions/rename\n      operations:\n      - name: renamedatabase\n        method: POST\n        description: Oracle Essbase Rename Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases-databasen\n      path: /applications/{applicationName}/databases/{databaseName}/aliases\n      operations:\n      - name: listaliases\n        method: GET\n        description: Oracle Essbase List Aliases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases-databasen\n      path: /applications/{applicationName}/databases/{databaseName}/aliases/getActiveAlias\n      operations:\n      - name:\
  \ getactivealias\n        method: GET\n        description: Oracle Essbase Get Active Alias\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases-databasen\n      path: /applications/{applicationName}/databases/{databaseName}/aliases/setActiveAlias\n      operations:\n      - name: setactivealias\n        method: PUT\n        description: Oracle Essbase Set Active Alias\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases-databasen\n      path: /applications/{applicationName}/databases/{databaseName}/currencySettings\n      operations:\n      - name: getcurrencysettings\n        method: GET\n        description: Oracle Essbase Get Currency Settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n      - name: setcurrencysettings\n        method: POST\n        description: Oracle Essbase Set Currency Settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases-databasen\n      path: /applications/{applicationName}/databases/{databaseName}/calculationFunctions\n      operations:\n      - name: getcalculationfunctions\n        method: GET\n        description: Oracle Essbase Get Calculation Functions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases-databasen\n      path: /applications/{applicationName}/databases/{databaseName}/formulaFunctions\n      operations:\n      - name: getformulafunctions\n        method: GET\n        description: Oracle Essbase Get Formula Functions\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases-databasen\n      path: /applications/{applicationName}/databases/{databaseName}/mdxFunctions\n      operations:\n      - name: getmdxfunctions\n        method: GET\n        description: Oracle Essbase Get MDX Functions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases-databasen\n      path: /applications/{applicationName}/databases/{databaseName}/executeReport\n      operations:\n      - name: executereportscript\n        method: GET\n        description: Oracle Essbase Execute Report Script\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /jobs\n      operations:\n      - name: listjobs\n        method:\
  \ GET\n        description: Oracle Essbase List Jobs\n        inputParameters:\n        - name: applicationName\n          in: query\n          type: string\n          description: Filter by application name.\n        - name: databaseName\n          in: query\n          type: string\n          description: Filter by database name.\n        - name: jobtype\n          in: query\n          type: string\n          description: Filter by job type.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of jobs to return.\n        - name: offset\n          in: query\n          type: integer\n          description: Number of records to skip.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: executejob\n        method: POST\n        description: Oracle Essbase Execute Job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: jobs-jobid\n      path: /jobs/{jobId}\n      operations:\n      - name: getjob\n        method: GET\n        description: Oracle Essbase Get Job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: integer\n          required: true\n          description: Unique job identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletejob\n        method: DELETE\n        description: Oracle Essbase Delete Job Record\n        inputParameters:\n        - name: jobId\n          in: path\n          type: integer\n          required: true\n          description: Unique job identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs-jobid-actions-rerun\n      path: /jobs/{jobId}/actions/rerun\n      operations:\n     \
  \ - name: rerunjob\n        method: POST\n        description: Oracle Essbase Rerun Job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: integer\n          required: true\n          description: Unique job identifier of the job to rerun.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sessions\n      path: /sessions\n      operations:\n      - name: listsessions\n        method: GET\n        description: Oracle Essbase List Sessions\n        inputParameters:\n        - name: application\n          in: query\n          type: string\n          description: Filter by application name.\n        - name: database\n          in: query\n          type: string\n          description: Filter by database name.\n        - name: userId\n          in: query\n          type: string\n          description: Filter by user ID. If not provided, returns all sessions.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sessions-sessionid\n      path: /sessions/{sessionId}\n      operations:\n      - name: deletesession\n        method: DELETE\n        description: Oracle Essbase Delete Session\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n          description: Session identifier to terminate.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: session-login\n      path: /session/login\n      operations:\n      - name: login\n        method: POST\n        description: Oracle Essbase Login\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: session-logout\n      path: /session/logout\n      operations:\n      - name: logout\n        method:\
  \ POST\n        description: Oracle Essbase Logout\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: session-password\n      path: /session/password\n      operations:\n      - name: changepassword\n        method: PUT\n        description: Oracle Essbase Change Password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: Oracle Essbase List Users\n        inputParameters:\n        - name: expand\n          in: query\n          type: string\n          description: Include service role and groups. Values are all or none.\n        - name: filter\n          in: query\n          type: string\n          description: User ID wildcard pattern for filtering.\n        - name: limit\n          in: query\n    \
  \      type: integer\n          description: Maximum number of users to return. -1 for no limit.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Oracle Essbase Create User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid\n      path: /users/{userId}\n      operations:\n      - name: getuser\n        method: GET\n        description: Oracle Essbase Get User\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PUT\n        description: Oracle Essbase Update User\n  \
  \      inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Oracle Essbase Delete User\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: Oracle Essbase List Groups\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          description: Group name wildcard pattern for filtering.\n       \
  \ - name: limit\n          in: query\n          type: integer\n          description: Maximum number of groups to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: Oracle Essbase Create Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-groupid\n      path: /groups/{groupId}\n      operations:\n      - name: getgroup\n        method: GET\n        description: Oracle Essbase Get Group\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroup\n        method: PUT\n        description:\
  \ Oracle Essbase Update Group\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroup\n        method: DELETE\n        description: Oracle Essbase Delete Group\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups-groupid-members\n      path: /groups/{groupId}/members\n      operations:\n      - name: listgroupmembers\n        method: GET\n        description: Oracle Essbase List Group Members\n        inputParameters:\n        - name: groupId\n          in: path\n          type:\
  \ string\n          required: true\n          description: Group identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases-databasen\n      path: /applications/{applicationName}/databases/{databaseName}/scripts\n      operations:\n      - name: listscripts\n        method: GET\n        description: Oracle Essbase List Scripts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createscript\n        method: POST\n        description: Oracle Essbase Create Script\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationname-databases-databasen\n      path: /applications/{applicationName}/databases/{databaseName}/scripts/{scriptName}\n      operations:\n      - name:\
  \ getscript\n        method: GET\n        description: Oracle Essbase Get Script\n        inputParameters:\n        - name: scriptName\n          in: path\n          type: string\n          required: true\n          description: Script name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatescript\n        method: PUT\n        description: Oracle Essbase Update Script\n        inputParameters:\n        - name: scriptName\n          in: path\n          type: string\n          required: true\n          description: Script name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletescript\n        method: DELETE\n        description: Oracle Essbase Delete Script\n        inputParameters:\n        - name: scriptName\n          in: path\n          type: string\n          required: true\n          description:\
  \ Script name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files\n      path: /files\n      operations:\n      - name: listrootfolders\n        method: GET\n        description: Oracle Essbase List Root Folders\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          description: Filter the list of files.\n        - name: recursive\n          in: query\n          type: boolean\n          description: Return search results recursively.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oracle-essbase-rest\n    description: REST adapter for Oracle Essbase REST API.\n    resources:\n    - path: /about\n      name: getaboutessbase\n      operations:\n      - method: GET\n        name: getaboutessbase\n        description:\
  \ Oracle Essbase Get About Essbase\n        call: oracle-essbase.getaboutessbase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /about/instance\n      name: getaboutessbaseinstance\n      operations:\n      - method: GET\n        name: getaboutessbaseinstance\n        description: Oracle Essbase Get About Essbase Instance\n        call: oracle-essbase.getaboutessbaseinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications\n      name: listapplications\n      operations:\n      - method: GET\n        name: listapplications\n        description: Oracle Essbase List Applications\n        call: oracle-essbase.listapplications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications\n      name: createapplication\n      operations:\n      - method: POST\n        name: createapplication\n        description: Oracle Essbase Create Application and Database\n\
  \        call: oracle-essbase.createapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationName}\n      name: getapplication\n      operations:\n      - method: GET\n        name: getapplication\n        description: Oracle Essbase Get Application\n        call: oracle-essbase.getapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationName}\n      name: startstopapplication\n      operations:\n      - method: PUT\n        name: startstopapplication\n        description: Oracle Essbase Start or Stop Application\n        call: oracle-essbase.startstopapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationName}\n      name: deleteapplication\n      operations:\n      - method: DELETE\n        name: deleteapplication\n        description: Oracle Essbase Delete Application\n        call:\
  \ oracle-essbase.deleteapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/actions/copy\n      name: copyapplication\n      operations:\n      - method: POST\n        name: copyapplication\n        description: Oracle Essbase Copy Application\n        call: oracle-essbase.copyapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/actions/rename\n      name: renameapplication\n      operations:\n      - method: POST\n        name: renameapplication\n        description: Oracle Essbase Rename Application\n        call: oracle-essbase.renameapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/actions/tree\n      name: getapplicationtreeview\n      operations:\n      - method: GET\n        name: getapplicationtreeview\n        description: Oracle Essbase Get Application Tree View\n        call: oracle-essbase.getapplicationtreeview\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/actions/name/{appVisibility}\n      name: listapplicationnames\n      operations:\n      - method: GET\n        name: listapplicationnames\n        description: Oracle Essbase List Application Names\n        call: oracle-essbase.listapplicationnames\n        with:\n          appVisibility: rest.appVisibility\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationName}/encrypt\n      name: encryptapplication\n      operations:\n      - method: POST\n        name: encryptapplication\n        description: Oracle Essbase Encrypt Application\n        call: oracle-essbase.encryptapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationName}/decrypt\n      name: decryptapplication\n      operations:\n      - method: POST\n        name: decryptapplication\n        description:\
  \ Oracle Essbase Decrypt Application\n        call: oracle-essbase.decryptapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationName}/encryptionconfig\n      name: getencryptioninfo\n      operations:\n      - method: GET\n        name: getencryptioninfo\n        description: Oracle Essbase Get Encryption Info\n        call: oracle-essbase.getencryptioninfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationName}/provisionReport\n      name: getapplicationprovisioningreport\n      operations:\n      - method: GET\n        name: getapplicationprovisioningreport\n        description: Oracle Essbase Get Application Provisioning Report\n        call: oracle-essbase.getapplicationprovisioningreport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/actions/shadowCopy\n      name: createshadowapplication\n     \
  \ operations:\n      - method: POST\n        name: createshadowapplication\n        description: Oracle Essbase Create Shadow Application\n        call: oracle-essbase.createshadowapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/actions/shadowPromote\n      name: promoteshadowapplication\n      operations:\n      - method: POST\n        name: promoteshadowapplication\n        description: Oracle Essbase Promote Shadow Application\n        call: oracle-essbase.promoteshadowapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/actions/shadowDelete/{shadowAppName}\n      name: deleteshadowapplication\n      operations:\n      - method: DELETE\n        name: deleteshadowapplication\n        description: Oracle Essbase Delete Shadow Application\n        call: oracle-essbase.deleteshadowapplication\n        with:\n          shadowAppName: rest.shadowAppName\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /applications/{applicationName}/databases\n      name: listdatabases\n      operations:\n      - method: GET\n        name: listdatabases\n        description: Oracle Essbase List Databases\n        call: oracle-essbase.listdatabases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationName}/databases/{databaseName}\n      name: getdatabase\n      operations:\n      - method: GET\n        name: getdatabase\n        description: Oracle Essbase Get Database\n        call: oracle-essbase.getdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationName}/databases/{databaseName}\n      name: startstopdatabase\n      operations:\n      - method: PUT\n        name: startstopdatabase\n        description: Oracle Essbase Start or Stop Database\n        call: oracle-essbase.startstopdatabase\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /applications/{applicationName}/databases/{databaseName}\n      name: deletedatabase\n      operations:\n      - method: DELETE\n        name: deletedatabase\n        description: Oracle Essbase Delete Database\n        call: oracle-essbase.deletedatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationName}/databases/actions/copy\n      name: copydatabase\n      operations:\n      - method: POST\n        name: copydatabase\n        description: Oracle Essbase Copy Database\n        call: oracle-essbase.copydatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    \n\n# --- truncated at 32 KB (66 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/oracle-essbase/refs/heads/main/capabilities/oracle-essbase-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-essbase/refs/heads/main/capabilities/oracle-essbase-capability.yaml
tags:
- Oracle
- Essbase
- API
tools:
- description: Oracle Essbase Get About Essbase
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaboutessbase
- description: Oracle Essbase Get About Essbase Instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaboutessbaseinstance
- description: Oracle Essbase List Applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplications
- description: Oracle Essbase Create Application and Database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplication
- description: Oracle Essbase Get Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplication
- description: Oracle Essbase Start or Stop Application
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: startstopapplication
- description: Oracle Essbase Delete Application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplication
- description: Oracle Essbase Copy Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copyapplication
- description: Oracle Essbase Rename Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renameapplication
- description: Oracle Essbase Get Application Tree View
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplicationtreeview
- description: Oracle Essbase List Application Names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationnames
- description: Oracle Essbase Encrypt Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: encryptapplication
- description: Oracle Essbase Decrypt Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: decryptapplication
- description: Oracle Essbase Get Encryption Info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getencryptioninfo
- description: Oracle Essbase Get Application Provisioning Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplicationprovisioningreport
- description: Oracle Essbase Create Shadow Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createshadowapplication
- description: Oracle Essbase Promote Shadow Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: promoteshadowapplication
- description: Oracle Essbase Delete Shadow Application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteshadowapplication
- description: Oracle Essbase List Databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatabases
- description: Oracle Essbase Get Database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatabase
- description: Oracle Essbase Start or Stop Database
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: startstopdatabase
- description: Oracle Essbase Delete Database
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatabase
- description: Oracle Essbase Copy Database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copydatabase
- description: Oracle Essbase Rename Database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renamedatabase
- description: Oracle Essbase List Aliases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaliases
- description: Oracle Essbase Get Active Alias
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getactivealias
- description: Oracle Essbase Set Active Alias
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setactivealias
- description: Oracle Essbase Get Currency Settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrencysettings
- description: Oracle Essbase Set Currency Settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setcurrencysettings
- description: Oracle Essbase Get Calculation Functions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcalculationfunctions
- description: Oracle Essbase Get Formula Functions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getformulafunctions
- description: Oracle Essbase Get MDX Functions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmdxfunctions
- description: Oracle Essbase Execute Report Script
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: executereportscript
- description: Oracle Essbase List Jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: Oracle Essbase Execute Job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executejob
- description: Oracle Essbase Get Job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjob
- description: Oracle Essbase Delete Job Record
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletejob
- description: Oracle Essbase Rerun Job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rerunjob
- description: Oracle Essbase List Sessions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsessions
- description: Oracle Essbase Delete Session
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesession
- description: Oracle Essbase Login
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login
- description: Oracle Essbase Logout
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: logout
- description: Oracle Essbase Change Password
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: changepassword
- description: Oracle Essbase List Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Oracle Essbase Create User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Oracle Essbase Get User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Oracle Essbase Update User
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Oracle Essbase Delete User
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Oracle Essbase List Groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: Oracle Essbase Create Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: Oracle Essbase Get Group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: Oracle Essbase Update Group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updategroup
- description: Oracle Essbase Delete Group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: Oracle Essbase List Group Members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroupmembers
- description: Oracle Essbase List Scripts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscripts
- description: Oracle Essbase Create Script
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createscript
- description: Oracle Essbase Get Script
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getscript
- description: Oracle Essbase Update Script
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatescript
- description: Oracle Essbase Delete Script
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletescript
- description: Oracle Essbase List Root Folders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrootfolders
---
