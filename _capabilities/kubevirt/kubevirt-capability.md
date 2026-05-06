---
categories: []
consumed_apis: []
description: The KubeVirt Containerized Data Importer (CDI) API provides Kubernetes CRD endpoints for managing virtual machine disk image import and cloning pipelines. CDI introduces DataVolume, DataSource, and StorageProfile resources that automate importing VM disk images from HTTP, S3, OCI registries, and other sources into PersistentVolumeClaims ready for use as KubeVirt VM disks.
layout: capability
name: KubeVirt Containerized Data Importer API
operations:
- description: KubeVirt List DataVolumes in a namespace
  method: GET
  name: listnamespaceddatavolume
  path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datavolumes
- description: KubeVirt Create a DataVolume
  method: POST
  name: createnamespaceddatavolume
  path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datavolumes
- description: KubeVirt Get a DataVolume
  method: GET
  name: readnamespaceddatavolume
  path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datavolumes/{name}
- description: KubeVirt Replace a DataVolume
  method: PUT
  name: replacenamespaceddatavolume
  path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datavolumes/{name}
- description: KubeVirt Delete a DataVolume
  method: DELETE
  name: deletenamespaceddatavolume
  path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datavolumes/{name}
- description: KubeVirt List DataSources in a namespace
  method: GET
  name: listnamespaceddatasource
  path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datasources
- description: KubeVirt Create a DataSource
  method: POST
  name: createnamespaceddatasource
  path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datasources
- description: KubeVirt Get a DataSource
  method: GET
  name: readnamespaceddatasource
  path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datasources/{name}
- description: KubeVirt Delete a DataSource
  method: DELETE
  name: deletenamespaceddatasource
  path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datasources/{name}
- description: KubeVirt List StorageProfiles
  method: GET
  name: liststorageprofiles
  path: /apis/cdi.kubevirt.io/v1beta1/storageprofiles
- description: KubeVirt Get a StorageProfile
  method: GET
  name: readstorageprofile
  path: /apis/cdi.kubevirt.io/v1beta1/storageprofiles/{name}
- description: KubeVirt Update a StorageProfile
  method: PATCH
  name: patchstorageprofile
  path: /apis/cdi.kubevirt.io/v1beta1/storageprofiles/{name}
personas: []
provider_name: KubeVirt
provider_slug: kubevirt
search_terms:
- kubevirt list datasources in a namespace
- patchstorageprofile
- incubating
- createnamespaceddatavolume
- deletenamespaceddatavolume
- kubevirt update a storageprofile
- kubevirt get a storageprofile
- kubevirt list storageprofiles
- virtual machines
- virtualization
- kubevirt delete a datavolume
- kubevirt get a datasource
- kubevirt create a datasource
- cloud native
- kubevirt list datavolumes in a namespace
- kubernetes
- kubevirt delete a datasource
- listnamespaceddatavolume
- readstorageprofile
- api
- readnamespaceddatavolume
- kubevirt replace a datavolume
- readnamespaceddatasource
- liststorageprofiles
- replacenamespaceddatavolume
- migration
- kubevirt
- createnamespaceddatasource
- kubevirt create a datavolume
- kubevirt get a datavolume
- listnamespaceddatasource
- deletenamespaceddatasource
slug: kubevirt-capability
source_filename: kubevirt-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: KubeVirt Containerized Data Importer API\n  description: The KubeVirt Containerized Data Importer (CDI) API provides Kubernetes CRD endpoints for managing virtual machine\n    disk image import and cloning pipelines. CDI introduces DataVolume, DataSource, and StorageProfile resources that automate\n    importing VM disk images from HTTP, S3, OCI registries, and other sources into PersistentVolumeClaims ready for use as\n    KubeVirt VM disks.\n  tags:\n  - Kubevirt\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: kubevirt\n    baseUri: https://localhost:6443\n    description: KubeVirt Containerized Data Importer API HTTP API.\n    resources:\n    - name: apis-cdi-kubevirt-io-v1beta1-namespaces-namespac\n      path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datavolumes\n      operations:\n      - name: listnamespaceddatavolume\n        method: GET\n        description:\
  \ KubeVirt List DataVolumes in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespaceddatavolume\n        method: POST\n        description: KubeVirt Create a DataVolume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-cdi-kubevirt-io-v1beta1-namespaces-namespac\n      path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datavolumes/{name}\n      operations:\n      - name: readnamespaceddatavolume\n        method: GET\n        description: KubeVirt Get a DataVolume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacenamespaceddatavolume\n        method: PUT\n        description: KubeVirt Replace a DataVolume\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: deletenamespaceddatavolume\n        method: DELETE\n        description: KubeVirt Delete a DataVolume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-cdi-kubevirt-io-v1beta1-namespaces-namespac\n      path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datasources\n      operations:\n      - name: listnamespaceddatasource\n        method: GET\n        description: KubeVirt List DataSources in a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespaceddatasource\n        method: POST\n        description: KubeVirt Create a DataSource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-cdi-kubevirt-io-v1beta1-namespaces-namespac\n\
  \      path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datasources/{name}\n      operations:\n      - name: readnamespaceddatasource\n        method: GET\n        description: KubeVirt Get a DataSource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenamespaceddatasource\n        method: DELETE\n        description: KubeVirt Delete a DataSource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-cdi-kubevirt-io-v1beta1-storageprofiles\n      path: /apis/cdi.kubevirt.io/v1beta1/storageprofiles\n      operations:\n      - name: liststorageprofiles\n        method: GET\n        description: KubeVirt List StorageProfiles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-cdi-kubevirt-io-v1beta1-storageprofiles-nam\n\
  \      path: /apis/cdi.kubevirt.io/v1beta1/storageprofiles/{name}\n      operations:\n      - name: readstorageprofile\n        method: GET\n        description: KubeVirt Get a StorageProfile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchstorageprofile\n        method: PATCH\n        description: KubeVirt Update a StorageProfile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kubevirt-rest\n    description: REST adapter for KubeVirt Containerized Data Importer API.\n    resources:\n    - path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datavolumes\n      name: listnamespaceddatavolume\n      operations:\n      - method: GET\n        name: listnamespaceddatavolume\n        description: KubeVirt List DataVolumes in a namespace\n        call:\
  \ kubevirt.listnamespaceddatavolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datavolumes\n      name: createnamespaceddatavolume\n      operations:\n      - method: POST\n        name: createnamespaceddatavolume\n        description: KubeVirt Create a DataVolume\n        call: kubevirt.createnamespaceddatavolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datavolumes/{name}\n      name: readnamespaceddatavolume\n      operations:\n      - method: GET\n        name: readnamespaceddatavolume\n        description: KubeVirt Get a DataVolume\n        call: kubevirt.readnamespaceddatavolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datavolumes/{name}\n      name: replacenamespaceddatavolume\n      operations:\n\
  \      - method: PUT\n        name: replacenamespaceddatavolume\n        description: KubeVirt Replace a DataVolume\n        call: kubevirt.replacenamespaceddatavolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datavolumes/{name}\n      name: deletenamespaceddatavolume\n      operations:\n      - method: DELETE\n        name: deletenamespaceddatavolume\n        description: KubeVirt Delete a DataVolume\n        call: kubevirt.deletenamespaceddatavolume\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datasources\n      name: listnamespaceddatasource\n      operations:\n      - method: GET\n        name: listnamespaceddatasource\n        description: KubeVirt List DataSources in a namespace\n        call: kubevirt.listnamespaceddatasource\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datasources\n      name: createnamespaceddatasource\n      operations:\n      - method: POST\n        name: createnamespaceddatasource\n        description: KubeVirt Create a DataSource\n        call: kubevirt.createnamespaceddatasource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datasources/{name}\n      name: readnamespaceddatasource\n      operations:\n      - method: GET\n        name: readnamespaceddatasource\n        description: KubeVirt Get a DataSource\n        call: kubevirt.readnamespaceddatasource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/cdi.kubevirt.io/v1beta1/namespaces/{namespace}/datasources/{name}\n      name: deletenamespaceddatasource\n      operations:\n      - method: DELETE\n        name: deletenamespaceddatasource\n        description: KubeVirt Delete\
  \ a DataSource\n        call: kubevirt.deletenamespaceddatasource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/cdi.kubevirt.io/v1beta1/storageprofiles\n      name: liststorageprofiles\n      operations:\n      - method: GET\n        name: liststorageprofiles\n        description: KubeVirt List StorageProfiles\n        call: kubevirt.liststorageprofiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/cdi.kubevirt.io/v1beta1/storageprofiles/{name}\n      name: readstorageprofile\n      operations:\n      - method: GET\n        name: readstorageprofile\n        description: KubeVirt Get a StorageProfile\n        call: kubevirt.readstorageprofile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/cdi.kubevirt.io/v1beta1/storageprofiles/{name}\n      name: patchstorageprofile\n      operations:\n      - method: PATCH\n        name: patchstorageprofile\n    \
  \    description: KubeVirt Update a StorageProfile\n        call: kubevirt.patchstorageprofile\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: kubevirt-mcp\n    transport: http\n    description: MCP adapter for KubeVirt Containerized Data Importer API for AI agent use.\n    tools:\n    - name: listnamespaceddatavolume\n      description: KubeVirt List DataVolumes in a namespace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubevirt.listnamespaceddatavolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespaceddatavolume\n      description: KubeVirt Create a DataVolume\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kubevirt.createnamespaceddatavolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readnamespaceddatavolume\n\
  \      description: KubeVirt Get a DataVolume\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubevirt.readnamespaceddatavolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacenamespaceddatavolume\n      description: KubeVirt Replace a DataVolume\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kubevirt.replacenamespaceddatavolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespaceddatavolume\n      description: KubeVirt Delete a DataVolume\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kubevirt.deletenamespaceddatavolume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespaceddatasource\n      description: KubeVirt List DataSources in a namespace\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: kubevirt.listnamespaceddatasource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespaceddatasource\n      description: KubeVirt Create a DataSource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kubevirt.createnamespaceddatasource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readnamespaceddatasource\n      description: KubeVirt Get a DataSource\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubevirt.readnamespaceddatasource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespaceddatasource\n      description: KubeVirt Delete a DataSource\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kubevirt.deletenamespaceddatasource\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: liststorageprofiles\n      description: KubeVirt List StorageProfiles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubevirt.liststorageprofiles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readstorageprofile\n      description: KubeVirt Get a StorageProfile\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubevirt.readstorageprofile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchstorageprofile\n      description: KubeVirt Update a StorageProfile\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kubevirt.patchstorageprofile\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/kubevirt/refs/heads/main/capabilities/kubevirt-capability.yaml
tags:
- Kubevirt
- API
tools:
- description: KubeVirt List DataVolumes in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespaceddatavolume
- description: KubeVirt Create a DataVolume
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespaceddatavolume
- description: KubeVirt Get a DataVolume
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readnamespaceddatavolume
- description: KubeVirt Replace a DataVolume
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacenamespaceddatavolume
- description: KubeVirt Delete a DataVolume
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespaceddatavolume
- description: KubeVirt List DataSources in a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespaceddatasource
- description: KubeVirt Create a DataSource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespaceddatasource
- description: KubeVirt Get a DataSource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readnamespaceddatasource
- description: KubeVirt Delete a DataSource
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespaceddatasource
- description: KubeVirt List StorageProfiles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststorageprofiles
- description: KubeVirt Get a StorageProfile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readstorageprofile
- description: KubeVirt Update a StorageProfile
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchstorageprofile
---
