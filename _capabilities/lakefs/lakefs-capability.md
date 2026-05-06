---
categories: []
consumed_apis: []
description: lakeFS HTTP API
layout: capability
name: lakeFS API
operations:
- description: setup communications preferences
  method: POST
  name: setupcommprefs
  path: /setup_comm_prefs
- description: check if the lakeFS installation is already set up
  method: GET
  name: getsetupstate
  path: /setup_lakefs
- description: setup lakeFS and create a first user
  method: POST
  name: setup
  path: /setup_lakefs
- description: get current user
  method: GET
  name: getcurrentuser
  path: /user
- description: perform a login
  method: POST
  name: login
  path: /auth/login
- description: perform a login using an external authenticator
  method: POST
  name: externalprincipallogin
  path: /auth/external/principal/login
- description: perform a login with STS
  method: POST
  name: stslogin
  path: /sts/login
- description: list authentication capabilities supported
  method: GET
  name: getauthcapabilities
  path: /auth/capabilities
- description: list users
  method: GET
  name: listusers
  path: /auth/users
- description: create user
  method: POST
  name: createuser
  path: /auth/users
- description: get user
  method: GET
  name: getuser
  path: /auth/users/{userId}
- description: delete user
  method: DELETE
  name: deleteuser
  path: /auth/users/{userId}
- description: list groups
  method: GET
  name: listgroups
  path: /auth/groups
- description: create group
  method: POST
  name: creategroup
  path: /auth/groups
- description: get group
  method: GET
  name: getgroup
  path: /auth/groups/{groupId}
- description: delete group
  method: DELETE
  name: deletegroup
  path: /auth/groups/{groupId}
- description: list policies
  method: GET
  name: listpolicies
  path: /auth/policies
- description: create policy
  method: POST
  name: createpolicy
  path: /auth/policies
- description: get policy
  method: GET
  name: getpolicy
  path: /auth/policies/{policyId}
- description: update policy
  method: PUT
  name: updatepolicy
  path: /auth/policies/{policyId}
- description: delete policy
  method: DELETE
  name: deletepolicy
  path: /auth/policies/{policyId}
- description: list group members
  method: GET
  name: listgroupmembers
  path: /auth/groups/{groupId}/members
- description: add group membership
  method: PUT
  name: addgroupmembership
  path: /auth/groups/{groupId}/members/{userId}
- description: delete group membership
  method: DELETE
  name: deletegroupmembership
  path: /auth/groups/{groupId}/members/{userId}
- description: list user credentials
  method: GET
  name: listusercredentials
  path: /auth/users/{userId}/credentials
- description: create credentials
  method: POST
  name: createcredentials
  path: /auth/users/{userId}/credentials
- description: delete credentials
  method: DELETE
  name: deletecredentials
  path: /auth/users/{userId}/credentials/{accessKeyId}
- description: get credentials
  method: GET
  name: getcredentials
  path: /auth/users/{userId}/credentials/{accessKeyId}
- description: list user groups
  method: GET
  name: listusergroups
  path: /auth/users/{userId}/groups
- description: list user policies
  method: GET
  name: listuserpolicies
  path: /auth/users/{userId}/policies
- description: attach policy to user
  method: PUT
  name: attachpolicytouser
  path: /auth/users/{userId}/policies/{policyId}
- description: detach policy from user
  method: DELETE
  name: detachpolicyfromuser
  path: /auth/users/{userId}/policies/{policyId}
- description: attach external principal to user
  method: POST
  name: createuserexternalprincipal
  path: /auth/users/{userId}/external/principals
- description: delete external principal from user
  method: DELETE
  name: deleteuserexternalprincipal
  path: /auth/users/{userId}/external/principals
- description: list user external policies attached to a user
  method: GET
  name: listuserexternalprincipals
  path: /auth/users/{userId}/external/principals/ls
- description: describe external principal by id
  method: GET
  name: getexternalprincipal
  path: /auth/external/principals
- description: list group policies
  method: GET
  name: listgrouppolicies
  path: /auth/groups/{groupId}/policies
- description: attach policy to group
  method: PUT
  name: attachpolicytogroup
  path: /auth/groups/{groupId}/policies/{policyId}
- description: detach policy from group
  method: DELETE
  name: detachpolicyfromgroup
  path: /auth/groups/{groupId}/policies/{policyId}
- description: set ACL of group
  method: POST
  name: setgroupacl
  path: /auth/groups/{groupId}/acl
- description: get ACL of group
  method: GET
  name: getgroupacl
  path: /auth/groups/{groupId}/acl
- description: list repositories
  method: GET
  name: listrepositories
  path: /repositories
- description: create repository
  method: POST
  name: createrepository
  path: /repositories
- description: get repository
  method: GET
  name: getrepository
  path: /repositories/{repository}
- description: delete repository
  method: DELETE
  name: deleterepository
  path: /repositories/{repository}
- description: get repository metadata
  method: GET
  name: getrepositorymetadata
  path: /repositories/{repository}/metadata
- description: set repository metadata
  method: POST
  name: setrepositorymetadata
  path: /repositories/{repository}/metadata
- description: delete repository metadata
  method: DELETE
  name: deleterepositorymetadata
  path: /repositories/{repository}/metadata
- description: get repository GC rules
  method: GET
  name: getgcrules
  path: /repositories/{repository}/settings/gc_rules
- description: PUT /repositories/{repository}/settings/gc_rules
  method: PUT
  name: setgcrules
  path: /repositories/{repository}/settings/gc_rules
- description: DELETE /repositories/{repository}/settings/gc_rules
  method: DELETE
  name: deletegcrules
  path: /repositories/{repository}/settings/gc_rules
- description: get branch protection rules
  method: GET
  name: getbranchprotectionrules
  path: /repositories/{repository}/settings/branch_protection
- description: PUT /repositories/{repository}/settings/branch_protection
  method: PUT
  name: setbranchprotectionrules
  path: /repositories/{repository}/settings/branch_protection
- description: 'Dump repository refs (tags, commits, branches) to object store Deprecated: a new API will introduce long running operations'
  method: PUT
  name: dumprefs
  path: /repositories/{repository}/refs/dump
- description: 'Restore repository refs (tags, commits, branches) from object store. Deprecated: a new API will introduce long running operations'
  method: PUT
  name: restorerefs
  path: /repositories/{repository}/refs/restore
- description: Backup the repository metadata (tags, commits, branches) and save the backup to the object store.
  method: POST
  name: dumpsubmit
  path: /repositories/{repository}/dump
- description: Status of a repository dump task
  method: GET
  name: dumpstatus
  path: /repositories/{repository}/dump
- description: Restore repository from a dump in the object store
  method: POST
  name: restoresubmit
  path: /repositories/{repository}/restore
- description: Status of a restore request
  method: GET
  name: restorestatus
  path: /repositories/{repository}/restore
- description: list tags
  method: GET
  name: listtags
  path: /repositories/{repository}/tags
personas: []
provider_name: lakeFS
provider_slug: lakefs
search_terms:
- attach external principal to user
- list group members
- perform a login
- describe external principal by id
- getrepository
- get credentials
- check if the lakefs installation is already set up
- delete user
- stslogin
- detach policy from user
- login
- deleterepositorymetadata
- api
- lakefs
- restorestatus
- setrepositorymetadata
- getuser
- list user external policies attached to a user
- setgroupacl
- put /repositories/{repository}/settings/branch_protection
- get policy
- deletepolicy
- list groups
- setup lakefs and create a first user
- deleteuser
- create repository
- data version control
- detachpolicyfromgroup
- creategroup
- list policies
- createuser
- set repository metadata
- dumpsubmit
- detachpolicyfromuser
- get repository gc rules
- get acl of group
- list group policies
- attach policy to user
- createrepository
- list user policies
- delete group
- getcredentials
- listuserexternalprincipals
- create user
- addgroupmembership
- deletegroupmembership
- status of a restore request
- updatepolicy
- restore repository from a dump in the object store
- setup communications preferences
- deleterepository
- open source
- attachpolicytouser
- listgroups
- externalprincipallogin
- list user groups
- list authentication capabilities supported
- delete policy
- create credentials
- listusercredentials
- get current user
- backup the repository metadata (tags, commits, branches) and save the backup to the object store.
- perform a login using an external authenticator
- listusers
- getgroup
- delete repository
- delete credentials
- createuserexternalprincipal
- listrepositories
- listgrouppolicies
- deletegcrules
- deleteuserexternalprincipal
- getgroupacl
- delete repository metadata
- 'restore repository refs (tags, commits, branches) from object store. deprecated: a new api will introduce long running operations'
- dumpstatus
- 'dump repository refs (tags, commits, branches) to object store deprecated: a new api will introduce long running operations'
- setgcrules
- setup
- listpolicies
- listgroupmembers
- listusergroups
- listuserpolicies
- set acl of group
- getexternalprincipal
- get repository metadata
- update policy
- detach policy from group
- getgcrules
- delete /repositories/{repository}/settings/gc_rules
- get branch protection rules
- attachpolicytogroup
- dumprefs
- git-like
- restorerefs
- list user credentials
- getcurrentuser
- listtags
- get repository
- createpolicy
- deletegroup
- status of a repository dump task
- put /repositories/{repository}/settings/gc_rules
- delete group membership
- list repositories
- get group
- delete external principal from user
- add group membership
- getsetupstate
- getpolicy
- perform a login with sts
- getauthcapabilities
- createcredentials
- setupcommprefs
- data lake
- getrepositorymetadata
- create policy
- list tags
- get user
- setbranchprotectionrules
- list users
- getbranchprotectionrules
- deletecredentials
- attach policy to group
- create group
- restoresubmit
slug: lakefs-capability
source_filename: lakefs-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: lakeFS API\n  description: lakeFS HTTP API\n  tags:\n  - Lakefs\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: lakefs\n    baseUri: /api/v1\n    description: lakeFS API HTTP API.\n    authentication:\n      type: basic\n      username: '{{LAKEFS_USERNAME}}'\n      password: '{{LAKEFS_PASSWORD}}'\n    resources:\n    - name: setup-comm-prefs\n      path: /setup_comm_prefs\n      operations:\n      - name: setupcommprefs\n        method: POST\n        description: setup communications preferences\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: setup-lakefs\n      path: /setup_lakefs\n      operations:\n      - name: getsetupstate\n        method: GET\n        description: check if the lakeFS installation is already set up\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: setup\n        method: POST\n        description: setup lakeFS and create a first user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /user\n      operations:\n      - name: getcurrentuser\n        method: GET\n        description: get current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-login\n      path: /auth/login\n      operations:\n      - name: login\n        method: POST\n        description: perform a login\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-external-principal-login\n      path: /auth/external/principal/login\n      operations:\n      - name: externalprincipallogin\n       \
  \ method: POST\n        description: perform a login using an external authenticator\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sts-login\n      path: /sts/login\n      operations:\n      - name: stslogin\n        method: POST\n        description: perform a login with STS\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-capabilities\n      path: /auth/capabilities\n      operations:\n      - name: getauthcapabilities\n        method: GET\n        description: list authentication capabilities supported\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-users\n      path: /auth/users\n      operations:\n      - name: listusers\n        method: GET\n        description: list users\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: create user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-users-userid\n      path: /auth/users/{userId}\n      operations:\n      - name: getuser\n        method: GET\n        description: get user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: delete user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-groups\n      path: /auth/groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: list groups\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: create group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-groups-groupid\n      path: /auth/groups/{groupId}\n      operations:\n      - name: getgroup\n        method: GET\n        description: get group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroup\n        method: DELETE\n        description: delete group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-policies\n      path: /auth/policies\n      operations:\n      - name: listpolicies\n        method: GET\n        description: list policies\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpolicy\n        method: POST\n        description: create policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-policies-policyid\n      path: /auth/policies/{policyId}\n      operations:\n      - name: getpolicy\n        method: GET\n        description: get policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepolicy\n        method: PUT\n        description: update policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepolicy\n        method: DELETE\n        description: delete policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: auth-groups-groupid-members\n      path: /auth/groups/{groupId}/members\n      operations:\n      - name: listgroupmembers\n        method: GET\n        description: list group members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-groups-groupid-members-userid\n      path: /auth/groups/{groupId}/members/{userId}\n      operations:\n      - name: addgroupmembership\n        method: PUT\n        description: add group membership\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroupmembership\n        method: DELETE\n        description: delete group membership\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-users-userid-credentials\n      path: /auth/users/{userId}/credentials\n\
  \      operations:\n      - name: listusercredentials\n        method: GET\n        description: list user credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcredentials\n        method: POST\n        description: create credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-users-userid-credentials-accesskeyid\n      path: /auth/users/{userId}/credentials/{accessKeyId}\n      operations:\n      - name: deletecredentials\n        method: DELETE\n        description: delete credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getcredentials\n        method: GET\n        description: get credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: auth-users-userid-groups\n      path: /auth/users/{userId}/groups\n      operations:\n      - name: listusergroups\n        method: GET\n        description: list user groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-users-userid-policies\n      path: /auth/users/{userId}/policies\n      operations:\n      - name: listuserpolicies\n        method: GET\n        description: list user policies\n        inputParameters:\n        - name: effective\n          in: query\n          type: boolean\n          description: will return all distinct policies attached to the user or any of its groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-users-userid-policies-policyid\n      path: /auth/users/{userId}/policies/{policyId}\n      operations:\n\
  \      - name: attachpolicytouser\n        method: PUT\n        description: attach policy to user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: detachpolicyfromuser\n        method: DELETE\n        description: detach policy from user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-users-userid-external-principals\n      path: /auth/users/{userId}/external/principals\n      operations:\n      - name: createuserexternalprincipal\n        method: POST\n        description: attach external principal to user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuserexternalprincipal\n        method: DELETE\n        description: delete external principal from user\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: auth-users-userid-external-principals-ls\n      path: /auth/users/{userId}/external/principals/ls\n      operations:\n      - name: listuserexternalprincipals\n        method: GET\n        description: list user external policies attached to a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-external-principals\n      path: /auth/external/principals\n      operations:\n      - name: getexternalprincipal\n        method: GET\n        description: describe external principal by id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-groups-groupid-policies\n      path: /auth/groups/{groupId}/policies\n      operations:\n      - name: listgrouppolicies\n        method: GET\n        description: list group policies\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-groups-groupid-policies-policyid\n      path: /auth/groups/{groupId}/policies/{policyId}\n      operations:\n      - name: attachpolicytogroup\n        method: PUT\n        description: attach policy to group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: detachpolicyfromgroup\n        method: DELETE\n        description: detach policy from group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-groups-groupid-acl\n      path: /auth/groups/{groupId}/acl\n      operations:\n      - name: setgroupacl\n        method: POST\n        description: set ACL of group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: getgroupacl\n        method: GET\n        description: get ACL of group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories\n      path: /repositories\n      operations:\n      - name: listrepositories\n        method: GET\n        description: list repositories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrepository\n        method: POST\n        description: create repository\n        inputParameters:\n        - name: bare\n          in: query\n          type: boolean\n          description: If true, create a bare repository with no initial commit and branch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repository\n      path: /repositories/{repository}\n\
  \      operations:\n      - name: getrepository\n        method: GET\n        description: get repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterepository\n        method: DELETE\n        description: delete repository\n        inputParameters:\n        - name: force\n          in: query\n          type: boolean\n          description: Bypass read-only protection and delete the repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repository-metadata\n      path: /repositories/{repository}/metadata\n      operations:\n      - name: getrepositorymetadata\n        method: GET\n        description: get repository metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setrepositorymetadata\n\
  \        method: POST\n        description: set repository metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterepositorymetadata\n        method: DELETE\n        description: delete repository metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repository-settings-gc-rules\n      path: /repositories/{repository}/settings/gc_rules\n      operations:\n      - name: getgcrules\n        method: GET\n        description: get repository GC rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setgcrules\n        method: PUT\n        description: PUT /repositories/{repository}/settings/gc_rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: deletegcrules\n        method: DELETE\n        description: DELETE /repositories/{repository}/settings/gc_rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repository-settings-branch-protecti\n      path: /repositories/{repository}/settings/branch_protection\n      operations:\n      - name: getbranchprotectionrules\n        method: GET\n        description: get branch protection rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setbranchprotectionrules\n        method: PUT\n        description: PUT /repositories/{repository}/settings/branch_protection\n        inputParameters:\n        - name: If-Match\n          in: header\n          type: string\n          description: if provided, the branch protection rules will be updated only if the\
  \ current ETag match the provided\n            value\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repository-refs-dump\n      path: /repositories/{repository}/refs/dump\n      operations:\n      - name: dumprefs\n        method: PUT\n        description: 'Dump repository refs (tags, commits, branches) to object store Deprecated: a new API will introduce\n          long running operations'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repository-refs-restore\n      path: /repositories/{repository}/refs/restore\n      operations:\n      - name: restorerefs\n        method: PUT\n        description: 'Restore repository refs (tags, commits, branches) from object store. Deprecated: a new API will introduce\n          long running operations'\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repository-dump\n      path: /repositories/{repository}/dump\n      operations:\n      - name: dumpsubmit\n        method: POST\n        description: Backup the repository metadata (tags, commits, branches) and save the backup to the object store.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: dumpstatus\n        method: GET\n        description: Status of a repository dump task\n        inputParameters:\n        - name: task_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repository-restore\n      path: /repositories/{repository}/restore\n      operations:\n      - name: restoresubmit\n        method:\
  \ POST\n        description: Restore repository from a dump in the object store\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: restorestatus\n        method: GET\n        description: Status of a restore request\n        inputParameters:\n        - name: task_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories-repository-tags\n      path: /repositories/{repository}/tags\n      operations:\n      - name: listtags\n        method: GET\n        description: list tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lakefs-rest\n    description: REST adapter for lakeFS API.\n    resources:\n\
  \    - path: /setup_comm_prefs\n      name: setupcommprefs\n      operations:\n      - method: POST\n        name: setupcommprefs\n        description: setup communications preferences\n        call: lakefs.setupcommprefs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /setup_lakefs\n      name: getsetupstate\n      operations:\n      - method: GET\n        name: getsetupstate\n        description: check if the lakeFS installation is already set up\n        call: lakefs.getsetupstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /setup_lakefs\n      name: setup\n      operations:\n      - method: POST\n        name: setup\n        description: setup lakeFS and create a first user\n        call: lakefs.setup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user\n      name: getcurrentuser\n      operations:\n      - method: GET\n        name: getcurrentuser\n        description:\
  \ get current user\n        call: lakefs.getcurrentuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/login\n      name: login\n      operations:\n      - method: POST\n        name: login\n        description: perform a login\n        call: lakefs.login\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/external/principal/login\n      name: externalprincipallogin\n      operations:\n      - method: POST\n        name: externalprincipallogin\n        description: perform a login using an external authenticator\n        call: lakefs.externalprincipallogin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sts/login\n      name: stslogin\n      operations:\n      - method: POST\n        name: stslogin\n        description: perform a login with STS\n        call: lakefs.stslogin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /auth/capabilities\n      name: getauthcapabilities\n      operations:\n      - method: GET\n        name: getauthcapabilities\n        description: list authentication capabilities supported\n        call: lakefs.getauthcapabilities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: list users\n        call: lakefs.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: create user\n        call: lakefs.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users/{userId}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: get user\n        call: lakefs.getuser\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users/{userId}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: delete user\n        call: lakefs.deleteuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: list groups\n        call: lakefs.listgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/groups\n      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: create group\n        call: lakefs.creategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/groups/{groupId}\n      name: getgroup\n      operations:\n      - method: GET\n        name: getgroup\n        description:\
  \ get group\n        call: lakefs.getgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/groups/{groupId}\n      name: deletegroup\n      operations:\n      - method: DELETE\n        name: deletegroup\n        description: delete group\n        call: lakefs.deletegroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/policies\n      name: listpolicies\n      operations:\n      - method: GET\n        name: listpolicies\n        description: list policies\n        call: lakefs.listpolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/policies\n      name: createpolicy\n      operations:\n      - method: POST\n        name: createpolicy\n        description: create policy\n        call: lakefs.createpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/policies/{policyId}\n      name: getpolicy\n      operations:\n\
  \      - method: GET\n        name: getpolicy\n        description: get policy\n        call: lakefs.getpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/policies/{policyId}\n      name: updatepolicy\n      operations:\n      - method: PUT\n        name: updatepolicy\n        description: update policy\n        call: lakefs.updatepolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/policies/{policyId}\n      name: deletepolicy\n      operations:\n      - method: DELETE\n        name: deletepolicy\n        description: delete policy\n        call: lakefs.deletepolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/groups/{groupId}/members\n      name: listgroupmembers\n      operations:\n      - method: GET\n        name: listgroupmembers\n        description: list group members\n        call: lakefs.listgroupmembers\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /auth/groups/{groupId}/members/{userId}\n      name: addgroupmembership\n      operations:\n      - method: PUT\n        name: addgroupmembership\n        description: add group membership\n        call: lakefs.addgroupmembership\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/groups/{groupId}/members/{userId}\n      name: deletegroupmembership\n      operations:\n      - method: DELETE\n        name: deletegroupmembership\n        description: delete group membership\n        call: lakefs.deletegroupmembership\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users/{userId}/credentials\n      name: listusercredentials\n      operations:\n      - method: GET\n        name: listusercredentials\n        description: list user credentials\n        call: lakefs.listusercredentials\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /auth/users/{userId}/credentials\n      name: createcredentials\n      operations:\n      - method: POST\n        name: createcredentials\n        description: create credentials\n        call: lakefs.createcredentials\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users/{userId}/credentials/{accessKeyId}\n      name: deletecredentials\n      operations:\n      - method: DELETE\n        name: deletecredentials\n        description: delete credentials\n        call: lakefs.deletecredentials\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users/{userId}/credentials/{accessKeyId}\n      name: getcredentials\n      operations:\n      - method: GET\n        name: getcredentials\n        description: get credentials\n        call: lakefs.getcredentials\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users/{userId}/groups\n      name: listusergroups\n\
  \      operations:\n      - method: GET\n        name: listusergroups\n        description: list user groups\n        call: lakefs.listusergroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users/{userId}/policies\n      name: listuserpolicies\n      operations:\n      - method: GET\n        name: listuserpolicies\n        description: list user policies\n        call: lakefs.listuserpolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users/{userId}/policies/{policyId}\n      name: attachpolicytouser\n      operations:\n      - method: PUT\n        name: attachpolicytouser\n        description: attach policy to user\n        call: lakefs.attachpolicytouser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users/{userId}/policies/{policyId}\n      name: detachpolicyfromuser\n      operations:\n      - method: DELETE\n        name: detachpolicyfromuser\n\
  \        description: detach policy from user\n        call: lakefs.detachpolicyfromuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users/{userId}/external/principals\n      name: createuserexternalprincipal\n      operations:\n      - method: POST\n        name: createuserexternalprincipal\n        description: attach external principal to user\n        call: lakefs.createuserexternalprincipal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users/{userId}/external/principals\n      name: deleteuserexternalprincipal\n      operations:\n      - method: DELETE\n        name: deleteuserexternalprincipal\n        description: delete external principal from user\n        call: lakefs.deleteuserexternalprincipal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/users/{userId}/external/principals/ls\n      name: listuserexternalprincipals\n      operations:\n\
  \      - method: GET\n        name: listuserexternalprincipals\n        description: list user external policies attached to a user\n        call: lakefs.listuserexternalprincipals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/external/principals\n      name: getexternalprincipal\n      operations:\n      - method: GET\n        name: getexternalprincipal\n        description: describe external principal by id\n        call: lakefs.getexternalprincipal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/groups/{groupId}/policies\n      name: listgrouppolicies\n      operations:\n      - method: GET\n        name: listgrouppolicies\n        description: list group policies\n        call: lakefs.listgrouppolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/groups/{groupId}/policies/{policyId}\n      name: attachpolicytogroup\n      operations:\n      - method:\
  \ PUT\n        name: attachpolicytogroup\n        description: attach policy to group\n        call: lakefs.attachpolicytogroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/groups/{groupId}/policies/{policyId}\n      name: detachpolicyfromgroup\n      operations:\n      - method: DELETE\n        name: detachpolicyfromgroup\n        description: detach policy from group\n        call: lakefs.detachpolicyfromgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/groups/{groupId}/acl\n      name: setgroupacl\n      operations:\n      - method: POST\n        name: setgroupacl\n        description: set ACL of group\n        call: lakefs.setgroupacl\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /auth/groups/{groupId}/acl\n      name: getgroupacl\n      operations:\n      - method: GET\n        name: getgroupacl\n        description: get ACL of group\n        call:\
  \ lakefs.getgroupacl\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories\n      name: listrepositories\n      operations:\n      - method: GET\n        name: listrepositories\n        description: list repositories\n        call: lakefs.listrepositories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories\n      name: createrepository\n      operations:\n      - method: POST\n        name: createrepository\n        description: create repository\n        call: lakefs.createrepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repository}\n      name: getrepository\n      operations:\n      - method: GET\n        name: getrepository\n        description: get repository\n        call: lakefs.getrepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repository}\n      name: deleterepository\n\
  \      operations:\n      - method: DELETE\n        name: deleterepository\n        description: delete repository\n        call: lakefs.deleterepository\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repository}/metadata\n      name: getrepositorymetadata\n      operations:\n      - method: GET\n        name: getrepositorymetadata\n        description: get repository metadata\n        call: lakefs.getrepositorymetadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repository}/metadata\n      name: setrepositorymetadata\n      operations:\n      - method: POST\n        name: setrepositorymetadata\n        description: set repository metadata\n        call: lakefs.setrepositorymetadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repository}/metadata\n      name: deleterepositorymetadata\n      operations:\n      - method:\
  \ DELETE\n        name: deleterepositorymetadata\n        description: delete repository metadata\n        call: lakefs.deleterepositorymetadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repository}/settings/gc_rules\n      name: getgcrules\n      operations:\n      - method: GET\n        name: getgcrules\n        description: get repository GC rules\n        call: lakefs.getgcrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /repositories/{repository}/settings/gc_rules\n      name: setgcrules\n      operations:\n      - method: PUT\n        name: setgcrules\n        description: PUT /repositories/{repository}/settings/gc_rules\n        call: lakefs.setgcrules\n        outputParameters:\n        - ty\n\n# --- truncated at 32 KB (51 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/lakefs/refs/heads/main/capabilities/lakefs-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lakefs/refs/heads/main/capabilities/lakefs-capability.yaml
tags:
- Lakefs
- API
tools:
- description: setup communications preferences
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setupcommprefs
- description: check if the lakeFS installation is already set up
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsetupstate
- description: setup lakeFS and create a first user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setup
- description: get current user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentuser
- description: perform a login
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login
- description: perform a login using an external authenticator
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: externalprincipallogin
- description: perform a login with STS
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stslogin
- description: list authentication capabilities supported
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthcapabilities
- description: list users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: create user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: get user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: delete user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: list groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: create group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: get group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: delete group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: list policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpolicies
- description: create policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpolicy
- description: get policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpolicy
- description: update policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepolicy
- description: delete policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepolicy
- description: list group members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroupmembers
- description: add group membership
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: addgroupmembership
- description: delete group membership
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroupmembership
- description: list user credentials
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusercredentials
- description: create credentials
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcredentials
- description: delete credentials
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecredentials
- description: get credentials
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcredentials
- description: list user groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusergroups
- description: list user policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuserpolicies
- description: attach policy to user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: attachpolicytouser
- description: detach policy from user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: detachpolicyfromuser
- description: attach external principal to user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuserexternalprincipal
- description: delete external principal from user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuserexternalprincipal
- description: list user external policies attached to a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuserexternalprincipals
- description: describe external principal by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexternalprincipal
- description: list group policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgrouppolicies
- description: attach policy to group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: attachpolicytogroup
- description: detach policy from group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: detachpolicyfromgroup
- description: set ACL of group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setgroupacl
- description: get ACL of group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupacl
- description: list repositories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrepositories
- description: create repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrepository
- description: get repository
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrepository
- description: delete repository
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterepository
- description: get repository metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrepositorymetadata
- description: set repository metadata
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setrepositorymetadata
- description: delete repository metadata
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterepositorymetadata
- description: get repository GC rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgcrules
- description: PUT /repositories/{repository}/settings/gc_rules
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setgcrules
- description: DELETE /repositories/{repository}/settings/gc_rules
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegcrules
- description: get branch protection rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbranchprotectionrules
- description: PUT /repositories/{repository}/settings/branch_protection
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: setbranchprotectionrules
- description: 'Dump repository refs (tags, commits, branches) to object store Deprecated: a new API will introduce long running operations'
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: dumprefs
- description: 'Restore repository refs (tags, commits, branches) from object store. Deprecated: a new API will introduce long running operations'
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: restorerefs
- description: Backup the repository metadata (tags, commits, branches) and save the backup to the object store.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: dumpsubmit
- description: Status of a repository dump task
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: dumpstatus
- description: Restore repository from a dump in the object store
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restoresubmit
- description: Status of a restore request
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: restorestatus
- description: list tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtags
---
