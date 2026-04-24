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
- npm
- get authorization tokens for package managers
- artifact repository
- storage and retrieval of software artifacts and their metadata.
- software supply chain
- manages repository infrastructure, external connections, and domain policies.
- Platform Engineer
- package management
- list repositories
- delete specific package versions from a repository
- devops
- connect a repository to a public package registry like npmjs or pypi
- get details about a codeartifact domain
- describe domain
- describe repository
- list packages in a repository
- copy package versions
- manage packages and package versions
- list package versions
- list versions of a package in a repository
- manage codeartifact domains
- list domains
- Software Developer
- associate external connection
- get details about a codeartifact repository
- managing software package lifecycle including publishing, versioning, and deprecation.
- get the package-format-specific endpoint url for a repository
- copy package versions between repositories in the same domain
- create domain
- list packages
- publish package version
- pypi
- publish a new package version to a repository
- list all codeartifact domains in the account
- get details about a package in a repository
- generate a temporary authorization token for accessing codeartifact repositories
- governance and security of external package dependencies and internal packages.
- create a new codeartifact domain
- get authorization token
- unified workflow for managing artifact repositories, packages, and software supply chain governance.
- sets up domains, repositories, and governance controls across teams.
- aws
- maven
- delete package versions
- get repository endpoint
- nuget
- manage codeartifact repositories
- create a new codeartifact repository within a domain
- amazon
- describe package
- list repositories in a domain
- create repository
- publishes and consumes packages from codeartifact repositories.
- DevOps Engineer
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
