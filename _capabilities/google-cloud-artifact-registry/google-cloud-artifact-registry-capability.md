---
categories: []
consumed_apis: []
description: The Artifact Registry API provides programmatic access to create and manage repositories, upload and download artifacts, manage packages and versions, and configure IAM policies for artifact storage across multiple formats including Docker images, language packages, and OS packages.
layout: capability
name: Google Cloud Artifact Registry API
operations:
- description: Google Cloud Artifact Registry List Locations
  method: GET
  name: listlocations
  path: /v1/projects/{projectId}/locations
- description: Google Cloud Artifact Registry List Repositories
  method: GET
  name: listrepositories
  path: /v1/projects/{projectId}/locations/{location}/repositories
- description: Google Cloud Artifact Registry Create Repository
  method: POST
  name: createrepository
  path: /v1/projects/{projectId}/locations/{location}/repositories
- description: Google Cloud Artifact Registry Get Repository
  method: GET
  name: getrepository
  path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}
- description: Google Cloud Artifact Registry Update Repository
  method: PATCH
  name: updaterepository
  path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}
- description: Google Cloud Artifact Registry Delete Repository
  method: DELETE
  name: deleterepository
  path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}
- description: Google Cloud Artifact Registry List Packages
  method: GET
  name: listpackages
  path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}/packages
- description: Google Cloud Artifact Registry List Docker Images
  method: GET
  name: listdockerimages
  path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}/dockerImages
personas: []
provider_name: Google Cloud Artifact Registry
provider_slug: google-cloud-artifact-registry
search_terms:
- listlocations
- containers
- google cloud artifact registry update repository
- google cloud artifact registry get repository
- artifacts
- google cloud artifact registry list locations
- createrepository
- api
- listrepositories
- supply chain
- google cloud artifact registry list docker images
- deleterepository
- updaterepository
- registry
- google
- registries
- listdockerimages
- artifact
- google cloud artifact registry create repository
- google cloud artifact registry list packages
- packages
- cloud
- google cloud artifact registry list repositories
- repositories
- listpackages
- google cloud
- getrepository
- docker
- security
- google cloud artifact registry delete repository
slug: google-cloud-artifact-registry-capability
source_filename: google-cloud-artifact-registry-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Artifact Registry API\n  description: The Artifact Registry API provides programmatic access to create and manage repositories, upload and download\n    artifacts, manage packages and versions, and configure IAM policies for artifact storage across multiple formats including\n    Docker images, language packages, and OS packages.\n  tags:\n  - Google\n  - Cloud\n  - Artifact\n  - Registry\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-artifact-registry\n    baseUri: https://artifactregistry.googleapis.com\n    description: Google Cloud Artifact Registry API HTTP API.\n    resources:\n    - name: v1-projects-projectid-locations\n      path: /v1/projects/{projectId}/locations\n      operations:\n      - name: listlocations\n        method: GET\n        description: Google Cloud Artifact Registry List Locations\n        inputParameters:\n    \
  \    - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-locations-location-reposit\n      path: /v1/projects/{projectId}/locations/{location}/repositories\n      operations:\n      - name: listrepositories\n        method: GET\n        description: Google Cloud Artifact Registry List Repositories\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createrepository\n        method: POST\n        description: Google Cloud Artifact Registry Create Repository\n        inputParameters:\n    \
  \    - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-locations-location-reposit\n      path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}\n      operations:\n      - name: getrepository\n        method: GET\n        description: Google Cloud Artifact Registry Get Repository\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: repositoryId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: updaterepository\n        method: PATCH\n        description: Google Cloud Artifact Registry Update Repository\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: repositoryId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterepository\n        method: DELETE\n        description: Google Cloud Artifact Registry Delete Repository\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: repositoryId\n     \
  \     in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-locations-location-reposit\n      path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}/packages\n      operations:\n      - name: listpackages\n        method: GET\n        description: Google Cloud Artifact Registry List Packages\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: repositoryId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-locations-location-reposit\n     \
  \ path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}/dockerImages\n      operations:\n      - name: listdockerimages\n        method: GET\n        description: Google Cloud Artifact Registry List Docker Images\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: repositoryId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-artifact-registry-rest\n    description: REST adapter for Google Cloud Artifact Registry API.\n    resources:\n    - path: /v1/projects/{projectId}/locations\n      name: listlocations\n      operations:\n      - method: GET\n        name: listlocations\n\
  \        description: Google Cloud Artifact Registry List Locations\n        call: google-cloud-artifact-registry.listlocations\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/locations/{location}/repositories\n      name: listrepositories\n      operations:\n      - method: GET\n        name: listrepositories\n        description: Google Cloud Artifact Registry List Repositories\n        call: google-cloud-artifact-registry.listrepositories\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/locations/{location}/repositories\n      name: createrepository\n      operations:\n      - method: POST\n        name: createrepository\n        description: Google Cloud Artifact Registry Create Repository\n        call: google-cloud-artifact-registry.createrepository\n\
  \        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}\n      name: getrepository\n      operations:\n      - method: GET\n        name: getrepository\n        description: Google Cloud Artifact Registry Get Repository\n        call: google-cloud-artifact-registry.getrepository\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          repositoryId: rest.repositoryId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}\n      name: updaterepository\n      operations:\n      - method: PATCH\n        name: updaterepository\n        description: Google Cloud Artifact Registry Update Repository\n        call: google-cloud-artifact-registry.updaterepository\n\
  \        with:\n          projectId: rest.projectId\n          location: rest.location\n          repositoryId: rest.repositoryId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}\n      name: deleterepository\n      operations:\n      - method: DELETE\n        name: deleterepository\n        description: Google Cloud Artifact Registry Delete Repository\n        call: google-cloud-artifact-registry.deleterepository\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          repositoryId: rest.repositoryId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}/packages\n      name: listpackages\n      operations:\n      - method: GET\n        name: listpackages\n        description: Google Cloud Artifact Registry List Packages\n       \
  \ call: google-cloud-artifact-registry.listpackages\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          repositoryId: rest.repositoryId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/locations/{location}/repositories/{repositoryId}/dockerImages\n      name: listdockerimages\n      operations:\n      - method: GET\n        name: listdockerimages\n        description: Google Cloud Artifact Registry List Docker Images\n        call: google-cloud-artifact-registry.listdockerimages\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          repositoryId: rest.repositoryId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-artifact-registry-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Artifact Registry API for AI agent use.\n    tools:\n\
  \    - name: listlocations\n      description: Google Cloud Artifact Registry List Locations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-artifact-registry.listlocations\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrepositories\n      description: Google Cloud Artifact Registry List Repositories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-artifact-registry.listrepositories\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n   \
  \     description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrepository\n      description: Google Cloud Artifact Registry Create Repository\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-artifact-registry.createrepository\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrepository\n      description: Google Cloud Artifact Registry Get Repository\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-artifact-registry.getrepository\n  \
  \    with:\n        projectId: tools.projectId\n        location: tools.location\n        repositoryId: tools.repositoryId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: repositoryId\n        type: string\n        description: repositoryId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updaterepository\n      description: Google Cloud Artifact Registry Update Repository\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-artifact-registry.updaterepository\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        repositoryId: tools.repositoryId\n      inputParameters:\n      - name: projectId\n        type: string\n        description:\
  \ projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: repositoryId\n        type: string\n        description: repositoryId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterepository\n      description: Google Cloud Artifact Registry Delete Repository\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-artifact-registry.deleterepository\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        repositoryId: tools.repositoryId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: repositoryId\n        type: string\n        description: repositoryId\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpackages\n      description: Google Cloud Artifact Registry List Packages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-artifact-registry.listpackages\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        repositoryId: tools.repositoryId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: repositoryId\n        type: string\n        description: repositoryId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdockerimages\n      description: Google Cloud Artifact Registry List Docker Images\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: google-cloud-artifact-registry.listdockerimages\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        repositoryId: tools.repositoryId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: repositoryId\n        type: string\n        description: repositoryId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-artifact-registry/refs/heads/main/capabilities/google-cloud-artifact-registry-capability.yaml
tags:
- Google
- Cloud
- Artifact
- Registry
- API
tools:
- description: Google Cloud Artifact Registry List Locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocations
- description: Google Cloud Artifact Registry List Repositories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrepositories
- description: Google Cloud Artifact Registry Create Repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrepository
- description: Google Cloud Artifact Registry Get Repository
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrepository
- description: Google Cloud Artifact Registry Update Repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updaterepository
- description: Google Cloud Artifact Registry Delete Repository
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterepository
- description: Google Cloud Artifact Registry List Packages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpackages
- description: Google Cloud Artifact Registry List Docker Images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdockerimages
---
