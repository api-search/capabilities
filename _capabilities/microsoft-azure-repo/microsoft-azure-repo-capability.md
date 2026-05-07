---
categories: []
consumed_apis: []
description: REST API for managing Git repositories, branches, commits, pull requests, pushes, and items in Azure Repos. Provides full programmatic control over Git-based source code hosted in Azure DevOps, including creating and reviewing pull requests, managing branches and tags, browsing repository content, and pushing commits.
layout: capability
name: Azure Repos Git API
operations:
- description: Azure Repos List repositories
  method: GET
  name: repositories-list
  path: /git/repositories
- description: Azure Repos Create a repository
  method: POST
  name: repositories-create
  path: /git/repositories
- description: Azure Repos Get a repository
  method: GET
  name: repositories-get
  path: /git/repositories/{repositoryId}
- description: Azure Repos Update a repository
  method: PATCH
  name: repositories-update
  path: /git/repositories/{repositoryId}
- description: Azure Repos Delete a repository
  method: DELETE
  name: repositories-delete
  path: /git/repositories/{repositoryId}
- description: Azure Repos List pull requests
  method: GET
  name: pullrequests-list
  path: /git/repositories/{repositoryId}/pullrequests
- description: Azure Repos Create a pull request
  method: POST
  name: pullrequests-create
  path: /git/repositories/{repositoryId}/pullrequests
- description: Azure Repos Get a pull request
  method: GET
  name: pullrequests-get
  path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}
- description: Azure Repos Update a pull request
  method: PATCH
  name: pullrequests-update
  path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}
- description: Azure Repos List pull request reviewers
  method: GET
  name: pullrequestreviewers-list
  path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/reviewers
- description: Azure Repos Add or update a reviewer
  method: PUT
  name: pullrequestreviewers-createorupdate
  path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/reviewers/{reviewerId}
- description: Azure Repos Remove a reviewer
  method: DELETE
  name: pullrequestreviewers-delete
  path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/reviewers/{reviewerId}
- description: Azure Repos List pull request threads
  method: GET
  name: pullrequestthreads-list
  path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/threads
- description: Azure Repos Create a comment thread
  method: POST
  name: pullrequestthreads-create
  path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/threads
- description: Azure Repos List pull request commits
  method: GET
  name: pullrequestcommits-list
  path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/commits
- description: Azure Repos List commits
  method: GET
  name: commits-list
  path: /git/repositories/{repositoryId}/commits
- description: Azure Repos Get a commit
  method: GET
  name: commits-get
  path: /git/repositories/{repositoryId}/commits/{commitId}
- description: Azure Repos List refs (branches and tags)
  method: GET
  name: refs-list
  path: /git/repositories/{repositoryId}/refs
- description: Azure Repos Create, update, or delete refs
  method: POST
  name: refs-update
  path: /git/repositories/{repositoryId}/refs
- description: Azure Repos List pushes
  method: GET
  name: pushes-list
  path: /git/repositories/{repositoryId}/pushes
- description: Azure Repos Create a push
  method: POST
  name: pushes-create
  path: /git/repositories/{repositoryId}/pushes
- description: Azure Repos Get a push
  method: GET
  name: pushes-get
  path: /git/repositories/{repositoryId}/pushes/{pushId}
- description: Azure Repos List items (files and folders)
  method: GET
  name: items-list
  path: /git/repositories/{repositoryId}/items
- description: Azure Repos List branch statistics
  method: GET
  name: stats-list
  path: /git/repositories/{repositoryId}/stats/branches
personas: []
provider_name: Azure Repos
provider_slug: microsoft-azure-repo
search_terms:
- devops
- azure repos update a repository
- git
- pullrequests list
- refs update
- azure repos create a push
- api
- repositories delete
- pushes list
- azure repos list pull request threads
- azure repos delete a repository
- azure repos list pull requests
- pushes create
- azure repos create a pull request
- pullrequestreviewers delete
- pullrequestcommits list
- repositories create
- pullrequests create
- microsoft
- repositories get
- pullrequestthreads create
- azure repos add or update a reviewer
- azure repos get a push
- azure repos create, update, or delete refs
- stats list
- azure repos list items (files and folders)
- azure repos list pushes
- azure repos list branch statistics
- tfvc
- repo
- azure repos get a repository
- pullrequests update
- azure repos list pull request reviewers
- azure repos remove a reviewer
- source control
- azure repos list repositories
- pullrequests get
- pullrequestreviewers createorupdate
- azure repos get a pull request
- azure repos create a comment thread
- pullrequestreviewers list
- azure repos list refs (branches and tags)
- repositories update
- azure repos update a pull request
- commits get
- repositories
- version control
- azure
- pullrequestthreads list
- commits list
- azure repos list pull request commits
- items list
- repositories list
- pushes get
- azure repos get a commit
- azure repos list commits
- refs list
- azure repos create a repository
slug: microsoft-azure-repo-capability
source_filename: microsoft-azure-repo-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Repos Git API\n  description: REST API for managing Git repositories, branches, commits, pull requests, pushes, and items in Azure Repos.\n    Provides full programmatic control over Git-based source code hosted in Azure DevOps, including creating and reviewing\n    pull requests, managing branches and tags, browsing repository content, and pushing commits.\n  tags:\n  - Microsoft\n  - Azure\n  - Repo\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-azure-repo\n    baseUri: https://dev.azure.com/myorganization/myproject/_apis\n    description: Azure Repos Git API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_AZURE_REPO_TOKEN}}'\n    resources:\n    - name: git-repositories\n      path: /git/repositories\n      operations:\n      - name: repositories-list\n        method: GET\n        description: Azure Repos List repositories\n\
  \        inputParameters:\n        - name: includeAllUrls\n          in: query\n          type: boolean\n          description: Set to true to include all remote URLs in the response. Defaults to false.\n        - name: includeHidden\n          in: query\n          type: boolean\n          description: Set to true to include hidden repositories. Defaults to false.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: repositories-create\n        method: POST\n        description: Azure Repos Create a repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: git-repositories-repositoryid\n      path: /git/repositories/{repositoryId}\n      operations:\n      - name: repositories-get\n        method: GET\n        description: Azure Repos Get a repository\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: repositories-update\n        method: PATCH\n        description: Azure Repos Update a repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: repositories-delete\n        method: DELETE\n        description: Azure Repos Delete a repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: git-repositories-repositoryid-pullrequests\n      path: /git/repositories/{repositoryId}/pullrequests\n      operations:\n      - name: pullrequests-list\n        method: GET\n        description: Azure Repos List pull requests\n        inputParameters:\n        - name: searchCriteria.status\n          in: query\n          type: string\n          description: Filter by pull request status. Defaults to active if unset.\n        - name:\
  \ searchCriteria.creatorId\n          in: query\n          type: string\n          description: Filter by the identity ID of the pull request creator\n        - name: searchCriteria.reviewerId\n          in: query\n          type: string\n          description: Filter by the identity ID of a reviewer\n        - name: searchCriteria.sourceRefName\n          in: query\n          type: string\n          description: Filter by source branch name (e.g., refs/heads/feature)\n        - name: searchCriteria.targetRefName\n          in: query\n          type: string\n          description: Filter by target branch name (e.g., refs/heads/main)\n        - name: searchCriteria.repositoryId\n          in: query\n          type: string\n          description: Filter by target repository ID\n        - name: searchCriteria.sourceRepositoryId\n          in: query\n          type: string\n          description: Filter by source repository ID\n        - name: searchCriteria.includeLinks\n          in: query\n\
  \          type: boolean\n          description: Whether to include the _links field on shallow references\n        - name: searchCriteria.minTime\n          in: query\n          type: string\n          description: Filter pull requests created or closed after this date based on queryTimeRangeType\n        - name: searchCriteria.maxTime\n          in: query\n          type: string\n          description: Filter pull requests created or closed before this date based on queryTimeRangeType\n        - name: searchCriteria.queryTimeRangeType\n          in: query\n          type: string\n          description: The type of time range for minTime and maxTime. Defaults to created if unset.\n        - name: $top\n          in: query\n          type: integer\n          description: Number of pull requests to retrieve\n        - name: $skip\n          in: query\n          type: integer\n          description: Number of pull requests to skip\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: pullrequests-create\n        method: POST\n        description: Azure Repos Create a pull request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: git-repositories-repositoryid-pullrequests-pullr\n      path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}\n      operations:\n      - name: pullrequests-get\n        method: GET\n        description: Azure Repos Get a pull request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: pullrequests-update\n        method: PATCH\n        description: Azure Repos Update a pull request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: git-repositories-repositoryid-pullrequests-pullr\n\
  \      path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/reviewers\n      operations:\n      - name: pullrequestreviewers-list\n        method: GET\n        description: Azure Repos List pull request reviewers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: git-repositories-repositoryid-pullrequests-pullr\n      path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/reviewers/{reviewerId}\n      operations:\n      - name: pullrequestreviewers-createorupdate\n        method: PUT\n        description: Azure Repos Add or update a reviewer\n        inputParameters:\n        - name: reviewerId\n          in: path\n          type: string\n          required: true\n          description: ID of the reviewer identity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: pullrequestreviewers-delete\n\
  \        method: DELETE\n        description: Azure Repos Remove a reviewer\n        inputParameters:\n        - name: reviewerId\n          in: path\n          type: string\n          required: true\n          description: ID of the reviewer identity to remove\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: git-repositories-repositoryid-pullrequests-pullr\n      path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/threads\n      operations:\n      - name: pullrequestthreads-list\n        method: GET\n        description: Azure Repos List pull request threads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: pullrequestthreads-create\n        method: POST\n        description: Azure Repos Create a comment thread\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: git-repositories-repositoryid-pullrequests-pullr\n      path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/commits\n      operations:\n      - name: pullrequestcommits-list\n        method: GET\n        description: Azure Repos List pull request commits\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: git-repositories-repositoryid-commits\n      path: /git/repositories/{repositoryId}/commits\n      operations:\n      - name: commits-list\n        method: GET\n        description: Azure Repos List commits\n        inputParameters:\n        - name: searchCriteria.itemVersion.version\n          in: query\n          type: string\n          description: Branch name or tag to search (e.g., main, develop)\n        - name: searchCriteria.itemVersion.versionType\n          in: query\n          type: string\n          description: Type\
  \ of version identifier\n        - name: searchCriteria.itemPath\n          in: query\n          type: string\n          description: Path of an item to filter commits that changed this path\n        - name: searchCriteria.fromDate\n          in: query\n          type: string\n          description: Start date for filtering commits\n        - name: searchCriteria.toDate\n          in: query\n          type: string\n          description: End date for filtering commits\n        - name: searchCriteria.author\n          in: query\n          type: string\n          description: Filter by author name or email\n        - name: searchCriteria.$top\n          in: query\n          type: integer\n          description: Maximum number of commits to return\n        - name: searchCriteria.$skip\n          in: query\n          type: integer\n          description: Number of commits to skip\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n    - name: git-repositories-repositoryid-commits-commitid\n      path: /git/repositories/{repositoryId}/commits/{commitId}\n      operations:\n      - name: commits-get\n        method: GET\n        description: Azure Repos Get a commit\n        inputParameters:\n        - name: commitId\n          in: path\n          type: string\n          required: true\n          description: The SHA-1 hash of the commit\n        - name: changeCount\n          in: query\n          type: integer\n          description: Maximum number of changes to include\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: git-repositories-repositoryid-refs\n      path: /git/repositories/{repositoryId}/refs\n      operations:\n      - name: refs-list\n        method: GET\n        description: Azure Repos List refs (branches and tags)\n        inputParameters:\n        - name: filter\n          in: query\n    \
  \      type: string\n          description: Filter refs by name prefix (e.g., heads/main, tags/v1)\n        - name: includeLinks\n          in: query\n          type: boolean\n          description: Include reference links in the response\n        - name: includeStatuses\n          in: query\n          type: boolean\n          description: Include status information for each ref\n        - name: includeMyBranches\n          in: query\n          type: boolean\n          description: Include only branches owned by the authenticated user\n        - name: peelTags\n          in: query\n          type: boolean\n          description: Annotated tags will populate the PeeledObjectId property\n        - name: $top\n          in: query\n          type: integer\n          description: Maximum number of refs to return\n        - name: continuationToken\n          in: query\n          type: string\n          description: Continuation token for paging through results\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refs-update\n        method: POST\n        description: Azure Repos Create, update, or delete refs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: git-repositories-repositoryid-pushes\n      path: /git/repositories/{repositoryId}/pushes\n      operations:\n      - name: pushes-list\n        method: GET\n        description: Azure Repos List pushes\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          description: Number of pushes to return\n        - name: $skip\n          in: query\n          type: integer\n          description: Number of pushes to skip\n        - name: searchCriteria.fromDate\n          in: query\n          type: string\n          description: Start date for filtering pushes\n        - name: searchCriteria.toDate\n \
  \         in: query\n          type: string\n          description: End date for filtering pushes\n        - name: searchCriteria.pusherId\n          in: query\n          type: string\n          description: Filter by pusher identity ID\n        - name: searchCriteria.refName\n          in: query\n          type: string\n          description: Filter by branch name (e.g., refs/heads/main)\n        - name: searchCriteria.includeRefUpdates\n          in: query\n          type: boolean\n          description: Include ref update details in results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: pushes-create\n        method: POST\n        description: Azure Repos Create a push\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: git-repositories-repositoryid-pushes-pushid\n      path: /git/repositories/{repositoryId}/pushes/{pushId}\n\
  \      operations:\n      - name: pushes-get\n        method: GET\n        description: Azure Repos Get a push\n        inputParameters:\n        - name: pushId\n          in: path\n          type: integer\n          required: true\n          description: ID of the push\n        - name: includeCommits\n          in: query\n          type: integer\n          description: Number of commits to include\n        - name: includeRefUpdates\n          in: query\n          type: boolean\n          description: Include ref update details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: git-repositories-repositoryid-items\n      path: /git/repositories/{repositoryId}/items\n      operations:\n      - name: items-list\n        method: GET\n        description: Azure Repos List items (files and folders)\n        inputParameters:\n        - name: scopePath\n          in: query\n          type: string\n       \
  \   description: The path scope for items (e.g., /src or /README.md)\n        - name: recursionLevel\n          in: query\n          type: string\n          description: Level of recursion for folder listing\n        - name: versionDescriptor.version\n          in: query\n          type: string\n          description: Branch name, tag, or commit to get items from\n        - name: versionDescriptor.versionType\n          in: query\n          type: string\n          description: Type of version identifier\n        - name: includeContentMetadata\n          in: query\n          type: boolean\n          description: Include content metadata for items\n        - name: latestProcessedChange\n          in: query\n          type: boolean\n          description: Include the latest change for each item\n        - name: includeLinks\n          in: query\n          type: boolean\n          description: Include reference links\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: git-repositories-repositoryid-stats-branches\n      path: /git/repositories/{repositoryId}/stats/branches\n      operations:\n      - name: stats-list\n        method: GET\n        description: Azure Repos List branch statistics\n        inputParameters:\n        - name: baseVersionDescriptor.version\n          in: query\n          type: string\n          description: Base branch or commit to compare against\n        - name: baseVersionDescriptor.versionType\n          in: query\n          type: string\n          description: Type of the base version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-azure-repo-rest\n    description: REST adapter for Azure Repos Git API.\n    resources:\n    - path: /git/repositories\n      name: repositories-list\n      operations:\n      - method:\
  \ GET\n        name: repositories-list\n        description: Azure Repos List repositories\n        call: microsoft-azure-repo.repositories-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories\n      name: repositories-create\n      operations:\n      - method: POST\n        name: repositories-create\n        description: Azure Repos Create a repository\n        call: microsoft-azure-repo.repositories-create\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}\n      name: repositories-get\n      operations:\n      - method: GET\n        name: repositories-get\n        description: Azure Repos Get a repository\n        call: microsoft-azure-repo.repositories-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}\n      name: repositories-update\n      operations:\n      - method: PATCH\n        name:\
  \ repositories-update\n        description: Azure Repos Update a repository\n        call: microsoft-azure-repo.repositories-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}\n      name: repositories-delete\n      operations:\n      - method: DELETE\n        name: repositories-delete\n        description: Azure Repos Delete a repository\n        call: microsoft-azure-repo.repositories-delete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pullrequests\n      name: pullrequests-list\n      operations:\n      - method: GET\n        name: pullrequests-list\n        description: Azure Repos List pull requests\n        call: microsoft-azure-repo.pullrequests-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pullrequests\n      name: pullrequests-create\n      operations:\n\
  \      - method: POST\n        name: pullrequests-create\n        description: Azure Repos Create a pull request\n        call: microsoft-azure-repo.pullrequests-create\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}\n      name: pullrequests-get\n      operations:\n      - method: GET\n        name: pullrequests-get\n        description: Azure Repos Get a pull request\n        call: microsoft-azure-repo.pullrequests-get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}\n      name: pullrequests-update\n      operations:\n      - method: PATCH\n        name: pullrequests-update\n        description: Azure Repos Update a pull request\n        call: microsoft-azure-repo.pullrequests-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/reviewers\n\
  \      name: pullrequestreviewers-list\n      operations:\n      - method: GET\n        name: pullrequestreviewers-list\n        description: Azure Repos List pull request reviewers\n        call: microsoft-azure-repo.pullrequestreviewers-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/reviewers/{reviewerId}\n      name: pullrequestreviewers-createorupdate\n      operations:\n      - method: PUT\n        name: pullrequestreviewers-createorupdate\n        description: Azure Repos Add or update a reviewer\n        call: microsoft-azure-repo.pullrequestreviewers-createorupdate\n        with:\n          reviewerId: rest.reviewerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/reviewers/{reviewerId}\n      name: pullrequestreviewers-delete\n      operations:\n      - method: DELETE\n \
  \       name: pullrequestreviewers-delete\n        description: Azure Repos Remove a reviewer\n        call: microsoft-azure-repo.pullrequestreviewers-delete\n        with:\n          reviewerId: rest.reviewerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/threads\n      name: pullrequestthreads-list\n      operations:\n      - method: GET\n        name: pullrequestthreads-list\n        description: Azure Repos List pull request threads\n        call: microsoft-azure-repo.pullrequestthreads-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/threads\n      name: pullrequestthreads-create\n      operations:\n      - method: POST\n        name: pullrequestthreads-create\n        description: Azure Repos Create a comment thread\n        call: microsoft-azure-repo.pullrequestthreads-create\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pullrequests/{pullRequestId}/commits\n      name: pullrequestcommits-list\n      operations:\n      - method: GET\n        name: pullrequestcommits-list\n        description: Azure Repos List pull request commits\n        call: microsoft-azure-repo.pullrequestcommits-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/commits\n      name: commits-list\n      operations:\n      - method: GET\n        name: commits-list\n        description: Azure Repos List commits\n        call: microsoft-azure-repo.commits-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/commits/{commitId}\n      name: commits-get\n      operations:\n      - method: GET\n        name: commits-get\n        description: Azure Repos Get a commit\n        call:\
  \ microsoft-azure-repo.commits-get\n        with:\n          commitId: rest.commitId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/refs\n      name: refs-list\n      operations:\n      - method: GET\n        name: refs-list\n        description: Azure Repos List refs (branches and tags)\n        call: microsoft-azure-repo.refs-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/refs\n      name: refs-update\n      operations:\n      - method: POST\n        name: refs-update\n        description: Azure Repos Create, update, or delete refs\n        call: microsoft-azure-repo.refs-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pushes\n      name: pushes-list\n      operations:\n      - method: GET\n        name: pushes-list\n        description: Azure Repos List pushes\n\
  \        call: microsoft-azure-repo.pushes-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pushes\n      name: pushes-create\n      operations:\n      - method: POST\n        name: pushes-create\n        description: Azure Repos Create a push\n        call: microsoft-azure-repo.pushes-create\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/pushes/{pushId}\n      name: pushes-get\n      operations:\n      - method: GET\n        name: pushes-get\n        description: Azure Repos Get a push\n        call: microsoft-azure-repo.pushes-get\n        with:\n          pushId: rest.pushId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/items\n      name: items-list\n      operations:\n      - method: GET\n        name: items-list\n        description: Azure Repos List items (files\
  \ and folders)\n        call: microsoft-azure-repo.items-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /git/repositories/{repositoryId}/stats/branches\n      name: stats-list\n      operations:\n      - method: GET\n        name: stats-list\n        description: Azure Repos List branch statistics\n        call: microsoft-azure-repo.stats-list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-azure-repo-mcp\n    transport: http\n    description: MCP adapter for Azure Repos Git API for AI agent use.\n    tools:\n    - name: repositories-list\n      description: Azure Repos List repositories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-repo.repositories-list\n      with:\n        includeAllUrls: tools.includeAllUrls\n        includeHidden: tools.includeHidden\n      inputParameters:\n    \
  \  - name: includeAllUrls\n        type: boolean\n        description: Set to true to include all remote URLs in the response. Defaults to false.\n      - name: includeHidden\n        type: boolean\n        description: Set to true to include hidden repositories. Defaults to false.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: repositories-create\n      description: Azure Repos Create a repository\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-repo.repositories-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: repositories-get\n      description: Azure Repos Get a repository\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-repo.repositories-get\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: repositories-update\n      description: Azure\
  \ Repos Update a repository\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-repo.repositories-update\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: repositories-delete\n      description: Azure Repos Delete a repository\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-azure-repo.repositories-delete\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pullrequests-list\n      description: Azure Repos List pull requests\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-repo.pullrequests-list\n      with:\n        searchCriteria.status: tools.searchCriteria.status\n        searchCriteria.creatorId: tools.searchCriteria.creatorId\n        searchCriteria.reviewerId: tools.searchCriteria.reviewerId\n        searchCriteria.sourceRefName:\
  \ tools.searchCriteria.sourceRefName\n        searchCriteria.targetRefName: tools.searchCriteria.targetRefName\n        searchCriteria.repositoryId: tools.searchCriteria.repositoryId\n        searchCriteria.sourceRepositoryId: tools.searchCriteria.sourceRepositoryId\n        searchCriteria.includeLinks: tools.searchCriteria.includeLinks\n        searchCriteria.minTime: tools.searchCriteria.minTime\n        searchCriteria.maxTime: tools.searchCriteria.maxTime\n        searchCriteria.queryTimeRangeType: tools.searchCriteria.queryTimeRangeType\n        $top: tools.$top\n        $skip: tools.$skip\n      inputParameters:\n      - name: searchCriteria.status\n        type: string\n        description: Filter by pull request status. Defaults to active if unset.\n      - name: searchCriteria.creatorId\n        type: string\n        description: Filter by the identity ID of the pull request creator\n      - name: searchCriteria.reviewerId\n        type: string\n        description: Filter by the\
  \ identity ID of a reviewer\n      - name: searchCriteria.sourceRefName\n        type: string\n        description: Filter by source branch name (e.g., refs/heads/feature)\n      - name: searchCriteria.targetRefName\n        type: string\n        description: Filter by target branch name (e.g., refs/heads/main)\n      - name: searchCriteria.repositoryId\n        type: string\n        description: Filter by target repository ID\n      - name: searchCriteria.sourceRepositoryId\n        type: string\n        description: Filter by source repository ID\n      - name: searchCriteria.includeLinks\n        type: boolean\n        description: Whether to include the _links field on shallow references\n      - name: searchCriteria.minTime\n        type: string\n        description: Filter pull requests created or closed after this date based on queryTimeRangeType\n      - name: searchCriteria.maxTime\n        type: string\n        description: Filter pull requests created or closed before this date\
  \ based on queryTimeRangeType\n      - name: searchCriteria.queryTimeRangeType\n        type: string\n        description: The type of time range for minTime and maxTime. Defaults to created if unset.\n      - name: $top\n        type: integer\n        description: Number of pull requests to retrieve\n      - name: $skip\n        type: integer\n        description: Number of pull requests to skip\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pullrequests-create\n      description: Azure Repos Create a pull request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-repo.pullrequests-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pullrequests-get\n      description: Azure Repos Get a pull request\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-repo.pullrequests-get\n   \
  \   outputParameters:\n      - type: object\n        mapping: $.\n    - name: pullrequests-update\n      description: Azure Repos Update a pull request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-repo.pullrequests-update\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pullrequestreviewers-list\n      description: Azure Repos List pull request reviewers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-repo.pullrequestreviewers-list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pullrequestreviewers-createorupdate\n      description: Azure Repos Add or update a reviewer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-repo.pullrequestreviewers-createorupdate\n      with:\n        reviewerId: tools.reviewerId\n\
  \      inputParameters:\n      - name: reviewerId\n        type: string\n        description: ID of the reviewer identity\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pullrequestreviewers-delete\n      description: Azure Repos Remove a reviewer\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-azure-repo.pullrequestreviewers-delete\n      with:\n        reviewerId: tools.reviewerId\n      inputParameters:\n      - name: reviewerId\n        type: string\n        description: ID of the reviewer identity to remove\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pullrequestthreads-list\n      description: Azure Repos List pull request threads\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-repo.pullrequestthreads-list\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: pullrequestthreads-create\n      description: Azure Repos Create a comment thread\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-azure-repo.pullrequestthreads-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pullrequestcommits-list\n      description: Azure Repos List pull request commits\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-azure-repo.pullrequestcommits-list\n      outp\n\n# --- truncated at 32 KB (40 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-repo/refs/heads/main/capabilities/microsoft-azure-repo-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-repo/refs/heads/main/capabilities/microsoft-azure-repo-capability.yaml
tags:
- Microsoft
- Azure
- Repo
- API
tools:
- description: Azure Repos List repositories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: repositories-list
- description: Azure Repos Create a repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: repositories-create
- description: Azure Repos Get a repository
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: repositories-get
- description: Azure Repos Update a repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: repositories-update
- description: Azure Repos Delete a repository
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: repositories-delete
- description: Azure Repos List pull requests
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: pullrequests-list
- description: Azure Repos Create a pull request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pullrequests-create
- description: Azure Repos Get a pull request
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: pullrequests-get
- description: Azure Repos Update a pull request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pullrequests-update
- description: Azure Repos List pull request reviewers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: pullrequestreviewers-list
- description: Azure Repos Add or update a reviewer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: pullrequestreviewers-createorupdate
- description: Azure Repos Remove a reviewer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: pullrequestreviewers-delete
- description: Azure Repos List pull request threads
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: pullrequestthreads-list
- description: Azure Repos Create a comment thread
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pullrequestthreads-create
- description: Azure Repos List pull request commits
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: pullrequestcommits-list
- description: Azure Repos List commits
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: commits-list
- description: Azure Repos Get a commit
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: commits-get
- description: Azure Repos List refs (branches and tags)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: refs-list
- description: Azure Repos Create, update, or delete refs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: refs-update
- description: Azure Repos List pushes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: pushes-list
- description: Azure Repos Create a push
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pushes-create
- description: Azure Repos Get a push
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: pushes-get
- description: Azure Repos List items (files and folders)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: items-list
- description: Azure Repos List branch statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: stats-list
---
