---
categories: []
consumed_apis: []
description: Unified workflow capability for managing the complete Vagrant box lifecycle - from searching the public catalog and creating new boxes, to publishing versions and managing providers. Designed for DevOps engineers and platform teams automating development environment distribution via Vagrant Cloud.
layout: capability
name: Vagrant Box Lifecycle
operations:
- description: Search the Vagrant box catalog
  method: GET
  name: search-boxes
  path: /v1/boxes
- description: Create a new Vagrant box
  method: POST
  name: create-box
  path: /v1/boxes
- description: Get a specific Vagrant box
  method: GET
  name: get-box
  path: /v1/boxes/{username}/{name}
- description: Update a Vagrant box
  method: PUT
  name: update-box
  path: /v1/boxes/{username}/{name}
- description: Delete a Vagrant box
  method: DELETE
  name: delete-box
  path: /v1/boxes/{username}/{name}
- description: Create a new version for a box
  method: POST
  name: create-version
  path: /v1/boxes/{username}/{name}/versions
- description: Get a specific box version
  method: GET
  name: get-version
  path: /v1/boxes/{username}/{name}/versions/{version}
- description: Publish a box version
  method: PUT
  name: release-version
  path: /v1/boxes/{username}/{name}/versions/{version}/release
personas: []
provider_name: Vagrant
provider_slug: vagrant
search_terms:
- get a specific vagrant box
- search and create vagrant boxes
- vagrant
- search the vagrant box catalog
- individual version management
- publish a box version
- get a specific box version details
- infrastructure
- development environments
- devops
- search the public vagrant box catalog
- create a new vagrant box
- virtualization
- cloud
- boxes
- hashicorp
- get details for a specific vagrant box
- release a box version
- create version
- get a specific box version
- create a new version for a vagrant box
- delete box
- ci/cd
- get version
- update a vagrant box metadata
- create a new vagrant box in the registry
- search boxes
- individual box management
- release version
- update box
- delete a vagrant box
- box version management
- create a new version for a box
- update a vagrant box
- get box
- publish a box version to make it available for download
- create box
slug: box-lifecycle
source_filename: box-lifecycle.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vagrant Box Lifecycle\n  description: Unified workflow capability for managing the complete Vagrant box lifecycle - from searching the public catalog\n    and creating new boxes, to publishing versions and managing providers. Designed for DevOps engineers and platform teams\n    automating development environment distribution via Vagrant Cloud.\n  tags:\n  - DevOps\n  - Virtualization\n  - Vagrant\n  - Boxes\n  - HashiCorp\n  - CI/CD\n  - Infrastructure\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VAGRANT_CLOUD_TOKEN: VAGRANT_CLOUD_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: vagrant-cloud\n    baseUri: https://app.vagrantup.com/api/v2\n    description: Vagrant Cloud API for box lifecycle management\n    authentication:\n      type: bearer\n      token: '{{VAGRANT_CLOUD_TOKEN}}'\n    resources:\n    - name: search\n      path: /search\n      description: Search the public\
  \ Vagrant box catalog\n      operations:\n      - name: search-boxes\n        method: GET\n        description: Search for Vagrant boxes in the public catalog\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: provider\n          in: query\n          type: string\n          required: false\n          description: Filter by provider\n        - name: architecture\n          in: query\n          type: string\n          required: false\n          description: Filter by architecture\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort by downloads, updated, or created\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: boxes\n      path: /boxes\n      description: Manage Vagrant boxes\n      operations:\n      - name: create-box\n        method: POST\n        description: Create a new Vagrant box\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            name: '{{tools.name}}'\n            short_description: '{{tools.short_description}}'\n            is_private: '{{tools.is_private}}'\n    - name: box\n      path: /box/{username}/{name}\n      description: Individual box management\n      operations:\n      - name: get-box\n        method: GET\n        description: Retrieve a specific Vagrant box\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Box owner username\n\
  \        - name: name\n          in: path\n          type: string\n          required: true\n          description: Box name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-box\n        method: PUT\n        description: Update a Vagrant box\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Box owner username\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Box name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-box\n        method: DELETE\n        description: Delete a Vagrant box\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Box\
  \ owner username\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Box name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: versions\n      path: /box/{username}/{name}/versions\n      description: Box versions management\n      operations:\n      - name: create-version\n        method: POST\n        description: Create a new version for a box\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Box owner username\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Box name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: version\n      path: /box/{username}/{name}/version/{version}\n  \
  \    description: Individual version management\n      operations:\n      - name: get-version\n        method: GET\n        description: Retrieve a specific box version\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: version\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: release-version\n        method: PUT\n        description: Release a version making it available for download\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: version\n          in: path\n         \
  \ type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: box-lifecycle-api\n    description: Unified REST API for Vagrant box lifecycle management.\n    resources:\n    - path: /v1/boxes\n      name: boxes\n      description: Search and create Vagrant boxes\n      operations:\n      - method: GET\n        name: search-boxes\n        description: Search the Vagrant box catalog\n        call: vagrant-cloud.search-boxes\n        with:\n          q: rest.q\n          provider: rest.provider\n          sort: rest.sort\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-box\n        description: Create a new Vagrant box\n        call: vagrant-cloud.create-box\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/boxes/{username}/{name}\n      name: box\n      description: Individual box management\n      operations:\n      - method: GET\n        name: get-box\n        description: Get a specific Vagrant box\n        call: vagrant-cloud.get-box\n        with:\n          username: rest.username\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-box\n        description: Update a Vagrant box\n        call: vagrant-cloud.update-box\n        with:\n          username: rest.username\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-box\n        description: Delete a Vagrant box\n        call: vagrant-cloud.delete-box\n        with:\n          username: rest.username\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/boxes/{username}/{name}/versions\n\
  \      name: versions\n      description: Box version management\n      operations:\n      - method: POST\n        name: create-version\n        description: Create a new version for a box\n        call: vagrant-cloud.create-version\n        with:\n          username: rest.username\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/boxes/{username}/{name}/versions/{version}\n      name: version\n      description: Individual version management\n      operations:\n      - method: GET\n        name: get-version\n        description: Get a specific box version\n        call: vagrant-cloud.get-version\n        with:\n          username: rest.username\n          name: rest.name\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/boxes/{username}/{name}/versions/{version}/release\n      name: version-release\n      description: Release a box version\n   \
  \   operations:\n      - method: PUT\n        name: release-version\n        description: Publish a box version\n        call: vagrant-cloud.release-version\n        with:\n          username: rest.username\n          name: rest.name\n          version: rest.version\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: box-lifecycle-mcp\n    transport: http\n    description: MCP server for AI-assisted Vagrant box lifecycle management.\n    tools:\n    - name: search-boxes\n      description: Search the public Vagrant box catalog\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vagrant-cloud.search-boxes\n      with:\n        q: tools.q\n        provider: tools.provider\n        sort: tools.sort\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-box\n      description: Get details for a specific Vagrant box\n      hints:\n        readOnly:\
  \ true\n        idempotent: true\n      call: vagrant-cloud.get-box\n      with:\n        username: tools.username\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-box\n      description: Create a new Vagrant box in the registry\n      hints:\n        readOnly: false\n      call: vagrant-cloud.create-box\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-box\n      description: Update a Vagrant box metadata\n      hints:\n        readOnly: false\n        idempotent: true\n      call: vagrant-cloud.update-box\n      with:\n        username: tools.username\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-box\n      description: Delete a Vagrant box\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: vagrant-cloud.delete-box\n      with:\n        username: tools.username\n\
  \        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-version\n      description: Create a new version for a Vagrant box\n      hints:\n        readOnly: false\n      call: vagrant-cloud.create-version\n      with:\n        username: tools.username\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-version\n      description: Get a specific box version details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vagrant-cloud.get-version\n      with:\n        username: tools.username\n        name: tools.name\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: release-version\n      description: Publish a box version to make it available for download\n      hints:\n        readOnly: false\n        idempotent: true\n      call: vagrant-cloud.release-version\n      with:\n        username:\
  \ tools.username\n        name: tools.name\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vagrant/refs/heads/main/capabilities/box-lifecycle.yaml
tags:
- DevOps
- Virtualization
- Vagrant
- Boxes
- HashiCorp
- CI/CD
- Infrastructure
tools:
- description: Search the public Vagrant box catalog
  hints:
    openWorld: true
    readOnly: true
  name: search-boxes
- description: Get details for a specific Vagrant box
  hints:
    idempotent: true
    readOnly: true
  name: get-box
- description: Create a new Vagrant box in the registry
  hints:
    readOnly: false
  name: create-box
- description: Update a Vagrant box metadata
  hints:
    idempotent: true
    readOnly: false
  name: update-box
- description: Delete a Vagrant box
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-box
- description: Create a new version for a Vagrant box
  hints:
    readOnly: false
  name: create-version
- description: Get a specific box version details
  hints:
    idempotent: true
    readOnly: true
  name: get-version
- description: Publish a box version to make it available for download
  hints:
    idempotent: true
    readOnly: false
  name: release-version
---
