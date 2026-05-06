---
categories: []
consumed_apis: []
description: REST API for managing build definitions, queuing builds, and retrieving build results, artifacts, tags, and logs in Azure DevOps. Supports the full lifecycle of continuous integration builds including creating and updating build definitions, listing and filtering builds by status and result, tagging builds for identification, and downloading build artifacts.
layout: capability
name: Azure Pipelines Build REST API
operations:
- description: Azure Pipelines List builds
  method: GET
  name: listbuilds
  path: /build/builds
- description: Azure Pipelines Get a build
  method: GET
  name: getbuild
  path: /build/builds/{buildId}
- description: Azure Pipelines Update a build
  method: PATCH
  name: updatebuild
  path: /build/builds/{buildId}
- description: Azure Pipelines Delete a build
  method: DELETE
  name: deletebuild
  path: /build/builds/{buildId}
- description: Azure Pipelines List build artifacts
  method: GET
  name: listbuildartifacts
  path: /build/builds/{buildId}/artifacts
- description: Azure Pipelines Get a specific build artifact
  method: GET
  name: getbuildartifact
  path: /build/builds/{buildId}/artifacts/{artifactName}
- description: Azure Pipelines List build tags
  method: GET
  name: listbuildtags
  path: /build/builds/{buildId}/tags
- description: Azure Pipelines Add a tag to a build
  method: PUT
  name: addbuildtag
  path: /build/builds/{buildId}/tags/{tag}
- description: Azure Pipelines Remove a tag from a build
  method: DELETE
  name: deletebuildtag
  path: /build/builds/{buildId}/tags/{tag}
- description: Azure Pipelines List build definitions
  method: GET
  name: listbuilddefinitions
  path: /build/definitions
- description: Azure Pipelines Get a build definition
  method: GET
  name: getbuilddefinition
  path: /build/definitions/{definitionId}
personas: []
provider_name: Azure Pipelines
provider_slug: microsoft-azure-pipelines
search_terms:
- deletebuildtag
- azure pipelines remove a tag from a build
- azure pipelines list build tags
- azure pipelines list build artifacts
- devops
- getbuild
- azure
- pipelines
- azure pipelines get a build definition
- deletebuild
- deployment
- listbuildartifacts
- azure pipelines get a specific build artifact
- build
- azure pipelines update a build
- azure pipelines list build definitions
- azure pipelines list builds
- ci/cd
- listbuildtags
- api
- updatebuild
- addbuildtag
- listbuilddefinitions
- getbuilddefinition
- azure pipelines get a build
- getbuildartifact
- listbuilds
- azure pipelines delete a build
- azure pipelines add a tag to a build
- microsoft
- automation
slug: microsoft-azure-pipelines-capability
source_filename: microsoft-azure-pipelines-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Pipelines Build REST API\n  description: REST API for managing build definitions, queuing builds, and retrieving build results, artifacts, tags, and\n    logs in Azure DevOps. Supports the full lifecycle of continuous integration builds including creating and updating build\n    definitions, listing and filtering builds by status and result, tagging builds for identification, and downloading build\n    artifacts.\n  tags:\n  - Microsoft\n  - Azure\n  - Pipelines\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-azure-pipelines\n    baseUri: https://dev.azure.com/myorganization/myproject/_apis\n    description: Azure Pipelines Build REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_AZURE_PIPELINES_TOKEN}}'\n    resources:\n    - name: build-builds\n      path: /build/builds\n      operations:\n      - name: listbuilds\n\
  \        method: GET\n        description: Azure Pipelines List builds\n        inputParameters:\n        - name: definitions\n          in: query\n          type: string\n          description: Comma-delimited list of definition IDs to filter by\n        - name: queues\n          in: query\n          type: string\n          description: Comma-delimited list of queue IDs to filter by\n        - name: buildNumber\n          in: query\n          type: string\n          description: Filter by build number. Append asterisk for prefix matching.\n        - name: minTime\n          in: query\n          type: string\n          description: Filter to builds after this date based on the query order\n        - name: maxTime\n          in: query\n          type: string\n          description: Filter to builds before this date based on the query order\n        - name: requestedFor\n          in: query\n          type: string\n          description: Filter to builds requested by this user\n        -\
  \ name: reasonFilter\n          in: query\n          type: string\n          description: Filter by the reason the build was created\n        - name: statusFilter\n          in: query\n          type: string\n          description: Filter by current build status\n        - name: resultFilter\n          in: query\n          type: string\n          description: Filter by build result\n        - name: tagFilters\n          in: query\n          type: string\n          description: Comma-delimited list of tags to filter by\n        - name: $top\n          in: query\n          type: integer\n          description: Maximum number of builds to return\n        - name: continuationToken\n          in: query\n          type: string\n          description: Continuation token for paginated results\n        - name: maxBuildsPerDefinition\n          in: query\n          type: integer\n          description: Maximum number of builds to return per definition\n        - name: deletedFilter\n          in:\
  \ query\n          type: string\n          description: Filter for deleted builds\n        - name: queryOrder\n          in: query\n          type: string\n          description: Sort order for the results\n        - name: branchName\n          in: query\n          type: string\n          description: Filter to builds from this branch\n        - name: buildIds\n          in: query\n          type: string\n          description: Comma-delimited list of build IDs to retrieve\n        - name: repositoryId\n          in: query\n          type: string\n          description: Filter to builds from this repository\n        - name: repositoryType\n          in: query\n          type: string\n          description: Filter to builds from repositories of this type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: build-builds-buildid\n      path: /build/builds/{buildId}\n      operations:\n      - name: getbuild\n\
  \        method: GET\n        description: Azure Pipelines Get a build\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebuild\n        method: PATCH\n        description: Azure Pipelines Update a build\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebuild\n        method: DELETE\n        description: Azure Pipelines Delete a build\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: build-builds-buildid-artifacts\n      path: /build/builds/{buildId}/artifacts\n      operations:\n      - name: listbuildartifacts\n        method: GET\n        description: Azure Pipelines List build artifacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: build-builds-buildid-artifacts-artifactname\n      path: /build/builds/{buildId}/artifacts/{artifactName}\n      operations:\n      - name: getbuildartifact\n        method: GET\n        description: Azure Pipelines Get a specific build artifact\n        inputParameters:\n        - name: artifactName\n          in: path\n          type: string\n          required: true\n          description: Name of the artifact to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: build-builds-buildid-tags\n      path: /build/builds/{buildId}/tags\n      operations:\n      - name: listbuildtags\n        method: GET\n        description: Azure Pipelines List build tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: build-builds-buildid-tags-tag\n      path: /build/builds/{buildId}/tags/{tag}\n\
  \      operations:\n      - name: addbuildtag\n        method: PUT\n        description: Azure Pipelines Add a tag to a build\n        inputParameters:\n        - name: tag\n          in: path\n          type: string\n          required: true\n          description: Tag to add to the build\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebuildtag\n        method: DELETE\n        description: Azure Pipelines Remove a tag from a build\n        inputParameters:\n        - name: tag\n          in: path\n          type: string\n          required: true\n          description: Tag to remove from the build\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: build-definitions\n      path: /build/definitions\n      operations:\n      - name: listbuilddefinitions\n        method: GET\n        description: Azure\
  \ Pipelines List build definitions\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter by definition name (supports prefix match with asterisk)\n        - name: repositoryId\n          in: query\n          type: string\n          description: Filter to definitions using this repository\n        - name: repositoryType\n          in: query\n          type: string\n          description: Filter by repository type\n        - name: queryOrder\n          in: query\n          type: string\n          description: Sort order for results\n        - name: $top\n          in: query\n          type: integer\n          description: Maximum number of definitions to return\n        - name: continuationToken\n          in: query\n          type: string\n          description: Continuation token for paginated results\n        - name: path\n          in: query\n          type: string\n          description: Filter by folder path\n  \
  \      - name: builtAfter\n          in: query\n          type: string\n          description: Filter to definitions with builds after this date\n        - name: notBuiltAfter\n          in: query\n          type: string\n          description: Filter to definitions without builds after this date\n        - name: includeAllProperties\n          in: query\n          type: boolean\n          description: Include all properties of the definition\n        - name: includeLatestBuilds\n          in: query\n          type: boolean\n          description: Include the latest build for each definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: build-definitions-definitionid\n      path: /build/definitions/{definitionId}\n      operations:\n      - name: getbuilddefinition\n        method: GET\n        description: Azure Pipelines Get a build definition\n        inputParameters:\n        - name: definitionId\n\
  \          in: path\n          type: integer\n          required: true\n          description: Numeric ID of the build definition\n        - name: revision\n          in: query\n          type: integer\n          description: Specific revision of the definition to retrieve\n        - name: includeLatestBuilds\n          in: query\n          type: boolean\n          description: Include the latest build for the definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-azure-pipelines-rest\n    description: REST adapter for Azure Pipelines Build REST API.\n    resources:\n    - path: /build/builds\n      name: listbuilds\n      operations:\n      - method: GET\n        name: listbuilds\n        description: Azure Pipelines List builds\n        call: microsoft-azure-pipelines.listbuilds\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /build/builds/{buildId}\n      name: getbuild\n      operations:\n      - method: GET\n        name: getbuild\n        description: Azure Pipelines Get a build\n        call: microsoft-azure-pipelines.getbuild\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /build/builds/{buildId}\n      name: updatebuild\n      operations:\n      - method: PATCH\n        name: updatebuild\n        description: Azure Pipelines Update a build\n        call: microsoft-azure-pipelines.updatebuild\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /build/builds/{buildId}\n      name: deletebuild\n      operations:\n      - method: DELETE\n        name: deletebuild\n        description: Azure Pipelines Delete a build\n        call: microsoft-azure-pipelines.deletebuild\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /build/builds/{buildId}/artifacts\n      name:\
  \ listbuildartifacts\n      operations:\n      - method: GET\n        name: listbuildartifacts\n        description: Azure Pipelines List build artifacts\n        call: microsoft-azure-pipelines.listbuildartifacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /build/builds/{buildId}/artifacts/{artifactName}\n      name: getbuildartifact\n      operations:\n      - method: GET\n        name: getbuildartifact\n        description: Azure Pipelines Get a specific build artifact\n        call: microsoft-azure-pipelines.getbuildartifact\n        with:\n          artifactName: rest.artifactName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /build/builds/{buildId}/tags\n      name: listbuildtags\n      operations:\n      - method: GET\n        name: listbuildtags\n        description: Azure Pipelines List build tags\n        call: microsoft-azure-pipelines.listbuildtags\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /build/builds/{buildId}/tags/{tag}\n      name: addbuildtag\n      operations:\n      - method: PUT\n        name: addbuildtag\n        description: Azure Pipelines Add a tag to a build\n        call: microsoft-azure-pipelines.addbuildtag\n        with:\n          tag: rest.tag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /build/builds/{buildId}/tags/{tag}\n      name: deletebuildtag\n      operations:\n      - method: DELETE\n        name: deletebuildtag\n        description: Azure Pipelines Remove a tag from a build\n        call: microsoft-azure-pipelines.deletebuildtag\n        with:\n          tag: rest.tag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /build/definitions\n      name: listbuilddefinitions\n      operations:\n      - method: GET\n        name: listbuilddefinitions\n        description: Azure Pipelines List build definitions\n        call: microsoft-azure-pipelines.listbuilddefinitions\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /build/definitions/{definitionId}\n      name: getbuilddefinition\n      operations:\n      - method: GET\n        name: getbuilddefinition\n        description: Azure Pipelines Get a build definition\n        call: microsoft-azure-pipelines.getbuilddefinition\n        with:\n          definitionId: rest.definitionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-azure-pipelines-mcp\n    transport: http\n    description: MCP adapter for Azure Pipelines Build REST API for AI agent use.\n    tools:\n    - name: listbuilds\n      description: Azure Pipelines List builds\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-pipelines.listbuilds\n      with:\n        definitions: tools.definitions\n        queues: tools.queues\n        buildNumber: tools.buildNumber\n\
  \        minTime: tools.minTime\n        maxTime: tools.maxTime\n        requestedFor: tools.requestedFor\n        reasonFilter: tools.reasonFilter\n        statusFilter: tools.statusFilter\n        resultFilter: tools.resultFilter\n        tagFilters: tools.tagFilters\n        $top: tools.$top\n        continuationToken: tools.continuationToken\n        maxBuildsPerDefinition: tools.maxBuildsPerDefinition\n        deletedFilter: tools.deletedFilter\n        queryOrder: tools.queryOrder\n        branchName: tools.branchName\n        buildIds: tools.buildIds\n        repositoryId: tools.repositoryId\n        repositoryType: tools.repositoryType\n      inputParameters:\n      - name: definitions\n        type: string\n        description: Comma-delimited list of definition IDs to filter by\n      - name: queues\n        type: string\n        description: Comma-delimited list of queue IDs to filter by\n      - name: buildNumber\n        type: string\n        description: Filter by build number.\
  \ Append asterisk for prefix matching.\n      - name: minTime\n        type: string\n        description: Filter to builds after this date based on the query order\n      - name: maxTime\n        type: string\n        description: Filter to builds before this date based on the query order\n      - name: requestedFor\n        type: string\n        description: Filter to builds requested by this user\n      - name: reasonFilter\n        type: string\n        description: Filter by the reason the build was created\n      - name: statusFilter\n        type: string\n        description: Filter by current build status\n      - name: resultFilter\n        type: string\n        description: Filter by build result\n      - name: tagFilters\n        type: string\n        description: Comma-delimited list of tags to filter by\n      - name: $top\n        type: integer\n        description: Maximum number of builds to return\n      - name: continuationToken\n        type: string\n        description:\
  \ Continuation token for paginated results\n      - name: maxBuildsPerDefinition\n        type: integer\n        description: Maximum number of builds to return per definition\n      - name: deletedFilter\n        type: string\n        description: Filter for deleted builds\n      - name: queryOrder\n        type: string\n        description: Sort order for the results\n      - name: branchName\n        type: string\n        description: Filter to builds from this branch\n      - name: buildIds\n        type: string\n        description: Comma-delimited list of build IDs to retrieve\n      - name: repositoryId\n        type: string\n        description: Filter to builds from this repository\n      - name: repositoryType\n        type: string\n        description: Filter to builds from repositories of this type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbuild\n      description: Azure Pipelines Get a build\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: microsoft-azure-pipelines.getbuild\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatebuild\n      description: Azure Pipelines Update a build\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-pipelines.updatebuild\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebuild\n      description: Azure Pipelines Delete a build\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-azure-pipelines.deletebuild\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbuildartifacts\n      description: Azure Pipelines List build artifacts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-pipelines.listbuildartifacts\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getbuildartifact\n      description: Azure Pipelines Get a specific build artifact\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-pipelines.getbuildartifact\n      with:\n        artifactName: tools.artifactName\n      inputParameters:\n      - name: artifactName\n        type: string\n        description: Name of the artifact to retrieve\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbuildtags\n      description: Azure Pipelines List build tags\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-pipelines.listbuildtags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addbuildtag\n      description: Azure Pipelines Add a tag to a build\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: true\n      call: microsoft-azure-pipelines.addbuildtag\n      with:\n        tag: tools.tag\n      inputParameters:\n      - name: tag\n        type: string\n        description: Tag to add to the build\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebuildtag\n      description: Azure Pipelines Remove a tag from a build\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-azure-pipelines.deletebuildtag\n      with:\n        tag: tools.tag\n      inputParameters:\n      - name: tag\n        type: string\n        description: Tag to remove from the build\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbuilddefinitions\n      description: Azure Pipelines List build definitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-pipelines.listbuilddefinitions\n\
  \      with:\n        name: tools.name\n        repositoryId: tools.repositoryId\n        repositoryType: tools.repositoryType\n        queryOrder: tools.queryOrder\n        $top: tools.$top\n        continuationToken: tools.continuationToken\n        path: tools.path\n        builtAfter: tools.builtAfter\n        notBuiltAfter: tools.notBuiltAfter\n        includeAllProperties: tools.includeAllProperties\n        includeLatestBuilds: tools.includeLatestBuilds\n      inputParameters:\n      - name: name\n        type: string\n        description: Filter by definition name (supports prefix match with asterisk)\n      - name: repositoryId\n        type: string\n        description: Filter to definitions using this repository\n      - name: repositoryType\n        type: string\n        description: Filter by repository type\n      - name: queryOrder\n        type: string\n        description: Sort order for results\n      - name: $top\n        type: integer\n        description: Maximum number\
  \ of definitions to return\n      - name: continuationToken\n        type: string\n        description: Continuation token for paginated results\n      - name: path\n        type: string\n        description: Filter by folder path\n      - name: builtAfter\n        type: string\n        description: Filter to definitions with builds after this date\n      - name: notBuiltAfter\n        type: string\n        description: Filter to definitions without builds after this date\n      - name: includeAllProperties\n        type: boolean\n        description: Include all properties of the definition\n      - name: includeLatestBuilds\n        type: boolean\n        description: Include the latest build for each definition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbuilddefinition\n      description: Azure Pipelines Get a build definition\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-pipelines.getbuilddefinition\n\
  \      with:\n        definitionId: tools.definitionId\n        revision: tools.revision\n        includeLatestBuilds: tools.includeLatestBuilds\n      inputParameters:\n      - name: definitionId\n        type: integer\n        description: Numeric ID of the build definition\n        required: true\n      - name: revision\n        type: integer\n        description: Specific revision of the definition to retrieve\n      - name: includeLatestBuilds\n        type: boolean\n        description: Include the latest build for the definition\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_AZURE_PIPELINES_TOKEN: MICROSOFT_AZURE_PIPELINES_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-pipelines/refs/heads/main/capabilities/microsoft-azure-pipelines-capability.yaml
tags:
- Microsoft
- Azure
- Pipelines
- API
tools:
- description: Azure Pipelines List builds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuilds
- description: Azure Pipelines Get a build
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbuild
- description: Azure Pipelines Update a build
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatebuild
- description: Azure Pipelines Delete a build
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebuild
- description: Azure Pipelines List build artifacts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuildartifacts
- description: Azure Pipelines Get a specific build artifact
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbuildartifact
- description: Azure Pipelines List build tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuildtags
- description: Azure Pipelines Add a tag to a build
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: addbuildtag
- description: Azure Pipelines Remove a tag from a build
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebuildtag
- description: Azure Pipelines List build definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuilddefinitions
- description: Azure Pipelines Get a build definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbuilddefinition
---
