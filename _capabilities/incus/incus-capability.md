---
categories: []
consumed_apis: []
description: This is the REST API used by all Incus clients. Internal endpoints aren't included in this documentation. The Incus API is available over both a local unix+http and remote https API. Authentication for local users relies on group membership and access to the unix socket. For remote users, the default authentication method is TLS client certificates.
layout: capability
name: Incus external REST API
operations:
- description: Get the supported API endpoints
  method: GET
  name: api-get
  path: /
- description: Get the server environment and configuration
  method: GET
  name: server-get
  path: /1.0
- description: Partially update the server configuration
  method: PATCH
  name: server-patch
  path: /1.0
- description: Update the server configuration
  method: PUT
  name: server-put
  path: /1.0
- description: Get the trusted certificates
  method: GET
  name: certificates-get
  path: /1.0/certificates
- description: Add a trusted certificate
  method: POST
  name: certificates-post
  path: /1.0/certificates
- description: Delete the trusted certificate
  method: DELETE
  name: certificate-delete
  path: /1.0/certificates/{fingerprint}
- description: Get the trusted certificate
  method: GET
  name: certificate-get
  path: /1.0/certificates/{fingerprint}
- description: Partially update the trusted certificate
  method: PATCH
  name: certificate-patch
  path: /1.0/certificates/{fingerprint}
- description: Update the trusted certificate
  method: PUT
  name: certificate-put
  path: /1.0/certificates/{fingerprint}
- description: Add a trusted certificate
  method: POST
  name: certificates-post-untrusted
  path: /1.0/certificates?public
- description: Get the trusted certificates
  method: GET
  name: certificates-get-recursion1
  path: /1.0/certificates?recursion=1
- description: Get the cluster configuration
  method: GET
  name: cluster-get
  path: /1.0/cluster
- description: Update the cluster configuration
  method: PUT
  name: cluster-put
  path: /1.0/cluster
- description: Update the certificate for the cluster
  method: PUT
  name: clustering-update-cert
  path: /1.0/cluster/certificate
- description: Get the cluster groups
  method: GET
  name: cluster-groups-get
  path: /1.0/cluster/groups
- description: Create a cluster group.
  method: POST
  name: cluster-groups-post
  path: /1.0/cluster/groups
- description: Delete the cluster group.
  method: DELETE
  name: cluster-group-delete
  path: /1.0/cluster/groups/{name}
- description: Get the cluster group
  method: GET
  name: cluster-group-get
  path: /1.0/cluster/groups/{name}
- description: Update the cluster group
  method: PATCH
  name: cluster-group-patch
  path: /1.0/cluster/groups/{name}
- description: Rename the cluster group
  method: POST
  name: cluster-group-post
  path: /1.0/cluster/groups/{name}
- description: Update the cluster group
  method: PUT
  name: cluster-group-put
  path: /1.0/cluster/groups/{name}
- description: Get the cluster groups
  method: GET
  name: cluster-groups-get-recursion1
  path: /1.0/cluster/groups?recursion=1
- description: Get the cluster members
  method: GET
  name: cluster-members-get
  path: /1.0/cluster/members
- description: Request a join token
  method: POST
  name: cluster-members-post
  path: /1.0/cluster/members
- description: Delete the cluster member
  method: DELETE
  name: cluster-member-delete
  path: /1.0/cluster/members/{name}
- description: Get the cluster member
  method: GET
  name: cluster-member-get
  path: /1.0/cluster/members/{name}
- description: Partially update the cluster member
  method: PATCH
  name: cluster-member-patch
  path: /1.0/cluster/members/{name}
- description: Rename the cluster member
  method: POST
  name: cluster-member-post
  path: /1.0/cluster/members/{name}
- description: Update the cluster member
  method: PUT
  name: cluster-member-put
  path: /1.0/cluster/members/{name}
- description: Get state of the cluster member
  method: GET
  name: cluster-member-state-get
  path: /1.0/cluster/members/{name}/state
- description: Evacuate or restore a cluster member
  method: POST
  name: cluster-member-state-post
  path: /1.0/cluster/members/{name}/state
- description: Get the cluster members
  method: GET
  name: cluster-members-get-recursion1
  path: /1.0/cluster/members?recursion=1
- description: Get the event stream
  method: GET
  name: events-get
  path: /1.0/events
- description: Get the images
  method: GET
  name: images-get
  path: /1.0/images
- description: Add an image
  method: POST
  name: images-post
  path: /1.0/images
- description: Delete the image
  method: DELETE
  name: image-delete
  path: /1.0/images/{fingerprint}
- description: Get the image
  method: GET
  name: image-get
  path: /1.0/images/{fingerprint}
- description: Partially update the image
  method: PATCH
  name: image-patch
  path: /1.0/images/{fingerprint}
- description: Update the image
  method: PUT
  name: image-put
  path: /1.0/images/{fingerprint}
- description: Get the raw image file(s)
  method: GET
  name: image-export-get
  path: /1.0/images/{fingerprint}/export
- description: Make the server push the image to a remote server
  method: POST
  name: images-export-post
  path: /1.0/images/{fingerprint}/export
- description: Get the raw image file(s)
  method: GET
  name: image-export-get-untrusted
  path: /1.0/images/{fingerprint}/export?public
- description: Refresh an image
  method: POST
  name: images-refresh-post
  path: /1.0/images/{fingerprint}/refresh
- description: Generate secret for retrieval of the image by an untrusted client
  method: POST
  name: images-secret-post
  path: /1.0/images/{fingerprint}/secret
- description: Get the public image
  method: GET
  name: image-get-untrusted
  path: /1.0/images/{fingerprint}?public
- description: Get the image aliases
  method: GET
  name: images-aliases-get
  path: /1.0/images/aliases
- description: Add an image alias
  method: POST
  name: images-aliases-post
  path: /1.0/images/aliases
- description: Delete the image alias
  method: DELETE
  name: image-alias-delete
  path: /1.0/images/aliases/{name}
- description: Get the image alias
  method: GET
  name: image-alias-get
  path: /1.0/images/aliases/{name}
- description: Partially update the image alias
  method: PATCH
  name: images-alias-patch
  path: /1.0/images/aliases/{name}
- description: Rename the image alias
  method: POST
  name: images-alias-post
  path: /1.0/images/aliases/{name}
- description: Update the image alias
  method: PUT
  name: images-aliases-put
  path: /1.0/images/aliases/{name}
- description: Get the public image alias
  method: GET
  name: image-alias-get-untrusted
  path: /1.0/images/aliases/{name}?public
- description: Get the image aliases
  method: GET
  name: images-aliases-get-recursion1
  path: /1.0/images/aliases?recursion=1
- description: Get the public images
  method: GET
  name: images-get-untrusted
  path: /1.0/images?public
- description: Add an image
  method: POST
  name: images-post-untrusted
  path: /1.0/images?public
- description: Get the public images
  method: GET
  name: images-get-recursion1-untrusted
  path: /1.0/images?public&recursion=1
- description: Get the images
  method: GET
  name: images-get-recursion1
  path: /1.0/images?recursion=1
- description: Get the instances
  method: GET
  name: instances-get
  path: /1.0/instances
personas: []
provider_name: Incus
provider_slug: incus
search_terms:
- get the public image
- containers
- images export post
- certificates get recursion1
- server patch
- api
- cluster group get
- cluster group put
- certificate get
- images post untrusted
- update the certificate for the cluster
- get the instances
- create a cluster group.
- delete the cluster member
- cluster member put
- cluster group patch
- linux
- cluster member state post
- image patch
- api get
- make the server push the image to a remote server
- virtual machines
- instances get
- cluster member patch
- delete the image
- evacuate or restore a cluster member
- update the image alias
- certificates post
- certificates get
- partially update the image alias
- rename the image alias
- images aliases get
- cluster group delete
- cluster group post
- update the cluster group
- virtualization
- get the cluster group
- get the cluster groups
- get the images
- delete the trusted certificate
- images get
- images aliases post
- partially update the server configuration
- image get untrusted
- events get
- cluster member state get
- images aliases get recursion1
- cluster members get
- update the trusted certificate
- images aliases put
- get the server environment and configuration
- partially update the trusted certificate
- get the cluster member
- images secret post
- get the raw image file(s)
- image delete
- get the image alias
- images get untrusted
- image alias get untrusted
- get the image
- get the public images
- certificate put
- get state of the cluster member
- cluster groups get recursion1
- images post
- clustering update cert
- get the trusted certificates
- cluster get
- images get recursion1
- server get
- certificate patch
- get the event stream
- update the server configuration
- partially update the cluster member
- get the public image alias
- image put
- refresh an image
- add an image alias
- cluster member get
- image export get
- images get recursion1 untrusted
- image alias get
- server put
- get the supported api endpoints
- cluster groups get
- get the image aliases
- image export get untrusted
- image alias delete
- images alias patch
- generate secret for retrieval of the image by an untrusted client
- update the cluster member
- get the cluster configuration
- delete the image alias
- images refresh post
- add an image
- certificate delete
- update the cluster configuration
- incus
- rename the cluster group
- images alias post
- open source
- get the cluster members
- cluster members post
- cluster members get recursion1
- cluster groups post
- partially update the image
- request a join token
- certificates post untrusted
- cluster put
- rename the cluster member
- update the image
- cluster member post
- cluster member delete
- add a trusted certificate
- image get
- get the trusted certificate
- delete the cluster group.
slug: incus-capability
source_filename: incus-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Incus external REST API\n  description: This is the REST API used by all Incus clients. Internal endpoints aren't included in this documentation. The\n    Incus API is available over both a local unix+http and remote https API. Authentication for local users relies on group\n    membership and access to the unix socket. For remote users, the default authentication method is TLS client certificates.\n  tags:\n  - Incus\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: incus\n    baseUri: https://api.example.com\n    description: Incus external REST API HTTP API.\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: api-get\n        method: GET\n        description: Get the supported API endpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0\n\
  \      path: /1.0\n      operations:\n      - name: server-get\n        method: GET\n        description: Get the server environment and configuration\n        inputParameters:\n        - name: target\n          in: query\n          type: string\n          description: Cluster member name\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: server-patch\n        method: PATCH\n        description: Partially update the server configuration\n        inputParameters:\n        - name: target\n          in: query\n          type: string\n          description: Cluster member name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: server-put\n        method: PUT\n        description: Update the server configuration\n\
  \        inputParameters:\n        - name: target\n          in: query\n          type: string\n          description: Cluster member name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-certificates\n      path: /1.0/certificates\n      operations:\n      - name: certificates-get\n        method: GET\n        description: Get the trusted certificates\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          description: Collection filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: certificates-post\n        method: POST\n        description: Add a trusted certificate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-certificates-fingerprint\n      path: /1.0/certificates/{fingerprint}\n\
  \      operations:\n      - name: certificate-delete\n        method: DELETE\n        description: Delete the trusted certificate\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: certificate-get\n        method: GET\n        description: Get the trusted certificate\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: certificate-patch\n        method: PATCH\n        description: Partially update the trusted certificate\n        inputParameters:\n        - name: fingerprint\n          in: path\n\
  \          type: string\n          required: true\n          description: Fingerprint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: certificate-put\n        method: PUT\n        description: Update the trusted certificate\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-certificates-public\n      path: /1.0/certificates?public\n      operations:\n      - name: certificates-post-untrusted\n        method: POST\n        description: Add a trusted certificate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-certificates-recursion-1\n      path: /1.0/certificates?recursion=1\n\
  \      operations:\n      - name: certificates-get-recursion1\n        method: GET\n        description: Get the trusted certificates\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          description: Collection filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-cluster\n      path: /1.0/cluster\n      operations:\n      - name: cluster-get\n        method: GET\n        description: Get the cluster configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cluster-put\n        method: PUT\n        description: Update the cluster configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-cluster-certificate\n      path: /1.0/cluster/certificate\n\
  \      operations:\n      - name: clustering-update-cert\n        method: PUT\n        description: Update the certificate for the cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-cluster-groups\n      path: /1.0/cluster/groups\n      operations:\n      - name: cluster-groups-get\n        method: GET\n        description: Get the cluster groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cluster-groups-post\n        method: POST\n        description: Create a cluster group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-cluster-groups-name\n      path: /1.0/cluster/groups/{name}\n      operations:\n      - name: cluster-group-delete\n        method: DELETE\n        description: Delete the cluster\
  \ group.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Cluster group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cluster-group-get\n        method: GET\n        description: Get the cluster group\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Cluster group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cluster-group-patch\n        method: PATCH\n        description: Update the cluster group\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Cluster group name\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: cluster-group-post\n        method: POST\n        description: Rename the cluster group\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Cluster group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cluster-group-put\n        method: PUT\n        description: Update the cluster group\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Cluster group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-cluster-groups-recursion-1\n      path: /1.0/cluster/groups?recursion=1\n      operations:\n      - name: cluster-groups-get-recursion1\n\
  \        method: GET\n        description: Get the cluster groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-cluster-members\n      path: /1.0/cluster/members\n      operations:\n      - name: cluster-members-get\n        method: GET\n        description: Get the cluster members\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          description: Collection filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cluster-members-post\n        method: POST\n        description: Request a join token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-cluster-members-name\n      path: /1.0/cluster/members/{name}\n      operations:\n      - name: cluster-member-delete\n\
  \        method: DELETE\n        description: Delete the cluster member\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Cluster member name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cluster-member-get\n        method: GET\n        description: Get the cluster member\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Cluster member name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cluster-member-patch\n        method: PATCH\n        description: Partially update the cluster member\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description:\
  \ Cluster member name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cluster-member-post\n        method: POST\n        description: Rename the cluster member\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Cluster member name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cluster-member-put\n        method: PUT\n        description: Update the cluster member\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Cluster member name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-cluster-members-name-state\n      path: /1.0/cluster/members/{name}/state\n\
  \      operations:\n      - name: cluster-member-state-get\n        method: GET\n        description: Get state of the cluster member\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Cluster member name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cluster-member-state-post\n        method: POST\n        description: Evacuate or restore a cluster member\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Cluster member name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-cluster-members-recursion-1\n      path: /1.0/cluster/members?recursion=1\n      operations:\n      - name: cluster-members-get-recursion1\n        method:\
  \ GET\n        description: Get the cluster members\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          description: Collection filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-events\n      path: /1.0/events\n      operations:\n      - name: events-get\n        method: GET\n        description: Get the event stream\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        - name: type\n          in: query\n          type: string\n          description: Event type(s), comma separated (valid types are logging, operation or lifecycle)\n        - name: all-projects\n          in: query\n          type: string\n          description: Retrieve instances from all projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n    - name: 1-0-images\n      path: /1.0/images\n      operations:\n      - name: images-get\n        method: GET\n        description: Get the images\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        - name: filter\n          in: query\n          type: string\n          description: Collection filter\n        - name: all-projects\n          in: query\n          type: string\n          description: Retrieve images from all projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: images-post\n        method: POST\n        description: Add an image\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        - name: X-Incus-secret\n          in: header\n          type: string\n   \
  \       description: Push secret for server to server communication\n        - name: X-Incus-fingerprint\n          in: header\n          type: string\n          description: Expected fingerprint when pushing a raw image\n        - name: X-Incus-aliases\n          in: header\n          type: array\n          description: List of aliases to assign\n        - name: X-Incus-properties\n          in: header\n          type: object\n          description: Descriptive properties\n        - name: X-Incus-public\n          in: header\n          type: boolean\n          description: Whether the image is available to unauthenticated users\n        - name: X-Incus-filename\n          in: header\n          type: string\n          description: Original filename of the image\n        - name: X-Incus-profiles\n          in: header\n          type: array\n          description: List of profiles to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: 1-0-images-fingerprint\n      path: /1.0/images/{fingerprint}\n      operations:\n      - name: image-delete\n        method: DELETE\n        description: Delete the image\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: image-get\n        method: GET\n        description: Get the image\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: image-patch\n        method: PATCH\n        description: Partially update the image\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: image-put\n        method: PUT\n        description: Update the image\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: 1-0-images-fingerprint-export\n      path: /1.0/images/{fingerprint}/export\n      operations:\n      - name: image-export-get\n        method: GET\n        description: Get the raw image file(s)\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: images-export-post\n        method: POST\n        description: Make the server push the image to a remote server\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        - name: project\n          in: query\n          type:\
  \ string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-images-fingerprint-export-public\n      path: /1.0/images/{fingerprint}/export?public\n      operations:\n      - name: image-export-get-untrusted\n        method: GET\n        description: Get the raw image file(s)\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        - name: secret\n          in: query\n          type: string\n          description: Secret token to retrieve a private image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-images-fingerprint-refresh\n      path: /1.0/images/{fingerprint}/refresh\n\
  \      operations:\n      - name: images-refresh-post\n        method: POST\n        description: Refresh an image\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-images-fingerprint-secret\n      path: /1.0/images/{fingerprint}/secret\n      operations:\n      - name: images-secret-post\n        method: POST\n        description: Generate secret for retrieval of the image by an untrusted client\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        - name: project\n          in: query\n          type: string\n     \
  \     description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-images-fingerprint-public\n      path: /1.0/images/{fingerprint}?public\n      operations:\n      - name: image-get-untrusted\n        method: GET\n        description: Get the public image\n        inputParameters:\n        - name: fingerprint\n          in: path\n          type: string\n          required: true\n          description: Fingerprint\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        - name: secret\n          in: query\n          type: string\n          description: Secret token to retrieve a private image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-images-aliases\n      path: /1.0/images/aliases\n      operations:\n      - name: images-aliases-get\n\
  \        method: GET\n        description: Get the image aliases\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: images-aliases-post\n        method: POST\n        description: Add an image alias\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-images-aliases-name\n      path: /1.0/images/aliases/{name}\n      operations:\n      - name: image-alias-delete\n        method: DELETE\n        description: Delete the image alias\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n\
  \          description: Alias name\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: image-alias-get\n        method: GET\n        description: Get the image alias\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Alias name\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: images-alias-patch\n        method: PATCH\n        description: Partially update the image alias\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description:\
  \ Alias name\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: images-alias-post\n        method: POST\n        description: Rename the image alias\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Alias name\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: images-aliases-put\n        method: PUT\n        description: Update the image alias\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Alias name\n        - name:\
  \ project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-images-aliases-name-public\n      path: /1.0/images/aliases/{name}?public\n      operations:\n      - name: image-alias-get-untrusted\n        method: GET\n        description: Get the public image alias\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Alias name\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-images-aliases-recursion-1\n      path: /1.0/images/aliases?recursion=1\n      operations:\n      - name: images-aliases-get-recursion1\n        method: GET\n\
  \        description: Get the image aliases\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-images-public\n      path: /1.0/images?public\n      operations:\n      - name: images-get-untrusted\n        method: GET\n        description: Get the public images\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        - name: filter\n          in: query\n          type: string\n          description: Collection filter\n        - name: all-projects\n          in: query\n          type: string\n          description: Retrieve images from all projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: images-post-untrusted\n        method: POST\n        description: Add an image\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-images-public-recursion-1\n      path: /1.0/images?public&recursion=1\n      operations:\n      - name: images-get-recursion1-untrusted\n        method: GET\n        description: Get the public images\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        - name: filter\n          in: query\n          type: string\n          description: Collection filter\n        - name: all-projects\n          in: query\n          type: string\n          description: Retrieve images from all projects\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: 1-0-images-recursion-1\n      path: /1.0/images?recursion=1\n      operations:\n      - name: images-get-recursion1\n        method: GET\n        description: Get the images\n        inputParameters:\n        - name: project\n          in: query\n          type: string\n          description: Project name\n        - name: filter\n          in: query\n          type: string\n          description: Collection filter\n        - name: all-projects\n          in: query\n          type: string\n          description: Retrieve images from all projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: 1-0-instances\n      path: /1.0/instances\n      operations:\n      - name: instances-get\n        method: GET\n        description: Get the instances\n        inputParameters:\n        - name: project\n          in: query\n  \
  \        type: string\n          description: Project name\n        - name: filter\n          in: query\n          type: string\n          description: Collection filter\n        - name: all-projects\n          in: query\n          type: string\n          description: Retrieve instances from all projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: incus-rest\n    description: REST adapter for Incus external REST API.\n    resources:\n    - path: /\n      name: api-get\n      operations:\n      - method: GET\n        name: api-get\n        description: Get the supported API endpoints\n        call: incus.api-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1.0\n      name: server-get\n      operations:\n      - method: GET\n        name: server-get\n        description: Get the server environment and configuration\n\
  \        call: incus.server-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1.0\n      name: server-patch\n      operations:\n      - method: PATCH\n        name: server-patch\n        description: Partially update the server configuration\n        call: incus.server-patch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1.0\n      name: server-put\n      operations:\n      - method: PUT\n        name: server-put\n        description: Update the server configuration\n        call: incus.server-put\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1.0/certificates\n      name: certificates-get\n      operations:\n      - method: GET\n        name: certificates-get\n        description: Get the trusted certificates\n        call: incus.certificates-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1.0/certificates\n      name:\
  \ certificates-post\n      operations:\n      - method: POST\n        name: certificates-post\n        description: Add a trusted certificate\n        call: incus.certificates-post\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1.0/certificates/{fingerprint}\n      name: certificate-delete\n      operations:\n      - method: DELETE\n        name: certificate-delete\n        description: Delete the trusted certificate\n        call: incus.certificate-delete\n        with:\n          fingerprint: rest.fingerprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1.0/certificates/{fingerprint}\n      name: certificate-get\n      operations:\n      - method: GET\n        name: certificate-get\n        description: Get the trusted certificate\n        call: incus.certificate-get\n        with:\n          fingerprint: rest.fingerprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /1.0/certificates/{fingerprint}\n      name: certificate-patch\n      operations:\n      - method: PATCH\n        name: certificate-patch\n        description: Partially update the trusted certificate\n        call: incus.certificate-patch\n        with:\n          fingerprint: rest.fingerprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1.0/certificates/{fingerprint}\n      name: certificate-put\n      operations:\n      - method: PUT\n        name: certificate-put\n        description: Update the trusted certificate\n        call: incus.certificate-put\n        with:\n          fingerprint: rest.fingerprint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1.0/certificates?public\n      name: certificates-post-untrusted\n      operations:\n      - method: POST\n        name: certificates-post-untrusted\n        description: Add a trusted certificate\n        call: incus.certificates-post-untrusted\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1.0/certificates?recursion=1\n      name: certificates-get-recursion1\n      operations:\n      - method: GET\n        name: certificates-get-recursion1\n        description: Get the trusted certificates\n        call: incus.certificates-get-recursion1\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1.0/cluster\n      name: cluster-get\n      operations:\n      - method: GET\n        name: cluster-get\n        description: Get the cluster configuration\n        call: incus.cluster-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /1.0/cluster\n      name: cluster-put\n      operations:\n      - met\n\n# --- truncated at 32 KB (74 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/incus/refs/heads/main/capabilities/incus-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/incus/refs/heads/main/capabilities/incus-capability.yaml
tags:
- Incus
- API
tools:
- description: Get the supported API endpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: api-get
- description: Get the server environment and configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: server-get
- description: Partially update the server configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: server-patch
- description: Update the server configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: server-put
- description: Get the trusted certificates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: certificates-get
- description: Add a trusted certificate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: certificates-post
- description: Delete the trusted certificate
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: certificate-delete
- description: Get the trusted certificate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: certificate-get
- description: Partially update the trusted certificate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: certificate-patch
- description: Update the trusted certificate
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: certificate-put
- description: Add a trusted certificate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: certificates-post-untrusted
- description: Get the trusted certificates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: certificates-get-recursion1
- description: Get the cluster configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cluster-get
- description: Update the cluster configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: cluster-put
- description: Update the certificate for the cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: clustering-update-cert
- description: Get the cluster groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cluster-groups-get
- description: Create a cluster group.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cluster-groups-post
- description: Delete the cluster group.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cluster-group-delete
- description: Get the cluster group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cluster-group-get
- description: Update the cluster group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cluster-group-patch
- description: Rename the cluster group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cluster-group-post
- description: Update the cluster group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: cluster-group-put
- description: Get the cluster groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cluster-groups-get-recursion1
- description: Get the cluster members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cluster-members-get
- description: Request a join token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cluster-members-post
- description: Delete the cluster member
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cluster-member-delete
- description: Get the cluster member
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cluster-member-get
- description: Partially update the cluster member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cluster-member-patch
- description: Rename the cluster member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cluster-member-post
- description: Update the cluster member
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: cluster-member-put
- description: Get state of the cluster member
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cluster-member-state-get
- description: Evacuate or restore a cluster member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cluster-member-state-post
- description: Get the cluster members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cluster-members-get-recursion1
- description: Get the event stream
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: events-get
- description: Get the images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: images-get
- description: Add an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: images-post
- description: Delete the image
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: image-delete
- description: Get the image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: image-get
- description: Partially update the image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: image-patch
- description: Update the image
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: image-put
- description: Get the raw image file(s)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: image-export-get
- description: Make the server push the image to a remote server
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: images-export-post
- description: Get the raw image file(s)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: image-export-get-untrusted
- description: Refresh an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: images-refresh-post
- description: Generate secret for retrieval of the image by an untrusted client
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: images-secret-post
- description: Get the public image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: image-get-untrusted
- description: Get the image aliases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: images-aliases-get
- description: Add an image alias
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: images-aliases-post
- description: Delete the image alias
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: image-alias-delete
- description: Get the image alias
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: image-alias-get
- description: Partially update the image alias
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: images-alias-patch
- description: Rename the image alias
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: images-alias-post
- description: Update the image alias
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: images-aliases-put
- description: Get the public image alias
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: image-alias-get-untrusted
- description: Get the image aliases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: images-aliases-get-recursion1
- description: Get the public images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: images-get-untrusted
- description: Add an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: images-post-untrusted
- description: Get the public images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: images-get-recursion1-untrusted
- description: Get the images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: images-get-recursion1
- description: Get the instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: instances-get
---
