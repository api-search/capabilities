---
categories: []
consumed_apis: []
description: The Flagsmith Admin API allows developers to programmatically manage all aspects of their Flagsmith projects. Anything that can be done through the Flagsmith dashboard can also be accomplished via this API, including creating, updating, and deleting projects, environments, feature flags, segments, and users. It uses a secret Organisation API Token for authentication and provides a Swagger interface at api.flagsmith.com/api/v1/docs for interactive exploration.
layout: capability
name: Flagsmith Admin API
operations:
- description: List organisations
  method: GET
  name: listorganisations
  path: /organisations/
- description: Get an organisation
  method: GET
  name: getorganisation
  path: /organisations/{organisation_id}/
- description: List projects
  method: GET
  name: listprojects
  path: /projects/
- description: Create a project
  method: POST
  name: createproject
  path: /projects/
- description: Get a project
  method: GET
  name: getproject
  path: /projects/{project_id}/
- description: Update a project
  method: PUT
  name: updateproject
  path: /projects/{project_id}/
- description: Delete a project
  method: DELETE
  name: deleteproject
  path: /projects/{project_id}/
- description: List environments
  method: GET
  name: listenvironments
  path: /environments/
- description: Get an environment
  method: GET
  name: getenvironment
  path: /environments/{environment_api_key}/
- description: Update an environment
  method: PUT
  name: updateenvironment
  path: /environments/{environment_api_key}/
- description: List features for a project
  method: GET
  name: listfeatures
  path: /projects/{project_id}/features/
- description: Create a feature flag
  method: POST
  name: createfeature
  path: /projects/{project_id}/features/
- description: Get a feature flag
  method: GET
  name: getfeature
  path: /projects/{project_id}/features/{feature_id}/
- description: Update a feature flag
  method: PUT
  name: updatefeature
  path: /projects/{project_id}/features/{feature_id}/
- description: Delete a feature flag
  method: DELETE
  name: deletefeature
  path: /projects/{project_id}/features/{feature_id}/
- description: List feature states for an environment
  method: GET
  name: listfeaturestates
  path: /environments/{environment_api_key}/featurestates/
- description: Update a feature state
  method: PATCH
  name: updatefeaturestate
  path: /environments/{environment_api_key}/featurestates/{feature_state_id}/
- description: List segments for a project
  method: GET
  name: listsegments
  path: /projects/{project_id}/segments/
- description: Create a segment
  method: POST
  name: createsegment
  path: /projects/{project_id}/segments/
- description: Get a segment
  method: GET
  name: getsegment
  path: /projects/{project_id}/segments/{segment_id}/
- description: Update a segment
  method: PUT
  name: updatesegment
  path: /projects/{project_id}/segments/{segment_id}/
- description: Delete a segment
  method: DELETE
  name: deletesegment
  path: /projects/{project_id}/segments/{segment_id}/
- description: List identities for an environment
  method: GET
  name: listidentities
  path: /environments/{environment_api_key}/identities/
- description: Get an identity
  method: GET
  name: getidentity
  path: /environments/{environment_api_key}/identities/{identity_id}/
- description: Delete an identity
  method: DELETE
  name: deleteidentity
  path: /environments/{environment_api_key}/identities/{identity_id}/
- description: List organisation users
  method: GET
  name: listorganisationusers
  path: /organisations/{organisation_id}/users/
- description: List environment webhooks
  method: GET
  name: listenvironmentwebhooks
  path: /environments/{environment_api_key}/webhooks/
- description: Create an environment webhook
  method: POST
  name: createenvironmentwebhook
  path: /environments/{environment_api_key}/webhooks/
- description: List organisation webhooks
  method: GET
  name: listorganisationwebhooks
  path: /organisations/{organisation_id}/webhooks/
- description: Create an organisation webhook
  method: POST
  name: createorganisationwebhook
  path: /organisations/{organisation_id}/webhooks/
personas: []
provider_name: flagsmith
provider_slug: flagsmith
search_terms:
- delete a feature flag
- create a segment
- listorganisationusers
- listfeaturestates
- getenvironment
- list environments
- createsegment
- listsegments
- getsegment
- deletesegment
- listidentities
- list features for a project
- listenvironmentwebhooks
- deleteproject
- updateenvironment
- flagsmith
- create an environment webhook
- listorganisationwebhooks
- listfeatures
- list identities for an environment
- create a feature flag
- update an environment
- updateproject
- create an organisation webhook
- get a segment
- create a project
- list feature states for an environment
- getproject
- deletefeature
- updatefeaturestate
- getorganisation
- get an environment
- list segments for a project
- get an identity
- deleteidentity
- update a segment
- getfeature
- api
- getidentity
- get a feature flag
- listenvironments
- delete a project
- update a project
- listorganisations
- listprojects
- list organisation users
- get an organisation
- updatefeature
- list projects
- list organisations
- delete an identity
- list environment webhooks
- update a feature state
- createorganisationwebhook
- list organisation webhooks
- update a feature flag
- delete a segment
- createfeature
- updatesegment
- createenvironmentwebhook
- createproject
- get a project
slug: flagsmith-capability
source_filename: flagsmith-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Flagsmith Admin API\n  description: The Flagsmith Admin API allows developers to programmatically manage all aspects of their Flagsmith projects.\n    Anything that can be done through the Flagsmith dashboard can also be accomplished via this API, including creating, updating,\n    and deleting projects, environments, feature flags, segments, and users. It uses a secret Organisation API Token for authentication\n    and provides a Swagger interface at api.flagsmith.com/api/v1/docs for interactive exploration.\n  tags:\n  - Flagsmith\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: flagsmith\n    baseUri: https://api.flagsmith.com/api/v1\n    description: Flagsmith Admin API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{FLAGSMITH_TOKEN}}'\n    resources:\n    - name: organisations\n      path: /organisations/\n\
  \      operations:\n      - name: listorganisations\n        method: GET\n        description: List organisations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organisations-organisation-id\n      path: /organisations/{organisation_id}/\n      operations:\n      - name: getorganisation\n        method: GET\n        description: Get an organisation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects/\n      operations:\n      - name: listprojects\n        method: GET\n        description: List projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Create a project\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: projects-project-id\n      path: /projects/{project_id}/\n      operations:\n      - name: getproject\n        method: GET\n        description: Get a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PUT\n        description: Update a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproject\n        method: DELETE\n        description: Delete a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments\n      path: /environments/\n      operations:\n      - name: listenvironments\n        method: GET\n        description: List environments\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environment-api-key\n      path: /environments/{environment_api_key}/\n      operations:\n      - name: getenvironment\n        method: GET\n        description: Get an environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateenvironment\n        method: PUT\n        description: Update an environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-features\n      path: /projects/{project_id}/features/\n      operations:\n      - name: listfeatures\n        method: GET\n        description: List features for a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ createfeature\n        method: POST\n        description: Create a feature flag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-features-feature-id\n      path: /projects/{project_id}/features/{feature_id}/\n      operations:\n      - name: getfeature\n        method: GET\n        description: Get a feature flag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefeature\n        method: PUT\n        description: Update a feature flag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefeature\n        method: DELETE\n        description: Delete a feature flag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: environments-environment-api-key-featurestates\n      path: /environments/{environment_api_key}/featurestates/\n      operations:\n      - name: listfeaturestates\n        method: GET\n        description: List feature states for an environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environment-api-key-featurestates-f\n      path: /environments/{environment_api_key}/featurestates/{feature_state_id}/\n      operations:\n      - name: updatefeaturestate\n        method: PATCH\n        description: Update a feature state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-segments\n      path: /projects/{project_id}/segments/\n      operations:\n      - name: listsegments\n        method: GET\n        description: List segments for a project\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsegment\n        method: POST\n        description: Create a segment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-segments-segment-id\n      path: /projects/{project_id}/segments/{segment_id}/\n      operations:\n      - name: getsegment\n        method: GET\n        description: Get a segment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesegment\n        method: PUT\n        description: Update a segment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesegment\n        method: DELETE\n        description: Delete a segment\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environment-api-key-identities\n      path: /environments/{environment_api_key}/identities/\n      operations:\n      - name: listidentities\n        method: GET\n        description: List identities for an environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environment-api-key-identities-iden\n      path: /environments/{environment_api_key}/identities/{identity_id}/\n      operations:\n      - name: getidentity\n        method: GET\n        description: Get an identity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteidentity\n        method: DELETE\n        description: Delete an identity\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: organisations-organisation-id-users\n      path: /organisations/{organisation_id}/users/\n      operations:\n      - name: listorganisationusers\n        method: GET\n        description: List organisation users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environment-api-key-webhooks\n      path: /environments/{environment_api_key}/webhooks/\n      operations:\n      - name: listenvironmentwebhooks\n        method: GET\n        description: List environment webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createenvironmentwebhook\n        method: POST\n        description: Create an environment webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: organisations-organisation-id-webhooks\n      path: /organisations/{organisation_id}/webhooks/\n      operations:\n      - name: listorganisationwebhooks\n        method: GET\n        description: List organisation webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorganisationwebhook\n        method: POST\n        description: Create an organisation webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: flagsmith-rest\n    description: REST adapter for Flagsmith Admin API.\n    resources:\n    - path: /organisations/\n      name: listorganisations\n      operations:\n      - method: GET\n        name: listorganisations\n        description: List organisations\n        call: flagsmith.listorganisations\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organisations/{organisation_id}/\n      name: getorganisation\n      operations:\n      - method: GET\n        name: getorganisation\n        description: Get an organisation\n        call: flagsmith.getorganisation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: List projects\n        call: flagsmith.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Create a project\n        call: flagsmith.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/\n      name: getproject\n      operations:\n      -\
  \ method: GET\n        name: getproject\n        description: Get a project\n        call: flagsmith.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/\n      name: updateproject\n      operations:\n      - method: PUT\n        name: updateproject\n        description: Update a project\n        call: flagsmith.updateproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/\n      name: deleteproject\n      operations:\n      - method: DELETE\n        name: deleteproject\n        description: Delete a project\n        call: flagsmith.deleteproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/\n      name: listenvironments\n      operations:\n      - method: GET\n        name: listenvironments\n        description: List environments\n        call: flagsmith.listenvironments\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /environments/{environment_api_key}/\n      name: getenvironment\n      operations:\n      - method: GET\n        name: getenvironment\n        description: Get an environment\n        call: flagsmith.getenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environment_api_key}/\n      name: updateenvironment\n      operations:\n      - method: PUT\n        name: updateenvironment\n        description: Update an environment\n        call: flagsmith.updateenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/features/\n      name: listfeatures\n      operations:\n      - method: GET\n        name: listfeatures\n        description: List features for a project\n        call: flagsmith.listfeatures\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/features/\n\
  \      name: createfeature\n      operations:\n      - method: POST\n        name: createfeature\n        description: Create a feature flag\n        call: flagsmith.createfeature\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/features/{feature_id}/\n      name: getfeature\n      operations:\n      - method: GET\n        name: getfeature\n        description: Get a feature flag\n        call: flagsmith.getfeature\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/features/{feature_id}/\n      name: updatefeature\n      operations:\n      - method: PUT\n        name: updatefeature\n        description: Update a feature flag\n        call: flagsmith.updatefeature\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/features/{feature_id}/\n      name: deletefeature\n      operations:\n      - method: DELETE\n   \
  \     name: deletefeature\n        description: Delete a feature flag\n        call: flagsmith.deletefeature\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environment_api_key}/featurestates/\n      name: listfeaturestates\n      operations:\n      - method: GET\n        name: listfeaturestates\n        description: List feature states for an environment\n        call: flagsmith.listfeaturestates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environment_api_key}/featurestates/{feature_state_id}/\n      name: updatefeaturestate\n      operations:\n      - method: PATCH\n        name: updatefeaturestate\n        description: Update a feature state\n        call: flagsmith.updatefeaturestate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/segments/\n      name: listsegments\n      operations:\n      - method: GET\n   \
  \     name: listsegments\n        description: List segments for a project\n        call: flagsmith.listsegments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/segments/\n      name: createsegment\n      operations:\n      - method: POST\n        name: createsegment\n        description: Create a segment\n        call: flagsmith.createsegment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/segments/{segment_id}/\n      name: getsegment\n      operations:\n      - method: GET\n        name: getsegment\n        description: Get a segment\n        call: flagsmith.getsegment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/segments/{segment_id}/\n      name: updatesegment\n      operations:\n      - method: PUT\n        name: updatesegment\n        description: Update a segment\n        call: flagsmith.updatesegment\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/segments/{segment_id}/\n      name: deletesegment\n      operations:\n      - method: DELETE\n        name: deletesegment\n        description: Delete a segment\n        call: flagsmith.deletesegment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environment_api_key}/identities/\n      name: listidentities\n      operations:\n      - method: GET\n        name: listidentities\n        description: List identities for an environment\n        call: flagsmith.listidentities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environment_api_key}/identities/{identity_id}/\n      name: getidentity\n      operations:\n      - method: GET\n        name: getidentity\n        description: Get an identity\n        call: flagsmith.getidentity\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /environments/{environment_api_key}/identities/{identity_id}/\n      name: deleteidentity\n      operations:\n      - method: DELETE\n        name: deleteidentity\n        description: Delete an identity\n        call: flagsmith.deleteidentity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organisations/{organisation_id}/users/\n      name: listorganisationusers\n      operations:\n      - method: GET\n        name: listorganisationusers\n        description: List organisation users\n        call: flagsmith.listorganisationusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environment_api_key}/webhooks/\n      name: listenvironmentwebhooks\n      operations:\n      - method: GET\n        name: listenvironmentwebhooks\n        description: List environment webhooks\n        call: flagsmith.listenvironmentwebhooks\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /environments/{environment_api_key}/webhooks/\n      name: createenvironmentwebhook\n      operations:\n      - method: POST\n        name: createenvironmentwebhook\n        description: Create an environment webhook\n        call: flagsmith.createenvironmentwebhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organisations/{organisation_id}/webhooks/\n      name: listorganisationwebhooks\n      operations:\n      - method: GET\n        name: listorganisationwebhooks\n        description: List organisation webhooks\n        call: flagsmith.listorganisationwebhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organisations/{organisation_id}/webhooks/\n      name: createorganisationwebhook\n      operations:\n      - method: POST\n        name: createorganisationwebhook\n        description: Create an organisation webhook\n        call: flagsmith.createorganisationwebhook\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: flagsmith-mcp\n    transport: http\n    description: MCP adapter for Flagsmith Admin API for AI agent use.\n    tools:\n    - name: listorganisations\n      description: List organisations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.listorganisations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorganisation\n      description: Get an organisation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.getorganisation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojects\n      description: List projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.listprojects\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: createproject\n      description: Create a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flagsmith.createproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Get a project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.getproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproject\n      description: Update a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: flagsmith.updateproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproject\n      description: Delete a project\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: flagsmith.deleteproject\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listenvironments\n      description: List environments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.listenvironments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getenvironment\n      description: Get an environment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.getenvironment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateenvironment\n      description: Update an environment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: flagsmith.updateenvironment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfeatures\n      description: List features for a project\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: flagsmith.listfeatures\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createfeature\n      description: Create a feature flag\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flagsmith.createfeature\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfeature\n      description: Get a feature flag\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.getfeature\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatefeature\n      description: Update a feature flag\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: flagsmith.updatefeature\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletefeature\n      description: Delete a feature flag\n\
  \      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: flagsmith.deletefeature\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfeaturestates\n      description: List feature states for an environment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.listfeaturestates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatefeaturestate\n      description: Update a feature state\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flagsmith.updatefeaturestate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsegments\n      description: List segments for a project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.listsegments\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: createsegment\n      description: Create a segment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flagsmith.createsegment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsegment\n      description: Get a segment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.getsegment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesegment\n      description: Update a segment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: flagsmith.updatesegment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesegment\n      description: Delete a segment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: flagsmith.deletesegment\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listidentities\n      description: List identities for an environment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.listidentities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getidentity\n      description: Get an identity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.getidentity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteidentity\n      description: Delete an identity\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: flagsmith.deleteidentity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorganisationusers\n      description: List organisation users\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: flagsmith.listorganisationusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listenvironmentwebhooks\n      description: List environment webhooks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.listenvironmentwebhooks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createenvironmentwebhook\n      description: Create an environment webhook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flagsmith.createenvironmentwebhook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorganisationwebhooks\n      description: List organisation webhooks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flagsmith.listorganisationwebhooks\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: createorganisationwebhook\n      description: Create an organisation webhook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flagsmith.createorganisationwebhook\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FLAGSMITH_TOKEN: FLAGSMITH_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/flagsmith/refs/heads/main/capabilities/flagsmith-capability.yaml
tags:
- Flagsmith
- API
tools:
- description: List organisations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganisations
- description: Get an organisation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganisation
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Create a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Get a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Update a project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproject
- description: Delete a project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproject
- description: List environments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listenvironments
- description: Get an environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironment
- description: Update an environment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateenvironment
- description: List features for a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfeatures
- description: Create a feature flag
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfeature
- description: Get a feature flag
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfeature
- description: Update a feature flag
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatefeature
- description: Delete a feature flag
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefeature
- description: List feature states for an environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfeaturestates
- description: Update a feature state
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatefeaturestate
- description: List segments for a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsegments
- description: Create a segment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsegment
- description: Get a segment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsegment
- description: Update a segment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesegment
- description: Delete a segment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesegment
- description: List identities for an environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listidentities
- description: Get an identity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getidentity
- description: Delete an identity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteidentity
- description: List organisation users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganisationusers
- description: List environment webhooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listenvironmentwebhooks
- description: Create an environment webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createenvironmentwebhook
- description: List organisation webhooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganisationwebhooks
- description: Create an organisation webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorganisationwebhook
---
