---
categories: []
consumed_apis: []
description: kgateway is the most widely deployed gateway in Kubernetes for microservices and AI agents. It is a feature-rich, fast, and flexible Kubernetes-native ingress controller and next-generation API gateway built on top of Envoy proxy and the Kubernetes Gateway API. kgateway provides custom resource definitions (CRDs) under the gateway.kgateway.dev API group for configuring traffic policies, backends, direct responses, gateway extensions, gateway parameters, HTTP listener policies, and AI backends. These resources are managed through the Kubernetes API server.
layout: capability
name: kgateway Kubernetes Gateway API
operations:
- description: Kgateway List TrafficPolicy resources
  method: GET
  name: listtrafficpolicies
  path: /namespaces/{namespace}/trafficpolicies
- description: Kgateway Create a TrafficPolicy
  method: POST
  name: createtrafficpolicy
  path: /namespaces/{namespace}/trafficpolicies
- description: Kgateway Get a TrafficPolicy
  method: GET
  name: gettrafficpolicy
  path: /namespaces/{namespace}/trafficpolicies/{name}
- description: Kgateway Replace a TrafficPolicy
  method: PUT
  name: replacetrafficpolicy
  path: /namespaces/{namespace}/trafficpolicies/{name}
- description: Kgateway Delete a TrafficPolicy
  method: DELETE
  name: deletetrafficpolicy
  path: /namespaces/{namespace}/trafficpolicies/{name}
- description: Kgateway List Backend resources
  method: GET
  name: listbackends
  path: /namespaces/{namespace}/backends
- description: Kgateway Create a Backend
  method: POST
  name: createbackend
  path: /namespaces/{namespace}/backends
- description: Kgateway Get a Backend
  method: GET
  name: getbackend
  path: /namespaces/{namespace}/backends/{name}
- description: Kgateway Replace a Backend
  method: PUT
  name: replacebackend
  path: /namespaces/{namespace}/backends/{name}
- description: Kgateway Delete a Backend
  method: DELETE
  name: deletebackend
  path: /namespaces/{namespace}/backends/{name}
- description: Kgateway List DirectResponse resources
  method: GET
  name: listdirectresponses
  path: /namespaces/{namespace}/directresponses
- description: Kgateway Create a DirectResponse
  method: POST
  name: createdirectresponse
  path: /namespaces/{namespace}/directresponses
- description: Kgateway Get a DirectResponse
  method: GET
  name: getdirectresponse
  path: /namespaces/{namespace}/directresponses/{name}
- description: Kgateway Replace a DirectResponse
  method: PUT
  name: replacedirectresponse
  path: /namespaces/{namespace}/directresponses/{name}
- description: Kgateway Delete a DirectResponse
  method: DELETE
  name: deletedirectresponse
  path: /namespaces/{namespace}/directresponses/{name}
- description: Kgateway List GatewayExtension resources
  method: GET
  name: listgatewayextensions
  path: /namespaces/{namespace}/gatewayextensions
- description: Kgateway Create a GatewayExtension
  method: POST
  name: creategatewayextension
  path: /namespaces/{namespace}/gatewayextensions
- description: Kgateway Get a GatewayExtension
  method: GET
  name: getgatewayextension
  path: /namespaces/{namespace}/gatewayextensions/{name}
- description: Kgateway Replace a GatewayExtension
  method: PUT
  name: replacegatewayextension
  path: /namespaces/{namespace}/gatewayextensions/{name}
- description: Kgateway Delete a GatewayExtension
  method: DELETE
  name: deletegatewayextension
  path: /namespaces/{namespace}/gatewayextensions/{name}
- description: Kgateway List GatewayParameters resources
  method: GET
  name: listgatewayparameters
  path: /namespaces/{namespace}/gatewayparameters
- description: Kgateway Create GatewayParameters
  method: POST
  name: creategatewayparameters
  path: /namespaces/{namespace}/gatewayparameters
- description: Kgateway Get GatewayParameters
  method: GET
  name: getgatewayparameters
  path: /namespaces/{namespace}/gatewayparameters/{name}
- description: Kgateway Replace GatewayParameters
  method: PUT
  name: replacegatewayparameters
  path: /namespaces/{namespace}/gatewayparameters/{name}
- description: Kgateway Delete GatewayParameters
  method: DELETE
  name: deletegatewayparameters
  path: /namespaces/{namespace}/gatewayparameters/{name}
- description: Kgateway List HTTPListenerPolicy resources
  method: GET
  name: listhttplistenerpolicies
  path: /namespaces/{namespace}/httplistenerpolicies
- description: Kgateway Create an HTTPListenerPolicy
  method: POST
  name: createhttplistenerpolicy
  path: /namespaces/{namespace}/httplistenerpolicies
- description: Kgateway Get an HTTPListenerPolicy
  method: GET
  name: gethttplistenerpolicy
  path: /namespaces/{namespace}/httplistenerpolicies/{name}
- description: Kgateway Replace an HTTPListenerPolicy
  method: PUT
  name: replacehttplistenerpolicy
  path: /namespaces/{namespace}/httplistenerpolicies/{name}
- description: Kgateway Delete an HTTPListenerPolicy
  method: DELETE
  name: deletehttplistenerpolicy
  path: /namespaces/{namespace}/httplistenerpolicies/{name}
- description: Kgateway List AIBackend resources
  method: GET
  name: listaibackends
  path: /namespaces/{namespace}/aibackends
- description: Kgateway Create an AIBackend
  method: POST
  name: createaibackend
  path: /namespaces/{namespace}/aibackends
- description: Kgateway Get an AIBackend
  method: GET
  name: getaibackend
  path: /namespaces/{namespace}/aibackends/{name}
- description: Kgateway Replace an AIBackend
  method: PUT
  name: replaceaibackend
  path: /namespaces/{namespace}/aibackends/{name}
- description: Kgateway Delete an AIBackend
  method: DELETE
  name: deleteaibackend
  path: /namespaces/{namespace}/aibackends/{name}
personas: []
provider_name: Kgateway
provider_slug: kgateway
search_terms:
- kgateway replace a trafficpolicy
- kgateway get an aibackend
- kgateway delete a gatewayextension
- listhttplistenerpolicies
- deletebackend
- createdirectresponse
- kgateway delete an aibackend
- api
- deletedirectresponse
- kgateway get a directresponse
- listdirectresponses
- getdirectresponse
- kgateway create an httplistenerpolicy
- gateways
- kgateway replace a gatewayextension
- deletehttplistenerpolicy
- kgateway create a directresponse
- kgateway create a gatewayextension
- kgateway get a gatewayextension
- creategatewayparameters
- kgateway replace an httplistenerpolicy
- kgateway list aibackend resources
- getgatewayparameters
- kgateway replace an aibackend
- listgatewayparameters
- replacegatewayparameters
- deletegatewayextension
- kgateway create a backend
- kgateway get a backend
- deleteaibackend
- kgateway delete a trafficpolicy
- kgateway delete gatewayparameters
- kgateway get a trafficpolicy
- replacedirectresponse
- creategatewayextension
- kgateway list gatewayparameters resources
- kgateway get an httplistenerpolicy
- getgatewayextension
- gethttplistenerpolicy
- kgateway delete a backend
- kgateway replace a directresponse
- replacegatewayextension
- deletetrafficpolicy
- gettrafficpolicy
- kgateway list directresponse resources
- listaibackends
- kgateway list gatewayextension resources
- replacebackend
- replacehttplistenerpolicy
- deletegatewayparameters
- kgateway create an aibackend
- kgateway replace a backend
- getaibackend
- replaceaibackend
- listtrafficpolicies
- kgateway create a trafficpolicy
- kgateway list trafficpolicy resources
- kgateway delete a directresponse
- kgateway
- listgatewayextensions
- listbackends
- createaibackend
- kgateway create gatewayparameters
- kgateway get gatewayparameters
- kgateway list httplistenerpolicy resources
- createhttplistenerpolicy
- createtrafficpolicy
- kgateway replace gatewayparameters
- kgateway list backend resources
- kgateway delete an httplistenerpolicy
- replacetrafficpolicy
- createbackend
- getbackend
slug: kgateway-capability
source_filename: kgateway-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: kgateway Kubernetes Gateway API\n  description: kgateway is the most widely deployed gateway in Kubernetes for microservices and AI agents. It is a feature-rich,\n    fast, and flexible Kubernetes-native ingress controller and next-generation API gateway built on top of Envoy proxy and\n    the Kubernetes Gateway API. kgateway provides custom resource definitions (CRDs) under the gateway.kgateway.dev API group\n    for configuring traffic policies, backends, direct responses, gateway extensions, gateway parameters, HTTP listener policies,\n    and AI backends. These resources are managed through the Kubernetes API server.\n  tags:\n  - Kgateway\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: kgateway\n    baseUri: https://kubernetes.default.svc/apis/gateway.kgateway.dev/v1alpha1\n    description: kgateway Kubernetes Gateway API HTTP API.\n    authentication:\n      type:\
  \ bearer\n      token: '{{KGATEWAY_TOKEN}}'\n    resources:\n    - name: namespaces-namespace-trafficpolicies\n      path: /namespaces/{namespace}/trafficpolicies\n      operations:\n      - name: listtrafficpolicies\n        method: GET\n        description: Kgateway List TrafficPolicy resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtrafficpolicy\n        method: POST\n        description: Kgateway Create a TrafficPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-trafficpolicies-name\n      path: /namespaces/{namespace}/trafficpolicies/{name}\n      operations:\n      - name: gettrafficpolicy\n        method: GET\n        description: Kgateway Get a TrafficPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: replacetrafficpolicy\n        method: PUT\n        description: Kgateway Replace a TrafficPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetrafficpolicy\n        method: DELETE\n        description: Kgateway Delete a TrafficPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-backends\n      path: /namespaces/{namespace}/backends\n      operations:\n      - name: listbackends\n        method: GET\n        description: Kgateway List Backend resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbackend\n        method: POST\n        description: Kgateway Create a Backend\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-backends-name\n      path: /namespaces/{namespace}/backends/{name}\n      operations:\n      - name: getbackend\n        method: GET\n        description: Kgateway Get a Backend\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacebackend\n        method: PUT\n        description: Kgateway Replace a Backend\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebackend\n        method: DELETE\n        description: Kgateway Delete a Backend\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-directresponses\n      path: /namespaces/{namespace}/directresponses\n      operations:\n      - name:\
  \ listdirectresponses\n        method: GET\n        description: Kgateway List DirectResponse resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdirectresponse\n        method: POST\n        description: Kgateway Create a DirectResponse\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-directresponses-name\n      path: /namespaces/{namespace}/directresponses/{name}\n      operations:\n      - name: getdirectresponse\n        method: GET\n        description: Kgateway Get a DirectResponse\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacedirectresponse\n        method: PUT\n        description: Kgateway Replace a DirectResponse\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletedirectresponse\n        method: DELETE\n        description: Kgateway Delete a DirectResponse\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-gatewayextensions\n      path: /namespaces/{namespace}/gatewayextensions\n      operations:\n      - name: listgatewayextensions\n        method: GET\n        description: Kgateway List GatewayExtension resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategatewayextension\n        method: POST\n        description: Kgateway Create a GatewayExtension\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-gatewayextensions-name\n      path: /namespaces/{namespace}/gatewayextensions/{name}\n\
  \      operations:\n      - name: getgatewayextension\n        method: GET\n        description: Kgateway Get a GatewayExtension\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacegatewayextension\n        method: PUT\n        description: Kgateway Replace a GatewayExtension\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegatewayextension\n        method: DELETE\n        description: Kgateway Delete a GatewayExtension\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-gatewayparameters\n      path: /namespaces/{namespace}/gatewayparameters\n      operations:\n      - name: listgatewayparameters\n        method: GET\n        description: Kgateway List GatewayParameters resources\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategatewayparameters\n        method: POST\n        description: Kgateway Create GatewayParameters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-gatewayparameters-name\n      path: /namespaces/{namespace}/gatewayparameters/{name}\n      operations:\n      - name: getgatewayparameters\n        method: GET\n        description: Kgateway Get GatewayParameters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacegatewayparameters\n        method: PUT\n        description: Kgateway Replace GatewayParameters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ deletegatewayparameters\n        method: DELETE\n        description: Kgateway Delete GatewayParameters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-httplistenerpolicies\n      path: /namespaces/{namespace}/httplistenerpolicies\n      operations:\n      - name: listhttplistenerpolicies\n        method: GET\n        description: Kgateway List HTTPListenerPolicy resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createhttplistenerpolicy\n        method: POST\n        description: Kgateway Create an HTTPListenerPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-httplistenerpolicies-name\n      path: /namespaces/{namespace}/httplistenerpolicies/{name}\n      operations:\n\
  \      - name: gethttplistenerpolicy\n        method: GET\n        description: Kgateway Get an HTTPListenerPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacehttplistenerpolicy\n        method: PUT\n        description: Kgateway Replace an HTTPListenerPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletehttplistenerpolicy\n        method: DELETE\n        description: Kgateway Delete an HTTPListenerPolicy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-aibackends\n      path: /namespaces/{namespace}/aibackends\n      operations:\n      - name: listaibackends\n        method: GET\n        description: Kgateway List AIBackend resources\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createaibackend\n        method: POST\n        description: Kgateway Create an AIBackend\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces-namespace-aibackends-name\n      path: /namespaces/{namespace}/aibackends/{name}\n      operations:\n      - name: getaibackend\n        method: GET\n        description: Kgateway Get an AIBackend\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replaceaibackend\n        method: PUT\n        description: Kgateway Replace an AIBackend\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteaibackend\n        method: DELETE\n        description: Kgateway Delete an AIBackend\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kgateway-rest\n    description: REST adapter for kgateway Kubernetes Gateway API.\n    resources:\n    - path: /namespaces/{namespace}/trafficpolicies\n      name: listtrafficpolicies\n      operations:\n      - method: GET\n        name: listtrafficpolicies\n        description: Kgateway List TrafficPolicy resources\n        call: kgateway.listtrafficpolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/trafficpolicies\n      name: createtrafficpolicy\n      operations:\n      - method: POST\n        name: createtrafficpolicy\n        description: Kgateway Create a TrafficPolicy\n        call: kgateway.createtrafficpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/trafficpolicies/{name}\n\
  \      name: gettrafficpolicy\n      operations:\n      - method: GET\n        name: gettrafficpolicy\n        description: Kgateway Get a TrafficPolicy\n        call: kgateway.gettrafficpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/trafficpolicies/{name}\n      name: replacetrafficpolicy\n      operations:\n      - method: PUT\n        name: replacetrafficpolicy\n        description: Kgateway Replace a TrafficPolicy\n        call: kgateway.replacetrafficpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/trafficpolicies/{name}\n      name: deletetrafficpolicy\n      operations:\n      - method: DELETE\n        name: deletetrafficpolicy\n        description: Kgateway Delete a TrafficPolicy\n        call: kgateway.deletetrafficpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/backends\n\
  \      name: listbackends\n      operations:\n      - method: GET\n        name: listbackends\n        description: Kgateway List Backend resources\n        call: kgateway.listbackends\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/backends\n      name: createbackend\n      operations:\n      - method: POST\n        name: createbackend\n        description: Kgateway Create a Backend\n        call: kgateway.createbackend\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/backends/{name}\n      name: getbackend\n      operations:\n      - method: GET\n        name: getbackend\n        description: Kgateway Get a Backend\n        call: kgateway.getbackend\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/backends/{name}\n      name: replacebackend\n      operations:\n      - method: PUT\n        name: replacebackend\n\
  \        description: Kgateway Replace a Backend\n        call: kgateway.replacebackend\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/backends/{name}\n      name: deletebackend\n      operations:\n      - method: DELETE\n        name: deletebackend\n        description: Kgateway Delete a Backend\n        call: kgateway.deletebackend\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/directresponses\n      name: listdirectresponses\n      operations:\n      - method: GET\n        name: listdirectresponses\n        description: Kgateway List DirectResponse resources\n        call: kgateway.listdirectresponses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/directresponses\n      name: createdirectresponse\n      operations:\n      - method: POST\n        name: createdirectresponse\n        description:\
  \ Kgateway Create a DirectResponse\n        call: kgateway.createdirectresponse\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/directresponses/{name}\n      name: getdirectresponse\n      operations:\n      - method: GET\n        name: getdirectresponse\n        description: Kgateway Get a DirectResponse\n        call: kgateway.getdirectresponse\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/directresponses/{name}\n      name: replacedirectresponse\n      operations:\n      - method: PUT\n        name: replacedirectresponse\n        description: Kgateway Replace a DirectResponse\n        call: kgateway.replacedirectresponse\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/directresponses/{name}\n      name: deletedirectresponse\n      operations:\n      - method: DELETE\n        name: deletedirectresponse\n\
  \        description: Kgateway Delete a DirectResponse\n        call: kgateway.deletedirectresponse\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/gatewayextensions\n      name: listgatewayextensions\n      operations:\n      - method: GET\n        name: listgatewayextensions\n        description: Kgateway List GatewayExtension resources\n        call: kgateway.listgatewayextensions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/gatewayextensions\n      name: creategatewayextension\n      operations:\n      - method: POST\n        name: creategatewayextension\n        description: Kgateway Create a GatewayExtension\n        call: kgateway.creategatewayextension\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/gatewayextensions/{name}\n      name: getgatewayextension\n      operations:\n      - method:\
  \ GET\n        name: getgatewayextension\n        description: Kgateway Get a GatewayExtension\n        call: kgateway.getgatewayextension\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/gatewayextensions/{name}\n      name: replacegatewayextension\n      operations:\n      - method: PUT\n        name: replacegatewayextension\n        description: Kgateway Replace a GatewayExtension\n        call: kgateway.replacegatewayextension\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/gatewayextensions/{name}\n      name: deletegatewayextension\n      operations:\n      - method: DELETE\n        name: deletegatewayextension\n        description: Kgateway Delete a GatewayExtension\n        call: kgateway.deletegatewayextension\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/gatewayparameters\n      name: listgatewayparameters\n\
  \      operations:\n      - method: GET\n        name: listgatewayparameters\n        description: Kgateway List GatewayParameters resources\n        call: kgateway.listgatewayparameters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/gatewayparameters\n      name: creategatewayparameters\n      operations:\n      - method: POST\n        name: creategatewayparameters\n        description: Kgateway Create GatewayParameters\n        call: kgateway.creategatewayparameters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/gatewayparameters/{name}\n      name: getgatewayparameters\n      operations:\n      - method: GET\n        name: getgatewayparameters\n        description: Kgateway Get GatewayParameters\n        call: kgateway.getgatewayparameters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/gatewayparameters/{name}\n\
  \      name: replacegatewayparameters\n      operations:\n      - method: PUT\n        name: replacegatewayparameters\n        description: Kgateway Replace GatewayParameters\n        call: kgateway.replacegatewayparameters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/gatewayparameters/{name}\n      name: deletegatewayparameters\n      operations:\n      - method: DELETE\n        name: deletegatewayparameters\n        description: Kgateway Delete GatewayParameters\n        call: kgateway.deletegatewayparameters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/httplistenerpolicies\n      name: listhttplistenerpolicies\n      operations:\n      - method: GET\n        name: listhttplistenerpolicies\n        description: Kgateway List HTTPListenerPolicy resources\n        call: kgateway.listhttplistenerpolicies\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /namespaces/{namespace}/httplistenerpolicies\n      name: createhttplistenerpolicy\n      operations:\n      - method: POST\n        name: createhttplistenerpolicy\n        description: Kgateway Create an HTTPListenerPolicy\n        call: kgateway.createhttplistenerpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/httplistenerpolicies/{name}\n      name: gethttplistenerpolicy\n      operations:\n      - method: GET\n        name: gethttplistenerpolicy\n        description: Kgateway Get an HTTPListenerPolicy\n        call: kgateway.gethttplistenerpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/httplistenerpolicies/{name}\n      name: replacehttplistenerpolicy\n      operations:\n      - method: PUT\n        name: replacehttplistenerpolicy\n        description: Kgateway Replace an HTTPListenerPolicy\n        call: kgateway.replacehttplistenerpolicy\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/httplistenerpolicies/{name}\n      name: deletehttplistenerpolicy\n      operations:\n      - method: DELETE\n        name: deletehttplistenerpolicy\n        description: Kgateway Delete an HTTPListenerPolicy\n        call: kgateway.deletehttplistenerpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/aibackends\n      name: listaibackends\n      operations:\n      - method: GET\n        name: listaibackends\n        description: Kgateway List AIBackend resources\n        call: kgateway.listaibackends\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/aibackends\n      name: createaibackend\n      operations:\n      - method: POST\n        name: createaibackend\n        description: Kgateway Create an AIBackend\n        call: kgateway.createaibackend\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/aibackends/{name}\n      name: getaibackend\n      operations:\n      - method: GET\n        name: getaibackend\n        description: Kgateway Get an AIBackend\n        call: kgateway.getaibackend\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/aibackends/{name}\n      name: replaceaibackend\n      operations:\n      - method: PUT\n        name: replaceaibackend\n        description: Kgateway Replace an AIBackend\n        call: kgateway.replaceaibackend\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /namespaces/{namespace}/aibackends/{name}\n      name: deleteaibackend\n      operations:\n      - method: DELETE\n        name: deleteaibackend\n        description: Kgateway Delete an AIBackend\n        call: kgateway.deleteaibackend\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: kgateway-mcp\n    transport: http\n    description: MCP adapter for kgateway Kubernetes Gateway API for AI agent use.\n    tools:\n    - name: listtrafficpolicies\n      description: Kgateway List TrafficPolicy resources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.listtrafficpolicies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtrafficpolicy\n      description: Kgateway Create a TrafficPolicy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kgateway.createtrafficpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettrafficpolicy\n      description: Kgateway Get a TrafficPolicy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.gettrafficpolicy\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: replacetrafficpolicy\n      description: Kgateway Replace a TrafficPolicy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kgateway.replacetrafficpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetrafficpolicy\n      description: Kgateway Delete a TrafficPolicy\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kgateway.deletetrafficpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbackends\n      description: Kgateway List Backend resources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.listbackends\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbackend\n      description: Kgateway Create a Backend\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: kgateway.createbackend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbackend\n      description: Kgateway Get a Backend\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.getbackend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacebackend\n      description: Kgateway Replace a Backend\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kgateway.replacebackend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebackend\n      description: Kgateway Delete a Backend\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kgateway.deletebackend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdirectresponses\n\
  \      description: Kgateway List DirectResponse resources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.listdirectresponses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdirectresponse\n      description: Kgateway Create a DirectResponse\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kgateway.createdirectresponse\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdirectresponse\n      description: Kgateway Get a DirectResponse\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.getdirectresponse\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacedirectresponse\n      description: Kgateway Replace a DirectResponse\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ true\n      call: kgateway.replacedirectresponse\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedirectresponse\n      description: Kgateway Delete a DirectResponse\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kgateway.deletedirectresponse\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgatewayextensions\n      description: Kgateway List GatewayExtension resources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.listgatewayextensions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategatewayextension\n      description: Kgateway Create a GatewayExtension\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kgateway.creategatewayextension\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getgatewayextension\n      description: Kgateway Get a GatewayExtension\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.getgatewayextension\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacegatewayextension\n      description: Kgateway Replace a GatewayExtension\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kgateway.replacegatewayextension\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletegatewayextension\n      description: Kgateway Delete a GatewayExtension\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kgateway.deletegatewayextension\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgatewayparameters\n      description: Kgateway List GatewayParameters resources\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.listgatewayparameters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategatewayparameters\n      description: Kgateway Create GatewayParameters\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kgateway.creategatewayparameters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgatewayparameters\n      description: Kgateway Get GatewayParameters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.getgatewayparameters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacegatewayparameters\n      description: Kgateway Replace GatewayParameters\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kgateway.replacegatewayparameters\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletegatewayparameters\n      description: Kgateway Delete GatewayParameters\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kgateway.deletegatewayparameters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listhttplistenerpolicies\n      description: Kgateway List HTTPListenerPolicy resources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.listhttplistenerpolicies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createhttplistenerpolicy\n      description: Kgateway Create an HTTPListenerPolicy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kgateway.createhttplistenerpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethttplistenerpolicy\n\
  \      description: Kgateway Get an HTTPListenerPolicy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.gethttplistenerpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacehttplistenerpolicy\n      description: Kgateway Replace an HTTPListenerPolicy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kgateway.replacehttplistenerpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletehttplistenerpolicy\n      description: Kgateway Delete an HTTPListenerPolicy\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kgateway.deletehttplistenerpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listaibackends\n      description: Kgateway List AIBackend resources\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: kgateway.listaibackends\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createaibackend\n      description: Kgateway Create an AIBackend\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kgateway.createaibackend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaibackend\n      description: Kgateway Get an AIBackend\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kgateway.getaibackend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replaceaibackend\n      description: Kgateway Replace an AIBackend\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kgateway.replaceaibackend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteaibackend\n     \
  \ description: Kgateway Delete an AIBackend\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kgateway.deleteaibackend\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    KGATEWAY_TOKEN: KGATEWAY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/kgateway/refs/heads/main/capabilities/kgateway-capability.yaml
tags:
- Kgateway
- API
tools:
- description: Kgateway List TrafficPolicy resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtrafficpolicies
- description: Kgateway Create a TrafficPolicy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtrafficpolicy
- description: Kgateway Get a TrafficPolicy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettrafficpolicy
- description: Kgateway Replace a TrafficPolicy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacetrafficpolicy
- description: Kgateway Delete a TrafficPolicy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetrafficpolicy
- description: Kgateway List Backend resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbackends
- description: Kgateway Create a Backend
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbackend
- description: Kgateway Get a Backend
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbackend
- description: Kgateway Replace a Backend
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacebackend
- description: Kgateway Delete a Backend
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebackend
- description: Kgateway List DirectResponse resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdirectresponses
- description: Kgateway Create a DirectResponse
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdirectresponse
- description: Kgateway Get a DirectResponse
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdirectresponse
- description: Kgateway Replace a DirectResponse
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacedirectresponse
- description: Kgateway Delete a DirectResponse
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedirectresponse
- description: Kgateway List GatewayExtension resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgatewayextensions
- description: Kgateway Create a GatewayExtension
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategatewayextension
- description: Kgateway Get a GatewayExtension
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgatewayextension
- description: Kgateway Replace a GatewayExtension
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacegatewayextension
- description: Kgateway Delete a GatewayExtension
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegatewayextension
- description: Kgateway List GatewayParameters resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgatewayparameters
- description: Kgateway Create GatewayParameters
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategatewayparameters
- description: Kgateway Get GatewayParameters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgatewayparameters
- description: Kgateway Replace GatewayParameters
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacegatewayparameters
- description: Kgateway Delete GatewayParameters
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegatewayparameters
- description: Kgateway List HTTPListenerPolicy resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listhttplistenerpolicies
- description: Kgateway Create an HTTPListenerPolicy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createhttplistenerpolicy
- description: Kgateway Get an HTTPListenerPolicy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethttplistenerpolicy
- description: Kgateway Replace an HTTPListenerPolicy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacehttplistenerpolicy
- description: Kgateway Delete an HTTPListenerPolicy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletehttplistenerpolicy
- description: Kgateway List AIBackend resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaibackends
- description: Kgateway Create an AIBackend
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaibackend
- description: Kgateway Get an AIBackend
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaibackend
- description: Kgateway Replace an AIBackend
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replaceaibackend
- description: Kgateway Delete an AIBackend
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaibackend
---
