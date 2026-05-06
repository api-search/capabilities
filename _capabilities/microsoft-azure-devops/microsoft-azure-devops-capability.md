---
categories: []
consumed_apis: []
description: REST API for managing packages, feeds, and artifact dependencies in Azure Artifacts. Supports NuGet, npm, Maven, Python, and Universal package formats in private or public feeds. Enables programmatic management of package feeds, discovery of packages and their versions, and lifecycle operations such as deprecating or deleting package versions.
layout: capability
name: Azure DevOps Artifacts API
operations:
- description: Azure DevOps List feeds
  method: GET
  name: feeds-list
  path: /packaging/feeds
- description: Azure DevOps Create a feed
  method: POST
  name: feeds-create
  path: /packaging/feeds
- description: Azure DevOps Get a feed
  method: GET
  name: feeds-get
  path: /packaging/feeds/{feedId}
- description: Azure DevOps Update a feed
  method: PATCH
  name: feeds-update
  path: /packaging/feeds/{feedId}
- description: Azure DevOps Delete a feed
  method: DELETE
  name: feeds-delete
  path: /packaging/feeds/{feedId}
- description: Azure DevOps List packages in a feed
  method: GET
  name: packages-list
  path: /packaging/feeds/{feedId}/packages
- description: Azure DevOps Get package details
  method: GET
  name: packages-get
  path: /packaging/feeds/{feedId}/packages/{packageId}
- description: Azure DevOps Delete a package version
  method: DELETE
  name: packageversions-delete
  path: /packaging/feeds/{feedId}/packages/{packageId}/versions/{packageVersionId}
personas: []
provider_name: Azure DevOps
provider_slug: microsoft-azure-devops
search_terms:
- azure devops get package details
- feeds delete
- feeds create
- devops
- azure
- azure devops create a feed
- azure devops list feeds
- azure devops delete a feed
- packages list
- project management
- packages get
- agile
- azure devops delete a package version
- ci/cd
- packageversions delete
- api
- azure devops update a feed
- azure devops list packages in a feed
- version control
- feeds get
- feeds update
- feeds list
- azure devops get a feed
- microsoft
slug: microsoft-azure-devops-capability
source_filename: microsoft-azure-devops-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure DevOps Artifacts API\n  description: REST API for managing packages, feeds, and artifact dependencies in Azure Artifacts. Supports NuGet, npm, Maven,\n    Python, and Universal package formats in private or public feeds. Enables programmatic management of package feeds, discovery\n    of packages and their versions, and lifecycle operations such as deprecating or deleting package versions.\n  tags:\n  - Microsoft\n  - Azure\n  - Devops\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-azure-devops\n    baseUri: https://feeds.dev.azure.com/myorganization/myproject/_apis\n    description: Azure DevOps Artifacts API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_AZURE_DEVOPS_TOKEN}}'\n    resources:\n    - name: packaging-feeds\n      path: /packaging/feeds\n      operations:\n      - name: feeds-list\n        method: GET\n \
  \       description: Azure DevOps List feeds\n        inputParameters:\n        - name: feedRole\n          in: query\n          type: string\n          description: Filter feeds by the current user's role\n        - name: includeDeletedUpstreams\n          in: query\n          type: boolean\n          description: Whether to include feeds with deleted upstream sources\n        - name: includeUrls\n          in: query\n          type: boolean\n          description: Whether to include package manager endpoint URLs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: feeds-create\n        method: POST\n        description: Azure DevOps Create a feed\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packaging-feeds-feedid\n      path: /packaging/feeds/{feedId}\n      operations:\n      - name: feeds-get\n      \
  \  method: GET\n        description: Azure DevOps Get a feed\n        inputParameters:\n        - name: includeDeletedUpstreams\n          in: query\n          type: boolean\n          description: Whether to include deleted upstream sources in the response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: feeds-update\n        method: PATCH\n        description: Azure DevOps Update a feed\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: feeds-delete\n        method: DELETE\n        description: Azure DevOps Delete a feed\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packaging-feeds-feedid-packages\n      path: /packaging/feeds/{feedId}/packages\n      operations:\n      - name: packages-list\n        method: GET\n\
  \        description: Azure DevOps List packages in a feed\n        inputParameters:\n        - name: protocolType\n          in: query\n          type: string\n          description: Filter packages by protocol type\n        - name: packageNameQuery\n          in: query\n          type: string\n          description: Filter packages whose names contain this string\n        - name: normalizedPackageName\n          in: query\n          type: string\n          description: Exact package name match (normalized form)\n        - name: includeUrls\n          in: query\n          type: boolean\n          description: Whether to include package manager URLs in the response\n        - name: includeAllVersions\n          in: query\n          type: boolean\n          description: Whether to include all versions or only the latest\n        - name: isListed\n          in: query\n          type: boolean\n          description: Filter by listed status (true=published, false=unlisted)\n        - name:\
  \ getTopPackageVersions\n          in: query\n          type: boolean\n          description: Whether to include the top versions for each package\n        - name: isDeleted\n          in: query\n          type: boolean\n          description: Whether to include deleted packages\n        - name: $top\n          in: query\n          type: integer\n          description: Maximum number of packages to return\n        - name: $skip\n          in: query\n          type: integer\n          description: Number of packages to skip (for pagination)\n        - name: continuationToken\n          in: query\n          type: string\n          description: Continuation token for paginated results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packaging-feeds-feedid-packages-packageid\n      path: /packaging/feeds/{feedId}/packages/{packageId}\n      operations:\n      - name: packages-get\n        method: GET\n\
  \        description: Azure DevOps Get package details\n        inputParameters:\n        - name: packageId\n          in: path\n          type: string\n          required: true\n          description: GUID identifier of the package\n        - name: includeAllVersions\n          in: query\n          type: boolean\n          description: Whether to include all versions or only the latest\n        - name: includeUrls\n          in: query\n          type: boolean\n          description: Whether to include package manager URLs\n        - name: isListed\n          in: query\n          type: boolean\n          description: Filter versions by listed status\n        - name: isDeleted\n          in: query\n          type: boolean\n          description: Whether to include deleted versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packaging-feeds-feedid-packages-packageid-versio\n      path: /packaging/feeds/{feedId}/packages/{packageId}/versions/{packageVersionId}\n\
  \      operations:\n      - name: packageversions-delete\n        method: DELETE\n        description: Azure DevOps Delete a package version\n        inputParameters:\n        - name: packageId\n          in: path\n          type: string\n          required: true\n          description: GUID identifier of the package\n        - name: packageVersionId\n          in: path\n          type: string\n          required: true\n          description: GUID identifier of the package version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-azure-devops-rest\n    description: REST adapter for Azure DevOps Artifacts API.\n    resources:\n    - path: /packaging/feeds\n      name: feeds-list\n      operations:\n      - method: GET\n        name: feeds-list\n        description: Azure DevOps List feeds\n        call: microsoft-azure-devops.feeds-list\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /packaging/feeds\n      name: feeds-create\n      operations:\n      - method: POST\n        name: feeds-create\n        description: Azure DevOps Create a feed\n        call: microsoft-azure-devops.feeds-create\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /packaging/feeds/{feedId}\n      name: feeds-get\n      operations:\n      - method: GET\n        name: feeds-get\n        description: Azure DevOps Get a feed\n        call: microsoft-azure-devops.feeds-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /packaging/feeds/{feedId}\n      name: feeds-update\n      operations:\n      - method: PATCH\n        name: feeds-update\n        description: Azure DevOps Update a feed\n        call: microsoft-azure-devops.feeds-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /packaging/feeds/{feedId}\n\
  \      name: feeds-delete\n      operations:\n      - method: DELETE\n        name: feeds-delete\n        description: Azure DevOps Delete a feed\n        call: microsoft-azure-devops.feeds-delete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /packaging/feeds/{feedId}/packages\n      name: packages-list\n      operations:\n      - method: GET\n        name: packages-list\n        description: Azure DevOps List packages in a feed\n        call: microsoft-azure-devops.packages-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /packaging/feeds/{feedId}/packages/{packageId}\n      name: packages-get\n      operations:\n      - method: GET\n        name: packages-get\n        description: Azure DevOps Get package details\n        call: microsoft-azure-devops.packages-get\n        with:\n          packageId: rest.packageId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /packaging/feeds/{feedId}/packages/{packageId}/versions/{packageVersionId}\n\
  \      name: packageversions-delete\n      operations:\n      - method: DELETE\n        name: packageversions-delete\n        description: Azure DevOps Delete a package version\n        call: microsoft-azure-devops.packageversions-delete\n        with:\n          packageId: rest.packageId\n          packageVersionId: rest.packageVersionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-azure-devops-mcp\n    transport: http\n    description: MCP adapter for Azure DevOps Artifacts API for AI agent use.\n    tools:\n    - name: feeds-list\n      description: Azure DevOps List feeds\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-devops.feeds-list\n      with:\n        feedRole: tools.feedRole\n        includeDeletedUpstreams: tools.includeDeletedUpstreams\n        includeUrls: tools.includeUrls\n      inputParameters:\n      - name: feedRole\n\
  \        type: string\n        description: Filter feeds by the current user's role\n      - name: includeDeletedUpstreams\n        type: boolean\n        description: Whether to include feeds with deleted upstream sources\n      - name: includeUrls\n        type: boolean\n        description: Whether to include package manager endpoint URLs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: feeds-create\n      description: Azure DevOps Create a feed\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-devops.feeds-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: feeds-get\n      description: Azure DevOps Get a feed\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-devops.feeds-get\n      with:\n        includeDeletedUpstreams: tools.includeDeletedUpstreams\n      inputParameters:\n\
  \      - name: includeDeletedUpstreams\n        type: boolean\n        description: Whether to include deleted upstream sources in the response\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: feeds-update\n      description: Azure DevOps Update a feed\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-devops.feeds-update\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: feeds-delete\n      description: Azure DevOps Delete a feed\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-azure-devops.feeds-delete\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: packages-list\n      description: Azure DevOps List packages in a feed\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-devops.packages-list\n\
  \      with:\n        protocolType: tools.protocolType\n        packageNameQuery: tools.packageNameQuery\n        normalizedPackageName: tools.normalizedPackageName\n        includeUrls: tools.includeUrls\n        includeAllVersions: tools.includeAllVersions\n        isListed: tools.isListed\n        getTopPackageVersions: tools.getTopPackageVersions\n        isDeleted: tools.isDeleted\n        $top: tools.$top\n        $skip: tools.$skip\n        continuationToken: tools.continuationToken\n      inputParameters:\n      - name: protocolType\n        type: string\n        description: Filter packages by protocol type\n      - name: packageNameQuery\n        type: string\n        description: Filter packages whose names contain this string\n      - name: normalizedPackageName\n        type: string\n        description: Exact package name match (normalized form)\n      - name: includeUrls\n        type: boolean\n        description: Whether to include package manager URLs in the response\n\
  \      - name: includeAllVersions\n        type: boolean\n        description: Whether to include all versions or only the latest\n      - name: isListed\n        type: boolean\n        description: Filter by listed status (true=published, false=unlisted)\n      - name: getTopPackageVersions\n        type: boolean\n        description: Whether to include the top versions for each package\n      - name: isDeleted\n        type: boolean\n        description: Whether to include deleted packages\n      - name: $top\n        type: integer\n        description: Maximum number of packages to return\n      - name: $skip\n        type: integer\n        description: Number of packages to skip (for pagination)\n      - name: continuationToken\n        type: string\n        description: Continuation token for paginated results\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: packages-get\n      description: Azure DevOps Get package details\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-devops.packages-get\n      with:\n        packageId: tools.packageId\n        includeAllVersions: tools.includeAllVersions\n        includeUrls: tools.includeUrls\n        isListed: tools.isListed\n        isDeleted: tools.isDeleted\n      inputParameters:\n      - name: packageId\n        type: string\n        description: GUID identifier of the package\n        required: true\n      - name: includeAllVersions\n        type: boolean\n        description: Whether to include all versions or only the latest\n      - name: includeUrls\n        type: boolean\n        description: Whether to include package manager URLs\n      - name: isListed\n        type: boolean\n        description: Filter versions by listed status\n      - name: isDeleted\n        type: boolean\n        description: Whether to include deleted versions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ packageversions-delete\n      description: Azure DevOps Delete a package version\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-azure-devops.packageversions-delete\n      with:\n        packageId: tools.packageId\n        packageVersionId: tools.packageVersionId\n      inputParameters:\n      - name: packageId\n        type: string\n        description: GUID identifier of the package\n        required: true\n      - name: packageVersionId\n        type: string\n        description: GUID identifier of the package version\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_AZURE_DEVOPS_TOKEN: MICROSOFT_AZURE_DEVOPS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-devops/refs/heads/main/capabilities/microsoft-azure-devops-capability.yaml
tags:
- Microsoft
- Azure
- Devops
- API
tools:
- description: Azure DevOps List feeds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feeds-list
- description: Azure DevOps Create a feed
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: feeds-create
- description: Azure DevOps Get a feed
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: feeds-get
- description: Azure DevOps Update a feed
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: feeds-update
- description: Azure DevOps Delete a feed
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: feeds-delete
- description: Azure DevOps List packages in a feed
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: packages-list
- description: Azure DevOps Get package details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: packages-get
- description: Azure DevOps Delete a package version
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: packageversions-delete
---
