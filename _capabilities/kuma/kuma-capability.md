---
categories: []
consumed_apis: []
description: Kuma API
layout: capability
name: Kuma API
operations:
- description: The index endpoint
  method: GET
  name: index
  path: /
- description: A list of all resources that exist
  method: GET
  name: get-resource-type-description
  path: /_resources
- description: Get Global Insight
  method: GET
  name: get-global-insight
  path: /global-insight
- description: Returns rules matching this dataplane
  method: GET
  name: inspect-dataplanes-rules
  path: /meshes/{mesh}/{resourceType}/{resourceName}/_rules
- description: Get a proxy XDS config on a CP, this endpoint is only available on zone CPs.
  method: GET
  name: get-dataplanes-xds-config
  path: /meshes/{mesh}/dataplanes/{name}/_config
- description: Get networking layout for this dataplane
  method: GET
  name: get-dataplanes-layout
  path: /meshes/{mesh}/dataplanes/{name}/_layout
- description: Get proxy policies for this dataplane
  method: GET
  name: get-proxy-policy-conf
  path: /meshes/{mesh}/dataplanes/{name}/_policies
- description: Get policies for this inbound
  method: GET
  name: get-inbound-policy-conf
  path: /meshes/{mesh}/dataplanes/{name}/_inbounds/{inbound-kri}/_policies
- description: Get policies for this outbound
  method: GET
  name: get-outbound-policy-conf
  path: /meshes/{mesh}/dataplanes/{name}/_outbounds/{kri}/_policies
- description: Get routes configuration for this outbound
  method: GET
  name: get-outbound-routes
  path: /meshes/{mesh}/dataplanes/{name}/_outbounds/{kri}/_routes
- description: Get policies for this route
  method: GET
  name: get-route-policy-conf
  path: /meshes/{mesh}/dataplanes/{name}/_outbounds/{outbound-kri}/_routes/{route-kri}/_policies
- description: Returns resources matched by this policy
  method: GET
  name: inspect-resources
  path: /meshes/{mesh}/{policyType}/{policyName}/_resources/dataplanes
- description: Returns dataplanes matched by a MeshService
  method: GET
  name: inspect-meshservices-dataplanes
  path: /meshes/{mesh}/meshservices/{name}/_dataplanes
- description: Returns hostnames for service
  method: GET
  name: inspect-hostnames
  path: /meshes/{mesh}/{serviceType}/{serviceName}/_hostnames
- description: Returns a resource by KRI
  method: GET
  name: getbykri
  path: /_kri/{kri}
- description: Returns MeshAccessLog entity
  method: GET
  name: getmeshaccesslog
  path: /meshes/{mesh}/meshaccesslogs/{name}
- description: Creates or Updates MeshAccessLog entity
  method: PUT
  name: putmeshaccesslog
  path: /meshes/{mesh}/meshaccesslogs/{name}
- description: Deletes MeshAccessLog entity
  method: DELETE
  name: deletemeshaccesslog
  path: /meshes/{mesh}/meshaccesslogs/{name}
- description: Returns a list of MeshAccessLog in the mesh.
  method: GET
  name: getmeshaccessloglist
  path: /meshes/{mesh}/meshaccesslogs
- description: Returns MeshCircuitBreaker entity
  method: GET
  name: getmeshcircuitbreaker
  path: /meshes/{mesh}/meshcircuitbreakers/{name}
- description: Creates or Updates MeshCircuitBreaker entity
  method: PUT
  name: putmeshcircuitbreaker
  path: /meshes/{mesh}/meshcircuitbreakers/{name}
- description: Deletes MeshCircuitBreaker entity
  method: DELETE
  name: deletemeshcircuitbreaker
  path: /meshes/{mesh}/meshcircuitbreakers/{name}
- description: Returns a list of MeshCircuitBreaker in the mesh.
  method: GET
  name: getmeshcircuitbreakerlist
  path: /meshes/{mesh}/meshcircuitbreakers
- description: Returns MeshFaultInjection entity
  method: GET
  name: getmeshfaultinjection
  path: /meshes/{mesh}/meshfaultinjections/{name}
- description: Creates or Updates MeshFaultInjection entity
  method: PUT
  name: putmeshfaultinjection
  path: /meshes/{mesh}/meshfaultinjections/{name}
- description: Deletes MeshFaultInjection entity
  method: DELETE
  name: deletemeshfaultinjection
  path: /meshes/{mesh}/meshfaultinjections/{name}
- description: Returns a list of MeshFaultInjection in the mesh.
  method: GET
  name: getmeshfaultinjectionlist
  path: /meshes/{mesh}/meshfaultinjections
- description: Returns MeshHealthCheck entity
  method: GET
  name: getmeshhealthcheck
  path: /meshes/{mesh}/meshhealthchecks/{name}
- description: Creates or Updates MeshHealthCheck entity
  method: PUT
  name: putmeshhealthcheck
  path: /meshes/{mesh}/meshhealthchecks/{name}
- description: Deletes MeshHealthCheck entity
  method: DELETE
  name: deletemeshhealthcheck
  path: /meshes/{mesh}/meshhealthchecks/{name}
- description: Returns a list of MeshHealthCheck in the mesh.
  method: GET
  name: getmeshhealthchecklist
  path: /meshes/{mesh}/meshhealthchecks
- description: Returns MeshHTTPRoute entity
  method: GET
  name: getmeshhttproute
  path: /meshes/{mesh}/meshhttproutes/{name}
- description: Creates or Updates MeshHTTPRoute entity
  method: PUT
  name: putmeshhttproute
  path: /meshes/{mesh}/meshhttproutes/{name}
- description: Deletes MeshHTTPRoute entity
  method: DELETE
  name: deletemeshhttproute
  path: /meshes/{mesh}/meshhttproutes/{name}
- description: Returns a list of MeshHTTPRoute in the mesh.
  method: GET
  name: getmeshhttproutelist
  path: /meshes/{mesh}/meshhttproutes
- description: Returns MeshLoadBalancingStrategy entity
  method: GET
  name: getmeshloadbalancingstrategy
  path: /meshes/{mesh}/meshloadbalancingstrategies/{name}
- description: Creates or Updates MeshLoadBalancingStrategy entity
  method: PUT
  name: putmeshloadbalancingstrategy
  path: /meshes/{mesh}/meshloadbalancingstrategies/{name}
- description: Deletes MeshLoadBalancingStrategy entity
  method: DELETE
  name: deletemeshloadbalancingstrategy
  path: /meshes/{mesh}/meshloadbalancingstrategies/{name}
- description: Returns a list of MeshLoadBalancingStrategy in the mesh.
  method: GET
  name: getmeshloadbalancingstrategylist
  path: /meshes/{mesh}/meshloadbalancingstrategies
- description: Returns MeshMetric entity
  method: GET
  name: getmeshmetric
  path: /meshes/{mesh}/meshmetrics/{name}
- description: Creates or Updates MeshMetric entity
  method: PUT
  name: putmeshmetric
  path: /meshes/{mesh}/meshmetrics/{name}
- description: Deletes MeshMetric entity
  method: DELETE
  name: deletemeshmetric
  path: /meshes/{mesh}/meshmetrics/{name}
- description: Returns a list of MeshMetric in the mesh.
  method: GET
  name: getmeshmetriclist
  path: /meshes/{mesh}/meshmetrics
- description: Returns MeshPassthrough entity
  method: GET
  name: getmeshpassthrough
  path: /meshes/{mesh}/meshpassthroughs/{name}
- description: Creates or Updates MeshPassthrough entity
  method: PUT
  name: putmeshpassthrough
  path: /meshes/{mesh}/meshpassthroughs/{name}
- description: Deletes MeshPassthrough entity
  method: DELETE
  name: deletemeshpassthrough
  path: /meshes/{mesh}/meshpassthroughs/{name}
- description: Returns a list of MeshPassthrough in the mesh.
  method: GET
  name: getmeshpassthroughlist
  path: /meshes/{mesh}/meshpassthroughs
- description: Returns MeshProxyPatch entity
  method: GET
  name: getmeshproxypatch
  path: /meshes/{mesh}/meshproxypatches/{name}
- description: Creates or Updates MeshProxyPatch entity
  method: PUT
  name: putmeshproxypatch
  path: /meshes/{mesh}/meshproxypatches/{name}
- description: Deletes MeshProxyPatch entity
  method: DELETE
  name: deletemeshproxypatch
  path: /meshes/{mesh}/meshproxypatches/{name}
- description: Returns a list of MeshProxyPatch in the mesh.
  method: GET
  name: getmeshproxypatchlist
  path: /meshes/{mesh}/meshproxypatches
- description: Returns MeshRateLimit entity
  method: GET
  name: getmeshratelimit
  path: /meshes/{mesh}/meshratelimits/{name}
- description: Creates or Updates MeshRateLimit entity
  method: PUT
  name: putmeshratelimit
  path: /meshes/{mesh}/meshratelimits/{name}
- description: Deletes MeshRateLimit entity
  method: DELETE
  name: deletemeshratelimit
  path: /meshes/{mesh}/meshratelimits/{name}
- description: Returns a list of MeshRateLimit in the mesh.
  method: GET
  name: getmeshratelimitlist
  path: /meshes/{mesh}/meshratelimits
- description: Returns MeshRetry entity
  method: GET
  name: getmeshretry
  path: /meshes/{mesh}/meshretries/{name}
- description: Creates or Updates MeshRetry entity
  method: PUT
  name: putmeshretry
  path: /meshes/{mesh}/meshretries/{name}
- description: Deletes MeshRetry entity
  method: DELETE
  name: deletemeshretry
  path: /meshes/{mesh}/meshretries/{name}
- description: Returns a list of MeshRetry in the mesh.
  method: GET
  name: getmeshretrylist
  path: /meshes/{mesh}/meshretries
- description: Returns MeshTCPRoute entity
  method: GET
  name: getmeshtcproute
  path: /meshes/{mesh}/meshtcproutes/{name}
personas: []
provider_name: Kuma
provider_slug: kuma
search_terms:
- deletemeshhealthcheck
- returns meshloadbalancingstrategy entity
- deletes meshhttproute entity
- returns meshpassthrough entity
- returns meshaccesslog entity
- inspect resources
- returns dataplanes matched by a meshservice
- returns meshfaultinjection entity
- api
- putmeshproxypatch
- putmeshratelimit
- get proxy policies for this dataplane
- returns a resource by kri
- deletemeshmetric
- getmeshloadbalancingstrategy
- get policies for this inbound
- deletemeshhttproute
- getmeshtcproute
- putmeshfaultinjection
- creates or updates meshmetric entity
- creates or updates meshpassthrough entity
- creates or updates meshhealthcheck entity
- deletemeshcircuitbreaker
- deletemeshproxypatch
- deletemeshpassthrough
- deletes meshaccesslog entity
- get inbound policy conf
- deletes meshcircuitbreaker entity
- returns a list of meshretry in the mesh.
- get policies for this route
- deletes meshmetric entity
- getmeshproxypatchlist
- getmeshratelimit
- returns a list of meshratelimit in the mesh.
- creates or updates meshaccesslog entity
- returns meshproxypatch entity
- getmeshratelimitlist
- kuma
- getmeshretrylist
- returns a list of meshmetric in the mesh.
- get proxy policy conf
- get networking layout for this dataplane
- getmeshfaultinjectionlist
- getmeshfaultinjection
- deletemeshretry
- returns a list of meshpassthrough in the mesh.
- get global insight
- get a proxy xds config on a cp, this endpoint is only available on zone cps.
- deletes meshloadbalancingstrategy entity
- deletes meshhealthcheck entity
- returns a list of meshloadbalancingstrategy in the mesh.
- returns resources matched by this policy
- creates or updates meshhttproute entity
- getmeshcircuitbreakerlist
- returns a list of meshfaultinjection in the mesh.
- putmeshcircuitbreaker
- returns meshretry entity
- putmeshretry
- envoy
- putmeshhttproute
- returns a list of meshhealthcheck in the mesh.
- deletemeshaccesslog
- inspect dataplanes rules
- security
- creates or updates meshratelimit entity
- a list of all resources that exist
- putmeshhealthcheck
- getmeshpassthrough
- putmeshloadbalancingstrategy
- creates or updates meshloadbalancingstrategy entity
- service mesh
- get route policy conf
- deletemeshloadbalancingstrategy
- getmeshmetriclist
- getmeshcircuitbreaker
- get dataplanes layout
- deletes meshproxypatch entity
- kubernetes
- putmeshmetric
- deletemeshfaultinjection
- inspect meshservices dataplanes
- returns meshhealthcheck entity
- returns meshcircuitbreaker entity
- putmeshpassthrough
- returns meshtcproute entity
- returns meshhttproute entity
- the index endpoint
- getmeshpassthroughlist
- deletes meshpassthrough entity
- creates or updates meshproxypatch entity
- microservices
- getmeshaccessloglist
- getmeshaccesslog
- getbykri
- creates or updates meshretry entity
- deletemeshratelimit
- get policies for this outbound
- putmeshaccesslog
- returns a list of meshhttproute in the mesh.
- get outbound policy conf
- returns a list of meshcircuitbreaker in the mesh.
- get resource type description
- inspect hostnames
- returns hostnames for service
- getmeshproxypatch
- get dataplanes xds config
- deletes meshfaultinjection entity
- creates or updates meshfaultinjection entity
- getmeshhttproute
- returns rules matching this dataplane
- get outbound routes
- getmeshloadbalancingstrategylist
- deletes meshratelimit entity
- returns a list of meshproxypatch in the mesh.
- getmeshhealthcheck
- get routes configuration for this outbound
- creates or updates meshcircuitbreaker entity
- getmeshmetric
- getmeshhttproutelist
- getmeshretry
- returns meshmetric entity
- deletes meshretry entity
- returns a list of meshaccesslog in the mesh.
- index
- returns meshratelimit entity
- getmeshhealthchecklist
slug: kuma-capability
source_filename: kuma-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Kuma API\n  description: Kuma API\n  tags:\n  - Kuma\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: kuma\n    baseUri: https://api.example.com\n    description: Kuma API HTTP API.\n    authentication:\n      type: basic\n      username: '{{KUMA_USERNAME}}'\n      password: '{{KUMA_PASSWORD}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: index\n        method: GET\n        description: The index endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resources\n      path: /_resources\n      operations:\n      - name: get-resource-type-description\n        method: GET\n        description: A list of all resources that exist\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: global-insight\n      path: /global-insight\n      operations:\n      - name: get-global-insight\n        method: GET\n        description: Get Global Insight\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-resourcetype-resourcename-rules\n      path: /meshes/{mesh}/{resourceType}/{resourceName}/_rules\n      operations:\n      - name: inspect-dataplanes-rules\n        method: GET\n        description: Returns rules matching this dataplane\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: The mesh the policy is part of\n        - name: resourceType\n          in: path\n          type: string\n          required: true\n          description: The type of resource (only some resources support rules api)\n        - name: resourceName\n          in: path\n          type:\
  \ string\n          required: true\n          description: The name of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-dataplanes-name-config\n      path: /meshes/{mesh}/dataplanes/{name}/_config\n      operations:\n      - name: get-dataplanes-xds-config\n        method: GET\n        description: Get a proxy XDS config on a CP, this endpoint is only available on zone CPs.\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: The mesh of the DPP to get the diff for.\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the DPP within the mesh to get the diff for.\n        - name: shadow\n          in: query\n          type: boolean\n          description: 'When computing XDS config the CP take into account policies\
  \ with ''kuma.io/effect: shadow'' label'\n        - name: include\n          in: query\n          type: array\n          description: An array of extra fields to include in the response. When `include=diff` the server computes a diff\n            in JSONPatch format between the current proxy XDS config and\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-dataplanes-name-layout\n      path: /meshes/{mesh}/dataplanes/{name}/_layout\n      operations:\n      - name: get-dataplanes-layout\n        method: GET\n        description: Get networking layout for this dataplane\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: The mesh of the DPP to get the layout for.\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the DPP within\
  \ the mesh to get the layout for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-dataplanes-name-policies\n      path: /meshes/{mesh}/dataplanes/{name}/_policies\n      operations:\n      - name: get-proxy-policy-conf\n        method: GET\n        description: Get proxy policies for this dataplane\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: The mesh of the DPP to get the diff for.\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the DPP within the mesh to get the diff for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-dataplanes-name-inbounds-inbound-kri\n      path: /meshes/{mesh}/dataplanes/{name}/_inbounds/{inbound-kri}/_policies\n\
  \      operations:\n      - name: get-inbound-policy-conf\n        method: GET\n        description: Get policies for this inbound\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: The mesh of the DPP to get the policies for.\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the DPP within the mesh to get the policies for.\n        - name: inbound-kri\n          in: path\n          type: string\n          required: true\n          description: The name of the Inbound from DPP to get the policies for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-dataplanes-name-outbounds-kri-polici\n      path: /meshes/{mesh}/dataplanes/{name}/_outbounds/{kri}/_policies\n      operations:\n      - name: get-outbound-policy-conf\n \
  \       method: GET\n        description: Get policies for this outbound\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: The mesh of the DPP to get the policies for.\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the DPP within the mesh to get the policies for.\n        - name: kri\n          in: path\n          type: string\n          required: true\n          description: The KRI of the Outbound to get the policies for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-dataplanes-name-outbounds-kri-routes\n      path: /meshes/{mesh}/dataplanes/{name}/_outbounds/{kri}/_routes\n      operations:\n      - name: get-outbound-routes\n        method: GET\n        description: Get routes configuration for this outbound\n\
  \        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: The mesh of the DPP to get the policies for.\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the DPP within the mesh to get the policies for.\n        - name: kri\n          in: path\n          type: string\n          required: true\n          description: The KRI of the Outbound to get the routes for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-dataplanes-name-outbounds-outbound-k\n      path: /meshes/{mesh}/dataplanes/{name}/_outbounds/{outbound-kri}/_routes/{route-kri}/_policies\n      operations:\n      - name: get-route-policy-conf\n        method: GET\n        description: Get policies for this route\n        inputParameters:\n        - name: mesh\n      \
  \    in: path\n          type: string\n          required: true\n          description: The mesh of the DPP to get the policies for.\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the DPP within the mesh to get the policies for.\n        - name: outbound-kri\n          in: path\n          type: string\n          required: true\n          description: The KRI of the Outbound to get the routes for.\n        - name: route-kri\n          in: path\n          type: string\n          required: true\n          description: The KRI of the Route to get the configuration for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-policytype-policyname-resources-data\n      path: /meshes/{mesh}/{policyType}/{policyName}/_resources/dataplanes\n      operations:\n      - name: inspect-resources\n        method: GET\n       \
  \ description: Returns resources matched by this policy\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: The mesh the policy is part of\n        - name: policyType\n          in: path\n          type: string\n          required: true\n          description: The type of the policy\n        - name: policyName\n          in: path\n          type: string\n          required: true\n          description: The type of the policy\n        - name: size\n          in: query\n          type: integer\n          description: The max number of items to return\n        - name: offset\n          in: query\n          type: integer\n          description: The offset of result\n        - name: name\n          in: query\n          type: string\n          description: A sub string to filter resources by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: meshes-mesh-meshservices-name-dataplanes\n      path: /meshes/{mesh}/meshservices/{name}/_dataplanes\n      operations:\n      - name: inspect-meshservices-dataplanes\n        method: GET\n        description: Returns dataplanes matched by a MeshService\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: The mesh the service is part of\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the service\n        - name: size\n          in: query\n          type: integer\n          description: The max number of items to return\n        - name: offset\n          in: query\n          type: integer\n          description: The offset of result\n        - name: name\n          in: query\n          type: string\n          description: A sub string to filter resources by name\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-servicetype-servicename-hostnames\n      path: /meshes/{mesh}/{serviceType}/{serviceName}/_hostnames\n      operations:\n      - name: inspect-hostnames\n        method: GET\n        description: Returns hostnames for service\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: The mesh the service is part of\n        - name: serviceType\n          in: path\n          type: string\n          required: true\n          description: The type of the service\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: The name of the service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kri-kri\n      path: /_kri/{kri}\n   \
  \   operations:\n      - name: getbykri\n        method: GET\n        description: Returns a resource by KRI\n        inputParameters:\n        - name: kri\n          in: path\n          type: string\n          required: true\n          description: KRI of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshaccesslogs-name\n      path: /meshes/{mesh}/meshaccesslogs/{name}\n      operations:\n      - name: getmeshaccesslog\n        method: GET\n        description: Returns MeshAccessLog entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshAccessLog\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: putmeshaccesslog\n        method: PUT\n        description: Creates or Updates MeshAccessLog entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshAccessLog\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemeshaccesslog\n        method: DELETE\n        description: Deletes MeshAccessLog entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshAccessLog\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshaccesslogs\n      path: /meshes/{mesh}/meshaccesslogs\n      operations:\n      - name: getmeshaccessloglist\n        method: GET\n        description: Returns a list of MeshAccessLog in the mesh.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: offset in the list of entities\n        - name: size\n          in: query\n          type: integer\n          description: the number of items per page\n        - name: filter\n          in: query\n          type: object\n          description: filter by labels when multiple filters are present, they are ANDed\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: meshes-mesh-meshcircuitbreakers-name\n      path: /meshes/{mesh}/meshcircuitbreakers/{name}\n      operations:\n      - name: getmeshcircuitbreaker\n        method: GET\n        description: Returns MeshCircuitBreaker entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshCircuitBreaker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putmeshcircuitbreaker\n        method: PUT\n        description: Creates or Updates MeshCircuitBreaker entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n\
  \        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshCircuitBreaker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemeshcircuitbreaker\n        method: DELETE\n        description: Deletes MeshCircuitBreaker entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshCircuitBreaker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshcircuitbreakers\n      path: /meshes/{mesh}/meshcircuitbreakers\n      operations:\n      - name: getmeshcircuitbreakerlist\n        method: GET\n\
  \        description: Returns a list of MeshCircuitBreaker in the mesh.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: offset in the list of entities\n        - name: size\n          in: query\n          type: integer\n          description: the number of items per page\n        - name: filter\n          in: query\n          type: object\n          description: filter by labels when multiple filters are present, they are ANDed\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshfaultinjections-name\n      path: /meshes/{mesh}/meshfaultinjections/{name}\n      operations:\n      - name: getmeshfaultinjection\n        method: GET\n        description: Returns MeshFaultInjection entity\n\
  \        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshFaultInjection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putmeshfaultinjection\n        method: PUT\n        description: Creates or Updates MeshFaultInjection entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshFaultInjection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: deletemeshfaultinjection\n        method: DELETE\n        description: Deletes MeshFaultInjection entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshFaultInjection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshfaultinjections\n      path: /meshes/{mesh}/meshfaultinjections\n      operations:\n      - name: getmeshfaultinjectionlist\n        method: GET\n        description: Returns a list of MeshFaultInjection in the mesh.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: offset in the list of entities\n        - name: size\n          in: query\n          type:\
  \ integer\n          description: the number of items per page\n        - name: filter\n          in: query\n          type: object\n          description: filter by labels when multiple filters are present, they are ANDed\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshhealthchecks-name\n      path: /meshes/{mesh}/meshhealthchecks/{name}\n      operations:\n      - name: getmeshhealthcheck\n        method: GET\n        description: Returns MeshHealthCheck entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshHealthCheck\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putmeshhealthcheck\n        method: PUT\n        description: Creates or Updates MeshHealthCheck entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshHealthCheck\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemeshhealthcheck\n        method: DELETE\n        description: Deletes MeshHealthCheck entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n       \
  \   type: string\n          required: true\n          description: name of the MeshHealthCheck\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshhealthchecks\n      path: /meshes/{mesh}/meshhealthchecks\n      operations:\n      - name: getmeshhealthchecklist\n        method: GET\n        description: Returns a list of MeshHealthCheck in the mesh.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: offset in the list of entities\n        - name: size\n          in: query\n          type: integer\n          description: the number of items per page\n        - name: filter\n          in: query\n          type: object\n          description: filter by labels when multiple filters are present, they are ANDed\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description:\
  \ name of the mesh\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshhttproutes-name\n      path: /meshes/{mesh}/meshhttproutes/{name}\n      operations:\n      - name: getmeshhttproute\n        method: GET\n        description: Returns MeshHTTPRoute entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshHTTPRoute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putmeshhttproute\n        method: PUT\n        description: Creates or Updates MeshHTTPRoute entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n\
  \          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshHTTPRoute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemeshhttproute\n        method: DELETE\n        description: Deletes MeshHTTPRoute entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshHTTPRoute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshhttproutes\n      path: /meshes/{mesh}/meshhttproutes\n      operations:\n      - name: getmeshhttproutelist\n\
  \        method: GET\n        description: Returns a list of MeshHTTPRoute in the mesh.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: offset in the list of entities\n        - name: size\n          in: query\n          type: integer\n          description: the number of items per page\n        - name: filter\n          in: query\n          type: object\n          description: filter by labels when multiple filters are present, they are ANDed\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshloadbalancingstrategies-name\n      path: /meshes/{mesh}/meshloadbalancingstrategies/{name}\n      operations:\n      - name: getmeshloadbalancingstrategy\n        method: GET\n        description:\
  \ Returns MeshLoadBalancingStrategy entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshLoadBalancingStrategy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putmeshloadbalancingstrategy\n        method: PUT\n        description: Creates or Updates MeshLoadBalancingStrategy entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshLoadBalancingStrategy\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n      - name: deletemeshloadbalancingstrategy\n        method: DELETE\n        description: Deletes MeshLoadBalancingStrategy entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshLoadBalancingStrategy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshloadbalancingstrategies\n      path: /meshes/{mesh}/meshloadbalancingstrategies\n      operations:\n      - name: getmeshloadbalancingstrategylist\n        method: GET\n        description: Returns a list of MeshLoadBalancingStrategy in the mesh.\n        inputParameters:\n        - name: offset\n          in: query\n          type:\
  \ integer\n          description: offset in the list of entities\n        - name: size\n          in: query\n          type: integer\n          description: the number of items per page\n        - name: filter\n          in: query\n          type: object\n          description: filter by labels when multiple filters are present, they are ANDed\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshmetrics-name\n      path: /meshes/{mesh}/meshmetrics/{name}\n      operations:\n      - name: getmeshmetric\n        method: GET\n        description: Returns MeshMetric entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n     \
  \     in: path\n          type: string\n          required: true\n          description: name of the MeshMetric\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putmeshmetric\n        method: PUT\n        description: Creates or Updates MeshMetric entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshMetric\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemeshmetric\n        method: DELETE\n        description: Deletes MeshMetric entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n   \
  \       description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshMetric\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshmetrics\n      path: /meshes/{mesh}/meshmetrics\n      operations:\n      - name: getmeshmetriclist\n        method: GET\n        description: Returns a list of MeshMetric in the mesh.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: offset in the list of entities\n        - name: size\n          in: query\n          type: integer\n          description: the number of items per page\n        - name: filter\n          in: query\n          type: object\n          description: filter by labels when multiple filters are present, they are ANDed\n        - name: mesh\n          in: path\n      \
  \    type: string\n          required: true\n          description: name of the mesh\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshpassthroughs-name\n      path: /meshes/{mesh}/meshpassthroughs/{name}\n      operations:\n      - name: getmeshpassthrough\n        method: GET\n        description: Returns MeshPassthrough entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshPassthrough\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putmeshpassthrough\n        method: PUT\n        description: Creates or Updates MeshPassthrough entity\n        inputParameters:\n\
  \        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshPassthrough\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemeshpassthrough\n        method: DELETE\n        description: Deletes MeshPassthrough entity\n        inputParameters:\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name of the MeshPassthrough\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meshes-mesh-meshpassthroughs\n      path:\
  \ /meshes/{mesh}/meshpassthroughs\n      operations:\n      - name: getmeshpassthroughlist\n        method: GET\n        description: Returns a list of MeshPassthrough in the mesh.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: offset in the list of entities\n        - name: size\n          in: query\n          type: integer\n          description: the number of items per page\n        - name: filter\n          in: query\n          type: object\n          description: filter by labels when multiple filters are present, they are ANDed\n        - name: mesh\n          in: path\n          type: string\n          required: true\n          description: name of the mesh\n        outputRawFormat: json\n        outputParameters:\n        - nam\n\n# --- truncated at 32 KB (101 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/kuma/refs/heads/main/capabilities/kuma-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/kuma/refs/heads/main/capabilities/kuma-capability.yaml
tags:
- Kuma
- API
tools:
- description: The index endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: index
- description: A list of all resources that exist
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-resource-type-description
- description: Get Global Insight
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-global-insight
- description: Returns rules matching this dataplane
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: inspect-dataplanes-rules
- description: Get a proxy XDS config on a CP, this endpoint is only available on zone CPs.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dataplanes-xds-config
- description: Get networking layout for this dataplane
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dataplanes-layout
- description: Get proxy policies for this dataplane
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-proxy-policy-conf
- description: Get policies for this inbound
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-inbound-policy-conf
- description: Get policies for this outbound
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-outbound-policy-conf
- description: Get routes configuration for this outbound
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-outbound-routes
- description: Get policies for this route
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-route-policy-conf
- description: Returns resources matched by this policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: inspect-resources
- description: Returns dataplanes matched by a MeshService
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: inspect-meshservices-dataplanes
- description: Returns hostnames for service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: inspect-hostnames
- description: Returns a resource by KRI
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbykri
- description: Returns MeshAccessLog entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshaccesslog
- description: Creates or Updates MeshAccessLog entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmeshaccesslog
- description: Deletes MeshAccessLog entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemeshaccesslog
- description: Returns a list of MeshAccessLog in the mesh.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshaccessloglist
- description: Returns MeshCircuitBreaker entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshcircuitbreaker
- description: Creates or Updates MeshCircuitBreaker entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmeshcircuitbreaker
- description: Deletes MeshCircuitBreaker entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemeshcircuitbreaker
- description: Returns a list of MeshCircuitBreaker in the mesh.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshcircuitbreakerlist
- description: Returns MeshFaultInjection entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshfaultinjection
- description: Creates or Updates MeshFaultInjection entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmeshfaultinjection
- description: Deletes MeshFaultInjection entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemeshfaultinjection
- description: Returns a list of MeshFaultInjection in the mesh.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshfaultinjectionlist
- description: Returns MeshHealthCheck entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshhealthcheck
- description: Creates or Updates MeshHealthCheck entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmeshhealthcheck
- description: Deletes MeshHealthCheck entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemeshhealthcheck
- description: Returns a list of MeshHealthCheck in the mesh.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshhealthchecklist
- description: Returns MeshHTTPRoute entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshhttproute
- description: Creates or Updates MeshHTTPRoute entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmeshhttproute
- description: Deletes MeshHTTPRoute entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemeshhttproute
- description: Returns a list of MeshHTTPRoute in the mesh.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshhttproutelist
- description: Returns MeshLoadBalancingStrategy entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshloadbalancingstrategy
- description: Creates or Updates MeshLoadBalancingStrategy entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmeshloadbalancingstrategy
- description: Deletes MeshLoadBalancingStrategy entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemeshloadbalancingstrategy
- description: Returns a list of MeshLoadBalancingStrategy in the mesh.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshloadbalancingstrategylist
- description: Returns MeshMetric entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshmetric
- description: Creates or Updates MeshMetric entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmeshmetric
- description: Deletes MeshMetric entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemeshmetric
- description: Returns a list of MeshMetric in the mesh.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshmetriclist
- description: Returns MeshPassthrough entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshpassthrough
- description: Creates or Updates MeshPassthrough entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmeshpassthrough
- description: Deletes MeshPassthrough entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemeshpassthrough
- description: Returns a list of MeshPassthrough in the mesh.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshpassthroughlist
- description: Returns MeshProxyPatch entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshproxypatch
- description: Creates or Updates MeshProxyPatch entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmeshproxypatch
- description: Deletes MeshProxyPatch entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemeshproxypatch
- description: Returns a list of MeshProxyPatch in the mesh.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshproxypatchlist
- description: Returns MeshRateLimit entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshratelimit
- description: Creates or Updates MeshRateLimit entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmeshratelimit
- description: Deletes MeshRateLimit entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemeshratelimit
- description: Returns a list of MeshRateLimit in the mesh.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshratelimitlist
- description: Returns MeshRetry entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshretry
- description: Creates or Updates MeshRetry entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putmeshretry
- description: Deletes MeshRetry entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemeshretry
- description: Returns a list of MeshRetry in the mesh.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshretrylist
- description: Returns MeshTCPRoute entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeshtcproute
---
