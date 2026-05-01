---
categories: []
consumed_apis:
- oci-compute
description: Manage Oracle Cloud Infrastructure compute resources including instances, images, shapes, and attachments. Used by cloud engineers and platform administrators.
layout: capability
name: Oracle Cloud Compute Management
operations:
- description: List compute instances in a compartment
  method: GET
  name: list-instances
  path: /v1/instances
- description: Launch a new compute instance
  method: POST
  name: launch-instance
  path: /v1/instances
- description: Get instance details
  method: GET
  name: get-instance
  path: /v1/instances/{instanceId}
- description: Update instance details
  method: PUT
  name: update-instance
  path: /v1/instances/{instanceId}
- description: Terminate an instance
  method: DELETE
  name: terminate-instance
  path: /v1/instances/{instanceId}
- description: List available compute shapes
  method: GET
  name: list-shapes
  path: /v1/shapes
- description: List compute images
  method: GET
  name: list-images
  path: /v1/images
- description: Create a custom image
  method: POST
  name: create-image
  path: /v1/images
- description: Get image details
  method: GET
  name: get-image
  path: /v1/images/{imageId}
- description: Update image details
  method: PUT
  name: update-image
  path: /v1/images/{imageId}
- description: Delete a custom image
  method: DELETE
  name: delete-image
  path: /v1/images/{imageId}
personas: []
provider_name: Oracle
provider_slug: oracle
search_terms:
- saas
- list available compute shapes
- update instance details
- update image details
- list instances
- list images
- create a custom image
- launch instance
- list instance console connections
- get details of a specific instance
- list vnic attachments
- compute
- create a custom image from an instance
- manage compute instances
- list compute instances in a compartment
- launch a new compute instance
- get instance details
- manage a specific image
- list volume attachments
- delete a custom image
- terminate instance
- instance action
- update instance
- terminate an instance
- database
- perform an action on an instance (start, stop, reset)
- infrastructure
- list console connections
- enterprise
- manage a specific compute instance
- manage compute images
- get image details
- oracle
- update image
- create image
- list volume attachments in a compartment
- list shapes
- cloud
- list vnic attachments in a compartment
- get image
- get instance
- list compute images
- delete image
- get details of a specific image
slug: cloud-compute
source_filename: cloud-compute.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Oracle Cloud Compute Management\"\n  description: \"Manage Oracle Cloud Infrastructure compute resources including instances, images, shapes, and attachments. Used by cloud engineers and platform administrators.\"\n  tags:\n    - Oracle\n    - Cloud\n    - Compute\n    - Infrastructure\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      OCI_API_KEY: OCI_API_KEY\n      OCI_TENANCY_OCID: OCI_TENANCY_OCID\n      OCI_USER_OCID: OCI_USER_OCID\n      OCI_FINGERPRINT: OCI_FINGERPRINT\n\ncapability:\n  consumes:\n    - import: oci-compute\n      location: ./shared/oci-compute.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: oracle-compute-api\n      description: \"Unified REST API for Oracle Cloud compute resource management.\"\n      resources:\n        - path: /v1/instances\n          name: instances\n          description: \"Manage compute instances\"\n     \
  \     operations:\n            - method: GET\n              name: list-instances\n              description: \"List compute instances in a compartment\"\n              call: \"oci-compute.list-instances\"\n              with:\n                compartmentId: \"rest.compartmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: launch-instance\n              description: \"Launch a new compute instance\"\n              call: \"oci-compute.launch-instance\"\n              with:\n                compartmentId: \"rest.compartmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/instances/{instanceId}\n          name: instance\n          description: \"Manage a specific compute instance\"\n          operations:\n            - method: GET\n              name: get-instance\n              description: \"Get instance details\"\
  \n              call: \"oci-compute.get-instance\"\n              with:\n                instanceId: \"rest.instanceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-instance\n              description: \"Update instance details\"\n              call: \"oci-compute.update-instance\"\n              with:\n                instanceId: \"rest.instanceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: terminate-instance\n              description: \"Terminate an instance\"\n              call: \"oci-compute.terminate-instance\"\n              with:\n                instanceId: \"rest.instanceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/shapes\n          name: shapes\n          description: \"List available\
  \ compute shapes\"\n          operations:\n            - method: GET\n              name: list-shapes\n              description: \"List available compute shapes\"\n              call: \"oci-compute.list-shapes\"\n              with:\n                compartmentId: \"rest.compartmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/images\n          name: images\n          description: \"Manage compute images\"\n          operations:\n            - method: GET\n              name: list-images\n              description: \"List compute images\"\n              call: \"oci-compute.list-images\"\n              with:\n                compartmentId: \"rest.compartmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-image\n              description: \"Create a custom image\"\n              call: \"oci-compute.create-image\"\
  \n              with:\n                compartmentId: \"rest.compartmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/images/{imageId}\n          name: image\n          description: \"Manage a specific image\"\n          operations:\n            - method: GET\n              name: get-image\n              description: \"Get image details\"\n              call: \"oci-compute.get-image\"\n              with:\n                imageId: \"rest.imageId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-image\n              description: \"Update image details\"\n              call: \"oci-compute.update-image\"\n              with:\n                imageId: \"rest.imageId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n        \
  \      name: delete-image\n              description: \"Delete a custom image\"\n              call: \"oci-compute.delete-image\"\n              with:\n                imageId: \"rest.imageId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: oracle-compute-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Oracle Cloud compute management.\"\n      tools:\n        - name: list-instances\n          description: \"List compute instances in a compartment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"oci-compute.list-instances\"\n          with:\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: launch-instance\n          description: \"Launch a new compute instance\"\n          hints:\n            readOnly:\
  \ false\n          call: \"oci-compute.launch-instance\"\n          with:\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-instance\n          description: \"Get details of a specific instance\"\n          hints:\n            readOnly: true\n          call: \"oci-compute.get-instance\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-instance\n          description: \"Update instance details\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"oci-compute.update-instance\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: terminate-instance\n          description: \"Terminate an instance\"\n\
  \          hints:\n            destructive: true\n            idempotent: true\n          call: \"oci-compute.terminate-instance\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: instance-action\n          description: \"Perform an action on an instance (start, stop, reset)\"\n          hints:\n            readOnly: false\n          call: \"oci-compute.instance-action\"\n          with:\n            instanceId: \"tools.instanceId\"\n            action: \"tools.action\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-shapes\n          description: \"List available compute shapes\"\n          hints:\n            readOnly: true\n          call: \"oci-compute.list-shapes\"\n          with:\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n            - type: object\n            \
  \  mapping: \"$.\"\n        - name: list-images\n          description: \"List compute images\"\n          hints:\n            readOnly: true\n          call: \"oci-compute.list-images\"\n          with:\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-image\n          description: \"Create a custom image from an instance\"\n          hints:\n            readOnly: false\n          call: \"oci-compute.create-image\"\n          with:\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-image\n          description: \"Get details of a specific image\"\n          hints:\n            readOnly: true\n          call: \"oci-compute.get-image\"\n          with:\n            imageId: \"tools.imageId\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: update-image\n          description: \"Update image details\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"oci-compute.update-image\"\n          with:\n            imageId: \"tools.imageId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-image\n          description: \"Delete a custom image\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"oci-compute.delete-image\"\n          with:\n            imageId: \"tools.imageId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-vnic-attachments\n          description: \"List VNIC attachments in a compartment\"\n          hints:\n            readOnly: true\n          call: \"oci-compute.list-vnic-attachments\"\n          with:\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-volume-attachments\n          description: \"List volume attachments in a compartment\"\n          hints:\n            readOnly: true\n          call: \"oci-compute.list-volume-attachments\"\n          with:\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-console-connections\n          description: \"List instance console connections\"\n          hints:\n            readOnly: true\n          call: \"oci-compute.list-console-connections\"\n          with:\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle/refs/heads/main/capabilities/cloud-compute.yaml
tags:
- Oracle
- Cloud
- Compute
- Infrastructure
tools:
- description: List compute instances in a compartment
  hints:
    openWorld: true
    readOnly: true
  name: list-instances
- description: Launch a new compute instance
  hints:
    readOnly: false
  name: launch-instance
- description: Get details of a specific instance
  hints:
    readOnly: true
  name: get-instance
- description: Update instance details
  hints:
    idempotent: true
    readOnly: false
  name: update-instance
- description: Terminate an instance
  hints:
    destructive: true
    idempotent: true
  name: terminate-instance
- description: Perform an action on an instance (start, stop, reset)
  hints:
    readOnly: false
  name: instance-action
- description: List available compute shapes
  hints:
    readOnly: true
  name: list-shapes
- description: List compute images
  hints:
    readOnly: true
  name: list-images
- description: Create a custom image from an instance
  hints:
    readOnly: false
  name: create-image
- description: Get details of a specific image
  hints:
    readOnly: true
  name: get-image
- description: Update image details
  hints:
    idempotent: true
    readOnly: false
  name: update-image
- description: Delete a custom image
  hints:
    destructive: true
    idempotent: true
  name: delete-image
- description: List VNIC attachments in a compartment
  hints:
    readOnly: true
  name: list-vnic-attachments
- description: List volume attachments in a compartment
  hints:
    readOnly: true
  name: list-volume-attachments
- description: List instance console connections
  hints:
    readOnly: true
  name: list-console-connections
---
