---
categories: []
consumed_apis: []
description: The Honeycomb API is a REST API that provides programmatic access to the Honeycomb observability platform. It enables developers to manage datasets and columns, configure SLOs and burn alerts, set up triggers and recipients, manage boards and markers, administer environments, API keys, and access auth, query annotations, calculated fields, marker settings, reporting, dataset definitions, and service maps.
layout: capability
name: Honeycomb API
operations:
- description: Authenticate API key
  method: GET
  name: getauth
  path: /1/auth
- description: List authorizations
  method: GET
  name: listauthorizations
  path: /1/auth/permissions
- description: List all datasets
  method: GET
  name: listdatasets
  path: /1/datasets
- description: Create a dataset
  method: POST
  name: createdataset
  path: /1/datasets
- description: Get a dataset
  method: GET
  name: getdataset
  path: /1/datasets/{datasetSlug}
- description: Update a dataset
  method: PUT
  name: updatedataset
  path: /1/datasets/{datasetSlug}
- description: List all columns
  method: GET
  name: listcolumns
  path: /1/columns/{datasetSlug}
- description: Create a column
  method: POST
  name: createcolumn
  path: /1/columns/{datasetSlug}
- description: Get a column
  method: GET
  name: getcolumn
  path: /1/columns/{datasetSlug}/{columnId}
- description: Update a column
  method: PUT
  name: updatecolumn
  path: /1/columns/{datasetSlug}/{columnId}
- description: Delete a column
  method: DELETE
  name: deletecolumn
  path: /1/columns/{datasetSlug}/{columnId}
- description: Get dataset definition
  method: GET
  name: getdatasetdefinition
  path: /1/dataset_definitions/{datasetSlug}
- description: Update dataset definition
  method: PUT
  name: updatedatasetdefinition
  path: /1/dataset_definitions/{datasetSlug}
- description: List calculated fields
  method: GET
  name: listcalculatedfields
  path: /1/calculated_fields/{datasetSlug}
- description: Create a calculated field
  method: POST
  name: createcalculatedfield
  path: /1/calculated_fields/{datasetSlug}
- description: Get a calculated field
  method: GET
  name: getcalculatedfield
  path: /1/calculated_fields/{datasetSlug}/{calculatedFieldId}
- description: Update a calculated field
  method: PUT
  name: updatecalculatedfield
  path: /1/calculated_fields/{datasetSlug}/{calculatedFieldId}
- description: Delete a calculated field
  method: DELETE
  name: deletecalculatedfield
  path: /1/calculated_fields/{datasetSlug}/{calculatedFieldId}
- description: List all boards
  method: GET
  name: listboards
  path: /1/boards
- description: Create a board
  method: POST
  name: createboard
  path: /1/boards
- description: Get a board
  method: GET
  name: getboard
  path: /1/boards/{boardId}
- description: Update a board
  method: PUT
  name: updateboard
  path: /1/boards/{boardId}
- description: Delete a board
  method: DELETE
  name: deleteboard
  path: /1/boards/{boardId}
- description: List all markers
  method: GET
  name: listmarkers
  path: /1/markers/{datasetSlug}
- description: Create a marker
  method: POST
  name: createmarker
  path: /1/markers/{datasetSlug}
- description: Update a marker
  method: PUT
  name: updatemarker
  path: /1/markers/{datasetSlug}/{markerId}
- description: Delete a marker
  method: DELETE
  name: deletemarker
  path: /1/markers/{datasetSlug}/{markerId}
- description: List all marker settings
  method: GET
  name: listmarkersettings
  path: /1/marker_settings/{datasetSlug}
- description: Create a marker setting
  method: POST
  name: createmarkersetting
  path: /1/marker_settings/{datasetSlug}
- description: Update a marker setting
  method: PUT
  name: updatemarkersetting
  path: /1/marker_settings/{datasetSlug}/{markerSettingId}
- description: Delete a marker setting
  method: DELETE
  name: deletemarkersetting
  path: /1/marker_settings/{datasetSlug}/{markerSettingId}
- description: List all triggers
  method: GET
  name: listtriggers
  path: /1/triggers/{datasetSlug}
- description: Create a trigger
  method: POST
  name: createtrigger
  path: /1/triggers/{datasetSlug}
- description: Get a trigger
  method: GET
  name: gettrigger
  path: /1/triggers/{datasetSlug}/{triggerId}
- description: Update a trigger
  method: PUT
  name: updatetrigger
  path: /1/triggers/{datasetSlug}/{triggerId}
- description: Delete a trigger
  method: DELETE
  name: deletetrigger
  path: /1/triggers/{datasetSlug}/{triggerId}
- description: List all recipients
  method: GET
  name: listrecipients
  path: /1/recipients
- description: Create a recipient
  method: POST
  name: createrecipient
  path: /1/recipients
- description: Get a recipient
  method: GET
  name: getrecipient
  path: /1/recipients/{recipientId}
- description: Update a recipient
  method: PUT
  name: updaterecipient
  path: /1/recipients/{recipientId}
- description: Delete a recipient
  method: DELETE
  name: deleterecipient
  path: /1/recipients/{recipientId}
- description: List all SLOs
  method: GET
  name: listslos
  path: /1/slos/{datasetSlug}
- description: Create an SLO
  method: POST
  name: createslo
  path: /1/slos/{datasetSlug}
- description: Get an SLO
  method: GET
  name: getslo
  path: /1/slos/{datasetSlug}/{sloId}
- description: Update an SLO
  method: PUT
  name: updateslo
  path: /1/slos/{datasetSlug}/{sloId}
- description: Delete an SLO
  method: DELETE
  name: deleteslo
  path: /1/slos/{datasetSlug}/{sloId}
- description: List all burn alerts
  method: GET
  name: listburnalerts
  path: /1/burn_alerts/{datasetSlug}
- description: Create a burn alert
  method: POST
  name: createburnalert
  path: /1/burn_alerts/{datasetSlug}
- description: Get a burn alert
  method: GET
  name: getburnalert
  path: /1/burn_alerts/{datasetSlug}/{burnAlertId}
- description: Update a burn alert
  method: PUT
  name: updateburnalert
  path: /1/burn_alerts/{datasetSlug}/{burnAlertId}
- description: Delete a burn alert
  method: DELETE
  name: deleteburnalert
  path: /1/burn_alerts/{datasetSlug}/{burnAlertId}
- description: Get SLO report
  method: GET
  name: getsloreport
  path: /1/slo_report/{datasetSlug}/{sloId}
- description: List all environments
  method: GET
  name: listenvironments
  path: /1/environments
- description: Create an environment
  method: POST
  name: createenvironment
  path: /1/environments
- description: Get an environment
  method: GET
  name: getenvironment
  path: /1/environments/{environmentId}
- description: Update an environment
  method: PUT
  name: updateenvironment
  path: /1/environments/{environmentId}
- description: Delete an environment
  method: DELETE
  name: deleteenvironment
  path: /1/environments/{environmentId}
- description: List all API keys
  method: GET
  name: listapikeys
  path: /1/api_keys
- description: Create an API key
  method: POST
  name: createapikey
  path: /1/api_keys
- description: Get an API key
  method: GET
  name: getapikey
  path: /1/api_keys/{keyId}
personas: []
provider_name: honeycomb
provider_slug: honeycomb
search_terms:
- update a column
- create a calculated field
- update an slo
- update a board
- createmarkersetting
- listdatasets
- delete a calculated field
- update a recipient
- getapikey
- createslo
- updatedataset
- get an environment
- deletetrigger
- get a burn alert
- deleterecipient
- authenticate api key
- api
- create a column
- create a marker setting
- listcalculatedfields
- create a board
- listtriggers
- listenvironments
- deleteburnalert
- listauthorizations
- createburnalert
- deleteenvironment
- getdataset
- delete a burn alert
- getenvironment
- deleteslo
- delete an environment
- list all environments
- get a calculated field
- get an api key
- updatemarkersetting
- createcolumn
- getcalculatedfield
- update a dataset
- create an environment
- createdataset
- list all slos
- delete a column
- deletecolumn
- get dataset definition
- delete an slo
- list all triggers
- updatecalculatedfield
- createcalculatedfield
- updatemarker
- update dataset definition
- createboard
- create a recipient
- get a recipient
- updatecolumn
- getboard
- deletecalculatedfield
- listapikeys
- getrecipient
- list calculated fields
- gettrigger
- update a trigger
- create a marker
- updatedatasetdefinition
- get a board
- createmarker
- get an slo
- honeycomb
- create a burn alert
- createenvironment
- deleteboard
- delete a marker
- updateburnalert
- list all marker settings
- update an environment
- updateboard
- list all columns
- update a marker setting
- update a calculated field
- list all burn alerts
- getcolumn
- listboards
- deletemarkersetting
- create an api key
- create a trigger
- updateslo
- listslos
- deletemarker
- list all api keys
- listrecipients
- delete a trigger
- create an slo
- listmarkersettings
- create a dataset
- getburnalert
- list all recipients
- getslo
- createrecipient
- getsloreport
- listcolumns
- listmarkers
- get a column
- updateenvironment
- list all boards
- update a marker
- list authorizations
- delete a recipient
- getauth
- list all datasets
- getdatasetdefinition
- delete a board
- createtrigger
- get slo report
- delete a marker setting
- listburnalerts
- updatetrigger
- updaterecipient
- get a trigger
- update a burn alert
- get a dataset
- createapikey
- list all markers
slug: honeycomb-capability
source_filename: honeycomb-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Honeycomb API\n  description: The Honeycomb API is a REST API that provides programmatic access to the Honeycomb observability platform.\n    It enables developers to manage datasets and columns, configure SLOs and burn alerts, set up triggers and recipients,\n    manage boards and markers, administer environments, API keys, and access auth, query annotations, calculated fields, marker\n    settings, reporting, dataset definitions, and service maps.\n  tags:\n  - Honeycomb\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: honeycomb\n    baseUri: https://api.honeycomb.io\n    description: Honeycomb API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Honeycomb-Team\n      value: '{{HONEYCOMB_TOKEN}}'\n    resources:\n    - name: 1-auth\n      path: /1/auth\n      operations:\n      - name: getauth\n        method: GET\n        description:\
  \ Authenticate API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-auth-permissions\n      path: /1/auth/permissions\n      operations:\n      - name: listauthorizations\n        method: GET\n        description: List authorizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-datasets\n      path: /1/datasets\n      operations:\n      - name: listdatasets\n        method: GET\n        description: List all datasets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdataset\n        method: POST\n        description: Create a dataset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-datasets-datasetslug\n   \
  \   path: /1/datasets/{datasetSlug}\n      operations:\n      - name: getdataset\n        method: GET\n        description: Get a dataset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedataset\n        method: PUT\n        description: Update a dataset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-columns-datasetslug\n      path: /1/columns/{datasetSlug}\n      operations:\n      - name: listcolumns\n        method: GET\n        description: List all columns\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcolumn\n        method: POST\n        description: Create a column\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: 1-columns-datasetslug-columnid\n      path: /1/columns/{datasetSlug}/{columnId}\n      operations:\n      - name: getcolumn\n        method: GET\n        description: Get a column\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecolumn\n        method: PUT\n        description: Update a column\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecolumn\n        method: DELETE\n        description: Delete a column\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-dataset-definitions-datasetslug\n      path: /1/dataset_definitions/{datasetSlug}\n      operations:\n      - name: getdatasetdefinition\n        method: GET\n        description: Get dataset definition\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedatasetdefinition\n        method: PUT\n        description: Update dataset definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-calculated-fields-datasetslug\n      path: /1/calculated_fields/{datasetSlug}\n      operations:\n      - name: listcalculatedfields\n        method: GET\n        description: List calculated fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcalculatedfield\n        method: POST\n        description: Create a calculated field\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-calculated-fields-datasetslug-calculatedfieldi\n      path: /1/calculated_fields/{datasetSlug}/{calculatedFieldId}\n\
  \      operations:\n      - name: getcalculatedfield\n        method: GET\n        description: Get a calculated field\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecalculatedfield\n        method: PUT\n        description: Update a calculated field\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecalculatedfield\n        method: DELETE\n        description: Delete a calculated field\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-boards\n      path: /1/boards\n      operations:\n      - name: listboards\n        method: GET\n        description: List all boards\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: createboard\n        method: POST\n        description: Create a board\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-boards-boardid\n      path: /1/boards/{boardId}\n      operations:\n      - name: getboard\n        method: GET\n        description: Get a board\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateboard\n        method: PUT\n        description: Update a board\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteboard\n        method: DELETE\n        description: Delete a board\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-markers-datasetslug\n      path: /1/markers/{datasetSlug}\n    \
  \  operations:\n      - name: listmarkers\n        method: GET\n        description: List all markers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmarker\n        method: POST\n        description: Create a marker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-markers-datasetslug-markerid\n      path: /1/markers/{datasetSlug}/{markerId}\n      operations:\n      - name: updatemarker\n        method: PUT\n        description: Update a marker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemarker\n        method: DELETE\n        description: Delete a marker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ 1-marker-settings-datasetslug\n      path: /1/marker_settings/{datasetSlug}\n      operations:\n      - name: listmarkersettings\n        method: GET\n        description: List all marker settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmarkersetting\n        method: POST\n        description: Create a marker setting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-marker-settings-datasetslug-markersettingid\n      path: /1/marker_settings/{datasetSlug}/{markerSettingId}\n      operations:\n      - name: updatemarkersetting\n        method: PUT\n        description: Update a marker setting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemarkersetting\n        method: DELETE\n        description:\
  \ Delete a marker setting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-triggers-datasetslug\n      path: /1/triggers/{datasetSlug}\n      operations:\n      - name: listtriggers\n        method: GET\n        description: List all triggers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtrigger\n        method: POST\n        description: Create a trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-triggers-datasetslug-triggerid\n      path: /1/triggers/{datasetSlug}/{triggerId}\n      operations:\n      - name: gettrigger\n        method: GET\n        description: Get a trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: updatetrigger\n        method: PUT\n        description: Update a trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetrigger\n        method: DELETE\n        description: Delete a trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-recipients\n      path: /1/recipients\n      operations:\n      - name: listrecipients\n        method: GET\n        description: List all recipients\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrecipient\n        method: POST\n        description: Create a recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-recipients-recipientid\n      path:\
  \ /1/recipients/{recipientId}\n      operations:\n      - name: getrecipient\n        method: GET\n        description: Get a recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterecipient\n        method: PUT\n        description: Update a recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterecipient\n        method: DELETE\n        description: Delete a recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-slos-datasetslug\n      path: /1/slos/{datasetSlug}\n      operations:\n      - name: listslos\n        method: GET\n        description: List all SLOs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: createslo\n        method: POST\n        description: Create an SLO\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-slos-datasetslug-sloid\n      path: /1/slos/{datasetSlug}/{sloId}\n      operations:\n      - name: getslo\n        method: GET\n        description: Get an SLO\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateslo\n        method: PUT\n        description: Update an SLO\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteslo\n        method: DELETE\n        description: Delete an SLO\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-burn-alerts-datasetslug\n      path: /1/burn_alerts/{datasetSlug}\n\
  \      operations:\n      - name: listburnalerts\n        method: GET\n        description: List all burn alerts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createburnalert\n        method: POST\n        description: Create a burn alert\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-burn-alerts-datasetslug-burnalertid\n      path: /1/burn_alerts/{datasetSlug}/{burnAlertId}\n      operations:\n      - name: getburnalert\n        method: GET\n        description: Get a burn alert\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateburnalert\n        method: PUT\n        description: Update a burn alert\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: deleteburnalert\n        method: DELETE\n        description: Delete a burn alert\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-slo-report-datasetslug-sloid\n      path: /1/slo_report/{datasetSlug}/{sloId}\n      operations:\n      - name: getsloreport\n        method: GET\n        description: Get SLO report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-environments\n      path: /1/environments\n      operations:\n      - name: listenvironments\n        method: GET\n        description: List all environments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createenvironment\n        method: POST\n        description: Create an environment\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-environments-environmentid\n      path: /1/environments/{environmentId}\n      operations:\n      - name: getenvironment\n        method: GET\n        description: Get an environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateenvironment\n        method: PUT\n        description: Update an environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteenvironment\n        method: DELETE\n        description: Delete an environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-api-keys\n      path: /1/api_keys\n      operations:\n      - name: listapikeys\n        method: GET\n        description:\
  \ List all API keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapikey\n        method: POST\n        description: Create an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-api-keys-keyid\n      path: /1/api_keys/{keyId}\n      operations:\n      - name: getapikey\n        method: GET\n        description: Get an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: honeycomb-rest\n    description: REST adapter for Honeycomb API.\n    resources:\n    - path: /1/auth\n      name: getauth\n      operations:\n      - method: GET\n        name: getauth\n        description: Authenticate API key\n        call: honeycomb.getauth\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /1/auth/permissions\n      name: listauthorizations\n      operations:\n      - method: GET\n        name: listauthorizations\n        description: List authorizations\n        call: honeycomb.listauthorizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/datasets\n      name: listdatasets\n      operations:\n      - method: GET\n        name: listdatasets\n        description: List all datasets\n        call: honeycomb.listdatasets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/datasets\n      name: createdataset\n      operations:\n      - method: POST\n        name: createdataset\n        description: Create a dataset\n        call: honeycomb.createdataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/datasets/{datasetSlug}\n      name: getdataset\n      operations:\n      - method: GET\n    \
  \    name: getdataset\n        description: Get a dataset\n        call: honeycomb.getdataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/datasets/{datasetSlug}\n      name: updatedataset\n      operations:\n      - method: PUT\n        name: updatedataset\n        description: Update a dataset\n        call: honeycomb.updatedataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/columns/{datasetSlug}\n      name: listcolumns\n      operations:\n      - method: GET\n        name: listcolumns\n        description: List all columns\n        call: honeycomb.listcolumns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/columns/{datasetSlug}\n      name: createcolumn\n      operations:\n      - method: POST\n        name: createcolumn\n        description: Create a column\n        call: honeycomb.createcolumn\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /1/columns/{datasetSlug}/{columnId}\n      name: getcolumn\n      operations:\n      - method: GET\n        name: getcolumn\n        description: Get a column\n        call: honeycomb.getcolumn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/columns/{datasetSlug}/{columnId}\n      name: updatecolumn\n      operations:\n      - method: PUT\n        name: updatecolumn\n        description: Update a column\n        call: honeycomb.updatecolumn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/columns/{datasetSlug}/{columnId}\n      name: deletecolumn\n      operations:\n      - method: DELETE\n        name: deletecolumn\n        description: Delete a column\n        call: honeycomb.deletecolumn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/dataset_definitions/{datasetSlug}\n      name: getdatasetdefinition\n      operations:\n     \
  \ - method: GET\n        name: getdatasetdefinition\n        description: Get dataset definition\n        call: honeycomb.getdatasetdefinition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/dataset_definitions/{datasetSlug}\n      name: updatedatasetdefinition\n      operations:\n      - method: PUT\n        name: updatedatasetdefinition\n        description: Update dataset definition\n        call: honeycomb.updatedatasetdefinition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/calculated_fields/{datasetSlug}\n      name: listcalculatedfields\n      operations:\n      - method: GET\n        name: listcalculatedfields\n        description: List calculated fields\n        call: honeycomb.listcalculatedfields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/calculated_fields/{datasetSlug}\n      name: createcalculatedfield\n      operations:\n      - method: POST\n\
  \        name: createcalculatedfield\n        description: Create a calculated field\n        call: honeycomb.createcalculatedfield\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/calculated_fields/{datasetSlug}/{calculatedFieldId}\n      name: getcalculatedfield\n      operations:\n      - method: GET\n        name: getcalculatedfield\n        description: Get a calculated field\n        call: honeycomb.getcalculatedfield\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/calculated_fields/{datasetSlug}/{calculatedFieldId}\n      name: updatecalculatedfield\n      operations:\n      - method: PUT\n        name: updatecalculatedfield\n        description: Update a calculated field\n        call: honeycomb.updatecalculatedfield\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/calculated_fields/{datasetSlug}/{calculatedFieldId}\n      name: deletecalculatedfield\n   \
  \   operations:\n      - method: DELETE\n        name: deletecalculatedfield\n        description: Delete a calculated field\n        call: honeycomb.deletecalculatedfield\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/boards\n      name: listboards\n      operations:\n      - method: GET\n        name: listboards\n        description: List all boards\n        call: honeycomb.listboards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/boards\n      name: createboard\n      operations:\n      - method: POST\n        name: createboard\n        description: Create a board\n        call: honeycomb.createboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/boards/{boardId}\n      name: getboard\n      operations:\n      - method: GET\n        name: getboard\n        description: Get a board\n        call: honeycomb.getboard\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /1/boards/{boardId}\n      name: updateboard\n      operations:\n      - method: PUT\n        name: updateboard\n        description: Update a board\n        call: honeycomb.updateboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/boards/{boardId}\n      name: deleteboard\n      operations:\n      - method: DELETE\n        name: deleteboard\n        description: Delete a board\n        call: honeycomb.deleteboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/markers/{datasetSlug}\n      name: listmarkers\n      operations:\n      - method: GET\n        name: listmarkers\n        description: List all markers\n        call: honeycomb.listmarkers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/markers/{datasetSlug}\n      name: createmarker\n      operations:\n      - method: POST\n        name: createmarker\n    \
  \    description: Create a marker\n        call: honeycomb.createmarker\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/markers/{datasetSlug}/{markerId}\n      name: updatemarker\n      operations:\n      - method: PUT\n        name: updatemarker\n        description: Update a marker\n        call: honeycomb.updatemarker\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/markers/{datasetSlug}/{markerId}\n      name: deletemarker\n      operations:\n      - method: DELETE\n        name: deletemarker\n        description: Delete a marker\n        call: honeycomb.deletemarker\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/marker_settings/{datasetSlug}\n      name: listmarkersettings\n      operations:\n      - method: GET\n        name: listmarkersettings\n        description: List all marker settings\n        call: honeycomb.listmarkersettings\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /1/marker_settings/{datasetSlug}\n      name: createmarkersetting\n      operations:\n      - method: POST\n        name: createmarkersetting\n        description: Create a marker setting\n        call: honeycomb.createmarkersetting\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/marker_settings/{datasetSlug}/{markerSettingId}\n      name: updatemarkersetting\n      operations:\n      - method: PUT\n        name: updatemarkersetting\n        description: Update a marker setting\n        call: honeycomb.updatemarkersetting\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/marker_settings/{datasetSlug}/{markerSettingId}\n      name: deletemarkersetting\n      operations:\n      - method: DELETE\n        name: deletemarkersetting\n        description: Delete a marker setting\n        call: honeycomb.deletemarkersetting\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /1/triggers/{datasetSlug}\n      name: listtriggers\n      operations:\n      - method: GET\n        name: listtriggers\n        description: List all triggers\n        call: honeycomb.listtriggers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/triggers/{datasetSlug}\n      name: createtrigger\n      operations:\n      - method: POST\n        name: createtrigger\n        description: Create a trigger\n        call: honeycomb.createtrigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/triggers/{datasetSlug}/{triggerId}\n      name: gettrigger\n      operations:\n      - method: GET\n        name: gettrigger\n        description: Get a trigger\n        call: honeycomb.gettrigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/triggers/{datasetSlug}/{triggerId}\n      name: updatetrigger\n      operations:\n\
  \      - method: PUT\n        name: updatetrigger\n        description: Update a trigger\n        call: honeycomb.updatetrigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/triggers/{datasetSlug}/{triggerId}\n      name: deletetrigger\n      operations:\n      - method: DELETE\n        name: deletetrigger\n        description: Delete a trigger\n        call: honeycomb.deletetrigger\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/recipients\n      name: listrecipients\n      operations:\n      - method: GET\n        name: listrecipients\n        description: List all recipients\n        call: honeycomb.listrecipients\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/recipients\n      name: createrecipient\n      operations:\n      - method: POST\n        name: createrecipient\n        description: Create a recipient\n        call: honeycomb.createrecipient\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/recipients/{recipientId}\n      name: getrecipient\n      operations:\n      - method: GET\n        name: getrecipient\n        description: Get a recipient\n        call: honeycomb.getrecipient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/recipients/{recipientId}\n      name: updaterecipient\n      operations:\n      - method: PUT\n        name: updaterecipient\n        description: Update a recipient\n        call: honeycomb.updaterecipient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/recipients/{recipientId}\n      name: deleterecipient\n      operations:\n      - method: DELETE\n        name: deleterecipient\n        description: Delete a recipient\n        call: honeycomb.deleterecipient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/slos/{datasetSlug}\n      name:\
  \ listslos\n      operations:\n      - method: GET\n        name: listslos\n        description: List all SLOs\n        call: honeycomb.listslos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/slos/{datasetSlug}\n      name: createslo\n      operations:\n      - method: POST\n        name: createslo\n        description: Create an SLO\n        call: honeycomb.createslo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/slos/{datasetSlug}/{sloId}\n      name: getslo\n      operations:\n      - method: GET\n        name: getslo\n        description: Get an SLO\n        call: honeycomb.getslo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/slos/{datasetSlug}/{sloId}\n      name: updateslo\n      operations:\n      - method: PUT\n        name: updateslo\n        description: Update an SLO\n        call: honeycomb.updateslo\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /1/slos/{datasetSlug}/{sloId}\n      name: deleteslo\n      operations:\n      - method: DELETE\n        name: deleteslo\n        description: Delete an SLO\n        call: honeycomb.deleteslo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/burn_alerts/{datasetSlug}\n      name: listburnalerts\n      operations:\n      - method: GET\n        name: listburnalerts\n        description: List all burn alerts\n        call: honeycomb.listburnalerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/burn_alerts/{datasetSlug}\n      name: createburnalert\n      operations:\n      - method: POST\n        name: createburnalert\n        description: Create a burn alert\n        call: honeycomb.createburnalert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/burn_alerts/{datasetSlug}/{burnAlertId}\n      name: getburnalert\n      operations:\n\
  \      - method: GET\n        name: getburnalert\n        description: Get a burn alert\n        call: honeycomb.getburnalert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/burn_alerts/{datasetSlug}/{burnAlertId}\n      name: updateburnalert\n      operations:\n      - method: PUT\n        name: updateburnalert\n        description: Update a burn alert\n        call: honeycomb.updateburnalert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/burn_alerts/{datasetSlug}/{burnAlertId}\n      name: deleteburnalert\n      operations:\n      - method: DELETE\n        name: deleteburnalert\n        description: Delete a burn alert\n        call: honeycomb.deleteburnalert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/slo_report/{datasetSlug}/{sloId}\n      name: getsloreport\n      operations:\n      - method: GET\n        name: getsloreport\n        description: Get SLO\
  \ report\n        call: honeycomb.getsloreport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/environments\n      name: listenvironments\n      operations:\n      - method: GET\n        name: listenvironments\n        description: List all environments\n        call: honeycomb.listenvironments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/environments\n      name: createenvironment\n      operations:\n      - method: POST\n        name: createenvironment\n        description: Create an environment\n        call: honeycomb.createenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/environments/{environmentId}\n      name: getenvironment\n      operations:\n      - method: GET\n        name: getenvironment\n        description: Get an environment\n        call: honeycomb.getenvironment\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /1/environments/{environmentId}\n      name: updateenvironment\n      operations:\n      - method: PUT\n        name: updateenvironment\n        description: Update an environment\n        call: honeycomb.updateenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/environments/{environmentId}\n      name: deleteenvironment\n      operations:\n      - method: DELETE\n        name: deleteenvironment\n        description: Delete an environment\n        call: honeycomb.deleteenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1/api_keys\n      name: listapikeys\n      operations:\n      - method: GET\n        name: listapikeys\n        description: List all API keys\n        call: honeycomb.listapikeys\n        outputParameters:\n        - type: object\n     \n\n# --- truncated at 32 KB (47 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/honeycomb/refs/heads/main/capabilities/honeycomb-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/honeycomb/refs/heads/main/capabilities/honeycomb-capability.yaml
tags:
- Honeycomb
- API
tools:
- description: Authenticate API key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauth
- description: List authorizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauthorizations
- description: List all datasets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatasets
- description: Create a dataset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdataset
- description: Get a dataset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdataset
- description: Update a dataset
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedataset
- description: List all columns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcolumns
- description: Create a column
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcolumn
- description: Get a column
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcolumn
- description: Update a column
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecolumn
- description: Delete a column
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecolumn
- description: Get dataset definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatasetdefinition
- description: Update dataset definition
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedatasetdefinition
- description: List calculated fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcalculatedfields
- description: Create a calculated field
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcalculatedfield
- description: Get a calculated field
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcalculatedfield
- description: Update a calculated field
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecalculatedfield
- description: Delete a calculated field
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecalculatedfield
- description: List all boards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listboards
- description: Create a board
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createboard
- description: Get a board
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getboard
- description: Update a board
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateboard
- description: Delete a board
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteboard
- description: List all markers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmarkers
- description: Create a marker
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmarker
- description: Update a marker
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemarker
- description: Delete a marker
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemarker
- description: List all marker settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmarkersettings
- description: Create a marker setting
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmarkersetting
- description: Update a marker setting
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemarkersetting
- description: Delete a marker setting
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemarkersetting
- description: List all triggers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtriggers
- description: Create a trigger
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtrigger
- description: Get a trigger
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettrigger
- description: Update a trigger
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatetrigger
- description: Delete a trigger
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetrigger
- description: List all recipients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecipients
- description: Create a recipient
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrecipient
- description: Get a recipient
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrecipient
- description: Update a recipient
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterecipient
- description: Delete a recipient
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterecipient
- description: List all SLOs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listslos
- description: Create an SLO
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createslo
- description: Get an SLO
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getslo
- description: Update an SLO
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateslo
- description: Delete an SLO
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteslo
- description: List all burn alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listburnalerts
- description: Create a burn alert
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createburnalert
- description: Get a burn alert
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getburnalert
- description: Update a burn alert
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateburnalert
- description: Delete a burn alert
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteburnalert
- description: Get SLO report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsloreport
- description: List all environments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listenvironments
- description: Create an environment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createenvironment
- description: Get an environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironment
- description: Update an environment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateenvironment
- description: Delete an environment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteenvironment
- description: List all API keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapikeys
- description: Create an API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapikey
- description: Get an API key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapikey
---
