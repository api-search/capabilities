---
categories: []
consumed_apis:
- codeartifact
description: Unified workflow for DevOps teams to manage artifact repositories, publish packages, control access, and govern software supply chains using Amazon CodeArtifact.
layout: capability
name: Amazon CodeArtifact Package Management
operations: []
personas: []
provider_name: Amazon CodeArtifact
provider_slug: amazon-codeartifact
search_terms:
- list repositories in a domain
- get details about a codeartifact domain
- copy package versions
- publish a new package version to a repository
- manage packages and package versions
- delete specific package versions from a repository
- list packages
- list domains
- get authorization token
- publish package version
- publishes and consumes packages from codeartifact repositories.
- connect a repository to a public package registry like npmjs or pypi
- describe repository
- governance and security of external package dependencies and internal packages.
- package management
- manage codeartifact domains
- describe package
- get authorization tokens for package managers
- get details about a package in a repository
- create repository
- delete package versions
- amazon
- copy package versions between repositories in the same domain
- aws
- list packages in a repository
- create a new codeartifact domain
- get the package-format-specific endpoint url for a repository
- generate a temporary authorization token for accessing codeartifact repositories
- npm
- DevOps Engineer
- manage codeartifact repositories
- storage and retrieval of software artifacts and their metadata.
- devops
- nuget
- unified workflow for managing artifact repositories, packages, and software supply chain governance.
- Software Developer
- managing software package lifecycle including publishing, versioning, and deprecation.
- create a new codeartifact repository within a domain
- list versions of a package in a repository
- associate external connection
- list package versions
- artifact repository
- sets up domains, repositories, and governance controls across teams.
- create domain
- get details about a codeartifact repository
- describe domain
- list repositories
- maven
- Platform Engineer
- pypi
- get repository endpoint
- list all codeartifact domains in the account
- manages repository infrastructure, external connections, and domain policies.
- software supply chain
slug: amazon-codeartifact-package-management
source_filename: amazon-codeartifact-package-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon CodeArtifact Package Management\n  description: Unified workflow for DevOps teams to manage artifact repositories, publish packages, control access, and govern software supply chains using Amazon CodeArtifact.\n  tags:\n  - Amazon\n  - AWS\n  - Package Management\n  - DevOps\n  - Artifact Repository\n  - Software Supply Chain\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: codeartifact\n    location: ./shared/codeartifact.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: package-management-api\n    description: Unified REST API for managing CodeArtifact packages and repositories.\n    resources:\n    - path: /v1/domains\n      name: domains\n      description: Manage CodeArtifact domains\n    - path: /v1/repositories\n \
  \     name: repositories\n      description: Manage CodeArtifact repositories\n    - path: /v1/packages\n      name: packages\n      description: Manage packages and package versions\n    - path: /v1/tokens\n      name: tokens\n      description: Get authorization tokens for package managers\n  - type: mcp\n    port: 9090\n    namespace: package-management-mcp\n    transport: http\n    description: MCP server for AI-assisted package repository management.\n    tools:\n    - name: list-domains\n      description: List all CodeArtifact domains in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeartifact.listDomains\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-repositories\n      description: List repositories in a domain\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeartifact.listRepositoriesInDomain\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: list-packages\n      description: List packages in a repository\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeartifact.listPackages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-package-versions\n      description: List versions of a package in a repository\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeartifact.listPackageVersions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-domain\n      description: Get details about a CodeArtifact domain\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeartifact.describeDomain\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-repository\n      description: Get details about a CodeArtifact repository\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeartifact.describeRepository\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: describe-package\n      description: Get details about a package in a repository\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeartifact.describePackage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-authorization-token\n      description: Generate a temporary authorization token for accessing CodeArtifact repositories\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codeartifact.getAuthorizationToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-domain\n      description: Create a new CodeArtifact domain\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codeartifact.createDomain\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-repository\n      description: Create a new CodeArtifact repository within a domain\n      hints:\n\
  \        readOnly: false\n        openWorld: false\n      call: codeartifact.createRepository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copy-package-versions\n      description: Copy package versions between repositories in the same domain\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codeartifact.copyPackageVersions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: associate-external-connection\n      description: Connect a repository to a public package registry like npmjs or PyPI\n      hints:\n        readOnly: false\n        openWorld: false\n      call: codeartifact.associateExternalConnection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-package-version\n      description: Publish a new package version to a repository\n      hints:\n        readOnly: false\n        destructive: false\n        openWorld: false\n      call: codeartifact.publishPackageVersion\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-package-versions\n      description: Delete specific package versions from a repository\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: codeartifact.deletePackageVersions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-repository-endpoint\n      description: Get the package-format-specific endpoint URL for a repository\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codeartifact.getRepositoryEndpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-codeartifact/refs/heads/main/capabilities/amazon-codeartifact-package-management.yaml
tags:
- Amazon
- AWS
- Package Management
- DevOps
- Artifact Repository
- Software Supply Chain
tools:
- description: List all CodeArtifact domains in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-domains
- description: List repositories in a domain
  hints:
    openWorld: true
    readOnly: true
  name: list-repositories
- description: List packages in a repository
  hints:
    openWorld: true
    readOnly: true
  name: list-packages
- description: List versions of a package in a repository
  hints:
    openWorld: true
    readOnly: true
  name: list-package-versions
- description: Get details about a CodeArtifact domain
  hints:
    openWorld: true
    readOnly: true
  name: describe-domain
- description: Get details about a CodeArtifact repository
  hints:
    openWorld: true
    readOnly: true
  name: describe-repository
- description: Get details about a package in a repository
  hints:
    openWorld: true
    readOnly: true
  name: describe-package
- description: Generate a temporary authorization token for accessing CodeArtifact repositories
  hints:
    openWorld: false
    readOnly: false
  name: get-authorization-token
- description: Create a new CodeArtifact domain
  hints:
    openWorld: false
    readOnly: false
  name: create-domain
- description: Create a new CodeArtifact repository within a domain
  hints:
    openWorld: false
    readOnly: false
  name: create-repository
- description: Copy package versions between repositories in the same domain
  hints:
    openWorld: false
    readOnly: false
  name: copy-package-versions
- description: Connect a repository to a public package registry like npmjs or PyPI
  hints:
    openWorld: false
    readOnly: false
  name: associate-external-connection
- description: Publish a new package version to a repository
  hints:
    destructive: false
    openWorld: false
    readOnly: false
  name: publish-package-version
- description: Delete specific package versions from a repository
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-package-versions
- description: Get the package-format-specific endpoint URL for a repository
  hints:
    openWorld: true
    readOnly: true
  name: get-repository-endpoint
---
