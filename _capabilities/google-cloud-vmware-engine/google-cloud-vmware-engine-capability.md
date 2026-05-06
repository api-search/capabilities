---
categories: []
consumed_apis: []
description: Programmatically manages VMware private clouds, clusters, and network resources on Google Cloud.
layout: capability
name: Google Cloud VMware Engine API
operations:
- description: Google Cloud VMware Engine List Private Clouds
  method: GET
  name: listprivateclouds
  path: /projects/{project}/locations/{location}/privateClouds
- description: Google Cloud VMware Engine Create Private Cloud
  method: POST
  name: createprivatecloud
  path: /projects/{project}/locations/{location}/privateClouds
- description: Google Cloud VMware Engine Get Private Cloud
  method: GET
  name: getprivatecloud
  path: /projects/{project}/locations/{location}/privateClouds/{privateCloudId}
- description: Google Cloud VMware Engine Delete Private Cloud
  method: DELETE
  name: deleteprivatecloud
  path: /projects/{project}/locations/{location}/privateClouds/{privateCloudId}
- description: Google Cloud VMware Engine List Clusters
  method: GET
  name: listclusters
  path: /projects/{project}/locations/{location}/privateClouds/{privateCloudId}/clusters
- description: Google Cloud VMware Engine Create Cluster
  method: POST
  name: createcluster
  path: /projects/{project}/locations/{location}/privateClouds/{privateCloudId}/clusters
- description: Google Cloud VMware Engine List Network Policies
  method: GET
  name: listnetworkpolicies
  path: /projects/{project}/locations/{location}/networkPolicies
personas: []
provider_name: Google Cloud VMware Engine
provider_slug: google-cloud-vmware-engine
search_terms:
- listclusters
- compute
- google cloud vmware engine get private cloud
- private cloud
- createprivatecloud
- listnetworkpolicies
- virtualization
- cloud
- engine
- google
- google cloud vmware engine create cluster
- createcluster
- google cloud vmware engine delete private cloud
- google cloud vmware engine list network policies
- api
- google cloud vmware engine list clusters
- migration
- google cloud vmware engine list private clouds
- getprivatecloud
- google cloud vmware engine create private cloud
- vmware
- google cloud
- deleteprivatecloud
- listprivateclouds
slug: google-cloud-vmware-engine-capability
source_filename: google-cloud-vmware-engine-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud VMware Engine API\n  description: Programmatically manages VMware private clouds, clusters, and network resources on Google Cloud.\n  tags:\n  - Google\n  - Cloud\n  - Vmware\n  - Engine\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-vmware-engine\n    baseUri: https://vmwareengine.googleapis.com/v1\n    description: Google Cloud VMware Engine API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_VMWARE_ENGINE_TOKEN}}'\n    resources:\n    - name: projects-project-locations-location-privatecloud\n      path: /projects/{project}/locations/{location}/privateClouds\n      operations:\n      - name: listprivateclouds\n        method: GET\n        description: Google Cloud VMware Engine List Private Clouds\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required:\
  \ true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createprivatecloud\n        method: POST\n        description: Google Cloud VMware Engine Create Private Cloud\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-privatecloud\n      path: /projects/{project}/locations/{location}/privateClouds/{privateCloudId}\n      operations:\n      - name: getprivatecloud\n        method: GET\n        description: Google Cloud VMware Engine Get Private Cloud\n        inputParameters:\n\
  \        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: privateCloudId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteprivatecloud\n        method: DELETE\n        description: Google Cloud VMware Engine Delete Private Cloud\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: privateCloudId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: projects-project-locations-location-privatecloud\n      path: /projects/{project}/locations/{location}/privateClouds/{privateCloudId}/clusters\n      operations:\n      - name: listclusters\n        method: GET\n        description: Google Cloud VMware Engine List Clusters\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: privateCloudId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcluster\n        method: POST\n        description: Google Cloud VMware Engine Create Cluster\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n        \
  \  in: path\n          type: string\n          required: true\n        - name: privateCloudId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-networkpolic\n      path: /projects/{project}/locations/{location}/networkPolicies\n      operations:\n      - name: listnetworkpolicies\n        method: GET\n        description: Google Cloud VMware Engine List Network Policies\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-vmware-engine-rest\n\
  \    description: REST adapter for Google Cloud VMware Engine API.\n    resources:\n    - path: /projects/{project}/locations/{location}/privateClouds\n      name: listprivateclouds\n      operations:\n      - method: GET\n        name: listprivateclouds\n        description: Google Cloud VMware Engine List Private Clouds\n        call: google-cloud-vmware-engine.listprivateclouds\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/privateClouds\n      name: createprivatecloud\n      operations:\n      - method: POST\n        name: createprivatecloud\n        description: Google Cloud VMware Engine Create Private Cloud\n        call: google-cloud-vmware-engine.createprivatecloud\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /projects/{project}/locations/{location}/privateClouds/{privateCloudId}\n      name: getprivatecloud\n      operations:\n      - method: GET\n        name: getprivatecloud\n        description: Google Cloud VMware Engine Get Private Cloud\n        call: google-cloud-vmware-engine.getprivatecloud\n        with:\n          project: rest.project\n          location: rest.location\n          privateCloudId: rest.privateCloudId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/privateClouds/{privateCloudId}\n      name: deleteprivatecloud\n      operations:\n      - method: DELETE\n        name: deleteprivatecloud\n        description: Google Cloud VMware Engine Delete Private Cloud\n        call: google-cloud-vmware-engine.deleteprivatecloud\n        with:\n          project: rest.project\n          location: rest.location\n          privateCloudId: rest.privateCloudId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/privateClouds/{privateCloudId}/clusters\n      name: listclusters\n      operations:\n      - method: GET\n        name: listclusters\n        description: Google Cloud VMware Engine List Clusters\n        call: google-cloud-vmware-engine.listclusters\n        with:\n          project: rest.project\n          location: rest.location\n          privateCloudId: rest.privateCloudId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/privateClouds/{privateCloudId}/clusters\n      name: createcluster\n      operations:\n      - method: POST\n        name: createcluster\n        description: Google Cloud VMware Engine Create Cluster\n        call: google-cloud-vmware-engine.createcluster\n        with:\n          project: rest.project\n          location: rest.location\n          privateCloudId: rest.privateCloudId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/networkPolicies\n      name: listnetworkpolicies\n      operations:\n      - method: GET\n        name: listnetworkpolicies\n        description: Google Cloud VMware Engine List Network Policies\n        call: google-cloud-vmware-engine.listnetworkpolicies\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-vmware-engine-mcp\n    transport: http\n    description: MCP adapter for Google Cloud VMware Engine API for AI agent use.\n    tools:\n    - name: listprivateclouds\n      description: Google Cloud VMware Engine List Private Clouds\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-vmware-engine.listprivateclouds\n      with:\n \
  \       project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createprivatecloud\n      description: Google Cloud VMware Engine Create Private Cloud\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-vmware-engine.createprivatecloud\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprivatecloud\n\
  \      description: Google Cloud VMware Engine Get Private Cloud\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-vmware-engine.getprivatecloud\n      with:\n        project: tools.project\n        location: tools.location\n        privateCloudId: tools.privateCloudId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: privateCloudId\n        type: string\n        description: privateCloudId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteprivatecloud\n      description: Google Cloud VMware Engine Delete Private Cloud\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-vmware-engine.deleteprivatecloud\n    \
  \  with:\n        project: tools.project\n        location: tools.location\n        privateCloudId: tools.privateCloudId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: privateCloudId\n        type: string\n        description: privateCloudId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclusters\n      description: Google Cloud VMware Engine List Clusters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-vmware-engine.listclusters\n      with:\n        project: tools.project\n        location: tools.location\n        privateCloudId: tools.privateCloudId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required:\
  \ true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: privateCloudId\n        type: string\n        description: privateCloudId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcluster\n      description: Google Cloud VMware Engine Create Cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-vmware-engine.createcluster\n      with:\n        project: tools.project\n        location: tools.location\n        privateCloudId: tools.privateCloudId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: privateCloudId\n        type: string\n        description: privateCloudId\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listnetworkpolicies\n      description: Google Cloud VMware Engine List Network Policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-vmware-engine.listnetworkpolicies\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_VMWARE_ENGINE_TOKEN: GOOGLE_CLOUD_VMWARE_ENGINE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-vmware-engine/refs/heads/main/capabilities/google-cloud-vmware-engine-capability.yaml
tags:
- Google
- Cloud
- Vmware
- Engine
- API
tools:
- description: Google Cloud VMware Engine List Private Clouds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprivateclouds
- description: Google Cloud VMware Engine Create Private Cloud
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprivatecloud
- description: Google Cloud VMware Engine Get Private Cloud
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprivatecloud
- description: Google Cloud VMware Engine Delete Private Cloud
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprivatecloud
- description: Google Cloud VMware Engine List Clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusters
- description: Google Cloud VMware Engine Create Cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcluster
- description: Google Cloud VMware Engine List Network Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnetworkpolicies
---
