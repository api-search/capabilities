---
categories: []
consumed_apis: []
description: The Kubernetes EndpointSlices API tracks the IP addresses, ports, readiness, and topology information for Pods backing a Service. EndpointSlices replaced the older Endpoints API to improve scalability for large clusters with thousands of pods. A single Service may be backed by multiple EndpointSlices, and the EndpointSlice controller automatically manages their lifecycle in response to pod and Service changes.
layout: capability
name: Kubernetes Services Kubernetes EndpointSlices API
operations:
- description: Kubernetes Services List EndpointSlices in a namespace
  method: GET
  name: listnamespacedendpointslices
  path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices
- description: Kubernetes Services Create an EndpointSlice
  method: POST
  name: createnamespacedendpointslice
  path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices
- description: Kubernetes Services Get an EndpointSlice
  method: GET
  name: getnamespacedendpointslice
  path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices/{name}
- description: Kubernetes Services Replace an EndpointSlice
  method: PUT
  name: replacenamespacedendpointslice
  path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices/{name}
- description: Kubernetes Services Patch an EndpointSlice
  method: PATCH
  name: patchnamespacedendpointslice
  path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices/{name}
- description: Kubernetes Services Delete an EndpointSlice
  method: DELETE
  name: deletenamespacedendpointslice
  path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices/{name}
- description: Kubernetes Services List EndpointSlices across all namespaces
  method: GET
  name: listendpointslicesallnamespaces
  path: /apis/discovery.k8s.io/v1/endpointslices
personas: []
provider_name: Kubernetes Services
provider_slug: kubernetes-services
search_terms:
- kubernetes services list endpointslices across all namespaces
- networking
- api
- kubernetes services get an endpointslice
- deletenamespacedendpointslice
- services
- kubernetes
- kubernetes services list endpointslices in a namespace
- kubernetes services delete an endpointslice
- kubernetes services patch an endpointslice
- service discovery
- createnamespacedendpointslice
- load balancing
- replacenamespacedendpointslice
- listnamespacedendpointslices
- patchnamespacedendpointslice
- container orchestration
- kubernetes services create an endpointslice
- kubernetes services replace an endpointslice
- listendpointslicesallnamespaces
- getnamespacedendpointslice
slug: kubernetes-services-capability
source_filename: kubernetes-services-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Kubernetes Services Kubernetes EndpointSlices API\n  description: The Kubernetes EndpointSlices API tracks the IP addresses, ports, readiness, and topology information for Pods\n    backing a Service. EndpointSlices replaced the older Endpoints API to improve scalability for large clusters with thousands\n    of pods. A single Service may be backed by multiple EndpointSlices, and the EndpointSlice controller automatically manages\n    their lifecycle in response to pod and Service changes.\n  tags:\n  - Kubernetes\n  - Services\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: kubernetes-services\n    baseUri: https://kubernetes.default.svc\n    description: Kubernetes Services Kubernetes EndpointSlices API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{KUBERNETES_SERVICES_TOKEN}}'\n    resources:\n    - name: apis-discovery-k8s-io-v1-namespaces-namespace-en\n\
  \      path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices\n      operations:\n      - name: listnamespacedendpointslices\n        method: GET\n        description: Kubernetes Services List EndpointSlices in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespacedendpointslice\n        method: POST\n        description: Kubernetes Services Create an EndpointSlice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-discovery-k8s-io-v1-namespaces-namespace-en\n      path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices/{name}\n      operations:\n      - name: getnamespacedendpointslice\n        method: GET\n        description: Kubernetes Services Get an EndpointSlice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: replacenamespacedendpointslice\n        method: PUT\n        description: Kubernetes Services Replace an EndpointSlice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchnamespacedendpointslice\n        method: PATCH\n        description: Kubernetes Services Patch an EndpointSlice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenamespacedendpointslice\n        method: DELETE\n        description: Kubernetes Services Delete an EndpointSlice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-discovery-k8s-io-v1-endpointslices\n      path: /apis/discovery.k8s.io/v1/endpointslices\n      operations:\n      - name: listendpointslicesallnamespaces\n\
  \        method: GET\n        description: Kubernetes Services List EndpointSlices across all namespaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kubernetes-services-rest\n    description: REST adapter for Kubernetes Services Kubernetes EndpointSlices API.\n    resources:\n    - path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices\n      name: listnamespacedendpointslices\n      operations:\n      - method: GET\n        name: listnamespacedendpointslices\n        description: Kubernetes Services List EndpointSlices in a namespace\n        call: kubernetes-services.listnamespacedendpointslices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices\n      name: createnamespacedendpointslice\n      operations:\n      - method: POST\n\
  \        name: createnamespacedendpointslice\n        description: Kubernetes Services Create an EndpointSlice\n        call: kubernetes-services.createnamespacedendpointslice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices/{name}\n      name: getnamespacedendpointslice\n      operations:\n      - method: GET\n        name: getnamespacedendpointslice\n        description: Kubernetes Services Get an EndpointSlice\n        call: kubernetes-services.getnamespacedendpointslice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices/{name}\n      name: replacenamespacedendpointslice\n      operations:\n      - method: PUT\n        name: replacenamespacedendpointslice\n        description: Kubernetes Services Replace an EndpointSlice\n        call: kubernetes-services.replacenamespacedendpointslice\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices/{name}\n      name: patchnamespacedendpointslice\n      operations:\n      - method: PATCH\n        name: patchnamespacedendpointslice\n        description: Kubernetes Services Patch an EndpointSlice\n        call: kubernetes-services.patchnamespacedendpointslice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/discovery.k8s.io/v1/namespaces/{namespace}/endpointslices/{name}\n      name: deletenamespacedendpointslice\n      operations:\n      - method: DELETE\n        name: deletenamespacedendpointslice\n        description: Kubernetes Services Delete an EndpointSlice\n        call: kubernetes-services.deletenamespacedendpointslice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/discovery.k8s.io/v1/endpointslices\n      name: listendpointslicesallnamespaces\n\
  \      operations:\n      - method: GET\n        name: listendpointslicesallnamespaces\n        description: Kubernetes Services List EndpointSlices across all namespaces\n        call: kubernetes-services.listendpointslicesallnamespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: kubernetes-services-mcp\n    transport: http\n    description: MCP adapter for Kubernetes Services Kubernetes EndpointSlices API for AI agent use.\n    tools:\n    - name: listnamespacedendpointslices\n      description: Kubernetes Services List EndpointSlices in a namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes-services.listnamespacedendpointslices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespacedendpointslice\n      description: Kubernetes Services Create an EndpointSlice\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: kubernetes-services.createnamespacedendpointslice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnamespacedendpointslice\n      description: Kubernetes Services Get an EndpointSlice\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes-services.getnamespacedendpointslice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacenamespacedendpointslice\n      description: Kubernetes Services Replace an EndpointSlice\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kubernetes-services.replacenamespacedendpointslice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchnamespacedendpointslice\n      description: Kubernetes Services Patch an EndpointSlice\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: kubernetes-services.patchnamespacedendpointslice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespacedendpointslice\n      description: Kubernetes Services Delete an EndpointSlice\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kubernetes-services.deletenamespacedendpointslice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listendpointslicesallnamespaces\n      description: Kubernetes Services List EndpointSlices across all namespaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes-services.listendpointslicesallnamespaces\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    KUBERNETES_SERVICES_TOKEN: KUBERNETES_SERVICES_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/kubernetes-services/refs/heads/main/capabilities/kubernetes-services-capability.yaml
tags:
- Kubernetes
- Services
- API
tools:
- description: Kubernetes Services List EndpointSlices in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacedendpointslices
- description: Kubernetes Services Create an EndpointSlice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespacedendpointslice
- description: Kubernetes Services Get an EndpointSlice
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnamespacedendpointslice
- description: Kubernetes Services Replace an EndpointSlice
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacenamespacedendpointslice
- description: Kubernetes Services Patch an EndpointSlice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchnamespacedendpointslice
- description: Kubernetes Services Delete an EndpointSlice
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespacedendpointslice
- description: Kubernetes Services List EndpointSlices across all namespaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listendpointslicesallnamespaces
---
