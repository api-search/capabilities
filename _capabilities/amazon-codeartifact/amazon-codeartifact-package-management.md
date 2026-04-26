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
- Software Developer
- list domains
- manages repository infrastructure, external connections, and domain policies.
- create domain
- list all codeartifact domains in the account
- get details about a codeartifact repository
- storage and retrieval of software artifacts and their metadata.
- list repositories
- generate a temporary authorization token for accessing codeartifact repositories
- publish package version
- publish a new package version to a repository
- list packages in a repository
- publishes and consumes packages from codeartifact repositories.
- package management
- manage codeartifact domains
- aws
- managing software package lifecycle including publishing, versioning, and deprecation.
- describe package
- get the package-format-specific endpoint url for a repository
- copy package versions between repositories in the same domain
- delete package versions
- describe domain
- list versions of a package in a repository
- governance and security of external package dependencies and internal packages.
- get details about a package in a repository
- get authorization token
- create a new codeartifact repository within a domain
- manage packages and package versions
- describe repository
- associate external connection
- software supply chain
- unified workflow for managing artifact repositories, packages, and software supply chain governance.
- nuget
- copy package versions
- sets up domains, repositories, and governance controls across teams.
- npm
- list package versions
- devops
- get details about a codeartifact domain
- delete specific package versions from a repository
- create a new codeartifact domain
- Platform Engineer
- list packages
- connect a repository to a public package registry like npmjs or pypi
- get repository endpoint
- amazon
- DevOps Engineer
- list repositories in a domain
- create repository
- maven
- get authorization tokens for package managers
- manage codeartifact repositories
- artifact repository
- pypi
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
