---
categories: []
consumed_apis: []
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
- list compute instances in a compartment
- create a custom image from an instance
- update image
- get image
- perform an action on an instance (start, stop, reset)
- list images
- manage a specific image
- create image
- saas
- list available compute shapes
- manage compute images
- get image details
- instance action
- get instance
- delete a custom image
- infrastructure
- list instances
- list shapes
- manage a specific compute instance
- list console connections
- update image details
- terminate instance
- enterprise
- update instance
- get details of a specific image
- list compute images
- database
- cloud
- compute
- list volume attachments in a compartment
- update instance details
- get details of a specific instance
- launch a new compute instance
- get instance details
- delete image
- list vnic attachments
- list instance console connections
- manage compute instances
- launch instance
- create a custom image
- list volume attachments
- terminate an instance
- oracle
- list vnic attachments in a compartment
slug: cloud-compute
source_filename: cloud-compute.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Cloud Compute Management\n  description: Manage Oracle Cloud Infrastructure compute resources including instances, images, shapes, and attachments.\n    Used by cloud engineers and platform administrators.\n  tags:\n  - Oracle\n  - Cloud\n  - Compute\n  - Infrastructure\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    OCI_API_KEY: OCI_API_KEY\n    OCI_TENANCY_OCID: OCI_TENANCY_OCID\n    OCI_USER_OCID: OCI_USER_OCID\n    OCI_FINGERPRINT: OCI_FINGERPRINT\ncapability:\n  consumes:\n  - type: http\n    namespace: oci-compute\n    baseUri: https://iaas.{region}.oraclecloud.com/20160918\n    description: OCI Compute API for managing cloud compute resources\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{OCI_API_KEY}}'\n      placement: header\n    resources:\n    - name: instances\n      path: /instances\n      description: Manage compute instances\n      operations:\n\
  \      - name: list-instances\n        method: GET\n        description: List instances in a compartment\n        inputParameters:\n        - name: compartmentId\n          in: query\n          type: string\n          required: true\n          description: The OCID of the compartment\n        - name: availabilityDomain\n          in: query\n          type: string\n          required: false\n          description: The availability domain name\n        - name: displayName\n          in: query\n          type: string\n          required: false\n          description: Filter by display name\n        - name: lifecycleState\n          in: query\n          type: string\n          required: false\n          description: Filter by lifecycle state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: launch-instance\n        method: POST\n        description: Launch a new compute instance\n        inputParameters:\n\
  \        - name: compartmentId\n          in: query\n          type: string\n          required: true\n          description: The OCID of the compartment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            compartmentId: '{{tools.compartmentId}}'\n            availabilityDomain: '{{tools.availabilityDomain}}'\n            shape: '{{tools.shape}}'\n            displayName: '{{tools.displayName}}'\n    - name: instance\n      path: /instances/{instanceId}\n      description: Manage a specific compute instance\n      operations:\n      - name: get-instance\n        method: GET\n        description: Get details of a specific instance\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the instance\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: update-instance\n        method: PUT\n        description: Update instance details\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n      - name: terminate-instance\n        method: DELETE\n        description: Terminate an instance\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instance-action\n\
  \      path: /instances/{instanceId}\n      description: Perform actions on instances\n      operations:\n      - name: instance-action\n        method: POST\n        description: Perform an action on an instance (start, stop, reset, etc.)\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the instance\n        - name: action\n          in: query\n          type: string\n          required: true\n          description: The action to perform\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shapes\n      path: /shapes\n      description: List available compute shapes\n      operations:\n      - name: list-shapes\n        method: GET\n        description: List available compute shapes in a compartment\n        inputParameters:\n        - name: compartmentId\n          in: query\n          type:\
  \ string\n          required: true\n          description: The OCID of the compartment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images\n      path: /images\n      description: Manage compute images\n      operations:\n      - name: list-images\n        method: GET\n        description: List images in a compartment\n        inputParameters:\n        - name: compartmentId\n          in: query\n          type: string\n          required: true\n          description: The OCID of the compartment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-image\n        method: POST\n        description: Create a custom image from an instance\n        inputParameters:\n        - name: compartmentId\n          in: query\n          type: string\n          required: true\n          description: The OCID of the\
  \ compartment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            compartmentId: '{{tools.compartmentId}}'\n            instanceId: '{{tools.instanceId}}'\n            displayName: '{{tools.displayName}}'\n    - name: image\n      path: /images/{imageId}\n      description: Manage a specific image\n      operations:\n      - name: get-image\n        method: GET\n        description: Get details of a specific image\n        inputParameters:\n        - name: imageId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-image\n        method: PUT\n        description: Update image details\n        inputParameters:\n        - name: imageId\n \
  \         in: path\n          type: string\n          required: true\n          description: The OCID of the image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n      - name: delete-image\n        method: DELETE\n        description: Delete a custom image\n        inputParameters:\n        - name: imageId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vnic-attachments\n      path: /vnicAttachments\n      description: List VNIC attachments\n      operations:\n      - name: list-vnic-attachments\n        method: GET\n        description: List VNIC attachments in a compartment\n        inputParameters:\n\
  \        - name: compartmentId\n          in: query\n          type: string\n          required: true\n          description: The OCID of the compartment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: volume-attachments\n      path: /volumeAttachments\n      description: List volume attachments\n      operations:\n      - name: list-volume-attachments\n        method: GET\n        description: List volume attachments in a compartment\n        inputParameters:\n        - name: compartmentId\n          in: query\n          type: string\n          required: true\n          description: The OCID of the compartment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: console-connections\n      path: /instanceConsoleConnections\n      description: List instance console connections\n      operations:\n      - name:\
  \ list-console-connections\n        method: GET\n        description: List instance console connections in a compartment\n        inputParameters:\n        - name: compartmentId\n          in: query\n          type: string\n          required: true\n          description: The OCID of the compartment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oracle-compute-api\n    description: Unified REST API for Oracle Cloud compute resource management.\n    resources:\n    - path: /v1/instances\n      name: instances\n      description: Manage compute instances\n      operations:\n      - method: GET\n        name: list-instances\n        description: List compute instances in a compartment\n        call: oci-compute.list-instances\n        with:\n          compartmentId: rest.compartmentId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: POST\n        name: launch-instance\n        description: Launch a new compute instance\n        call: oci-compute.launch-instance\n        with:\n          compartmentId: rest.compartmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{instanceId}\n      name: instance\n      description: Manage a specific compute instance\n      operations:\n      - method: GET\n        name: get-instance\n        description: Get instance details\n        call: oci-compute.get-instance\n        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-instance\n        description: Update instance details\n        call: oci-compute.update-instance\n        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: terminate-instance\n\
  \        description: Terminate an instance\n        call: oci-compute.terminate-instance\n        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shapes\n      name: shapes\n      description: List available compute shapes\n      operations:\n      - method: GET\n        name: list-shapes\n        description: List available compute shapes\n        call: oci-compute.list-shapes\n        with:\n          compartmentId: rest.compartmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images\n      name: images\n      description: Manage compute images\n      operations:\n      - method: GET\n        name: list-images\n        description: List compute images\n        call: oci-compute.list-images\n        with:\n          compartmentId: rest.compartmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n    \
  \    name: create-image\n        description: Create a custom image\n        call: oci-compute.create-image\n        with:\n          compartmentId: rest.compartmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images/{imageId}\n      name: image\n      description: Manage a specific image\n      operations:\n      - method: GET\n        name: get-image\n        description: Get image details\n        call: oci-compute.get-image\n        with:\n          imageId: rest.imageId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-image\n        description: Update image details\n        call: oci-compute.update-image\n        with:\n          imageId: rest.imageId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-image\n        description: Delete a custom image\n        call: oci-compute.delete-image\n     \
  \   with:\n          imageId: rest.imageId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oracle-compute-mcp\n    transport: http\n    description: MCP server for AI-assisted Oracle Cloud compute management.\n    tools:\n    - name: list-instances\n      description: List compute instances in a compartment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: oci-compute.list-instances\n      with:\n        compartmentId: tools.compartmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: launch-instance\n      description: Launch a new compute instance\n      hints:\n        readOnly: false\n      call: oci-compute.launch-instance\n      with:\n        compartmentId: tools.compartmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-instance\n      description: Get details of a specific instance\n      hints:\n        readOnly:\
  \ true\n      call: oci-compute.get-instance\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-instance\n      description: Update instance details\n      hints:\n        readOnly: false\n        idempotent: true\n      call: oci-compute.update-instance\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: terminate-instance\n      description: Terminate an instance\n      hints:\n        destructive: true\n        idempotent: true\n      call: oci-compute.terminate-instance\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: instance-action\n      description: Perform an action on an instance (start, stop, reset)\n      hints:\n        readOnly: false\n      call: oci-compute.instance-action\n      with:\n        instanceId: tools.instanceId\n\
  \        action: tools.action\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-shapes\n      description: List available compute shapes\n      hints:\n        readOnly: true\n      call: oci-compute.list-shapes\n      with:\n        compartmentId: tools.compartmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-images\n      description: List compute images\n      hints:\n        readOnly: true\n      call: oci-compute.list-images\n      with:\n        compartmentId: tools.compartmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-image\n      description: Create a custom image from an instance\n      hints:\n        readOnly: false\n      call: oci-compute.create-image\n      with:\n        compartmentId: tools.compartmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-image\n      description: Get details of a specific image\n\
  \      hints:\n        readOnly: true\n      call: oci-compute.get-image\n      with:\n        imageId: tools.imageId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-image\n      description: Update image details\n      hints:\n        readOnly: false\n        idempotent: true\n      call: oci-compute.update-image\n      with:\n        imageId: tools.imageId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-image\n      description: Delete a custom image\n      hints:\n        destructive: true\n        idempotent: true\n      call: oci-compute.delete-image\n      with:\n        imageId: tools.imageId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vnic-attachments\n      description: List VNIC attachments in a compartment\n      hints:\n        readOnly: true\n      call: oci-compute.list-vnic-attachments\n      with:\n        compartmentId: tools.compartmentId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-volume-attachments\n      description: List volume attachments in a compartment\n      hints:\n        readOnly: true\n      call: oci-compute.list-volume-attachments\n      with:\n        compartmentId: tools.compartmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-console-connections\n      description: List instance console connections\n      hints:\n        readOnly: true\n      call: oci-compute.list-console-connections\n      with:\n        compartmentId: tools.compartmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
