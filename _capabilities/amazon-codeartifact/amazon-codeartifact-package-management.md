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
- nuget
- list package versions
- create a new codeartifact repository within a domain
- npm
- sets up domains, repositories, and governance controls across teams.
- list domains
- create a new codeartifact domain
- pypi
- copy package versions
- manage packages and package versions
- get details about a codeartifact domain
- manage codeartifact repositories
- get repository endpoint
- list packages
- list versions of a package in a repository
- publish a new package version to a repository
- Platform Engineer
- publishes and consumes packages from codeartifact repositories.
- artifact repository
- describe package
- manages repository infrastructure, external connections, and domain policies.
- amazon
- manage codeartifact domains
- unified workflow for managing artifact repositories, packages, and software supply chain governance.
- delete specific package versions from a repository
- devops
- describe domain
- storage and retrieval of software artifacts and their metadata.
- generate a temporary authorization token for accessing codeartifact repositories
- delete package versions
- managing software package lifecycle including publishing, versioning, and deprecation.
- list repositories in a domain
- get details about a package in a repository
- software supply chain
- copy package versions between repositories in the same domain
- get the package-format-specific endpoint url for a repository
- get authorization token
- governance and security of external package dependencies and internal packages.
- DevOps Engineer
- get authorization tokens for package managers
- list packages in a repository
- package management
- connect a repository to a public package registry like npmjs or pypi
- list all codeartifact domains in the account
- create repository
- maven
- aws
- create domain
- publish package version
- Software Developer
- get details about a codeartifact repository
- list repositories
- associate external connection
- describe repository
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
