---
categories: []
consumed_apis: []
description: The Migration Center API provides programmatic access to Google Cloud Migration Center for discovering, assessing, and planning migrations of on-premises infrastructure to Google Cloud. It enables management of assets, groups, import jobs, discovery clients, preference sets, and export jobs to support automated migration planning workflows.
layout: capability
name: Google Cloud Migration Center Google Migration Center API
operations:
- description: Google Cloud Migration Center List assets
  method: GET
  name: listassets
  path: /projects/{projectId}/locations/{location}/assets
- description: Google Cloud Migration Center Get an asset
  method: GET
  name: getasset
  path: /projects/{projectId}/locations/{location}/assets/{assetId}
- description: Google Cloud Migration Center Update an asset
  method: PATCH
  name: updateasset
  path: /projects/{projectId}/locations/{location}/assets/{assetId}
- description: Google Cloud Migration Center Delete an asset
  method: DELETE
  name: deleteasset
  path: /projects/{projectId}/locations/{location}/assets/{assetId}
- description: Google Cloud Migration Center List groups
  method: GET
  name: listgroups
  path: /projects/{projectId}/locations/{location}/groups
- description: Google Cloud Migration Center Create a group
  method: POST
  name: creategroup
  path: /projects/{projectId}/locations/{location}/groups
- description: Google Cloud Migration Center List import jobs
  method: GET
  name: listimportjobs
  path: /projects/{projectId}/locations/{location}/importJobs
- description: Google Cloud Migration Center Create an import job
  method: POST
  name: createimportjob
  path: /projects/{projectId}/locations/{location}/importJobs
- description: Google Cloud Migration Center List preference sets
  method: GET
  name: listpreferencesets
  path: /projects/{projectId}/locations/{location}/preferenceSets
- description: Google Cloud Migration Center Create a preference set
  method: POST
  name: createpreferenceset
  path: /projects/{projectId}/locations/{location}/preferenceSets
personas: []
provider_name: Google Cloud Migration Center
provider_slug: google-cloud-migration-center
search_terms:
- google cloud migration center create a group
- creategroup
- api
- deleteasset
- google cloud migration center update an asset
- listpreferencesets
- migration
- google cloud migration center create an import job
- google cloud migration center list groups
- google
- google cloud migration center delete an asset
- google cloud migration center list import jobs
- google cloud migration center list assets
- infrastructure
- cloud migration
- listgroups
- planning
- discovery
- google cloud migration center list preference sets
- google cloud migration center create a preference set
- google cloud migration center get an asset
- updateasset
- center
- createpreferenceset
- listassets
- cloud
- assessment
- listimportjobs
- createimportjob
- getasset
slug: google-cloud-migration-center-capability
source_filename: google-cloud-migration-center-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Migration Center Google Migration Center API\n  description: The Migration Center API provides programmatic access to Google Cloud Migration Center for discovering, assessing,\n    and planning migrations of on-premises infrastructure to Google Cloud. It enables management of assets, groups, import\n    jobs, discovery clients, preference sets, and export jobs to support automated migration planning workflows.\n  tags:\n  - Google\n  - Cloud\n  - Migration\n  - Center\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-migration-center\n    baseUri: https://migrationcenter.googleapis.com/v1\n    description: Google Cloud Migration Center Google Migration Center API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_MIGRATION_CENTER_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-assets\n\
  \      path: /projects/{projectId}/locations/{location}/assets\n      operations:\n      - name: listassets\n        method: GET\n        description: Google Cloud Migration Center List assets\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The ID of the project\n        - name: location\n          in: path\n          type: string\n          required: true\n          description: The location of the assets\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of assets to return\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for pagination\n        - name: filter\n          in: query\n          type: string\n          description: Filter expression for assets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: projects-projectid-locations-location-assets-ass\n      path: /projects/{projectId}/locations/{location}/assets/{assetId}\n      operations:\n      - name: getasset\n        method: GET\n        description: Google Cloud Migration Center Get an asset\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: assetId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateasset\n        method: PATCH\n        description: Google Cloud Migration Center Update an asset\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in:\
  \ path\n          type: string\n          required: true\n        - name: assetId\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n          description: Field mask for partial update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteasset\n        method: DELETE\n        description: Google Cloud Migration Center Delete an asset\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: assetId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-groups\n\
  \      path: /projects/{projectId}/locations/{location}/groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: Google Cloud Migration Center List groups\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: Google Cloud Migration Center Create a group\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n      \
  \    required: true\n        - name: groupId\n          in: query\n          type: string\n          description: The ID to use for the group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-importjobs\n      path: /projects/{projectId}/locations/{location}/importJobs\n      operations:\n      - name: listimportjobs\n        method: GET\n        description: Google Cloud Migration Center List import jobs\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createimportjob\n        method: POST\n        description: Google Cloud Migration Center Create an import\
  \ job\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-preference\n      path: /projects/{projectId}/locations/{location}/preferenceSets\n      operations:\n      - name: listpreferencesets\n        method: GET\n        description: Google Cloud Migration Center List preference sets\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpreferenceset\n\
  \        method: POST\n        description: Google Cloud Migration Center Create a preference set\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-migration-center-rest\n    description: REST adapter for Google Cloud Migration Center Google Migration Center API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/assets\n      name: listassets\n      operations:\n      - method: GET\n        name: listassets\n        description: Google Cloud Migration Center List assets\n        call: google-cloud-migration-center.listassets\n        with:\n          projectId: rest.projectId\n          location: rest.location\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/assets/{assetId}\n      name: getasset\n      operations:\n      - method: GET\n        name: getasset\n        description: Google Cloud Migration Center Get an asset\n        call: google-cloud-migration-center.getasset\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          assetId: rest.assetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/assets/{assetId}\n      name: updateasset\n      operations:\n      - method: PATCH\n        name: updateasset\n        description: Google Cloud Migration Center Update an asset\n        call: google-cloud-migration-center.updateasset\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          assetId: rest.assetId\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/assets/{assetId}\n      name: deleteasset\n      operations:\n      - method: DELETE\n        name: deleteasset\n        description: Google Cloud Migration Center Delete an asset\n        call: google-cloud-migration-center.deleteasset\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          assetId: rest.assetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: Google Cloud Migration Center List groups\n        call: google-cloud-migration-center.listgroups\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/groups\n\
  \      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: Google Cloud Migration Center Create a group\n        call: google-cloud-migration-center.creategroup\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/importJobs\n      name: listimportjobs\n      operations:\n      - method: GET\n        name: listimportjobs\n        description: Google Cloud Migration Center List import jobs\n        call: google-cloud-migration-center.listimportjobs\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/importJobs\n      name: createimportjob\n      operations:\n      - method: POST\n        name: createimportjob\n\
  \        description: Google Cloud Migration Center Create an import job\n        call: google-cloud-migration-center.createimportjob\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/preferenceSets\n      name: listpreferencesets\n      operations:\n      - method: GET\n        name: listpreferencesets\n        description: Google Cloud Migration Center List preference sets\n        call: google-cloud-migration-center.listpreferencesets\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/preferenceSets\n      name: createpreferenceset\n      operations:\n      - method: POST\n        name: createpreferenceset\n        description: Google Cloud Migration Center\
  \ Create a preference set\n        call: google-cloud-migration-center.createpreferenceset\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-migration-center-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Migration Center Google Migration Center API for AI agent use.\n    tools:\n    - name: listassets\n      description: Google Cloud Migration Center List assets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-migration-center.listassets\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        filter: tools.filter\n      inputParameters:\n      - name: projectId\n        type: string\n        description: The ID of the project\n\
  \        required: true\n      - name: location\n        type: string\n        description: The location of the assets\n        required: true\n      - name: pageSize\n        type: integer\n        description: Maximum number of assets to return\n      - name: pageToken\n        type: string\n        description: Page token for pagination\n      - name: filter\n        type: string\n        description: Filter expression for assets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getasset\n      description: Google Cloud Migration Center Get an asset\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-migration-center.getasset\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        assetId: tools.assetId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n\
  \        type: string\n        description: location\n        required: true\n      - name: assetId\n        type: string\n        description: assetId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateasset\n      description: Google Cloud Migration Center Update an asset\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-migration-center.updateasset\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        assetId: tools.assetId\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: assetId\n        type: string\n        description: assetId\n        required: true\n      - name: updateMask\n        type:\
  \ string\n        description: Field mask for partial update\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteasset\n      description: Google Cloud Migration Center Delete an asset\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-migration-center.deleteasset\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        assetId: tools.assetId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: assetId\n        type: string\n        description: assetId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroups\n      description: Google Cloud Migration Center List groups\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: google-cloud-migration-center.listgroups\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategroup\n      description: Google Cloud Migration Center Create a group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-migration-center.creategroup\n      with:\n        projectId: tools.projectId\n\
  \        location: tools.location\n        groupId: tools.groupId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: groupId\n        type: string\n        description: The ID to use for the group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listimportjobs\n      description: Google Cloud Migration Center List import jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-migration-center.listimportjobs\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createimportjob\n      description: Google Cloud Migration Center Create an import job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-migration-center.createimportjob\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpreferencesets\n      description: Google Cloud Migration Center List preference sets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-migration-center.listpreferencesets\n      with:\n        projectId: tools.projectId\n\
  \        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpreferenceset\n      description: Google Cloud Migration Center Create a preference set\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-migration-center.createpreferenceset\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n\
  \  keys:\n    GOOGLE_CLOUD_MIGRATION_CENTER_TOKEN: GOOGLE_CLOUD_MIGRATION_CENTER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-migration-center/refs/heads/main/capabilities/google-cloud-migration-center-capability.yaml
tags:
- Google
- Cloud
- Migration
- Center
- API
tools:
- description: Google Cloud Migration Center List assets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listassets
- description: Google Cloud Migration Center Get an asset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getasset
- description: Google Cloud Migration Center Update an asset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateasset
- description: Google Cloud Migration Center Delete an asset
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteasset
- description: Google Cloud Migration Center List groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: Google Cloud Migration Center Create a group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: Google Cloud Migration Center List import jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listimportjobs
- description: Google Cloud Migration Center Create an import job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createimportjob
- description: Google Cloud Migration Center List preference sets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpreferencesets
- description: Google Cloud Migration Center Create a preference set
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpreferenceset
---
