---
categories: []
consumed_apis: []
description: The Kubernetes API lets you query and manipulate the state of objects in Kubernetes. The core of Kubernetes control plane is the API server and the HTTP API that it exposes. Users, the different parts of your cluster, and external components all communicate with one another through the API server. The API is a resource-based (RESTful) programmatic interface provided via HTTP that supports retrieving, creating, updating, and deleting primary resources via the standard HTTP verbs (POST, PUT, PATCH, DELETE, GET).
layout: capability
name: Kubernetes API
operations:
- description: Kubernetes List namespaces
  method: GET
  name: listnamespaces
  path: /api/v1/namespaces
- description: Kubernetes Create a namespace
  method: POST
  name: createnamespace
  path: /api/v1/namespaces
- description: Kubernetes Get a namespace
  method: GET
  name: getnamespace
  path: /api/v1/namespaces/{name}
- description: Kubernetes Replace a namespace
  method: PUT
  name: replacenamespace
  path: /api/v1/namespaces/{name}
- description: Kubernetes Delete a namespace
  method: DELETE
  name: deletenamespace
  path: /api/v1/namespaces/{name}
- description: Kubernetes List pods in a namespace
  method: GET
  name: listnamespacedpods
  path: /api/v1/namespaces/{namespace}/pods
- description: Kubernetes Create a pod
  method: POST
  name: createnamespacedpod
  path: /api/v1/namespaces/{namespace}/pods
- description: Kubernetes Get a pod
  method: GET
  name: getnamespacedpod
  path: /api/v1/namespaces/{namespace}/pods/{name}
- description: Kubernetes Replace a pod
  method: PUT
  name: replacenamespacedpod
  path: /api/v1/namespaces/{namespace}/pods/{name}
- description: Kubernetes Delete a pod
  method: DELETE
  name: deletenamespacedpod
  path: /api/v1/namespaces/{namespace}/pods/{name}
- description: Kubernetes Read pod logs
  method: GET
  name: readnamespacedpodlog
  path: /api/v1/namespaces/{namespace}/pods/{name}/log
- description: Kubernetes List deployments in a namespace
  method: GET
  name: listnamespaceddeployments
  path: /apis/apps/v1/namespaces/{namespace}/deployments
- description: Kubernetes Create a deployment
  method: POST
  name: createnamespaceddeployment
  path: /apis/apps/v1/namespaces/{namespace}/deployments
- description: Kubernetes Get a deployment
  method: GET
  name: getnamespaceddeployment
  path: /apis/apps/v1/namespaces/{namespace}/deployments/{name}
- description: Kubernetes Replace a deployment
  method: PUT
  name: replacenamespaceddeployment
  path: /apis/apps/v1/namespaces/{namespace}/deployments/{name}
- description: Kubernetes Delete a deployment
  method: DELETE
  name: deletenamespaceddeployment
  path: /apis/apps/v1/namespaces/{namespace}/deployments/{name}
- description: Kubernetes Get deployment scale
  method: GET
  name: getnamespaceddeploymentscale
  path: /apis/apps/v1/namespaces/{namespace}/deployments/{name}/scale
- description: Kubernetes Scale a deployment
  method: PUT
  name: replacenamespaceddeploymentscale
  path: /apis/apps/v1/namespaces/{namespace}/deployments/{name}/scale
- description: Kubernetes List services in a namespace
  method: GET
  name: listnamespacedservices
  path: /api/v1/namespaces/{namespace}/services
- description: Kubernetes Create a service
  method: POST
  name: createnamespacedservice
  path: /api/v1/namespaces/{namespace}/services
- description: Kubernetes Get a service
  method: GET
  name: getnamespacedservice
  path: /api/v1/namespaces/{namespace}/services/{name}
- description: Kubernetes Replace a service
  method: PUT
  name: replacenamespacedservice
  path: /api/v1/namespaces/{namespace}/services/{name}
- description: Kubernetes Delete a service
  method: DELETE
  name: deletenamespacedservice
  path: /api/v1/namespaces/{namespace}/services/{name}
- description: Kubernetes List ConfigMaps in a namespace
  method: GET
  name: listnamespacedconfigmaps
  path: /api/v1/namespaces/{namespace}/configmaps
- description: Kubernetes Create a ConfigMap
  method: POST
  name: createnamespacedconfigmap
  path: /api/v1/namespaces/{namespace}/configmaps
- description: Kubernetes List Secrets in a namespace
  method: GET
  name: listnamespacedsecrets
  path: /api/v1/namespaces/{namespace}/secrets
- description: Kubernetes Create a Secret
  method: POST
  name: createnamespacedsecret
  path: /api/v1/namespaces/{namespace}/secrets
- description: Kubernetes List nodes
  method: GET
  name: listnodes
  path: /api/v1/nodes
- description: Kubernetes Get a node
  method: GET
  name: getnode
  path: /api/v1/nodes/{name}
- description: Kubernetes List ClusterRoles
  method: GET
  name: listclusterroles
  path: /apis/rbac.authorization.k8s.io/v1/clusterroles
- description: Kubernetes Create a ClusterRole
  method: POST
  name: createclusterrole
  path: /apis/rbac.authorization.k8s.io/v1/clusterroles
- description: Kubernetes List HorizontalPodAutoscalers in a namespace
  method: GET
  name: listnamespacedhorizontalpodautoscalers
  path: /apis/autoscaling/v2/namespaces/{namespace}/horizontalpodautoscalers
- description: Kubernetes Create a HorizontalPodAutoscaler
  method: POST
  name: createnamespacedhorizontalpodautoscaler
  path: /apis/autoscaling/v2/namespaces/{namespace}/horizontalpodautoscalers
- description: Kubernetes List events in a namespace
  method: GET
  name: listnamespacedevents
  path: /apis/events.k8s.io/v1/namespaces/{namespace}/events
personas: []
provider_name: Kubernetes
provider_slug: kubernetes
search_terms:
- getnamespacedpod
- scaling
- containers
- kubernetes list horizontalpodautoscalers in a namespace
- kubernetes delete a deployment
- api
- listnamespacedevents
- listnamespacedsecrets
- listnamespacedpods
- kubernetes get a pod
- deployment
- kubernetes create a deployment
- kubernetes replace a namespace
- kubernetes delete a pod
- cncf
- kubernetes read pod logs
- kubernetes create a namespace
- kubernetes get a namespace
- createnamespacedhorizontalpodautoscaler
- replacenamespaceddeploymentscale
- createnamespacedpod
- kubernetes get a node
- kubernetes create a secret
- kubernetes list nodes
- replacenamespacedpod
- replacenamespace
- kubernetes list services in a namespace
- deletenamespace
- getnamespace
- replacenamespacedservice
- cloud native
- deletenamespaceddeployment
- deletenamespacedpod
- listclusterroles
- readnamespacedpodlog
- kubernetes delete a service
- listnamespacedservices
- createnamespacedconfigmap
- kubernetes scale a deployment
- kubernetes create a clusterrole
- kubernetes list namespaces
- getnamespaceddeploymentscale
- listnamespacedhorizontalpodautoscalers
- kubernetes create a horizontalpodautoscaler
- createclusterrole
- listnamespaces
- kubernetes delete a namespace
- automation
- replacenamespaceddeployment
- kubernetes list clusterroles
- listnodes
- kubernetes list secrets in a namespace
- kubernetes
- getnode
- createnamespace
- kubernetes replace a service
- kubernetes list pods in a namespace
- kubernetes get a deployment
- listnamespacedconfigmaps
- getnamespaceddeployment
- listnamespaceddeployments
- deletenamespacedservice
- createnamespacedsecret
- getnamespacedservice
- kubernetes list events in a namespace
- open source
- kubernetes create a pod
- orchestration
- kubernetes create a configmap
- kubernetes get deployment scale
- kubernetes create a service
- createnamespacedservice
- kubernetes replace a deployment
- kubernetes list configmaps in a namespace
- kubernetes replace a pod
- kubernetes get a service
- kubernetes list deployments in a namespace
- createnamespaceddeployment
slug: kubernetes-capability
source_filename: kubernetes-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Kubernetes API\n  description: The Kubernetes API lets you query and manipulate the state of objects in Kubernetes. The core of Kubernetes\n    control plane is the API server and the HTTP API that it exposes. Users, the different parts of your cluster, and external\n    components all communicate with one another through the API server. The API is a resource-based (RESTful) programmatic\n    interface provided via HTTP that supports retrieving, creating, updating, and deleting primary resources via the standard\n    HTTP verbs (POST, PUT, PATCH, DELETE, GET).\n  tags:\n  - Kubernetes\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: kubernetes\n    baseUri: https://kubernetes.default.svc\n    description: Kubernetes API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{KUBERNETES_TOKEN}}'\n    resources:\n    - name: api-v1-namespaces\n      path: /api/v1/namespaces\n\
  \      operations:\n      - name: listnamespaces\n        method: GET\n        description: Kubernetes List namespaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespace\n        method: POST\n        description: Kubernetes Create a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-namespaces-name\n      path: /api/v1/namespaces/{name}\n      operations:\n      - name: getnamespace\n        method: GET\n        description: Kubernetes Get a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacenamespace\n        method: PUT\n        description: Kubernetes Replace a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: deletenamespace\n        method: DELETE\n        description: Kubernetes Delete a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-namespaces-namespace-pods\n      path: /api/v1/namespaces/{namespace}/pods\n      operations:\n      - name: listnamespacedpods\n        method: GET\n        description: Kubernetes List pods in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespacedpod\n        method: POST\n        description: Kubernetes Create a pod\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-namespaces-namespace-pods-name\n      path: /api/v1/namespaces/{namespace}/pods/{name}\n      operations:\n      - name: getnamespacedpod\n\
  \        method: GET\n        description: Kubernetes Get a pod\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacenamespacedpod\n        method: PUT\n        description: Kubernetes Replace a pod\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenamespacedpod\n        method: DELETE\n        description: Kubernetes Delete a pod\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-namespaces-namespace-pods-name-log\n      path: /api/v1/namespaces/{namespace}/pods/{name}/log\n      operations:\n      - name: readnamespacedpodlog\n        method: GET\n        description: Kubernetes Read pod logs\n        inputParameters:\n        - name: container\n          in: query\n          type: string\n        \
  \  description: Name of the container to read logs from. Defaults to only container if there is only one, otherwise\n            required.\n        - name: follow\n          in: query\n          type: boolean\n          description: Whether to stream log output. If false, returns current log snapshot.\n        - name: tailLines\n          in: query\n          type: integer\n          description: Number of lines from the end of the log to retrieve.\n        - name: sinceSeconds\n          in: query\n          type: integer\n          description: Only return logs newer than a relative duration in seconds.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-apps-v1-namespaces-namespace-deployments\n      path: /apis/apps/v1/namespaces/{namespace}/deployments\n      operations:\n      - name: listnamespaceddeployments\n        method: GET\n        description: Kubernetes List deployments in a namespace\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespaceddeployment\n        method: POST\n        description: Kubernetes Create a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-apps-v1-namespaces-namespace-deployments-na\n      path: /apis/apps/v1/namespaces/{namespace}/deployments/{name}\n      operations:\n      - name: getnamespaceddeployment\n        method: GET\n        description: Kubernetes Get a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacenamespaceddeployment\n        method: PUT\n        description: Kubernetes Replace a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: deletenamespaceddeployment\n        method: DELETE\n        description: Kubernetes Delete a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-apps-v1-namespaces-namespace-deployments-na\n      path: /apis/apps/v1/namespaces/{namespace}/deployments/{name}/scale\n      operations:\n      - name: getnamespaceddeploymentscale\n        method: GET\n        description: Kubernetes Get deployment scale\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacenamespaceddeploymentscale\n        method: PUT\n        description: Kubernetes Scale a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-namespaces-namespace-services\n      path: /api/v1/namespaces/{namespace}/services\n\
  \      operations:\n      - name: listnamespacedservices\n        method: GET\n        description: Kubernetes List services in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespacedservice\n        method: POST\n        description: Kubernetes Create a service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-namespaces-namespace-services-name\n      path: /api/v1/namespaces/{namespace}/services/{name}\n      operations:\n      - name: getnamespacedservice\n        method: GET\n        description: Kubernetes Get a service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacenamespacedservice\n        method: PUT\n        description: Kubernetes Replace a service\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenamespacedservice\n        method: DELETE\n        description: Kubernetes Delete a service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-namespaces-namespace-configmaps\n      path: /api/v1/namespaces/{namespace}/configmaps\n      operations:\n      - name: listnamespacedconfigmaps\n        method: GET\n        description: Kubernetes List ConfigMaps in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespacedconfigmap\n        method: POST\n        description: Kubernetes Create a ConfigMap\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-namespaces-namespace-secrets\n\
  \      path: /api/v1/namespaces/{namespace}/secrets\n      operations:\n      - name: listnamespacedsecrets\n        method: GET\n        description: Kubernetes List Secrets in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespacedsecret\n        method: POST\n        description: Kubernetes Create a Secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-nodes\n      path: /api/v1/nodes\n      operations:\n      - name: listnodes\n        method: GET\n        description: Kubernetes List nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-nodes-name\n      path: /api/v1/nodes/{name}\n      operations:\n      - name: getnode\n        method: GET\n        description: Kubernetes\
  \ Get a node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-rbac-authorization-k8s-io-v1-clusterroles\n      path: /apis/rbac.authorization.k8s.io/v1/clusterroles\n      operations:\n      - name: listclusterroles\n        method: GET\n        description: Kubernetes List ClusterRoles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createclusterrole\n        method: POST\n        description: Kubernetes Create a ClusterRole\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-autoscaling-v2-namespaces-namespace-horizon\n      path: /apis/autoscaling/v2/namespaces/{namespace}/horizontalpodautoscalers\n      operations:\n      - name: listnamespacedhorizontalpodautoscalers\n        method: GET\n        description:\
  \ Kubernetes List HorizontalPodAutoscalers in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespacedhorizontalpodautoscaler\n        method: POST\n        description: Kubernetes Create a HorizontalPodAutoscaler\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-events-k8s-io-v1-namespaces-namespace-event\n      path: /apis/events.k8s.io/v1/namespaces/{namespace}/events\n      operations:\n      - name: listnamespacedevents\n        method: GET\n        description: Kubernetes List events in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kubernetes-rest\n    description: REST adapter for Kubernetes API.\n    resources:\n    - path:\
  \ /api/v1/namespaces\n      name: listnamespaces\n      operations:\n      - method: GET\n        name: listnamespaces\n        description: Kubernetes List namespaces\n        call: kubernetes.listnamespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces\n      name: createnamespace\n      operations:\n      - method: POST\n        name: createnamespace\n        description: Kubernetes Create a namespace\n        call: kubernetes.createnamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{name}\n      name: getnamespace\n      operations:\n      - method: GET\n        name: getnamespace\n        description: Kubernetes Get a namespace\n        call: kubernetes.getnamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{name}\n      name: replacenamespace\n      operations:\n      - method: PUT\n        name:\
  \ replacenamespace\n        description: Kubernetes Replace a namespace\n        call: kubernetes.replacenamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{name}\n      name: deletenamespace\n      operations:\n      - method: DELETE\n        name: deletenamespace\n        description: Kubernetes Delete a namespace\n        call: kubernetes.deletenamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/pods\n      name: listnamespacedpods\n      operations:\n      - method: GET\n        name: listnamespacedpods\n        description: Kubernetes List pods in a namespace\n        call: kubernetes.listnamespacedpods\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/pods\n      name: createnamespacedpod\n      operations:\n      - method: POST\n        name: createnamespacedpod\n        description:\
  \ Kubernetes Create a pod\n        call: kubernetes.createnamespacedpod\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/pods/{name}\n      name: getnamespacedpod\n      operations:\n      - method: GET\n        name: getnamespacedpod\n        description: Kubernetes Get a pod\n        call: kubernetes.getnamespacedpod\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/pods/{name}\n      name: replacenamespacedpod\n      operations:\n      - method: PUT\n        name: replacenamespacedpod\n        description: Kubernetes Replace a pod\n        call: kubernetes.replacenamespacedpod\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/pods/{name}\n      name: deletenamespacedpod\n      operations:\n      - method: DELETE\n        name: deletenamespacedpod\n        description: Kubernetes Delete\
  \ a pod\n        call: kubernetes.deletenamespacedpod\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/pods/{name}/log\n      name: readnamespacedpodlog\n      operations:\n      - method: GET\n        name: readnamespacedpodlog\n        description: Kubernetes Read pod logs\n        call: kubernetes.readnamespacedpodlog\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/apps/v1/namespaces/{namespace}/deployments\n      name: listnamespaceddeployments\n      operations:\n      - method: GET\n        name: listnamespaceddeployments\n        description: Kubernetes List deployments in a namespace\n        call: kubernetes.listnamespaceddeployments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/apps/v1/namespaces/{namespace}/deployments\n      name: createnamespaceddeployment\n      operations:\n      - method: POST\n        name: createnamespaceddeployment\n\
  \        description: Kubernetes Create a deployment\n        call: kubernetes.createnamespaceddeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/apps/v1/namespaces/{namespace}/deployments/{name}\n      name: getnamespaceddeployment\n      operations:\n      - method: GET\n        name: getnamespaceddeployment\n        description: Kubernetes Get a deployment\n        call: kubernetes.getnamespaceddeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/apps/v1/namespaces/{namespace}/deployments/{name}\n      name: replacenamespaceddeployment\n      operations:\n      - method: PUT\n        name: replacenamespaceddeployment\n        description: Kubernetes Replace a deployment\n        call: kubernetes.replacenamespaceddeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/apps/v1/namespaces/{namespace}/deployments/{name}\n      name: deletenamespaceddeployment\n\
  \      operations:\n      - method: DELETE\n        name: deletenamespaceddeployment\n        description: Kubernetes Delete a deployment\n        call: kubernetes.deletenamespaceddeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/apps/v1/namespaces/{namespace}/deployments/{name}/scale\n      name: getnamespaceddeploymentscale\n      operations:\n      - method: GET\n        name: getnamespaceddeploymentscale\n        description: Kubernetes Get deployment scale\n        call: kubernetes.getnamespaceddeploymentscale\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/apps/v1/namespaces/{namespace}/deployments/{name}/scale\n      name: replacenamespaceddeploymentscale\n      operations:\n      - method: PUT\n        name: replacenamespaceddeploymentscale\n        description: Kubernetes Scale a deployment\n        call: kubernetes.replacenamespaceddeploymentscale\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/services\n      name: listnamespacedservices\n      operations:\n      - method: GET\n        name: listnamespacedservices\n        description: Kubernetes List services in a namespace\n        call: kubernetes.listnamespacedservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/services\n      name: createnamespacedservice\n      operations:\n      - method: POST\n        name: createnamespacedservice\n        description: Kubernetes Create a service\n        call: kubernetes.createnamespacedservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/services/{name}\n      name: getnamespacedservice\n      operations:\n      - method: GET\n        name: getnamespacedservice\n        description: Kubernetes Get a service\n        call: kubernetes.getnamespacedservice\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/services/{name}\n      name: replacenamespacedservice\n      operations:\n      - method: PUT\n        name: replacenamespacedservice\n        description: Kubernetes Replace a service\n        call: kubernetes.replacenamespacedservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/services/{name}\n      name: deletenamespacedservice\n      operations:\n      - method: DELETE\n        name: deletenamespacedservice\n        description: Kubernetes Delete a service\n        call: kubernetes.deletenamespacedservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/configmaps\n      name: listnamespacedconfigmaps\n      operations:\n      - method: GET\n        name: listnamespacedconfigmaps\n        description: Kubernetes List ConfigMaps\
  \ in a namespace\n        call: kubernetes.listnamespacedconfigmaps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/configmaps\n      name: createnamespacedconfigmap\n      operations:\n      - method: POST\n        name: createnamespacedconfigmap\n        description: Kubernetes Create a ConfigMap\n        call: kubernetes.createnamespacedconfigmap\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/secrets\n      name: listnamespacedsecrets\n      operations:\n      - method: GET\n        name: listnamespacedsecrets\n        description: Kubernetes List Secrets in a namespace\n        call: kubernetes.listnamespacedsecrets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/namespaces/{namespace}/secrets\n      name: createnamespacedsecret\n      operations:\n      - method: POST\n        name: createnamespacedsecret\n\
  \        description: Kubernetes Create a Secret\n        call: kubernetes.createnamespacedsecret\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/nodes\n      name: listnodes\n      operations:\n      - method: GET\n        name: listnodes\n        description: Kubernetes List nodes\n        call: kubernetes.listnodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/nodes/{name}\n      name: getnode\n      operations:\n      - method: GET\n        name: getnode\n        description: Kubernetes Get a node\n        call: kubernetes.getnode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/rbac.authorization.k8s.io/v1/clusterroles\n      name: listclusterroles\n      operations:\n      - method: GET\n        name: listclusterroles\n        description: Kubernetes List ClusterRoles\n        call: kubernetes.listclusterroles\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /apis/rbac.authorization.k8s.io/v1/clusterroles\n      name: createclusterrole\n      operations:\n      - method: POST\n        name: createclusterrole\n        description: Kubernetes Create a ClusterRole\n        call: kubernetes.createclusterrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/autoscaling/v2/namespaces/{namespace}/horizontalpodautoscalers\n      name: listnamespacedhorizontalpodautoscalers\n      operations:\n      - method: GET\n        name: listnamespacedhorizontalpodautoscalers\n        description: Kubernetes List HorizontalPodAutoscalers in a namespace\n        call: kubernetes.listnamespacedhorizontalpodautoscalers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/autoscaling/v2/namespaces/{namespace}/horizontalpodautoscalers\n      name: createnamespacedhorizontalpodautoscaler\n      operations:\n      - method: POST\n\
  \        name: createnamespacedhorizontalpodautoscaler\n        description: Kubernetes Create a HorizontalPodAutoscaler\n        call: kubernetes.createnamespacedhorizontalpodautoscaler\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/events.k8s.io/v1/namespaces/{namespace}/events\n      name: listnamespacedevents\n      operations:\n      - method: GET\n        name: listnamespacedevents\n        description: Kubernetes List events in a namespace\n        call: kubernetes.listnamespacedevents\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: kubernetes-mcp\n    transport: http\n    description: MCP adapter for Kubernetes API for AI agent use.\n    tools:\n    - name: listnamespaces\n      description: Kubernetes List namespaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.listnamespaces\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createnamespace\n      description: Kubernetes Create a namespace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kubernetes.createnamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnamespace\n      description: Kubernetes Get a namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.getnamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacenamespace\n      description: Kubernetes Replace a namespace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kubernetes.replacenamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespace\n      description: Kubernetes Delete a namespace\n      hints:\n        readOnly: false\n   \
  \     destructive: true\n        idempotent: true\n      call: kubernetes.deletenamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespacedpods\n      description: Kubernetes List pods in a namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.listnamespacedpods\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespacedpod\n      description: Kubernetes Create a pod\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kubernetes.createnamespacedpod\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnamespacedpod\n      description: Kubernetes Get a pod\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.getnamespacedpod\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: replacenamespacedpod\n      description: Kubernetes Replace a pod\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kubernetes.replacenamespacedpod\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespacedpod\n      description: Kubernetes Delete a pod\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kubernetes.deletenamespacedpod\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readnamespacedpodlog\n      description: Kubernetes Read pod logs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.readnamespacedpodlog\n      with:\n        container: tools.container\n        follow: tools.follow\n        tailLines: tools.tailLines\n        sinceSeconds: tools.sinceSeconds\n      inputParameters:\n      - name: container\n     \
  \   type: string\n        description: Name of the container to read logs from. Defaults to only container if there is only one, otherwise required.\n      - name: follow\n        type: boolean\n        description: Whether to stream log output. If false, returns current log snapshot.\n      - name: tailLines\n        type: integer\n        description: Number of lines from the end of the log to retrieve.\n      - name: sinceSeconds\n        type: integer\n        description: Only return logs newer than a relative duration in seconds.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespaceddeployments\n      description: Kubernetes List deployments in a namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.listnamespaceddeployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespaceddeployment\n      description: Kubernetes Create\
  \ a deployment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kubernetes.createnamespaceddeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnamespaceddeployment\n      description: Kubernetes Get a deployment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.getnamespaceddeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacenamespaceddeployment\n      description: Kubernetes Replace a deployment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kubernetes.replacenamespaceddeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespaceddeployment\n      description: Kubernetes Delete a deployment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: kubernetes.deletenamespaceddeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnamespaceddeploymentscale\n      description: Kubernetes Get deployment scale\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.getnamespaceddeploymentscale\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacenamespaceddeploymentscale\n      description: Kubernetes Scale a deployment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kubernetes.replacenamespaceddeploymentscale\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespacedservices\n      description: Kubernetes List services in a namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.listnamespacedservices\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createnamespacedservice\n      description: Kubernetes Create a service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kubernetes.createnamespacedservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnamespacedservice\n      description: Kubernetes Get a service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.getnamespacedservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacenamespacedservice\n      description: Kubernetes Replace a service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kubernetes.replacenamespacedservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespacedservice\n      description: Kubernetes Delete a service\n\
  \      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kubernetes.deletenamespacedservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespacedconfigmaps\n      description: Kubernetes List ConfigMaps in a namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.listnamespacedconfigmaps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespacedconfigmap\n      description: Kubernetes Create a ConfigMap\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kubernetes.createnamespacedconfigmap\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespacedsecrets\n      description: Kubernetes List Secrets in a namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: kubernetes.listnamespacedsecrets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespacedsecret\n      description: Kubernetes Create a Secret\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kubernetes.createnamespacedsecret\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnodes\n      description: Kubernetes List nodes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.listnodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnode\n      description: Kubernetes Get a node\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.getnode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclusterroles\n      description: Kubernetes List ClusterRoles\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubernetes.listclusterroles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createclusterrole\n      description: Kubernetes Create a ClusterRole\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kubernetes.createclusterrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespacedhorizontalpodautoscalers\n      description: Kubernetes List HorizontalPodAutoscalers in a namespace\n      hints:\n        readOnly: true\n        destructive: fa\n\n# --- truncated at 32 KB (32 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/kubernetes/refs/heads/main/capabilities/kubernetes-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/kubernetes/refs/heads/main/capabilities/kubernetes-capability.yaml
tags:
- Kubernetes
- API
tools:
- description: Kubernetes List namespaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespaces
- description: Kubernetes Create a namespace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespace
- description: Kubernetes Get a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnamespace
- description: Kubernetes Replace a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacenamespace
- description: Kubernetes Delete a namespace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespace
- description: Kubernetes List pods in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacedpods
- description: Kubernetes Create a pod
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespacedpod
- description: Kubernetes Get a pod
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnamespacedpod
- description: Kubernetes Replace a pod
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacenamespacedpod
- description: Kubernetes Delete a pod
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespacedpod
- description: Kubernetes Read pod logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readnamespacedpodlog
- description: Kubernetes List deployments in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespaceddeployments
- description: Kubernetes Create a deployment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespaceddeployment
- description: Kubernetes Get a deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnamespaceddeployment
- description: Kubernetes Replace a deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacenamespaceddeployment
- description: Kubernetes Delete a deployment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespaceddeployment
- description: Kubernetes Get deployment scale
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnamespaceddeploymentscale
- description: Kubernetes Scale a deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacenamespaceddeploymentscale
- description: Kubernetes List services in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacedservices
- description: Kubernetes Create a service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespacedservice
- description: Kubernetes Get a service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnamespacedservice
- description: Kubernetes Replace a service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacenamespacedservice
- description: Kubernetes Delete a service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespacedservice
- description: Kubernetes List ConfigMaps in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacedconfigmaps
- description: Kubernetes Create a ConfigMap
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespacedconfigmap
- description: Kubernetes List Secrets in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacedsecrets
- description: Kubernetes Create a Secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespacedsecret
- description: Kubernetes List nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnodes
- description: Kubernetes Get a node
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnode
- description: Kubernetes List ClusterRoles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusterroles
- description: Kubernetes Create a ClusterRole
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createclusterrole
- description: Kubernetes List HorizontalPodAutoscalers in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacedhorizontalpodautoscalers
- description: Kubernetes Create a HorizontalPodAutoscaler
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespacedhorizontalpodautoscaler
- description: Kubernetes List events in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespacedevents
---
