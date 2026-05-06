---
categories: []
consumed_apis: []
description: The Istio Extensions API (extensions.istio.io) provides configuration resources for extending the Istio service mesh with custom functionality. The WasmPlugin resource enables deploying WebAssembly (Wasm) modules as plugins to the Envoy sidecar proxies, allowing custom processing of network traffic at various phases of the request lifecycle. These resources are defined as Kubernetes Custom Resource Definitions (CRDs) and are accessed via the Kubernetes API server.
layout: capability
name: Istio Extensions API
operations:
- description: Istio List WasmPlugins
  method: GET
  name: listwasmplugins
  path: /namespaces/{namespace}/wasmplugins
- description: Istio Create a WasmPlugin
  method: POST
  name: createwasmplugin
  path: /namespaces/{namespace}/wasmplugins
- description: Istio Get a WasmPlugin
  method: GET
  name: getwasmplugin
  path: /namespaces/{namespace}/wasmplugins/{name}
- description: Istio Replace a WasmPlugin
  method: PUT
  name: replacewasmplugin
  path: /namespaces/{namespace}/wasmplugins/{name}
- description: Istio Delete a WasmPlugin
  method: DELETE
  name: deletewasmplugin
  path: /namespaces/{namespace}/wasmplugins/{name}
personas: []
provider_name: Istio
provider_slug: istio
search_terms:
- service mesh
- replacewasmplugin
- createwasmplugin
- istio get a wasmplugin
- listwasmplugins
- api
- istio create a wasmplugin
- istio replace a wasmplugin
- deletewasmplugin
- cncf
- istio
- getwasmplugin
- istio delete a wasmplugin
- microservices
- open source
- kubernetes
- istio list wasmplugins
slug: istio-capability
source_filename: istio-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Istio Extensions API\n  description: The Istio Extensions API (extensions.istio.io) provides configuration resources for extending the Istio service\n    mesh with custom functionality. The WasmPlugin resource enables deploying WebAssembly (Wasm) modules as plugins to the\n    Envoy sidecar proxies, allowing custom processing of network traffic at various phases of the request lifecycle. These\n    resources are defined as Kubernetes Custom Resource Definitions (CRDs) and are accessed via the Kubernetes API server.\n  tags:\n  - Istio\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: istio\n    baseUri: https://kubernetes.default.svc/apis/extensions.istio.io/v1alpha1\n    description: Istio Extensions API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ISTIO_TOKEN}}'\n    resources:\n    - name: namespaces-namespace-wasmplugins\n      path: /namespaces/{namespace}/wasmplugins\n\
  \      operations:\n      - name: listwasmplugins\n        method: GET\n        description: Istio List WasmPlugins\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createwasmplugin\n        method: POST\n        description: Istio Create a WasmPlugin\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-wasmplugins-name\n      path: /namespaces/{namespace}/wasmplugins/{name}\n      operations:\n      - name: getwasmplugin\n        method: GET\n        description: Istio Get a WasmPlugin\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacewasmplugin\n        method: PUT\n        description: Istio Replace a WasmPlugin\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: deletewasmplugin\n        method: DELETE\n        description: Istio Delete a WasmPlugin\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: istio-rest\n    description: REST adapter for Istio Extensions API.\n    resources:\n    - path: /namespaces/{namespace}/wasmplugins\n      name: listwasmplugins\n      operations:\n      - method: GET\n        name: listwasmplugins\n        description: Istio List WasmPlugins\n        call: istio.listwasmplugins\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/wasmplugins\n      name: createwasmplugin\n      operations:\n      - method: POST\n        name: createwasmplugin\n        description: Istio Create a WasmPlugin\n        call: istio.createwasmplugin\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/wasmplugins/{name}\n      name: getwasmplugin\n      operations:\n      - method: GET\n        name: getwasmplugin\n        description: Istio Get a WasmPlugin\n        call: istio.getwasmplugin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/wasmplugins/{name}\n      name: replacewasmplugin\n      operations:\n      - method: PUT\n        name: replacewasmplugin\n        description: Istio Replace a WasmPlugin\n        call: istio.replacewasmplugin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/wasmplugins/{name}\n      name: deletewasmplugin\n      operations:\n      - method: DELETE\n        name: deletewasmplugin\n        description: Istio Delete a WasmPlugin\n        call: istio.deletewasmplugin\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n\
  \    port: 9090\n    namespace: istio-mcp\n    transport: http\n    description: MCP adapter for Istio Extensions API for AI agent use.\n    tools:\n    - name: listwasmplugins\n      description: Istio List WasmPlugins\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: istio.listwasmplugins\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createwasmplugin\n      description: Istio Create a WasmPlugin\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: istio.createwasmplugin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getwasmplugin\n      description: Istio Get a WasmPlugin\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: istio.getwasmplugin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacewasmplugin\n      description:\
  \ Istio Replace a WasmPlugin\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: istio.replacewasmplugin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletewasmplugin\n      description: Istio Delete a WasmPlugin\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: istio.deletewasmplugin\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ISTIO_TOKEN: ISTIO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/istio/refs/heads/main/capabilities/istio-capability.yaml
tags:
- Istio
- API
tools:
- description: Istio List WasmPlugins
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwasmplugins
- description: Istio Create a WasmPlugin
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwasmplugin
- description: Istio Get a WasmPlugin
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwasmplugin
- description: Istio Replace a WasmPlugin
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacewasmplugin
- description: Istio Delete a WasmPlugin
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletewasmplugin
---
