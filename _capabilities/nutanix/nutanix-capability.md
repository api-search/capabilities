---
categories: []
consumed_apis: []
description: RESTful API for managing Nutanix clusters, VMs, storage, networking, and other infrastructure components through Prism Central. The v3 API uses an intent-based model where resources are defined by their desired state, and the system works to achieve that state. All list operations use POST with server-side filtering, grouping, and sorting. Authentication is via HTTP Basic Auth with Prism Central credentials.
layout: capability
name: Nutanix Prism Central API v3
operations:
- description: Nutanix List virtual machines
  method: POST
  name: listvms
  path: /vms/list
- description: Nutanix Create a virtual machine
  method: POST
  name: createvm
  path: /vms
- description: Nutanix Get a virtual machine
  method: GET
  name: getvm
  path: /vms/{uuid}
- description: Nutanix Update a virtual machine
  method: PUT
  name: updatevm
  path: /vms/{uuid}
- description: Nutanix Delete a virtual machine
  method: DELETE
  name: deletevm
  path: /vms/{uuid}
- description: Nutanix List clusters
  method: POST
  name: listclusters
  path: /clusters/list
- description: Nutanix Get a cluster
  method: GET
  name: getcluster
  path: /clusters/{uuid}
- description: Nutanix List subnets
  method: POST
  name: listsubnets
  path: /subnets/list
- description: Nutanix Create a subnet
  method: POST
  name: createsubnet
  path: /subnets
- description: Nutanix Get a subnet
  method: GET
  name: getsubnet
  path: /subnets/{uuid}
- description: Nutanix Update a subnet
  method: PUT
  name: updatesubnet
  path: /subnets/{uuid}
- description: Nutanix Delete a subnet
  method: DELETE
  name: deletesubnet
  path: /subnets/{uuid}
- description: Nutanix List images
  method: POST
  name: listimages
  path: /images/list
- description: Nutanix Create an image
  method: POST
  name: createimage
  path: /images
- description: Nutanix Get an image
  method: GET
  name: getimage
  path: /images/{uuid}
- description: Nutanix Delete an image
  method: DELETE
  name: deleteimage
  path: /images/{uuid}
- description: Nutanix Get a category key
  method: GET
  name: getcategory
  path: /categories/{name}
- description: Nutanix Create or update a category key
  method: PUT
  name: updatecategory
  path: /categories/{name}
- description: Nutanix Delete a category key
  method: DELETE
  name: deletecategory
  path: /categories/{name}
- description: Nutanix Create or update a category value
  method: PUT
  name: updatecategoryvalue
  path: /categories/{name}/{value}
- description: Nutanix Delete a category value
  method: DELETE
  name: deletecategoryvalue
  path: /categories/{name}/{value}
- description: Nutanix List projects
  method: POST
  name: listprojects
  path: /projects/list
- description: Nutanix Get a project
  method: GET
  name: getproject
  path: /projects/{uuid}
- description: Nutanix List hosts
  method: POST
  name: listhosts
  path: /hosts/list
- description: Nutanix Get a host
  method: GET
  name: gethost
  path: /hosts/{uuid}
- description: Nutanix List network security rules
  method: POST
  name: listnetworksecurityrules
  path: /network_security_rules/list
- description: Nutanix Create a network security rule
  method: POST
  name: createnetworksecurityrule
  path: /network_security_rules
- description: Nutanix Get a network security rule
  method: GET
  name: getnetworksecurityrule
  path: /network_security_rules/{uuid}
- description: Nutanix Update a network security rule
  method: PUT
  name: updatenetworksecurityrule
  path: /network_security_rules/{uuid}
- description: Nutanix Delete a network security rule
  method: DELETE
  name: deletenetworksecurityrule
  path: /network_security_rules/{uuid}
- description: Nutanix List webhooks
  method: POST
  name: listwebhooks
  path: /webhooks/list
- description: Nutanix Create a webhook
  method: POST
  name: createwebhook
  path: /webhooks
- description: Nutanix Get a webhook
  method: GET
  name: getwebhook
  path: /webhooks/{uuid}
- description: Nutanix Update a webhook
  method: PUT
  name: updatewebhook
  path: /webhooks/{uuid}
- description: Nutanix Delete a webhook
  method: DELETE
  name: deletewebhook
  path: /webhooks/{uuid}
personas: []
provider_name: Nutanix
provider_slug: nutanix
search_terms:
- nutanix get a project
- api
- cloud management
- createimage
- nutanix update a network security rule
- getsubnet
- nutanix update a virtual machine
- getnetworksecurityrule
- updatecategoryvalue
- deleteimage
- nutanix create a network security rule
- listimages
- nutanix delete a subnet
- createnetworksecurityrule
- nutanix get a network security rule
- nutanix get a subnet
- deletecategory
- updatenetworksecurityrule
- nutanix get an image
- createvm
- deletenetworksecurityrule
- listhosts
- gethost
- virtualization
- nutanix delete a virtual machine
- getimage
- nutanix list webhooks
- nutanix get a virtual machine
- nutanix list network security rules
- nutanix create an image
- nutanix list virtual machines
- nutanix list hosts
- listsubnets
- deletecategoryvalue
- getproject
- hyperconverged
- updatevm
- deletesubnet
- updatesubnet
- nutanix list subnets
- nutanix create or update a category key
- nutanix get a host
- updatewebhook
- nutanix update a subnet
- infrastructure
- listnetworksecurityrules
- nutanix create a virtual machine
- listvms
- kubernetes
- nutanix create a subnet
- nutanix create or update a category value
- nutanix delete a category value
- database
- nutanix delete a category key
- nutanix list clusters
- getvm
- getwebhook
- getcluster
- getcategory
- updatecategory
- deletevm
- nutanix get a category key
- createwebhook
- nutanix update a webhook
- listclusters
- nutanix get a cluster
- nutanix get a webhook
- createsubnet
- nutanix create a webhook
- nutanix delete an image
- nutanix list images
- nutanix list projects
- nutanix delete a network security rule
- listwebhooks
- deletewebhook
- listprojects
- nutanix
- nutanix delete a webhook
slug: nutanix-capability
source_filename: nutanix-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Nutanix Prism Central API v3\n  description: RESTful API for managing Nutanix clusters, VMs, storage, networking, and other infrastructure components through\n    Prism Central. The v3 API uses an intent-based model where resources are defined by their desired state, and the system\n    works to achieve that state. All list operations use POST with server-side filtering, grouping, and sorting. Authentication\n    is via HTTP Basic Auth with Prism Central credentials.\n  tags:\n  - Nutanix\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nutanix\n    baseUri: https://localhost:9440/api/nutanix/v3\n    description: Nutanix Prism Central API v3 HTTP API.\n    authentication:\n      type: basic\n      username: '{{NUTANIX_USERNAME}}'\n      password: '{{NUTANIX_PASSWORD}}'\n    resources:\n    - name: vms-list\n      path: /vms/list\n      operations:\n      - name: listvms\n\
  \        method: POST\n        description: Nutanix List virtual machines\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vms\n      path: /vms\n      operations:\n      - name: createvm\n        method: POST\n        description: Nutanix Create a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vms-uuid\n      path: /vms/{uuid}\n      operations:\n      - name: getvm\n        method: GET\n        description: Nutanix Get a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatevm\n        method: PUT\n        description: Nutanix Update a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: deletevm\n        method: DELETE\n        description: Nutanix Delete a virtual machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters-list\n      path: /clusters/list\n      operations:\n      - name: listclusters\n        method: POST\n        description: Nutanix List clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters-uuid\n      path: /clusters/{uuid}\n      operations:\n      - name: getcluster\n        method: GET\n        description: Nutanix Get a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subnets-list\n      path: /subnets/list\n      operations:\n      - name: listsubnets\n        method: POST\n        description: Nutanix List subnets\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subnets\n      path: /subnets\n      operations:\n      - name: createsubnet\n        method: POST\n        description: Nutanix Create a subnet\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subnets-uuid\n      path: /subnets/{uuid}\n      operations:\n      - name: getsubnet\n        method: GET\n        description: Nutanix Get a subnet\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesubnet\n        method: PUT\n        description: Nutanix Update a subnet\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesubnet\n        method: DELETE\n        description: Nutanix Delete a subnet\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-list\n      path: /images/list\n      operations:\n      - name: listimages\n        method: POST\n        description: Nutanix List images\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images\n      path: /images\n      operations:\n      - name: createimage\n        method: POST\n        description: Nutanix Create an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-uuid\n      path: /images/{uuid}\n      operations:\n      - name: getimage\n        method: GET\n        description: Nutanix Get an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteimage\n\
  \        method: DELETE\n        description: Nutanix Delete an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories-name\n      path: /categories/{name}\n      operations:\n      - name: getcategory\n        method: GET\n        description: Nutanix Get a category key\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the category key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecategory\n        method: PUT\n        description: Nutanix Create or update a category key\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the category key.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletecategory\n        method: DELETE\n        description: Nutanix Delete a category key\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the category key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories-name-value\n      path: /categories/{name}/{value}\n      operations:\n      - name: updatecategoryvalue\n        method: PUT\n        description: Nutanix Create or update a category value\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the category key.\n        - name: value\n          in: path\n          type: string\n          required: true\n          description: The category value.\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecategoryvalue\n        method: DELETE\n        description: Nutanix Delete a category value\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the category key.\n        - name: value\n          in: path\n          type: string\n          required: true\n          description: The category value.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-list\n      path: /projects/list\n      operations:\n      - name: listprojects\n        method: POST\n        description: Nutanix List projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-uuid\n \
  \     path: /projects/{uuid}\n      operations:\n      - name: getproject\n        method: GET\n        description: Nutanix Get a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hosts-list\n      path: /hosts/list\n      operations:\n      - name: listhosts\n        method: POST\n        description: Nutanix List hosts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hosts-uuid\n      path: /hosts/{uuid}\n      operations:\n      - name: gethost\n        method: GET\n        description: Nutanix Get a host\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: network-security-rules-list\n      path: /network_security_rules/list\n      operations:\n      - name: listnetworksecurityrules\n        method: POST\n   \
  \     description: Nutanix List network security rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: network-security-rules\n      path: /network_security_rules\n      operations:\n      - name: createnetworksecurityrule\n        method: POST\n        description: Nutanix Create a network security rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: network-security-rules-uuid\n      path: /network_security_rules/{uuid}\n      operations:\n      - name: getnetworksecurityrule\n        method: GET\n        description: Nutanix Get a network security rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatenetworksecurityrule\n        method: PUT\n        description: Nutanix Update a network security rule\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenetworksecurityrule\n        method: DELETE\n        description: Nutanix Delete a network security rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-list\n      path: /webhooks/list\n      operations:\n      - name: listwebhooks\n        method: POST\n        description: Nutanix List webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n      operations:\n      - name: createwebhook\n        method: POST\n        description: Nutanix Create a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-uuid\n      path:\
  \ /webhooks/{uuid}\n      operations:\n      - name: getwebhook\n        method: GET\n        description: Nutanix Get a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatewebhook\n        method: PUT\n        description: Nutanix Update a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletewebhook\n        method: DELETE\n        description: Nutanix Delete a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nutanix-rest\n    description: REST adapter for Nutanix Prism Central API v3.\n    resources:\n    - path: /vms/list\n      name: listvms\n      operations:\n      - method: POST\n        name: listvms\n        description: Nutanix List\
  \ virtual machines\n        call: nutanix.listvms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vms\n      name: createvm\n      operations:\n      - method: POST\n        name: createvm\n        description: Nutanix Create a virtual machine\n        call: nutanix.createvm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vms/{uuid}\n      name: getvm\n      operations:\n      - method: GET\n        name: getvm\n        description: Nutanix Get a virtual machine\n        call: nutanix.getvm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vms/{uuid}\n      name: updatevm\n      operations:\n      - method: PUT\n        name: updatevm\n        description: Nutanix Update a virtual machine\n        call: nutanix.updatevm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vms/{uuid}\n      name: deletevm\n      operations:\n      - method:\
  \ DELETE\n        name: deletevm\n        description: Nutanix Delete a virtual machine\n        call: nutanix.deletevm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/list\n      name: listclusters\n      operations:\n      - method: POST\n        name: listclusters\n        description: Nutanix List clusters\n        call: nutanix.listclusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{uuid}\n      name: getcluster\n      operations:\n      - method: GET\n        name: getcluster\n        description: Nutanix Get a cluster\n        call: nutanix.getcluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subnets/list\n      name: listsubnets\n      operations:\n      - method: POST\n        name: listsubnets\n        description: Nutanix List subnets\n        call: nutanix.listsubnets\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n    - path: /subnets\n      name: createsubnet\n      operations:\n      - method: POST\n        name: createsubnet\n        description: Nutanix Create a subnet\n        call: nutanix.createsubnet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subnets/{uuid}\n      name: getsubnet\n      operations:\n      - method: GET\n        name: getsubnet\n        description: Nutanix Get a subnet\n        call: nutanix.getsubnet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subnets/{uuid}\n      name: updatesubnet\n      operations:\n      - method: PUT\n        name: updatesubnet\n        description: Nutanix Update a subnet\n        call: nutanix.updatesubnet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subnets/{uuid}\n      name: deletesubnet\n      operations:\n      - method: DELETE\n        name: deletesubnet\n        description: Nutanix Delete a\
  \ subnet\n        call: nutanix.deletesubnet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images/list\n      name: listimages\n      operations:\n      - method: POST\n        name: listimages\n        description: Nutanix List images\n        call: nutanix.listimages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images\n      name: createimage\n      operations:\n      - method: POST\n        name: createimage\n        description: Nutanix Create an image\n        call: nutanix.createimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images/{uuid}\n      name: getimage\n      operations:\n      - method: GET\n        name: getimage\n        description: Nutanix Get an image\n        call: nutanix.getimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images/{uuid}\n      name: deleteimage\n      operations:\n      - method:\
  \ DELETE\n        name: deleteimage\n        description: Nutanix Delete an image\n        call: nutanix.deleteimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories/{name}\n      name: getcategory\n      operations:\n      - method: GET\n        name: getcategory\n        description: Nutanix Get a category key\n        call: nutanix.getcategory\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories/{name}\n      name: updatecategory\n      operations:\n      - method: PUT\n        name: updatecategory\n        description: Nutanix Create or update a category key\n        call: nutanix.updatecategory\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories/{name}\n      name: deletecategory\n      operations:\n      - method: DELETE\n        name: deletecategory\n    \
  \    description: Nutanix Delete a category key\n        call: nutanix.deletecategory\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories/{name}/{value}\n      name: updatecategoryvalue\n      operations:\n      - method: PUT\n        name: updatecategoryvalue\n        description: Nutanix Create or update a category value\n        call: nutanix.updatecategoryvalue\n        with:\n          name: rest.name\n          value: rest.value\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories/{name}/{value}\n      name: deletecategoryvalue\n      operations:\n      - method: DELETE\n        name: deletecategoryvalue\n        description: Nutanix Delete a category value\n        call: nutanix.deletecategoryvalue\n        with:\n          name: rest.name\n          value: rest.value\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \ - path: /projects/list\n      name: listprojects\n      operations:\n      - method: POST\n        name: listprojects\n        description: Nutanix List projects\n        call: nutanix.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{uuid}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Nutanix Get a project\n        call: nutanix.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hosts/list\n      name: listhosts\n      operations:\n      - method: POST\n        name: listhosts\n        description: Nutanix List hosts\n        call: nutanix.listhosts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hosts/{uuid}\n      name: gethost\n      operations:\n      - method: GET\n        name: gethost\n        description: Nutanix Get a host\n        call: nutanix.gethost\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /network_security_rules/list\n      name: listnetworksecurityrules\n      operations:\n      - method: POST\n        name: listnetworksecurityrules\n        description: Nutanix List network security rules\n        call: nutanix.listnetworksecurityrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /network_security_rules\n      name: createnetworksecurityrule\n      operations:\n      - method: POST\n        name: createnetworksecurityrule\n        description: Nutanix Create a network security rule\n        call: nutanix.createnetworksecurityrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /network_security_rules/{uuid}\n      name: getnetworksecurityrule\n      operations:\n      - method: GET\n        name: getnetworksecurityrule\n        description: Nutanix Get a network security rule\n        call: nutanix.getnetworksecurityrule\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /network_security_rules/{uuid}\n      name: updatenetworksecurityrule\n      operations:\n      - method: PUT\n        name: updatenetworksecurityrule\n        description: Nutanix Update a network security rule\n        call: nutanix.updatenetworksecurityrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /network_security_rules/{uuid}\n      name: deletenetworksecurityrule\n      operations:\n      - method: DELETE\n        name: deletenetworksecurityrule\n        description: Nutanix Delete a network security rule\n        call: nutanix.deletenetworksecurityrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/list\n      name: listwebhooks\n      operations:\n      - method: POST\n        name: listwebhooks\n        description: Nutanix List webhooks\n        call: nutanix.listwebhooks\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /webhooks\n      name: createwebhook\n      operations:\n      - method: POST\n        name: createwebhook\n        description: Nutanix Create a webhook\n        call: nutanix.createwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{uuid}\n      name: getwebhook\n      operations:\n      - method: GET\n        name: getwebhook\n        description: Nutanix Get a webhook\n        call: nutanix.getwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{uuid}\n      name: updatewebhook\n      operations:\n      - method: PUT\n        name: updatewebhook\n        description: Nutanix Update a webhook\n        call: nutanix.updatewebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{uuid}\n      name: deletewebhook\n      operations:\n      - method: DELETE\n        name: deletewebhook\n\
  \        description: Nutanix Delete a webhook\n        call: nutanix.deletewebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nutanix-mcp\n    transport: http\n    description: MCP adapter for Nutanix Prism Central API v3 for AI agent use.\n    tools:\n    - name: listvms\n      description: Nutanix List virtual machines\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.listvms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createvm\n      description: Nutanix Create a virtual machine\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.createvm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvm\n      description: Nutanix Get a virtual machine\n      hints:\n        readOnly: true\n        destructive: false\n   \
  \     idempotent: true\n      call: nutanix.getvm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatevm\n      description: Nutanix Update a virtual machine\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nutanix.updatevm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletevm\n      description: Nutanix Delete a virtual machine\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nutanix.deletevm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclusters\n      description: Nutanix List clusters\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.listclusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcluster\n      description: Nutanix Get a cluster\n      hints:\n     \
  \   readOnly: true\n        destructive: false\n        idempotent: true\n      call: nutanix.getcluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsubnets\n      description: Nutanix List subnets\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.listsubnets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsubnet\n      description: Nutanix Create a subnet\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.createsubnet\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubnet\n      description: Nutanix Get a subnet\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nutanix.getsubnet\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesubnet\n      description:\
  \ Nutanix Update a subnet\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nutanix.updatesubnet\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesubnet\n      description: Nutanix Delete a subnet\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nutanix.deletesubnet\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listimages\n      description: Nutanix List images\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.listimages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createimage\n      description: Nutanix Create an image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.createimage\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getimage\n      description: Nutanix Get an image\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nutanix.getimage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteimage\n      description: Nutanix Delete an image\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nutanix.deleteimage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategory\n      description: Nutanix Get a category key\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nutanix.getcategory\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: The name of the category key.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecategory\n    \
  \  description: Nutanix Create or update a category key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nutanix.updatecategory\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: The name of the category key.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecategory\n      description: Nutanix Delete a category key\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nutanix.deletecategory\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: The name of the category key.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecategoryvalue\n      description: Nutanix Create or update a category value\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nutanix.updatecategoryvalue\n      with:\n        name: tools.name\n        value: tools.value\n      inputParameters:\n      - name: name\n        type: string\n        description: The name of the category key.\n        required: true\n      - name: value\n        type: string\n        description: The category value.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecategoryvalue\n      description: Nutanix Delete a category value\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nutanix.deletecategoryvalue\n      with:\n        name: tools.name\n        value: tools.value\n      inputParameters:\n      - name: name\n        type: string\n        description: The name of the category key.\n        required: true\n      - name: value\n        type: string\n        description: The\
  \ category value.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojects\n      description: Nutanix List projects\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.listprojects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Nutanix Get a project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nutanix.getproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listhosts\n      description: Nutanix List hosts\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.listhosts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethost\n      description: Nutanix Get a host\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: nutanix.gethost\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnetworksecurityrules\n      description: Nutanix List network security rules\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.listnetworksecurityrules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnetworksecurityrule\n      description: Nutanix Create a network security rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.createnetworksecurityrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnetworksecurityrule\n      description: Nutanix Get a network security rule\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nutanix.getnetworksecurityrule\n      outputParameters:\n     \
  \ - type: object\n        mapping: $.\n    - name: updatenetworksecurityrule\n      description: Nutanix Update a network security rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nutanix.updatenetworksecurityrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenetworksecurityrule\n      description: Nutanix Delete a network security rule\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nutanix.deletenetworksecurityrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listwebhooks\n      description: Nutanix List webhooks\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.listwebhooks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createwebhook\n      description: Nutanix Create a webhook\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nutanix.createwebhook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getwebhook\n      description: Nutanix Get a webhook\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nutanix.getwebhook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatewebhook\n      description: Nutanix Update a webhook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nutanix.updatewebhook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletewebhook\n      description: Nutanix Delete a webhook\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nutanix.deletewebhook\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n\
  \  keys:\n    NUTANIX_USERNAME: NUTANIX_USERNAME\n    NUTANIX_PASSWORD: NUTANIX_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nutanix/refs/heads/main/capabilities/nutanix-capability.yaml
tags:
- Nutanix
- API
tools:
- description: Nutanix List virtual machines
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listvms
- description: Nutanix Create a virtual machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvm
- description: Nutanix Get a virtual machine
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvm
- description: Nutanix Update a virtual machine
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatevm
- description: Nutanix Delete a virtual machine
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletevm
- description: Nutanix List clusters
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listclusters
- description: Nutanix Get a cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcluster
- description: Nutanix List subnets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listsubnets
- description: Nutanix Create a subnet
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubnet
- description: Nutanix Get a subnet
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubnet
- description: Nutanix Update a subnet
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesubnet
- description: Nutanix Delete a subnet
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesubnet
- description: Nutanix List images
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listimages
- description: Nutanix Create an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createimage
- description: Nutanix Get an image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getimage
- description: Nutanix Delete an image
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteimage
- description: Nutanix Get a category key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategory
- description: Nutanix Create or update a category key
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecategory
- description: Nutanix Delete a category key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecategory
- description: Nutanix Create or update a category value
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecategoryvalue
- description: Nutanix Delete a category value
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecategoryvalue
- description: Nutanix List projects
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listprojects
- description: Nutanix Get a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Nutanix List hosts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listhosts
- description: Nutanix Get a host
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethost
- description: Nutanix List network security rules
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listnetworksecurityrules
- description: Nutanix Create a network security rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnetworksecurityrule
- description: Nutanix Get a network security rule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnetworksecurityrule
- description: Nutanix Update a network security rule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatenetworksecurityrule
- description: Nutanix Delete a network security rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenetworksecurityrule
- description: Nutanix List webhooks
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listwebhooks
- description: Nutanix Create a webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createwebhook
- description: Nutanix Get a webhook
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwebhook
- description: Nutanix Update a webhook
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatewebhook
- description: Nutanix Delete a webhook
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletewebhook
---
