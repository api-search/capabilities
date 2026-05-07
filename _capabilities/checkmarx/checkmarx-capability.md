---
categories: []
consumed_apis: []
description: Unified REST API for the Checkmarx One cloud-native application security platform, providing consolidated access to SAST, SCA, KICS, and other security scanning capabilities through a single API with project management, scan orchestration, and results retrieval.
layout: capability
name: Checkmarx One API
operations:
- description: Checkmarx Obtain access token
  method: POST
  name: authenticate
  path: /auth/realms/{realm}/protocol/openid-connect/token
- description: Checkmarx List applications
  method: GET
  name: listapplications
  path: /applications
- description: Checkmarx Create an application
  method: POST
  name: createapplication
  path: /applications
- description: Checkmarx Get application details
  method: GET
  name: getapplication
  path: /applications/{applicationId}
- description: Checkmarx Update an application
  method: PUT
  name: updateapplication
  path: /applications/{applicationId}
- description: Checkmarx Delete an application
  method: DELETE
  name: deleteapplication
  path: /applications/{applicationId}
- description: Checkmarx List projects
  method: GET
  name: listprojects
  path: /projects
- description: Checkmarx Create a project
  method: POST
  name: createproject
  path: /projects
- description: Checkmarx Get project details
  method: GET
  name: getproject
  path: /projects/{projectId}
- description: Checkmarx Update a project
  method: PUT
  name: updateproject
  path: /projects/{projectId}
- description: Checkmarx Delete a project
  method: DELETE
  name: deleteproject
  path: /projects/{projectId}
- description: Checkmarx List scans
  method: GET
  name: listscans
  path: /scans
- description: Checkmarx Create a new scan
  method: POST
  name: createscan
  path: /scans
- description: Checkmarx Get scan details
  method: GET
  name: getscan
  path: /scans/{scanId}
- description: Checkmarx Cancel a scan
  method: DELETE
  name: cancelscan
  path: /scans/{scanId}
- description: Checkmarx List scan results
  method: GET
  name: listresults
  path: /results
- description: Checkmarx Get result details
  method: GET
  name: getresult
  path: /results/{resultId}
- description: Checkmarx Update result state
  method: PATCH
  name: updateresult
  path: /results/{resultId}
- description: Checkmarx Get results summary
  method: GET
  name: getresultssummary
  path: /results/summary
- description: Checkmarx List SAST queries
  method: GET
  name: listqueries
  path: /queries
- description: Checkmarx List scan presets
  method: GET
  name: listpresets
  path: /presets
- description: Checkmarx Get preset details
  method: GET
  name: getpreset
  path: /presets/{presetId}
- description: Checkmarx List groups
  method: GET
  name: listgroups
  path: /groups
- description: Checkmarx Get project scan configuration
  method: GET
  name: getprojectconfiguration
  path: /configuration/project
- description: Checkmarx Update project scan configuration
  method: PATCH
  name: updateprojectconfiguration
  path: /configuration/project
personas: []
provider_name: Checkmarx
provider_slug: checkmarx
search_terms:
- checkmarx create an application
- updateprojectconfiguration
- getproject
- checkmarx list scan results
- checkmarx get result details
- application security
- checkmarx get results summary
- api
- checkmarx get project details
- getprojectconfiguration
- devsecops
- updateresult
- checkmarx list scan presets
- vulnerability scanning
- getpreset
- checkmarx create a project
- checkmarx list sast queries
- createapplication
- deleteapplication
- createscan
- cancelscan
- updateproject
- checkmarx update project scan configuration
- listgroups
- listqueries
- listpresets
- checkmarx get preset details
- checkmarx delete an application
- security testing
- authenticate
- checkmarx obtain access token
- getapplication
- listresults
- checkmarx create a new scan
- getscan
- checkmarx list applications
- listscans
- checkmarx list scans
- checkmarx delete a project
- deleteproject
- checkmarx get scan details
- getresult
- checkmarx update result state
- checkmarx get project scan configuration
- getresultssummary
- checkmarx
- sast
- code analysis
- listapplications
- checkmarx update an application
- checkmarx update a project
- checkmarx list groups
- listprojects
- updateapplication
- checkmarx get application details
- checkmarx cancel a scan
- checkmarx list projects
- createproject
slug: checkmarx-capability
source_filename: checkmarx-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Checkmarx One API\n  description: Unified REST API for the Checkmarx One cloud-native application security platform, providing consolidated access\n    to SAST, SCA, KICS, and other security scanning capabilities through a single API with project management, scan orchestration,\n    and results retrieval.\n  tags:\n  - Checkmarx\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: checkmarx\n    baseUri: https://ast.checkmarx.net/api\n    description: Checkmarx One API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CHECKMARX_TOKEN}}'\n    resources:\n    - name: auth-realms-realm-protocol-openid-connect-token\n      path: /auth/realms/{realm}/protocol/openid-connect/token\n      operations:\n      - name: authenticate\n        method: POST\n        description: Checkmarx Obtain access token\n        inputParameters:\n        - name: realm\n          in:\
  \ path\n          type: string\n          required: true\n          description: Authentication realm name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /applications\n      operations:\n      - name: listapplications\n        method: GET\n        description: Checkmarx List applications\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          description: Number of results to return\n        - name: name\n          in: query\n          type: string\n          description: Filter by application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapplication\n        method: POST\n        description: Checkmarx\
  \ Create an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationid\n      path: /applications/{applicationId}\n      operations:\n      - name: getapplication\n        method: GET\n        description: Checkmarx Get application details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapplication\n        method: PUT\n        description: Checkmarx Update an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapplication\n        method: DELETE\n        description: Checkmarx Delete an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n\
  \      operations:\n      - name: listprojects\n        method: GET\n        description: Checkmarx List projects\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          description: Number of results to return\n        - name: name\n          in: query\n          type: string\n          description: Filter by project name\n        - name: groups\n          in: query\n          type: string\n          description: Filter by group IDs (comma-separated)\n        - name: tags-keys\n          in: query\n          type: string\n          description: Filter by tag keys\n        - name: tags-values\n          in: query\n          type: string\n          description: Filter by tag values\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n\
  \        method: POST\n        description: Checkmarx Create a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid\n      path: /projects/{projectId}\n      operations:\n      - name: getproject\n        method: GET\n        description: Checkmarx Get project details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PUT\n        description: Checkmarx Update a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproject\n        method: DELETE\n        description: Checkmarx Delete a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scans\n      path: /scans\n\
  \      operations:\n      - name: listscans\n        method: GET\n        description: Checkmarx List scans\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          description: Number of results to return\n        - name: project-id\n          in: query\n          type: string\n          description: Filter by project ID\n        - name: statuses\n          in: query\n          type: string\n          description: Filter by scan statuses (comma-separated)\n        - name: sort\n          in: query\n          type: string\n          description: Sort field and direction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createscan\n        method: POST\n        description: Checkmarx Create a new scan\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scans-scanid\n      path: /scans/{scanId}\n      operations:\n      - name: getscan\n        method: GET\n        description: Checkmarx Get scan details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancelscan\n        method: DELETE\n        description: Checkmarx Cancel a scan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results\n      path: /results\n      operations:\n      - name: listresults\n        method: GET\n        description: Checkmarx List scan results\n        inputParameters:\n        - name: scan-id\n          in: query\n          type: string\n          required: true\n          description: Scan ID to retrieve results for\n        - name: offset\n          in: query\n      \
  \    type: integer\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          description: Number of results to return\n        - name: severity\n          in: query\n          type: string\n          description: Filter by severity (comma-separated)\n        - name: state\n          in: query\n          type: string\n          description: Filter by result state (comma-separated)\n        - name: status\n          in: query\n          type: string\n          description: Filter by result status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results-resultid\n      path: /results/{resultId}\n      operations:\n      - name: getresult\n        method: GET\n        description: Checkmarx Get result details\n        inputParameters:\n        - name: resultId\n          in: path\n          type: string\n          required: true\n      \
  \    description: Result unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateresult\n        method: PATCH\n        description: Checkmarx Update result state\n        inputParameters:\n        - name: resultId\n          in: path\n          type: string\n          required: true\n          description: Result unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results-summary\n      path: /results/summary\n      operations:\n      - name: getresultssummary\n        method: GET\n        description: Checkmarx Get results summary\n        inputParameters:\n        - name: scan-id\n          in: query\n          type: string\n          required: true\n          description: Scan ID to summarize\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: queries\n      path: /queries\n      operations:\n      - name: listqueries\n        method: GET\n        description: Checkmarx List SAST queries\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          description: Number of results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: presets\n      path: /presets\n      operations:\n      - name: listpresets\n        method: GET\n        description: Checkmarx List scan presets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: presets-presetid\n      path: /presets/{presetId}\n      operations:\n      - name: getpreset\n        method:\
  \ GET\n        description: Checkmarx Get preset details\n        inputParameters:\n        - name: presetId\n          in: path\n          type: integer\n          required: true\n          description: Preset unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: Checkmarx List groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration-project\n      path: /configuration/project\n      operations:\n      - name: getprojectconfiguration\n        method: GET\n        description: Checkmarx Get project scan configuration\n        inputParameters:\n        - name: project-id\n          in: query\n          type: string\n          required: true\n          description: Project\
  \ ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateprojectconfiguration\n        method: PATCH\n        description: Checkmarx Update project scan configuration\n        inputParameters:\n        - name: project-id\n          in: query\n          type: string\n          required: true\n          description: Project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: checkmarx-rest\n    description: REST adapter for Checkmarx One API.\n    resources:\n    - path: /auth/realms/{realm}/protocol/openid-connect/token\n      name: authenticate\n      operations:\n      - method: POST\n        name: authenticate\n        description: Checkmarx Obtain access token\n        call: checkmarx.authenticate\n        with:\n          realm: rest.realm\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /applications\n      name: listapplications\n      operations:\n      - method: GET\n        name: listapplications\n        description: Checkmarx List applications\n        call: checkmarx.listapplications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications\n      name: createapplication\n      operations:\n      - method: POST\n        name: createapplication\n        description: Checkmarx Create an application\n        call: checkmarx.createapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationId}\n      name: getapplication\n      operations:\n      - method: GET\n        name: getapplication\n        description: Checkmarx Get application details\n        call: checkmarx.getapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationId}\n\
  \      name: updateapplication\n      operations:\n      - method: PUT\n        name: updateapplication\n        description: Checkmarx Update an application\n        call: checkmarx.updateapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationId}\n      name: deleteapplication\n      operations:\n      - method: DELETE\n        name: deleteapplication\n        description: Checkmarx Delete an application\n        call: checkmarx.deleteapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: Checkmarx List projects\n        call: checkmarx.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n       \
  \ description: Checkmarx Create a project\n        call: checkmarx.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Checkmarx Get project details\n        call: checkmarx.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}\n      name: updateproject\n      operations:\n      - method: PUT\n        name: updateproject\n        description: Checkmarx Update a project\n        call: checkmarx.updateproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}\n      name: deleteproject\n      operations:\n      - method: DELETE\n        name: deleteproject\n        description: Checkmarx Delete a project\n        call: checkmarx.deleteproject\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /scans\n      name: listscans\n      operations:\n      - method: GET\n        name: listscans\n        description: Checkmarx List scans\n        call: checkmarx.listscans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scans\n      name: createscan\n      operations:\n      - method: POST\n        name: createscan\n        description: Checkmarx Create a new scan\n        call: checkmarx.createscan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scans/{scanId}\n      name: getscan\n      operations:\n      - method: GET\n        name: getscan\n        description: Checkmarx Get scan details\n        call: checkmarx.getscan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scans/{scanId}\n      name: cancelscan\n      operations:\n      - method: DELETE\n        name: cancelscan\n        description: Checkmarx Cancel a scan\n\
  \        call: checkmarx.cancelscan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /results\n      name: listresults\n      operations:\n      - method: GET\n        name: listresults\n        description: Checkmarx List scan results\n        call: checkmarx.listresults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /results/{resultId}\n      name: getresult\n      operations:\n      - method: GET\n        name: getresult\n        description: Checkmarx Get result details\n        call: checkmarx.getresult\n        with:\n          resultId: rest.resultId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /results/{resultId}\n      name: updateresult\n      operations:\n      - method: PATCH\n        name: updateresult\n        description: Checkmarx Update result state\n        call: checkmarx.updateresult\n        with:\n          resultId: rest.resultId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /results/summary\n      name: getresultssummary\n      operations:\n      - method: GET\n        name: getresultssummary\n        description: Checkmarx Get results summary\n        call: checkmarx.getresultssummary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /queries\n      name: listqueries\n      operations:\n      - method: GET\n        name: listqueries\n        description: Checkmarx List SAST queries\n        call: checkmarx.listqueries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /presets\n      name: listpresets\n      operations:\n      - method: GET\n        name: listpresets\n        description: Checkmarx List scan presets\n        call: checkmarx.listpresets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /presets/{presetId}\n      name: getpreset\n      operations:\n      - method: GET\n  \
  \      name: getpreset\n        description: Checkmarx Get preset details\n        call: checkmarx.getpreset\n        with:\n          presetId: rest.presetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: Checkmarx List groups\n        call: checkmarx.listgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /configuration/project\n      name: getprojectconfiguration\n      operations:\n      - method: GET\n        name: getprojectconfiguration\n        description: Checkmarx Get project scan configuration\n        call: checkmarx.getprojectconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /configuration/project\n      name: updateprojectconfiguration\n      operations:\n      - method: PATCH\n        name: updateprojectconfiguration\n  \
  \      description: Checkmarx Update project scan configuration\n        call: checkmarx.updateprojectconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: checkmarx-mcp\n    transport: http\n    description: MCP adapter for Checkmarx One API for AI agent use.\n    tools:\n    - name: authenticate\n      description: Checkmarx Obtain access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: checkmarx.authenticate\n      with:\n        realm: tools.realm\n      inputParameters:\n      - name: realm\n        type: string\n        description: Authentication realm name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapplications\n      description: Checkmarx List applications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkmarx.listapplications\n\
  \      with:\n        offset: tools.offset\n        limit: tools.limit\n        name: tools.name\n      inputParameters:\n      - name: offset\n        type: integer\n        description: Pagination offset\n      - name: limit\n        type: integer\n        description: Number of results to return\n      - name: name\n        type: string\n        description: Filter by application name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapplication\n      description: Checkmarx Create an application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: checkmarx.createapplication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapplication\n      description: Checkmarx Get application details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkmarx.getapplication\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: updateapplication\n      description: Checkmarx Update an application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: checkmarx.updateapplication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteapplication\n      description: Checkmarx Delete an application\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: checkmarx.deleteapplication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojects\n      description: Checkmarx List projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkmarx.listprojects\n      with:\n        offset: tools.offset\n        limit: tools.limit\n        name: tools.name\n        groups: tools.groups\n        tags-keys: tools.tags-keys\n        tags-values: tools.tags-values\n      inputParameters:\n\
  \      - name: offset\n        type: integer\n        description: Pagination offset\n      - name: limit\n        type: integer\n        description: Number of results to return\n      - name: name\n        type: string\n        description: Filter by project name\n      - name: groups\n        type: string\n        description: Filter by group IDs (comma-separated)\n      - name: tags-keys\n        type: string\n        description: Filter by tag keys\n      - name: tags-values\n        type: string\n        description: Filter by tag values\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproject\n      description: Checkmarx Create a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: checkmarx.createproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Checkmarx Get project details\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: checkmarx.getproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproject\n      description: Checkmarx Update a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: checkmarx.updateproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproject\n      description: Checkmarx Delete a project\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: checkmarx.deleteproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listscans\n      description: Checkmarx List scans\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkmarx.listscans\n      with:\n        offset: tools.offset\n        limit: tools.limit\n        project-id: tools.project-id\n \
  \       statuses: tools.statuses\n        sort: tools.sort\n      inputParameters:\n      - name: offset\n        type: integer\n        description: Pagination offset\n      - name: limit\n        type: integer\n        description: Number of results to return\n      - name: project-id\n        type: string\n        description: Filter by project ID\n      - name: statuses\n        type: string\n        description: Filter by scan statuses (comma-separated)\n      - name: sort\n        type: string\n        description: Sort field and direction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createscan\n      description: Checkmarx Create a new scan\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: checkmarx.createscan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getscan\n      description: Checkmarx Get scan details\n      hints:\n        readOnly: true\n    \
  \    destructive: false\n        idempotent: true\n      call: checkmarx.getscan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelscan\n      description: Checkmarx Cancel a scan\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: checkmarx.cancelscan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listresults\n      description: Checkmarx List scan results\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkmarx.listresults\n      with:\n        scan-id: tools.scan-id\n        offset: tools.offset\n        limit: tools.limit\n        severity: tools.severity\n        state: tools.state\n        status: tools.status\n      inputParameters:\n      - name: scan-id\n        type: string\n        description: Scan ID to retrieve results for\n        required: true\n      - name: offset\n        type: integer\n\
  \        description: Pagination offset\n      - name: limit\n        type: integer\n        description: Number of results to return\n      - name: severity\n        type: string\n        description: Filter by severity (comma-separated)\n      - name: state\n        type: string\n        description: Filter by result state (comma-separated)\n      - name: status\n        type: string\n        description: Filter by result status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getresult\n      description: Checkmarx Get result details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkmarx.getresult\n      with:\n        resultId: tools.resultId\n      inputParameters:\n      - name: resultId\n        type: string\n        description: Result unique identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateresult\n      description:\
  \ Checkmarx Update result state\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: checkmarx.updateresult\n      with:\n        resultId: tools.resultId\n      inputParameters:\n      - name: resultId\n        type: string\n        description: Result unique identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getresultssummary\n      description: Checkmarx Get results summary\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkmarx.getresultssummary\n      with:\n        scan-id: tools.scan-id\n      inputParameters:\n      - name: scan-id\n        type: string\n        description: Scan ID to summarize\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listqueries\n      description: Checkmarx List SAST queries\n      hints:\n        readOnly: true\n      \
  \  destructive: false\n        idempotent: true\n      call: checkmarx.listqueries\n      with:\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: offset\n        type: integer\n        description: Pagination offset\n      - name: limit\n        type: integer\n        description: Number of results to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpresets\n      description: Checkmarx List scan presets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkmarx.listpresets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpreset\n      description: Checkmarx Get preset details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkmarx.getpreset\n      with:\n        presetId: tools.presetId\n      inputParameters:\n      - name: presetId\n        type:\
  \ integer\n        description: Preset unique identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroups\n      description: Checkmarx List groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkmarx.listgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprojectconfiguration\n      description: Checkmarx Get project scan configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: checkmarx.getprojectconfiguration\n      with:\n        project-id: tools.project-id\n      inputParameters:\n      - name: project-id\n        type: string\n        description: Project ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateprojectconfiguration\n      description: Checkmarx Update project scan configuration\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: checkmarx.updateprojectconfiguration\n      with:\n        project-id: tools.project-id\n      inputParameters:\n      - name: project-id\n        type: string\n        description: Project ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CHECKMARX_TOKEN: CHECKMARX_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/checkmarx/refs/heads/main/capabilities/checkmarx-capability.yaml
tags:
- Checkmarx
- API
tools:
- description: Checkmarx Obtain access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authenticate
- description: Checkmarx List applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplications
- description: Checkmarx Create an application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplication
- description: Checkmarx Get application details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplication
- description: Checkmarx Update an application
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapplication
- description: Checkmarx Delete an application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplication
- description: Checkmarx List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Checkmarx Create a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Checkmarx Get project details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Checkmarx Update a project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproject
- description: Checkmarx Delete a project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproject
- description: Checkmarx List scans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscans
- description: Checkmarx Create a new scan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createscan
- description: Checkmarx Get scan details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getscan
- description: Checkmarx Cancel a scan
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancelscan
- description: Checkmarx List scan results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listresults
- description: Checkmarx Get result details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresult
- description: Checkmarx Update result state
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateresult
- description: Checkmarx Get results summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresultssummary
- description: Checkmarx List SAST queries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listqueries
- description: Checkmarx List scan presets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpresets
- description: Checkmarx Get preset details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpreset
- description: Checkmarx List groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: Checkmarx Get project scan configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectconfiguration
- description: Checkmarx Update project scan configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateprojectconfiguration
---
