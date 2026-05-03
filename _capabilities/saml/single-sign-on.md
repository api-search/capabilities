---
api_specs:
- filename: saml-sso-bindings.yml
  format: yaml
  label: saml-sso
  slug: saml-sso
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/saml/refs/heads/main/openapi/saml-sso-bindings.yml
categories: []
consumed_apis:
- saml-sso
description: 'SAML 2.0 Single Sign-On workflow capability implementing the complete SSO lifecycle: SP-initiated SSO via HTTP Redirect Binding and HTTP POST Binding, Assertion Consumer Service (ACS) processing, Single Logout (SLO), and metadata exchange. Designed for identity and access management engineers integrating SAML-based federation between Identity Providers and Service Providers.'
layout: capability
name: SAML 2.0 Single Sign-On
operations:
- description: Initiate SAML SSO via HTTP Redirect Binding
  method: GET
  name: initiate-sso-redirect
  path: /v1/sso/redirect
- description: Submit SAML AuthnRequest via HTTP POST Binding
  method: POST
  name: initiate-sso-post
  path: /v1/sso/post
- description: Process SAML Response at Assertion Consumer Service
  method: POST
  name: process-saml-response
  path: /v1/acs
- description: Initiate or process SAML Single Logout
  method: GET
  name: initiate-slo
  path: /v1/slo
- description: Retrieve SAML EntityDescriptor metadata from Identity Provider
  method: GET
  name: get-idp-metadata
  path: /v1/metadata
personas: []
provider_name: SAML
provider_slug: saml
search_terms:
- authentication
- open standard
- initiate saml sso via http redirect binding
- process saml response at assertion consumer service
- submit saml authnrequest via http post binding
- saml
- assertion consumer service - process incoming saml responses from idp
- initiate sp-to-idp sso using http post binding
- saml entitydescriptor metadata for federation configuration
- security
- process acs response
- single logout - initiate or receive saml logout
- process saml response
- retrieve saml entitydescriptor metadata from identity provider
- initiate slo
- initiate sso post
- initiate sp-to-idp sso using http redirect binding
- single sign-on
- get idp metadata
- initiate saml 2.0 sso using the http redirect binding with a deflated authnrequest
- identity management
- initiate saml single logout via http redirect binding
- federation
- initiate saml 2.0 sso using the http post binding with a base64-encoded authnrequest
- sso
- process an incoming saml response at the assertion consumer service endpoint
- xml
- oasis
- initiate or process saml single logout
- initiate single logout
- authorization
- initiate sso redirect
- retrieve saml 2.0 entitydescriptor metadata from the identity provider for federation setup
slug: single-sign-on
source_filename: single-sign-on.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAML 2.0 Single Sign-On\"\n  description: >-\n    SAML 2.0 Single Sign-On workflow capability implementing the complete SSO\n    lifecycle: SP-initiated SSO via HTTP Redirect Binding and HTTP POST Binding,\n    Assertion Consumer Service (ACS) processing, Single Logout (SLO), and\n    metadata exchange. Designed for identity and access management engineers\n    integrating SAML-based federation between Identity Providers and Service Providers.\n  tags:\n    - Authentication\n    - Federation\n    - Identity Management\n    - OASIS\n    - SAML\n    - Security\n    - Single Sign-On\n    - SSO\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAML_IDP_BASE_URL: SAML_IDP_BASE_URL\n\ncapability:\n  consumes:\n    - import: saml-sso\n      location: ./shared/saml-sso-bindings.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: single-sign-on-api\n      description:\
  \ \"Unified REST API for SAML 2.0 Single Sign-On workflow implementation.\"\n      resources:\n        - path: /v1/sso/redirect\n          name: sso-redirect\n          description: \"Initiate SP-to-IdP SSO using HTTP Redirect Binding\"\n          operations:\n            - method: GET\n              name: initiate-sso-redirect\n              description: \"Initiate SAML SSO via HTTP Redirect Binding\"\n              call: \"saml-sso.sso-redirect-binding\"\n              with:\n                SAMLRequest: \"rest.SAMLRequest\"\n                RelayState: \"rest.RelayState\"\n                SigAlg: \"rest.SigAlg\"\n                Signature: \"rest.Signature\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sso/post\n          name: sso-post\n          description: \"Initiate SP-to-IdP SSO using HTTP POST Binding\"\n          operations:\n            - method: POST\n              name: initiate-sso-post\n       \
  \       description: \"Submit SAML AuthnRequest via HTTP POST Binding\"\n              call: \"saml-sso.sso-post-binding\"\n              with:\n                SAMLRequest: \"rest.SAMLRequest\"\n                RelayState: \"rest.RelayState\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/acs\n          name: acs\n          description: \"Assertion Consumer Service - process incoming SAML Responses from IdP\"\n          operations:\n            - method: POST\n              name: process-saml-response\n              description: \"Process SAML Response at Assertion Consumer Service\"\n              call: \"saml-sso.assertion-consumer-service\"\n              with:\n                SAMLResponse: \"rest.SAMLResponse\"\n                RelayState: \"rest.RelayState\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/slo\n          name: slo\n  \
  \        description: \"Single Logout - initiate or receive SAML logout\"\n          operations:\n            - method: GET\n              name: initiate-slo\n              description: \"Initiate or process SAML Single Logout\"\n              call: \"saml-sso.slo-redirect-binding\"\n              with:\n                SAMLRequest: \"rest.SAMLRequest\"\n                SAMLResponse: \"rest.SAMLResponse\"\n                RelayState: \"rest.RelayState\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metadata\n          name: metadata\n          description: \"SAML EntityDescriptor metadata for federation configuration\"\n          operations:\n            - method: GET\n              name: get-idp-metadata\n              description: \"Retrieve SAML EntityDescriptor metadata from Identity Provider\"\n              call: \"saml-sso.get-metadata\"\n              outputParameters:\n                - type: object\n \
  \                 mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: single-sign-on-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAML SSO configuration and troubleshooting.\"\n      tools:\n        - name: initiate-sso-redirect\n          description: \"Initiate SAML 2.0 SSO using the HTTP Redirect Binding with a deflated AuthnRequest\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"saml-sso.sso-redirect-binding\"\n          with:\n            SAMLRequest: \"tools.SAMLRequest\"\n            RelayState: \"tools.RelayState\"\n            SigAlg: \"tools.SigAlg\"\n            Signature: \"tools.Signature\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: initiate-sso-post\n          description: \"Initiate SAML 2.0 SSO using the HTTP POST Binding with a base64-encoded AuthnRequest\"\n          hints:\n\
  \            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"saml-sso.sso-post-binding\"\n          with:\n            SAMLRequest: \"tools.SAMLRequest\"\n            RelayState: \"tools.RelayState\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: process-acs-response\n          description: \"Process an incoming SAML Response at the Assertion Consumer Service endpoint\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"saml-sso.assertion-consumer-service\"\n          with:\n            SAMLResponse: \"tools.SAMLResponse\"\n            RelayState: \"tools.RelayState\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: initiate-single-logout\n          description: \"Initiate SAML Single Logout via HTTP Redirect Binding\"\n          hints:\n          \
  \  readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"saml-sso.slo-redirect-binding\"\n          with:\n            SAMLRequest: \"tools.SAMLRequest\"\n            RelayState: \"tools.RelayState\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-idp-metadata\n          description: \"Retrieve SAML 2.0 EntityDescriptor metadata from the Identity Provider for federation setup\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"saml-sso.get-metadata\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/saml/refs/heads/main/capabilities/single-sign-on.yaml
tags:
- Authentication
- Federation
- Identity Management
- OASIS
- SAML
- Security
- Single Sign-On
- SSO
tools:
- description: Initiate SAML 2.0 SSO using the HTTP Redirect Binding with a deflated AuthnRequest
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initiate-sso-redirect
- description: Initiate SAML 2.0 SSO using the HTTP POST Binding with a base64-encoded AuthnRequest
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initiate-sso-post
- description: Process an incoming SAML Response at the Assertion Consumer Service endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: process-acs-response
- description: Initiate SAML Single Logout via HTTP Redirect Binding
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: initiate-single-logout
- description: Retrieve SAML 2.0 EntityDescriptor metadata from the Identity Provider for federation setup
  hints:
    openWorld: true
    readOnly: true
  name: get-idp-metadata
---
