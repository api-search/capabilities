---
categories: []
consumed_apis: []
description: Workflow capability for discovering and evaluating Ruby gems using the RubyGems.org APIs. Combines search, gem metadata retrieval, version history, download statistics, and dependency analysis for developers choosing gems for their projects. Serves Ruby developers, DevOps teams, and security researchers evaluating the Ruby gem ecosystem.
layout: capability
name: RubyGems Gem Discovery
operations:
- description: Search RubyGems.org for gems by name or description
  method: GET
  name: search-gems
  path: /v1/gems/search
- description: Get detailed gem metadata
  method: GET
  name: get-gem
  path: /v1/gems/{gemName}
- description: List all published versions of a gem
  method: GET
  name: list-gem-versions
  path: /v1/gems/{gemName}/versions
- description: Get the latest version of a gem
  method: GET
  name: get-latest-version
  path: /v1/gems/{gemName}/versions/latest
- description: List gems depending on a specific gem
  method: GET
  name: get-reverse-dependencies
  path: /v1/gems/{gemName}/reverse-dependencies
- description: Get gem versions released in a timeframe
  method: GET
  name: get-timeframe-versions
  path: /v1/versions
personas: []
provider_name: RubyGems
provider_slug: rubygems
search_terms:
- get gem info
- get gem versions released in a timeframe
- get timeframe versions
- gems
- get reverse dependencies
- search for gems
- list all published versions of a gem
- package manager
- get detailed gem metadata
- rubygems
- get the latest version of a gem
- open source
- get recently released versions
- get gems that depend on this gem
- search gems
- get the latest published version number of a ruby gem
- developer tools
- discovery
- get gem details
- get gem
- ruby
- get gem owners
- list gem versions
- get detailed metadata for a specific ruby gem
- recently released gem versions
- get all gem versions
- get all gem versions released within a given timeframe (up to 7 days)
- list all published versions of a ruby gem with metadata
- find which ruby gems depend on a given gem (downstream impact analysis)
- get latest version
- search rubygems.org for ruby gems by name or description
- list the owners of a specific ruby gem
- search rubygems.org for gems by name or description
- get latest gem version
- list gems depending on a specific gem
slug: gem-discovery
source_filename: gem-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: RubyGems Gem Discovery\n  description: Workflow capability for discovering and evaluating Ruby gems using the RubyGems.org APIs. Combines search,\n    gem metadata retrieval, version history, download statistics, and dependency analysis for developers choosing gems for\n    their projects. Serves Ruby developers, DevOps teams, and security researchers evaluating the Ruby gem ecosystem.\n  tags:\n  - Ruby\n  - Gems\n  - Discovery\n  - Package Manager\n  - RubyGems\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RUBYGEMS_API_KEY: RUBYGEMS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: gems-api\n    baseUri: https://rubygems.org/api/v1\n    description: RubyGems Gems API v1 for gem metadata, ownership, and publishing\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{RUBYGEMS_API_KEY}}'\n      placement: header\n    resources:\n    - name: gems\n\
  \      path: /gems\n      description: Gem metadata and publishing operations\n      operations:\n      - name: get-gem-info\n        method: GET\n        description: Get detailed information about a specific gem by name\n        inputParameters:\n        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-owned-gems\n        method: GET\n        description: List gems owned by the authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: push-gem\n        method: POST\n        description: Submit a built gem to RubyGems.org\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: yank-gem\n\
  \        method: DELETE\n        description: Remove a specific gem version from RubyGems.org\n        inputParameters:\n        - name: gem_name\n          in: query\n          type: string\n          required: true\n          description: Gem name to yank\n        - name: version\n          in: query\n          type: string\n          required: true\n          description: Version to yank\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-reverse-dependencies\n        method: GET\n        description: Get list of gems that depend on a specific gem\n        inputParameters:\n        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: versions\n      path: /versions\n      description: Gem\
  \ version querying\n      operations:\n      - name: get-gem-versions\n        method: GET\n        description: Get all versions for a specific gem\n        inputParameters:\n        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-latest-gem-version\n        method: GET\n        description: Get the latest version of a gem\n        inputParameters:\n        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-timeframe-versions\n        method: GET\n        description: Get gem versions released within a timeframe\n        inputParameters:\n        - name: from\n\
  \          in: query\n          type: string\n          required: true\n          description: Start of timeframe (ISO 8601)\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of timeframe (ISO 8601)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: owners\n      path: /gems\n      description: Gem ownership management\n      operations:\n      - name: list-gem-owners\n        method: GET\n        description: List owners of a specific gem\n        inputParameters:\n        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-gem-owner\n        method: POST\n        description: Add an owner to a gem\n        inputParameters:\n\
  \        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        - name: email\n          in: body\n          type: string\n          required: true\n          description: Email of new owner\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-gem-owner\n        method: DELETE\n        description: Remove an owner from a gem\n        inputParameters:\n        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        - name: email\n          in: body\n          type: string\n          required: true\n          description: Email of owner to remove\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles\n      path: /profiles\n      description: User profile retrieval\n\
  \      operations:\n      - name: get-user-profile\n        method: GET\n        description: Get profile information for a user\n        inputParameters:\n        - name: userHandle\n          in: path\n          type: string\n          required: true\n          description: User handle or ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: search-api\n    baseUri: https://rubygems.org/api/v1\n    description: RubyGems Search API for gem discovery\n    resources:\n    - name: search\n      path: /search\n      description: Search for gems by name and description\n      operations:\n      - name: search-gems\n        method: GET\n        description: Search RubyGems.org for gems matching a query\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query string\n        - name: page\n\
  \          in: query\n          type: integer\n          required: false\n          description: Page number (30 results per page)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gem-discovery-api\n    description: Unified REST API for Ruby gem discovery and evaluation.\n    resources:\n    - path: /v1/gems/search\n      name: gem-search\n      description: Search for gems\n      operations:\n      - method: GET\n        name: search-gems\n        description: Search RubyGems.org for gems by name or description\n        call: search-api.search-gems\n        with:\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gems/{gemName}\n      name: gem-details\n      description: Get gem details\n      operations:\n      - method: GET\n        name: get-gem\n        description: Get detailed\
  \ gem metadata\n        call: gems-api.get-gem-info\n        with:\n          gemName: rest.gemName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gems/{gemName}/versions\n      name: gem-versions\n      description: Get all gem versions\n      operations:\n      - method: GET\n        name: list-gem-versions\n        description: List all published versions of a gem\n        call: gems-api.get-gem-versions\n        with:\n          gemName: rest.gemName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gems/{gemName}/versions/latest\n      name: latest-version\n      description: Get latest gem version\n      operations:\n      - method: GET\n        name: get-latest-version\n        description: Get the latest version of a gem\n        call: gems-api.get-latest-gem-version\n        with:\n          gemName: rest.gemName\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/gems/{gemName}/reverse-dependencies\n      name: reverse-deps\n      description: Get gems that depend on this gem\n      operations:\n      - method: GET\n        name: get-reverse-dependencies\n        description: List gems depending on a specific gem\n        call: gems-api.get-reverse-dependencies\n        with:\n          gemName: rest.gemName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/versions\n      name: recent-versions\n      description: Recently released gem versions\n      operations:\n      - method: GET\n        name: get-timeframe-versions\n        description: Get gem versions released in a timeframe\n        call: gems-api.get-timeframe-versions\n        with:\n          from: rest.from\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: gem-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted Ruby gem discovery and\
  \ evaluation.\n    tools:\n    - name: search-gems\n      description: Search RubyGems.org for Ruby gems by name or description\n      hints:\n        readOnly: true\n        openWorld: true\n      call: search-api.search-gems\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-gem-info\n      description: Get detailed metadata for a specific Ruby gem\n      hints:\n        readOnly: true\n        openWorld: false\n      call: gems-api.get-gem-info\n      with:\n        gemName: tools.gemName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-gem-versions\n      description: List all published versions of a Ruby gem with metadata\n      hints:\n        readOnly: true\n        openWorld: false\n      call: gems-api.get-gem-versions\n      with:\n        gemName: tools.gemName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-latest-gem-version\n\
  \      description: Get the latest published version number of a Ruby gem\n      hints:\n        readOnly: true\n        openWorld: false\n      call: gems-api.get-latest-gem-version\n      with:\n        gemName: tools.gemName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-reverse-dependencies\n      description: Find which Ruby gems depend on a given gem (downstream impact analysis)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: gems-api.get-reverse-dependencies\n      with:\n        gemName: tools.gemName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-gem-owners\n      description: List the owners of a specific Ruby gem\n      hints:\n        readOnly: true\n        openWorld: false\n      call: gems-api.list-gem-owners\n      with:\n        gemName: tools.gemName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-recently-released-versions\n  \
  \    description: Get all gem versions released within a given timeframe (up to 7 days)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: gems-api.get-timeframe-versions\n      with:\n        from: tools.from\n        to: tools.to\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rubygems/refs/heads/main/capabilities/gem-discovery.yaml
tags:
- Ruby
- Gems
- Discovery
- Package Manager
- RubyGems
tools:
- description: Search RubyGems.org for Ruby gems by name or description
  hints:
    openWorld: true
    readOnly: true
  name: search-gems
- description: Get detailed metadata for a specific Ruby gem
  hints:
    openWorld: false
    readOnly: true
  name: get-gem-info
- description: List all published versions of a Ruby gem with metadata
  hints:
    openWorld: false
    readOnly: true
  name: list-gem-versions
- description: Get the latest published version number of a Ruby gem
  hints:
    openWorld: false
    readOnly: true
  name: get-latest-gem-version
- description: Find which Ruby gems depend on a given gem (downstream impact analysis)
  hints:
    openWorld: false
    readOnly: true
  name: get-reverse-dependencies
- description: List the owners of a specific Ruby gem
  hints:
    openWorld: false
    readOnly: true
  name: get-gem-owners
- description: Get all gem versions released within a given timeframe (up to 7 days)
  hints:
    openWorld: false
    readOnly: true
  name: get-recently-released-versions
---
