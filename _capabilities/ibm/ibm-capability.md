---
categories: []
consumed_apis: []
description: The IBM Cloud Identity and Access Management (IAM) API enables you to manage IAM access tokens, API keys, service IDs, trusted profiles, and access policies. Use this API to authenticate identities, authorize access to IBM Cloud resources, and manage the full lifecycle of identity and policy objects within your IBM Cloud account.
layout: capability
name: IBM Cloud IAM API
operations:
- description: Create an IAM access token
  method: POST
  name: createaccesstoken
  path: /identity/token
- description: List API keys
  method: GET
  name: listapikeys
  path: /v1/apikeys
- description: Create an API key
  method: POST
  name: createapikey
  path: /v1/apikeys
- description: Get API key details by value
  method: GET
  name: getapikeysdetails
  path: /v1/apikeys/details
- description: Get an API key
  method: GET
  name: getapikey
  path: /v1/apikeys/{id}
- description: Update an API key
  method: PUT
  name: updateapikey
  path: /v1/apikeys/{id}
- description: Delete an API key
  method: DELETE
  name: deleteapikey
  path: /v1/apikeys/{id}
- description: Lock an API key
  method: POST
  name: lockapikey
  path: /v1/apikeys/{id}/lock
- description: Unlock an API key
  method: DELETE
  name: unlockapikey
  path: /v1/apikeys/{id}/lock
- description: Disable an API key
  method: POST
  name: disableapikey
  path: /v1/apikeys/{id}/disable
- description: Enable an API key
  method: DELETE
  name: enableapikey
  path: /v1/apikeys/{id}/disable
- description: List service IDs
  method: GET
  name: listserviceids
  path: /v1/serviceids/
- description: Create a service ID
  method: POST
  name: createserviceid
  path: /v1/serviceids/
- description: Get a service ID
  method: GET
  name: getserviceid
  path: /v1/serviceids/{id}
- description: Update a service ID
  method: PUT
  name: updateserviceid
  path: /v1/serviceids/{id}
- description: Delete a service ID
  method: DELETE
  name: deleteserviceid
  path: /v1/serviceids/{id}
- description: Lock a service ID
  method: POST
  name: lockserviceid
  path: /v1/serviceids/{id}/lock
- description: Unlock a service ID
  method: DELETE
  name: unlockserviceid
  path: /v1/serviceids/{id}/lock
- description: List trusted profiles
  method: GET
  name: listprofiles
  path: /v1/profiles
- description: Create a trusted profile
  method: POST
  name: createprofile
  path: /v1/profiles
- description: Get a trusted profile
  method: GET
  name: getprofile
  path: /v1/profiles/{profile-id}
- description: Update a trusted profile
  method: PUT
  name: updateprofile
  path: /v1/profiles/{profile-id}
- description: Delete a trusted profile
  method: DELETE
  name: deleteprofile
  path: /v1/profiles/{profile-id}
- description: List claim rules for a trusted profile
  method: GET
  name: listclaimrules
  path: /v1/profiles/{profile-id}/rules
- description: Create a claim rule
  method: POST
  name: createclaimrule
  path: /v1/profiles/{profile-id}/rules
- description: Get a claim rule
  method: GET
  name: getclaimrule
  path: /v1/profiles/{profile-id}/rules/{rule-id}
- description: Update a claim rule
  method: PUT
  name: updateclaimrule
  path: /v1/profiles/{profile-id}/rules/{rule-id}
- description: Delete a claim rule
  method: DELETE
  name: deleteclaimrule
  path: /v1/profiles/{profile-id}/rules/{rule-id}
- description: List access policies
  method: GET
  name: listpolicies
  path: /v1/policies
- description: Create an access policy
  method: POST
  name: createpolicy
  path: /v1/policies
- description: Get an access policy
  method: GET
  name: getpolicy
  path: /v1/policies/{policy_id}
- description: Replace an access policy
  method: PUT
  name: replacepolicy
  path: /v1/policies/{policy_id}
- description: Delete an access policy
  method: DELETE
  name: deletepolicy
  path: /v1/policies/{policy_id}
- description: Update policy state
  method: PATCH
  name: updatepolicystate
  path: /v1/policies/{policy_id}
- description: List IAM roles
  method: GET
  name: listroles
  path: /v2/roles
- description: Create a custom role
  method: POST
  name: createrole
  path: /v2/roles
- description: Get a role
  method: GET
  name: getrole
  path: /v2/roles/{role_id}
- description: Replace a custom role
  method: PUT
  name: replacerole
  path: /v2/roles/{role_id}
- description: Delete a custom role
  method: DELETE
  name: deleterole
  path: /v2/roles/{role_id}
personas: []
provider_name: IBM
provider_slug: ibm
search_terms:
- containers
- create an iam access token
- api
- delete a service id
- unlockapikey
- deletepolicy
- api management
- watson
- getpolicy
- updatepolicystate
- list iam roles
- lock an api key
- create an access policy
- machine learning
- createclaimrule
- getrole
- lock a service id
- updateserviceid
- get an api key
- getapikey
- enableapikey
- data governance
- update a trusted profile
- createaccesstoken
- databases
- createrole
- delete a custom role
- get api key details by value
- list trusted profiles
- listpolicies
- createserviceid
- deleteprofile
- create a trusted profile
- artificial intelligence
- listserviceids
- create a service id
- serverless
- listapikeys
- delete an api key
- update policy state
- replacepolicy
- enterprise
- updateapikey
- storage
- updateprofile
- update a service id
- security
- replace a custom role
- get a service id
- networking
- get a role
- disableapikey
- getclaimrule
- create a custom role
- billing
- update an api key
- deleteserviceid
- getserviceid
- list claim rules for a trusted profile
- watsonx
- cloud computing
- listprofiles
- infrastructure
- deleteapikey
- replacerole
- getapikeysdetails
- update a claim rule
- observability
- get a claim rule
- getprofile
- generative ai
- list access policies
- hybrid cloud
- createapikey
- delete a claim rule
- delete an access policy
- listclaimrules
- devops
- get an access policy
- unlock an api key
- ibm
- create a claim rule
- createprofile
- unlockserviceid
- deleterole
- disable an api key
- enable an api key
- list service ids
- create an api key
- createpolicy
- list api keys
- updateclaimrule
- get a trusted profile
- listroles
- unlock a service id
- deleteclaimrule
- lockserviceid
- delete a trusted profile
- lockapikey
- replace an access policy
slug: ibm-capability
source_filename: ibm-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: IBM Cloud IAM API\n  description: The IBM Cloud Identity and Access Management (IAM) API enables you to manage IAM access tokens, API keys, service\n    IDs, trusted profiles, and access policies. Use this API to authenticate identities, authorize access to IBM Cloud resources,\n    and manage the full lifecycle of identity and policy objects within your IBM Cloud account.\n  tags:\n  - Ibm\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ibm\n    baseUri: https://iam.cloud.ibm.com\n    description: IBM Cloud IAM API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{IBM_TOKEN}}'\n    resources:\n    - name: identity-token\n      path: /identity/token\n      operations:\n      - name: createaccesstoken\n        method: POST\n        description: Create an IAM access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: v1-apikeys\n      path: /v1/apikeys\n      operations:\n      - name: listapikeys\n        method: GET\n        description: List API keys\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          description: The account ID of the API keys to query.\n        - name: iam_id\n          in: query\n          type: string\n          description: The IAM ID associated with the API keys.\n        - name: pagesize\n          in: query\n          type: integer\n          description: Number of results per page.\n        - name: pagetoken\n          in: query\n          type: string\n          description: Page token from a previous request for pagination.\n        - name: scope\n          in: query\n          type: string\n          description: Scope of the query, either account or iam_id.\n        - name: type\n          in: query\n          type: string\n          description: Filter\
  \ by API key type.\n        - name: sort\n          in: query\n          type: string\n          description: Field to sort by.\n        - name: order\n          in: query\n          type: string\n          description: Sort order.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapikey\n        method: POST\n        description: Create an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-apikeys-details\n      path: /v1/apikeys/details\n      operations:\n      - name: getapikeysdetails\n        method: GET\n        description: Get API key details by value\n        inputParameters:\n        - name: IAM-ApiKey\n          in: header\n          type: string\n          description: The API key value to look up.\n        - name: include_history\n          in: query\n          type: boolean\n\
  \          description: Include activity history of the API key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-apikeys-id\n      path: /v1/apikeys/{id}\n      operations:\n      - name: getapikey\n        method: GET\n        description: Get an API key\n        inputParameters:\n        - name: include_history\n          in: query\n          type: boolean\n          description: Include the history of the API key.\n        - name: include_activity\n          in: query\n          type: boolean\n          description: Include the activity of the API key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapikey\n        method: PUT\n        description: Update an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: deleteapikey\n        method: DELETE\n        description: Delete an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-apikeys-id-lock\n      path: /v1/apikeys/{id}/lock\n      operations:\n      - name: lockapikey\n        method: POST\n        description: Lock an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unlockapikey\n        method: DELETE\n        description: Unlock an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-apikeys-id-disable\n      path: /v1/apikeys/{id}/disable\n      operations:\n      - name: disableapikey\n        method: POST\n        description: Disable an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: enableapikey\n        method: DELETE\n        description: Enable an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-serviceids\n      path: /v1/serviceids/\n      operations:\n      - name: listserviceids\n        method: GET\n        description: List service IDs\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          description: The account ID of the service IDs to query.\n        - name: name\n          in: query\n          type: string\n          description: Filter service IDs by name.\n        - name: pagesize\n          in: query\n          type: integer\n          description: Number of results per page.\n        - name: pagetoken\n          in: query\n          type: string\n          description: Page token from a previous request for pagination.\n        - name:\
  \ sort\n          in: query\n          type: string\n          description: Field to sort results by.\n        - name: order\n          in: query\n          type: string\n          description: Sort order.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createserviceid\n        method: POST\n        description: Create a service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-serviceids-id\n      path: /v1/serviceids/{id}\n      operations:\n      - name: getserviceid\n        method: GET\n        description: Get a service ID\n        inputParameters:\n        - name: include_history\n          in: query\n          type: boolean\n          description: Include the history of the service ID.\n        - name: include_activity\n          in: query\n          type: boolean\n          description: Include\
  \ the activity of the service ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateserviceid\n        method: PUT\n        description: Update a service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteserviceid\n        method: DELETE\n        description: Delete a service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-serviceids-id-lock\n      path: /v1/serviceids/{id}/lock\n      operations:\n      - name: lockserviceid\n        method: POST\n        description: Lock a service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unlockserviceid\n        method: DELETE\n        description: Unlock\
  \ a service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-profiles\n      path: /v1/profiles\n      operations:\n      - name: listprofiles\n        method: GET\n        description: List trusted profiles\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: true\n          description: The account ID to list trusted profiles for.\n        - name: name\n          in: query\n          type: string\n          description: Filter profiles by name.\n        - name: pagesize\n          in: query\n          type: integer\n          description: Number of results per page.\n        - name: pagetoken\n          in: query\n          type: string\n          description: Page token from a previous request.\n        - name: sort\n          in: query\n          type: string\n          description: Field to sort by.\n        - name: order\n\
  \          in: query\n          type: string\n          description: Sort order.\n        - name: include_history\n          in: query\n          type: boolean\n          description: Include the history of the profiles.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createprofile\n        method: POST\n        description: Create a trusted profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-profiles-profile-id\n      path: /v1/profiles/{profile-id}\n      operations:\n      - name: getprofile\n        method: GET\n        description: Get a trusted profile\n        inputParameters:\n        - name: include_activity\n          in: query\n          type: boolean\n          description: Include the activity of the profile.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: updateprofile\n        method: PUT\n        description: Update a trusted profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteprofile\n        method: DELETE\n        description: Delete a trusted profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-profiles-profile-id-rules\n      path: /v1/profiles/{profile-id}/rules\n      operations:\n      - name: listclaimrules\n        method: GET\n        description: List claim rules for a trusted profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createclaimrule\n        method: POST\n        description: Create a claim rule\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v1-profiles-profile-id-rules-rule-id\n      path: /v1/profiles/{profile-id}/rules/{rule-id}\n      operations:\n      - name: getclaimrule\n        method: GET\n        description: Get a claim rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateclaimrule\n        method: PUT\n        description: Update a claim rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteclaimrule\n        method: DELETE\n        description: Delete a claim rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-policies\n      path: /v1/policies\n      operations:\n      - name: listpolicies\n        method: GET\n        description: List access\
  \ policies\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: true\n          description: The account ID to list policies for.\n        - name: iam_id\n          in: query\n          type: string\n          description: Filter by the IAM ID of the subject.\n        - name: access_group_id\n          in: query\n          type: string\n          description: Filter by access group ID.\n        - name: type\n          in: query\n          type: string\n          description: Filter by policy type.\n        - name: service_type\n          in: query\n          type: string\n          description: Filter by service type.\n        - name: state\n          in: query\n          type: string\n          description: Filter by policy state.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of policies to return.\n        - name: start\n          in: query\n          type:\
  \ string\n          description: Pagination start token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpolicy\n        method: POST\n        description: Create an access policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-policies-policy-id\n      path: /v1/policies/{policy_id}\n      operations:\n      - name: getpolicy\n        method: GET\n        description: Get an access policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacepolicy\n        method: PUT\n        description: Replace an access policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepolicy\n        method: DELETE\n       \
  \ description: Delete an access policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepolicystate\n        method: PATCH\n        description: Update policy state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-roles\n      path: /v2/roles\n      operations:\n      - name: listroles\n        method: GET\n        description: List IAM roles\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          description: The account ID to list custom roles for.\n        - name: service_name\n          in: query\n          type: string\n          description: Filter roles by the service they apply to.\n        - name: source_service_name\n          in: query\n          type: string\n          description: Filter by the source service name for authorization\
  \ policies.\n        - name: policy_type\n          in: query\n          type: string\n          description: Filter by policy type.\n        - name: service_group_id\n          in: query\n          type: string\n          description: Filter by the service group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrole\n        method: POST\n        description: Create a custom role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-roles-role-id\n      path: /v2/roles/{role_id}\n      operations:\n      - name: getrole\n        method: GET\n        description: Get a role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacerole\n        method: PUT\n        description: Replace a custom role\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterole\n        method: DELETE\n        description: Delete a custom role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ibm-rest\n    description: REST adapter for IBM Cloud IAM API.\n    resources:\n    - path: /identity/token\n      name: createaccesstoken\n      operations:\n      - method: POST\n        name: createaccesstoken\n        description: Create an IAM access token\n        call: ibm.createaccesstoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apikeys\n      name: listapikeys\n      operations:\n      - method: GET\n        name: listapikeys\n        description: List API keys\n        call: ibm.listapikeys\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/apikeys\n      name: createapikey\n      operations:\n      - method: POST\n        name: createapikey\n        description: Create an API key\n        call: ibm.createapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apikeys/details\n      name: getapikeysdetails\n      operations:\n      - method: GET\n        name: getapikeysdetails\n        description: Get API key details by value\n        call: ibm.getapikeysdetails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apikeys/{id}\n      name: getapikey\n      operations:\n      - method: GET\n        name: getapikey\n        description: Get an API key\n        call: ibm.getapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apikeys/{id}\n      name: updateapikey\n      operations:\n      - method: PUT\n        name: updateapikey\n        description:\
  \ Update an API key\n        call: ibm.updateapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apikeys/{id}\n      name: deleteapikey\n      operations:\n      - method: DELETE\n        name: deleteapikey\n        description: Delete an API key\n        call: ibm.deleteapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apikeys/{id}/lock\n      name: lockapikey\n      operations:\n      - method: POST\n        name: lockapikey\n        description: Lock an API key\n        call: ibm.lockapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apikeys/{id}/lock\n      name: unlockapikey\n      operations:\n      - method: DELETE\n        name: unlockapikey\n        description: Unlock an API key\n        call: ibm.unlockapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apikeys/{id}/disable\n      name: disableapikey\n\
  \      operations:\n      - method: POST\n        name: disableapikey\n        description: Disable an API key\n        call: ibm.disableapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apikeys/{id}/disable\n      name: enableapikey\n      operations:\n      - method: DELETE\n        name: enableapikey\n        description: Enable an API key\n        call: ibm.enableapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/serviceids/\n      name: listserviceids\n      operations:\n      - method: GET\n        name: listserviceids\n        description: List service IDs\n        call: ibm.listserviceids\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/serviceids/\n      name: createserviceid\n      operations:\n      - method: POST\n        name: createserviceid\n        description: Create a service ID\n        call: ibm.createserviceid\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/serviceids/{id}\n      name: getserviceid\n      operations:\n      - method: GET\n        name: getserviceid\n        description: Get a service ID\n        call: ibm.getserviceid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/serviceids/{id}\n      name: updateserviceid\n      operations:\n      - method: PUT\n        name: updateserviceid\n        description: Update a service ID\n        call: ibm.updateserviceid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/serviceids/{id}\n      name: deleteserviceid\n      operations:\n      - method: DELETE\n        name: deleteserviceid\n        description: Delete a service ID\n        call: ibm.deleteserviceid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/serviceids/{id}/lock\n      name: lockserviceid\n      operations:\n      - method: POST\n  \
  \      name: lockserviceid\n        description: Lock a service ID\n        call: ibm.lockserviceid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/serviceids/{id}/lock\n      name: unlockserviceid\n      operations:\n      - method: DELETE\n        name: unlockserviceid\n        description: Unlock a service ID\n        call: ibm.unlockserviceid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles\n      name: listprofiles\n      operations:\n      - method: GET\n        name: listprofiles\n        description: List trusted profiles\n        call: ibm.listprofiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles\n      name: createprofile\n      operations:\n      - method: POST\n        name: createprofile\n        description: Create a trusted profile\n        call: ibm.createprofile\n        outputParameters:\n        - type: object\n        \
  \  mapping: $.\n    - path: /v1/profiles/{profile-id}\n      name: getprofile\n      operations:\n      - method: GET\n        name: getprofile\n        description: Get a trusted profile\n        call: ibm.getprofile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles/{profile-id}\n      name: updateprofile\n      operations:\n      - method: PUT\n        name: updateprofile\n        description: Update a trusted profile\n        call: ibm.updateprofile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles/{profile-id}\n      name: deleteprofile\n      operations:\n      - method: DELETE\n        name: deleteprofile\n        description: Delete a trusted profile\n        call: ibm.deleteprofile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles/{profile-id}/rules\n      name: listclaimrules\n      operations:\n      - method: GET\n        name:\
  \ listclaimrules\n        description: List claim rules for a trusted profile\n        call: ibm.listclaimrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles/{profile-id}/rules\n      name: createclaimrule\n      operations:\n      - method: POST\n        name: createclaimrule\n        description: Create a claim rule\n        call: ibm.createclaimrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles/{profile-id}/rules/{rule-id}\n      name: getclaimrule\n      operations:\n      - method: GET\n        name: getclaimrule\n        description: Get a claim rule\n        call: ibm.getclaimrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles/{profile-id}/rules/{rule-id}\n      name: updateclaimrule\n      operations:\n      - method: PUT\n        name: updateclaimrule\n        description: Update a claim rule\n        call: ibm.updateclaimrule\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles/{profile-id}/rules/{rule-id}\n      name: deleteclaimrule\n      operations:\n      - method: DELETE\n        name: deleteclaimrule\n        description: Delete a claim rule\n        call: ibm.deleteclaimrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies\n      name: listpolicies\n      operations:\n      - method: GET\n        name: listpolicies\n        description: List access policies\n        call: ibm.listpolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies\n      name: createpolicy\n      operations:\n      - method: POST\n        name: createpolicy\n        description: Create an access policy\n        call: ibm.createpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies/{policy_id}\n      name: getpolicy\n      operations:\n\
  \      - method: GET\n        name: getpolicy\n        description: Get an access policy\n        call: ibm.getpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies/{policy_id}\n      name: replacepolicy\n      operations:\n      - method: PUT\n        name: replacepolicy\n        description: Replace an access policy\n        call: ibm.replacepolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies/{policy_id}\n      name: deletepolicy\n      operations:\n      - method: DELETE\n        name: deletepolicy\n        description: Delete an access policy\n        call: ibm.deletepolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies/{policy_id}\n      name: updatepolicystate\n      operations:\n      - method: PATCH\n        name: updatepolicystate\n        description: Update policy state\n        call: ibm.updatepolicystate\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v2/roles\n      name: listroles\n      operations:\n      - method: GET\n        name: listroles\n        description: List IAM roles\n        call: ibm.listroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/roles\n      name: createrole\n      operations:\n      - method: POST\n        name: createrole\n        description: Create a custom role\n        call: ibm.createrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/roles/{role_id}\n      name: getrole\n      operations:\n      - method: GET\n        name: getrole\n        description: Get a role\n        call: ibm.getrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/roles/{role_id}\n      name: replacerole\n      operations:\n      - method: PUT\n        name: replacerole\n        description: Replace a custom role\n        call: ibm.replacerole\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/roles/{role_id}\n      name: deleterole\n      operations:\n      - method: DELETE\n        name: deleterole\n        description: Delete a custom role\n        call: ibm.deleterole\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ibm-mcp\n    transport: http\n    description: MCP adapter for IBM Cloud IAM API for AI agent use.\n    tools:\n    - name: createaccesstoken\n      description: Create an IAM access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibm.createaccesstoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapikeys\n      description: List API keys\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm.listapikeys\n      with:\n        account_id: tools.account_id\n\
  \        iam_id: tools.iam_id\n        pagesize: tools.pagesize\n        pagetoken: tools.pagetoken\n        scope: tools.scope\n        type: tools.type\n        sort: tools.sort\n        order: tools.order\n      inputParameters:\n      - name: account_id\n        type: string\n        description: The account ID of the API keys to query.\n      - name: iam_id\n        type: string\n        description: The IAM ID associated with the API keys.\n      - name: pagesize\n        type: integer\n        description: Number of results per page.\n      - name: pagetoken\n        type: string\n        description: Page token from a previous request for pagination.\n      - name: scope\n        type: string\n        description: Scope of the query, either account or iam_id.\n      - name: type\n        type: string\n        description: Filter by API key type.\n      - name: sort\n        type: string\n        description: Field to sort by.\n      - name: order\n        type: string\n       \
  \ description: Sort order.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapikey\n      description: Create an API key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibm.createapikey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapikeysdetails\n      description: Get API key details by value\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm.getapikeysdetails\n      with:\n        include_history: tools.include_history\n      inputParameters:\n      - name: include_history\n        type: boolean\n        description: Include activity history of the API key.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapikey\n      description: Get an API key\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm.getapikey\n\
  \      with:\n        include_history: tools.include_history\n        include_activity: tools.include_activity\n      inputParameters:\n      - name: include_history\n        type: boolean\n        description: Include the history of the API key.\n      - name: include_activity\n        type: boolean\n        description: Include the activity of the API key.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapikey\n      description: Update an API key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ibm.updateapikey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteapikey\n      description: Delete an API key\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ibm.deleteapikey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lockapikey\n      description: Lock an API key\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibm.lockapikey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unlockapikey\n      description: Unlock an API key\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ibm.unlockapikey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disableapikey\n      description: Disable an API key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibm.disableapikey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enableapikey\n      description: Enable an API key\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ibm.enableapikey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listserviceids\n      description:\
  \ List service IDs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm.listserviceids\n      with:\n        account_id: tools.account_id\n        name: tools.name\n        pagesize: tools.pagesize\n        pagetoken: tools.pagetoken\n        sort: tools.sort\n        order: tools.order\n      inputParameters:\n      - name: account_id\n        type: string\n        description: The account ID of the service IDs to query.\n      - name: name\n        type: string\n        description: Filter service IDs by name.\n      - name: pagesize\n        type: integer\n        description: Number of results per page.\n      - name: pagetoken\n        type: string\n        description: Page token from a previous request for pagination.\n      - name: sort\n        type: string\n        description: Field to sort results by.\n      - name: order\n        type: string\n        description: Sort order.\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: createserviceid\n      description: Create a service ID\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ibm.createserviceid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getserviceid\n      description: Get a service ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ibm.getserviceid\n      with:\n        include_history: tools.include_history\n        include_activity: tools.include_activity\n      inputParameters:\n      - name: include_history\n        type: boolean\n        description: Include the history of the service ID.\n      - name: include_activity\n        type: boolean\n        description: Include the activity of the service ID.\n      outputParameters:\n      - type: object\n  \n\n# --- truncated at 32 KB (41 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/ibm/refs/heads/main/capabilities/ibm-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ibm/refs/heads/main/capabilities/ibm-capability.yaml
tags:
- Ibm
- API
tools:
- description: Create an IAM access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaccesstoken
- description: List API keys
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
- description: Get API key details by value
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapikeysdetails
- description: Get an API key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapikey
- description: Update an API key
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapikey
- description: Delete an API key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapikey
- description: Lock an API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lockapikey
- description: Unlock an API key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: unlockapikey
- description: Disable an API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: disableapikey
- description: Enable an API key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: enableapikey
- description: List service IDs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listserviceids
- description: Create a service ID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createserviceid
- description: Get a service ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getserviceid
- description: Update a service ID
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateserviceid
- description: Delete a service ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteserviceid
- description: Lock a service ID
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lockserviceid
- description: Unlock a service ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: unlockserviceid
- description: List trusted profiles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprofiles
- description: Create a trusted profile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprofile
- description: Get a trusted profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprofile
- description: Update a trusted profile
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateprofile
- description: Delete a trusted profile
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprofile
- description: List claim rules for a trusted profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclaimrules
- description: Create a claim rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createclaimrule
- description: Get a claim rule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclaimrule
- description: Update a claim rule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateclaimrule
- description: Delete a claim rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteclaimrule
- description: List access policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpolicies
- description: Create an access policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpolicy
- description: Get an access policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpolicy
- description: Replace an access policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacepolicy
- description: Delete an access policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepolicy
- description: Update policy state
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatepolicystate
- description: List IAM roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroles
- description: Create a custom role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrole
- description: Get a role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrole
- description: Replace a custom role
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacerole
- description: Delete a custom role
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterole
---
