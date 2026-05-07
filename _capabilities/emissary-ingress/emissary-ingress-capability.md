---
categories: []
consumed_apis: []
description: Emissary-Ingress is a CNCF incubating Kubernetes-native API gateway and ingress controller built on the Envoy proxy. It is configured through Kubernetes Custom Resource Definitions (CRDs) including Mapping for request routing, Host for domain and TLS management, TLSContext for TLS termination settings, RateLimitService for delegating rate limiting to external services, and AuthService for external authentication. All resources are managed through the Kubernetes API server using standard CRUD operations.
layout: capability
name: Emissary-Ingress Configuration API
operations:
- description: Emissary-Ingress List Mapping resources in a namespace
  method: GET
  name: listnamespacedmapping
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings
- description: Emissary-Ingress Create a Mapping resource
  method: POST
  name: createnamespacedmapping
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings
- description: Emissary-Ingress Get a specific Mapping resource
  method: GET
  name: readnamespacedmapping
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings/{name}
- description: Emissary-Ingress Replace a Mapping resource
  method: PUT
  name: replacenamespacedmapping
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings/{name}
- description: Emissary-Ingress Partially update a Mapping resource
  method: PATCH
  name: patchnamespacedmapping
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings/{name}
- description: Emissary-Ingress Delete a Mapping resource
  method: DELETE
  name: deletenamespacedmapping
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings/{name}
- description: Emissary-Ingress List Mapping resources across all namespaces
  method: GET
  name: listmappingallnamespaces
  path: /apis/getambassador.io/v3alpha1/mappings
- description: Emissary-Ingress List Host resources in a namespace
  method: GET
  name: listnamespacedhost
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/hosts
- description: Emissary-Ingress Create a Host resource
  method: POST
  name: createnamespacedhost
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/hosts
- description: Emissary-Ingress Get a specific Host resource
  method: GET
  name: readnamespacedhost
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/hosts/{name}
- description: Emissary-Ingress Replace a Host resource
  method: PUT
  name: replacenamespacedhost
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/hosts/{name}
- description: Emissary-Ingress Delete a Host resource
  method: DELETE
  name: deletenamespacedhost
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/hosts/{name}
- description: Emissary-Ingress List TLSContext resources in a namespace
  method: GET
  name: listnamespacedtlscontext
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/tlscontexts
- description: Emissary-Ingress Create a TLSContext resource
  method: POST
  name: createnamespacedtlscontext
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/tlscontexts
- description: Emissary-Ingress Get a specific TLSContext resource
  method: GET
  name: readnamespacedtlscontext
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/tlscontexts/{name}
- description: Emissary-Ingress Delete a TLSContext resource
  method: DELETE
  name: deletenamespacedtlscontext
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/tlscontexts/{name}
- description: Emissary-Ingress List RateLimitService resources in a namespace
  method: GET
  name: listnamespacedratelimitservice
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/ratelimitservices
- description: Emissary-Ingress Create a RateLimitService resource
  method: POST
  name: createnamespacedratelimitservice
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/ratelimitservices
- description: Emissary-Ingress List AuthService resources in a namespace
  method: GET
  name: listnamespacedauthservice
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/authservices
- description: Emissary-Ingress Create an AuthService resource
  method: POST
  name: createnamespacedauthservice
  path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/authservices
personas: []
provider_name: Emissary-Ingress
provider_slug: emissary-ingress
search_terms:
- emissary-ingress create a ratelimitservice resource
- ingress
- createnamespacedtlscontext
- readnamespacedtlscontext
- readnamespacedmapping
- api
- createnamespacedauthservice
- emissary-ingress create a mapping resource
- patchnamespacedmapping
- cloud native
- deletenamespacedmapping
- incubating
- createnamespacedmapping
- emissary-ingress list tlscontext resources in a namespace
- listnamespacedtlscontext
- createnamespacedhost
- kubernetes
- readnamespacedhost
- listnamespacedratelimitservice
- emissary-ingress create an authservice resource
- listnamespacedmapping
- api gateway
- emissary-ingress create a host resource
- emissary-ingress delete a tlscontext resource
- listnamespacedhost
- emissary
- emissary-ingress get a specific host resource
- deletenamespacedhost
- emissary-ingress replace a mapping resource
- emissary-ingress create a tlscontext resource
- emissary-ingress get a specific tlscontext resource
- deletenamespacedtlscontext
- envoy
- createnamespacedratelimitservice
- emissary-ingress get a specific mapping resource
- replacenamespacedhost
- emissary-ingress partially update a mapping resource
- emissary-ingress delete a mapping resource
- replacenamespacedmapping
- emissary-ingress list mapping resources in a namespace
- emissary-ingress list mapping resources across all namespaces
- listmappingallnamespaces
- emissary-ingress delete a host resource
- emissary-ingress replace a host resource
- listnamespacedauthservice
- emissary-ingress list ratelimitservice resources in a namespace
- emissary-ingress list host resources in a namespace
- emissary-ingress list authservice resources in a namespace
slug: emissary-ingress-capability
source_filename: emissary-ingress-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Emissary-Ingress Configuration API\n  description: Emissary-Ingress is a CNCF incubating Kubernetes-native API gateway and ingress controller built on the Envoy\n    proxy. It is configured through Kubernetes Custom Resource Definitions (CRDs) including Mapping for request routing, Host\n    for domain and TLS management, TLSContext for TLS termination settings, RateLimitService for delegating rate limiting\n    to external services, and AuthService for external authentication. All resources are managed through the Kubernetes API\n    server using standard CRUD operations.\n  tags:\n  - Emissary\n  - Ingress\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: emissary-ingress\n    baseUri: https://localhost:6443\n    description: Emissary-Ingress Configuration API HTTP API.\n    resources:\n    - name: apis-getambassador-io-v3alpha1-namespaces-namesp\n      path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings\n\
  \      operations:\n      - name: listnamespacedmapping\n        method: GET\n        description: Emissary-Ingress List Mapping resources in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespacedmapping\n        method: POST\n        description: Emissary-Ingress Create a Mapping resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-getambassador-io-v3alpha1-namespaces-namesp\n      path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings/{name}\n      operations:\n      - name: readnamespacedmapping\n        method: GET\n        description: Emissary-Ingress Get a specific Mapping resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacenamespacedmapping\n   \
  \     method: PUT\n        description: Emissary-Ingress Replace a Mapping resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchnamespacedmapping\n        method: PATCH\n        description: Emissary-Ingress Partially update a Mapping resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenamespacedmapping\n        method: DELETE\n        description: Emissary-Ingress Delete a Mapping resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-getambassador-io-v3alpha1-mappings\n      path: /apis/getambassador.io/v3alpha1/mappings\n      operations:\n      - name: listmappingallnamespaces\n        method: GET\n        description: Emissary-Ingress List Mapping resources across all namespaces\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-getambassador-io-v3alpha1-namespaces-namesp\n      path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/hosts\n      operations:\n      - name: listnamespacedhost\n        method: GET\n        description: Emissary-Ingress List Host resources in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespacedhost\n        method: POST\n        description: Emissary-Ingress Create a Host resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-getambassador-io-v3alpha1-namespaces-namesp\n      path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/hosts/{name}\n      operations:\n      - name: readnamespacedhost\n        method: GET\n\
  \        description: Emissary-Ingress Get a specific Host resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacenamespacedhost\n        method: PUT\n        description: Emissary-Ingress Replace a Host resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenamespacedhost\n        method: DELETE\n        description: Emissary-Ingress Delete a Host resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-getambassador-io-v3alpha1-namespaces-namesp\n      path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/tlscontexts\n      operations:\n      - name: listnamespacedtlscontext\n        method: GET\n        description: Emissary-Ingress List TLSContext resources in a namespace\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespacedtlscontext\n        method: POST\n        description: Emissary-Ingress Create a TLSContext resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-getambassador-io-v3alpha1-namespaces-namesp\n      path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/tlscontexts/{name}\n      operations:\n      - name: readnamespacedtlscontext\n        method: GET\n        description: Emissary-Ingress Get a specific TLSContext resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenamespacedtlscontext\n        method: DELETE\n        description: Emissary-Ingress Delete a TLSContext resource\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: apis-getambassador-io-v3alpha1-namespaces-namesp\n      path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/ratelimitservices\n      operations:\n      - name: listnamespacedratelimitservice\n        method: GET\n        description: Emissary-Ingress List RateLimitService resources in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespacedratelimitservice\n        method: POST\n        description: Emissary-Ingress Create a RateLimitService resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-getambassador-io-v3alpha1-namespaces-namesp\n      path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/authservices\n      operations:\n      - name: listnamespacedauthservice\n        method:\
  \ GET\n        description: Emissary-Ingress List AuthService resources in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespacedauthservice\n        method: POST\n        description: Emissary-Ingress Create an AuthService resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: emissary-ingress-rest\n    description: REST adapter for Emissary-Ingress Configuration API.\n    resources:\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings\n      name: listnamespacedmapping\n      operations:\n      - method: GET\n        name: listnamespacedmapping\n        description: Emissary-Ingress List Mapping resources in a namespace\n        call: emissary-ingress.listnamespacedmapping\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings\n      name: createnamespacedmapping\n      operations:\n      - method: POST\n        name: createnamespacedmapping\n        description: Emissary-Ingress Create a Mapping resource\n        call: emissary-ingress.createnamespacedmapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings/{name}\n      name: readnamespacedmapping\n      operations:\n      - method: GET\n        name: readnamespacedmapping\n        description: Emissary-Ingress Get a specific Mapping resource\n        call: emissary-ingress.readnamespacedmapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings/{name}\n      name: replacenamespacedmapping\n      operations:\n      - method: PUT\n        name:\
  \ replacenamespacedmapping\n        description: Emissary-Ingress Replace a Mapping resource\n        call: emissary-ingress.replacenamespacedmapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings/{name}\n      name: patchnamespacedmapping\n      operations:\n      - method: PATCH\n        name: patchnamespacedmapping\n        description: Emissary-Ingress Partially update a Mapping resource\n        call: emissary-ingress.patchnamespacedmapping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/mappings/{name}\n      name: deletenamespacedmapping\n      operations:\n      - method: DELETE\n        name: deletenamespacedmapping\n        description: Emissary-Ingress Delete a Mapping resource\n        call: emissary-ingress.deletenamespacedmapping\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/mappings\n      name: listmappingallnamespaces\n      operations:\n      - method: GET\n        name: listmappingallnamespaces\n        description: Emissary-Ingress List Mapping resources across all namespaces\n        call: emissary-ingress.listmappingallnamespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/hosts\n      name: listnamespacedhost\n      operations:\n      - method: GET\n        name: listnamespacedhost\n        description: Emissary-Ingress List Host resources in a namespace\n        call: emissary-ingress.listnamespacedhost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/hosts\n      name: createnamespacedhost\n      operations:\n      - method: POST\n        name: createnamespacedhost\n        description: Emissary-Ingress\
  \ Create a Host resource\n        call: emissary-ingress.createnamespacedhost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/hosts/{name}\n      name: readnamespacedhost\n      operations:\n      - method: GET\n        name: readnamespacedhost\n        description: Emissary-Ingress Get a specific Host resource\n        call: emissary-ingress.readnamespacedhost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/hosts/{name}\n      name: replacenamespacedhost\n      operations:\n      - method: PUT\n        name: replacenamespacedhost\n        description: Emissary-Ingress Replace a Host resource\n        call: emissary-ingress.replacenamespacedhost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/hosts/{name}\n \
  \     name: deletenamespacedhost\n      operations:\n      - method: DELETE\n        name: deletenamespacedhost\n        description: Emissary-Ingress Delete a Host resource\n        call: emissary-ingress.deletenamespacedhost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/tlscontexts\n      name: listnamespacedtlscontext\n      operations:\n      - method: GET\n        name: listnamespacedtlscontext\n        description: Emissary-Ingress List TLSContext resources in a namespace\n        call: emissary-ingress.listnamespacedtlscontext\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/tlscontexts\n      name: createnamespacedtlscontext\n      operations:\n      - method: POST\n        name: createnamespacedtlscontext\n        description: Emissary-Ingress Create a TLSContext resource\n        call: emissary-ingress.createnamespacedtlscontext\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/tlscontexts/{name}\n      name: readnamespacedtlscontext\n      operations:\n      - method: GET\n        name: readnamespacedtlscontext\n        description: Emissary-Ingress Get a specific TLSContext resource\n        call: emissary-ingress.readnamespacedtlscontext\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/tlscontexts/{name}\n      name: deletenamespacedtlscontext\n      operations:\n      - method: DELETE\n        name: deletenamespacedtlscontext\n        description: Emissary-Ingress Delete a TLSContext resource\n        call: emissary-ingress.deletenamespacedtlscontext\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/ratelimitservices\n      name: listnamespacedratelimitservice\n\
  \      operations:\n      - method: GET\n        name: listnamespacedratelimitservice\n        description: Emissary-Ingress List RateLimitService resources in a namespace\n        call: emissary-ingress.listnamespacedratelimitservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/ratelimitservices\n      name: createnamespacedratelimitservice\n      operations:\n      - method: POST\n        name: createnamespacedratelimitservice\n        description: Emissary-Ingress Create a RateLimitService resource\n        call: emissary-ingress.createnamespacedratelimitservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/authservices\n      name: listnamespacedauthservice\n      operations:\n      - method: GET\n        name: listnamespacedauthservice\n        description: Emissary-Ingress List AuthService\
  \ resources in a namespace\n        call: emissary-ingress.listnamespacedauthservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/getambassador.io/v3alpha1/namespaces/{namespace}/authservices\n      name: createnamespacedauthservice\n      operations:\n      - method: POST\n        name: createnamespacedauthservice\n        description: Emissary-Ingress Create an AuthService resource\n        call: emissary-ingress.createnamespacedauthservice\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: emissary-ingress-mcp\n    transport: http\n    description: MCP adapter for Emissary-Ingress Configuration API for AI agent use.\n    tools:\n    - name: listnamespacedmapping\n      description: Emissary-Ingress List Mapping resources in a namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: emissary-ingress.listnamespacedmapping\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespacedmapping\n      description: Emissary-Ingress Create a Mapping resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: emissary-ingress.createnamespacedmapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readnamespacedmapping\n      description: Emissary-Ingress Get a specific Mapping resource\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: emissary-ingress.readnamespacedmapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacenamespacedmapping\n      description: Emissary-Ingress Replace a Mapping resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: emissary-ingress.replacenamespacedmapping\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: patchnamespacedmapping\n      description: Emissary-Ingress Partially update a Mapping resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: emissary-ingress.patchnamespacedmapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespacedmapping\n      description: Emissary-Ingress Delete a Mapping resource\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: emissary-ingress.deletenamespacedmapping\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmappingallnamespaces\n      description: Emissary-Ingress List Mapping resources across all namespaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: emissary-ingress.listmappingallnamespaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: listnamespacedhost\n      description: Emissary-Ingress List Host resources in a namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: emissary-ingress.listnamespacedhost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespacedhost\n      description: Emissary-Ingress Create a Host resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: emissary-ingress.createnamespacedhost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readnamespacedhost\n      description: Emissary-Ingress Get a specific Host resource\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: emissary-ingress.readnamespacedhost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacenamespacedhost\n      description: Emissary-Ingress Replace\
  \ a Host resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: emissary-ingress.replacenamespacedhost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespacedhost\n      description: Emissary-Ingress Delete a Host resource\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: emissary-ingress.deletenamespacedhost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespacedtlscontext\n      description: Emissary-Ingress List TLSContext resources in a namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: emissary-ingress.listnamespacedtlscontext\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespacedtlscontext\n      description: Emissary-Ingress Create a TLSContext resource\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: emissary-ingress.createnamespacedtlscontext\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readnamespacedtlscontext\n      description: Emissary-Ingress Get a specific TLSContext resource\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: emissary-ingress.readnamespacedtlscontext\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespacedtlscontext\n      description: Emissary-Ingress Delete a TLSContext resource\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: emissary-ingress.deletenamespacedtlscontext\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespacedratelimitservice\n      description: Emissary-Ingress List RateLimitService resources in a namespace\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: emissary-ingress.listnamespacedratelimitservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespacedratelimitservice\n      description: Emissary-Ingress Create a RateLimitService resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: emissary-ingress.createnamespacedratelimitservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespacedauthservice\n      description: Emissary-Ingress List AuthService resources in a namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: emissary-ingress.listnamespacedauthservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespacedauthservice\n      description: Emissary-Ingress Create an AuthService resource\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: emissary-ingress.createnamespacedauthservice\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/emissary-ingress/refs/heads/main/capabilities/emissary-ingress-capability.yaml
tags:
- Emissary
- Ingress
- API
tools:
- description: Emissary-Ingress List Mapping resources in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacedmapping
- description: Emissary-Ingress Create a Mapping resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespacedmapping
- description: Emissary-Ingress Get a specific Mapping resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readnamespacedmapping
- description: Emissary-Ingress Replace a Mapping resource
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacenamespacedmapping
- description: Emissary-Ingress Partially update a Mapping resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchnamespacedmapping
- description: Emissary-Ingress Delete a Mapping resource
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespacedmapping
- description: Emissary-Ingress List Mapping resources across all namespaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmappingallnamespaces
- description: Emissary-Ingress List Host resources in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacedhost
- description: Emissary-Ingress Create a Host resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespacedhost
- description: Emissary-Ingress Get a specific Host resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readnamespacedhost
- description: Emissary-Ingress Replace a Host resource
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacenamespacedhost
- description: Emissary-Ingress Delete a Host resource
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespacedhost
- description: Emissary-Ingress List TLSContext resources in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacedtlscontext
- description: Emissary-Ingress Create a TLSContext resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespacedtlscontext
- description: Emissary-Ingress Get a specific TLSContext resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readnamespacedtlscontext
- description: Emissary-Ingress Delete a TLSContext resource
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespacedtlscontext
- description: Emissary-Ingress List RateLimitService resources in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacedratelimitservice
- description: Emissary-Ingress Create a RateLimitService resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespacedratelimitservice
- description: Emissary-Ingress List AuthService resources in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacedauthservice
- description: Emissary-Ingress Create an AuthService resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespacedauthservice
---
