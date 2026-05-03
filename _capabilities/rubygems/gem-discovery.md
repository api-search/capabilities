---
categories: []
consumed_apis:
- gems-api
- search-api
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
- list gems depending on a specific gem
- get all gem versions released within a given timeframe (up to 7 days)
- list all published versions of a ruby gem with metadata
- open source
- get gem
- search for gems
- get gem details
- get detailed metadata for a specific ruby gem
- package manager
- rubygems
- get timeframe versions
- list the owners of a specific ruby gem
- get detailed gem metadata
- search rubygems.org for ruby gems by name or description
- get gem owners
- get reverse dependencies
- get the latest published version number of a ruby gem
- developer tools
- get all gem versions
- gems
- list all published versions of a gem
- get gem info
- get the latest version of a gem
- discovery
- recently released gem versions
- ruby
- get gem versions released in a timeframe
- get gems that depend on this gem
- get latest gem version
- get latest version
- list gem versions
- search gems
- get recently released versions
- find which ruby gems depend on a given gem (downstream impact analysis)
- search rubygems.org for gems by name or description
slug: gem-discovery
source_filename: gem-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"RubyGems Gem Discovery\"\n  description: >-\n    Workflow capability for discovering and evaluating Ruby gems using the\n    RubyGems.org APIs. Combines search, gem metadata retrieval, version\n    history, download statistics, and dependency analysis for developers\n    choosing gems for their projects. Serves Ruby developers, DevOps teams,\n    and security researchers evaluating the Ruby gem ecosystem.\n  tags:\n    - Ruby\n    - Gems\n    - Discovery\n    - Package Manager\n    - RubyGems\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RUBYGEMS_API_KEY: RUBYGEMS_API_KEY\n\ncapability:\n  consumes:\n    - import: gems-api\n      location: ./shared/gems-api.yaml\n    - import: search-api\n      location: ./shared/search-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: gem-discovery-api\n      description: \"Unified REST API for Ruby gem discovery\
  \ and evaluation.\"\n      resources:\n        - path: /v1/gems/search\n          name: gem-search\n          description: \"Search for gems\"\n          operations:\n            - method: GET\n              name: search-gems\n              description: \"Search RubyGems.org for gems by name or description\"\n              call: \"search-api.search-gems\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/gems/{gemName}\n          name: gem-details\n          description: \"Get gem details\"\n          operations:\n            - method: GET\n              name: get-gem\n              description: \"Get detailed gem metadata\"\n              call: \"gems-api.get-gem-info\"\n              with:\n                gemName: \"rest.gemName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/gems/{gemName}/versions\n\
  \          name: gem-versions\n          description: \"Get all gem versions\"\n          operations:\n            - method: GET\n              name: list-gem-versions\n              description: \"List all published versions of a gem\"\n              call: \"gems-api.get-gem-versions\"\n              with:\n                gemName: \"rest.gemName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/gems/{gemName}/versions/latest\n          name: latest-version\n          description: \"Get latest gem version\"\n          operations:\n            - method: GET\n              name: get-latest-version\n              description: \"Get the latest version of a gem\"\n              call: \"gems-api.get-latest-gem-version\"\n              with:\n                gemName: \"rest.gemName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/gems/{gemName}/reverse-dependencies\n\
  \          name: reverse-deps\n          description: \"Get gems that depend on this gem\"\n          operations:\n            - method: GET\n              name: get-reverse-dependencies\n              description: \"List gems depending on a specific gem\"\n              call: \"gems-api.get-reverse-dependencies\"\n              with:\n                gemName: \"rest.gemName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/versions\n          name: recent-versions\n          description: \"Recently released gem versions\"\n          operations:\n            - method: GET\n              name: get-timeframe-versions\n              description: \"Get gem versions released in a timeframe\"\n              call: \"gems-api.get-timeframe-versions\"\n              with:\n                from: \"rest.from\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n\
  \      port: 9090\n      namespace: gem-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Ruby gem discovery and evaluation.\"\n      tools:\n        - name: search-gems\n          description: \"Search RubyGems.org for Ruby gems by name or description\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"search-api.search-gems\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-gem-info\n          description: \"Get detailed metadata for a specific Ruby gem\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"gems-api.get-gem-info\"\n          with:\n            gemName: \"tools.gemName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-gem-versions\n          description: \"List all published versions\
  \ of a Ruby gem with metadata\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"gems-api.get-gem-versions\"\n          with:\n            gemName: \"tools.gemName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-latest-gem-version\n          description: \"Get the latest published version number of a Ruby gem\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"gems-api.get-latest-gem-version\"\n          with:\n            gemName: \"tools.gemName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-reverse-dependencies\n          description: \"Find which Ruby gems depend on a given gem (downstream impact analysis)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"gems-api.get-reverse-dependencies\"\n          with:\n            gemName:\
  \ \"tools.gemName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-gem-owners\n          description: \"List the owners of a specific Ruby gem\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"gems-api.list-gem-owners\"\n          with:\n            gemName: \"tools.gemName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-recently-released-versions\n          description: \"Get all gem versions released within a given timeframe (up to 7 days)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"gems-api.get-timeframe-versions\"\n          with:\n            from: \"tools.from\"\n            to: \"tools.to\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
