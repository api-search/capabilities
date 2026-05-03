---
categories: []
consumed_apis:
- amplify-platform
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
- axway create oidc idp
- provider idpCreateSAML
- saml
- org idpUpdate
- security
- provider idpUpdate
- axway remove organization idp config
- axway get public idp signing or encryption certificate
- axway
- org idpRemove
- provider idpFind
- api management
- provider idpRemove
- org idpCreateOIDC
- org idpDownloadDescriptor
- org idpAssociate
- integration
- axway update organizations custom idp
- axway associate with another organizations idp
- org idpFind
- axway get all organization idps
- provider idpCreateOIDC
- axway create consumer oidc idp
- axway reload saml validating certificates
- axway get idp
- idp operations
- enterprise
- axway get consumer idp
- sso
- org idpReloadKeys
- axway remove consumer idp
- axway create consumer saml v2.0 idp
- org idpFindOne
- axway update consumer idp
- axway create saml v2.0 idp
- oidc
- org idpDownloadCert
- identity provider
- axway get idp descriptor
- org idpCreateSAML
slug: identity-provider-management
source_filename: identity-provider-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Axway Identity Provider Management\n  description: Configure and manage SAML and OIDC identity providers for SSO across the Axway Amplify platform.\n  tags:\n  - Axway\n  - Identity Provider\n  - SAML\n  - OIDC\n  - SSO\n  created: '2026-04-21'\n  modified: '2026-04-21'\nbinds:\n- namespace: env\n  keys:\n    AXWAY_BEARER_TOKEN: AXWAY_BEARER_TOKEN\ncapability:\n  consumes:\n  - import: amplify-platform\n    location: ./shared/amplify-platform.yaml\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: identity-provider-management-api\n    description: Unified REST API for configure and manage saml and oidc identity providers for sso across the axway amplify platform.\n    resources:\n    - path: /v1/idp\n      name: idp\n      description: Idp operations\n      operations:\n      - method: POST\n        name: provider-idpCreateSAML\n        description: Axway Create Consumer SAML V2.0 IdP\n        call: amplify-platform.provider-idpCreateSAML\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: provider-idpCreateOIDC\n        description: Axway Create Consumer OIDC IdP\n        call: amplify-platform.provider-idpCreateOIDC\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: provider-idpFind\n        description: Axway Get Consumer IdP\n        call: amplify-platform.provider-idpFind\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: provider-idpRemove\n        description: Axway Remove Consumer IdP\n        call: amplify-platform.provider-idpRemove\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: provider-idpUpdate\n        description: Axway Update Consumer IdP\n        call: amplify-platform.provider-idpUpdate\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \    - method: POST\n        name: org-idpCreateSAML\n        description: Axway Create SAML V2.0 IdP\n        call: amplify-platform.org-idpCreateSAML\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: org-idpCreateOIDC\n        description: Axway Create OIDC IdP\n        call: amplify-platform.org-idpCreateOIDC\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: org-idpReloadKeys\n        description: Axway Reload SAML Validating Certificates\n        call: amplify-platform.org-idpReloadKeys\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: org-idpDownloadDescriptor\n        description: Axway Get IdP Descriptor\n        call: amplify-platform.org-idpDownloadDescriptor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: org-idpDownloadCert\n        description:\
  \ Axway Get Public IdP Signing or Encryption Certificate\n        call: amplify-platform.org-idpDownloadCert\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: org-idpAssociate\n        description: Axway Associate with Another Organizations IdP\n        call: amplify-platform.org-idpAssociate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: org-idpFindOne\n        description: Axway Get IdP\n        call: amplify-platform.org-idpFindOne\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: org-idpRemove\n        description: Axway Remove Organization IdP Config\n        call: amplify-platform.org-idpRemove\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: org-idpUpdate\n        description: Axway Update Organizations Custom IdP\n        call: amplify-platform.org-idpUpdate\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: org-idpFind\n        description: Axway Get All Organization IdPs\n        call: amplify-platform.org-idpFind\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: identity-provider-management-mcp\n    transport: http\n    description: MCP server for AI-assisted configure and manage saml and oidc identity providers for sso across the axway amplify platform.\n    tools:\n    - name: provider-idpCreateSAML\n      description: Axway Create Consumer SAML V2.0 IdP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.provider-idpCreateSAML\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-idpCreateOIDC\n      description: Axway Create Consumer OIDC IdP\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: amplify-platform.provider-idpCreateOIDC\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-idpFind\n      description: Axway Get Consumer IdP\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-idpFind\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-idpRemove\n      description: Axway Remove Consumer IdP\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.provider-idpRemove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provider-idpUpdate\n      description: Axway Update Consumer IdP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.provider-idpUpdate\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: org-idpCreateSAML\n      description: Axway Create SAML V2.0 IdP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.org-idpCreateSAML\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-idpCreateOIDC\n      description: Axway Create OIDC IdP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.org-idpCreateOIDC\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-idpReloadKeys\n      description: Axway Reload SAML Validating Certificates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-idpReloadKeys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-idpDownloadDescriptor\n      description: Axway Get IdP Descriptor\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: amplify-platform.org-idpDownloadDescriptor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-idpDownloadCert\n      description: Axway Get Public IdP Signing or Encryption Certificate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-idpDownloadCert\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-idpAssociate\n      description: Axway Associate with Another Organizations IdP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.org-idpAssociate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-idpFindOne\n      description: Axway Get IdP\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-idpFindOne\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-idpRemove\n      description: Axway Remove Organization IdP Config\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.org-idpRemove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-idpUpdate\n      description: Axway Update Organizations Custom IdP\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-idpUpdate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: org-idpFind\n      description: Axway Get All Organization IdPs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.org-idpFind\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
