---
api_specs:
- filename: rescuegroups-org-openapi.yml
  format: yaml
  label: rescuegroups
  slug: rescuegroups
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/rescuegroups-org/refs/heads/main/openapi/rescuegroups-org-openapi.yml
categories: []
consumed_apis:
- rescuegroups
description: Workflow capability for searching and discovering adoptable pets and rescue organizations. Enables geographic search, breed/species filtering, and organization lookup for pet adoption platforms, rescue directories, and shelter management integrations.
layout: capability
name: RescueGroups.org Pet Adoption Search
operations:
- description: List all available adoptable animals
  method: GET
  name: list-animals
  path: /v1/animals
- description: Get details for a single adoptable animal
  method: GET
  name: get-animal
  path: /v1/animals/{id}
- description: Search animals with breed, species, location, and geodistance filters
  method: POST
  name: search-animals
  path: /v1/animals/search
- description: List all rescue organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: Get details for a single rescue organization
  method: GET
  name: get-organization
  path: /v1/organizations/{id}
- description: List all available animal breeds
  method: GET
  name: list-breeds
  path: /v1/breeds
- description: List all animal species
  method: GET
  name: list-species
  path: /v1/species
- description: List all animal colors
  method: GET
  name: list-colors
  path: /v1/colors
- description: List all animal coat patterns
  method: GET
  name: list-patterns
  path: /v1/patterns
- description: Get a pet list by keystring
  method: GET
  name: get-pet-list
  path: /v1/pet-lists/{keystring}
personas: []
provider_name: RescueGroups.org
provider_slug: rescuegroups-org
search_terms:
- get complete details for a specific adoptable animal by id
- get details for a specific rescue organization including adoption process and service areas
- animals
- search animals with breed, species, location, and geodistance filters
- rescue organizations and shelters
- list all animal colors
- search adoptable animals by breed, species, age, size, location, and distance
- find rescue organizations and shelters near a location
- get organization details
- list all animal coat patterns
- list all animal species
- list patterns
- get animal details
- look up all available animal coat pattern classifications
- list all rescue organizations
- list breeds
- get a rescue organization's pet list by keystring
- pet adoption
- animal species reference data
- list organizations
- list all available animal breeds
- organization pet lists
- search
- get org pet list
- animal coat pattern reference data
- get pet list
- get organization
- list available adoptable animals with optional filtering
- list all available adoptable animals
- list colors
- animal breed reference data
- look up all available animal breed classifications
- search animals by criteria
- get details for a single adoptable animal
- list species
- lookup animal breeds
- lookup animal species
- animal color reference data
- rescue
- single adoptable animal
- look up all available animal species classifications
- organizations
- get animal
- search and list adoptable animals
- list animals
- list adoptable animals
- single rescue organization
- get a pet list by keystring
- search animals
- find rescue organizations
- look up all available animal color classifications
- get details for a single rescue organization
- animal welfare
- lookup animal patterns
- advanced animal search
- lookup animal colors
slug: pet-adoption-search
source_filename: pet-adoption-search.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"RescueGroups.org Pet Adoption Search\"\n  description: >-\n    Workflow capability for searching and discovering adoptable pets and rescue\n    organizations. Enables geographic search, breed/species filtering, and\n    organization lookup for pet adoption platforms, rescue directories, and\n    shelter management integrations.\n  tags:\n    - Animals\n    - Pet Adoption\n    - Rescue\n    - Organizations\n    - Animal Welfare\n    - Search\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RESCUEGROUPS_API_KEY: RESCUEGROUPS_API_KEY\n\ncapability:\n  consumes:\n    - import: rescuegroups\n      location: ./shared/rescuegroups-org.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: pet-adoption-search-api\n      description: \"Unified REST API for pet adoption search and discovery.\"\n      resources:\n        - path: /v1/animals\n          name: animals\n\
  \          description: \"Search and list adoptable animals\"\n          operations:\n            - method: GET\n              name: list-animals\n              description: \"List all available adoptable animals\"\n              call: \"rescuegroups.list-public-animals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/animals/{id}\n          name: animal\n          description: \"Single adoptable animal\"\n          operations:\n            - method: GET\n              name: get-animal\n              description: \"Get details for a single adoptable animal\"\n              call: \"rescuegroups.get-public-animal\"\n              with:\n                animal_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/animals/search\n          name: animal-search\n          description: \"Advanced animal search\"\n          operations:\n \
  \           - method: POST\n              name: search-animals\n              description: \"Search animals with breed, species, location, and geodistance filters\"\n              call: \"rescuegroups.search-public-animals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations\n          name: organizations\n          description: \"Rescue organizations and shelters\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List all rescue organizations\"\n              call: \"rescuegroups.list-public-orgs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{id}\n          name: organization\n          description: \"Single rescue organization\"\n          operations:\n            - method: GET\n              name: get-organization\n              description:\
  \ \"Get details for a single rescue organization\"\n              call: \"rescuegroups.get-public-org\"\n              with:\n                org_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/breeds\n          name: breeds\n          description: \"Animal breed reference data\"\n          operations:\n            - method: GET\n              name: list-breeds\n              description: \"List all available animal breeds\"\n              call: \"rescuegroups.list-animal-breeds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/species\n          name: species\n          description: \"Animal species reference data\"\n          operations:\n            - method: GET\n              name: list-species\n              description: \"List all animal species\"\n              call: \"rescuegroups.list-animal-species\"\n             \
  \ outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/colors\n          name: colors\n          description: \"Animal color reference data\"\n          operations:\n            - method: GET\n              name: list-colors\n              description: \"List all animal colors\"\n              call: \"rescuegroups.list-animal-colors\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/patterns\n          name: patterns\n          description: \"Animal coat pattern reference data\"\n          operations:\n            - method: GET\n              name: list-patterns\n              description: \"List all animal coat patterns\"\n              call: \"rescuegroups.list-animal-patterns\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pet-lists/{keystring}\n          name: pet-list\n          description:\
  \ \"Organization pet lists\"\n          operations:\n            - method: GET\n              name: get-pet-list\n              description: \"Get a pet list by keystring\"\n              call: \"rescuegroups.get-pet-list\"\n              with:\n                keystring: \"rest.keystring\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: pet-adoption-search-mcp\n      transport: http\n      description: \"MCP server for AI-assisted pet adoption search and rescue organization discovery.\"\n      tools:\n        - name: list-adoptable-animals\n          description: \"List available adoptable animals with optional filtering\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rescuegroups.list-public-animals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-animal-details\n      \
  \    description: \"Get complete details for a specific adoptable animal by ID\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rescuegroups.get-public-animal\"\n          with:\n            animal_id: \"tools.animal_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-animals-by-criteria\n          description: \"Search adoptable animals by breed, species, age, size, location, and distance\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rescuegroups.search-public-animals\"\n          with:\n            view_name: \"tools.view_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-rescue-organizations\n          description: \"Find rescue organizations and shelters near a location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"rescuegroups.list-public-orgs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-organization-details\n          description: \"Get details for a specific rescue organization including adoption process and service areas\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rescuegroups.get-public-org\"\n          with:\n            org_id: \"tools.org_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-animal-breeds\n          description: \"Look up all available animal breed classifications\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rescuegroups.list-animal-breeds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-animal-species\n          description: \"Look up all available animal species classifications\"\
  \n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rescuegroups.list-animal-species\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-animal-colors\n          description: \"Look up all available animal color classifications\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rescuegroups.list-animal-colors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-animal-patterns\n          description: \"Look up all available animal coat pattern classifications\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rescuegroups.list-animal-patterns\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-org-pet-list\n          description: \"Get a rescue organization's pet list by keystring\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rescuegroups.get-pet-list\"\n          with:\n            keystring: \"tools.keystring\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rescuegroups-org/refs/heads/main/capabilities/pet-adoption-search.yaml
tags:
- Animals
- Pet Adoption
- Rescue
- Organizations
- Animal Welfare
- Search
tools:
- description: List available adoptable animals with optional filtering
  hints:
    openWorld: true
    readOnly: true
  name: list-adoptable-animals
- description: Get complete details for a specific adoptable animal by ID
  hints:
    openWorld: true
    readOnly: true
  name: get-animal-details
- description: Search adoptable animals by breed, species, age, size, location, and distance
  hints:
    openWorld: true
    readOnly: true
  name: search-animals-by-criteria
- description: Find rescue organizations and shelters near a location
  hints:
    openWorld: true
    readOnly: true
  name: find-rescue-organizations
- description: Get details for a specific rescue organization including adoption process and service areas
  hints:
    openWorld: true
    readOnly: true
  name: get-organization-details
- description: Look up all available animal breed classifications
  hints:
    openWorld: false
    readOnly: true
  name: lookup-animal-breeds
- description: Look up all available animal species classifications
  hints:
    openWorld: false
    readOnly: true
  name: lookup-animal-species
- description: Look up all available animal color classifications
  hints:
    openWorld: false
    readOnly: true
  name: lookup-animal-colors
- description: Look up all available animal coat pattern classifications
  hints:
    openWorld: false
    readOnly: true
  name: lookup-animal-patterns
- description: Get a rescue organization's pet list by keystring
  hints:
    openWorld: true
    readOnly: true
  name: get-org-pet-list
---
