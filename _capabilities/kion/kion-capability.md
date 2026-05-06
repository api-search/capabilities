---
categories: []
consumed_apis: []
description: The Kion Public API provides programmatic access to manage cloud operations, governance, compliance, and financial management across AWS, Azure, GCP, and OCI. Kion is a self-hosted cloud operations platform that consolidates account provisioning, access management, compliance enforcement, and FinOps into a single interface. The API uses Bearer token authentication via Kion App API Keys and is accessible at the /api/v3/ path of your Kion instance.
layout: capability
name: Kion Cloud Operations API
operations:
- description: Kion List accounts
  method: GET
  name: listaccounts
  path: /account
- description: Kion Create an account
  method: POST
  name: createaccount
  path: /account
- description: Kion Get an account
  method: GET
  name: getaccount
  path: /account/{id}
- description: Kion Update an account
  method: PATCH
  name: updateaccount
  path: /account/{id}
- description: Kion List projects
  method: GET
  name: listprojects
  path: /project
- description: Kion Create a project
  method: POST
  name: createproject
  path: /project
- description: Kion Get a project
  method: GET
  name: getproject
  path: /project/{id}
- description: Kion Update a project
  method: PATCH
  name: updateproject
  path: /project/{id}
- description: Kion Delete a project
  method: DELETE
  name: deleteproject
  path: /project/{id}
- description: Kion List project notes
  method: GET
  name: listprojectnotes
  path: /project/{id}/note
- description: Kion Create a project note
  method: POST
  name: createprojectnote
  path: /project/{id}/note
- description: Kion List project enforcements
  method: GET
  name: listprojectenforcements
  path: /project/{id}/enforcement
- description: Kion Create a project enforcement
  method: POST
  name: createprojectenforcement
  path: /project/{id}/enforcement
- description: Kion List project cloud access roles
  method: GET
  name: listprojectcloudaccessroles
  path: /project/{id}/cloud-access-role
- description: Kion Create a project cloud access role
  method: POST
  name: createprojectcloudaccessrole
  path: /project/{id}/cloud-access-role
- description: Kion List project permission mappings
  method: GET
  name: listprojectpermissionmappings
  path: /project/{id}/permission-mapping
- description: Kion Create a project permission mapping
  method: POST
  name: createprojectpermissionmapping
  path: /project/{id}/permission-mapping
- description: Kion List organizational units
  method: GET
  name: listous
  path: /ou
- description: Kion Create an organizational unit
  method: POST
  name: createou
  path: /ou
- description: Kion Get an organizational unit
  method: GET
  name: getou
  path: /ou/{id}
- description: Kion Update an organizational unit
  method: PATCH
  name: updateou
  path: /ou/{id}
- description: Kion Delete an organizational unit
  method: DELETE
  name: deleteou
  path: /ou/{id}
- description: Kion List OU cloud access roles
  method: GET
  name: listoucloudaccessroles
  path: /ou/{id}/cloud-access-role
- description: Kion Create an OU cloud access role
  method: POST
  name: createoucloudaccessrole
  path: /ou/{id}/cloud-access-role
- description: Kion List OU permission mappings
  method: GET
  name: listoupermissionmappings
  path: /ou/{id}/permission-mapping
- description: Kion Create an OU permission mapping
  method: POST
  name: createoupermissionmapping
  path: /ou/{id}/permission-mapping
- description: Kion List cloud rules
  method: GET
  name: listcloudrules
  path: /cloud-rule
- description: Kion Create a cloud rule
  method: POST
  name: createcloudrule
  path: /cloud-rule
- description: Kion Get a cloud rule
  method: GET
  name: getcloudrule
  path: /cloud-rule/{id}
- description: Kion Update a cloud rule
  method: PATCH
  name: updatecloudrule
  path: /cloud-rule/{id}
- description: Kion Delete a cloud rule
  method: DELETE
  name: deletecloudrule
  path: /cloud-rule/{id}
- description: Kion List compliance checks
  method: GET
  name: listcompliancechecks
  path: /compliance-check
- description: Kion Create a compliance check
  method: POST
  name: createcompliancecheck
  path: /compliance-check
- description: Kion Get a compliance check
  method: GET
  name: getcompliancecheck
  path: /compliance-check/{id}
- description: Kion Update a compliance check
  method: PATCH
  name: updatecompliancecheck
  path: /compliance-check/{id}
- description: Kion Delete a compliance check
  method: DELETE
  name: deletecompliancecheck
  path: /compliance-check/{id}
- description: Kion List compliance standards
  method: GET
  name: listcompliancestandards
  path: /compliance-standard
- description: Kion Create a compliance standard
  method: POST
  name: createcompliancestandard
  path: /compliance-standard
- description: Kion Get a compliance standard
  method: GET
  name: getcompliancestandard
  path: /compliance-standard/{id}
- description: Kion Update a compliance standard
  method: PATCH
  name: updatecompliancestandard
  path: /compliance-standard/{id}
- description: Kion Delete a compliance standard
  method: DELETE
  name: deletecompliancestandard
  path: /compliance-standard/{id}
- description: Kion List funding sources
  method: GET
  name: listfundingsources
  path: /funding-source
- description: Kion Create a funding source
  method: POST
  name: createfundingsource
  path: /funding-source
- description: Kion Get a funding source
  method: GET
  name: getfundingsource
  path: /funding-source/{id}
- description: Kion Update a funding source
  method: PATCH
  name: updatefundingsource
  path: /funding-source/{id}
- description: Kion Delete a funding source
  method: DELETE
  name: deletefundingsource
  path: /funding-source/{id}
- description: Kion List funding source permission mappings
  method: GET
  name: listfundingsourcepermissionmappings
  path: /funding-source/{id}/permission-mapping
- description: Kion Create a funding source permission mapping
  method: POST
  name: createfundingsourcepermissionmapping
  path: /funding-source/{id}/permission-mapping
- description: Kion List labels
  method: GET
  name: listlabels
  path: /label
- description: Kion Create a label
  method: POST
  name: createlabel
  path: /label
- description: Kion Get a label
  method: GET
  name: getlabel
  path: /label/{id}
- description: Kion Update a label
  method: PATCH
  name: updatelabel
  path: /label/{id}
- description: Kion Delete a label
  method: DELETE
  name: deletelabel
  path: /label/{id}
- description: Kion List users
  method: GET
  name: listusers
  path: /user
- description: Kion Create a user
  method: POST
  name: createuser
  path: /user
- description: Kion Get a user
  method: GET
  name: getuser
  path: /user/{id}
- description: Kion Update a user
  method: PATCH
  name: updateuser
  path: /user/{id}
- description: Kion Delete a user
  method: DELETE
  name: deleteuser
  path: /user/{id}
- description: Kion List user groups
  method: GET
  name: listusergroups
  path: /user-group
- description: Kion Create a user group
  method: POST
  name: createusergroup
  path: /user-group
personas: []
provider_name: Kion
provider_slug: kion
search_terms:
- createprojectnote
- listlabels
- finops
- deleteproject
- kion create a user group
- listcloudrules
- listfundingsourcepermissionmappings
- getlabel
- getproject
- kion create a compliance standard
- createoucloudaccessrole
- kion list compliance standards
- createfundingsourcepermissionmapping
- api
- listcompliancestandards
- createou
- listoupermissionmappings
- getuser
- kion delete a funding source
- kion list project cloud access roles
- getcompliancestandard
- getcloudrule
- updateuser
- deletecompliancecheck
- createproject
- updateou
- kion update a compliance standard
- kion create a user
- deleteuser
- createuser
- kion create an ou permission mapping
- deletefundingsource
- kion list funding sources
- createfundingsource
- deletelabel
- kion update a compliance check
- updateproject
- updatecompliancecheck
- kion list organizational units
- spend
- createprojectenforcement
- listcompliancechecks
- getou
- kion create a compliance check
- listprojectcloudaccessroles
- createoupermissionmapping
- kion list funding source permission mappings
- kion create a label
- listprojects
- listoucloudaccessroles
- kion get a cloud rule
- updatecompliancestandard
- listfundingsources
- kion get a compliance standard
- listusers
- kion update a label
- kion list compliance checks
- listaccounts
- kion
- kion delete a compliance check
- kion update a funding source
- kion delete a project
- kion create an organizational unit
- updatefundingsource
- kion create a funding source permission mapping
- listprojectnotes
- kion get an account
- createprojectcloudaccessrole
- kion create a funding source
- kion update a cloud rule
- compliance
- listusergroups
- kion delete a user
- createusergroup
- createcompliancecheck
- kion get a label
- kion delete an organizational unit
- kion delete a label
- updatecloudrule
- kion list users
- kion get a funding source
- updateaccount
- kion create a project enforcement
- kion create a project note
- deleteou
- kion get a compliance check
- deletecloudrule
- kion create an account
- kion create an ou cloud access role
- kion update a user
- kion list user groups
- costs
- createcompliancestandard
- governance
- kion create a project
- kion create a project permission mapping
- listprojectpermissionmappings
- kion list cloud rules
- kion update an organizational unit
- createcloudrule
- deletecompliancestandard
- kion list projects
- createaccount
- kion get a project
- kion list labels
- updatelabel
- createprojectpermissionmapping
- kion list ou cloud access roles
- cloud operations
- kion create a cloud rule
- getaccount
- kion list accounts
- listous
- kion create a project cloud access role
- getfundingsource
- kion list project notes
- createlabel
- kion list project permission mappings
- listprojectenforcements
- kion get a user
- kion delete a cloud rule
- kion update a project
- kion list project enforcements
- getcompliancecheck
- kion list ou permission mappings
- kion get an organizational unit
- kion delete a compliance standard
- kion update an account
slug: kion-capability
source_filename: kion-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Kion Cloud Operations API\n  description: The Kion Public API provides programmatic access to manage cloud operations, governance, compliance, and financial\n    management across AWS, Azure, GCP, and OCI. Kion is a self-hosted cloud operations platform that consolidates account\n    provisioning, access management, compliance enforcement, and FinOps into a single interface. The API uses Bearer token\n    authentication via Kion App API Keys and is accessible at the /api/v3/ path of your Kion instance.\n  tags:\n  - Kion\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: kion\n    baseUri: https://your-kion-instance.example.com/api/v3\n    description: Kion Cloud Operations API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{KION_TOKEN}}'\n    resources:\n    - name: account\n      path: /account\n      operations:\n      - name: listaccounts\n     \
  \   method: GET\n        description: Kion List accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createaccount\n        method: POST\n        description: Kion Create an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-id\n      path: /account/{id}\n      operations:\n      - name: getaccount\n        method: GET\n        description: Kion Get an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccount\n        method: PATCH\n        description: Kion Update an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project\n      path: /project\n      operations:\n      - name: listprojects\n\
  \        method: GET\n        description: Kion List projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Kion Create a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project-id\n      path: /project/{id}\n      operations:\n      - name: getproject\n        method: GET\n        description: Kion Get a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PATCH\n        description: Kion Update a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproject\n        method: DELETE\n        description: Kion Delete\
  \ a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project-id-note\n      path: /project/{id}/note\n      operations:\n      - name: listprojectnotes\n        method: GET\n        description: Kion List project notes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createprojectnote\n        method: POST\n        description: Kion Create a project note\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project-id-enforcement\n      path: /project/{id}/enforcement\n      operations:\n      - name: listprojectenforcements\n        method: GET\n        description: Kion List project enforcements\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n      - name: createprojectenforcement\n        method: POST\n        description: Kion Create a project enforcement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project-id-cloud-access-role\n      path: /project/{id}/cloud-access-role\n      operations:\n      - name: listprojectcloudaccessroles\n        method: GET\n        description: Kion List project cloud access roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createprojectcloudaccessrole\n        method: POST\n        description: Kion Create a project cloud access role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project-id-permission-mapping\n      path: /project/{id}/permission-mapping\n      operations:\n      - name: listprojectpermissionmappings\n\
  \        method: GET\n        description: Kion List project permission mappings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createprojectpermissionmapping\n        method: POST\n        description: Kion Create a project permission mapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ou\n      path: /ou\n      operations:\n      - name: listous\n        method: GET\n        description: Kion List organizational units\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createou\n        method: POST\n        description: Kion Create an organizational unit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ou-id\n      path:\
  \ /ou/{id}\n      operations:\n      - name: getou\n        method: GET\n        description: Kion Get an organizational unit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateou\n        method: PATCH\n        description: Kion Update an organizational unit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteou\n        method: DELETE\n        description: Kion Delete an organizational unit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ou-id-cloud-access-role\n      path: /ou/{id}/cloud-access-role\n      operations:\n      - name: listoucloudaccessroles\n        method: GET\n        description: Kion List OU cloud access roles\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: createoucloudaccessrole\n        method: POST\n        description: Kion Create an OU cloud access role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ou-id-permission-mapping\n      path: /ou/{id}/permission-mapping\n      operations:\n      - name: listoupermissionmappings\n        method: GET\n        description: Kion List OU permission mappings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createoupermissionmapping\n        method: POST\n        description: Kion Create an OU permission mapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-rule\n      path: /cloud-rule\n      operations:\n      - name: listcloudrules\n        method:\
  \ GET\n        description: Kion List cloud rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcloudrule\n        method: POST\n        description: Kion Create a cloud rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-rule-id\n      path: /cloud-rule/{id}\n      operations:\n      - name: getcloudrule\n        method: GET\n        description: Kion Get a cloud rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecloudrule\n        method: PATCH\n        description: Kion Update a cloud rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecloudrule\n        method: DELETE\n        description:\
  \ Kion Delete a cloud rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-check\n      path: /compliance-check\n      operations:\n      - name: listcompliancechecks\n        method: GET\n        description: Kion List compliance checks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcompliancecheck\n        method: POST\n        description: Kion Create a compliance check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-check-id\n      path: /compliance-check/{id}\n      operations:\n      - name: getcompliancecheck\n        method: GET\n        description: Kion Get a compliance check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: updatecompliancecheck\n        method: PATCH\n        description: Kion Update a compliance check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecompliancecheck\n        method: DELETE\n        description: Kion Delete a compliance check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-standard\n      path: /compliance-standard\n      operations:\n      - name: listcompliancestandards\n        method: GET\n        description: Kion List compliance standards\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcompliancestandard\n        method: POST\n        description: Kion Create a compliance standard\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: compliance-standard-id\n      path: /compliance-standard/{id}\n      operations:\n      - name: getcompliancestandard\n        method: GET\n        description: Kion Get a compliance standard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecompliancestandard\n        method: PATCH\n        description: Kion Update a compliance standard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecompliancestandard\n        method: DELETE\n        description: Kion Delete a compliance standard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: funding-source\n      path: /funding-source\n      operations:\n      - name: listfundingsources\n\
  \        method: GET\n        description: Kion List funding sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfundingsource\n        method: POST\n        description: Kion Create a funding source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: funding-source-id\n      path: /funding-source/{id}\n      operations:\n      - name: getfundingsource\n        method: GET\n        description: Kion Get a funding source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefundingsource\n        method: PATCH\n        description: Kion Update a funding source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefundingsource\n\
  \        method: DELETE\n        description: Kion Delete a funding source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: funding-source-id-permission-mapping\n      path: /funding-source/{id}/permission-mapping\n      operations:\n      - name: listfundingsourcepermissionmappings\n        method: GET\n        description: Kion List funding source permission mappings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfundingsourcepermissionmapping\n        method: POST\n        description: Kion Create a funding source permission mapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: label\n      path: /label\n      operations:\n      - name: listlabels\n        method: GET\n        description: Kion List labels\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlabel\n        method: POST\n        description: Kion Create a label\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: label-id\n      path: /label/{id}\n      operations:\n      - name: getlabel\n        method: GET\n        description: Kion Get a label\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelabel\n        method: PATCH\n        description: Kion Update a label\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelabel\n        method: DELETE\n        description: Kion Delete a label\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /user\n      operations:\n      - name: listusers\n        method: GET\n        description: Kion List users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Kion Create a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-id\n      path: /user/{id}\n      operations:\n      - name: getuser\n        method: GET\n        description: Kion Get a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PATCH\n        description: Kion Update a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Kion Delete a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-group\n      path: /user-group\n      operations:\n      - name: listusergroups\n        method: GET\n        description: Kion List user groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createusergroup\n        method: POST\n        description: Kion Create a user group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kion-rest\n    description: REST adapter for Kion Cloud Operations API.\n    resources:\n    - path: /account\n      name: listaccounts\n      operations:\n      - method:\
  \ GET\n        name: listaccounts\n        description: Kion List accounts\n        call: kion.listaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account\n      name: createaccount\n      operations:\n      - method: POST\n        name: createaccount\n        description: Kion Create an account\n        call: kion.createaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/{id}\n      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Kion Get an account\n        call: kion.getaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/{id}\n      name: updateaccount\n      operations:\n      - method: PATCH\n        name: updateaccount\n        description: Kion Update an account\n        call: kion.updateaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /project\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: Kion List projects\n        call: kion.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /project\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Kion Create a project\n        call: kion.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /project/{id}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Kion Get a project\n        call: kion.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /project/{id}\n      name: updateproject\n      operations:\n      - method: PATCH\n        name: updateproject\n        description: Kion Update a project\n        call: kion.updateproject\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /project/{id}\n      name: deleteproject\n      operations:\n      - method: DELETE\n        name: deleteproject\n        description: Kion Delete a project\n        call: kion.deleteproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /project/{id}/note\n      name: listprojectnotes\n      operations:\n      - method: GET\n        name: listprojectnotes\n        description: Kion List project notes\n        call: kion.listprojectnotes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /project/{id}/note\n      name: createprojectnote\n      operations:\n      - method: POST\n        name: createprojectnote\n        description: Kion Create a project note\n        call: kion.createprojectnote\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /project/{id}/enforcement\n      name: listprojectenforcements\n\
  \      operations:\n      - method: GET\n        name: listprojectenforcements\n        description: Kion List project enforcements\n        call: kion.listprojectenforcements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /project/{id}/enforcement\n      name: createprojectenforcement\n      operations:\n      - method: POST\n        name: createprojectenforcement\n        description: Kion Create a project enforcement\n        call: kion.createprojectenforcement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /project/{id}/cloud-access-role\n      name: listprojectcloudaccessroles\n      operations:\n      - method: GET\n        name: listprojectcloudaccessroles\n        description: Kion List project cloud access roles\n        call: kion.listprojectcloudaccessroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /project/{id}/cloud-access-role\n      name: createprojectcloudaccessrole\n\
  \      operations:\n      - method: POST\n        name: createprojectcloudaccessrole\n        description: Kion Create a project cloud access role\n        call: kion.createprojectcloudaccessrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /project/{id}/permission-mapping\n      name: listprojectpermissionmappings\n      operations:\n      - method: GET\n        name: listprojectpermissionmappings\n        description: Kion List project permission mappings\n        call: kion.listprojectpermissionmappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /project/{id}/permission-mapping\n      name: createprojectpermissionmapping\n      operations:\n      - method: POST\n        name: createprojectpermissionmapping\n        description: Kion Create a project permission mapping\n        call: kion.createprojectpermissionmapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /ou\n      name: listous\n      operations:\n      - method: GET\n        name: listous\n        description: Kion List organizational units\n        call: kion.listous\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ou\n      name: createou\n      operations:\n      - method: POST\n        name: createou\n        description: Kion Create an organizational unit\n        call: kion.createou\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ou/{id}\n      name: getou\n      operations:\n      - method: GET\n        name: getou\n        description: Kion Get an organizational unit\n        call: kion.getou\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ou/{id}\n      name: updateou\n      operations:\n      - method: PATCH\n        name: updateou\n        description: Kion Update an organizational unit\n        call: kion.updateou\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /ou/{id}\n      name: deleteou\n      operations:\n      - method: DELETE\n        name: deleteou\n        description: Kion Delete an organizational unit\n        call: kion.deleteou\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ou/{id}/cloud-access-role\n      name: listoucloudaccessroles\n      operations:\n      - method: GET\n        name: listoucloudaccessroles\n        description: Kion List OU cloud access roles\n        call: kion.listoucloudaccessroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ou/{id}/cloud-access-role\n      name: createoucloudaccessrole\n      operations:\n      - method: POST\n        name: createoucloudaccessrole\n        description: Kion Create an OU cloud access role\n        call: kion.createoucloudaccessrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ou/{id}/permission-mapping\n\
  \      name: listoupermissionmappings\n      operations:\n      - method: GET\n        name: listoupermissionmappings\n        description: Kion List OU permission mappings\n        call: kion.listoupermissionmappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ou/{id}/permission-mapping\n      name: createoupermissionmapping\n      operations:\n      - method: POST\n        name: createoupermissionmapping\n        description: Kion Create an OU permission mapping\n        call: kion.createoupermissionmapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cloud-rule\n      name: listcloudrules\n      operations:\n      - method: GET\n        name: listcloudrules\n        description: Kion List cloud rules\n        call: kion.listcloudrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cloud-rule\n      name: createcloudrule\n      operations:\n      - method: POST\n\
  \        name: createcloudrule\n        description: Kion Create a cloud rule\n        call: kion.createcloudrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cloud-rule/{id}\n      name: getcloudrule\n      operations:\n      - method: GET\n        name: getcloudrule\n        description: Kion Get a cloud rule\n        call: kion.getcloudrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cloud-rule/{id}\n      name: updatecloudrule\n      operations:\n      - method: PATCH\n        name: updatecloudrule\n        description: Kion Update a cloud rule\n        call: kion.updatecloudrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cloud-rule/{id}\n      name: deletecloudrule\n      operations:\n      - method: DELETE\n        name: deletecloudrule\n        description: Kion Delete a cloud rule\n        call: kion.deletecloudrule\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /compliance-check\n      name: listcompliancechecks\n      operations:\n      - method: GET\n        name: listcompliancechecks\n        description: Kion List compliance checks\n        call: kion.listcompliancechecks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /compliance-check\n      name: createcompliancecheck\n      operations:\n      - method: POST\n        name: createcompliancecheck\n        description: Kion Create a compliance check\n        call: kion.createcompliancecheck\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /compliance-check/{id}\n      name: getcompliancecheck\n      operations:\n      - method: GET\n        name: getcompliancecheck\n        description: Kion Get a compliance check\n        call: kion.getcompliancecheck\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /compliance-check/{id}\n\
  \      name: updatecompliancecheck\n      operations:\n      - method: PATCH\n        name: updatecompliancecheck\n        description: Kion Update a compliance check\n        call: kion.updatecompliancecheck\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /compliance-check/{id}\n      name: deletecompliancecheck\n      operations:\n      - method: DELETE\n        name: deletecompliancecheck\n        description: Kion Delete a compliance check\n        call: kion.deletecompliancecheck\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /compliance-standard\n      name: listcompliancestandards\n      operations:\n      - method: GET\n        name: listcompliancestandards\n        description: Kion List compliance standards\n        call: kion.listcompliancestandards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /compliance-standard\n      name: createcompliancestandard\n  \
  \    operations:\n      - method: POST\n        name: createcompliancestandard\n        description: Kion Create a compliance standard\n        call: kion.createcompliancestandard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /compliance-standard/{id}\n      name: getcompliancestandard\n      operations:\n      - method: GET\n        name: getcompliancestandard\n        description: Kion Get a compliance standard\n        call: kion.getcompliancestandard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /compliance-standard/{id}\n      name: updatecompliancestandard\n      operations:\n      - method: PATCH\n        name: updatecompliancestandard\n        description: Kion Update a compliance standard\n        call: kion.updatecompliancestandard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /compliance-standard/{id}\n      name: deletecompliancestandard\n      operations:\n\
  \      - method: DELETE\n        name: deletecompliancestandard\n        description: Kion Delete a compliance standard\n        call: kion.deletecompliancestandard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /funding-source\n      name: listfundingsources\n      operations:\n      - method: GET\n        name: listfundingsources\n        description: Kion List funding sources\n        call: kion.listfundingsources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /funding-source\n      name: createfundingsource\n      operations:\n      - method: POST\n        name: createfundingsource\n        description: Kion Create a funding source\n        call: kion.createfundingsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /funding-source/{id}\n      name: getfundingsource\n      operations:\n      - method: GET\n        name: getfundingsource\n        description: Kion\
  \ Get a funding source\n        call: kion.getfundingsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /funding-source/{id}\n      name: updatefundingsource\n      operations:\n      - method: PATCH\n        name: updatefundingsource\n        description: Kion Update a funding source\n        call: kion.updatefundingsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /funding-source/{id}\n      name: deletefundingsource\n      operations:\n      - method: DELETE\n        name: deletefundingsource\n        description: Kion Delete a funding source\n        call: kion.deletefundingsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /funding-source/{id}/permission-mapping\n      name: listfundingsourcepermissionmappings\n      operations:\n      - method: GET\n        name: listfundingsourcepermissionmappings\n        description: Kion List funding source permission\
  \ mappings\n        call: kion.listfundingsourcepermissionmappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /funding-source/{id}/permission-mapping\n      name: createfundingsourcepermissionmapping\n      operations:\n      - method: POST\n        name: createfundingsourcepermissionmapping\n        description: Kion Create a funding source permission mapping\n        call: kion.createfundingsourcepermissionmapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /label\n      name: listlabels\n      operations:\n      - method: GET\n        name: listlabels\n        description: Kion List labels\n        call: kion.listlabels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /label\n      name: createlabel\n      operations:\n      - method: POST\n        name: createlabel\n        description: Kion Create a label\n        call: kion.createlabel\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /label/{id}\n      name: getlabel\n      operations:\n      - method: GET\n        name: getlabel\n        description: Kion Get a label\n        call: kion.getlabel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /label/{id}\n      name: updatelabel\n      operations:\n      - method: PATCH\n        name: updatelabel\n        description: Kion Update a label\n        call: kion.updatelabel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /label/{id}\n      name: deletelabel\n      operations:\n      - method: DELETE\n        name: deletelabel\n        description: Kion Delete a label\n        call: kion.deletelabel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: Kion List users\n        call: kion.listusers\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Kion Create a user\n        call: kion.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user/{id}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Kion Get a user\n        call: kion.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user/{id}\n      name: updateuser\n      operations:\n      - method: PATCH\n        name: updateuser\n        description: Kion Update a user\n        call: kion.updateuser\n        outputParameters:\n      \n\n# --- truncated at 32 KB (48 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/kion/refs/heads/main/capabilities/kion-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/kion/refs/heads/main/capabilities/kion-capability.yaml
tags:
- Kion
- API
tools:
- description: Kion List accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Kion Create an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaccount
- description: Kion Get an account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Kion Update an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateaccount
- description: Kion List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Kion Create a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Kion Get a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Kion Update a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateproject
- description: Kion Delete a project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproject
- description: Kion List project notes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectnotes
- description: Kion Create a project note
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprojectnote
- description: Kion List project enforcements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectenforcements
- description: Kion Create a project enforcement
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprojectenforcement
- description: Kion List project cloud access roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectcloudaccessroles
- description: Kion Create a project cloud access role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprojectcloudaccessrole
- description: Kion List project permission mappings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectpermissionmappings
- description: Kion Create a project permission mapping
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprojectpermissionmapping
- description: Kion List organizational units
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listous
- description: Kion Create an organizational unit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createou
- description: Kion Get an organizational unit
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getou
- description: Kion Update an organizational unit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateou
- description: Kion Delete an organizational unit
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteou
- description: Kion List OU cloud access roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoucloudaccessroles
- description: Kion Create an OU cloud access role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createoucloudaccessrole
- description: Kion List OU permission mappings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoupermissionmappings
- description: Kion Create an OU permission mapping
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createoupermissionmapping
- description: Kion List cloud rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcloudrules
- description: Kion Create a cloud rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcloudrule
- description: Kion Get a cloud rule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcloudrule
- description: Kion Update a cloud rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecloudrule
- description: Kion Delete a cloud rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecloudrule
- description: Kion List compliance checks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcompliancechecks
- description: Kion Create a compliance check
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcompliancecheck
- description: Kion Get a compliance check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompliancecheck
- description: Kion Update a compliance check
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecompliancecheck
- description: Kion Delete a compliance check
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecompliancecheck
- description: Kion List compliance standards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcompliancestandards
- description: Kion Create a compliance standard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcompliancestandard
- description: Kion Get a compliance standard
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcompliancestandard
- description: Kion Update a compliance standard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecompliancestandard
- description: Kion Delete a compliance standard
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecompliancestandard
- description: Kion List funding sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfundingsources
- description: Kion Create a funding source
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfundingsource
- description: Kion Get a funding source
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfundingsource
- description: Kion Update a funding source
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatefundingsource
- description: Kion Delete a funding source
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefundingsource
- description: Kion List funding source permission mappings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfundingsourcepermissionmappings
- description: Kion Create a funding source permission mapping
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfundingsourcepermissionmapping
- description: Kion List labels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlabels
- description: Kion Create a label
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlabel
- description: Kion Get a label
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlabel
- description: Kion Update a label
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatelabel
- description: Kion Delete a label
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelabel
- description: Kion List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Kion Create a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Kion Get a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Kion Update a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateuser
- description: Kion Delete a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Kion List user groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusergroups
- description: Kion Create a user group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createusergroup
---
