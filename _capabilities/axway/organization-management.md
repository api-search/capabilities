---
categories: []
consumed_apis:
- amplify-platform
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
- org domainAssociateConfirm
- axway find organization environments
- axway start domain ownership process
- axway remove consumer idp
- axway initiates oauth 2.0 auth
- axway find subscription
- entitlement find
- axway find consumer organization
- axway update consumer idp
- org userCreate
- axway get provider marketplaces
- axway update org member association
- org remove
- axway remove domain association
- axway delete organization
- org findOne
- org stats
- axway trigger domain association flow
- axway get marketplace activity
- integration
- enterprise
- axway enable idp for a domain
- org domainCreate
- env remove
- axway create consumer organization
- provider consumerFind
- axway remove user
- axway get org user
- domain operations
- entitlement operations
- provider oauthConfirm
- org domainAssociateSubdomain
- provider consumerFindOne
- subscription operations
- axway find environments
- env update
- env operations
- axway find environment
- org domainDissociate
- provider oauthAuthorize
- axway add user
- provider oauthCallback
- axway get organization
- org domainConfirm
- provider idpCreateSAML
- axway update organization
- org domainAssociate
- org userUpdate
- axway get organization stats
- provider idpCreateOIDC
- env findOne
- axway delete environment
- security
- org findEnvs
- provider activity
- axway associate subdomain to parent domain idp
- axway
- provider create
- org domainRemove
- axway sets the primary contract for the org
- org userPrimary
- org update
- administration
- axway confirm domain ownership
- axway consolidate domain users
- axway get provider marketplace onboarding settings
- axway create provider marketplace
- org findSubscriptions
- api management
- org userFindOne
- organization
- axway concludes oauth 2.0 auth
- org domainEnable
- axway find consumer organizations
- axway oauth 2.0 auth signup confirmation
- axway update provider marketplace
- axway find subscriptions
- provider find
- axway confirm domain idp association
- provider findOne
- provider update
- org operations
- org domainConsolidate
- provider operations
- org userRemove
- axway update environment
- axway create environment
- axway delete a consumer organization
- org findOneSubscription
- axway get provider marketplace
- provider findOnboarding
- env find
- axway create consumer saml v2.0 idp
- axway get all domains
- axway get entitlement meta
- provider idpUpdate
- provider consumerUpdate
- provider idpRemove
- provider consumerCreate
- axway get members
- axway delete provider marketplace
- org domainFind
- axway update consumer organization
- env create
- provider consumerRemove
- axway create consumer oidc idp
- provider remove
- org userFind
slug: organization-management
source_filename: organization-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Axway Organization Management\n  description: Manage organizations, subscriptions, domains, entitlements, and environments on the Axway Amplify platform.\n  tags:\n  - Axway\n  - Organization\n  - Enterprise\n  - Administration\n  created: '2026-04-21'\n  modified: '2026-04-21'\nbinds:\n- namespace: env\n  keys:\n    AXWAY_BEARER_TOKEN: AXWAY_BEARER_TOKEN\ncapability:\n  consumes:\n  - import: amplify-platform\n    location: ./shared/amplify-platform.yaml\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: organization-management-api\n    description: Unified REST API for manage organizations, subscriptions, domains, entitlements, and environments on the axway amplify platform.\n    resources:\n    - path: /v1/org\n      name: org\n      description: Org operations\n      operations:\n      - method: GET\n        name: org-findEnvs\n        description: Axway Find Organization Environments\n        call: amplify-platform.org-findEnvs\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: org-userPrimary\n        description: Axway Sets the Primary Contract for the Org\n        call: amplify-platform.org-userPrimary\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: org-userFindOne\n        description: Axway Get Org User\n        call: amplify-platform.org-userFindOne\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: org-userRemove\n        description: Axway Remove User\n        call: amplify-platform.org-userRemove\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: org-userUpdate\n        description: Axway Update Org Member Association\n        call: amplify-platform.org-userUpdate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n  \
  \      name: org-userCreate\n        description: Axway Add User\n        call: amplify-platform.org-userCreate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: org-userFind\n        description: Axway Get Members\n        call: amplify-platform.org-userFind\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: org-stats\n        description: Axway Get Organization Stats\n        call: amplify-platform.org-stats\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: org-findOne\n        description: Axway Get Organization\n        call: amplify-platform.org-findOne\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: org-remove\n        description: Axway Delete Organization\n        call: amplify-platform.org-remove\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n      - method: PUT\n        name: org-update\n        description: Axway Update Organization\n        call: amplify-platform.org-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/domain\n      name: domain\n      description: Domain operations\n      operations:\n      - method: POST\n        name: org-domainAssociate\n        description: Axway Trigger Domain Association Flow\n        call: amplify-platform.org-domainAssociate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: org-domainAssociateSubdomain\n        description: Axway Associate Subdomain to Parent Domain IdP\n        call: amplify-platform.org-domainAssociateSubdomain\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: org-domainEnable\n        description: Axway Enable IdP for a Domain\n        call: amplify-platform.org-domainEnable\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: org-domainDissociate\n        description: Axway Remove Domain Association\n        call: amplify-platform.org-domainDissociate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: org-domainConsolidate\n        description: Axway Consolidate Domain Users\n        call: amplify-platform.org-domainConsolidate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: org-domainConfirm\n        description: Axway Confirm Domain Ownership\n        call: amplify-platform.org-domainConfirm\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: org-domainRemove\n        description: Axway Remove Domain Association\n        call: amplify-platform.org-domainRemove\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n      - method: PUT\n        name: org-domainAssociateConfirm\n        description: Axway Confirm Domain IdP Association\n        call: amplify-platform.org-domainAssociateConfirm\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: org-domainCreate\n        description: Axway Start Domain Ownership Process\n        call: amplify-platform.org-domainCreate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: org-domainFind\n        description: Axway Get All Domains\n        call: amplify-platform.org-domainFind\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscription\n      name: subscription\n      description: Subscription operations\n      operations:\n      - method: GET\n        name: org-findOneSubscription\n        description: Axway Find Subscription\n        call: amplify-platform.org-findOneSubscription\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: org-findSubscriptions\n        description: Axway Find Subscriptions\n        call: amplify-platform.org-findSubscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entitlement\n      name: entitlement\n      description: Entitlement operations\n      operations:\n      - method: GET\n        name: entitlement-find\n        description: Axway Get Entitlement Meta\n        call: amplify-platform.entitlement-find\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/env\n      name: env\n      description: Env operations\n      operations:\n      - method: POST\n        name: env-create\n        description: Axway Create Environment\n        call: amplify-platform.env-create\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: env-find\n \
  \       description: Axway Find Environments\n        call: amplify-platform.env-find\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: env-findOne\n        description: Axway Find Environment\n        call: amplify-platform.env-findOne\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: env-remove\n        description: Axway Delete Environment\n        call: amplify-platform.env-remove\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: env-update\n        description: Axway Update Environment\n        call: amplify-platform.env-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provider\n      name: provider\n      description: Provider operations\n      operations:\n      - method: POST\n        name: provider-create\n        description: Axway Create Provider\
  \ Marketplace\n        call: amplify-platform.provider-create\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: provider-find\n        description: Axway Get Provider Marketplaces\n        call: amplify-platform.provider-find\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: provider-findOnboarding\n        description: Axway Get Provider Marketplace Onboarding Settings\n        call: amplify-platform.provider-findOnboarding\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: provider-oauthConfirm\n        description: Axway OAuth 2.0 Auth Signup Confirmation\n        call: amplify-platform.provider-oauthConfirm\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: provider-oauthCallback\n        description: Axway Concludes OAuth 2.0 Auth\n        call:\
  \ amplify-platform.provider-oauthCallback\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: provider-oauthAuthorize\n        description: Axway Initiates OAuth 2.0 Auth\n        call: amplify-platform.provider-oauthAuthorize\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: provider-idpCreateSAML\n        description: Axway Create Consumer SAML V2.0 IdP\n        call: amplify-platform.provider-idpCreateSAML\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: provider-idpCreateOIDC\n        description: Axway Create Consumer OIDC IdP\n        call: amplify-platform.provider-idpCreateOIDC\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: provider-idpRemove\n        description: Axway Remove Consumer IdP\n        call: amplify-platform.provider-idpRemove\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: provider-idpUpdate\n        description: Axway Update Consumer IdP\n        call: amplify-platform.provider-idpUpdate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: provider-consumerUpdate\n        description: Axway Update Consumer Organization\n        call: amplify-platform.provider-consumerUpdate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: provider-consumerFindOne\n        description: Axway Find Consumer Organization\n        call: amplify-platform.provider-consumerFindOne\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: provider-consumerRemove\n        description: Axway Delete a Consumer Organization\n        call: amplify-platform.provider-consumerRemove\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: provider-consumerCreate\n        description: Axway Create Consumer Organization\n        call: amplify-platform.provider-consumerCreate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: provider-consumerFind\n        description: Axway Find Consumer Organizations\n        call: amplify-platform.provider-consumerFind\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: provider-activity\n        description: Axway Get Marketplace Activity\n        call: amplify-platform.provider-activity\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: provider-findOne\n        description: Axway Get Provider Marketplace\n        call: amplify-platform.provider-findOne\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \     - method: DELETE\n        name: provider-remove\n        description: Axway Delete Provider Marketplace\n        call: amplify-platform.provider-remove\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: provider-update\n        description: Axway Update Provider Marketplace\n        call: amplify-platform.provider-update\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: organization-management-mcp\n    transport: http\n    description: MCP server for AI-assisted manage organizations, subscriptions, domains, entitlements, and environments on the axway amplify platform.\n    tools:\n    - name: org-findEnvs\n      description: Axway Find Organization Environments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-findEnvs\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: org-userPrimary\n      description: Axway Sets the Primary Contract for the Org\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-userPrimary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-userFindOne\n      description: Axway Get Org User\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-userFindOne\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-userRemove\n      description: Axway Remove User\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.org-userRemove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-userUpdate\n      description: Axway Update Org Member Association\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: true\n      call: amplify-platform.org-userUpdate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-userCreate\n      description: Axway Add User\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.org-userCreate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-userFind\n      description: Axway Get Members\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-userFind\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-stats\n      description: Axway Get Organization Stats\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-stats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-findOne\n      description: Axway Get\
  \ Organization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-findOne\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-remove\n      description: Axway Delete Organization\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.org-remove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-update\n      description: Axway Update Organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-update\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-domainAssociate\n      description: Axway Trigger Domain Association Flow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.org-domainAssociate\n   \
  \   outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-domainAssociateSubdomain\n      description: Axway Associate Subdomain to Parent Domain IdP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.org-domainAssociateSubdomain\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-domainEnable\n      description: Axway Enable IdP for a Domain\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.org-domainEnable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-domainDissociate\n      description: Axway Remove Domain Association\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.org-domainDissociate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-domainConsolidate\n\
  \      description: Axway Consolidate Domain Users\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.org-domainConsolidate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-domainConfirm\n      description: Axway Confirm Domain Ownership\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.org-domainConfirm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-domainRemove\n      description: Axway Remove Domain Association\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.org-domainRemove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-domainAssociateConfirm\n      description: Axway Confirm Domain IdP Association\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: true\n      call: amplify-platform.org-domainAssociateConfirm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-domainCreate\n      description: Axway Start Domain Ownership Process\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.org-domainCreate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-domainFind\n      description: Axway Get All Domains\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-domainFind\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-findOneSubscription\n      description: Axway Find Subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-findOneSubscription\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: org-findSubscriptions\n      description: Axway Find Subscriptions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-findSubscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: entitlement-find\n      description: Axway Get Entitlement Meta\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.entitlement-find\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: env-create\n      description: Axway Create Environment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.env-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: env-find\n      description: Axway Find Environments\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: amplify-platform.env-find\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: env-findOne\n      description: Axway Find Environment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.env-findOne\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: env-remove\n      description: Axway Delete Environment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.env-remove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: env-update\n      description: Axway Update Environment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.env-update\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-create\n      description: Axway Create\
  \ Provider Marketplace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.provider-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-find\n      description: Axway Get Provider Marketplaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-find\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-findOnboarding\n      description: Axway Get Provider Marketplace Onboarding Settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-findOnboarding\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-oauthConfirm\n      description: Axway OAuth 2.0 Auth Signup Confirmation\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: amplify-platform.provider-oauthConfirm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-oauthCallback\n      description: Axway Concludes OAuth 2.0 Auth\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-oauthCallback\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-oauthAuthorize\n      description: Axway Initiates OAuth 2.0 Auth\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-oauthAuthorize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-idpCreateSAML\n      description: Axway Create Consumer SAML V2.0 IdP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.provider-idpCreateSAML\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: provider-idpCreateOIDC\n      description: Axway Create Consumer OIDC IdP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.provider-idpCreateOIDC\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-idpRemove\n      description: Axway Remove Consumer IdP\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.provider-idpRemove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-idpUpdate\n      description: Axway Update Consumer IdP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-idpUpdate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-consumerUpdate\n      description: Axway Update Consumer Organization\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-consumerUpdate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-consumerFindOne\n      description: Axway Find Consumer Organization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-consumerFindOne\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-consumerRemove\n      description: Axway Delete a Consumer Organization\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.provider-consumerRemove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-consumerCreate\n      description: Axway Create Consumer Organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: amplify-platform.provider-consumerCreate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-consumerFind\n      description: Axway Find Consumer Organizations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-consumerFind\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-activity\n      description: Axway Get Marketplace Activity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-activity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-findOne\n      description: Axway Get Provider Marketplace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-findOne\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: provider-remove\n      description: Axway Delete Provider Marketplace\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.provider-remove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-update\n      description: Axway Update Provider Marketplace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-update\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
