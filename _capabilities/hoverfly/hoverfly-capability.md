---
categories: []
consumed_apis: []
description: Hoverfly's Admin API provides programmatic control of a Hoverfly instance, including simulation management, mode and middleware configuration, journal and diff inspection, state management, caching, logging, templating data sources, and post-serve actions.
layout: capability
name: Hoverfly Admin API
operations:
- description: Get simulation
  method: GET
  name: getsimulation
  path: /api/v2/simulation
- description: Replace simulation
  method: PUT
  name: replacesimulation
  path: /api/v2/simulation
- description: Append simulation
  method: POST
  name: appendsimulation
  path: /api/v2/simulation
- description: Clear simulation
  method: DELETE
  name: clearsimulation
  path: /api/v2/simulation
- description: Get simulation JSON schema
  method: GET
  name: getsimulationschema
  path: /api/v2/simulation/schema
- description: Get Hoverfly configuration
  method: GET
  name: gethoverfly
  path: /api/v2/hoverfly
- description: Get CORS settings
  method: GET
  name: getcors
  path: /api/v2/hoverfly/cors
- description: Get destination
  method: GET
  name: getdestination
  path: /api/v2/hoverfly/destination
- description: Set destination
  method: PUT
  name: setdestination
  path: /api/v2/hoverfly/destination
- description: Get middleware
  method: GET
  name: getmiddleware
  path: /api/v2/hoverfly/middleware
- description: Update middleware
  method: PUT
  name: setmiddleware
  path: /api/v2/hoverfly/middleware
- description: Get mode
  method: GET
  name: getmode
  path: /api/v2/hoverfly/mode
- description: Set mode
  method: PUT
  name: setmode
  path: /api/v2/hoverfly/mode
- description: Get version
  method: GET
  name: getversion
  path: /api/v2/hoverfly/version
- description: Get usage metrics
  method: GET
  name: getusage
  path: /api/v2/hoverfly/usage
- description: Get upstream proxy
  method: GET
  name: getupstreamproxy
  path: /api/v2/hoverfly/upstream-proxy
- description: Get PAC file
  method: GET
  name: getpac
  path: /api/v2/hoverfly/pac
- description: Set PAC file
  method: PUT
  name: setpac
  path: /api/v2/hoverfly/pac
- description: Delete PAC file
  method: DELETE
  name: deletepac
  path: /api/v2/hoverfly/pac
- description: List post-serve actions
  method: GET
  name: listpostserveactions
  path: /api/v2/hoverfly/post-serve-action
- description: Create or update post-serve action
  method: PUT
  name: upsertpostserveaction
  path: /api/v2/hoverfly/post-serve-action
- description: Delete post-serve action
  method: DELETE
  name: deletepostserveaction
  path: /api/v2/hoverfly/post-serve-action/{actionName}
- description: Get cache
  method: GET
  name: getcache
  path: /api/v2/cache
- description: Clear cache
  method: DELETE
  name: clearcache
  path: /api/v2/cache
- description: Get logs
  method: GET
  name: getlogs
  path: /api/v2/logs
- description: Get journal
  method: GET
  name: getjournal
  path: /api/v2/journal
- description: Filter journal
  method: POST
  name: filterjournal
  path: /api/v2/journal
- description: Clear journal
  method: DELETE
  name: clearjournal
  path: /api/v2/journal
- description: List journal indexes
  method: GET
  name: listjournalindexes
  path: /api/v2/journal/index
- description: Create journal index
  method: POST
  name: createjournalindex
  path: /api/v2/journal/index
- description: Delete journal index
  method: DELETE
  name: deletejournalindex
  path: /api/v2/journal/index/{indexName}
- description: Get state
  method: GET
  name: getstate
  path: /api/v2/state
- description: Replace state
  method: PUT
  name: replacestate
  path: /api/v2/state
- description: Patch state
  method: PATCH
  name: patchstate
  path: /api/v2/state
- description: Clear state
  method: DELETE
  name: clearstate
  path: /api/v2/state
- description: Get diff reports
  method: GET
  name: getdiff
  path: /api/v2/diff
- description: Filter diff reports
  method: POST
  name: filterdiff
  path: /api/v2/diff
- description: Clear diff reports
  method: DELETE
  name: cleardiff
  path: /api/v2/diff
- description: List CSV data sources
  method: GET
  name: listcsvdatasources
  path: /api/v2/hoverfly/templating-data-source/csv
- description: Upsert CSV data source
  method: PUT
  name: upsertcsvdatasource
  path: /api/v2/hoverfly/templating-data-source/csv
- description: Delete CSV data source
  method: DELETE
  name: deletecsvdatasource
  path: /api/v2/hoverfly/templating-data-source/csv/{dataSourceName}
- description: Shut down Hoverfly
  method: DELETE
  name: shutdown
  path: /api/v2/shutdown
personas: []
provider_name: Hoverfly
provider_slug: hoverfly
search_terms:
- list post-serve actions
- clear journal
- getcors
- set pac file
- setpac
- listcsvdatasources
- appendsimulation
- get logs
- getlogs
- clear state
- get version
- getcache
- getdiff
- patchstate
- api
- getversion
- listpostserveactions
- clear diff reports
- list journal indexes
- get simulation
- get usage metrics
- list csv data sources
- append simulation
- clearcache
- clearjournal
- get cors settings
- get simulation json schema
- filter diff reports
- deletepostserveaction
- get journal
- delete csv data source
- clear cache
- delete post-serve action
- get middleware
- shut down hoverfly
- getpac
- replace state
- set mode
- clearsimulation
- mocking
- update middleware
- replace simulation
- getdestination
- hoverfly
- replacesimulation
- create or update post-serve action
- getupstreamproxy
- getjournal
- create journal index
- clearstate
- getmode
- get mode
- get state
- upsertcsvdatasource
- gethoverfly
- get hoverfly configuration
- testing
- get cache
- cleardiff
- clear simulation
- upsert csv data source
- deletecsvdatasource
- replacestate
- shutdown
- setmiddleware
- delete pac file
- deletejournalindex
- getusage
- filter journal
- get diff reports
- listjournalindexes
- patch state
- deletepac
- getmiddleware
- setdestination
- get pac file
- upsertpostserveaction
- createjournalindex
- getsimulation
- get destination
- delete journal index
- filterdiff
- setmode
- filterjournal
- getsimulationschema
- getstate
- get upstream proxy
- set destination
slug: hoverfly-capability
source_filename: hoverfly-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hoverfly Admin API\n  description: Hoverfly's Admin API provides programmatic control of a Hoverfly instance, including simulation management,\n    mode and middleware configuration, journal and diff inspection, state management, caching, logging, templating data sources,\n    and post-serve actions.\n  tags:\n  - Hoverfly\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hoverfly\n    baseUri: http://localhost:8888\n    description: Hoverfly Admin API HTTP API.\n    resources:\n    - name: api-v2-simulation\n      path: /api/v2/simulation\n      operations:\n      - name: getsimulation\n        method: GET\n        description: Get simulation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacesimulation\n        method: PUT\n        description: Replace simulation\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: appendsimulation\n        method: POST\n        description: Append simulation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: clearsimulation\n        method: DELETE\n        description: Clear simulation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-simulation-schema\n      path: /api/v2/simulation/schema\n      operations:\n      - name: getsimulationschema\n        method: GET\n        description: Get simulation JSON schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-hoverfly\n      path: /api/v2/hoverfly\n      operations:\n      - name: gethoverfly\n \
  \       method: GET\n        description: Get Hoverfly configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-hoverfly-cors\n      path: /api/v2/hoverfly/cors\n      operations:\n      - name: getcors\n        method: GET\n        description: Get CORS settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-hoverfly-destination\n      path: /api/v2/hoverfly/destination\n      operations:\n      - name: getdestination\n        method: GET\n        description: Get destination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setdestination\n        method: PUT\n        description: Set destination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: api-v2-hoverfly-middleware\n      path: /api/v2/hoverfly/middleware\n      operations:\n      - name: getmiddleware\n        method: GET\n        description: Get middleware\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setmiddleware\n        method: PUT\n        description: Update middleware\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-hoverfly-mode\n      path: /api/v2/hoverfly/mode\n      operations:\n      - name: getmode\n        method: GET\n        description: Get mode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setmode\n        method: PUT\n        description: Set mode\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: api-v2-hoverfly-version\n      path: /api/v2/hoverfly/version\n      operations:\n      - name: getversion\n        method: GET\n        description: Get version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-hoverfly-usage\n      path: /api/v2/hoverfly/usage\n      operations:\n      - name: getusage\n        method: GET\n        description: Get usage metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-hoverfly-upstream-proxy\n      path: /api/v2/hoverfly/upstream-proxy\n      operations:\n      - name: getupstreamproxy\n        method: GET\n        description: Get upstream proxy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ api-v2-hoverfly-pac\n      path: /api/v2/hoverfly/pac\n      operations:\n      - name: getpac\n        method: GET\n        description: Get PAC file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setpac\n        method: PUT\n        description: Set PAC file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepac\n        method: DELETE\n        description: Delete PAC file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-hoverfly-post-serve-action\n      path: /api/v2/hoverfly/post-serve-action\n      operations:\n      - name: listpostserveactions\n        method: GET\n        description: List post-serve actions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: upsertpostserveaction\n        method: PUT\n        description: Create or update post-serve action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-hoverfly-post-serve-action-actionname\n      path: /api/v2/hoverfly/post-serve-action/{actionName}\n      operations:\n      - name: deletepostserveaction\n        method: DELETE\n        description: Delete post-serve action\n        inputParameters:\n        - name: actionName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-cache\n      path: /api/v2/cache\n      operations:\n      - name: getcache\n        method: GET\n        description: Get cache\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: clearcache\n        method: DELETE\n        description: Clear cache\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-logs\n      path: /api/v2/logs\n      operations:\n      - name: getlogs\n        method: GET\n        description: Get logs\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: from\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-journal\n      path: /api/v2/journal\n      operations:\n      - name: getjournal\n        method: GET\n        description: Get journal\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n\
  \          type: integer\n        - name: from\n          in: query\n          type: integer\n        - name: to\n          in: query\n          type: integer\n        - name: sort\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: filterjournal\n        method: POST\n        description: Filter journal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: clearjournal\n        method: DELETE\n        description: Clear journal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-journal-index\n      path: /api/v2/journal/index\n      operations:\n      - name: listjournalindexes\n        method: GET\n        description: List journal indexes\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createjournalindex\n        method: POST\n        description: Create journal index\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-journal-index-indexname\n      path: /api/v2/journal/index/{indexName}\n      operations:\n      - name: deletejournalindex\n        method: DELETE\n        description: Delete journal index\n        inputParameters:\n        - name: indexName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-state\n      path: /api/v2/state\n      operations:\n      - name: getstate\n        method: GET\n        description: Get state\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: replacestate\n        method: PUT\n        description: Replace state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchstate\n        method: PATCH\n        description: Patch state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: clearstate\n        method: DELETE\n        description: Clear state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-diff\n      path: /api/v2/diff\n      operations:\n      - name: getdiff\n        method: GET\n        description: Get diff reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: filterdiff\n\
  \        method: POST\n        description: Filter diff reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cleardiff\n        method: DELETE\n        description: Clear diff reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-hoverfly-templating-data-source-csv\n      path: /api/v2/hoverfly/templating-data-source/csv\n      operations:\n      - name: listcsvdatasources\n        method: GET\n        description: List CSV data sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upsertcsvdatasource\n        method: PUT\n        description: Upsert CSV data source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: api-v2-hoverfly-templating-data-source-csv-datas\n      path: /api/v2/hoverfly/templating-data-source/csv/{dataSourceName}\n      operations:\n      - name: deletecsvdatasource\n        method: DELETE\n        description: Delete CSV data source\n        inputParameters:\n        - name: dataSourceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-shutdown\n      path: /api/v2/shutdown\n      operations:\n      - name: shutdown\n        method: DELETE\n        description: Shut down Hoverfly\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hoverfly-rest\n    description: REST adapter for Hoverfly Admin API.\n    resources:\n    - path: /api/v2/simulation\n      name: getsimulation\n\
  \      operations:\n      - method: GET\n        name: getsimulation\n        description: Get simulation\n        call: hoverfly.getsimulation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/simulation\n      name: replacesimulation\n      operations:\n      - method: PUT\n        name: replacesimulation\n        description: Replace simulation\n        call: hoverfly.replacesimulation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/simulation\n      name: appendsimulation\n      operations:\n      - method: POST\n        name: appendsimulation\n        description: Append simulation\n        call: hoverfly.appendsimulation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/simulation\n      name: clearsimulation\n      operations:\n      - method: DELETE\n        name: clearsimulation\n        description: Clear simulation\n        call: hoverfly.clearsimulation\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/simulation/schema\n      name: getsimulationschema\n      operations:\n      - method: GET\n        name: getsimulationschema\n        description: Get simulation JSON schema\n        call: hoverfly.getsimulationschema\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly\n      name: gethoverfly\n      operations:\n      - method: GET\n        name: gethoverfly\n        description: Get Hoverfly configuration\n        call: hoverfly.gethoverfly\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/cors\n      name: getcors\n      operations:\n      - method: GET\n        name: getcors\n        description: Get CORS settings\n        call: hoverfly.getcors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/destination\n      name: getdestination\n\
  \      operations:\n      - method: GET\n        name: getdestination\n        description: Get destination\n        call: hoverfly.getdestination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/destination\n      name: setdestination\n      operations:\n      - method: PUT\n        name: setdestination\n        description: Set destination\n        call: hoverfly.setdestination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/middleware\n      name: getmiddleware\n      operations:\n      - method: GET\n        name: getmiddleware\n        description: Get middleware\n        call: hoverfly.getmiddleware\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/middleware\n      name: setmiddleware\n      operations:\n      - method: PUT\n        name: setmiddleware\n        description: Update middleware\n        call: hoverfly.setmiddleware\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/mode\n      name: getmode\n      operations:\n      - method: GET\n        name: getmode\n        description: Get mode\n        call: hoverfly.getmode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/mode\n      name: setmode\n      operations:\n      - method: PUT\n        name: setmode\n        description: Set mode\n        call: hoverfly.setmode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/version\n      name: getversion\n      operations:\n      - method: GET\n        name: getversion\n        description: Get version\n        call: hoverfly.getversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/usage\n      name: getusage\n      operations:\n      - method: GET\n        name: getusage\n        description:\
  \ Get usage metrics\n        call: hoverfly.getusage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/upstream-proxy\n      name: getupstreamproxy\n      operations:\n      - method: GET\n        name: getupstreamproxy\n        description: Get upstream proxy\n        call: hoverfly.getupstreamproxy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/pac\n      name: getpac\n      operations:\n      - method: GET\n        name: getpac\n        description: Get PAC file\n        call: hoverfly.getpac\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/pac\n      name: setpac\n      operations:\n      - method: PUT\n        name: setpac\n        description: Set PAC file\n        call: hoverfly.setpac\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/pac\n      name: deletepac\n\
  \      operations:\n      - method: DELETE\n        name: deletepac\n        description: Delete PAC file\n        call: hoverfly.deletepac\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/post-serve-action\n      name: listpostserveactions\n      operations:\n      - method: GET\n        name: listpostserveactions\n        description: List post-serve actions\n        call: hoverfly.listpostserveactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/post-serve-action\n      name: upsertpostserveaction\n      operations:\n      - method: PUT\n        name: upsertpostserveaction\n        description: Create or update post-serve action\n        call: hoverfly.upsertpostserveaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/post-serve-action/{actionName}\n      name: deletepostserveaction\n      operations:\n      - method:\
  \ DELETE\n        name: deletepostserveaction\n        description: Delete post-serve action\n        call: hoverfly.deletepostserveaction\n        with:\n          actionName: rest.actionName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/cache\n      name: getcache\n      operations:\n      - method: GET\n        name: getcache\n        description: Get cache\n        call: hoverfly.getcache\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/cache\n      name: clearcache\n      operations:\n      - method: DELETE\n        name: clearcache\n        description: Clear cache\n        call: hoverfly.clearcache\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/logs\n      name: getlogs\n      operations:\n      - method: GET\n        name: getlogs\n        description: Get logs\n        call: hoverfly.getlogs\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /api/v2/journal\n      name: getjournal\n      operations:\n      - method: GET\n        name: getjournal\n        description: Get journal\n        call: hoverfly.getjournal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/journal\n      name: filterjournal\n      operations:\n      - method: POST\n        name: filterjournal\n        description: Filter journal\n        call: hoverfly.filterjournal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/journal\n      name: clearjournal\n      operations:\n      - method: DELETE\n        name: clearjournal\n        description: Clear journal\n        call: hoverfly.clearjournal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/journal/index\n      name: listjournalindexes\n      operations:\n      - method: GET\n        name: listjournalindexes\n        description: List\
  \ journal indexes\n        call: hoverfly.listjournalindexes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/journal/index\n      name: createjournalindex\n      operations:\n      - method: POST\n        name: createjournalindex\n        description: Create journal index\n        call: hoverfly.createjournalindex\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/journal/index/{indexName}\n      name: deletejournalindex\n      operations:\n      - method: DELETE\n        name: deletejournalindex\n        description: Delete journal index\n        call: hoverfly.deletejournalindex\n        with:\n          indexName: rest.indexName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/state\n      name: getstate\n      operations:\n      - method: GET\n        name: getstate\n        description: Get state\n        call: hoverfly.getstate\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /api/v2/state\n      name: replacestate\n      operations:\n      - method: PUT\n        name: replacestate\n        description: Replace state\n        call: hoverfly.replacestate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/state\n      name: patchstate\n      operations:\n      - method: PATCH\n        name: patchstate\n        description: Patch state\n        call: hoverfly.patchstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/state\n      name: clearstate\n      operations:\n      - method: DELETE\n        name: clearstate\n        description: Clear state\n        call: hoverfly.clearstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/diff\n      name: getdiff\n      operations:\n      - method: GET\n        name: getdiff\n        description: Get diff reports\n        call:\
  \ hoverfly.getdiff\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/diff\n      name: filterdiff\n      operations:\n      - method: POST\n        name: filterdiff\n        description: Filter diff reports\n        call: hoverfly.filterdiff\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/diff\n      name: cleardiff\n      operations:\n      - method: DELETE\n        name: cleardiff\n        description: Clear diff reports\n        call: hoverfly.cleardiff\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/templating-data-source/csv\n      name: listcsvdatasources\n      operations:\n      - method: GET\n        name: listcsvdatasources\n        description: List CSV data sources\n        call: hoverfly.listcsvdatasources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/templating-data-source/csv\n\
  \      name: upsertcsvdatasource\n      operations:\n      - method: PUT\n        name: upsertcsvdatasource\n        description: Upsert CSV data source\n        call: hoverfly.upsertcsvdatasource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/hoverfly/templating-data-source/csv/{dataSourceName}\n      name: deletecsvdatasource\n      operations:\n      - method: DELETE\n        name: deletecsvdatasource\n        description: Delete CSV data source\n        call: hoverfly.deletecsvdatasource\n        with:\n          dataSourceName: rest.dataSourceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/shutdown\n      name: shutdown\n      operations:\n      - method: DELETE\n        name: shutdown\n        description: Shut down Hoverfly\n        call: hoverfly.shutdown\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hoverfly-mcp\n\
  \    transport: http\n    description: MCP adapter for Hoverfly Admin API for AI agent use.\n    tools:\n    - name: getsimulation\n      description: Get simulation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getsimulation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacesimulation\n      description: Replace simulation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hoverfly.replacesimulation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: appendsimulation\n      description: Append simulation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hoverfly.appendsimulation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clearsimulation\n      description: Clear simulation\n      hints:\n        readOnly:\
  \ false\n        destructive: true\n        idempotent: true\n      call: hoverfly.clearsimulation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsimulationschema\n      description: Get simulation JSON schema\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getsimulationschema\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethoverfly\n      description: Get Hoverfly configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.gethoverfly\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcors\n      description: Get CORS settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getcors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdestination\n      description:\
  \ Get destination\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getdestination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setdestination\n      description: Set destination\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hoverfly.setdestination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmiddleware\n      description: Get middleware\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getmiddleware\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setmiddleware\n      description: Update middleware\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hoverfly.setmiddleware\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: getmode\n      description: Get mode\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getmode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setmode\n      description: Set mode\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hoverfly.setmode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getversion\n      description: Get version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getusage\n      description: Get usage metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getusage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getupstreamproxy\n\
  \      description: Get upstream proxy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getupstreamproxy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpac\n      description: Get PAC file\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getpac\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setpac\n      description: Set PAC file\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hoverfly.setpac\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletepac\n      description: Delete PAC file\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hoverfly.deletepac\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpostserveactions\n\
  \      description: List post-serve actions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.listpostserveactions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upsertpostserveaction\n      description: Create or update post-serve action\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hoverfly.upsertpostserveaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletepostserveaction\n      description: Delete post-serve action\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hoverfly.deletepostserveaction\n      with:\n        actionName: tools.actionName\n      inputParameters:\n      - name: actionName\n        type: string\n        description: actionName\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getcache\n      description: Get cache\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getcache\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clearcache\n      description: Clear cache\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hoverfly.clearcache\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlogs\n      description: Get logs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getlogs\n      with:\n        limit: tools.limit\n        from: tools.from\n      inputParameters:\n      - name: limit\n        type: integer\n        description: limit\n      - name: from\n        type: integer\n        description: from\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjournal\n    \
  \  description: Get journal\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.getjournal\n      with:\n        limit: tools.limit\n        offset: tools.offset\n        from: tools.from\n        to: tools.to\n        sort: tools.sort\n      inputParameters:\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      - name: from\n        type: integer\n        description: from\n      - name: to\n        type: integer\n        description: to\n      - name: sort\n        type: string\n        description: sort\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: filterjournal\n      description: Filter journal\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hoverfly.filterjournal\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: clearjournal\n      description: Clear journal\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: hoverfly.clearjournal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjournalindexes\n      description: List journal indexes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hoverfly.listjournalindexes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createjournalindex\n      description: Create journal index\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: hoverfly.createjournalindex\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletejournalindex\n      description: Delete journal index\n      hints:\n        readOnly: false\n        destruc\n\n# --- truncated at 32 KB (35 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/hoverfly/refs/heads/main/capabilities/hoverfly-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hoverfly/refs/heads/main/capabilities/hoverfly-capability.yaml
tags:
- Hoverfly
- API
tools:
- description: Get simulation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsimulation
- description: Replace simulation
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacesimulation
- description: Append simulation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: appendsimulation
- description: Clear simulation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: clearsimulation
- description: Get simulation JSON schema
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsimulationschema
- description: Get Hoverfly configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethoverfly
- description: Get CORS settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcors
- description: Get destination
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdestination
- description: Set destination
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setdestination
- description: Get middleware
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmiddleware
- description: Update middleware
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setmiddleware
- description: Get mode
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmode
- description: Set mode
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setmode
- description: Get version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getversion
- description: Get usage metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusage
- description: Get upstream proxy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getupstreamproxy
- description: Get PAC file
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpac
- description: Set PAC file
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setpac
- description: Delete PAC file
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepac
- description: List post-serve actions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpostserveactions
- description: Create or update post-serve action
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: upsertpostserveaction
- description: Delete post-serve action
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepostserveaction
- description: Get cache
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcache
- description: Clear cache
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: clearcache
- description: Get logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlogs
- description: Get journal
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjournal
- description: Filter journal
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: filterjournal
- description: Clear journal
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: clearjournal
- description: List journal indexes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjournalindexes
- description: Create journal index
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createjournalindex
- description: Delete journal index
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletejournalindex
- description: Get state
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstate
- description: Replace state
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacestate
- description: Patch state
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchstate
- description: Clear state
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: clearstate
- description: Get diff reports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdiff
- description: Filter diff reports
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: filterdiff
- description: Clear diff reports
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cleardiff
- description: List CSV data sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcsvdatasources
- description: Upsert CSV data source
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: upsertcsvdatasource
- description: Delete CSV data source
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecsvdatasource
- description: Shut down Hoverfly
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: shutdown
---
