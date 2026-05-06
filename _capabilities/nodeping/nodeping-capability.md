---
categories: []
consumed_apis: []
description: NodePing provides uptime monitoring for websites and services. The REST API lets accounts manage checks, contacts, contact groups, schedules, results, notifications, and account settings.
layout: capability
name: NodePing API
operations:
- description: Get account information
  method: GET
  name: getaccounts
  path: /accounts
- description: Create a SubAccount
  method: POST
  name: createaccount
  path: /accounts
- description: Update account
  method: PUT
  name: updateaccount
  path: /accounts
- description: Delete a SubAccount
  method: DELETE
  name: deleteaccount
  path: /accounts
- description: List checks
  method: GET
  name: listchecks
  path: /checks
- description: Create a check
  method: POST
  name: createcheck
  path: /checks
- description: Get a single check
  method: GET
  name: getcheck
  path: /checks/{checkid}
- description: Update a check
  method: PUT
  name: updatecheck
  path: /checks/{checkid}
- description: Delete a check
  method: DELETE
  name: deletecheck
  path: /checks/{checkid}
- description: List contacts
  method: GET
  name: listcontacts
  path: /contacts
- description: Create a contact
  method: POST
  name: createcontact
  path: /contacts
- description: Update a contact
  method: PUT
  name: updatecontact
  path: /contacts
- description: Delete a contact
  method: DELETE
  name: deletecontact
  path: /contacts
- description: List contact groups
  method: GET
  name: listcontactgroups
  path: /contactgroups
- description: Create a contact group
  method: POST
  name: createcontactgroup
  path: /contactgroups
- description: Update a contact group
  method: PUT
  name: updatecontactgroup
  path: /contactgroups
- description: Delete a contact group
  method: DELETE
  name: deletecontactgroup
  path: /contactgroups
- description: List notification schedules
  method: GET
  name: listschedules
  path: /schedules
- description: Update a schedule
  method: PUT
  name: updateschedule
  path: /schedules
- description: Delete a schedule
  method: DELETE
  name: deleteschedule
  path: /schedules
- description: Get check results
  method: GET
  name: getresults
  path: /results
- description: Get uptime statistics
  method: GET
  name: getuptime
  path: /results/uptime
- description: Get current check states
  method: GET
  name: getcurrentresults
  path: /results/current
- description: List notifications
  method: GET
  name: listnotifications
  path: /notifications
- description: Get probe / location information
  method: GET
  name: getinfo
  path: /info
personas: []
provider_name: NodePing
provider_slug: nodeping
search_terms:
- createcheck
- listcontactgroups
- get a single check
- nodeping
- deletecheck
- listcontacts
- update a schedule
- createaccount
- create a subaccount
- listchecks
- delete a check
- updatecontactgroup
- listnotifications
- list notifications
- get probe / location information
- uptime
- deleteaccount
- create a contact group
- updatecheck
- getinfo
- get check results
- list checks
- delete a subaccount
- update a contact group
- update account
- deleteschedule
- monitoring
- get current check states
- updatecontact
- create a contact
- deletecontactgroup
- getcheck
- create a check
- createcontact
- get account information
- update a contact
- getcurrentresults
- api
- updateaccount
- list notification schedules
- list contact groups
- getresults
- deletecontact
- get uptime statistics
- saas
- notifications
- getuptime
- delete a schedule
- delete a contact
- getaccounts
- list contacts
- listschedules
- createcontactgroup
- delete a contact group
- update a check
- updateschedule
slug: nodeping-capability
source_filename: nodeping-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NodePing API\n  description: NodePing provides uptime monitoring for websites and services. The REST API lets accounts manage checks, contacts,\n    contact groups, schedules, results, notifications, and account settings.\n  tags:\n  - Nodeping\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nodeping\n    baseUri: https://api.nodeping.com/api/1\n    description: NodePing API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: token\n      value: '{{NODEPING_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      operations:\n      - name: getaccounts\n        method: GET\n        description: Get account information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createaccount\n        method: POST\n        description: Create\
  \ a SubAccount\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccount\n        method: PUT\n        description: Update account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteaccount\n        method: DELETE\n        description: Delete a SubAccount\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: checks\n      path: /checks\n      operations:\n      - name: listchecks\n        method: GET\n        description: List checks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcheck\n        method: POST\n        description: Create a check\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: checks-checkid\n      path: /checks/{checkid}\n      operations:\n      - name: getcheck\n        method: GET\n        description: Get a single check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecheck\n        method: PUT\n        description: Update a check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecheck\n        method: DELETE\n        description: Delete a check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /contacts\n      operations:\n      - name: listcontacts\n        method: GET\n        description: List contacts\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: createcontact\n        method: POST\n        description: Create a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecontact\n        method: PUT\n        description: Update a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontact\n        method: DELETE\n        description: Delete a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contactgroups\n      path: /contactgroups\n      operations:\n      - name: listcontactgroups\n        method: GET\n        description: List contact groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: createcontactgroup\n        method: POST\n        description: Create a contact group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecontactgroup\n        method: PUT\n        description: Update a contact group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontactgroup\n        method: DELETE\n        description: Delete a contact group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules\n      path: /schedules\n      operations:\n      - name: listschedules\n        method: GET\n        description: List notification schedules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateschedule\n\
  \        method: PUT\n        description: Update a schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteschedule\n        method: DELETE\n        description: Delete a schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results\n      path: /results\n      operations:\n      - name: getresults\n        method: GET\n        description: Get check results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results-uptime\n      path: /results/uptime\n      operations:\n      - name: getuptime\n        method: GET\n        description: Get uptime statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results-current\n\
  \      path: /results/current\n      operations:\n      - name: getcurrentresults\n        method: GET\n        description: Get current check states\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notifications\n      path: /notifications\n      operations:\n      - name: listnotifications\n        method: GET\n        description: List notifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: info\n      path: /info\n      operations:\n      - name: getinfo\n        method: GET\n        description: Get probe / location information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nodeping-rest\n    description: REST adapter for NodePing API.\n    resources:\n    -\
  \ path: /accounts\n      name: getaccounts\n      operations:\n      - method: GET\n        name: getaccounts\n        description: Get account information\n        call: nodeping.getaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts\n      name: createaccount\n      operations:\n      - method: POST\n        name: createaccount\n        description: Create a SubAccount\n        call: nodeping.createaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts\n      name: updateaccount\n      operations:\n      - method: PUT\n        name: updateaccount\n        description: Update account\n        call: nodeping.updateaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts\n      name: deleteaccount\n      operations:\n      - method: DELETE\n        name: deleteaccount\n        description: Delete a SubAccount\n        call: nodeping.deleteaccount\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /checks\n      name: listchecks\n      operations:\n      - method: GET\n        name: listchecks\n        description: List checks\n        call: nodeping.listchecks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /checks\n      name: createcheck\n      operations:\n      - method: POST\n        name: createcheck\n        description: Create a check\n        call: nodeping.createcheck\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /checks/{checkid}\n      name: getcheck\n      operations:\n      - method: GET\n        name: getcheck\n        description: Get a single check\n        call: nodeping.getcheck\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /checks/{checkid}\n      name: updatecheck\n      operations:\n      - method: PUT\n        name: updatecheck\n        description: Update\
  \ a check\n        call: nodeping.updatecheck\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /checks/{checkid}\n      name: deletecheck\n      operations:\n      - method: DELETE\n        name: deletecheck\n        description: Delete a check\n        call: nodeping.deletecheck\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: listcontacts\n      operations:\n      - method: GET\n        name: listcontacts\n        description: List contacts\n        call: nodeping.listcontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: createcontact\n      operations:\n      - method: POST\n        name: createcontact\n        description: Create a contact\n        call: nodeping.createcontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: updatecontact\n      operations:\n \
  \     - method: PUT\n        name: updatecontact\n        description: Update a contact\n        call: nodeping.updatecontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: deletecontact\n      operations:\n      - method: DELETE\n        name: deletecontact\n        description: Delete a contact\n        call: nodeping.deletecontact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactgroups\n      name: listcontactgroups\n      operations:\n      - method: GET\n        name: listcontactgroups\n        description: List contact groups\n        call: nodeping.listcontactgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactgroups\n      name: createcontactgroup\n      operations:\n      - method: POST\n        name: createcontactgroup\n        description: Create a contact group\n        call: nodeping.createcontactgroup\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /contactgroups\n      name: updatecontactgroup\n      operations:\n      - method: PUT\n        name: updatecontactgroup\n        description: Update a contact group\n        call: nodeping.updatecontactgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contactgroups\n      name: deletecontactgroup\n      operations:\n      - method: DELETE\n        name: deletecontactgroup\n        description: Delete a contact group\n        call: nodeping.deletecontactgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules\n      name: listschedules\n      operations:\n      - method: GET\n        name: listschedules\n        description: List notification schedules\n        call: nodeping.listschedules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules\n      name: updateschedule\n      operations:\n   \
  \   - method: PUT\n        name: updateschedule\n        description: Update a schedule\n        call: nodeping.updateschedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules\n      name: deleteschedule\n      operations:\n      - method: DELETE\n        name: deleteschedule\n        description: Delete a schedule\n        call: nodeping.deleteschedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /results\n      name: getresults\n      operations:\n      - method: GET\n        name: getresults\n        description: Get check results\n        call: nodeping.getresults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /results/uptime\n      name: getuptime\n      operations:\n      - method: GET\n        name: getuptime\n        description: Get uptime statistics\n        call: nodeping.getuptime\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /results/current\n      name: getcurrentresults\n      operations:\n      - method: GET\n        name: getcurrentresults\n        description: Get current check states\n        call: nodeping.getcurrentresults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /notifications\n      name: listnotifications\n      operations:\n      - method: GET\n        name: listnotifications\n        description: List notifications\n        call: nodeping.listnotifications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /info\n      name: getinfo\n      operations:\n      - method: GET\n        name: getinfo\n        description: Get probe / location information\n        call: nodeping.getinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nodeping-mcp\n    transport: http\n    description: MCP adapter for NodePing API for AI agent use.\n\
  \    tools:\n    - name: getaccounts\n      description: Get account information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nodeping.getaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createaccount\n      description: Create a SubAccount\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nodeping.createaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateaccount\n      description: Update account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nodeping.updateaccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteaccount\n      description: Delete a SubAccount\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nodeping.deleteaccount\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: listchecks\n      description: List checks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nodeping.listchecks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcheck\n      description: Create a check\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nodeping.createcheck\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcheck\n      description: Get a single check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nodeping.getcheck\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecheck\n      description: Update a check\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nodeping.updatecheck\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecheck\n      description: Delete a check\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nodeping.deletecheck\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontacts\n      description: List contacts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nodeping.listcontacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontact\n      description: Create a contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nodeping.createcontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecontact\n      description: Update a contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n  \
  \    call: nodeping.updatecontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontact\n      description: Delete a contact\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nodeping.deletecontact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontactgroups\n      description: List contact groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nodeping.listcontactgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontactgroup\n      description: Create a contact group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nodeping.createcontactgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecontactgroup\n      description: Update a contact group\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nodeping.updatecontactgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontactgroup\n      description: Delete a contact group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nodeping.deletecontactgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listschedules\n      description: List notification schedules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nodeping.listschedules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateschedule\n      description: Update a schedule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nodeping.updateschedule\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: deleteschedule\n      description: Delete a schedule\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nodeping.deleteschedule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getresults\n      description: Get check results\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nodeping.getresults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuptime\n      description: Get uptime statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nodeping.getuptime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcurrentresults\n      description: Get current check states\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nodeping.getcurrentresults\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listnotifications\n      description: List notifications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nodeping.listnotifications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinfo\n      description: Get probe / location information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nodeping.getinfo\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NODEPING_TOKEN: NODEPING_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nodeping/refs/heads/main/capabilities/nodeping-capability.yaml
tags:
- Nodeping
- API
tools:
- description: Get account information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccounts
- description: Create a SubAccount
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaccount
- description: Update account
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateaccount
- description: Delete a SubAccount
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaccount
- description: List checks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchecks
- description: Create a check
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcheck
- description: Get a single check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcheck
- description: Update a check
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecheck
- description: Delete a check
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecheck
- description: List contacts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontacts
- description: Create a contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontact
- description: Update a contact
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecontact
- description: Delete a contact
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontact
- description: List contact groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontactgroups
- description: Create a contact group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontactgroup
- description: Update a contact group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecontactgroup
- description: Delete a contact group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontactgroup
- description: List notification schedules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschedules
- description: Update a schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateschedule
- description: Delete a schedule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteschedule
- description: Get check results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresults
- description: Get uptime statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuptime
- description: Get current check states
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentresults
- description: List notifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnotifications
- description: Get probe / location information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinfo
---
