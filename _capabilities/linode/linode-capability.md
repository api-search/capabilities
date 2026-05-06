---
categories: []
consumed_apis: []
description: The Linode API v4 provides programmatic access to the full range of Akamai Connected Cloud (formerly Linode) products and services. It enables developers to create and manage compute instances, deploy Kubernetes clusters, configure NodeBalancers, manage DNS domains, provision Block Storage volumes, control Object Storage buckets, set up firewalls, and administer account settings. The RESTful API uses OAuth and personal access tokens for authentication and returns JSON responses, with support for filtering and sorting across all resource endpoints.
layout: capability
name: Linode API v4
operations:
- description: Get account info
  method: GET
  name: getaccount
  path: /account
- description: Update account info
  method: PUT
  name: updateaccount
  path: /account
- description: List users
  method: GET
  name: getusers
  path: /account/users
- description: Create a user
  method: POST
  name: createuser
  path: /account/users
- description: Get a user
  method: GET
  name: getuser
  path: /account/users/{username}
- description: Update a user
  method: PUT
  name: updateuser
  path: /account/users/{username}
- description: Delete a user
  method: DELETE
  name: deleteuser
  path: /account/users/{username}
- description: List events
  method: GET
  name: getevents
  path: /account/events
- description: Get an event
  method: GET
  name: getevent
  path: /account/events/{eventId}
- description: List invoices
  method: GET
  name: getinvoices
  path: /account/invoices
- description: List payments
  method: GET
  name: getpayments
  path: /account/payments
- description: Make a payment
  method: POST
  name: createpayment
  path: /account/payments
- description: List Managed Databases
  method: GET
  name: getdatabaseinstances
  path: /databases/instances
- description: List Managed Database engines
  method: GET
  name: getdatabaseengines
  path: /databases/engines
- description: List Managed Database types
  method: GET
  name: getdatabasetypes
  path: /databases/types
- description: Get a Managed Database
  method: GET
  name: getdatabaseinstance
  path: /databases/{databaseEngine}/{databaseId}
- description: Update a Managed Database
  method: PUT
  name: updatedatabaseinstance
  path: /databases/{databaseEngine}/{databaseId}
- description: Delete a Managed Database
  method: DELETE
  name: deletedatabaseinstance
  path: /databases/{databaseEngine}/{databaseId}
- description: List domains
  method: GET
  name: getdomains
  path: /domains
- description: Create a domain
  method: POST
  name: createdomain
  path: /domains
- description: Get a domain
  method: GET
  name: getdomain
  path: /domains/{domainId}
- description: Update a domain
  method: PUT
  name: updatedomain
  path: /domains/{domainId}
- description: Delete a domain
  method: DELETE
  name: deletedomain
  path: /domains/{domainId}
- description: List domain records
  method: GET
  name: getdomainrecords
  path: /domains/{domainId}/records
- description: Create a domain record
  method: POST
  name: createdomainrecord
  path: /domains/{domainId}/records
- description: List images
  method: GET
  name: getimages
  path: /images
- description: Create an image
  method: POST
  name: createimage
  path: /images
- description: Get an image
  method: GET
  name: getimage
  path: /images/{imageId}
- description: Update an image
  method: PUT
  name: updateimage
  path: /images/{imageId}
- description: Delete an image
  method: DELETE
  name: deleteimage
  path: /images/{imageId}
- description: List Linodes
  method: GET
  name: getlinodeinstances
  path: /linode/instances
- description: Create a Linode
  method: POST
  name: createlinodeinstance
  path: /linode/instances
- description: Get a Linode
  method: GET
  name: getlinodeinstance
  path: /linode/instances/{linodeId}
- description: Update a Linode
  method: PUT
  name: updatelinodeinstance
  path: /linode/instances/{linodeId}
- description: Delete a Linode
  method: DELETE
  name: deletelinodeinstance
  path: /linode/instances/{linodeId}
- description: Boot a Linode
  method: POST
  name: bootlinodeinstance
  path: /linode/instances/{linodeId}/boot
- description: Reboot a Linode
  method: POST
  name: rebootlinodeinstance
  path: /linode/instances/{linodeId}/reboot
- description: Shut down a Linode
  method: POST
  name: shutdownlinodeinstance
  path: /linode/instances/{linodeId}/shutdown
- description: Resize a Linode
  method: POST
  name: resizelinodeinstance
  path: /linode/instances/{linodeId}/resize
- description: Rebuild a Linode
  method: POST
  name: rebuildlinodeinstance
  path: /linode/instances/{linodeId}/rebuild
- description: Clone a Linode
  method: POST
  name: clonelinodeinstance
  path: /linode/instances/{linodeId}/clone
- description: List backups
  method: GET
  name: getbackups
  path: /linode/instances/{linodeId}/backups
- description: List disks
  method: GET
  name: getlinodedisks
  path: /linode/instances/{linodeId}/disks
- description: List configuration profiles
  method: GET
  name: getlinodeconfigs
  path: /linode/instances/{linodeId}/configs
- description: Get networking information
  method: GET
  name: getlinodeips
  path: /linode/instances/{linodeId}/ips
- description: List types
  method: GET
  name: getlinodetypes
  path: /linode/types
- description: List kernels
  method: GET
  name: getkernels
  path: /linode/kernels
- description: List StackScripts
  method: GET
  name: getstackscripts
  path: /linode/stackscripts
- description: Create a StackScript
  method: POST
  name: createstackscript
  path: /linode/stackscripts
- description: Get a StackScript
  method: GET
  name: getstackscript
  path: /linode/stackscripts/{stackscriptId}
- description: Update a StackScript
  method: PUT
  name: updatestackscript
  path: /linode/stackscripts/{stackscriptId}
- description: Delete a StackScript
  method: DELETE
  name: deletestackscript
  path: /linode/stackscripts/{stackscriptId}
- description: List Kubernetes clusters
  method: GET
  name: getlkeclusters
  path: /lke/clusters
- description: Create a Kubernetes cluster
  method: POST
  name: createlkecluster
  path: /lke/clusters
- description: Get a Kubernetes cluster
  method: GET
  name: getlkecluster
  path: /lke/clusters/{clusterId}
- description: Update a Kubernetes cluster
  method: PUT
  name: updatelkecluster
  path: /lke/clusters/{clusterId}
- description: Delete a Kubernetes cluster
  method: DELETE
  name: deletelkecluster
  path: /lke/clusters/{clusterId}
- description: List node pools
  method: GET
  name: getlkenodepools
  path: /lke/clusters/{clusterId}/pools
- description: Create a node pool
  method: POST
  name: createlkenodepool
  path: /lke/clusters/{clusterId}/pools
- description: Get kubeconfig
  method: GET
  name: getlkeclusterkubeconfig
  path: /lke/clusters/{clusterId}/kubeconfig
personas: []
provider_name: linode
provider_slug: linode
search_terms:
- list events
- getstackscripts
- deletelinodeinstance
- createlinodeinstance
- list linodes
- getdomain
- getlinodeinstances
- getlkeclusters
- update a linode
- list payments
- get a stackscript
- list managed database engines
- api
- getlinodeconfigs
- getkernels
- delete a stackscript
- list managed databases
- create a user
- shut down a linode
- create a domain record
- getimages
- getuser
- getlinodetypes
- getevent
- list invoices
- reboot a linode
- clone a linode
- getdatabaseengines
- updateuser
- deletelkecluster
- deleteuser
- create a kubernetes cluster
- createuser
- resizelinodeinstance
- get networking information
- clonelinodeinstance
- getpayments
- getlinodeinstance
- delete a domain
- delete an image
- list stackscripts
- create a node pool
- createstackscript
- make a payment
- get an event
- linode
- updateimage
- list kernels
- update an image
- get a managed database
- getusers
- delete a managed database
- rebuild a linode
- create an image
- getdatabaseinstance
- getinvoices
- getlinodeips
- list domains
- deletestackscript
- list types
- get a domain
- deletedatabaseinstance
- getlkeclusterkubeconfig
- getstackscript
- createdomain
- resize a linode
- update account info
- shutdownlinodeinstance
- create a linode
- list kubernetes clusters
- deletedomain
- updatedatabaseinstance
- getlinodedisks
- list configuration profiles
- get an image
- update a managed database
- get a linode
- rebuildlinodeinstance
- get a kubernetes cluster
- updateaccount
- delete a linode
- getevents
- list node pools
- update a stackscript
- list disks
- getdatabaseinstances
- updatelkecluster
- list images
- create a stackscript
- getbackups
- update a domain
- delete a kubernetes cluster
- update a kubernetes cluster
- list domain records
- create a domain
- delete a user
- updatedomain
- get kubeconfig
- createpayment
- getaccount
- list backups
- updatelinodeinstance
- get account info
- getimage
- getdatabasetypes
- bootlinodeinstance
- getlkecluster
- getdomains
- createlkenodepool
- list users
- get a user
- update a user
- createlkecluster
- createimage
- boot a linode
- list managed database types
- getlkenodepools
- updatestackscript
- rebootlinodeinstance
- getdomainrecords
- deleteimage
- createdomainrecord
slug: linode-capability
source_filename: linode-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Linode API v4\n  description: The Linode API v4 provides programmatic access to the full range of Akamai Connected Cloud (formerly Linode)\n    products and services. It enables developers to create and manage compute instances, deploy Kubernetes clusters, configure\n    NodeBalancers, manage DNS domains, provision Block Storage volumes, control Object Storage buckets, set up firewalls,\n    and administer account settings. The RESTful API uses OAuth and personal access tokens for authentication and returns\n    JSON responses, with support for filtering and sorting across all resource endpoints.\n  tags:\n  - Linode\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: linode\n    baseUri: https://api.linode.com/v4\n    description: Linode API v4 HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LINODE_TOKEN}}'\n    resources:\n    - name: account\n    \
  \  path: /account\n      operations:\n      - name: getaccount\n        method: GET\n        description: Get account info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccount\n        method: PUT\n        description: Update account info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-users\n      path: /account/users\n      operations:\n      - name: getusers\n        method: GET\n        description: List users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Create a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-users-username\n   \
  \   path: /account/users/{username}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PUT\n        description: Update a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Delete a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-events\n      path: /account/events\n      operations:\n      - name: getevents\n        method: GET\n        description: List events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-events-eventid\n\
  \      path: /account/events/{eventId}\n      operations:\n      - name: getevent\n        method: GET\n        description: Get an event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-invoices\n      path: /account/invoices\n      operations:\n      - name: getinvoices\n        method: GET\n        description: List invoices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-payments\n      path: /account/payments\n      operations:\n      - name: getpayments\n        method: GET\n        description: List payments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpayment\n        method: POST\n        description: Make a payment\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: databases-instances\n      path: /databases/instances\n      operations:\n      - name: getdatabaseinstances\n        method: GET\n        description: List Managed Databases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: databases-engines\n      path: /databases/engines\n      operations:\n      - name: getdatabaseengines\n        method: GET\n        description: List Managed Database engines\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: databases-types\n      path: /databases/types\n      operations:\n      - name: getdatabasetypes\n        method: GET\n        description: List Managed Database types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: databases-databaseengine-databaseid\n      path: /databases/{databaseEngine}/{databaseId}\n      operations:\n      - name: getdatabaseinstance\n        method: GET\n        description: Get a Managed Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedatabaseinstance\n        method: PUT\n        description: Update a Managed Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedatabaseinstance\n        method: DELETE\n        description: Delete a Managed Database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains\n      path: /domains\n      operations:\n      - name: getdomains\n        method: GET\n        description: List domains\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdomain\n        method: POST\n        description: Create a domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains-domainid\n      path: /domains/{domainId}\n      operations:\n      - name: getdomain\n        method: GET\n        description: Get a domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedomain\n        method: PUT\n        description: Update a domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedomain\n        method: DELETE\n        description: Delete a domain\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: domains-domainid-records\n      path: /domains/{domainId}/records\n      operations:\n      - name: getdomainrecords\n        method: GET\n        description: List domain records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdomainrecord\n        method: POST\n        description: Create a domain record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images\n      path: /images\n      operations:\n      - name: getimages\n        method: GET\n        description: List images\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createimage\n        method: POST\n        description: Create an image\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: images-imageid\n      path: /images/{imageId}\n      operations:\n      - name: getimage\n        method: GET\n        description: Get an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateimage\n        method: PUT\n        description: Update an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteimage\n        method: DELETE\n        description: Delete an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: linode-instances\n      path: /linode/instances\n      operations:\n      - name: getlinodeinstances\n        method: GET\n        description: List Linodes\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createlinodeinstance\n        method: POST\n        description: Create a Linode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: linode-instances-linodeid\n      path: /linode/instances/{linodeId}\n      operations:\n      - name: getlinodeinstance\n        method: GET\n        description: Get a Linode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelinodeinstance\n        method: PUT\n        description: Update a Linode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelinodeinstance\n        method: DELETE\n        description: Delete a Linode\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: linode-instances-linodeid-boot\n      path: /linode/instances/{linodeId}/boot\n      operations:\n      - name: bootlinodeinstance\n        method: POST\n        description: Boot a Linode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: linode-instances-linodeid-reboot\n      path: /linode/instances/{linodeId}/reboot\n      operations:\n      - name: rebootlinodeinstance\n        method: POST\n        description: Reboot a Linode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: linode-instances-linodeid-shutdown\n      path: /linode/instances/{linodeId}/shutdown\n      operations:\n      - name: shutdownlinodeinstance\n        method: POST\n        description: Shut down a Linode\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n    - name: linode-instances-linodeid-resize\n      path: /linode/instances/{linodeId}/resize\n      operations:\n      - name: resizelinodeinstance\n        method: POST\n        description: Resize a Linode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: linode-instances-linodeid-rebuild\n      path: /linode/instances/{linodeId}/rebuild\n      operations:\n      - name: rebuildlinodeinstance\n        method: POST\n        description: Rebuild a Linode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: linode-instances-linodeid-clone\n      path: /linode/instances/{linodeId}/clone\n      operations:\n      - name: clonelinodeinstance\n        method: POST\n        description: Clone a Linode\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: linode-instances-linodeid-backups\n      path: /linode/instances/{linodeId}/backups\n      operations:\n      - name: getbackups\n        method: GET\n        description: List backups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: linode-instances-linodeid-disks\n      path: /linode/instances/{linodeId}/disks\n      operations:\n      - name: getlinodedisks\n        method: GET\n        description: List disks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: linode-instances-linodeid-configs\n      path: /linode/instances/{linodeId}/configs\n      operations:\n      - name: getlinodeconfigs\n        method: GET\n        description: List configuration profiles\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n    - name: linode-instances-linodeid-ips\n      path: /linode/instances/{linodeId}/ips\n      operations:\n      - name: getlinodeips\n        method: GET\n        description: Get networking information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: linode-types\n      path: /linode/types\n      operations:\n      - name: getlinodetypes\n        method: GET\n        description: List types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: linode-kernels\n      path: /linode/kernels\n      operations:\n      - name: getkernels\n        method: GET\n        description: List kernels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: linode-stackscripts\n\
  \      path: /linode/stackscripts\n      operations:\n      - name: getstackscripts\n        method: GET\n        description: List StackScripts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createstackscript\n        method: POST\n        description: Create a StackScript\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: linode-stackscripts-stackscriptid\n      path: /linode/stackscripts/{stackscriptId}\n      operations:\n      - name: getstackscript\n        method: GET\n        description: Get a StackScript\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatestackscript\n        method: PUT\n        description: Update a StackScript\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: deletestackscript\n        method: DELETE\n        description: Delete a StackScript\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lke-clusters\n      path: /lke/clusters\n      operations:\n      - name: getlkeclusters\n        method: GET\n        description: List Kubernetes clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlkecluster\n        method: POST\n        description: Create a Kubernetes cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lke-clusters-clusterid\n      path: /lke/clusters/{clusterId}\n      operations:\n      - name: getlkecluster\n        method: GET\n        description: Get a Kubernetes cluster\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelkecluster\n        method: PUT\n        description: Update a Kubernetes cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelkecluster\n        method: DELETE\n        description: Delete a Kubernetes cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lke-clusters-clusterid-pools\n      path: /lke/clusters/{clusterId}/pools\n      operations:\n      - name: getlkenodepools\n        method: GET\n        description: List node pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlkenodepool\n        method: POST\n        description: Create a node\
  \ pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lke-clusters-clusterid-kubeconfig\n      path: /lke/clusters/{clusterId}/kubeconfig\n      operations:\n      - name: getlkeclusterkubeconfig\n        method: GET\n        description: Get kubeconfig\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: linode-rest\n    description: REST adapter for Linode API v4.\n    resources:\n    - path: /account\n      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Get account info\n        call: linode.getaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account\n      name: updateaccount\n      operations:\n      - method: PUT\n        name: updateaccount\n        description:\
  \ Update account info\n        call: linode.updateaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/users\n      name: getusers\n      operations:\n      - method: GET\n        name: getusers\n        description: List users\n        call: linode.getusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/users\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Create a user\n        call: linode.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/users/{username}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get a user\n        call: linode.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/users/{username}\n      name: updateuser\n      operations:\n      - method:\
  \ PUT\n        name: updateuser\n        description: Update a user\n        call: linode.updateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/users/{username}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Delete a user\n        call: linode.deleteuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/events\n      name: getevents\n      operations:\n      - method: GET\n        name: getevents\n        description: List events\n        call: linode.getevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/events/{eventId}\n      name: getevent\n      operations:\n      - method: GET\n        name: getevent\n        description: Get an event\n        call: linode.getevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/invoices\n\
  \      name: getinvoices\n      operations:\n      - method: GET\n        name: getinvoices\n        description: List invoices\n        call: linode.getinvoices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/payments\n      name: getpayments\n      operations:\n      - method: GET\n        name: getpayments\n        description: List payments\n        call: linode.getpayments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/payments\n      name: createpayment\n      operations:\n      - method: POST\n        name: createpayment\n        description: Make a payment\n        call: linode.createpayment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/instances\n      name: getdatabaseinstances\n      operations:\n      - method: GET\n        name: getdatabaseinstances\n        description: List Managed Databases\n        call: linode.getdatabaseinstances\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/engines\n      name: getdatabaseengines\n      operations:\n      - method: GET\n        name: getdatabaseengines\n        description: List Managed Database engines\n        call: linode.getdatabaseengines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/types\n      name: getdatabasetypes\n      operations:\n      - method: GET\n        name: getdatabasetypes\n        description: List Managed Database types\n        call: linode.getdatabasetypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/{databaseEngine}/{databaseId}\n      name: getdatabaseinstance\n      operations:\n      - method: GET\n        name: getdatabaseinstance\n        description: Get a Managed Database\n        call: linode.getdatabaseinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /databases/{databaseEngine}/{databaseId}\n      name: updatedatabaseinstance\n      operations:\n      - method: PUT\n        name: updatedatabaseinstance\n        description: Update a Managed Database\n        call: linode.updatedatabaseinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/{databaseEngine}/{databaseId}\n      name: deletedatabaseinstance\n      operations:\n      - method: DELETE\n        name: deletedatabaseinstance\n        description: Delete a Managed Database\n        call: linode.deletedatabaseinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains\n      name: getdomains\n      operations:\n      - method: GET\n        name: getdomains\n        description: List domains\n        call: linode.getdomains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains\n      name: createdomain\n      operations:\n     \
  \ - method: POST\n        name: createdomain\n        description: Create a domain\n        call: linode.createdomain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domainId}\n      name: getdomain\n      operations:\n      - method: GET\n        name: getdomain\n        description: Get a domain\n        call: linode.getdomain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domainId}\n      name: updatedomain\n      operations:\n      - method: PUT\n        name: updatedomain\n        description: Update a domain\n        call: linode.updatedomain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domainId}\n      name: deletedomain\n      operations:\n      - method: DELETE\n        name: deletedomain\n        description: Delete a domain\n        call: linode.deletedomain\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /domains/{domainId}/records\n      name: getdomainrecords\n      operations:\n      - method: GET\n        name: getdomainrecords\n        description: List domain records\n        call: linode.getdomainrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains/{domainId}/records\n      name: createdomainrecord\n      operations:\n      - method: POST\n        name: createdomainrecord\n        description: Create a domain record\n        call: linode.createdomainrecord\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images\n      name: getimages\n      operations:\n      - method: GET\n        name: getimages\n        description: List images\n        call: linode.getimages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images\n      name: createimage\n      operations:\n      - method: POST\n        name: createimage\n        description: Create\
  \ an image\n        call: linode.createimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images/{imageId}\n      name: getimage\n      operations:\n      - method: GET\n        name: getimage\n        description: Get an image\n        call: linode.getimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images/{imageId}\n      name: updateimage\n      operations:\n      - method: PUT\n        name: updateimage\n        description: Update an image\n        call: linode.updateimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images/{imageId}\n      name: deleteimage\n      operations:\n      - method: DELETE\n        name: deleteimage\n        description: Delete an image\n        call: linode.deleteimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances\n      name: getlinodeinstances\n      operations:\n\
  \      - method: GET\n        name: getlinodeinstances\n        description: List Linodes\n        call: linode.getlinodeinstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances\n      name: createlinodeinstance\n      operations:\n      - method: POST\n        name: createlinodeinstance\n        description: Create a Linode\n        call: linode.createlinodeinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances/{linodeId}\n      name: getlinodeinstance\n      operations:\n      - method: GET\n        name: getlinodeinstance\n        description: Get a Linode\n        call: linode.getlinodeinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances/{linodeId}\n      name: updatelinodeinstance\n      operations:\n      - method: PUT\n        name: updatelinodeinstance\n        description: Update a Linode\n        call:\
  \ linode.updatelinodeinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances/{linodeId}\n      name: deletelinodeinstance\n      operations:\n      - method: DELETE\n        name: deletelinodeinstance\n        description: Delete a Linode\n        call: linode.deletelinodeinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances/{linodeId}/boot\n      name: bootlinodeinstance\n      operations:\n      - method: POST\n        name: bootlinodeinstance\n        description: Boot a Linode\n        call: linode.bootlinodeinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances/{linodeId}/reboot\n      name: rebootlinodeinstance\n      operations:\n      - method: POST\n        name: rebootlinodeinstance\n        description: Reboot a Linode\n        call: linode.rebootlinodeinstance\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /linode/instances/{linodeId}/shutdown\n      name: shutdownlinodeinstance\n      operations:\n      - method: POST\n        name: shutdownlinodeinstance\n        description: Shut down a Linode\n        call: linode.shutdownlinodeinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances/{linodeId}/resize\n      name: resizelinodeinstance\n      operations:\n      - method: POST\n        name: resizelinodeinstance\n        description: Resize a Linode\n        call: linode.resizelinodeinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances/{linodeId}/rebuild\n      name: rebuildlinodeinstance\n      operations:\n      - method: POST\n        name: rebuildlinodeinstance\n        description: Rebuild a Linode\n        call: linode.rebuildlinodeinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /linode/instances/{linodeId}/clone\n      name: clonelinodeinstance\n      operations:\n      - method: POST\n        name: clonelinodeinstance\n        description: Clone a Linode\n        call: linode.clonelinodeinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances/{linodeId}/backups\n      name: getbackups\n      operations:\n      - method: GET\n        name: getbackups\n        description: List backups\n        call: linode.getbackups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances/{linodeId}/disks\n      name: getlinodedisks\n      operations:\n      - method: GET\n        name: getlinodedisks\n        description: List disks\n        call: linode.getlinodedisks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances/{linodeId}/configs\n      name: getlinodeconfigs\n      operations:\n      - method: GET\n \
  \       name: getlinodeconfigs\n        description: List configuration profiles\n        call: linode.getlinodeconfigs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/instances/{linodeId}/ips\n      name: getlinodeips\n      operations:\n      - method: GET\n        name: getlinodeips\n        description: Get networking information\n        call: linode.getlinodeips\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/types\n      name: getlinodetypes\n      operations:\n      - method: GET\n        name: getlinodetypes\n        description: List types\n        call: linode.getlinodetypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/kernels\n      name: getkernels\n      operations:\n      - method: GET\n        name: getkernels\n        description: List kernels\n        call: linode.getkernels\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /linode/stackscripts\n      name: getstackscripts\n      operations:\n      - method: GET\n        name: getstackscripts\n        description: List StackScripts\n        call: linode.getstackscripts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/stackscripts\n      name: createstackscript\n      operations:\n      - method: POST\n        name: createstackscript\n        description: Create a StackScript\n        call: linode.createstackscript\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/stackscripts/{stackscriptId}\n      name: getstackscript\n      operations:\n      - method: GET\n        name: getstackscript\n        description: Get a StackScript\n        call: linode.getstackscript\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/stackscripts/{stackscriptId}\n      name: updatestackscript\n      operations:\n\
  \      - method: PUT\n        name: updatestackscript\n        description: Update a StackScript\n        call: linode.updatestackscript\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /linode/stackscripts/{stackscriptId}\n      name: deletestackscript\n      operations:\n      - method: DELETE\n        name: deletestackscript\n        description: Delete a StackScript\n        call: linode.deletestackscript\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lke/clusters\n      name: getlkeclusters\n      operations:\n      - method: GET\n        name: getlkeclusters\n        description: List Kubernetes clusters\n        call: linode.getlkeclusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lke/clusters\n      name: createlkecluster\n      operations:\n      - method: POST\n        name: createlkecluster\n        description: Create a Kubernetes cluster\n        call:\
  \ linode.createlkecluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lke/clusters/{clusterId}\n      name: getlkecluster\n      operations:\n      - method: GET\n        name: getlkecluster\n        description: Get a Kubernetes cluster\n        call: linode.getlkecluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lke/clusters/{clusterId}\n      name: updatelkecluster\n      operations:\n      - method: PUT\n        name: updatelkecluster\n        description: Update a Kubernetes cluster\n        call: linode.updatelkecluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lke/clusters/{clusterId}\n      name: deletelkecluster\n      operations:\n      - method: DELETE\n        name: deletelkecluster\n        description: Delete a Kubernetes cluster\n        call: linode.deletelkecluster\n      \n\n# --- truncated at 32 KB (47 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/linode/refs/heads/main/capabilities/linode-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/linode/refs/heads/main/capabilities/linode-capability.yaml
tags:
- Linode
- API
tools:
- description: Get account info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Update account info
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateaccount
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusers
- description: Create a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Get a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Update a user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Delete a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: List events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevents
- description: Get an event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevent
- description: List invoices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinvoices
- description: List payments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpayments
- description: Make a payment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpayment
- description: List Managed Databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatabaseinstances
- description: List Managed Database engines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatabaseengines
- description: List Managed Database types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatabasetypes
- description: Get a Managed Database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatabaseinstance
- description: Update a Managed Database
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedatabaseinstance
- description: Delete a Managed Database
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatabaseinstance
- description: List domains
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdomains
- description: Create a domain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdomain
- description: Get a domain
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdomain
- description: Update a domain
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedomain
- description: Delete a domain
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedomain
- description: List domain records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdomainrecords
- description: Create a domain record
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdomainrecord
- description: List images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getimages
- description: Create an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createimage
- description: Get an image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getimage
- description: Update an image
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateimage
- description: Delete an image
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteimage
- description: List Linodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlinodeinstances
- description: Create a Linode
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlinodeinstance
- description: Get a Linode
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlinodeinstance
- description: Update a Linode
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelinodeinstance
- description: Delete a Linode
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelinodeinstance
- description: Boot a Linode
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: bootlinodeinstance
- description: Reboot a Linode
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rebootlinodeinstance
- description: Shut down a Linode
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: shutdownlinodeinstance
- description: Resize a Linode
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resizelinodeinstance
- description: Rebuild a Linode
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rebuildlinodeinstance
- description: Clone a Linode
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clonelinodeinstance
- description: List backups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbackups
- description: List disks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlinodedisks
- description: List configuration profiles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlinodeconfigs
- description: Get networking information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlinodeips
- description: List types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlinodetypes
- description: List kernels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getkernels
- description: List StackScripts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstackscripts
- description: Create a StackScript
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createstackscript
- description: Get a StackScript
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstackscript
- description: Update a StackScript
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatestackscript
- description: Delete a StackScript
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletestackscript
- description: List Kubernetes clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlkeclusters
- description: Create a Kubernetes cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlkecluster
- description: Get a Kubernetes cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlkecluster
- description: Update a Kubernetes cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelkecluster
- description: Delete a Kubernetes cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelkecluster
- description: List node pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlkenodepools
- description: Create a node pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlkenodepool
- description: Get kubeconfig
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlkeclusterkubeconfig
---
