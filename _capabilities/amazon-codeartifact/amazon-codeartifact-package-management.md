---
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
- list domains
- manage codeartifact domains
- list packages
- create a new codeartifact domain
- sets up domains, repositories, and governance controls across teams.
- get details about a package in a repository
- governance and security of external package dependencies and internal packages.
- manage packages and package versions
- list packages in a repository
- Platform Engineer
- delete specific package versions from a repository
- nuget
- get details about a codeartifact domain
- associate external connection
- list repositories
- list all codeartifact domains in the account
- create domain
- copy package versions between repositories in the same domain
- get repository endpoint
- package management
- DevOps Engineer
- list repositories in a domain
- get authorization tokens for package managers
- get the package-format-specific endpoint url for a repository
- publish a new package version to a repository
- Software Developer
- list package versions
- copy package versions
- npm
- pypi
- storage and retrieval of software artifacts and their metadata.
- delete package versions
- describe package
- aws
- generate a temporary authorization token for accessing codeartifact repositories
- describe repository
- manages repository infrastructure, external connections, and domain policies.
- describe domain
- get authorization token
- create a new codeartifact repository within a domain
- create repository
- devops
- publish package version
- publishes and consumes packages from codeartifact repositories.
- connect a repository to a public package registry like npmjs or pypi
- software supply chain
- amazon
- maven
- unified workflow for managing artifact repositories, packages, and software supply chain governance.
- manage codeartifact repositories
- artifact repository
- list versions of a package in a repository
- get details about a codeartifact repository
- managing software package lifecycle including publishing, versioning, and deprecation.
slug: amazon-codeartifact-package-management
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
