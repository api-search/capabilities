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
- get details about a codeartifact domain
- manages repository infrastructure, external connections, and domain policies.
- devops
- associate external connection
- artifact repository
- list repositories
- delete package versions
- DevOps Engineer
- governance and security of external package dependencies and internal packages.
- managing software package lifecycle including publishing, versioning, and deprecation.
- npm
- nuget
- get authorization tokens for package managers
- amazon
- connect a repository to a public package registry like npmjs or pypi
- storage and retrieval of software artifacts and their metadata.
- manage codeartifact domains
- manage packages and package versions
- create a new codeartifact domain
- sets up domains, repositories, and governance controls across teams.
- aws
- get authorization token
- create repository
- create domain
- list packages in a repository
- pypi
- list all codeartifact domains in the account
- describe domain
- get details about a package in a repository
- describe package
- get repository endpoint
- package management
- list versions of a package in a repository
- get the package-format-specific endpoint url for a repository
- describe repository
- Platform Engineer
- Software Developer
- list packages
- generate a temporary authorization token for accessing codeartifact repositories
- publish a new package version to a repository
- list domains
- list repositories in a domain
- list package versions
- publish package version
- maven
- copy package versions between repositories in the same domain
- software supply chain
- delete specific package versions from a repository
- copy package versions
- unified workflow for managing artifact repositories, packages, and software supply chain governance.
- get details about a codeartifact repository
- publishes and consumes packages from codeartifact repositories.
- manage codeartifact repositories
- create a new codeartifact repository within a domain
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
