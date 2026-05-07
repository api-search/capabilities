---
categories: []
consumed_apis: []
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
- oasis
- initiate sp-to-idp sso using http redirect binding
- initiate or process saml single logout
- process an incoming saml response at the assertion consumer service endpoint
- open standard
- initiate sp-to-idp sso using http post binding
- saml
- initiate saml sso via http redirect binding
- initiate sso redirect
- submit saml authnrequest via http post binding
- saml entitydescriptor metadata for federation configuration
- retrieve saml 2.0 entitydescriptor metadata from the identity provider for federation setup
- identity management
- authentication
- sso
- initiate saml single logout via http redirect binding
- get idp metadata
- process saml response
- single logout - initiate or receive saml logout
- initiate sso post
- assertion consumer service - process incoming saml responses from idp
- process acs response
- xml
- initiate slo
- initiate saml 2.0 sso using the http post binding with a base64-encoded authnrequest
- federation
- authorization
- initiate single logout
- retrieve saml entitydescriptor metadata from identity provider
- process saml response at assertion consumer service
- single sign-on
- security
- initiate saml 2.0 sso using the http redirect binding with a deflated authnrequest
slug: single-sign-on
source_filename: single-sign-on.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAML 2.0 Single Sign-On\n  description: 'SAML 2.0 Single Sign-On workflow capability implementing the complete SSO lifecycle: SP-initiated SSO via\n    HTTP Redirect Binding and HTTP POST Binding, Assertion Consumer Service (ACS) processing, Single Logout (SLO), and metadata\n    exchange. Designed for identity and access management engineers integrating SAML-based federation between Identity Providers\n    and Service Providers.'\n  tags:\n  - Authentication\n  - Federation\n  - Identity Management\n  - OASIS\n  - SAML\n  - Security\n  - Single Sign-On\n  - SSO\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAML_IDP_BASE_URL: SAML_IDP_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: saml-sso\n    baseUri: '{{SAML_IDP_BASE_URL}}'\n    description: SAML 2.0 Identity Provider HTTP Bindings endpoints\n    resources:\n    - name: sso-redirect\n      path: /saml/sso/redirect\n  \
  \    description: SAML 2.0 SSO HTTP Redirect Binding for AuthnRequest initiation\n      operations:\n      - name: sso-redirect-binding\n        method: GET\n        description: SSO HTTP Redirect Binding - Initiate SAML 2.0 SSO via HTTP Redirect\n        inputParameters:\n        - name: SAMLRequest\n          in: query\n          type: string\n          required: true\n          description: Deflated, base64-encoded, URL-encoded SAML AuthnRequest XML\n        - name: RelayState\n          in: query\n          type: string\n          required: false\n          description: Opaque SP state reference (max 80 bytes)\n        - name: SigAlg\n          in: query\n          type: string\n          required: false\n          description: Algorithm URI for signature (e.g., http://www.w3.org/2001/04/xmldsig-more#rsa-sha256)\n        - name: Signature\n          in: query\n          type: string\n          required: false\n          description: Base64-encoded URL-encoded digital signature over\
  \ SAMLRequest and RelayState\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sso-post\n      path: /saml/sso/post\n      description: SAML 2.0 SSO HTTP POST Binding\n      operations:\n      - name: sso-post-binding\n        method: POST\n        description: SSO HTTP POST Binding - Submit SAML AuthnRequest or receive IdP Response\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            SAMLRequest: '{{tools.SAMLRequest}}'\n            RelayState: '{{tools.RelayState}}'\n    - name: acs\n      path: /saml/acs\n      description: Assertion Consumer Service (ACS) endpoint for receiving SAML Responses\n      operations:\n      - name: assertion-consumer-service\n        method: POST\n        description: Assertion Consumer Service (ACS) - Receive and process SAML Response\n\
  \        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            SAMLResponse: '{{tools.SAMLResponse}}'\n            RelayState: '{{tools.RelayState}}'\n    - name: slo\n      path: /saml/slo\n      description: Single Logout (SLO) HTTP Redirect Binding\n      operations:\n      - name: slo-redirect-binding\n        method: GET\n        description: SLO HTTP Redirect Binding - Initiate or receive SAML Single Logout\n        inputParameters:\n        - name: SAMLRequest\n          in: query\n          type: string\n          required: false\n          description: LogoutRequest XML (deflated and base64-encoded)\n        - name: SAMLResponse\n          in: query\n          type: string\n          required: false\n          description: LogoutResponse XML (deflated and base64-encoded)\n        - name: RelayState\n          in: query\n          type: string\n    \
  \      required: false\n          description: Opaque SP state reference\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata\n      path: /saml/metadata\n      description: SAML 2.0 EntityDescriptor metadata endpoint\n      operations:\n      - name: get-metadata\n        method: GET\n        description: SAML 2.0 Metadata Endpoint - Retrieve EntityDescriptor XML\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: single-sign-on-api\n    description: Unified REST API for SAML 2.0 Single Sign-On workflow implementation.\n    resources:\n    - path: /v1/sso/redirect\n      name: sso-redirect\n      description: Initiate SP-to-IdP SSO using HTTP Redirect Binding\n      operations:\n      - method: GET\n        name: initiate-sso-redirect\n        description: Initiate\
  \ SAML SSO via HTTP Redirect Binding\n        call: saml-sso.sso-redirect-binding\n        with:\n          SAMLRequest: rest.SAMLRequest\n          RelayState: rest.RelayState\n          SigAlg: rest.SigAlg\n          Signature: rest.Signature\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sso/post\n      name: sso-post\n      description: Initiate SP-to-IdP SSO using HTTP POST Binding\n      operations:\n      - method: POST\n        name: initiate-sso-post\n        description: Submit SAML AuthnRequest via HTTP POST Binding\n        call: saml-sso.sso-post-binding\n        with:\n          SAMLRequest: rest.SAMLRequest\n          RelayState: rest.RelayState\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/acs\n      name: acs\n      description: Assertion Consumer Service - process incoming SAML Responses from IdP\n      operations:\n      - method: POST\n        name: process-saml-response\n     \
  \   description: Process SAML Response at Assertion Consumer Service\n        call: saml-sso.assertion-consumer-service\n        with:\n          SAMLResponse: rest.SAMLResponse\n          RelayState: rest.RelayState\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/slo\n      name: slo\n      description: Single Logout - initiate or receive SAML logout\n      operations:\n      - method: GET\n        name: initiate-slo\n        description: Initiate or process SAML Single Logout\n        call: saml-sso.slo-redirect-binding\n        with:\n          SAMLRequest: rest.SAMLRequest\n          SAMLResponse: rest.SAMLResponse\n          RelayState: rest.RelayState\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metadata\n      name: metadata\n      description: SAML EntityDescriptor metadata for federation configuration\n      operations:\n      - method: GET\n        name: get-idp-metadata\n        description:\
  \ Retrieve SAML EntityDescriptor metadata from Identity Provider\n        call: saml-sso.get-metadata\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: single-sign-on-mcp\n    transport: http\n    description: MCP server for AI-assisted SAML SSO configuration and troubleshooting.\n    tools:\n    - name: initiate-sso-redirect\n      description: Initiate SAML 2.0 SSO using the HTTP Redirect Binding with a deflated AuthnRequest\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: saml-sso.sso-redirect-binding\n      with:\n        SAMLRequest: tools.SAMLRequest\n        RelayState: tools.RelayState\n        SigAlg: tools.SigAlg\n        Signature: tools.Signature\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiate-sso-post\n      description: Initiate SAML 2.0 SSO using the HTTP POST Binding with a base64-encoded AuthnRequest\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: saml-sso.sso-post-binding\n      with:\n        SAMLRequest: tools.SAMLRequest\n        RelayState: tools.RelayState\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-acs-response\n      description: Process an incoming SAML Response at the Assertion Consumer Service endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: saml-sso.assertion-consumer-service\n      with:\n        SAMLResponse: tools.SAMLResponse\n        RelayState: tools.RelayState\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiate-single-logout\n      description: Initiate SAML Single Logout via HTTP Redirect Binding\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: saml-sso.slo-redirect-binding\n      with:\n        SAMLRequest:\
  \ tools.SAMLRequest\n        RelayState: tools.RelayState\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-idp-metadata\n      description: Retrieve SAML 2.0 EntityDescriptor metadata from the Identity Provider for federation setup\n      hints:\n        readOnly: true\n        openWorld: true\n      call: saml-sso.get-metadata\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
