---
categories: []
consumed_apis: []
description: REST APIs for Oracle Fusion Cloud Applications Common features, providing access to shared services such as attachments, flexfields, lookup types, roles, users, security, scheduled processes, announcements, and approval workflows used across all Fusion Cloud application pillars.
layout: capability
name: Oracle Fusion Cloud Applications Oracle Fusion Common Features REST API
operations:
- description: Oracle Fusion Cloud Applications List common lookups
  method: GET
  name: listcommonlookups
  path: /fscmRestApi/resources/11.13.18.05/commonLookups
- description: Oracle Fusion Cloud Applications Create a common lookup
  method: POST
  name: createcommonlookup
  path: /fscmRestApi/resources/11.13.18.05/commonLookups
- description: Oracle Fusion Cloud Applications Get a common lookup
  method: GET
  name: getcommonlookup
  path: /fscmRestApi/resources/11.13.18.05/commonLookups/{LookupType}
- description: Oracle Fusion Cloud Applications Update a common lookup
  method: PATCH
  name: updatecommonlookup
  path: /fscmRestApi/resources/11.13.18.05/commonLookups/{LookupType}
- description: Oracle Fusion Cloud Applications Delete a common lookup
  method: DELETE
  name: deletecommonlookup
  path: /fscmRestApi/resources/11.13.18.05/commonLookups/{LookupType}
- description: Oracle Fusion Cloud Applications List lookup codes for a lookup type
  method: GET
  name: listlookupcodes
  path: /fscmRestApi/resources/11.13.18.05/commonLookups/{LookupType}/child/lookupCodes
- description: Oracle Fusion Cloud Applications Create a lookup code
  method: POST
  name: createlookupcode
  path: /fscmRestApi/resources/11.13.18.05/commonLookups/{LookupType}/child/lookupCodes
- description: Oracle Fusion Cloud Applications List announcements
  method: GET
  name: listannouncements
  path: /fscmRestApi/resources/11.13.18.05/announcements
- description: Oracle Fusion Cloud Applications Create an announcement
  method: POST
  name: createannouncement
  path: /fscmRestApi/resources/11.13.18.05/announcements
- description: Oracle Fusion Cloud Applications Get an announcement
  method: GET
  name: getannouncement
  path: /fscmRestApi/resources/11.13.18.05/announcements/{AnnouncementId}
- description: Oracle Fusion Cloud Applications Update an announcement
  method: PATCH
  name: updateannouncement
  path: /fscmRestApi/resources/11.13.18.05/announcements/{AnnouncementId}
- description: Oracle Fusion Cloud Applications Delete an announcement
  method: DELETE
  name: deleteannouncement
  path: /fscmRestApi/resources/11.13.18.05/announcements/{AnnouncementId}
- description: Oracle Fusion Cloud Applications List persons
  method: GET
  name: listpersons
  path: /fscmRestApi/resources/11.13.18.05/persons
- description: Oracle Fusion Cloud Applications Create a person
  method: POST
  name: createperson
  path: /fscmRestApi/resources/11.13.18.05/persons
- description: Oracle Fusion Cloud Applications Get a person
  method: GET
  name: getperson
  path: /fscmRestApi/resources/11.13.18.05/persons/{Personid}
- description: Oracle Fusion Cloud Applications Update a person
  method: PATCH
  name: updateperson
  path: /fscmRestApi/resources/11.13.18.05/persons/{Personid}
- description: Oracle Fusion Cloud Applications Delete a person
  method: DELETE
  name: deleteperson
  path: /fscmRestApi/resources/11.13.18.05/persons/{Personid}
- description: Oracle Fusion Cloud Applications List roles
  method: GET
  name: listroles
  path: /hcmRestApi/scim/Roles
- description: Oracle Fusion Cloud Applications Get a role
  method: GET
  name: getrole
  path: /hcmRestApi/scim/Roles/{id}
- description: Oracle Fusion Cloud Applications Update a role
  method: PATCH
  name: updaterole
  path: /hcmRestApi/scim/Roles/{id}
- description: Oracle Fusion Cloud Applications List scheduled process requests
  method: GET
  name: listscheduledrequests
  path: /ess/rest/scheduler/v1/requests
- description: Oracle Fusion Cloud Applications Submit a scheduled process request
  method: POST
  name: submitscheduledrequest
  path: /ess/rest/scheduler/v1/requests
- description: Oracle Fusion Cloud Applications Get a scheduled process request
  method: GET
  name: getscheduledrequest
  path: /ess/rest/scheduler/v1/requests/{requestId}
- description: Oracle Fusion Cloud Applications List workflow tasks
  method: GET
  name: listworkflowtasks
  path: /bpm/api/4.0/tasks
- description: Oracle Fusion Cloud Applications Get a workflow task
  method: GET
  name: getworkflowtask
  path: /bpm/api/4.0/tasks/{id}
- description: Oracle Fusion Cloud Applications Perform a task action
  method: PUT
  name: performtaskaction
  path: /bpm/api/4.0/tasks/{id}
- description: Oracle Fusion Cloud Applications List features
  method: GET
  name: listfeatures
  path: /fscmRestApi/resources/11.13.18.05/features
- description: Oracle Fusion Cloud Applications Get audit history
  method: GET
  name: getaudithistory
  path: /fscmRestApi/fndAuditRESTService/audittrail/getaudithistory
personas: []
provider_name: Oracle Fusion Cloud Applications
provider_slug: oracle-fusion
search_terms:
- getcommonlookup
- oracle fusion cloud applications get an announcement
- performtaskaction
- oracle fusion cloud applications submit a scheduled process request
- oracle fusion cloud applications get audit history
- oracle fusion cloud applications create a lookup code
- rest api
- oracle fusion cloud applications create a person
- oracle fusion cloud applications update a person
- deleteperson
- oracle fusion cloud applications update an announcement
- epm
- updateperson
- createcommonlookup
- getrole
- oracle fusion cloud applications create an announcement
- listpersons
- createlookupcode
- listfeatures
- cx
- updatecommonlookup
- listannouncements
- oracle fusion cloud applications list features
- scm
- oracle fusion cloud applications delete a common lookup
- oracle fusion cloud applications delete a person
- oracle fusion cloud applications update a role
- cloud
- deleteannouncement
- listcommonlookups
- oracle fusion cloud applications delete an announcement
- updaterole
- oracle fusion cloud applications get a workflow task
- oracle fusion cloud applications perform a task action
- getaudithistory
- oracle fusion cloud applications get a scheduled process request
- enterprise
- oracle fusion cloud applications get a common lookup
- oracle fusion cloud applications list workflow tasks
- project management
- submitscheduledrequest
- erp
- getannouncement
- listscheduledrequests
- listworkflowtasks
- oracle
- listroles
- listlookupcodes
- oracle fusion cloud applications list persons
- fusion
- oracle fusion cloud applications list lookup codes for a lookup type
- api
- oracle fusion cloud applications list common lookups
- getperson
- deletecommonlookup
- oracle fusion cloud applications list scheduled process requests
- hcm
- saas
- oracle fusion cloud applications update a common lookup
- getworkflowtask
- getscheduledrequest
- oracle fusion cloud applications get a person
- updateannouncement
- createperson
- oracle fusion cloud applications list announcements
- createannouncement
- oracle fusion cloud applications create a common lookup
- oracle fusion cloud applications get a role
- oracle fusion cloud applications list roles
slug: oracle-fusion-capability
source_filename: oracle-fusion-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Fusion Cloud Applications Oracle Fusion Common Features REST API\n  description: REST APIs for Oracle Fusion Cloud Applications Common features, providing access to shared services such as\n    attachments, flexfields, lookup types, roles, users, security, scheduled processes, announcements, and approval workflows\n    used across all Fusion Cloud application pillars.\n  tags:\n  - Oracle\n  - Fusion\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-fusion\n    baseUri: https://servername.oraclecloud.com\n    description: Oracle Fusion Cloud Applications Oracle Fusion Common Features REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ORACLE_FUSION_TOKEN}}'\n    resources:\n    - name: fscmrestapi-resources-11-13-18-05-commonlookups\n      path: /fscmRestApi/resources/11.13.18.05/commonLookups\n      operations:\n      - name: listcommonlookups\n\
  \        method: GET\n        description: Oracle Fusion Cloud Applications List common lookups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcommonlookup\n        method: POST\n        description: Oracle Fusion Cloud Applications Create a common lookup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-commonlookups-\n      path: /fscmRestApi/resources/11.13.18.05/commonLookups/{LookupType}\n      operations:\n      - name: getcommonlookup\n        method: GET\n        description: Oracle Fusion Cloud Applications Get a common lookup\n        inputParameters:\n        - name: LookupType\n          in: path\n          type: string\n          required: true\n          description: Lookup type identifier\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n      - name: updatecommonlookup\n        method: PATCH\n        description: Oracle Fusion Cloud Applications Update a common lookup\n        inputParameters:\n        - name: LookupType\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecommonlookup\n        method: DELETE\n        description: Oracle Fusion Cloud Applications Delete a common lookup\n        inputParameters:\n        - name: LookupType\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-commonlookups-\n      path: /fscmRestApi/resources/11.13.18.05/commonLookups/{LookupType}/child/lookupCodes\n   \
  \   operations:\n      - name: listlookupcodes\n        method: GET\n        description: Oracle Fusion Cloud Applications List lookup codes for a lookup type\n        inputParameters:\n        - name: LookupType\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlookupcode\n        method: POST\n        description: Oracle Fusion Cloud Applications Create a lookup code\n        inputParameters:\n        - name: LookupType\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-announcements\n      path: /fscmRestApi/resources/11.13.18.05/announcements\n      operations:\n      - name: listannouncements\n        method: GET\n        description:\
  \ Oracle Fusion Cloud Applications List announcements\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createannouncement\n        method: POST\n        description: Oracle Fusion Cloud Applications Create an announcement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-announcements-\n      path: /fscmRestApi/resources/11.13.18.05/announcements/{AnnouncementId}\n      operations:\n      - name: getannouncement\n        method: GET\n        description: Oracle Fusion Cloud Applications Get an announcement\n        inputParameters:\n        - name: AnnouncementId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ updateannouncement\n        method: PATCH\n        description: Oracle Fusion Cloud Applications Update an announcement\n        inputParameters:\n        - name: AnnouncementId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteannouncement\n        method: DELETE\n        description: Oracle Fusion Cloud Applications Delete an announcement\n        inputParameters:\n        - name: AnnouncementId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-persons\n      path: /fscmRestApi/resources/11.13.18.05/persons\n      operations:\n      - name: listpersons\n        method: GET\n        description: Oracle Fusion Cloud Applications\
  \ List persons\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createperson\n        method: POST\n        description: Oracle Fusion Cloud Applications Create a person\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-persons-person\n      path: /fscmRestApi/resources/11.13.18.05/persons/{Personid}\n      operations:\n      - name: getperson\n        method: GET\n        description: Oracle Fusion Cloud Applications Get a person\n        inputParameters:\n        - name: Personid\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateperson\n        method: PATCH\n        description: Oracle Fusion Cloud Applications\
  \ Update a person\n        inputParameters:\n        - name: Personid\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteperson\n        method: DELETE\n        description: Oracle Fusion Cloud Applications Delete a person\n        inputParameters:\n        - name: Personid\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hcmrestapi-scim-roles\n      path: /hcmRestApi/scim/Roles\n      operations:\n      - name: listroles\n        method: GET\n        description: Oracle Fusion Cloud Applications List roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hcmrestapi-scim-roles-id\n\
  \      path: /hcmRestApi/scim/Roles/{id}\n      operations:\n      - name: getrole\n        method: GET\n        description: Oracle Fusion Cloud Applications Get a role\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterole\n        method: PATCH\n        description: Oracle Fusion Cloud Applications Update a role\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ess-rest-scheduler-v1-requests\n      path: /ess/rest/scheduler/v1/requests\n      operations:\n      - name: listscheduledrequests\n        method: GET\n        description: Oracle Fusion Cloud Applications List\
  \ scheduled process requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submitscheduledrequest\n        method: POST\n        description: Oracle Fusion Cloud Applications Submit a scheduled process request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ess-rest-scheduler-v1-requests-requestid\n      path: /ess/rest/scheduler/v1/requests/{requestId}\n      operations:\n      - name: getscheduledrequest\n        method: GET\n        description: Oracle Fusion Cloud Applications Get a scheduled process request\n        inputParameters:\n        - name: requestId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bpm-api-4-0-tasks\n      path:\
  \ /bpm/api/4.0/tasks\n      operations:\n      - name: listworkflowtasks\n        method: GET\n        description: Oracle Fusion Cloud Applications List workflow tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bpm-api-4-0-tasks-id\n      path: /bpm/api/4.0/tasks/{id}\n      operations:\n      - name: getworkflowtask\n        method: GET\n        description: Oracle Fusion Cloud Applications Get a workflow task\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: performtaskaction\n        method: PUT\n        description: Oracle Fusion Cloud Applications Perform a task action\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-resources-11-13-18-05-features\n      path: /fscmRestApi/resources/11.13.18.05/features\n      operations:\n      - name: listfeatures\n        method: GET\n        description: Oracle Fusion Cloud Applications List features\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fscmrestapi-fndauditrestservice-audittrail-getau\n      path: /fscmRestApi/fndAuditRESTService/audittrail/getaudithistory\n      operations:\n      - name: getaudithistory\n        method: GET\n        description: Oracle Fusion Cloud Applications Get audit history\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oracle-fusion-rest\n    description:\
  \ REST adapter for Oracle Fusion Cloud Applications Oracle Fusion Common Features REST API.\n    resources:\n    - path: /fscmRestApi/resources/11.13.18.05/commonLookups\n      name: listcommonlookups\n      operations:\n      - method: GET\n        name: listcommonlookups\n        description: Oracle Fusion Cloud Applications List common lookups\n        call: oracle-fusion.listcommonlookups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/commonLookups\n      name: createcommonlookup\n      operations:\n      - method: POST\n        name: createcommonlookup\n        description: Oracle Fusion Cloud Applications Create a common lookup\n        call: oracle-fusion.createcommonlookup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/commonLookups/{LookupType}\n      name: getcommonlookup\n      operations:\n      - method: GET\n        name: getcommonlookup\n\
  \        description: Oracle Fusion Cloud Applications Get a common lookup\n        call: oracle-fusion.getcommonlookup\n        with:\n          LookupType: rest.LookupType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/commonLookups/{LookupType}\n      name: updatecommonlookup\n      operations:\n      - method: PATCH\n        name: updatecommonlookup\n        description: Oracle Fusion Cloud Applications Update a common lookup\n        call: oracle-fusion.updatecommonlookup\n        with:\n          LookupType: rest.LookupType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/commonLookups/{LookupType}\n      name: deletecommonlookup\n      operations:\n      - method: DELETE\n        name: deletecommonlookup\n        description: Oracle Fusion Cloud Applications Delete a common lookup\n        call: oracle-fusion.deletecommonlookup\n   \
  \     with:\n          LookupType: rest.LookupType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/commonLookups/{LookupType}/child/lookupCodes\n      name: listlookupcodes\n      operations:\n      - method: GET\n        name: listlookupcodes\n        description: Oracle Fusion Cloud Applications List lookup codes for a lookup type\n        call: oracle-fusion.listlookupcodes\n        with:\n          LookupType: rest.LookupType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/commonLookups/{LookupType}/child/lookupCodes\n      name: createlookupcode\n      operations:\n      - method: POST\n        name: createlookupcode\n        description: Oracle Fusion Cloud Applications Create a lookup code\n        call: oracle-fusion.createlookupcode\n        with:\n          LookupType: rest.LookupType\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/announcements\n      name: listannouncements\n      operations:\n      - method: GET\n        name: listannouncements\n        description: Oracle Fusion Cloud Applications List announcements\n        call: oracle-fusion.listannouncements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/announcements\n      name: createannouncement\n      operations:\n      - method: POST\n        name: createannouncement\n        description: Oracle Fusion Cloud Applications Create an announcement\n        call: oracle-fusion.createannouncement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/announcements/{AnnouncementId}\n      name: getannouncement\n      operations:\n      - method: GET\n        name: getannouncement\n        description: Oracle Fusion Cloud Applications Get an announcement\n\
  \        call: oracle-fusion.getannouncement\n        with:\n          AnnouncementId: rest.AnnouncementId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/announcements/{AnnouncementId}\n      name: updateannouncement\n      operations:\n      - method: PATCH\n        name: updateannouncement\n        description: Oracle Fusion Cloud Applications Update an announcement\n        call: oracle-fusion.updateannouncement\n        with:\n          AnnouncementId: rest.AnnouncementId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/announcements/{AnnouncementId}\n      name: deleteannouncement\n      operations:\n      - method: DELETE\n        name: deleteannouncement\n        description: Oracle Fusion Cloud Applications Delete an announcement\n        call: oracle-fusion.deleteannouncement\n        with:\n          AnnouncementId: rest.AnnouncementId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/persons\n      name: listpersons\n      operations:\n      - method: GET\n        name: listpersons\n        description: Oracle Fusion Cloud Applications List persons\n        call: oracle-fusion.listpersons\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/persons\n      name: createperson\n      operations:\n      - method: POST\n        name: createperson\n        description: Oracle Fusion Cloud Applications Create a person\n        call: oracle-fusion.createperson\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/persons/{Personid}\n      name: getperson\n      operations:\n      - method: GET\n        name: getperson\n        description: Oracle Fusion Cloud Applications Get a person\n        call: oracle-fusion.getperson\n\
  \        with:\n          Personid: rest.Personid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/persons/{Personid}\n      name: updateperson\n      operations:\n      - method: PATCH\n        name: updateperson\n        description: Oracle Fusion Cloud Applications Update a person\n        call: oracle-fusion.updateperson\n        with:\n          Personid: rest.Personid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/persons/{Personid}\n      name: deleteperson\n      operations:\n      - method: DELETE\n        name: deleteperson\n        description: Oracle Fusion Cloud Applications Delete a person\n        call: oracle-fusion.deleteperson\n        with:\n          Personid: rest.Personid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hcmRestApi/scim/Roles\n      name: listroles\n      operations:\n\
  \      - method: GET\n        name: listroles\n        description: Oracle Fusion Cloud Applications List roles\n        call: oracle-fusion.listroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hcmRestApi/scim/Roles/{id}\n      name: getrole\n      operations:\n      - method: GET\n        name: getrole\n        description: Oracle Fusion Cloud Applications Get a role\n        call: oracle-fusion.getrole\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hcmRestApi/scim/Roles/{id}\n      name: updaterole\n      operations:\n      - method: PATCH\n        name: updaterole\n        description: Oracle Fusion Cloud Applications Update a role\n        call: oracle-fusion.updaterole\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ess/rest/scheduler/v1/requests\n      name: listscheduledrequests\n\
  \      operations:\n      - method: GET\n        name: listscheduledrequests\n        description: Oracle Fusion Cloud Applications List scheduled process requests\n        call: oracle-fusion.listscheduledrequests\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ess/rest/scheduler/v1/requests\n      name: submitscheduledrequest\n      operations:\n      - method: POST\n        name: submitscheduledrequest\n        description: Oracle Fusion Cloud Applications Submit a scheduled process request\n        call: oracle-fusion.submitscheduledrequest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ess/rest/scheduler/v1/requests/{requestId}\n      name: getscheduledrequest\n      operations:\n      - method: GET\n        name: getscheduledrequest\n        description: Oracle Fusion Cloud Applications Get a scheduled process request\n        call: oracle-fusion.getscheduledrequest\n        with:\n          requestId:\
  \ rest.requestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bpm/api/4.0/tasks\n      name: listworkflowtasks\n      operations:\n      - method: GET\n        name: listworkflowtasks\n        description: Oracle Fusion Cloud Applications List workflow tasks\n        call: oracle-fusion.listworkflowtasks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bpm/api/4.0/tasks/{id}\n      name: getworkflowtask\n      operations:\n      - method: GET\n        name: getworkflowtask\n        description: Oracle Fusion Cloud Applications Get a workflow task\n        call: oracle-fusion.getworkflowtask\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bpm/api/4.0/tasks/{id}\n      name: performtaskaction\n      operations:\n      - method: PUT\n        name: performtaskaction\n        description: Oracle Fusion Cloud Applications Perform a task\
  \ action\n        call: oracle-fusion.performtaskaction\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/resources/11.13.18.05/features\n      name: listfeatures\n      operations:\n      - method: GET\n        name: listfeatures\n        description: Oracle Fusion Cloud Applications List features\n        call: oracle-fusion.listfeatures\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fscmRestApi/fndAuditRESTService/audittrail/getaudithistory\n      name: getaudithistory\n      operations:\n      - method: GET\n        name: getaudithistory\n        description: Oracle Fusion Cloud Applications Get audit history\n        call: oracle-fusion.getaudithistory\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oracle-fusion-mcp\n    transport: http\n    description: MCP adapter for Oracle Fusion\
  \ Cloud Applications Oracle Fusion Common Features REST API for AI agent use.\n    tools:\n    - name: listcommonlookups\n      description: Oracle Fusion Cloud Applications List common lookups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.listcommonlookups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcommonlookup\n      description: Oracle Fusion Cloud Applications Create a common lookup\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-fusion.createcommonlookup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcommonlookup\n      description: Oracle Fusion Cloud Applications Get a common lookup\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.getcommonlookup\n      with:\n        LookupType: tools.LookupType\n\
  \      inputParameters:\n      - name: LookupType\n        type: string\n        description: Lookup type identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecommonlookup\n      description: Oracle Fusion Cloud Applications Update a common lookup\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-fusion.updatecommonlookup\n      with:\n        LookupType: tools.LookupType\n      inputParameters:\n      - name: LookupType\n        type: string\n        description: LookupType\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecommonlookup\n      description: Oracle Fusion Cloud Applications Delete a common lookup\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: oracle-fusion.deletecommonlookup\n      with:\n        LookupType: tools.LookupType\n\
  \      inputParameters:\n      - name: LookupType\n        type: string\n        description: LookupType\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlookupcodes\n      description: Oracle Fusion Cloud Applications List lookup codes for a lookup type\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.listlookupcodes\n      with:\n        LookupType: tools.LookupType\n      inputParameters:\n      - name: LookupType\n        type: string\n        description: LookupType\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createlookupcode\n      description: Oracle Fusion Cloud Applications Create a lookup code\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-fusion.createlookupcode\n      with:\n        LookupType: tools.LookupType\n      inputParameters:\n\
  \      - name: LookupType\n        type: string\n        description: LookupType\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listannouncements\n      description: Oracle Fusion Cloud Applications List announcements\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.listannouncements\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createannouncement\n      description: Oracle Fusion Cloud Applications Create an announcement\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-fusion.createannouncement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getannouncement\n      description: Oracle Fusion Cloud Applications Get an announcement\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ oracle-fusion.getannouncement\n      with:\n        AnnouncementId: tools.AnnouncementId\n      inputParameters:\n      - name: AnnouncementId\n        type: integer\n        description: AnnouncementId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateannouncement\n      description: Oracle Fusion Cloud Applications Update an announcement\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-fusion.updateannouncement\n      with:\n        AnnouncementId: tools.AnnouncementId\n      inputParameters:\n      - name: AnnouncementId\n        type: integer\n        description: AnnouncementId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteannouncement\n      description: Oracle Fusion Cloud Applications Delete an announcement\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: oracle-fusion.deleteannouncement\n      with:\n        AnnouncementId: tools.AnnouncementId\n      inputParameters:\n      - name: AnnouncementId\n        type: integer\n        description: AnnouncementId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpersons\n      description: Oracle Fusion Cloud Applications List persons\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.listpersons\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createperson\n      description: Oracle Fusion Cloud Applications Create a person\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-fusion.createperson\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getperson\n      description: Oracle Fusion Cloud Applications Get a person\n    \
  \  hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.getperson\n      with:\n        Personid: tools.Personid\n      inputParameters:\n      - name: Personid\n        type: integer\n        description: Personid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateperson\n      description: Oracle Fusion Cloud Applications Update a person\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-fusion.updateperson\n      with:\n        Personid: tools.Personid\n      inputParameters:\n      - name: Personid\n        type: integer\n        description: Personid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteperson\n      description: Oracle Fusion Cloud Applications Delete a person\n      hints:\n        readOnly: false\n        destructive: true\n \
  \       idempotent: true\n      call: oracle-fusion.deleteperson\n      with:\n        Personid: tools.Personid\n      inputParameters:\n      - name: Personid\n        type: integer\n        description: Personid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroles\n      description: Oracle Fusion Cloud Applications List roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.listroles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrole\n      description: Oracle Fusion Cloud Applications Get a role\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.getrole\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: updaterole\n      description: Oracle Fusion Cloud Applications Update a role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-fusion.updaterole\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listscheduledrequests\n      description: Oracle Fusion Cloud Applications List scheduled process requests\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.listscheduledrequests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitscheduledrequest\n      description: Oracle Fusion Cloud Applications Submit a scheduled process request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: oracle-fusion.submitscheduledrequest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getscheduledrequest\n      description: Oracle Fusion Cloud Applications Get a scheduled process request\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.getscheduledrequest\n      with:\n        requestId: tools.requestId\n      inputParameters:\n      - name: requestId\n        type: integer\n        description: requestId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkflowtasks\n      description: Oracle Fusion Cloud Applications List workflow tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.listworkflowtasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkflowtask\n      description: Oracle Fusion\
  \ Cloud Applications Get a workflow task\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.getworkflowtask\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: performtaskaction\n      description: Oracle Fusion Cloud Applications Perform a task action\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: oracle-fusion.performtaskaction\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        descript\n\n# --- truncated at 32 KB (32 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/oracle-fusion/refs/heads/main/capabilities/oracle-fusion-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-fusion/refs/heads/main/capabilities/oracle-fusion-capability.yaml
tags:
- Oracle
- Fusion
- API
tools:
- description: Oracle Fusion Cloud Applications List common lookups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcommonlookups
- description: Oracle Fusion Cloud Applications Create a common lookup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcommonlookup
- description: Oracle Fusion Cloud Applications Get a common lookup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcommonlookup
- description: Oracle Fusion Cloud Applications Update a common lookup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecommonlookup
- description: Oracle Fusion Cloud Applications Delete a common lookup
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecommonlookup
- description: Oracle Fusion Cloud Applications List lookup codes for a lookup type
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlookupcodes
- description: Oracle Fusion Cloud Applications Create a lookup code
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlookupcode
- description: Oracle Fusion Cloud Applications List announcements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listannouncements
- description: Oracle Fusion Cloud Applications Create an announcement
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createannouncement
- description: Oracle Fusion Cloud Applications Get an announcement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getannouncement
- description: Oracle Fusion Cloud Applications Update an announcement
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateannouncement
- description: Oracle Fusion Cloud Applications Delete an announcement
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteannouncement
- description: Oracle Fusion Cloud Applications List persons
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpersons
- description: Oracle Fusion Cloud Applications Create a person
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createperson
- description: Oracle Fusion Cloud Applications Get a person
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getperson
- description: Oracle Fusion Cloud Applications Update a person
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateperson
- description: Oracle Fusion Cloud Applications Delete a person
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteperson
- description: Oracle Fusion Cloud Applications List roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroles
- description: Oracle Fusion Cloud Applications Get a role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrole
- description: Oracle Fusion Cloud Applications Update a role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updaterole
- description: Oracle Fusion Cloud Applications List scheduled process requests
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscheduledrequests
- description: Oracle Fusion Cloud Applications Submit a scheduled process request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitscheduledrequest
- description: Oracle Fusion Cloud Applications Get a scheduled process request
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getscheduledrequest
- description: Oracle Fusion Cloud Applications List workflow tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflowtasks
- description: Oracle Fusion Cloud Applications Get a workflow task
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflowtask
- description: Oracle Fusion Cloud Applications Perform a task action
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: performtaskaction
- description: Oracle Fusion Cloud Applications List features
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfeatures
- description: Oracle Fusion Cloud Applications Get audit history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaudithistory
---
