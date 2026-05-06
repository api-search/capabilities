---
categories: []
consumed_apis: []
description: The Certificate Manager API provides programmatic access to manage TLS certificates, certificate maps, DNS authorizations, and certificate issuance configurations for Google Cloud. It supports automated provisioning and renewal of Google-managed certificates and upload of self-managed certificates.
layout: capability
name: Google Cloud Certificate Manager API
operations:
- description: Google Cloud Certificate Manager List certificates
  method: GET
  name: listcertificates
  path: /projects/{projectId}/locations/{location}/certificates
- description: Google Cloud Certificate Manager Create a certificate
  method: POST
  name: createcertificate
  path: /projects/{projectId}/locations/{location}/certificates
- description: Google Cloud Certificate Manager List certificate maps
  method: GET
  name: listcertificatemaps
  path: /projects/{projectId}/locations/{location}/certificateMaps
- description: Google Cloud Certificate Manager List DNS authorizations
  method: GET
  name: listdnsauthorizations
  path: /projects/{projectId}/locations/{location}/dnsAuthorizations
personas: []
provider_name: Google Cloud Certificate Manager
provider_slug: google-cloud-certificate-manager
search_terms:
- google cloud certificate manager list certificates
- createcertificate
- google cloud certificate manager list certificate maps
- manager
- certificate
- cloud
- ssl
- google
- google cloud certificate manager list dns authorizations
- security
- listcertificates
- google cloud certificate manager create a certificate
- tls
- listcertificatemaps
- api
- listdnsauthorizations
- load balancing
- certificate management
- certificates
slug: google-cloud-certificate-manager-capability
source_filename: google-cloud-certificate-manager-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Certificate Manager API\n  description: The Certificate Manager API provides programmatic access to manage TLS certificates, certificate maps, DNS\n    authorizations, and certificate issuance configurations for Google Cloud. It supports automated provisioning and renewal\n    of Google-managed certificates and upload of self-managed certificates.\n  tags:\n  - Google\n  - Cloud\n  - Certificate\n  - Manager\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-certificate-manager\n    baseUri: https://certificatemanager.googleapis.com/v1\n    description: Google Cloud Certificate Manager API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_CERTIFICATE_MANAGER_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-certificat\n      path: /projects/{projectId}/locations/{location}/certificates\n\
  \      operations:\n      - name: listcertificates\n        method: GET\n        description: Google Cloud Certificate Manager List certificates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcertificate\n        method: POST\n        description: Google Cloud Certificate Manager Create a certificate\n        inputParameters:\n        - name: certificateId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-certificat\n      path: /projects/{projectId}/locations/{location}/certificateMaps\n      operations:\n      - name: listcertificatemaps\n        method: GET\n        description: Google Cloud Certificate Manager List certificate maps\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-dnsauthori\n      path: /projects/{projectId}/locations/{location}/dnsAuthorizations\n      operations:\n      - name: listdnsauthorizations\n        method: GET\n        description: Google Cloud Certificate Manager List DNS authorizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-certificate-manager-rest\n    description: REST adapter for Google Cloud Certificate Manager API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/certificates\n      name: listcertificates\n      operations:\n      - method: GET\n        name: listcertificates\n        description: Google Cloud Certificate Manager List certificates\n        call: google-cloud-certificate-manager.listcertificates\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/certificates\n      name: createcertificate\n      operations:\n      - method: POST\n        name: createcertificate\n        description: Google Cloud Certificate Manager Create a certificate\n        call: google-cloud-certificate-manager.createcertificate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/certificateMaps\n      name: listcertificatemaps\n      operations:\n      - method: GET\n        name: listcertificatemaps\n        description: Google Cloud Certificate Manager List certificate maps\n        call: google-cloud-certificate-manager.listcertificatemaps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/dnsAuthorizations\n      name: listdnsauthorizations\n      operations:\n      - method: GET\n        name:\
  \ listdnsauthorizations\n        description: Google Cloud Certificate Manager List DNS authorizations\n        call: google-cloud-certificate-manager.listdnsauthorizations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-certificate-manager-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Certificate Manager API for AI agent use.\n    tools:\n    - name: listcertificates\n      description: Google Cloud Certificate Manager List certificates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-certificate-manager.listcertificates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcertificate\n      description: Google Cloud Certificate Manager Create a certificate\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-certificate-manager.createcertificate\n\
  \      with:\n        certificateId: tools.certificateId\n      inputParameters:\n      - name: certificateId\n        type: string\n        description: certificateId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcertificatemaps\n      description: Google Cloud Certificate Manager List certificate maps\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-certificate-manager.listcertificatemaps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdnsauthorizations\n      description: Google Cloud Certificate Manager List DNS authorizations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-certificate-manager.listdnsauthorizations\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_CERTIFICATE_MANAGER_TOKEN:\
  \ GOOGLE_CLOUD_CERTIFICATE_MANAGER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-certificate-manager/refs/heads/main/capabilities/google-cloud-certificate-manager-capability.yaml
tags:
- Google
- Cloud
- Certificate
- Manager
- API
tools:
- description: Google Cloud Certificate Manager List certificates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcertificates
- description: Google Cloud Certificate Manager Create a certificate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcertificate
- description: Google Cloud Certificate Manager List certificate maps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcertificatemaps
- description: Google Cloud Certificate Manager List DNS authorizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdnsauthorizations
---
