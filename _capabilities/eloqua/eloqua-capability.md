---
categories: []
consumed_apis: []
description: The Bulk API for Oracle Eloqua Marketing Cloud Service, designed for high-volume data operations including imports, exports, and synchronization of large datasets for contacts, accounts, activities, and custom objects.
layout: capability
name: Oracle Eloqua Bulk API
operations:
- description: Oracle Eloqua List contact export definitions
  method: GET
  name: listcontactexports
  path: /contacts/exports
- description: Oracle Eloqua Create a contact export definition
  method: POST
  name: createcontactexport
  path: /contacts/exports
- description: Oracle Eloqua Retrieve a contact export definition
  method: GET
  name: getcontactexport
  path: /contacts/exports/{id}
- description: Oracle Eloqua Update a contact export definition
  method: PUT
  name: updatecontactexport
  path: /contacts/exports/{id}
- description: Oracle Eloqua Delete a contact export definition
  method: DELETE
  name: deletecontactexport
  path: /contacts/exports/{id}
- description: Oracle Eloqua Retrieve contact export data
  method: GET
  name: getcontactexportdata
  path: /contacts/exports/{id}/data
- description: Oracle Eloqua List contact import definitions
  method: GET
  name: listcontactimports
  path: /contacts/imports
- description: Oracle Eloqua Create a contact import definition
  method: POST
  name: createcontactimport
  path: /contacts/imports
- description: Oracle Eloqua Retrieve a contact import definition
  method: GET
  name: getcontactimport
  path: /contacts/imports/{id}
- description: Oracle Eloqua Update a contact import definition
  method: PUT
  name: updatecontactimport
  path: /contacts/imports/{id}
- description: Oracle Eloqua Delete a contact import definition
  method: DELETE
  name: deletecontactimport
  path: /contacts/imports/{id}
- description: Oracle Eloqua Push data to a contact import
  method: POST
  name: pushcontactimportdata
  path: /contacts/imports/{id}/data
- description: Oracle Eloqua Delete staged contact import data
  method: DELETE
  name: deletecontactimportdata
  path: /contacts/imports/{id}/data
- description: Oracle Eloqua List contact fields
  method: GET
  name: listcontactfields
  path: /contacts/fields
- description: Oracle Eloqua Create a contact sync action
  method: POST
  name: createcontactsyncaction
  path: /contacts/syncActions
- description: Oracle Eloqua List account export definitions
  method: GET
  name: listaccountexports
  path: /accounts/exports
- description: Oracle Eloqua Create an account export definition
  method: POST
  name: createaccountexport
  path: /accounts/exports
- description: Oracle Eloqua Retrieve an account export definition
  method: GET
  name: getaccountexport
  path: /accounts/exports/{id}
- description: Oracle Eloqua Delete an account export definition
  method: DELETE
  name: deleteaccountexport
  path: /accounts/exports/{id}
- description: Oracle Eloqua List account import definitions
  method: GET
  name: listaccountimports
  path: /accounts/imports
- description: Oracle Eloqua Create an account import definition
  method: POST
  name: createaccountimport
  path: /accounts/imports
- description: Oracle Eloqua Retrieve an account import definition
  method: GET
  name: getaccountimport
  path: /accounts/imports/{id}
- description: Oracle Eloqua Delete an account import definition
  method: DELETE
  name: deleteaccountimport
  path: /accounts/imports/{id}
- description: Oracle Eloqua Push data to an account import
  method: POST
  name: pushaccountimportdata
  path: /accounts/imports/{id}/data
- description: Oracle Eloqua List account fields
  method: GET
  name: listaccountfields
  path: /accounts/fields
- description: Oracle Eloqua List activity export definitions
  method: GET
  name: listactivityexports
  path: /activities/exports
- description: Oracle Eloqua Create an activity export definition
  method: POST
  name: createactivityexport
  path: /activities/exports
- description: Oracle Eloqua Retrieve an activity export definition
  method: GET
  name: getactivityexport
  path: /activities/exports/{id}
- description: Oracle Eloqua Delete an activity export definition
  method: DELETE
  name: deleteactivityexport
  path: /activities/exports/{id}
- description: Oracle Eloqua Create an activity import definition
  method: POST
  name: createactivityimport
  path: /activities/imports
- description: Oracle Eloqua Push data to an activity import
  method: POST
  name: pushactivityimportdata
  path: /activities/imports/{id}/data
- description: Oracle Eloqua List custom object export definitions
  method: GET
  name: listcustomobjectexports
  path: /customObjects/{parentId}/exports
- description: Oracle Eloqua Create a custom object export definition
  method: POST
  name: createcustomobjectexport
  path: /customObjects/{parentId}/exports
- description: Oracle Eloqua List custom object import definitions
  method: GET
  name: listcustomobjectimports
  path: /customObjects/{parentId}/imports
- description: Oracle Eloqua Create a custom object import definition
  method: POST
  name: createcustomobjectimport
  path: /customObjects/{parentId}/imports
- description: Oracle Eloqua Push data to a custom object import
  method: POST
  name: pushcustomobjectimportdata
  path: /customObjects/{parentId}/imports/{id}/data
- description: Oracle Eloqua List available custom objects
  method: GET
  name: listbulkcustomobjects
  path: /customObjects
- description: Oracle Eloqua List syncs
  method: GET
  name: listsyncs
  path: /syncs
- description: Oracle Eloqua Create a sync
  method: POST
  name: createsync
  path: /syncs
- description: Oracle Eloqua Retrieve a sync
  method: GET
  name: getsync
  path: /syncs/{id}
- description: Oracle Eloqua Retrieve sync data
  method: GET
  name: getsyncdata
  path: /syncs/{id}/data
- description: Oracle Eloqua Delete sync data
  method: DELETE
  name: deletesyncdata
  path: /syncs/{id}/data
- description: Oracle Eloqua Retrieve sync logs
  method: GET
  name: getsynclogs
  path: /syncs/{id}/logs
- description: Oracle Eloqua Retrieve sync rejects
  method: GET
  name: getsyncrejects
  path: /syncs/{id}/rejects
personas: []
provider_name: Oracle Eloqua
provider_slug: eloqua
search_terms:
- listcustomobjectimports
- listcontactimports
- api
- createcontactsyncaction
- createaccountimport
- listactivityexports
- getsync
- deletecontactexport
- oracle eloqua delete staged contact import data
- listcontactfields
- oracle eloqua list custom object export definitions
- oracle eloqua create an account import definition
- lead management
- listaccountfields
- oracle eloqua retrieve a contact import definition
- createcustomobjectimport
- oracle eloqua list contact fields
- oracle eloqua list contact export definitions
- oracle eloqua delete a contact import definition
- listaccountimports
- oracle eloqua retrieve sync logs
- oracle eloqua list custom object import definitions
- oracle eloqua list syncs
- listsyncs
- createcontactexport
- oracle eloqua create a contact import definition
- listaccountexports
- oracle eloqua update a contact import definition
- oracle eloqua create a custom object export definition
- oracle eloqua list account export definitions
- oracle eloqua delete an account export definition
- oracle eloqua delete sync data
- listbulkcustomobjects
- createcustomobjectexport
- oracle eloqua retrieve an activity export definition
- oracle eloqua list account fields
- createactivityexport
- oracle eloqua create a contact sync action
- oracle eloqua delete a contact export definition
- oracle eloqua retrieve an account export definition
- listcustomobjectexports
- oracle eloqua retrieve a contact export definition
- oracle eloqua list contact import definitions
- deletesyncdata
- oracle eloqua retrieve a sync
- listcontactexports
- oracle eloqua push data to a custom object import
- deletecontactimport
- createcontactimport
- oracle eloqua create an account export definition
- pushcustomobjectimportdata
- oracle eloqua retrieve sync rejects
- getcontactexport
- oracle eloqua list activity export definitions
- getaccountimport
- oracle eloqua create an activity import definition
- deleteactivityexport
- getactivityexport
- pushcontactimportdata
- oracle eloqua push data to an activity import
- getcontactexportdata
- createsync
- pushactivityimportdata
- oracle eloqua list account import definitions
- oracle eloqua create a contact export definition
- email marketing
- oracle eloqua delete an activity export definition
- deleteaccountimport
- oracle eloqua create an activity export definition
- oracle eloqua retrieve sync data
- getsyncdata
- oracle eloqua delete an account import definition
- createaccountexport
- deletecontactimportdata
- getsynclogs
- crm
- eloqua
- createactivityimport
- oracle eloqua update a contact export definition
- oracle eloqua create a sync
- oracle eloqua list available custom objects
- getsyncrejects
- updatecontactimport
- pushaccountimportdata
- oracle eloqua push data to an account import
- oracle eloqua create a custom object import definition
- oracle eloqua retrieve an account import definition
- oracle eloqua retrieve contact export data
- getaccountexport
- marketing automation
- oracle eloqua push data to a contact import
- getcontactimport
- updatecontactexport
- deleteaccountexport
slug: eloqua-capability
source_filename: eloqua-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Eloqua Bulk API\n  description: The Bulk API for Oracle Eloqua Marketing Cloud Service, designed for high-volume data operations including\n    imports, exports, and synchronization of large datasets for contacts, accounts, activities, and custom objects.\n  tags:\n  - Eloqua\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: eloqua\n    baseUri: https://secure.p01.eloqua.com/API/Bulk/2.0\n    description: Oracle Eloqua Bulk API HTTP API.\n    authentication:\n      type: basic\n      username: '{{ELOQUA_USERNAME}}'\n      password: '{{ELOQUA_PASSWORD}}'\n    resources:\n    - name: contacts-exports\n      path: /contacts/exports\n      operations:\n      - name: listcontactexports\n        method: GET\n        description: Oracle Eloqua List contact export definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: createcontactexport\n        method: POST\n        description: Oracle Eloqua Create a contact export definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-exports-id\n      path: /contacts/exports/{id}\n      operations:\n      - name: getcontactexport\n        method: GET\n        description: Oracle Eloqua Retrieve a contact export definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecontactexport\n        method: PUT\n        description: Oracle Eloqua Update a contact export definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontactexport\n        method: DELETE\n        description: Oracle Eloqua Delete a contact export definition\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-exports-id-data\n      path: /contacts/exports/{id}/data\n      operations:\n      - name: getcontactexportdata\n        method: GET\n        description: Oracle Eloqua Retrieve contact export data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-imports\n      path: /contacts/imports\n      operations:\n      - name: listcontactimports\n        method: GET\n        description: Oracle Eloqua List contact import definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontactimport\n        method: POST\n        description: Oracle Eloqua Create a contact import definition\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: contacts-imports-id\n      path: /contacts/imports/{id}\n      operations:\n      - name: getcontactimport\n        method: GET\n        description: Oracle Eloqua Retrieve a contact import definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecontactimport\n        method: PUT\n        description: Oracle Eloqua Update a contact import definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontactimport\n        method: DELETE\n        description: Oracle Eloqua Delete a contact import definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-imports-id-data\n      path: /contacts/imports/{id}/data\n      operations:\n\
  \      - name: pushcontactimportdata\n        method: POST\n        description: Oracle Eloqua Push data to a contact import\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontactimportdata\n        method: DELETE\n        description: Oracle Eloqua Delete staged contact import data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-fields\n      path: /contacts/fields\n      operations:\n      - name: listcontactfields\n        method: GET\n        description: Oracle Eloqua List contact fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts-syncactions\n      path: /contacts/syncActions\n      operations:\n      - name: createcontactsyncaction\n        method: POST\n        description: Oracle\
  \ Eloqua Create a contact sync action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-exports\n      path: /accounts/exports\n      operations:\n      - name: listaccountexports\n        method: GET\n        description: Oracle Eloqua List account export definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createaccountexport\n        method: POST\n        description: Oracle Eloqua Create an account export definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-exports-id\n      path: /accounts/exports/{id}\n      operations:\n      - name: getaccountexport\n        method: GET\n        description: Oracle Eloqua Retrieve an account export definition\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteaccountexport\n        method: DELETE\n        description: Oracle Eloqua Delete an account export definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-imports\n      path: /accounts/imports\n      operations:\n      - name: listaccountimports\n        method: GET\n        description: Oracle Eloqua List account import definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createaccountimport\n        method: POST\n        description: Oracle Eloqua Create an account import definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-imports-id\n      path: /accounts/imports/{id}\n\
  \      operations:\n      - name: getaccountimport\n        method: GET\n        description: Oracle Eloqua Retrieve an account import definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteaccountimport\n        method: DELETE\n        description: Oracle Eloqua Delete an account import definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-imports-id-data\n      path: /accounts/imports/{id}/data\n      operations:\n      - name: pushaccountimportdata\n        method: POST\n        description: Oracle Eloqua Push data to an account import\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-fields\n      path: /accounts/fields\n      operations:\n      - name: listaccountfields\n     \
  \   method: GET\n        description: Oracle Eloqua List account fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activities-exports\n      path: /activities/exports\n      operations:\n      - name: listactivityexports\n        method: GET\n        description: Oracle Eloqua List activity export definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createactivityexport\n        method: POST\n        description: Oracle Eloqua Create an activity export definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activities-exports-id\n      path: /activities/exports/{id}\n      operations:\n      - name: getactivityexport\n        method: GET\n        description: Oracle Eloqua Retrieve an activity export\
  \ definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteactivityexport\n        method: DELETE\n        description: Oracle Eloqua Delete an activity export definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activities-imports\n      path: /activities/imports\n      operations:\n      - name: createactivityimport\n        method: POST\n        description: Oracle Eloqua Create an activity import definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activities-imports-id-data\n      path: /activities/imports/{id}/data\n      operations:\n      - name: pushactivityimportdata\n        method: POST\n        description: Oracle Eloqua Push data to an activity import\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customobjects-parentid-exports\n      path: /customObjects/{parentId}/exports\n      operations:\n      - name: listcustomobjectexports\n        method: GET\n        description: Oracle Eloqua List custom object export definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcustomobjectexport\n        method: POST\n        description: Oracle Eloqua Create a custom object export definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customobjects-parentid-imports\n      path: /customObjects/{parentId}/imports\n      operations:\n      - name: listcustomobjectimports\n        method: GET\n        description: Oracle Eloqua List custom object import definitions\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcustomobjectimport\n        method: POST\n        description: Oracle Eloqua Create a custom object import definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customobjects-parentid-imports-id-data\n      path: /customObjects/{parentId}/imports/{id}/data\n      operations:\n      - name: pushcustomobjectimportdata\n        method: POST\n        description: Oracle Eloqua Push data to a custom object import\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customobjects\n      path: /customObjects\n      operations:\n      - name: listbulkcustomobjects\n        method: GET\n        description: Oracle Eloqua List available custom objects\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: syncs\n      path: /syncs\n      operations:\n      - name: listsyncs\n        method: GET\n        description: Oracle Eloqua List syncs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsync\n        method: POST\n        description: Oracle Eloqua Create a sync\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: syncs-id\n      path: /syncs/{id}\n      operations:\n      - name: getsync\n        method: GET\n        description: Oracle Eloqua Retrieve a sync\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: syncs-id-data\n      path: /syncs/{id}/data\n      operations:\n      - name: getsyncdata\n        method: GET\n        description:\
  \ Oracle Eloqua Retrieve sync data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesyncdata\n        method: DELETE\n        description: Oracle Eloqua Delete sync data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: syncs-id-logs\n      path: /syncs/{id}/logs\n      operations:\n      - name: getsynclogs\n        method: GET\n        description: Oracle Eloqua Retrieve sync logs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: syncs-id-rejects\n      path: /syncs/{id}/rejects\n      operations:\n      - name: getsyncrejects\n        method: GET\n        description: Oracle Eloqua Retrieve sync rejects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: eloqua-rest\n    description: REST adapter for Oracle Eloqua Bulk API.\n    resources:\n    - path: /contacts/exports\n      name: listcontactexports\n      operations:\n      - method: GET\n        name: listcontactexports\n        description: Oracle Eloqua List contact export definitions\n        call: eloqua.listcontactexports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/exports\n      name: createcontactexport\n      operations:\n      - method: POST\n        name: createcontactexport\n        description: Oracle Eloqua Create a contact export definition\n        call: eloqua.createcontactexport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/exports/{id}\n      name: getcontactexport\n      operations:\n      - method: GET\n        name: getcontactexport\n        description: Oracle Eloqua Retrieve a\
  \ contact export definition\n        call: eloqua.getcontactexport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/exports/{id}\n      name: updatecontactexport\n      operations:\n      - method: PUT\n        name: updatecontactexport\n        description: Oracle Eloqua Update a contact export definition\n        call: eloqua.updatecontactexport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/exports/{id}\n      name: deletecontactexport\n      operations:\n      - method: DELETE\n        name: deletecontactexport\n        description: Oracle Eloqua Delete a contact export definition\n        call: eloqua.deletecontactexport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/exports/{id}/data\n      name: getcontactexportdata\n      operations:\n      - method: GET\n        name: getcontactexportdata\n        description: Oracle Eloqua Retrieve\
  \ contact export data\n        call: eloqua.getcontactexportdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/imports\n      name: listcontactimports\n      operations:\n      - method: GET\n        name: listcontactimports\n        description: Oracle Eloqua List contact import definitions\n        call: eloqua.listcontactimports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/imports\n      name: createcontactimport\n      operations:\n      - method: POST\n        name: createcontactimport\n        description: Oracle Eloqua Create a contact import definition\n        call: eloqua.createcontactimport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/imports/{id}\n      name: getcontactimport\n      operations:\n      - method: GET\n        name: getcontactimport\n        description: Oracle Eloqua Retrieve a contact import definition\n \
  \       call: eloqua.getcontactimport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/imports/{id}\n      name: updatecontactimport\n      operations:\n      - method: PUT\n        name: updatecontactimport\n        description: Oracle Eloqua Update a contact import definition\n        call: eloqua.updatecontactimport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/imports/{id}\n      name: deletecontactimport\n      operations:\n      - method: DELETE\n        name: deletecontactimport\n        description: Oracle Eloqua Delete a contact import definition\n        call: eloqua.deletecontactimport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/imports/{id}/data\n      name: pushcontactimportdata\n      operations:\n      - method: POST\n        name: pushcontactimportdata\n        description: Oracle Eloqua Push data to a contact import\n \
  \       call: eloqua.pushcontactimportdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/imports/{id}/data\n      name: deletecontactimportdata\n      operations:\n      - method: DELETE\n        name: deletecontactimportdata\n        description: Oracle Eloqua Delete staged contact import data\n        call: eloqua.deletecontactimportdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/fields\n      name: listcontactfields\n      operations:\n      - method: GET\n        name: listcontactfields\n        description: Oracle Eloqua List contact fields\n        call: eloqua.listcontactfields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts/syncActions\n      name: createcontactsyncaction\n      operations:\n      - method: POST\n        name: createcontactsyncaction\n        description: Oracle Eloqua Create a contact sync action\n        call:\
  \ eloqua.createcontactsyncaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/exports\n      name: listaccountexports\n      operations:\n      - method: GET\n        name: listaccountexports\n        description: Oracle Eloqua List account export definitions\n        call: eloqua.listaccountexports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/exports\n      name: createaccountexport\n      operations:\n      - method: POST\n        name: createaccountexport\n        description: Oracle Eloqua Create an account export definition\n        call: eloqua.createaccountexport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/exports/{id}\n      name: getaccountexport\n      operations:\n      - method: GET\n        name: getaccountexport\n        description: Oracle Eloqua Retrieve an account export definition\n        call: eloqua.getaccountexport\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/exports/{id}\n      name: deleteaccountexport\n      operations:\n      - method: DELETE\n        name: deleteaccountexport\n        description: Oracle Eloqua Delete an account export definition\n        call: eloqua.deleteaccountexport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/imports\n      name: listaccountimports\n      operations:\n      - method: GET\n        name: listaccountimports\n        description: Oracle Eloqua List account import definitions\n        call: eloqua.listaccountimports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/imports\n      name: createaccountimport\n      operations:\n      - method: POST\n        name: createaccountimport\n        description: Oracle Eloqua Create an account import definition\n        call: eloqua.createaccountimport\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /accounts/imports/{id}\n      name: getaccountimport\n      operations:\n      - method: GET\n        name: getaccountimport\n        description: Oracle Eloqua Retrieve an account import definition\n        call: eloqua.getaccountimport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/imports/{id}\n      name: deleteaccountimport\n      operations:\n      - method: DELETE\n        name: deleteaccountimport\n        description: Oracle Eloqua Delete an account import definition\n        call: eloqua.deleteaccountimport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/imports/{id}/data\n      name: pushaccountimportdata\n      operations:\n      - method: POST\n        name: pushaccountimportdata\n        description: Oracle Eloqua Push data to an account import\n        call: eloqua.pushaccountimportdata\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /accounts/fields\n      name: listaccountfields\n      operations:\n      - method: GET\n        name: listaccountfields\n        description: Oracle Eloqua List account fields\n        call: eloqua.listaccountfields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /activities/exports\n      name: listactivityexports\n      operations:\n      - method: GET\n        name: listactivityexports\n        description: Oracle Eloqua List activity export definitions\n        call: eloqua.listactivityexports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /activities/exports\n      name: createactivityexport\n      operations:\n      - method: POST\n        name: createactivityexport\n        description: Oracle Eloqua Create an activity export definition\n        call: eloqua.createactivityexport\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /activities/exports/{id}\n      name: getactivityexport\n      operations:\n      - method: GET\n        name: getactivityexport\n        description: Oracle Eloqua Retrieve an activity export definition\n        call: eloqua.getactivityexport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /activities/exports/{id}\n      name: deleteactivityexport\n      operations:\n      - method: DELETE\n        name: deleteactivityexport\n        description: Oracle Eloqua Delete an activity export definition\n        call: eloqua.deleteactivityexport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /activities/imports\n      name: createactivityimport\n      operations:\n      - method: POST\n        name: createactivityimport\n        description: Oracle Eloqua Create an activity import definition\n        call: eloqua.createactivityimport\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /activities/imports/{id}/data\n      name: pushactivityimportdata\n      operations:\n      - method: POST\n        name: pushactivityimportdata\n        description: Oracle Eloqua Push data to an activity import\n        call: eloqua.pushactivityimportdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customObjects/{parentId}/exports\n      name: listcustomobjectexports\n      operations:\n      - method: GET\n        name: listcustomobjectexports\n        description: Oracle Eloqua List custom object export definitions\n        call: eloqua.listcustomobjectexports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customObjects/{parentId}/exports\n      name: createcustomobjectexport\n      operations:\n      - method: POST\n        name: createcustomobjectexport\n        description: Oracle Eloqua Create a custom object export definition\n        call: eloqua.createcustomobjectexport\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customObjects/{parentId}/imports\n      name: listcustomobjectimports\n      operations:\n      - method: GET\n        name: listcustomobjectimports\n        description: Oracle Eloqua List custom object import definitions\n        call: eloqua.listcustomobjectimports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customObjects/{parentId}/imports\n      name: createcustomobjectimport\n      operations:\n      - method: POST\n        name: createcustomobjectimport\n        description: Oracle Eloqua Create a custom object import definition\n        call: eloqua.createcustomobjectimport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customObjects/{parentId}/imports/{id}/data\n      name: pushcustomobjectimportdata\n      operations:\n      - method: POST\n        name: pushcustomobjectimportdata\n        description: Oracle\
  \ Eloqua Push data to a custom object import\n        call: eloqua.pushcustomobjectimportdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customObjects\n      name: listbulkcustomobjects\n      operations:\n      - method: GET\n        name: listbulkcustomobjects\n        description: Oracle Eloqua List available custom objects\n        call: eloqua.listbulkcustomobjects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /syncs\n      name: listsyncs\n      operations:\n      - method: GET\n        name: listsyncs\n        description: Oracle Eloqua List syncs\n        call: eloqua.listsyncs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /syncs\n      name: createsync\n      operations:\n      - method: POST\n        name: createsync\n        description: Oracle Eloqua Create a sync\n        call: eloqua.createsync\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /syncs/{id}\n      name: getsync\n      operations:\n      - method: GET\n        name: getsync\n        description: Oracle Eloqua Retrieve a sync\n        call: eloqua.getsync\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /syncs/{id}/data\n      name: getsyncdata\n      operations:\n      - method: GET\n        name: getsyncdata\n        description: Oracle Eloqua Retrieve sync data\n        call: eloqua.getsyncdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /syncs/{id}/data\n      name: deletesyncdata\n      operations:\n      - method: DELETE\n        name: deletesyncdata\n        description: Oracle Eloqua Delete sync data\n        call: eloqua.deletesyncdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /syncs/{id}/logs\n      name: getsynclogs\n      operations:\n      - method: GET\n        name: getsynclogs\n        description:\
  \ Oracle Eloqua Retrieve sync logs\n        call: eloqua.getsynclogs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /syncs/{id}/rejects\n      name: getsyncrejects\n      operations:\n      - method: GET\n        name: getsyncrejects\n        description: Oracle Eloqua Retrieve sync rejects\n        call: eloqua.getsyncrejects\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: eloqua-mcp\n    transport: http\n    description: MCP adapter for Oracle Eloqua Bulk API for AI agent use.\n    tools:\n    - name: listcontactexports\n      description: Oracle Eloqua List contact export definitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eloqua.listcontactexports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontactexport\n      description: Oracle Eloqua Create a contact export definition\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eloqua.createcontactexport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontactexport\n      description: Oracle Eloqua Retrieve a contact export definition\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eloqua.getcontactexport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecontactexport\n      description: Oracle Eloqua Update a contact export definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: eloqua.updatecontactexport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontactexport\n      description: Oracle Eloqua Delete a contact export definition\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n \
  \     call: eloqua.deletecontactexport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcontactexportdata\n      description: Oracle Eloqua Retrieve contact export data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eloqua.getcontactexportdata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontactimports\n      description: Oracle Eloqua List contact import definitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eloqua.listcontactimports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontactimport\n      description: Oracle Eloqua Create a contact import definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eloqua.createcontactimport\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getcontactimport\n      description: Oracle Eloqua Retrieve a contact import definition\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eloqua.getcontactimport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecontactimport\n      description: Oracle Eloqua Update a contact import definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: eloqua.updatecontactimport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontactimport\n      description: Oracle Eloqua Delete a contact import definition\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: eloqua.deletecontactimport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pushcontactimportdata\n      description: Oracle Eloqua Push data to a contact\
  \ import\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eloqua.pushcontactimportdata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecontactimportdata\n      description: Oracle Eloqua Delete staged contact import data\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: eloqua.deletecontactimportdata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontactfields\n      description: Oracle Eloqua List contact fields\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eloqua.listcontactfields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcontactsyncaction\n      description: Oracle Eloqua Create a contact sync action\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: eloqua.createcontactsyncaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listaccountexports\n      description: Oracle Eloqua List account export definitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: eloqua.listaccountexports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createaccountexport\n      description: Oracle Eloqua Create an account export definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: eloqua.createaccountexport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountexport\n      description: Oracle \n\n# --- truncated at 32 KB (39 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/eloqua/refs/heads/main/capabilities/eloqua-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/eloqua/refs/heads/main/capabilities/eloqua-capability.yaml
tags:
- Eloqua
- API
tools:
- description: Oracle Eloqua List contact export definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontactexports
- description: Oracle Eloqua Create a contact export definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontactexport
- description: Oracle Eloqua Retrieve a contact export definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontactexport
- description: Oracle Eloqua Update a contact export definition
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecontactexport
- description: Oracle Eloqua Delete a contact export definition
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontactexport
- description: Oracle Eloqua Retrieve contact export data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontactexportdata
- description: Oracle Eloqua List contact import definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontactimports
- description: Oracle Eloqua Create a contact import definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontactimport
- description: Oracle Eloqua Retrieve a contact import definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontactimport
- description: Oracle Eloqua Update a contact import definition
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecontactimport
- description: Oracle Eloqua Delete a contact import definition
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontactimport
- description: Oracle Eloqua Push data to a contact import
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pushcontactimportdata
- description: Oracle Eloqua Delete staged contact import data
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecontactimportdata
- description: Oracle Eloqua List contact fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontactfields
- description: Oracle Eloqua Create a contact sync action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontactsyncaction
- description: Oracle Eloqua List account export definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccountexports
- description: Oracle Eloqua Create an account export definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaccountexport
- description: Oracle Eloqua Retrieve an account export definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountexport
- description: Oracle Eloqua Delete an account export definition
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaccountexport
- description: Oracle Eloqua List account import definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccountimports
- description: Oracle Eloqua Create an account import definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaccountimport
- description: Oracle Eloqua Retrieve an account import definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountimport
- description: Oracle Eloqua Delete an account import definition
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaccountimport
- description: Oracle Eloqua Push data to an account import
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pushaccountimportdata
- description: Oracle Eloqua List account fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccountfields
- description: Oracle Eloqua List activity export definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listactivityexports
- description: Oracle Eloqua Create an activity export definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createactivityexport
- description: Oracle Eloqua Retrieve an activity export definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getactivityexport
- description: Oracle Eloqua Delete an activity export definition
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteactivityexport
- description: Oracle Eloqua Create an activity import definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createactivityimport
- description: Oracle Eloqua Push data to an activity import
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pushactivityimportdata
- description: Oracle Eloqua List custom object export definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcustomobjectexports
- description: Oracle Eloqua Create a custom object export definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcustomobjectexport
- description: Oracle Eloqua List custom object import definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcustomobjectimports
- description: Oracle Eloqua Create a custom object import definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcustomobjectimport
- description: Oracle Eloqua Push data to a custom object import
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pushcustomobjectimportdata
- description: Oracle Eloqua List available custom objects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbulkcustomobjects
- description: Oracle Eloqua List syncs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsyncs
- description: Oracle Eloqua Create a sync
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsync
- description: Oracle Eloqua Retrieve a sync
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsync
- description: Oracle Eloqua Retrieve sync data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsyncdata
- description: Oracle Eloqua Delete sync data
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesyncdata
- description: Oracle Eloqua Retrieve sync logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsynclogs
- description: Oracle Eloqua Retrieve sync rejects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsyncrejects
---
