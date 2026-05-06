---
categories: []
consumed_apis: []
description: 'API references for Logto services. Note: The documentation is for Logto Cloud. If you are using Logto OSS, please refer to the response of `/api/swagger.json` endpoint on your Logto instance.'
layout: capability
name: Logto API references
operations:
- description: Get applications
  method: GET
  name: listapplications
  path: /api/applications
- description: Create an application
  method: POST
  name: createapplication
  path: /api/applications
- description: Get application
  method: GET
  name: getapplication
  path: /api/applications/{id}
- description: Update application
  method: PATCH
  name: updateapplication
  path: /api/applications/{id}
- description: Delete application
  method: DELETE
  name: deleteapplication
  path: /api/applications/{id}
- description: Update application custom data
  method: PATCH
  name: updateapplicationcustomdata
  path: /api/applications/{applicationId}/custom-data
- description: Get application API resource roles
  method: GET
  name: listapplicationroles
  path: /api/applications/{applicationId}/roles
- description: Assign API resource roles to application
  method: POST
  name: assignapplicationroles
  path: /api/applications/{applicationId}/roles
- description: Update API resource roles for application
  method: PUT
  name: replaceapplicationroles
  path: /api/applications/{applicationId}/roles
- description: Remove a API resource role from application
  method: DELETE
  name: deleteapplicationrole
  path: /api/applications/{applicationId}/roles/{roleId}
- description: Get application custom domains.
  method: GET
  name: listapplicationprotectedappmetadatacustomdomains
  path: /api/applications/{id}/protected-app-metadata/custom-domains
- description: Add a custom domain to the application.
  method: POST
  name: createapplicationprotectedappmetadatacustomdomai
  path: /api/applications/{id}/protected-app-metadata/custom-domains
- description: Remove custom domain.
  method: DELETE
  name: deleteapplicationprotectedappmetadatacustomdomai
  path: /api/applications/{id}/protected-app-metadata/custom-domains/{domain}
- description: Get application organizations
  method: GET
  name: listapplicationorganizations
  path: /api/applications/{id}/organizations
- description: Delete application legacy secret
  method: DELETE
  name: deleteapplicationlegacysecret
  path: /api/applications/{id}/legacy-secret
- description: Get application secrets
  method: GET
  name: listapplicationsecrets
  path: /api/applications/{id}/secrets
- description: Add application secret
  method: POST
  name: createapplicationsecret
  path: /api/applications/{id}/secrets
- description: Delete application secret
  method: DELETE
  name: deleteapplicationsecret
  path: /api/applications/{id}/secrets/{name}
- description: Update application secret
  method: PATCH
  name: updateapplicationsecret
  path: /api/applications/{id}/secrets/{name}
- description: Assign user consent scopes to application.
  method: POST
  name: createapplicationuserconsentscope
  path: /api/applications/{applicationId}/user-consent-scopes
- description: List all the user consent scopes of an application.
  method: GET
  name: listapplicationuserconsentscopes
  path: /api/applications/{applicationId}/user-consent-scopes
- description: Remove user consent scope from application.
  method: DELETE
  name: deleteapplicationuserconsentscope
  path: /api/applications/{applicationId}/user-consent-scopes/{scopeType}/{scopeId}
- description: Update application level sign-in experience
  method: PUT
  name: replaceapplicationsigninexperience
  path: /api/applications/{applicationId}/sign-in-experience
- description: Get the application level sign-in experience
  method: GET
  name: getapplicationsigninexperience
  path: /api/applications/{applicationId}/sign-in-experience
- description: List all the user consented organizations of a application.
  method: GET
  name: listapplicationuserconsentorganizations
  path: /api/applications/{id}/users/{userId}/consent-organizations
- description: Grant a list of organization access of a user for a application.
  method: PUT
  name: replaceapplicationuserconsentorganizations
  path: /api/applications/{id}/users/{userId}/consent-organizations
- description: Grant a list of organization access of a user for a application.
  method: POST
  name: createapplicationuserconsentorganization
  path: /api/applications/{id}/users/{userId}/consent-organizations
- description: Revoke a user's access to an organization for a application.
  method: DELETE
  name: deleteapplicationuserconsentorganization
  path: /api/applications/{id}/users/{userId}/consent-organizations/{organizationId}
- description: Get admin console config
  method: GET
  name: getadminconsoleconfig
  path: /api/configs/admin-console
- description: Update admin console config
  method: PATCH
  name: updateadminconsoleconfig
  path: /api/configs/admin-console
- description: Get OIDC session config
  method: GET
  name: getoidcsessionconfig
  path: /api/configs/oidc/session
- description: Update OIDC session config
  method: PATCH
  name: updateoidcsessionconfig
  path: /api/configs/oidc/session
- description: Get OIDC keys
  method: GET
  name: getoidckeys
  path: /api/configs/oidc/{keyType}
- description: Delete OIDC key
  method: DELETE
  name: deleteoidckey
  path: /api/configs/oidc/{keyType}/{keyId}
- description: Rotate OIDC keys
  method: POST
  name: rotateoidckeys
  path: /api/configs/oidc/{keyType}/rotate
- description: Create or update JWT customizer
  method: PUT
  name: upsertjwtcustomizer
  path: /api/configs/jwt-customizer/{tokenTypePath}
- description: Update JWT customizer
  method: PATCH
  name: updatejwtcustomizer
  path: /api/configs/jwt-customizer/{tokenTypePath}
- description: Get JWT customizer
  method: GET
  name: getjwtcustomizer
  path: /api/configs/jwt-customizer/{tokenTypePath}
- description: Delete JWT customizer
  method: DELETE
  name: deletejwtcustomizer
  path: /api/configs/jwt-customizer/{tokenTypePath}
- description: Get all JWT customizers
  method: GET
  name: listjwtcustomizers
  path: /api/configs/jwt-customizer
- description: Test JWT customizer
  method: POST
  name: testjwtcustomizer
  path: /api/configs/jwt-customizer/test
- description: Get ID token claims configuration
  method: GET
  name: getidtokenconfig
  path: /api/configs/id-token
- description: Upsert ID token claims configuration
  method: PUT
  name: upsertidtokenconfig
  path: /api/configs/id-token
- description: Create connector
  method: POST
  name: createconnector
  path: /api/connectors
- description: Get connectors
  method: GET
  name: listconnectors
  path: /api/connectors
- description: Get connector
  method: GET
  name: getconnector
  path: /api/connectors/{id}
- description: Update connector
  method: PATCH
  name: updateconnector
  path: /api/connectors/{id}
- description: Delete connector
  method: DELETE
  name: deleteconnector
  path: /api/connectors/{id}
- description: Test passwordless connector
  method: POST
  name: createconnectortest
  path: /api/connectors/{factoryId}/test
- description: Get connector's authorization URI
  method: POST
  name: createconnectorauthorizationuri
  path: /api/connectors/{connectorId}/authorization-uri
- description: Get connector factories
  method: GET
  name: listconnectorfactories
  path: /api/connector-factories
- description: Get connector factory
  method: GET
  name: getconnectorfactory
  path: /api/connector-factories/{id}
- description: Get API resources
  method: GET
  name: listresources
  path: /api/resources
- description: Create an API resource
  method: POST
  name: createresource
  path: /api/resources
- description: Get API resource
  method: GET
  name: getresource
  path: /api/resources/{id}
- description: Update API resource
  method: PATCH
  name: updateresource
  path: /api/resources/{id}
- description: Delete API resource
  method: DELETE
  name: deleteresource
  path: /api/resources/{id}
- description: Set API resource as default
  method: PATCH
  name: updateresourceisdefault
  path: /api/resources/{id}/is-default
- description: Get API resource scopes
  method: GET
  name: listresourcescopes
  path: /api/resources/{resourceId}/scopes
- description: Create API resource scope
  method: POST
  name: createresourcescope
  path: /api/resources/{resourceId}/scopes
personas: []
provider_name: Logto
provider_slug: logto
search_terms:
- create connector
- replaceapplicationroles
- replaceapplicationsigninexperience
- get api resources
- get all jwt customizers
- updateresourceisdefault
- get application api resource roles
- listapplicationuserconsentscopes
- updateapplicationcustomdata
- test passwordless connector
- updateresource
- get application organizations
- delete jwt customizer
- deleteresource
- updateapplication
- update api resource
- get application secrets
- getconnector
- api
- updateoidcsessionconfig
- authorization
- create an api resource
- listapplicationsecrets
- assign user consent scopes to application.
- get connector's authorization uri
- get jwt customizer
- getapplicationsigninexperience
- rotate oidc keys
- delete api resource
- deleteapplicationprotectedappmetadatacustomdomai
- rotateoidckeys
- deleteapplicationlegacysecret
- deleteapplicationrole
- delete connector
- create api resource scope
- identity
- getconnectorfactory
- update admin console config
- get connector factories
- remove custom domain.
- getadminconsoleconfig
- list all the user consented organizations of a application.
- createconnectortest
- open source
- replaceapplicationuserconsentorganizations
- delete application
- get connector
- authentication
- get api resource scopes
- get application custom domains.
- createapplicationprotectedappmetadatacustomdomai
- get oidc keys
- createconnectorauthorizationuri
- remove a api resource role from application
- listapplicationorganizations
- listapplicationuserconsentorganizations
- delete application secret
- update jwt customizer
- delete application legacy secret
- listapplications
- updateconnector
- updateapplicationsecret
- listconnectors
- deleteconnector
- getoidcsessionconfig
- update connector
- getresource
- update application level sign-in experience
- deleteapplicationuserconsentscope
- update api resource roles for application
- createapplicationuserconsentscope
- delete oidc key
- upsertidtokenconfig
- createapplicationsecret
- get connectors
- update application
- assignapplicationroles
- deleteapplication
- get applications
- add application secret
- remove user consent scope from application.
- oidc
- upsert id token claims configuration
- get application
- createresourcescope
- getoidckeys
- getjwtcustomizer
- get admin console config
- deleteoidckey
- update application secret
- test jwt customizer
- deleteapplicationuserconsentorganization
- deletejwtcustomizer
- update oidc session config
- get id token claims configuration
- list all the user consent scopes of an application.
- listresourcescopes
- set api resource as default
- create an application
- createconnector
- testjwtcustomizer
- logto
- create or update jwt customizer
- createresource
- listjwtcustomizers
- deleteapplicationsecret
- createapplication
- update application custom data
- assign api resource roles to application
- get oidc session config
- oauth
- get the application level sign-in experience
- updateadminconsoleconfig
- get connector factory
- saml
- listconnectorfactories
- listresources
- updatejwtcustomizer
- get api resource
- listapplicationprotectedappmetadatacustomdomains
- getapplication
- revoke a user's access to an organization for a application.
- createapplicationuserconsentorganization
- add a custom domain to the application.
- getidtokenconfig
- listapplicationroles
- upsertjwtcustomizer
- grant a list of organization access of a user for a application.
slug: logto-capability
source_filename: logto-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Logto API references\n  description: 'API references for Logto services. Note: The documentation is for Logto Cloud. If you are using Logto OSS,\n    please refer to the response of `/api/swagger.json` endpoint on your Logto instance.'\n  tags:\n  - Logto\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: logto\n    baseUri: https://[tenant_id].logto.app\n    description: Logto API references HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LOGTO_TOKEN}}'\n    resources:\n    - name: api-applications\n      path: /api/applications\n      operations:\n      - name: listapplications\n        method: GET\n        description: Get applications\n        inputParameters:\n        - name: types\n          in: query\n          type: string\n          description: An array of application types to filter applications.\n        - name: excludeRoleId\n          in:\
  \ query\n          type: string\n        - name: excludeOrganizationId\n          in: query\n          type: string\n        - name: isThirdParty\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n          description: Page number (starts from 1).\n        - name: page_size\n          in: query\n          type: integer\n          description: Entries per page.\n        - name: search_params\n          in: query\n          type: object\n          description: Search query parameters.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapplication\n        method: POST\n        description: Create an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-id\n      path: /api/applications/{id}\n      operations:\n     \
  \ - name: getapplication\n        method: GET\n        description: Get application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapplication\n        method: PATCH\n        description: Update application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapplication\n        method: DELETE\n        description: Delete application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-applicationid-custom-data\n      path: /api/applications/{applicationId}/custom-data\n      operations:\n      - name: updateapplicationcustomdata\n        method: PATCH\n        description: Update application custom data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n    - name: api-applications-applicationid-roles\n      path: /api/applications/{applicationId}/roles\n      operations:\n      - name: listapplicationroles\n        method: GET\n        description: Get application API resource roles\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Page number (starts from 1).\n        - name: page_size\n          in: query\n          type: integer\n          description: Entries per page.\n        - name: search_params\n          in: query\n          type: object\n          description: Search query parameters.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: assignapplicationroles\n        method: POST\n        description: Assign API resource roles to application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n      - name: replaceapplicationroles\n        method: PUT\n        description: Update API resource roles for application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-applicationid-roles-roleid\n      path: /api/applications/{applicationId}/roles/{roleId}\n      operations:\n      - name: deleteapplicationrole\n        method: DELETE\n        description: Remove a API resource role from application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-id-protected-app-metadata-custo\n      path: /api/applications/{id}/protected-app-metadata/custom-domains\n      operations:\n      - name: listapplicationprotectedappmetadatacustomdomains\n        method: GET\n        description: Get application custom domains.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapplicationprotectedappmetadatacustomdomai\n        method: POST\n        description: Add a custom domain to the application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-id-protected-app-metadata-custo\n      path: /api/applications/{id}/protected-app-metadata/custom-domains/{domain}\n      operations:\n      - name: deleteapplicationprotectedappmetadatacustomdomai\n        method: DELETE\n        description: Remove custom domain.\n        inputParameters:\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-id-organizations\n      path: /api/applications/{id}/organizations\n\
  \      operations:\n      - name: listapplicationorganizations\n        method: GET\n        description: Get application organizations\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Page number (starts from 1).\n        - name: page_size\n          in: query\n          type: integer\n          description: Entries per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-id-legacy-secret\n      path: /api/applications/{id}/legacy-secret\n      operations:\n      - name: deleteapplicationlegacysecret\n        method: DELETE\n        description: Delete application legacy secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-id-secrets\n      path: /api/applications/{id}/secrets\n      operations:\n  \
  \    - name: listapplicationsecrets\n        method: GET\n        description: Get application secrets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapplicationsecret\n        method: POST\n        description: Add application secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-id-secrets-name\n      path: /api/applications/{id}/secrets/{name}\n      operations:\n      - name: deleteapplicationsecret\n        method: DELETE\n        description: Delete application secret\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the secret.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapplicationsecret\n\
  \        method: PATCH\n        description: Update application secret\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the secret.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-applicationid-user-consent-scop\n      path: /api/applications/{applicationId}/user-consent-scopes\n      operations:\n      - name: createapplicationuserconsentscope\n        method: POST\n        description: Assign user consent scopes to application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listapplicationuserconsentscopes\n        method: GET\n        description: List all the user consent scopes of an application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: api-applications-applicationid-user-consent-scop\n      path: /api/applications/{applicationId}/user-consent-scopes/{scopeType}/{scopeId}\n      operations:\n      - name: deleteapplicationuserconsentscope\n        method: DELETE\n        description: Remove user consent scope from application.\n        inputParameters:\n        - name: scopeType\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-applicationid-sign-in-experienc\n      path: /api/applications/{applicationId}/sign-in-experience\n      operations:\n      - name: replaceapplicationsigninexperience\n        method: PUT\n        description: Update application level sign-in experience\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n      - name: getapplicationsigninexperience\n        method: GET\n        description: Get the application level sign-in experience\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-id-users-userid-consent-organiz\n      path: /api/applications/{id}/users/{userId}/consent-organizations\n      operations:\n      - name: listapplicationuserconsentorganizations\n        method: GET\n        description: List all the user consented organizations of a application.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Page number (starts from 1).\n        - name: page_size\n          in: query\n          type: integer\n          description: Entries per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replaceapplicationuserconsentorganizations\n\
  \        method: PUT\n        description: Grant a list of organization access of a user for a application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapplicationuserconsentorganization\n        method: POST\n        description: Grant a list of organization access of a user for a application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications-id-users-userid-consent-organiz\n      path: /api/applications/{id}/users/{userId}/consent-organizations/{organizationId}\n      operations:\n      - name: deleteapplicationuserconsentorganization\n        method: DELETE\n        description: Revoke a user's access to an organization for a application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ api-configs-admin-console\n      path: /api/configs/admin-console\n      operations:\n      - name: getadminconsoleconfig\n        method: GET\n        description: Get admin console config\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateadminconsoleconfig\n        method: PATCH\n        description: Update admin console config\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-configs-oidc-session\n      path: /api/configs/oidc/session\n      operations:\n      - name: getoidcsessionconfig\n        method: GET\n        description: Get OIDC session config\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateoidcsessionconfig\n        method: PATCH\n        description: Update OIDC session config\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-configs-oidc-keytype\n      path: /api/configs/oidc/{keyType}\n      operations:\n      - name: getoidckeys\n        method: GET\n        description: Get OIDC keys\n        inputParameters:\n        - name: keyType\n          in: path\n          type: string\n          required: true\n          description: Private keys are used to sign OIDC JWTs. Cookie keys are used to sign OIDC cookies. For clients, they\n            do not need to know private keys to verify OIDC JWTs; they\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-configs-oidc-keytype-keyid\n      path: /api/configs/oidc/{keyType}/{keyId}\n      operations:\n      - name: deleteoidckey\n        method: DELETE\n        description: Delete OIDC key\n        inputParameters:\n        - name: keyType\n\
  \          in: path\n          type: string\n          required: true\n          description: Private keys are used to sign OIDC JWTs. Cookie keys are used to sign OIDC cookies. For clients, they\n            do not need to know private keys to verify OIDC JWTs; they\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-configs-oidc-keytype-rotate\n      path: /api/configs/oidc/{keyType}/rotate\n      operations:\n      - name: rotateoidckeys\n        method: POST\n        description: Rotate OIDC keys\n        inputParameters:\n        - name: keyType\n          in: path\n          type: string\n          required: true\n          description: Private keys are used to sign OIDC JWTs. Cookie keys are used to sign OIDC cookies. For clients, they\n            do not need to know private keys to verify OIDC JWTs; they\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: api-configs-jwt-customizer-tokentypepath\n      path: /api/configs/jwt-customizer/{tokenTypePath}\n      operations:\n      - name: upsertjwtcustomizer\n        method: PUT\n        description: Create or update JWT customizer\n        inputParameters:\n        - name: tokenTypePath\n          in: path\n          type: string\n          required: true\n          description: The token type to create a JWT customizer for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatejwtcustomizer\n        method: PATCH\n        description: Update JWT customizer\n        inputParameters:\n        - name: tokenTypePath\n          in: path\n          type: string\n          required: true\n          description: The token type to update a JWT customizer for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: getjwtcustomizer\n        method: GET\n        description: Get JWT customizer\n        inputParameters:\n        - name: tokenTypePath\n          in: path\n          type: string\n          required: true\n          description: The token type to get the JWT customizer for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletejwtcustomizer\n        method: DELETE\n        description: Delete JWT customizer\n        inputParameters:\n        - name: tokenTypePath\n          in: path\n          type: string\n          required: true\n          description: The token type path to delete the JWT customizer for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-configs-jwt-customizer\n      path: /api/configs/jwt-customizer\n      operations:\n      -\
  \ name: listjwtcustomizers\n        method: GET\n        description: Get all JWT customizers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-configs-jwt-customizer-test\n      path: /api/configs/jwt-customizer/test\n      operations:\n      - name: testjwtcustomizer\n        method: POST\n        description: Test JWT customizer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-configs-id-token\n      path: /api/configs/id-token\n      operations:\n      - name: getidtokenconfig\n        method: GET\n        description: Get ID token claims configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upsertidtokenconfig\n        method: PUT\n        description: Upsert ID token claims configuration\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-connectors\n      path: /api/connectors\n      operations:\n      - name: createconnector\n        method: POST\n        description: Create connector\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listconnectors\n        method: GET\n        description: Get connectors\n        inputParameters:\n        - name: target\n          in: query\n          type: string\n          description: Filter connectors by target.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-connectors-id\n      path: /api/connectors/{id}\n      operations:\n      - name: getconnector\n        method: GET\n        description: Get connector\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: updateconnector\n        method: PATCH\n        description: Update connector\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteconnector\n        method: DELETE\n        description: Delete connector\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-connectors-factoryid-test\n      path: /api/connectors/{factoryId}/test\n      operations:\n      - name: createconnectortest\n        method: POST\n        description: Test passwordless connector\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-connectors-connectorid-authorization-uri\n      path: /api/connectors/{connectorId}/authorization-uri\n      operations:\n      - name:\
  \ createconnectorauthorizationuri\n        method: POST\n        description: Get connector's authorization URI\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-connector-factories\n      path: /api/connector-factories\n      operations:\n      - name: listconnectorfactories\n        method: GET\n        description: Get connector factories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-connector-factories-id\n      path: /api/connector-factories/{id}\n      operations:\n      - name: getconnectorfactory\n        method: GET\n        description: Get connector factory\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-resources\n      path: /api/resources\n      operations:\n      - name: listresources\n \
  \       method: GET\n        description: Get API resources\n        inputParameters:\n        - name: includeScopes\n          in: query\n          type: string\n          description: If it's provided with a truthy value (`true`, `1`, `yes`), the scopes of each resource will be included\n            in the response.\n        - name: page\n          in: query\n          type: integer\n          description: Page number (starts from 1).\n        - name: page_size\n          in: query\n          type: integer\n          description: Entries per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createresource\n        method: POST\n        description: Create an API resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-resources-id\n      path: /api/resources/{id}\n      operations:\n      - name:\
  \ getresource\n        method: GET\n        description: Get API resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateresource\n        method: PATCH\n        description: Update API resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteresource\n        method: DELETE\n        description: Delete API resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-resources-id-is-default\n      path: /api/resources/{id}/is-default\n      operations:\n      - name: updateresourceisdefault\n        method: PATCH\n        description: Set API resource as default\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ api-resources-resourceid-scopes\n      path: /api/resources/{resourceId}/scopes\n      operations:\n      - name: listresourcescopes\n        method: GET\n        description: Get API resource scopes\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          description: Page number (starts from 1).\n        - name: page_size\n          in: query\n          type: integer\n          description: Entries per page.\n        - name: search_params\n          in: query\n          type: object\n          description: Search query parameters.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createresourcescope\n        method: POST\n        description: Create API resource scope\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ logto-rest\n    description: REST adapter for Logto API references.\n    resources:\n    - path: /api/applications\n      name: listapplications\n      operations:\n      - method: GET\n        name: listapplications\n        description: Get applications\n        call: logto.listapplications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications\n      name: createapplication\n      operations:\n      - method: POST\n        name: createapplication\n        description: Create an application\n        call: logto.createapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{id}\n      name: getapplication\n      operations:\n      - method: GET\n        name: getapplication\n        description: Get application\n        call: logto.getapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{id}\n      name: updateapplication\n\
  \      operations:\n      - method: PATCH\n        name: updateapplication\n        description: Update application\n        call: logto.updateapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{id}\n      name: deleteapplication\n      operations:\n      - method: DELETE\n        name: deleteapplication\n        description: Delete application\n        call: logto.deleteapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{applicationId}/custom-data\n      name: updateapplicationcustomdata\n      operations:\n      - method: PATCH\n        name: updateapplicationcustomdata\n        description: Update application custom data\n        call: logto.updateapplicationcustomdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{applicationId}/roles\n      name: listapplicationroles\n      operations:\n     \
  \ - method: GET\n        name: listapplicationroles\n        description: Get application API resource roles\n        call: logto.listapplicationroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{applicationId}/roles\n      name: assignapplicationroles\n      operations:\n      - method: POST\n        name: assignapplicationroles\n        description: Assign API resource roles to application\n        call: logto.assignapplicationroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{applicationId}/roles\n      name: replaceapplicationroles\n      operations:\n      - method: PUT\n        name: replaceapplicationroles\n        description: Update API resource roles for application\n        call: logto.replaceapplicationroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{applicationId}/roles/{roleId}\n      name:\
  \ deleteapplicationrole\n      operations:\n      - method: DELETE\n        name: deleteapplicationrole\n        description: Remove a API resource role from application\n        call: logto.deleteapplicationrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{id}/protected-app-metadata/custom-domains\n      name: listapplicationprotectedappmetadatacustomdomains\n      operations:\n      - method: GET\n        name: listapplicationprotectedappmetadatacustomdomains\n        description: Get application custom domains.\n        call: logto.listapplicationprotectedappmetadatacustomdomains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{id}/protected-app-metadata/custom-domains\n      name: createapplicationprotectedappmetadatacustomdomai\n      operations:\n      - method: POST\n        name: createapplicationprotectedappmetadatacustomdomai\n        description: Add a custom\
  \ domain to the application.\n        call: logto.createapplicationprotectedappmetadatacustomdomai\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{id}/protected-app-metadata/custom-domains/{domain}\n      name: deleteapplicationprotectedappmetadatacustomdomai\n      operations:\n      - method: DELETE\n        name: deleteapplicationprotectedappmetadatacustomdomai\n        description: Remove custom domain.\n        call: logto.deleteapplicationprotectedappmetadatacustomdomai\n        with:\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{id}/organizations\n      name: listapplicationorganizations\n      operations:\n      - method: GET\n        name: listapplicationorganizations\n        description: Get application organizations\n        call: logto.listapplicationorganizations\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /api/applications/{id}/legacy-secret\n      name: deleteapplicationlegacysecret\n      operations:\n      - method: DELETE\n        name: deleteapplicationlegacysecret\n        description: Delete application legacy secret\n        call: logto.deleteapplicationlegacysecret\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{id}/secrets\n      name: listapplicationsecrets\n      operations:\n      - method: GET\n        name: listapplicationsecrets\n        description: Get application secrets\n        call: logto.listapplicationsecrets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{id}/secrets\n      name: createapplicationsecret\n      operations:\n      - method: POST\n        name: createapplicationsecret\n        description: Add application secret\n        call: logto.createapplicationsecret\n        outputParameters:\n        - type: object\n        \
  \  mapping: $.\n    - path: /api/applications/{id}/secrets/{name}\n      name: deleteapplicationsecret\n      operations:\n      - method: DELETE\n        name: deleteapplicationsecret\n        description: Delete application secret\n        call: logto.deleteapplicationsecret\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{id}/secrets/{name}\n      name: updateapplicationsecret\n      operations:\n      - method: PATCH\n        name: updateapplicationsecret\n        description: Update application secret\n        call: logto.updateapplicationsecret\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{applicationId}/user-consent-scopes\n      name: createapplicationuserconsentscope\n      operations:\n      - method: POST\n        name: createapplicationuserconsentscope\n        description: Assign\
  \ user consent scopes to application.\n        call: logto.createapplicationuserconsentscope\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{applicationId}/user-consent-scopes\n      name: listapplicationuserconsentscopes\n      operations:\n      - method: GET\n        name: listapplicationuserconsentscopes\n        description: List all the user consent scopes of an application.\n        call: logto.listapplicationuserconsentscopes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{applicationId}/user-consent-scopes/{scopeType}/{scopeId}\n      name: deleteapplicationuserconsentscope\n      operations:\n      - method: DELETE\n        name: deleteapplicationuserconsentscope\n        description: Remove user consent scope from application.\n        call: logto.deleteapplicationuserconsentscope\n        with:\n          scopeType: rest.scopeType\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /api/applications/{applicationId}/sign-in-experience\n      name: replaceapplicationsigninexperience\n      operations:\n      - method: PUT\n        name: replaceapplicationsigninexperience\n        description: Update application level sign-in experience\n        call: logto.replaceapplicationsigninexperience\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{applicationId}/sign-in-experience\n      name: getapplicationsigninexperience\n      operations:\n      - method: GET\n        name: getapplicationsigninexperience\n        description: Get the application level sign-in experience\n        call: logto.getapplicationsigninexperience\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{id}/users/{userId}/consent-organizations\n      name: listapplicationuserconsentorganizations\n      operations:\n      - method: GET\n\
  \        name: listapplicationuserconsentorganizations\n        description: List all the user consented organizations of a application.\n        call: logto.listapplicationuserconsentorganizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/applications/{id}/users/{userId}/consent-organizations\n      name: replaceapplicationuserconsentorganizations\n      operations:\n      - method: PUT\n        name: replaceapplicationuserconsentorganizations\n        description: Grant a list of organization access of a user for a application.\n        call: logto.replaceapplicationuserconsentorganizations\n        outputParameters:\n        - type: object\n         \n\n# --- truncated at 32 KB (64 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/logto/refs/heads/main/capabilities/logto-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/logto/refs/heads/main/capabilities/logto-capability.yaml
tags:
- Logto
- API
tools:
- description: Get applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplications
- description: Create an application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplication
- description: Get application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplication
- description: Update application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapplication
- description: Delete application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplication
- description: Update application custom data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapplicationcustomdata
- description: Get application API resource roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationroles
- description: Assign API resource roles to application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assignapplicationroles
- description: Update API resource roles for application
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replaceapplicationroles
- description: Remove a API resource role from application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplicationrole
- description: Get application custom domains.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationprotectedappmetadatacustomdomains
- description: Add a custom domain to the application.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplicationprotectedappmetadatacustomdomai
- description: Remove custom domain.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplicationprotectedappmetadatacustomdomai
- description: Get application organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationorganizations
- description: Delete application legacy secret
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplicationlegacysecret
- description: Get application secrets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationsecrets
- description: Add application secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplicationsecret
- description: Delete application secret
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplicationsecret
- description: Update application secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapplicationsecret
- description: Assign user consent scopes to application.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplicationuserconsentscope
- description: List all the user consent scopes of an application.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationuserconsentscopes
- description: Remove user consent scope from application.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplicationuserconsentscope
- description: Update application level sign-in experience
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replaceapplicationsigninexperience
- description: Get the application level sign-in experience
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplicationsigninexperience
- description: List all the user consented organizations of a application.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationuserconsentorganizations
- description: Grant a list of organization access of a user for a application.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replaceapplicationuserconsentorganizations
- description: Grant a list of organization access of a user for a application.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplicationuserconsentorganization
- description: Revoke a user's access to an organization for a application.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplicationuserconsentorganization
- description: Get admin console config
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadminconsoleconfig
- description: Update admin console config
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateadminconsoleconfig
- description: Get OIDC session config
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoidcsessionconfig
- description: Update OIDC session config
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateoidcsessionconfig
- description: Get OIDC keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoidckeys
- description: Delete OIDC key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteoidckey
- description: Rotate OIDC keys
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rotateoidckeys
- description: Create or update JWT customizer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: upsertjwtcustomizer
- description: Update JWT customizer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatejwtcustomizer
- description: Get JWT customizer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjwtcustomizer
- description: Delete JWT customizer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletejwtcustomizer
- description: Get all JWT customizers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjwtcustomizers
- description: Test JWT customizer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: testjwtcustomizer
- description: Get ID token claims configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidtokenconfig
- description: Upsert ID token claims configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: upsertidtokenconfig
- description: Create connector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconnector
- description: Get connectors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconnectors
- description: Get connector
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnector
- description: Update connector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateconnector
- description: Delete connector
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteconnector
- description: Test passwordless connector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconnectortest
- description: Get connector's authorization URI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconnectorauthorizationuri
- description: Get connector factories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconnectorfactories
- description: Get connector factory
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnectorfactory
- description: Get API resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listresources
- description: Create an API resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createresource
- description: Get API resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getresource
- description: Update API resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateresource
- description: Delete API resource
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteresource
- description: Set API resource as default
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateresourceisdefault
- description: Get API resource scopes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listresourcescopes
- description: Create API resource scope
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createresourcescope
---
