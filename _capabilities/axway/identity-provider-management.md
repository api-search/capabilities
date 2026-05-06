---
categories: []
consumed_apis: []
description: Configure and manage SAML and OIDC identity providers for SSO across the Axway Amplify platform.
layout: capability
name: Axway Identity Provider Management
operations:
- description: Axway Create Consumer SAML V2.0 IdP
  method: POST
  name: provider-idpCreateSAML
  path: /v1/idp
- description: Axway Create Consumer OIDC IdP
  method: POST
  name: provider-idpCreateOIDC
  path: /v1/idp
- description: Axway Get Consumer IdP
  method: GET
  name: provider-idpFind
  path: /v1/idp
- description: Axway Remove Consumer IdP
  method: DELETE
  name: provider-idpRemove
  path: /v1/idp
- description: Axway Update Consumer IdP
  method: PUT
  name: provider-idpUpdate
  path: /v1/idp
- description: Axway Create SAML V2.0 IdP
  method: POST
  name: org-idpCreateSAML
  path: /v1/idp
- description: Axway Create OIDC IdP
  method: POST
  name: org-idpCreateOIDC
  path: /v1/idp
- description: Axway Reload SAML Validating Certificates
  method: GET
  name: org-idpReloadKeys
  path: /v1/idp
- description: Axway Get IdP Descriptor
  method: GET
  name: org-idpDownloadDescriptor
  path: /v1/idp
- description: Axway Get Public IdP Signing or Encryption Certificate
  method: GET
  name: org-idpDownloadCert
  path: /v1/idp
- description: Axway Associate with Another Organizations IdP
  method: POST
  name: org-idpAssociate
  path: /v1/idp
- description: Axway Get IdP
  method: GET
  name: org-idpFindOne
  path: /v1/idp
- description: Axway Remove Organization IdP Config
  method: DELETE
  name: org-idpRemove
  path: /v1/idp
- description: Axway Update Organizations Custom IdP
  method: PUT
  name: org-idpUpdate
  path: /v1/idp
- description: Axway Get All Organization IdPs
  method: GET
  name: org-idpFind
  path: /v1/idp
personas: []
provider_name: Axway
provider_slug: axway
search_terms:
- axway create saml v2.0 idp
- org idpDownloadCert
- provider idpCreateSAML
- provider idpUpdate
- axway remove consumer idp
- axway
- identity provider
- org idpReloadKeys
- org idpDownloadDescriptor
- integration
- axway create consumer saml v2.0 idp
- provider idpRemove
- axway update organizations custom idp
- org idpUpdate
- axway get consumer idp
- axway create consumer oidc idp
- security
- enterprise
- axway get idp descriptor
- provider idpCreateOIDC
- axway create oidc idp
- axway get all organization idps
- saml
- sso
- axway associate with another organizations idp
- org idpCreateOIDC
- org idpFind
- org idpFindOne
- axway get public idp signing or encryption certificate
- axway get idp
- api management
- idp operations
- org idpRemove
- oidc
- provider idpFind
- org idpCreateSAML
- org idpAssociate
- axway reload saml validating certificates
- axway update consumer idp
- axway remove organization idp config
slug: identity-provider-management
source_filename: identity-provider-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Axway Identity Provider Management\n  description: Configure and manage SAML and OIDC identity providers for SSO across the Axway Amplify platform.\n  tags:\n  - Axway\n  - Identity Provider\n  - SAML\n  - OIDC\n  - SSO\n  created: '2026-04-21'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AXWAY_BEARER_TOKEN: AXWAY_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: amplify-platform\n    baseUri: https://platform.axway.com/api/v1\n    description: Axway Amplify Platform API v1\n    authentication:\n      type: bearer\n      token: '{{env.AXWAY_BEARER_TOKEN}}'\n    resources:\n    - name: aca\n      path: /aca\n      description: Aca management operations\n      operations:\n      - name: aca-setMetadata\n        method: PUT\n        description: Axway Set Metadata by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: aca_id\n          in: path\n          type: string\n          required: true\n          description: aca_id parameter\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name parameter\n        body:\n          type: json\n          data: {}\n      - name: aca-findOne\n        method: GET\n        description: Axway Find Crash Record by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n   \
  \     - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: aca_id\n          in: path\n          type: string\n          required: true\n          description: aca_id parameter\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n    - name: activity\n      path: /activity\n      description: Activity management operations\n      operations:\n      - name: activity-findEvents\n        method: GET\n        description: Axway Get Activity Event Names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n    \
  \      description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: authorization\n          in: header\n          type: string\n          required: false\n          description: authorization parameter\n      - name: activity-find\n        method: GET\n        description: Axway Get Activity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_guid\n          in: query\n          type: string\n          required: false\n          description: app_guid parameter\n        - name: contexts\n          in: query\n\
  \          type: array\n          required: false\n          description: contexts parameter\n        - name: data\n          in: query\n          type: boolean\n          required: false\n          description: data parameter\n        - name: enrich\n          in: query\n          type: boolean\n          required: false\n          description: enrich parameter\n        - name: exclude_contexts\n          in: query\n          type: array\n          required: false\n          description: exclude_contexts parameter\n        - name: from\n          in: query\n          type: number\n          required: false\n          description: from parameter\n        - name: org_id\n          in: query\n          type: string\n          required: false\n          description: org_id parameter\n        - name: redact\n          in: query\n          type: boolean\n          required: false\n          description: redact parameter\n        - name: sort\n          in: query\n          type: number\n  \
  \        required: false\n          description: sort parameter\n        - name: term\n          in: query\n          type: string\n          required: false\n          description: term parameter\n        - name: to\n          in: query\n          type: number\n          required: false\n          description: to parameter\n        - name: user_guid\n          in: query\n          type: string\n          required: false\n          description: user_guid parameter\n        - name: user_messages\n          in: query\n          type: boolean\n          required: false\n          description: user_messages parameter\n        - name: limit\n          in: query\n          type: number\n          required: false\n          description: limit parameter\n        - name: page\n          in: query\n          type: number\n          required: false\n          description: page parameter\n        - name: skip\n          in: query\n          type: number\n          required: false\n          description:\
  \ skip parameter\n    - name: analytics\n      path: /analytics\n      description: Analytics management operations\n      operations:\n      - name: analytics-query\n        method: GET\n        description: Axway Analytics Query Using Lexus\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: apim_tier\n          in: query\n          type: string\n          required: false\n          description: apim_tier parameter\n        - name: app_guid\n          in: query\n          type: string\n          required: false\n          description: app_guid parameter\n        - name: clients\n          in: query\n          type: array\n          required: false\n          description: clients parameter\n        - name: cross_org\n          in: query\n          type: boolean\n          required: false\n          description: cross_org parameter\n        - name: custom_query\n      \
  \    in: query\n          type: string\n          required: false\n          description: custom_query parameter\n        - name: debug\n          in: query\n          type: boolean\n          required: false\n          description: debug parameter\n        - name: endpoint\n          in: query\n          type: string\n          required: false\n          description: endpoint parameter\n        - name: events\n          in: query\n          type: string\n          required: false\n          description: events parameter\n        - name: field\n          in: query\n          type: string\n          required: false\n          description: field parameter\n        - name: from\n          in: query\n          type: number\n          required: false\n          description: from parameter\n        - name: granularity\n          in: query\n          type: string\n          required: false\n          description: granularity parameter\n        - name: group_by\n          in: query\n         \
  \ type: string\n          required: false\n          description: group_by parameter\n        - name: grquantity\n          in: query\n          type: number\n          required: false\n          description: grquantity parameter\n        - name: include_query\n          in: query\n          type: string\n          required: false\n          description: include_query parameter\n        - name: org_id\n          in: query\n          type: string\n          required: false\n          description: org_id parameter\n        - name: platform\n          in: query\n          type: string\n          required: false\n          description: platform parameter\n        - name: post_process\n          in: query\n          type: boolean\n          required: false\n          description: post_process parameter\n        - name: prefix\n          in: query\n          type: string\n          required: false\n          description: prefix parameter\n        - name: preprocessor\n          in: query\n \
  \         type: string\n          required: false\n          description: preprocessor parameter\n        - name: processor\n          in: query\n          type: string\n          required: false\n          description: processor parameter\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: query parameter\n        - name: region\n          in: query\n          type: string\n          required: false\n          description: region parameter\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: status parameter\n        - name: to\n          in: query\n          type: number\n          required: false\n          description: to parameter\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: type parameter\n        - name: username\n          in: query\n          type: string\n          required:\
  \ false\n          description: username parameter\n      - name: analytics-error\n        method: POST\n        description: Axway Report an Error\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: analytics-customCreate\n        method: POST\n        description: Axway Create a Custom Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n       \
  \ body:\n          type: json\n          data: {}\n      - name: analytics-customFind\n        method: GET\n        description: Axway Find Custom Queries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n      - name: analytics-customRemove\n        method: DELETE\n        description: Axway Delete a Custom Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n         \
  \ in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: query_id\n          in: path\n          type: string\n          required: true\n          description: query_id parameter\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n      - name: analytics-customUpdate\n        method: PUT\n        description: Axway Update a Custom Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n         \
  \ description: ' parameter'\n        - name: query_id\n          in: path\n          type: string\n          required: true\n          description: query_id parameter\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n        body:\n          type: json\n          data: {}\n      - name: analytics-customFindOne\n        method: GET\n        description: Axway Get Custom Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: query_id\n          in: path\n          type: string\n          required: true\n          description: query_id\
  \ parameter\n        - name: org_id\n          in: query\n          type: string\n          required: false\n          description: org_id parameter\n    - name: app\n      path: /app\n      description: App management operations\n      operations:\n      - name: app-create\n        method: POST\n        description: Axway Create App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data: {}\n      - name: app-find\n        method: GET\n        description: Axway Find Apps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n        inputParameters:\n        - name: fields\n          in: query\n          type: array\n          required: false\n          description: A list of fields to include in the response.\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n        - name: provider_guid\n          in: query\n          type: string\n          required: false\n          description: provider_guid parameter\n        - name: subtype\n          in: query\n          type: string\n          required: false\n          description: subtype parameter\n        - name: type\n          in: query\n          type: string\n          required: false\n          description:\
  \ type parameter\n      - name: app-findOne\n        method: GET\n        description: Axway Find App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n      - name: app-remove\n        method: DELETE\n        description: Axway Remove App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n      - name: app-update\n        method: PUT\n        description: Axway Update App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: app_id parameter\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n        body:\n          type: json\n          data: {}\n    - name: auth\n      path: /auth\n      description: Auth management operations\n      operations:\n      - name: auth-validatePassword\n        method: POST\n        description: Axway Validates a User Password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: x-auth-password\n          in: header\n          type: string\n          required: true\n          description: x-auth-password parameter\n      - name: auth-acceptTerms\n        method: PUT\n        description: Axway Accept Terms & Conditions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: grant\n          in: query\n          type: string\n          required: false\n          description: grant parameter\n      - name: auth-sessionSwitchOrg\n        method: POST\n        description: Axway Switch Signed-in Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data:\
  \ {}\n      - name: auth-signup\n        method: POST\n        description: Axway Sign Up\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-findPasswordPolicy\n        method: GET\n        description: Axway Get Effective Password Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: provider_guid\n          in: query\n          type: string\n          required: false\n          description: provider_guid parameter\n        - name: user_guid\n          in: query\n\
  \          type: string\n          required: false\n          description: user_guid parameter\n      - name: auth-onboarding\n        method: PUT\n        description: Axway Onboarding Capture\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: grant\n          in: query\n          type: string\n          required: false\n          description: grant parameter\n        body:\n          type: json\n          data: {}\n      - name: auth-mfaVerify\n        method: POST\n        description: Axway Verify an Authorization Code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data: {}\n      - name: auth-mfaSend\n        method: POST\n        description: Axway Send an Authorization Code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data: {}\n      - name: auth-logout\n        method: GET\n      \
  \  description: Axway Sign-out\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: msg\n          in: query\n          type: string\n          required: false\n          description: msg parameter\n        - name: redirect\n          in: query\n          type: string\n          required: false\n          description: redirect parameter\n      - name: auth-login\n        method: POST\n        description: Axway Sign-in\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n      \
  \    type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: grant\n          in: query\n          type: string\n          required: false\n          description: grant parameter\n        body:\n          type: json\n          data: {}\n      - name: auth-unimpersonate\n        method: DELETE\n        description: Axway Unimpersonate User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n      - name: auth-forgot\n        method: POST\n        description: Axway Send\
  \ Forgot Password Link\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-sessionFind\n        method: GET\n        description: Axway Retrieves the Current Session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: from parameter\n      - name: auth-deviceauthResend\n        method: POST\n        description: Axway Resends Device Authorization\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n      - name: auth-deviceauthValidate\n        method: POST\n        description: Axway Validates a New Sessions Device Authorization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: grant\n          in: query\n          type: string\n\
  \          required: false\n          description: grant parameter\n        body:\n          type: json\n          data: {}\n      - name: auth-sessionCheck\n        method: GET\n        description: Axway Checks if the User is Signed in\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n      - name: auth-deviceauthConfirm\n        method: POST\n        description: Axway Confirm Authenticator App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-deviceauthCreate\n        method:\
  \ GET\n        description: Axway Initiate Authenticator App Setup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n      - name: auth-deviceauthRemoveApp\n        method: DELETE\n        description: Axway Remove Authenticator App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: x-auth-password\n          in: header\n          type: string\n          required: true\n          description: x-auth-password parameter\n      - name: auth-activationSignup\n        method: POST\n        description: Axway Activate a\
  \ Signup User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-activationResend\n        method: POST\n        description: Axway Resend Activation Link\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-activationForgot\n        method: POST\n        description: Axway Reset User Password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-activationConfirm\n        method: POST\n        description: Axway Activate a User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-activationUnlock\n        method: PUT\n        description: Axway Unlock Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: activation_id\n          in: path\n          type: string\n          required: true\n          description: activation_id parameter\n      - name: auth-revokeOauth\n        method: DELETE\n        description: Axway Revoke OAuth Service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n      \
  \  - name: service\n          in: path\n          type: string\n          required: true\n          description: service parameter\n      - name: auth-deviceauthFind\n        method: GET\n        description: Axway Retrieve Authorized Devices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: user_id parameter\n      - name: auth-deviceauthRemove\n        method: DELETE\n        description: Axway Remove Authorized Device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        inputParameters:\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: device_id parameter\n      - name: auth-activationFind\n        method: GET\n        description: Axway Find Activation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: activation_id\n          in: path\n          type: string\n          required: true\n          description: activation_id parameter\n    - name: client\n      path: /client\n      description: Client management operations\n      operations:\n      - name: client-create\n   \
  \     method: POST\n        description: Axway Add Service Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data: {}\n      - name: client-find\n        method: GET\n        description: Axway Get Service Accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required:\
  \ false\n          description: ' p\n\n# --- truncated at 32 KB (117 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/axway/refs/heads/main/capabilities/identity-provider-management.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/axway/refs/heads/main/capabilities/identity-provider-management.yaml
tags:
- Axway
- Identity Provider
- SAML
- OIDC
- SSO
tools:
- description: Axway Create Consumer SAML V2.0 IdP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provider-idpCreateSAML
- description: Axway Create Consumer OIDC IdP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provider-idpCreateOIDC
- description: Axway Get Consumer IdP
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: provider-idpFind
- description: Axway Remove Consumer IdP
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: provider-idpRemove
- description: Axway Update Consumer IdP
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: provider-idpUpdate
- description: Axway Create SAML V2.0 IdP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: org-idpCreateSAML
- description: Axway Create OIDC IdP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: org-idpCreateOIDC
- description: Axway Reload SAML Validating Certificates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-idpReloadKeys
- description: Axway Get IdP Descriptor
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-idpDownloadDescriptor
- description: Axway Get Public IdP Signing or Encryption Certificate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-idpDownloadCert
- description: Axway Associate with Another Organizations IdP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: org-idpAssociate
- description: Axway Get IdP
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-idpFindOne
- description: Axway Remove Organization IdP Config
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: org-idpRemove
- description: Axway Update Organizations Custom IdP
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: org-idpUpdate
- description: Axway Get All Organization IdPs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-idpFind
---
