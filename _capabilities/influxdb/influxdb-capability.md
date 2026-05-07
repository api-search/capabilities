---
categories: []
consumed_apis: []
description: Complete InfluxDB Cloud API API capability.
layout: capability
name: Complete InfluxDB Cloud API
operations:
- description: List all top level routes
  method: GET
  name: getroutes
  path: /api/v2
- description: List authorizations
  method: GET
  name: getauthorizations
  path: /api/v2/authorizations
- description: Create an authorization
  method: POST
  name: postauthorizations
  path: /api/v2/authorizations
- description: Delete an authorization
  method: DELETE
  name: deleteauthorizationsid
  path: /api/v2/authorizations/{authID}
- description: Retrieve an authorization
  method: GET
  name: getauthorizationsid
  path: /api/v2/authorizations/{authID}
- description: Update an API token to be active or inactive
  method: PATCH
  name: patchauthorizationsid
  path: /api/v2/authorizations/{authID}
- description: List buckets
  method: GET
  name: getbuckets
  path: /api/v2/buckets
- description: Create a bucket
  method: POST
  name: postbuckets
  path: /api/v2/buckets
- description: Delete a bucket
  method: DELETE
  name: deletebucketsid
  path: /api/v2/buckets/{bucketID}
- description: Retrieve a bucket
  method: GET
  name: getbucketsid
  path: /api/v2/buckets/{bucketID}
- description: Update a bucket
  method: PATCH
  name: patchbucketsid
  path: /api/v2/buckets/{bucketID}
- description: List all labels for a bucket
  method: GET
  name: getbucketsidlabels
  path: /api/v2/buckets/{bucketID}/labels
- description: Add a label to a bucket
  method: POST
  name: postbucketsidlabels
  path: /api/v2/buckets/{bucketID}/labels
- description: Delete a label from a bucket
  method: DELETE
  name: deletebucketsidlabelsid
  path: /api/v2/buckets/{bucketID}/labels/{labelID}
- description: List all users with member privileges for a bucket
  method: GET
  name: getbucketsidmembers
  path: /api/v2/buckets/{bucketID}/members
- description: Add a member to a bucket
  method: POST
  name: postbucketsidmembers
  path: /api/v2/buckets/{bucketID}/members
- description: Remove a member from a bucket
  method: DELETE
  name: deletebucketsidmembersid
  path: /api/v2/buckets/{bucketID}/members/{userID}
- description: List all owners of a bucket
  method: GET
  name: getbucketsidowners
  path: /api/v2/buckets/{bucketID}/owners
- description: Add an owner to a bucket
  method: POST
  name: postbucketsidowners
  path: /api/v2/buckets/{bucketID}/owners
- description: Remove an owner from a bucket
  method: DELETE
  name: deletebucketsidownersid
  path: /api/v2/buckets/{bucketID}/owners/{userID}
- description: List measurement schemas of a bucket
  method: GET
  name: getmeasurementschemas
  path: /api/v2/buckets/{bucketID}/schema/measurements
- description: Create a measurement schema for a bucket
  method: POST
  name: createmeasurementschema
  path: /api/v2/buckets/{bucketID}/schema/measurements
- description: Retrieve a measurement schema
  method: GET
  name: getmeasurementschema
  path: /api/v2/buckets/{bucketID}/schema/measurements/{measurementID}
- description: Update a measurement schema
  method: PATCH
  name: updatemeasurementschema
  path: /api/v2/buckets/{bucketID}/schema/measurements/{measurementID}
- description: List all checks
  method: GET
  name: getchecks
  path: /api/v2/checks
- description: Add new check
  method: POST
  name: createcheck
  path: /api/v2/checks
- description: Delete a check
  method: DELETE
  name: deletechecksid
  path: /api/v2/checks/{checkID}
- description: Retrieve a check
  method: GET
  name: getchecksid
  path: /api/v2/checks/{checkID}
- description: Update a check
  method: PATCH
  name: patchchecksid
  path: /api/v2/checks/{checkID}
- description: Update a check
  method: PUT
  name: putchecksid
  path: /api/v2/checks/{checkID}
- description: List all labels for a check
  method: GET
  name: getchecksidlabels
  path: /api/v2/checks/{checkID}/labels
- description: Add a label to a check
  method: POST
  name: postchecksidlabels
  path: /api/v2/checks/{checkID}/labels
- description: Delete label from a check
  method: DELETE
  name: deletechecksidlabelsid
  path: /api/v2/checks/{checkID}/labels/{labelID}
- description: Retrieve a check query
  method: GET
  name: getchecksidquery
  path: /api/v2/checks/{checkID}/query
- description: List dashboards
  method: GET
  name: getdashboards
  path: /api/v2/dashboards
- description: Create a dashboard
  method: POST
  name: postdashboards
  path: /api/v2/dashboards
- description: Delete a dashboard
  method: DELETE
  name: deletedashboardsid
  path: /api/v2/dashboards/{dashboardID}
- description: Retrieve a dashboard
  method: GET
  name: getdashboardsid
  path: /api/v2/dashboards/{dashboardID}
- description: Update a dashboard
  method: PATCH
  name: patchdashboardsid
  path: /api/v2/dashboards/{dashboardID}
- description: Create a dashboard cell
  method: POST
  name: postdashboardsidcells
  path: /api/v2/dashboards/{dashboardID}/cells
- description: Replace cells in a dashboard
  method: PUT
  name: putdashboardsidcells
  path: /api/v2/dashboards/{dashboardID}/cells
- description: Delete a dashboard cell
  method: DELETE
  name: deletedashboardsidcellsid
  path: /api/v2/dashboards/{dashboardID}/cells/{cellID}
- description: Update the non-positional information related to a cell
  method: PATCH
  name: patchdashboardsidcellsid
  path: /api/v2/dashboards/{dashboardID}/cells/{cellID}
- description: Retrieve the view for a cell
  method: GET
  name: getdashboardsidcellsidview
  path: /api/v2/dashboards/{dashboardID}/cells/{cellID}/view
- description: Update the view for a cell
  method: PATCH
  name: patchdashboardsidcellsidview
  path: /api/v2/dashboards/{dashboardID}/cells/{cellID}/view
- description: List all labels for a dashboard
  method: GET
  name: getdashboardsidlabels
  path: /api/v2/dashboards/{dashboardID}/labels
- description: Add a label to a dashboard
  method: POST
  name: postdashboardsidlabels
  path: /api/v2/dashboards/{dashboardID}/labels
- description: Delete a label from a dashboard
  method: DELETE
  name: deletedashboardsidlabelsid
  path: /api/v2/dashboards/{dashboardID}/labels/{labelID}
- description: List all dashboard members
  method: GET
  name: getdashboardsidmembers
  path: /api/v2/dashboards/{dashboardID}/members
- description: Add a member to a dashboard
  method: POST
  name: postdashboardsidmembers
  path: /api/v2/dashboards/{dashboardID}/members
- description: Remove a member from a dashboard
  method: DELETE
  name: deletedashboardsidmembersid
  path: /api/v2/dashboards/{dashboardID}/members/{userID}
- description: List all dashboard owners
  method: GET
  name: getdashboardsidowners
  path: /api/v2/dashboards/{dashboardID}/owners
- description: Add an owner to a dashboard
  method: POST
  name: postdashboardsidowners
  path: /api/v2/dashboards/{dashboardID}/owners
- description: Remove an owner from a dashboard
  method: DELETE
  name: deletedashboardsidownersid
  path: /api/v2/dashboards/{dashboardID}/owners/{userID}
- description: List database retention policy mappings
  method: GET
  name: getdbrps
  path: /api/v2/dbrps
- description: Add a database retention policy mapping
  method: POST
  name: postdbrp
  path: /api/v2/dbrps
- description: Delete a database retention policy
  method: DELETE
  name: deletedbrpid
  path: /api/v2/dbrps/{dbrpID}
- description: Retrieve a database retention policy mapping
  method: GET
  name: getdbrpsid
  path: /api/v2/dbrps/{dbrpID}
- description: Update a database retention policy mapping
  method: PATCH
  name: patchdbrpid
  path: /api/v2/dbrps/{dbrpID}
- description: Delete data
  method: POST
  name: postdelete
  path: /api/v2/delete
personas: []
provider_name: InfluxDB
provider_slug: influxdb
search_terms:
- createcheck
- delete a label from a bucket
- updatemeasurementschema
- api
- add a member to a bucket
- list all labels for a check
- add a member to a dashboard
- delete a bucket
- deletedashboardsidlabelsid
- create an authorization
- getdashboardsidlabels
- update a bucket
- getbucketsid
- postdbrp
- deletedashboardsidownersid
- postauthorizations
- create a measurement schema for a bucket
- getdashboardsidcellsidview
- retrieve a measurement schema
- deletechecksidlabelsid
- deletedashboardsidmembersid
- postdelete
- putchecksid
- patchdashboardsidcellsid
- list authorizations
- retrieve a check
- patchdashboardsidcellsidview
- patchbucketsid
- patchdbrpid
- createmeasurementschema
- deletedashboardsidcellsid
- deletebucketsidlabelsid
- getchecksidquery
- retrieve a bucket
- remove an owner from a dashboard
- retrieve a check query
- postbuckets
- retrieve a dashboard
- getchecksidlabels
- postdashboards
- postdashboardsidcells
- getbucketsidmembers
- influxdb
- delete a database retention policy
- postbucketsidmembers
- postdashboardsidlabels
- patchauthorizationsid
- delete a dashboard cell
- add an owner to a dashboard
- add an owner to a bucket
- postchecksidlabels
- deletebucketsid
- real-time
- getmeasurementschema
- deletedbrpid
- getmeasurementschemas
- patchchecksid
- update the view for a cell
- putdashboardsidcells
- list measurement schemas of a bucket
- update a check
- list database retention policy mappings
- add a database retention policy mapping
- update a dashboard
- delete a check
- retrieve an authorization
- getdashboardsid
- getdbrps
- remove an owner from a bucket
- list all users with member privileges for a bucket
- update an api token to be active or inactive
- list all dashboard owners
- getbucketsidlabels
- list all checks
- update a database retention policy mapping
- replace cells in a dashboard
- getbucketsidowners
- getdashboards
- deleteauthorizationsid
- database
- create a dashboard cell
- getdbrpsid
- deletebucketsidownersid
- create a dashboard
- getchecksid
- list all top level routes
- analytics
- postbucketsidowners
- list buckets
- add a label to a dashboard
- deletedashboardsid
- deletebucketsidmembersid
- retrieve the view for a cell
- add new check
- delete a label from a dashboard
- getchecks
- patchdashboardsid
- retrieve a database retention policy mapping
- getbuckets
- update the non-positional information related to a cell
- postbucketsidlabels
- delete a dashboard
- postdashboardsidmembers
- delete label from a check
- remove a member from a dashboard
- list all labels for a dashboard
- getdashboardsidmembers
- getauthorizationsid
- deletechecksid
- list all labels for a bucket
- add a label to a bucket
- list all owners of a bucket
- getdashboardsidowners
- create a bucket
- getauthorizations
- remove a member from a bucket
- delete an authorization
- add a label to a check
- list dashboards
- postdashboardsidowners
- getroutes
- update a measurement schema
- list all dashboard members
- delete data
- time series
slug: influxdb-capability
source_filename: influxdb-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Complete InfluxDB Cloud API\n  description: Complete InfluxDB Cloud API API capability.\n  tags:\n  - Influxdb\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: influxdb\n    baseUri: ''\n    description: Complete InfluxDB Cloud API HTTP API.\n    authentication:\n      type: basic\n      username: '{{INFLUXDB_USERNAME}}'\n      password: '{{INFLUXDB_PASSWORD}}'\n    resources:\n    - name: api-v2\n      path: /api/v2\n      operations:\n      - name: getroutes\n        method: GET\n        description: List all top level routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-authorizations\n      path: /api/v2/authorizations\n      operations:\n      - name: getauthorizations\n        method: GET\n        description: List authorizations\n        inputParameters:\n     \
  \   - name: userID\n          in: query\n          type: string\n          description: A user ID. Only returns authorizations scoped to the specified [user](https://docs.influxdata.com/influxdb/cloud/reference/glossary/#user).\n        - name: user\n          in: query\n          type: string\n          description: A user name. Only returns authorizations scoped to the specified [user](https://docs.influxdata.com/influxdb/cloud/reference/glossary/#user).\n        - name: orgID\n          in: query\n          type: string\n          description: An organization ID. Only returns authorizations that belong to the specified [organization](https://docs.influxdata.com/influxdb/cloud/reference/glossary/#organ\n        - name: org\n          in: query\n          type: string\n          description: An organization name. Only returns authorizations that belong to the specified [organization](https://docs.influxdata.com/influxdb/cloud/reference/glossary/#org\n        - name: token\n          in:\
  \ query\n          type: string\n          description: An API [token](https://docs.influxdata.com/influxdb/cloud/reference/glossary/#token) value. Specifies\n            an authorization by its `token` property value and returns\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postauthorizations\n        method: POST\n        description: Create an authorization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-authorizations-authid\n      path: /api/v2/authorizations/{authID}\n      operations:\n      - name: deleteauthorizationsid\n        method: DELETE\n        description: Delete an authorization\n        inputParameters:\n        - name: authID\n          in: path\n          type: string\n          required: true\n          description: An authorization ID. Specifies the authorization to delete.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getauthorizationsid\n        method: GET\n        description: Retrieve an authorization\n        inputParameters:\n        - name: authID\n          in: path\n          type: string\n          required: true\n          description: An authorization ID. Specifies the authorization to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchauthorizationsid\n        method: PATCH\n        description: Update an API token to be active or inactive\n        inputParameters:\n        - name: authID\n          in: path\n          type: string\n          required: true\n          description: An authorization ID. Specifies the authorization to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: api-v2-buckets\n      path: /api/v2/buckets\n      operations:\n      - name: getbuckets\n        method: GET\n        description: List buckets\n        inputParameters:\n        - name: org\n          in: query\n          type: string\n          description: 'An organization name. #### InfluxDB Cloud - Doesn''t use the `org` parameter or `orgID` parameter.\n            - Lists buckets for the organization associated with the autho'\n        - name: orgID\n          in: query\n          type: string\n          description: 'An organization ID. #### InfluxDB Cloud - Doesn''t use the `org` parameter or `orgID` parameter. -\n            Lists buckets for the organization associated with the authori'\n        - name: name\n          in: query\n          type: string\n          description: A bucket name. Only returns buckets with the specified name.\n        - name: id\n          in: query\n          type: string\n          description: A bucket ID. Only\
  \ returns the bucket with the specified ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postbuckets\n        method: POST\n        description: Create a bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-buckets-bucketid\n      path: /api/v2/buckets/{bucketID}\n      operations:\n      - name: deletebucketsid\n        method: DELETE\n        description: Delete a bucket\n        inputParameters:\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: Bucket ID. The ID of the bucket to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getbucketsid\n        method: GET\n        description: Retrieve a bucket\n        inputParameters:\n\
  \        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: The ID of the bucket to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchbucketsid\n        method: PATCH\n        description: Update a bucket\n        inputParameters:\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: The bucket ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-buckets-bucketid-labels\n      path: /api/v2/buckets/{bucketID}/labels\n      operations:\n      - name: getbucketsidlabels\n        method: GET\n        description: List all labels for a bucket\n        inputParameters:\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n\
  \          description: The ID of the bucket to retrieve labels for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postbucketsidlabels\n        method: POST\n        description: Add a label to a bucket\n        inputParameters:\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: Bucket ID. The ID of the bucket to label.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-buckets-bucketid-labels-labelid\n      path: /api/v2/buckets/{bucketID}/labels/{labelID}\n      operations:\n      - name: deletebucketsidlabelsid\n        method: DELETE\n        description: Delete a label from a bucket\n        inputParameters:\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description:\
  \ The bucket ID.\n        - name: labelID\n          in: path\n          type: string\n          required: true\n          description: The ID of the label to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-buckets-bucketid-members\n      path: /api/v2/buckets/{bucketID}/members\n      operations:\n      - name: getbucketsidmembers\n        method: GET\n        description: List all users with member privileges for a bucket\n        inputParameters:\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: The ID of the bucket to retrieve users for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postbucketsidmembers\n        method: POST\n        description: Add a member to a bucket\n        inputParameters:\n        - name:\
  \ bucketID\n          in: path\n          type: string\n          required: true\n          description: The ID of the bucket to retrieve users for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-buckets-bucketid-members-userid\n      path: /api/v2/buckets/{bucketID}/members/{userID}\n      operations:\n      - name: deletebucketsidmembersid\n        method: DELETE\n        description: Remove a member from a bucket\n        inputParameters:\n        - name: userID\n          in: path\n          type: string\n          required: true\n          description: The ID of the user to remove.\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: The ID of the bucket to remove a user from.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-buckets-bucketid-owners\n\
  \      path: /api/v2/buckets/{bucketID}/owners\n      operations:\n      - name: getbucketsidowners\n        method: GET\n        description: List all owners of a bucket\n        inputParameters:\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: The ID of the bucket to retrieve owners for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postbucketsidowners\n        method: POST\n        description: Add an owner to a bucket\n        inputParameters:\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: The ID of the bucket to add an owner for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-buckets-bucketid-owners-userid\n      path: /api/v2/buckets/{bucketID}/owners/{userID}\n\
  \      operations:\n      - name: deletebucketsidownersid\n        method: DELETE\n        description: Remove an owner from a bucket\n        inputParameters:\n        - name: userID\n          in: path\n          type: string\n          required: true\n          description: The ID of the owner to remove.\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: The ID of the bucket to remove an owner from.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-buckets-bucketid-schema-measurements\n      path: /api/v2/buckets/{bucketID}/schema/measurements\n      operations:\n      - name: getmeasurementschemas\n        method: GET\n        description: List measurement schemas of a bucket\n        inputParameters:\n        - name: org\n          in: query\n          type: string\n          description: An organization name. Specifies\
  \ the organization that owns the schema.\n        - name: orgID\n          in: query\n          type: string\n          description: An organization ID. Specifies the organization that owns the schema.\n        - name: name\n          in: query\n          type: string\n          description: A measurement name. Only returns measurement schemas with the specified name.\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: A bucket ID. Lists measurement schemas for the specified bucket.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmeasurementschema\n        method: POST\n        description: Create a measurement schema for a bucket\n        inputParameters:\n        - name: org\n          in: query\n          type: string\n          description: An organization name. Specifies the organization that owns the schema.\n    \
  \    - name: orgID\n          in: query\n          type: string\n          description: An organization ID. Specifies the organization that owns the schema.\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: A bucket ID. Adds a schema for the specified bucket.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-buckets-bucketid-schema-measurements-meas\n      path: /api/v2/buckets/{bucketID}/schema/measurements/{measurementID}\n      operations:\n      - name: getmeasurementschema\n        method: GET\n        description: Retrieve a measurement schema\n        inputParameters:\n        - name: org\n          in: query\n          type: string\n          description: Organization name. Specifies the organization that owns the schema.\n        - name: orgID\n          in: query\n          type: string\n          description: Organization\
  \ ID. Specifies the organization that owns the schema.\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: A bucket ID. Retrieves schemas for the specified bucket.\n        - name: measurementID\n          in: path\n          type: string\n          required: true\n          description: The measurement schema ID. Specifies the measurement schema to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemeasurementschema\n        method: PATCH\n        description: Update a measurement schema\n        inputParameters:\n        - name: org\n          in: query\n          type: string\n          description: An organization name. Specifies the organization that owns the schema.\n        - name: orgID\n          in: query\n          type: string\n          description: An organization ID. Specifies the organization that\
  \ owns the schema.\n        - name: bucketID\n          in: path\n          type: string\n          required: true\n          description: A bucket ID. Specifies the bucket to retrieve schemas for.\n        - name: measurementID\n          in: path\n          type: string\n          required: true\n          description: A measurement schema ID. Retrieves the specified measurement schema.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-checks\n      path: /api/v2/checks\n      operations:\n      - name: getchecks\n        method: GET\n        description: List all checks\n        inputParameters:\n        - name: orgID\n          in: query\n          type: string\n          required: true\n          description: Only show checks that belong to a specific organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: createcheck\n        method: POST\n        description: Add new check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-checks-checkid\n      path: /api/v2/checks/{checkID}\n      operations:\n      - name: deletechecksid\n        method: DELETE\n        description: Delete a check\n        inputParameters:\n        - name: checkID\n          in: path\n          type: string\n          required: true\n          description: The check ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getchecksid\n        method: GET\n        description: Retrieve a check\n        inputParameters:\n        - name: checkID\n          in: path\n          type: string\n          required: true\n          description: The check ID.\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: patchchecksid\n        method: PATCH\n        description: Update a check\n        inputParameters:\n        - name: checkID\n          in: path\n          type: string\n          required: true\n          description: The check ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putchecksid\n        method: PUT\n        description: Update a check\n        inputParameters:\n        - name: checkID\n          in: path\n          type: string\n          required: true\n          description: The check ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-checks-checkid-labels\n      path: /api/v2/checks/{checkID}/labels\n      operations:\n      - name: getchecksidlabels\n        method: GET\n        description: List all labels\
  \ for a check\n        inputParameters:\n        - name: checkID\n          in: path\n          type: string\n          required: true\n          description: The check ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postchecksidlabels\n        method: POST\n        description: Add a label to a check\n        inputParameters:\n        - name: checkID\n          in: path\n          type: string\n          required: true\n          description: The check ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-checks-checkid-labels-labelid\n      path: /api/v2/checks/{checkID}/labels/{labelID}\n      operations:\n      - name: deletechecksidlabelsid\n        method: DELETE\n        description: Delete label from a check\n        inputParameters:\n        - name: checkID\n          in: path\n      \
  \    type: string\n          required: true\n          description: The check ID.\n        - name: labelID\n          in: path\n          type: string\n          required: true\n          description: The ID of the label to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-checks-checkid-query\n      path: /api/v2/checks/{checkID}/query\n      operations:\n      - name: getchecksidquery\n        method: GET\n        description: Retrieve a check query\n        inputParameters:\n        - name: checkID\n          in: path\n          type: string\n          required: true\n          description: The check ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-dashboards\n      path: /api/v2/dashboards\n      operations:\n      - name: getdashboards\n        method: GET\n        description:\
  \ List dashboards\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description: The maximum number of [dashboards](https://docs.influxdata.com/influxdb/cloud/reference/glossary/#dashboard)\n            to return. Default is `20`. The minimum is `-1` and\n        - name: owner\n          in: query\n          type: string\n          description: A user ID. Only returns [dashboards](https://docs.influxdata.com/influxdb/cloud/reference/glossary/#dashboard)\n            where the specified user has the `owner` role.\n        - name: sortBy\n          in: query\n          type: string\n          description: The column to sort by.\n        - name: id\n          in: query\n          type: array\n          description: 'A list of dashboard IDs. Returns only the specified [dashboards](https://docs.influxdata.com/influxdb/cloud/reference/glossary/#dashboard).\n            If you specify `id` '\n        - name: orgID\n          in: query\n\
  \          type: string\n          description: An organization ID. Only returns [dashboards](https://docs.influxdata.com/influxdb/cloud/reference/glossary/#dashboard)\n            that belong to the specified [organizati\n        - name: org\n          in: query\n          type: string\n          description: An organization name. Only returns [dashboards](https://docs.influxdata.com/influxdb/cloud/reference/glossary/#dashboard)\n            that belong to the specified [organiza\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postdashboards\n        method: POST\n        description: Create a dashboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-dashboards-dashboardid\n      path: /api/v2/dashboards/{dashboardID}\n      operations:\n      - name: deletedashboardsid\n        method: DELETE\n\
  \        description: Delete a dashboard\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The ID of the dashboard to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdashboardsid\n        method: GET\n        description: Retrieve a dashboard\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The ID of the dashboard to update.\n        - name: include\n          in: query\n          type: string\n          description: If `properties`, includes the cell view properties in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchdashboardsid\n        method: PATCH\n        description: Update\
  \ a dashboard\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The ID of the dashboard to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-dashboards-dashboardid-cells\n      path: /api/v2/dashboards/{dashboardID}/cells\n      operations:\n      - name: postdashboardsidcells\n        method: POST\n        description: Create a dashboard cell\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The ID of the dashboard to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putdashboardsidcells\n        method: PUT\n        description: Replace cells in a dashboard\n        inputParameters:\n   \
  \     - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The ID of the dashboard to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-dashboards-dashboardid-cells-cellid\n      path: /api/v2/dashboards/{dashboardID}/cells/{cellID}\n      operations:\n      - name: deletedashboardsidcellsid\n        method: DELETE\n        description: Delete a dashboard cell\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The ID of the dashboard to delete.\n        - name: cellID\n          in: path\n          type: string\n          required: true\n          description: The ID of the cell to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ patchdashboardsidcellsid\n        method: PATCH\n        description: Update the non-positional information related to a cell\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The ID of the dashboard to update.\n        - name: cellID\n          in: path\n          type: string\n          required: true\n          description: The ID of the cell to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-dashboards-dashboardid-cells-cellid-view\n      path: /api/v2/dashboards/{dashboardID}/cells/{cellID}/view\n      operations:\n      - name: getdashboardsidcellsidview\n        method: GET\n        description: Retrieve the view for a cell\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The\
  \ dashboard ID.\n        - name: cellID\n          in: path\n          type: string\n          required: true\n          description: The cell ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchdashboardsidcellsidview\n        method: PATCH\n        description: Update the view for a cell\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The ID of the dashboard to update.\n        - name: cellID\n          in: path\n          type: string\n          required: true\n          description: The ID of the cell to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-dashboards-dashboardid-labels\n      path: /api/v2/dashboards/{dashboardID}/labels\n      operations:\n      - name: getdashboardsidlabels\n\
  \        method: GET\n        description: List all labels for a dashboard\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The dashboard ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postdashboardsidlabels\n        method: POST\n        description: Add a label to a dashboard\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The dashboard ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-dashboards-dashboardid-labels-labelid\n      path: /api/v2/dashboards/{dashboardID}/labels/{labelID}\n      operations:\n      - name: deletedashboardsidlabelsid\n        method: DELETE\n        description:\
  \ Delete a label from a dashboard\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The dashboard ID.\n        - name: labelID\n          in: path\n          type: string\n          required: true\n          description: The ID of the label to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-dashboards-dashboardid-members\n      path: /api/v2/dashboards/{dashboardID}/members\n      operations:\n      - name: getdashboardsidmembers\n        method: GET\n        description: List all dashboard members\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The dashboard ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: postdashboardsidmembers\n        method: POST\n        description: Add a member to a dashboard\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The dashboard ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-dashboards-dashboardid-members-userid\n      path: /api/v2/dashboards/{dashboardID}/members/{userID}\n      operations:\n      - name: deletedashboardsidmembersid\n        method: DELETE\n        description: Remove a member from a dashboard\n        inputParameters:\n        - name: userID\n          in: path\n          type: string\n          required: true\n          description: The ID of the member to remove.\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The dashboard ID.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-dashboards-dashboardid-owners\n      path: /api/v2/dashboards/{dashboardID}/owners\n      operations:\n      - name: getdashboardsidowners\n        method: GET\n        description: List all dashboard owners\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The dashboard ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postdashboardsidowners\n        method: POST\n        description: Add an owner to a dashboard\n        inputParameters:\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The dashboard ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: api-v2-dashboards-dashboardid-owners-userid\n      path: /api/v2/dashboards/{dashboardID}/owners/{userID}\n      operations:\n      - name: deletedashboardsidownersid\n        method: DELETE\n        description: Remove an owner from a dashboard\n        inputParameters:\n        - name: userID\n          in: path\n          type: string\n          required: true\n          description: The ID of the owner to remove.\n        - name: dashboardID\n          in: path\n          type: string\n          required: true\n          description: The dashboard ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-dbrps\n      path: /api/v2/dbrps\n      operations:\n      - name: getdbrps\n        method: GET\n        description: List database retention policy mappings\n        inputParameters:\n        - name: orgID\n          in: query\n          type: string\n\
  \          description: An organization ID. Only returns DBRP mappings for the specified organization.\n        - name: org\n          in: query\n          type: string\n          description: An organization name. Only returns DBRP mappings for the specified organization.\n        - name: id\n          in: query\n          type: string\n          description: A DBPR mapping ID. Only returns the specified DBRP mapping.\n        - name: bucketID\n          in: query\n          type: string\n          description: A bucket ID. Only returns DBRP mappings that belong to the specified bucket.\n        - name: default\n          in: query\n          type: boolean\n          description: Specifies filtering on default\n        - name: db\n          in: query\n          type: string\n          description: A database. Only returns DBRP mappings that belong to the 1.x database.\n        - name: rp\n          in: query\n          type: string\n          description: A [retention policy](https://docs.influxdata.com/influxdb/v1.8/concepts/glossary/#retention-policy-rp).\n\
  \            Specifies the 1.x retention policy to filter on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: postdbrp\n        method: POST\n        description: Add a database retention policy mapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-dbrps-dbrpid\n      path: /api/v2/dbrps/{dbrpID}\n      operations:\n      - name: deletedbrpid\n        method: DELETE\n        description: Delete a database retention policy\n        inputParameters:\n        - name: orgID\n        \n\n# --- truncated at 32 KB (91 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/influxdb/refs/heads/main/capabilities/influxdb-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/influxdb/refs/heads/main/capabilities/influxdb-capability.yaml
tags:
- Influxdb
- API
tools:
- description: List all top level routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroutes
- description: List authorizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthorizations
- description: Create an authorization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postauthorizations
- description: Delete an authorization
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteauthorizationsid
- description: Retrieve an authorization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthorizationsid
- description: Update an API token to be active or inactive
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchauthorizationsid
- description: List buckets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbuckets
- description: Create a bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postbuckets
- description: Delete a bucket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketsid
- description: Retrieve a bucket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketsid
- description: Update a bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchbucketsid
- description: List all labels for a bucket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketsidlabels
- description: Add a label to a bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postbucketsidlabels
- description: Delete a label from a bucket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketsidlabelsid
- description: List all users with member privileges for a bucket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketsidmembers
- description: Add a member to a bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postbucketsidmembers
- description: Remove a member from a bucket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketsidmembersid
- description: List all owners of a bucket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucketsidowners
- description: Add an owner to a bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postbucketsidowners
- description: Remove an owner from a bucket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucketsidownersid
- description: List measurement schemas of a bucket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeasurementschemas
- description: Create a measurement schema for a bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmeasurementschema
- description: Retrieve a measurement schema
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeasurementschema
- description: Update a measurement schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatemeasurementschema
- description: List all checks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchecks
- description: Add new check
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcheck
- description: Delete a check
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletechecksid
- description: Retrieve a check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchecksid
- description: Update a check
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchchecksid
- description: Update a check
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putchecksid
- description: List all labels for a check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchecksidlabels
- description: Add a label to a check
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postchecksidlabels
- description: Delete label from a check
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletechecksidlabelsid
- description: Retrieve a check query
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchecksidquery
- description: List dashboards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboards
- description: Create a dashboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postdashboards
- description: Delete a dashboard
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedashboardsid
- description: Retrieve a dashboard
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboardsid
- description: Update a dashboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchdashboardsid
- description: Create a dashboard cell
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postdashboardsidcells
- description: Replace cells in a dashboard
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putdashboardsidcells
- description: Delete a dashboard cell
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedashboardsidcellsid
- description: Update the non-positional information related to a cell
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchdashboardsidcellsid
- description: Retrieve the view for a cell
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboardsidcellsidview
- description: Update the view for a cell
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchdashboardsidcellsidview
- description: List all labels for a dashboard
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboardsidlabels
- description: Add a label to a dashboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postdashboardsidlabels
- description: Delete a label from a dashboard
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedashboardsidlabelsid
- description: List all dashboard members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboardsidmembers
- description: Add a member to a dashboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postdashboardsidmembers
- description: Remove a member from a dashboard
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedashboardsidmembersid
- description: List all dashboard owners
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboardsidowners
- description: Add an owner to a dashboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postdashboardsidowners
- description: Remove an owner from a dashboard
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedashboardsidownersid
- description: List database retention policy mappings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdbrps
- description: Add a database retention policy mapping
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postdbrp
- description: Delete a database retention policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedbrpid
- description: Retrieve a database retention policy mapping
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdbrpsid
- description: Update a database retention policy mapping
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchdbrpid
- description: Delete data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postdelete
---
