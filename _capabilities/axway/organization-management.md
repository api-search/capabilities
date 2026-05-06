---
categories: []
consumed_apis: []
description: Manage organizations, subscriptions, domains, entitlements, and environments on the Axway Amplify platform.
layout: capability
name: Axway Organization Management
operations:
- description: Axway Find Organization Environments
  method: GET
  name: org-findEnvs
  path: /v1/org
- description: Axway Sets the Primary Contract for the Org
  method: PUT
  name: org-userPrimary
  path: /v1/org
- description: Axway Get Org User
  method: GET
  name: org-userFindOne
  path: /v1/org
- description: Axway Remove User
  method: DELETE
  name: org-userRemove
  path: /v1/org
- description: Axway Update Org Member Association
  method: PUT
  name: org-userUpdate
  path: /v1/org
- description: Axway Add User
  method: POST
  name: org-userCreate
  path: /v1/org
- description: Axway Get Members
  method: GET
  name: org-userFind
  path: /v1/org
- description: Axway Get Organization Stats
  method: GET
  name: org-stats
  path: /v1/org
- description: Axway Get Organization
  method: GET
  name: org-findOne
  path: /v1/org
- description: Axway Delete Organization
  method: DELETE
  name: org-remove
  path: /v1/org
- description: Axway Update Organization
  method: PUT
  name: org-update
  path: /v1/org
- description: Axway Trigger Domain Association Flow
  method: POST
  name: org-domainAssociate
  path: /v1/domain
- description: Axway Associate Subdomain to Parent Domain IdP
  method: POST
  name: org-domainAssociateSubdomain
  path: /v1/domain
- description: Axway Enable IdP for a Domain
  method: POST
  name: org-domainEnable
  path: /v1/domain
- description: Axway Remove Domain Association
  method: POST
  name: org-domainDissociate
  path: /v1/domain
- description: Axway Consolidate Domain Users
  method: POST
  name: org-domainConsolidate
  path: /v1/domain
- description: Axway Confirm Domain Ownership
  method: POST
  name: org-domainConfirm
  path: /v1/domain
- description: Axway Remove Domain Association
  method: DELETE
  name: org-domainRemove
  path: /v1/domain
- description: Axway Confirm Domain IdP Association
  method: PUT
  name: org-domainAssociateConfirm
  path: /v1/domain
- description: Axway Start Domain Ownership Process
  method: POST
  name: org-domainCreate
  path: /v1/domain
- description: Axway Get All Domains
  method: GET
  name: org-domainFind
  path: /v1/domain
- description: Axway Find Subscription
  method: GET
  name: org-findOneSubscription
  path: /v1/subscription
- description: Axway Find Subscriptions
  method: GET
  name: org-findSubscriptions
  path: /v1/subscription
- description: Axway Get Entitlement Meta
  method: GET
  name: entitlement-find
  path: /v1/entitlement
- description: Axway Create Environment
  method: POST
  name: env-create
  path: /v1/env
- description: Axway Find Environments
  method: GET
  name: env-find
  path: /v1/env
- description: Axway Find Environment
  method: GET
  name: env-findOne
  path: /v1/env
- description: Axway Delete Environment
  method: DELETE
  name: env-remove
  path: /v1/env
- description: Axway Update Environment
  method: PUT
  name: env-update
  path: /v1/env
- description: Axway Create Provider Marketplace
  method: POST
  name: provider-create
  path: /v1/provider
- description: Axway Get Provider Marketplaces
  method: GET
  name: provider-find
  path: /v1/provider
- description: Axway Get Provider Marketplace Onboarding Settings
  method: GET
  name: provider-findOnboarding
  path: /v1/provider
- description: Axway OAuth 2.0 Auth Signup Confirmation
  method: POST
  name: provider-oauthConfirm
  path: /v1/provider
- description: Axway Concludes OAuth 2.0 Auth
  method: GET
  name: provider-oauthCallback
  path: /v1/provider
- description: Axway Initiates OAuth 2.0 Auth
  method: GET
  name: provider-oauthAuthorize
  path: /v1/provider
- description: Axway Create Consumer SAML V2.0 IdP
  method: POST
  name: provider-idpCreateSAML
  path: /v1/provider
- description: Axway Create Consumer OIDC IdP
  method: POST
  name: provider-idpCreateOIDC
  path: /v1/provider
- description: Axway Remove Consumer IdP
  method: DELETE
  name: provider-idpRemove
  path: /v1/provider
- description: Axway Update Consumer IdP
  method: PUT
  name: provider-idpUpdate
  path: /v1/provider
- description: Axway Update Consumer Organization
  method: PUT
  name: provider-consumerUpdate
  path: /v1/provider
- description: Axway Find Consumer Organization
  method: GET
  name: provider-consumerFindOne
  path: /v1/provider
- description: Axway Delete a Consumer Organization
  method: DELETE
  name: provider-consumerRemove
  path: /v1/provider
- description: Axway Create Consumer Organization
  method: POST
  name: provider-consumerCreate
  path: /v1/provider
- description: Axway Find Consumer Organizations
  method: GET
  name: provider-consumerFind
  path: /v1/provider
- description: Axway Get Marketplace Activity
  method: GET
  name: provider-activity
  path: /v1/provider
- description: Axway Get Provider Marketplace
  method: GET
  name: provider-findOne
  path: /v1/provider
- description: Axway Delete Provider Marketplace
  method: DELETE
  name: provider-remove
  path: /v1/provider
- description: Axway Update Provider Marketplace
  method: PUT
  name: provider-update
  path: /v1/provider
personas: []
provider_name: Axway
provider_slug: axway
search_terms:
- org userFindOne
- provider idpCreateSAML
- provider idpUpdate
- org stats
- integration
- axway get all domains
- org domainCreate
- provider create
- env remove
- env create
- axway consolidate domain users
- axway find consumer organization
- axway create consumer oidc idp
- security
- axway delete provider marketplace
- org domainRemove
- provider findOne
- env find
- subscription operations
- axway sets the primary contract for the org
- org operations
- axway initiates oauth 2.0 auth
- axway get marketplace activity
- org userCreate
- axway start domain ownership process
- api management
- axway confirm domain idp association
- axway remove user
- entitlement operations
- axway find environment
- axway enable idp for a domain
- org findOneSubscription
- axway trigger domain association flow
- axway update consumer organization
- axway get organization
- org domainConfirm
- axway get provider marketplace
- org domainEnable
- org domainFind
- axway
- org userFind
- axway delete organization
- axway create consumer saml v2.0 idp
- org userUpdate
- axway delete a consumer organization
- env update
- provider idpRemove
- axway get provider marketplaces
- axway find subscriptions
- org findEnvs
- env operations
- axway update environment
- axway find consumer organizations
- provider findOnboarding
- provider consumerUpdate
- entitlement find
- axway create environment
- org findSubscriptions
- org domainConsolidate
- env findOne
- org userRemove
- provider oauthConfirm
- provider consumerCreate
- organization
- axway remove consumer idp
- axway get entitlement meta
- axway get organization stats
- provider oauthCallback
- provider consumerRemove
- axway add user
- org findOne
- axway concludes oauth 2.0 auth
- axway update provider marketplace
- axway associate subdomain to parent domain idp
- provider oauthAuthorize
- provider idpCreateOIDC
- axway find organization environments
- axway get members
- provider consumerFind
- axway update organization
- provider consumerFindOne
- administration
- domain operations
- provider update
- axway update consumer idp
- axway oauth 2.0 auth signup confirmation
- axway delete environment
- provider activity
- axway find subscription
- enterprise
- axway find environments
- org domainDissociate
- axway update org member association
- axway get org user
- org remove
- provider remove
- org domainAssociateSubdomain
- provider find
- org update
- org domainAssociateConfirm
- org userPrimary
- axway remove domain association
- provider operations
- axway confirm domain ownership
- org domainAssociate
- axway get provider marketplace onboarding settings
- axway create consumer organization
- axway create provider marketplace
slug: organization-management
source_filename: organization-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Axway Organization Management\n  description: Manage organizations, subscriptions, domains, entitlements, and environments on the Axway Amplify platform.\n  tags:\n  - Axway\n  - Organization\n  - Enterprise\n  - Administration\n  created: '2026-04-21'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AXWAY_BEARER_TOKEN: AXWAY_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: amplify-platform\n    baseUri: https://platform.axway.com/api/v1\n    description: Axway Amplify Platform API v1\n    authentication:\n      type: bearer\n      token: '{{env.AXWAY_BEARER_TOKEN}}'\n    resources:\n    - name: aca\n      path: /aca\n      description: Aca management operations\n      operations:\n      - name: aca-setMetadata\n        method: PUT\n        description: Axway Set Metadata by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: aca_id\n          in: path\n          type: string\n          required: true\n          description: aca_id parameter\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name parameter\n        body:\n          type: json\n          data: {}\n      - name: aca-findOne\n        method: GET\n        description: Axway Find Crash Record by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n\
  \        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: aca_id\n          in: path\n          type: string\n          required: true\n          description: aca_id parameter\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n    - name: activity\n      path: /activity\n      description: Activity management operations\n      operations:\n      - name: activity-findEvents\n        method: GET\n        description: Axway Get Activity Event Names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n \
  \         description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: authorization\n          in: header\n          type: string\n          required: false\n          description: authorization parameter\n      - name: activity-find\n        method: GET\n        description: Axway Get Activity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_guid\n          in: query\n          type: string\n          required: false\n          description: app_guid parameter\n        - name: contexts\n          in:\
  \ query\n          type: array\n          required: false\n          description: contexts parameter\n        - name: data\n          in: query\n          type: boolean\n          required: false\n          description: data parameter\n        - name: enrich\n          in: query\n          type: boolean\n          required: false\n          description: enrich parameter\n        - name: exclude_contexts\n          in: query\n          type: array\n          required: false\n          description: exclude_contexts parameter\n        - name: from\n          in: query\n          type: number\n          required: false\n          description: from parameter\n        - name: org_id\n          in: query\n          type: string\n          required: false\n          description: org_id parameter\n        - name: redact\n          in: query\n          type: boolean\n          required: false\n          description: redact parameter\n        - name: sort\n          in: query\n          type: number\n\
  \          required: false\n          description: sort parameter\n        - name: term\n          in: query\n          type: string\n          required: false\n          description: term parameter\n        - name: to\n          in: query\n          type: number\n          required: false\n          description: to parameter\n        - name: user_guid\n          in: query\n          type: string\n          required: false\n          description: user_guid parameter\n        - name: user_messages\n          in: query\n          type: boolean\n          required: false\n          description: user_messages parameter\n        - name: limit\n          in: query\n          type: number\n          required: false\n          description: limit parameter\n        - name: page\n          in: query\n          type: number\n          required: false\n          description: page parameter\n        - name: skip\n          in: query\n          type: number\n          required: false\n          description:\
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
  \ false\n          descrip\n\n# --- truncated at 32 KB (133 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/axway/refs/heads/main/capabilities/organization-management.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/axway/refs/heads/main/capabilities/organization-management.yaml
tags:
- Axway
- Organization
- Enterprise
- Administration
tools:
- description: Axway Find Organization Environments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-findEnvs
- description: Axway Sets the Primary Contract for the Org
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: org-userPrimary
- description: Axway Get Org User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-userFindOne
- description: Axway Remove User
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: org-userRemove
- description: Axway Update Org Member Association
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: org-userUpdate
- description: Axway Add User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: org-userCreate
- description: Axway Get Members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-userFind
- description: Axway Get Organization Stats
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-stats
- description: Axway Get Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-findOne
- description: Axway Delete Organization
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: org-remove
- description: Axway Update Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: org-update
- description: Axway Trigger Domain Association Flow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: org-domainAssociate
- description: Axway Associate Subdomain to Parent Domain IdP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: org-domainAssociateSubdomain
- description: Axway Enable IdP for a Domain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: org-domainEnable
- description: Axway Remove Domain Association
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: org-domainDissociate
- description: Axway Consolidate Domain Users
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: org-domainConsolidate
- description: Axway Confirm Domain Ownership
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: org-domainConfirm
- description: Axway Remove Domain Association
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: org-domainRemove
- description: Axway Confirm Domain IdP Association
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: org-domainAssociateConfirm
- description: Axway Start Domain Ownership Process
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: org-domainCreate
- description: Axway Get All Domains
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-domainFind
- description: Axway Find Subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-findOneSubscription
- description: Axway Find Subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: org-findSubscriptions
- description: Axway Get Entitlement Meta
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: entitlement-find
- description: Axway Create Environment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: env-create
- description: Axway Find Environments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: env-find
- description: Axway Find Environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: env-findOne
- description: Axway Delete Environment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: env-remove
- description: Axway Update Environment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: env-update
- description: Axway Create Provider Marketplace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provider-create
- description: Axway Get Provider Marketplaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: provider-find
- description: Axway Get Provider Marketplace Onboarding Settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: provider-findOnboarding
- description: Axway OAuth 2.0 Auth Signup Confirmation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provider-oauthConfirm
- description: Axway Concludes OAuth 2.0 Auth
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: provider-oauthCallback
- description: Axway Initiates OAuth 2.0 Auth
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: provider-oauthAuthorize
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
- description: Axway Update Consumer Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: provider-consumerUpdate
- description: Axway Find Consumer Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: provider-consumerFindOne
- description: Axway Delete a Consumer Organization
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: provider-consumerRemove
- description: Axway Create Consumer Organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provider-consumerCreate
- description: Axway Find Consumer Organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: provider-consumerFind
- description: Axway Get Marketplace Activity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: provider-activity
- description: Axway Get Provider Marketplace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: provider-findOne
- description: Axway Delete Provider Marketplace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: provider-remove
- description: Axway Update Provider Marketplace
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: provider-update
---
