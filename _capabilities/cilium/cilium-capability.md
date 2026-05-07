---
categories: []
consumed_apis: []
description: The Cilium REST API provides access to the Cilium daemon and agent endpoints for managing Kubernetes network policy, security, and connectivity. The API is served by the cilium-agent process over a local Unix domain socket and HTTP interface. It covers endpoint management, identity management, policy configuration, IP address management, service configuration, BGP operations, and daemon health status.
layout: capability
name: Cilium API
operations:
- description: Cilium Get daemon health status
  method: GET
  name: getdaemonhealth
  path: /healthz
- description: Cilium Get daemon configuration
  method: GET
  name: getdaemonconfig
  path: /config
- description: Cilium Modify daemon configuration
  method: PATCH
  name: patchdaemonconfig
  path: /config
- description: Cilium List cluster nodes
  method: GET
  name: getclusternodes
  path: /cluster/nodes
- description: Cilium Get debugging information
  method: GET
  name: getdebuginfo
  path: /debuginfo
- description: Cilium List BPF maps
  method: GET
  name: getbpfmaps
  path: /map
- description: Cilium Get node IDs
  method: GET
  name: getnodeids
  path: /node/ids
- description: Cilium List endpoints
  method: GET
  name: listendpoints
  path: /endpoint
- description: Cilium Delete endpoints by label selector
  method: DELETE
  name: deleteendpoints
  path: /endpoint
- description: Cilium Get endpoint by ID
  method: GET
  name: getendpoint
  path: /endpoint/{id}
- description: Cilium Create or replace endpoint
  method: PUT
  name: putendpoint
  path: /endpoint/{id}
- description: Cilium Modify endpoint
  method: PATCH
  name: patchendpoint
  path: /endpoint/{id}
- description: Cilium Delete endpoint
  method: DELETE
  name: deleteendpoint
  path: /endpoint/{id}
- description: Cilium Get endpoint configuration
  method: GET
  name: getendpointconfig
  path: /endpoint/{id}/config
- description: Cilium Modify endpoint configuration
  method: PATCH
  name: patchendpointconfig
  path: /endpoint/{id}/config
- description: Cilium Get endpoint labels
  method: GET
  name: getendpointlabels
  path: /endpoint/{id}/labels
- description: Cilium Modify endpoint labels
  method: PATCH
  name: patchendpointlabels
  path: /endpoint/{id}/labels
- description: Cilium Get endpoint status log
  method: GET
  name: getendpointlog
  path: /endpoint/{id}/log
- description: Cilium Get endpoint health
  method: GET
  name: getendpointhealth
  path: /endpoint/{id}/healthz
- description: Cilium List security identities
  method: GET
  name: listidentities
  path: /identity
- description: Cilium Get identity by ID
  method: GET
  name: getidentity
  path: /identity/{id}
- description: Cilium List local endpoint identities
  method: GET
  name: getlocalendpointidentities
  path: /identity/endpoints
- description: Cilium Get policy selectors
  method: GET
  name: getpolicyselectors
  path: /policy/selectors
- description: Cilium Get FQDN DNS cache
  method: GET
  name: getfqdncache
  path: /fqdn/cache
- description: Cilium Clear FQDN DNS cache
  method: DELETE
  name: deletefqdncache
  path: /fqdn/cache
- description: Cilium Get FQDN selector names
  method: GET
  name: getfqdnnames
  path: /fqdn/names
- description: Cilium Allocate IP address
  method: POST
  name: allocateipaddress
  path: /ipam
- description: Cilium Allocate specific IP address
  method: POST
  name: allocatespecificipaddress
  path: /ipam/{ip}
- description: Cilium Release IP address
  method: DELETE
  name: releaseipaddress
  path: /ipam/{ip}
- description: Cilium List IP addresses
  method: GET
  name: listipaddresses
  path: /ip
- description: Cilium List services
  method: GET
  name: listservices
  path: /service
- description: Cilium Get service by ID
  method: GET
  name: getservice
  path: /service/{id}
- description: Cilium Create or update service
  method: PUT
  name: putservice
  path: /service/{id}
- description: Cilium Delete service
  method: DELETE
  name: deleteservice
  path: /service/{id}
- description: Cilium List local redirect policies
  method: GET
  name: listlocalredirectpolicies
  path: /lrp
- description: Cilium Get prefilter configuration
  method: GET
  name: getprefilterconfig
  path: /prefilter
- description: Cilium Update prefilter configuration
  method: PATCH
  name: patchprefilterconfig
  path: /prefilter
- description: Cilium Delete prefilter entries
  method: DELETE
  name: deleteprefilterconfig
  path: /prefilter
- description: Cilium List BGP peers
  method: GET
  name: getbgppeers
  path: /bgp/peers
- description: Cilium List BGP routes
  method: GET
  name: getbgproutes
  path: /bgp/routes
- description: Cilium List BGP route policies
  method: GET
  name: getbgproutepolicies
  path: /bgp/route-policies
personas: []
provider_name: Cilium
provider_slug: cilium
search_terms:
- putendpoint
- cilium delete endpoint
- cilium clear fqdn dns cache
- getdaemonconfig
- getbgproutepolicies
- api
- cilium list security identities
- cilium list bgp peers
- deleteendpoint
- releaseipaddress
- cilium
- cilium get endpoint status log
- allocatespecificipaddress
- patchendpointlabels
- getendpointconfig
- getpolicyselectors
- deletefqdncache
- cilium create or replace endpoint
- cilium get endpoint configuration
- cilium get debugging information
- patchendpoint
- getbpfmaps
- deleteservice
- cilium get daemon configuration
- listservices
- cilium get fqdn selector names
- getlocalendpointidentities
- ebpf
- cilium create or update service
- getprefilterconfig
- getendpointhealth
- cilium modify daemon configuration
- listlocalredirectpolicies
- cilium delete prefilter entries
- cloud native
- cilium modify endpoint labels
- cilium delete endpoints by label selector
- cilium list bpf maps
- cilium modify endpoint configuration
- cilium update prefilter configuration
- cilium get policy selectors
- cilium release ip address
- getendpointlog
- getfqdnnames
- security
- cilium delete service
- patchendpointconfig
- cilium list bgp route policies
- getclusternodes
- networking
- putservice
- listipaddresses
- cilium list bgp routes
- cilium get endpoint by id
- listendpoints
- getidentity
- cilium get service by id
- cilium get identity by id
- kubernetes
- listidentities
- cilium list cluster nodes
- cilium get endpoint health
- cilium get fqdn dns cache
- cilium list local redirect policies
- deleteprefilterconfig
- getbgppeers
- getfqdncache
- cilium allocate ip address
- cilium get endpoint labels
- cilium list ip addresses
- getendpointlabels
- cilium modify endpoint
- getservice
- getdaemonhealth
- cilium list services
- getnodeids
- deleteendpoints
- getbgproutes
- getendpoint
- patchprefilterconfig
- cilium get daemon health status
- getdebuginfo
- cilium get node ids
- allocateipaddress
- cilium get prefilter configuration
- cilium list local endpoint identities
- cilium list endpoints
- patchdaemonconfig
- cilium allocate specific ip address
slug: cilium-capability
source_filename: cilium-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Cilium API\n  description: The Cilium REST API provides access to the Cilium daemon and agent endpoints for managing Kubernetes network\n    policy, security, and connectivity. The API is served by the cilium-agent process over a local Unix domain socket and\n    HTTP interface. It covers endpoint management, identity management, policy configuration, IP address management, service\n    configuration, BGP operations, and daemon health status.\n  tags:\n  - Cilium\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: cilium\n    baseUri: http://localhost/v1\n    description: Cilium API HTTP API.\n    resources:\n    - name: healthz\n      path: /healthz\n      operations:\n      - name: getdaemonhealth\n        method: GET\n        description: Cilium Get daemon health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: config\n      path: /config\n      operations:\n      - name: getdaemonconfig\n        method: GET\n        description: Cilium Get daemon configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchdaemonconfig\n        method: PATCH\n        description: Cilium Modify daemon configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster-nodes\n      path: /cluster/nodes\n      operations:\n      - name: getclusternodes\n        method: GET\n        description: Cilium List cluster nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: debuginfo\n      path: /debuginfo\n      operations:\n      - name: getdebuginfo\n        method: GET\n        description:\
  \ Cilium Get debugging information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: map\n      path: /map\n      operations:\n      - name: getbpfmaps\n        method: GET\n        description: Cilium List BPF maps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: node-ids\n      path: /node/ids\n      operations:\n      - name: getnodeids\n        method: GET\n        description: Cilium Get node IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint\n      path: /endpoint\n      operations:\n      - name: listendpoints\n        method: GET\n        description: Cilium List endpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: deleteendpoints\n        method: DELETE\n        description: Cilium Delete endpoints by label selector\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-id\n      path: /endpoint/{id}\n      operations:\n      - name: getendpoint\n        method: GET\n        description: Cilium Get endpoint by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putendpoint\n        method: PUT\n        description: Cilium Create or replace endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchendpoint\n        method: PATCH\n        description: Cilium Modify endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \    - name: deleteendpoint\n        method: DELETE\n        description: Cilium Delete endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-id-config\n      path: /endpoint/{id}/config\n      operations:\n      - name: getendpointconfig\n        method: GET\n        description: Cilium Get endpoint configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchendpointconfig\n        method: PATCH\n        description: Cilium Modify endpoint configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-id-labels\n      path: /endpoint/{id}/labels\n      operations:\n      - name: getendpointlabels\n        method: GET\n        description: Cilium Get endpoint labels\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchendpointlabels\n        method: PATCH\n        description: Cilium Modify endpoint labels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-id-log\n      path: /endpoint/{id}/log\n      operations:\n      - name: getendpointlog\n        method: GET\n        description: Cilium Get endpoint status log\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-id-healthz\n      path: /endpoint/{id}/healthz\n      operations:\n      - name: getendpointhealth\n        method: GET\n        description: Cilium Get endpoint health\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity\n      path:\
  \ /identity\n      operations:\n      - name: listidentities\n        method: GET\n        description: Cilium List security identities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-id\n      path: /identity/{id}\n      operations:\n      - name: getidentity\n        method: GET\n        description: Cilium Get identity by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-endpoints\n      path: /identity/endpoints\n      operations:\n      - name: getlocalendpointidentities\n        method: GET\n        description: Cilium List local endpoint identities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policy-selectors\n      path: /policy/selectors\n      operations:\n      - name: getpolicyselectors\n\
  \        method: GET\n        description: Cilium Get policy selectors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fqdn-cache\n      path: /fqdn/cache\n      operations:\n      - name: getfqdncache\n        method: GET\n        description: Cilium Get FQDN DNS cache\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefqdncache\n        method: DELETE\n        description: Cilium Clear FQDN DNS cache\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fqdn-names\n      path: /fqdn/names\n      operations:\n      - name: getfqdnnames\n        method: GET\n        description: Cilium Get FQDN selector names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: ipam\n      path: /ipam\n      operations:\n      - name: allocateipaddress\n        method: POST\n        description: Cilium Allocate IP address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ipam-ip\n      path: /ipam/{ip}\n      operations:\n      - name: allocatespecificipaddress\n        method: POST\n        description: Cilium Allocate specific IP address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: releaseipaddress\n        method: DELETE\n        description: Cilium Release IP address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ip\n      path: /ip\n      operations:\n      - name: listipaddresses\n        method: GET\n        description: Cilium List IP addresses\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service\n      path: /service\n      operations:\n      - name: listservices\n        method: GET\n        description: Cilium List services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-id\n      path: /service/{id}\n      operations:\n      - name: getservice\n        method: GET\n        description: Cilium Get service by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putservice\n        method: PUT\n        description: Cilium Create or update service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteservice\n        method: DELETE\n        description:\
  \ Cilium Delete service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lrp\n      path: /lrp\n      operations:\n      - name: listlocalredirectpolicies\n        method: GET\n        description: Cilium List local redirect policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prefilter\n      path: /prefilter\n      operations:\n      - name: getprefilterconfig\n        method: GET\n        description: Cilium Get prefilter configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchprefilterconfig\n        method: PATCH\n        description: Cilium Update prefilter configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: deleteprefilterconfig\n        method: DELETE\n        description: Cilium Delete prefilter entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bgp-peers\n      path: /bgp/peers\n      operations:\n      - name: getbgppeers\n        method: GET\n        description: Cilium List BGP peers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bgp-routes\n      path: /bgp/routes\n      operations:\n      - name: getbgproutes\n        method: GET\n        description: Cilium List BGP routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bgp-route-policies\n      path: /bgp/route-policies\n      operations:\n      - name: getbgproutepolicies\n        method: GET\n        description: Cilium List BGP route\
  \ policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cilium-rest\n    description: REST adapter for Cilium API.\n    resources:\n    - path: /healthz\n      name: getdaemonhealth\n      operations:\n      - method: GET\n        name: getdaemonhealth\n        description: Cilium Get daemon health status\n        call: cilium.getdaemonhealth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /config\n      name: getdaemonconfig\n      operations:\n      - method: GET\n        name: getdaemonconfig\n        description: Cilium Get daemon configuration\n        call: cilium.getdaemonconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /config\n      name: patchdaemonconfig\n      operations:\n      - method: PATCH\n        name: patchdaemonconfig\n        description: Cilium\
  \ Modify daemon configuration\n        call: cilium.patchdaemonconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cluster/nodes\n      name: getclusternodes\n      operations:\n      - method: GET\n        name: getclusternodes\n        description: Cilium List cluster nodes\n        call: cilium.getclusternodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /debuginfo\n      name: getdebuginfo\n      operations:\n      - method: GET\n        name: getdebuginfo\n        description: Cilium Get debugging information\n        call: cilium.getdebuginfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /map\n      name: getbpfmaps\n      operations:\n      - method: GET\n        name: getbpfmaps\n        description: Cilium List BPF maps\n        call: cilium.getbpfmaps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /node/ids\n   \
  \   name: getnodeids\n      operations:\n      - method: GET\n        name: getnodeids\n        description: Cilium Get node IDs\n        call: cilium.getnodeids\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoint\n      name: listendpoints\n      operations:\n      - method: GET\n        name: listendpoints\n        description: Cilium List endpoints\n        call: cilium.listendpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoint\n      name: deleteendpoints\n      operations:\n      - method: DELETE\n        name: deleteendpoints\n        description: Cilium Delete endpoints by label selector\n        call: cilium.deleteendpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoint/{id}\n      name: getendpoint\n      operations:\n      - method: GET\n        name: getendpoint\n        description: Cilium Get endpoint by ID\n        call: cilium.getendpoint\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoint/{id}\n      name: putendpoint\n      operations:\n      - method: PUT\n        name: putendpoint\n        description: Cilium Create or replace endpoint\n        call: cilium.putendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoint/{id}\n      name: patchendpoint\n      operations:\n      - method: PATCH\n        name: patchendpoint\n        description: Cilium Modify endpoint\n        call: cilium.patchendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoint/{id}\n      name: deleteendpoint\n      operations:\n      - method: DELETE\n        name: deleteendpoint\n        description: Cilium Delete endpoint\n        call: cilium.deleteendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoint/{id}/config\n      name: getendpointconfig\n      operations:\n\
  \      - method: GET\n        name: getendpointconfig\n        description: Cilium Get endpoint configuration\n        call: cilium.getendpointconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoint/{id}/config\n      name: patchendpointconfig\n      operations:\n      - method: PATCH\n        name: patchendpointconfig\n        description: Cilium Modify endpoint configuration\n        call: cilium.patchendpointconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoint/{id}/labels\n      name: getendpointlabels\n      operations:\n      - method: GET\n        name: getendpointlabels\n        description: Cilium Get endpoint labels\n        call: cilium.getendpointlabels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoint/{id}/labels\n      name: patchendpointlabels\n      operations:\n      - method: PATCH\n        name: patchendpointlabels\n       \
  \ description: Cilium Modify endpoint labels\n        call: cilium.patchendpointlabels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoint/{id}/log\n      name: getendpointlog\n      operations:\n      - method: GET\n        name: getendpointlog\n        description: Cilium Get endpoint status log\n        call: cilium.getendpointlog\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoint/{id}/healthz\n      name: getendpointhealth\n      operations:\n      - method: GET\n        name: getendpointhealth\n        description: Cilium Get endpoint health\n        call: cilium.getendpointhealth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /identity\n      name: listidentities\n      operations:\n      - method: GET\n        name: listidentities\n        description: Cilium List security identities\n        call: cilium.listidentities\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /identity/{id}\n      name: getidentity\n      operations:\n      - method: GET\n        name: getidentity\n        description: Cilium Get identity by ID\n        call: cilium.getidentity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /identity/endpoints\n      name: getlocalendpointidentities\n      operations:\n      - method: GET\n        name: getlocalendpointidentities\n        description: Cilium List local endpoint identities\n        call: cilium.getlocalendpointidentities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policy/selectors\n      name: getpolicyselectors\n      operations:\n      - method: GET\n        name: getpolicyselectors\n        description: Cilium Get policy selectors\n        call: cilium.getpolicyselectors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fqdn/cache\n      name:\
  \ getfqdncache\n      operations:\n      - method: GET\n        name: getfqdncache\n        description: Cilium Get FQDN DNS cache\n        call: cilium.getfqdncache\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fqdn/cache\n      name: deletefqdncache\n      operations:\n      - method: DELETE\n        name: deletefqdncache\n        description: Cilium Clear FQDN DNS cache\n        call: cilium.deletefqdncache\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fqdn/names\n      name: getfqdnnames\n      operations:\n      - method: GET\n        name: getfqdnnames\n        description: Cilium Get FQDN selector names\n        call: cilium.getfqdnnames\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ipam\n      name: allocateipaddress\n      operations:\n      - method: POST\n        name: allocateipaddress\n        description: Cilium Allocate IP address\n        call: cilium.allocateipaddress\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ipam/{ip}\n      name: allocatespecificipaddress\n      operations:\n      - method: POST\n        name: allocatespecificipaddress\n        description: Cilium Allocate specific IP address\n        call: cilium.allocatespecificipaddress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ipam/{ip}\n      name: releaseipaddress\n      operations:\n      - method: DELETE\n        name: releaseipaddress\n        description: Cilium Release IP address\n        call: cilium.releaseipaddress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ip\n      name: listipaddresses\n      operations:\n      - method: GET\n        name: listipaddresses\n        description: Cilium List IP addresses\n        call: cilium.listipaddresses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /service\n      name:\
  \ listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: Cilium List services\n        call: cilium.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /service/{id}\n      name: getservice\n      operations:\n      - method: GET\n        name: getservice\n        description: Cilium Get service by ID\n        call: cilium.getservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /service/{id}\n      name: putservice\n      operations:\n      - method: PUT\n        name: putservice\n        description: Cilium Create or update service\n        call: cilium.putservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /service/{id}\n      name: deleteservice\n      operations:\n      - method: DELETE\n        name: deleteservice\n        description: Cilium Delete service\n        call: cilium.deleteservice\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /lrp\n      name: listlocalredirectpolicies\n      operations:\n      - method: GET\n        name: listlocalredirectpolicies\n        description: Cilium List local redirect policies\n        call: cilium.listlocalredirectpolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /prefilter\n      name: getprefilterconfig\n      operations:\n      - method: GET\n        name: getprefilterconfig\n        description: Cilium Get prefilter configuration\n        call: cilium.getprefilterconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /prefilter\n      name: patchprefilterconfig\n      operations:\n      - method: PATCH\n        name: patchprefilterconfig\n        description: Cilium Update prefilter configuration\n        call: cilium.patchprefilterconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /prefilter\n\
  \      name: deleteprefilterconfig\n      operations:\n      - method: DELETE\n        name: deleteprefilterconfig\n        description: Cilium Delete prefilter entries\n        call: cilium.deleteprefilterconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bgp/peers\n      name: getbgppeers\n      operations:\n      - method: GET\n        name: getbgppeers\n        description: Cilium List BGP peers\n        call: cilium.getbgppeers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bgp/routes\n      name: getbgproutes\n      operations:\n      - method: GET\n        name: getbgproutes\n        description: Cilium List BGP routes\n        call: cilium.getbgproutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bgp/route-policies\n      name: getbgproutepolicies\n      operations:\n      - method: GET\n        name: getbgproutepolicies\n        description: Cilium List\
  \ BGP route policies\n        call: cilium.getbgproutepolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cilium-mcp\n    transport: http\n    description: MCP adapter for Cilium API for AI agent use.\n    tools:\n    - name: getdaemonhealth\n      description: Cilium Get daemon health status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getdaemonhealth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdaemonconfig\n      description: Cilium Get daemon configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getdaemonconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchdaemonconfig\n      description: Cilium Modify daemon configuration\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: cilium.patchdaemonconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclusternodes\n      description: Cilium List cluster nodes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getclusternodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdebuginfo\n      description: Cilium Get debugging information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getdebuginfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbpfmaps\n      description: Cilium List BPF maps\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getbpfmaps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnodeids\n      description: Cilium Get node IDs\n  \
  \    hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getnodeids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listendpoints\n      description: Cilium List endpoints\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.listendpoints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteendpoints\n      description: Cilium Delete endpoints by label selector\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: cilium.deleteendpoints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getendpoint\n      description: Cilium Get endpoint by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getendpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: putendpoint\n      description: Cilium Create or replace endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: cilium.putendpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchendpoint\n      description: Cilium Modify endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cilium.patchendpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteendpoint\n      description: Cilium Delete endpoint\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: cilium.deleteendpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getendpointconfig\n      description: Cilium Get endpoint configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getendpointconfig\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchendpointconfig\n      description: Cilium Modify endpoint configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cilium.patchendpointconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getendpointlabels\n      description: Cilium Get endpoint labels\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getendpointlabels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchendpointlabels\n      description: Cilium Modify endpoint labels\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cilium.patchendpointlabels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getendpointlog\n      description: Cilium Get endpoint status log\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getendpointlog\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getendpointhealth\n      description: Cilium Get endpoint health\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getendpointhealth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listidentities\n      description: Cilium List security identities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.listidentities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getidentity\n      description: Cilium Get identity by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getidentity\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getlocalendpointidentities\n      description: Cilium List local endpoint identities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getlocalendpointidentities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpolicyselectors\n      description: Cilium Get policy selectors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getpolicyselectors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfqdncache\n      description: Cilium Get FQDN DNS cache\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getfqdncache\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletefqdncache\n      description: Cilium Clear FQDN DNS cache\n      hints:\n        readOnly: false\n        destructive: true\n \
  \       idempotent: true\n      call: cilium.deletefqdncache\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfqdnnames\n      description: Cilium Get FQDN selector names\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getfqdnnames\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: allocateipaddress\n      description: Cilium Allocate IP address\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cilium.allocateipaddress\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: allocatespecificipaddress\n      description: Cilium Allocate specific IP address\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cilium.allocatespecificipaddress\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: releaseipaddress\n\
  \      description: Cilium Release IP address\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: cilium.releaseipaddress\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listipaddresses\n      description: Cilium List IP addresses\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.listipaddresses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservices\n      description: Cilium List services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.listservices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservice\n      description: Cilium Get service by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.getservice\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: putservice\n      description: Cilium Create or update service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: cilium.putservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteservice\n      description: Cilium Delete service\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: cilium.deleteservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlocalredirectpolicies\n      description: Cilium List local redirect policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cilium.listlocalredirectpolicies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprefilt\n\n# --- truncated at 32 KB (33 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/cilium/refs/heads/main/capabilities/cilium-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cilium/refs/heads/main/capabilities/cilium-capability.yaml
tags:
- Cilium
- API
tools:
- description: Cilium Get daemon health status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdaemonhealth
- description: Cilium Get daemon configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdaemonconfig
- description: Cilium Modify daemon configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchdaemonconfig
- description: Cilium List cluster nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclusternodes
- description: Cilium Get debugging information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdebuginfo
- description: Cilium List BPF maps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbpfmaps
- description: Cilium Get node IDs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnodeids
- description: Cilium List endpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listendpoints
- description: Cilium Delete endpoints by label selector
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteendpoints
- description: Cilium Get endpoint by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getendpoint
- description: Cilium Create or replace endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putendpoint
- description: Cilium Modify endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchendpoint
- description: Cilium Delete endpoint
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteendpoint
- description: Cilium Get endpoint configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getendpointconfig
- description: Cilium Modify endpoint configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchendpointconfig
- description: Cilium Get endpoint labels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getendpointlabels
- description: Cilium Modify endpoint labels
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchendpointlabels
- description: Cilium Get endpoint status log
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getendpointlog
- description: Cilium Get endpoint health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getendpointhealth
- description: Cilium List security identities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listidentities
- description: Cilium Get identity by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentity
- description: Cilium List local endpoint identities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocalendpointidentities
- description: Cilium Get policy selectors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpolicyselectors
- description: Cilium Get FQDN DNS cache
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfqdncache
- description: Cilium Clear FQDN DNS cache
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefqdncache
- description: Cilium Get FQDN selector names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfqdnnames
- description: Cilium Allocate IP address
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: allocateipaddress
- description: Cilium Allocate specific IP address
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: allocatespecificipaddress
- description: Cilium Release IP address
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: releaseipaddress
- description: Cilium List IP addresses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listipaddresses
- description: Cilium List services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Cilium Get service by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: Cilium Create or update service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putservice
- description: Cilium Delete service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteservice
- description: Cilium List local redirect policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocalredirectpolicies
- description: Cilium Get prefilter configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprefilterconfig
- description: Cilium Update prefilter configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchprefilterconfig
- description: Cilium Delete prefilter entries
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprefilterconfig
- description: Cilium List BGP peers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbgppeers
- description: Cilium List BGP routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbgproutes
- description: Cilium List BGP route policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbgproutepolicies
---
