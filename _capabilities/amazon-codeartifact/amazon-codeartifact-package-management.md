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
- create repository
- publish a new package version to a repository
- package management
- sets up domains, repositories, and governance controls across teams.
- get authorization tokens for package managers
- artifact repository
- storage and retrieval of software artifacts and their metadata.
- list all codeartifact domains in the account
- list repositories
- get details about a codeartifact repository
- delete specific package versions from a repository
- get repository endpoint
- unified workflow for managing artifact repositories, packages, and software supply chain governance.
- governance and security of external package dependencies and internal packages.
- Software Developer
- pypi
- get details about a package in a repository
- managing software package lifecycle including publishing, versioning, and deprecation.
- describe domain
- generate a temporary authorization token for accessing codeartifact repositories
- get the package-format-specific endpoint url for a repository
- copy package versions between repositories in the same domain
- manage codeartifact repositories
- publish package version
- delete package versions
- list domains
- DevOps Engineer
- list packages in a repository
- publishes and consumes packages from codeartifact repositories.
- get details about a codeartifact domain
- create a new codeartifact domain
- manages repository infrastructure, external connections, and domain policies.
- describe repository
- manage codeartifact domains
- list package versions
- copy package versions
- connect a repository to a public package registry like npmjs or pypi
- devops
- associate external connection
- get authorization token
- list packages
- describe package
- list versions of a package in a repository
- maven
- create domain
- nuget
- aws
- create a new codeartifact repository within a domain
- npm
- list repositories in a domain
- manage packages and package versions
- amazon
- software supply chain
- Platform Engineer
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
