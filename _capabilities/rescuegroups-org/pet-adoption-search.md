---
categories: []
consumed_apis: []
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
- get org pet list
- lookup animal patterns
- rescue organizations and shelters
- animal species reference data
- single adoptable animal
- look up all available animal breed classifications
- get details for a single rescue organization
- list breeds
- search adoptable animals by breed, species, age, size, location, and distance
- get animal details
- get a pet list by keystring
- animals
- look up all available animal coat pattern classifications
- pet adoption
- search animals with breed, species, location, and geodistance filters
- find rescue organizations and shelters near a location
- animal coat pattern reference data
- lookup animal breeds
- lookup animal colors
- list patterns
- rescue
- list animals
- list all animal coat patterns
- find rescue organizations
- look up all available animal species classifications
- search animals
- get animal
- get complete details for a specific adoptable animal by id
- list adoptable animals
- lookup animal species
- get details for a specific rescue organization including adoption process and service areas
- list all animal colors
- get organization details
- list colors
- get pet list
- list available adoptable animals with optional filtering
- list all animal species
- get details for a single adoptable animal
- list organizations
- single rescue organization
- search animals by criteria
- organization pet lists
- look up all available animal color classifications
- animal welfare
- get a rescue organization's pet list by keystring
- list all rescue organizations
- search
- list species
- search and list adoptable animals
- animal breed reference data
- animal color reference data
- list all available animal breeds
- get organization
- organizations
- advanced animal search
- list all available adoptable animals
slug: pet-adoption-search
source_filename: pet-adoption-search.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: RescueGroups.org Pet Adoption Search\n  description: Workflow capability for searching and discovering adoptable pets and rescue organizations. Enables geographic\n    search, breed/species filtering, and organization lookup for pet adoption platforms, rescue directories, and shelter management\n    integrations.\n  tags:\n  - Animals\n  - Pet Adoption\n  - Rescue\n  - Organizations\n  - Animal Welfare\n  - Search\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RESCUEGROUPS_API_KEY: RESCUEGROUPS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: rescuegroups\n    baseUri: https://api.rescuegroups.org/v5\n    description: RescueGroups.org REST API v5 for adoptable pet data\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{RESCUEGROUPS_API_KEY}}'\n      placement: header\n    resources:\n    - name: public-animals\n      path: /public/animals\n  \
  \    description: Public adoptable animal records\n      operations:\n      - name: list-public-animals\n        method: GET\n        description: Retrieve a paginated list of public adoptable animals\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for paginated results\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page (max 250)\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort field with +/- prefix\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-public-animal\n        method: GET\n        description: Retrieve a single public adoptable animal by ID\n        inputParameters:\n        - name: animal_id\n          in:\
  \ path\n          type: string\n          required: true\n          description: The unique animal identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-public-animals\n        method: POST\n        description: Search public adoptable animals using filters, views, and geodistance\n        inputParameters:\n        - name: view_name\n          in: path\n          type: string\n          required: true\n          description: Predefined view name (e.g., available, cats, dogs)\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n  \
  \        type: json\n          data:\n            data:\n              filters: '{{tools.filters}}'\n              geodistance: '{{tools.geodistance}}'\n    - name: public-orgs\n      path: /public/orgs\n      description: Public rescue organization records\n      operations:\n      - name: list-public-orgs\n        method: GET\n        description: Retrieve a paginated list of public rescue organizations\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-public-org\n        method: GET\n        description: Retrieve a single public rescue organization by ID\n        inputParameters:\n        - name: org_id\n\
  \          in: path\n          type: string\n          required: true\n          description: The unique organization identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reference-data\n      path: /public/animals\n      description: Animal reference data (breeds, species, colors, patterns)\n      operations:\n      - name: list-animal-breeds\n        method: GET\n        description: Retrieve all animal breed reference values\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-animal-species\n        method: GET\n        description: Retrieve all animal species reference values\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-animal-colors\n        method: GET\n        description: Retrieve all animal\
  \ color reference values\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-animal-patterns\n        method: GET\n        description: Retrieve all animal pattern reference values\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pet-lists\n      path: /public/petlists\n      description: Organization pet lists\n      operations:\n      - name: get-pet-list\n        method: GET\n        description: Retrieve a pet list by its keystring\n        inputParameters:\n        - name: keystring\n          in: path\n          type: string\n          required: true\n          description: The pet list keystring identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pet-adoption-search-api\n\
  \    description: Unified REST API for pet adoption search and discovery.\n    resources:\n    - path: /v1/animals\n      name: animals\n      description: Search and list adoptable animals\n      operations:\n      - method: GET\n        name: list-animals\n        description: List all available adoptable animals\n        call: rescuegroups.list-public-animals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/animals/{id}\n      name: animal\n      description: Single adoptable animal\n      operations:\n      - method: GET\n        name: get-animal\n        description: Get details for a single adoptable animal\n        call: rescuegroups.get-public-animal\n        with:\n          animal_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/animals/search\n      name: animal-search\n      description: Advanced animal search\n      operations:\n      - method: POST\n        name: search-animals\n\
  \        description: Search animals with breed, species, location, and geodistance filters\n        call: rescuegroups.search-public-animals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations\n      name: organizations\n      description: Rescue organizations and shelters\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List all rescue organizations\n        call: rescuegroups.list-public-orgs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{id}\n      name: organization\n      description: Single rescue organization\n      operations:\n      - method: GET\n        name: get-organization\n        description: Get details for a single rescue organization\n        call: rescuegroups.get-public-org\n        with:\n          org_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/breeds\n\
  \      name: breeds\n      description: Animal breed reference data\n      operations:\n      - method: GET\n        name: list-breeds\n        description: List all available animal breeds\n        call: rescuegroups.list-animal-breeds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/species\n      name: species\n      description: Animal species reference data\n      operations:\n      - method: GET\n        name: list-species\n        description: List all animal species\n        call: rescuegroups.list-animal-species\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/colors\n      name: colors\n      description: Animal color reference data\n      operations:\n      - method: GET\n        name: list-colors\n        description: List all animal colors\n        call: rescuegroups.list-animal-colors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/patterns\n    \
  \  name: patterns\n      description: Animal coat pattern reference data\n      operations:\n      - method: GET\n        name: list-patterns\n        description: List all animal coat patterns\n        call: rescuegroups.list-animal-patterns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pet-lists/{keystring}\n      name: pet-list\n      description: Organization pet lists\n      operations:\n      - method: GET\n        name: get-pet-list\n        description: Get a pet list by keystring\n        call: rescuegroups.get-pet-list\n        with:\n          keystring: rest.keystring\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pet-adoption-search-mcp\n    transport: http\n    description: MCP server for AI-assisted pet adoption search and rescue organization discovery.\n    tools:\n    - name: list-adoptable-animals\n      description: List available adoptable animals with\
  \ optional filtering\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rescuegroups.list-public-animals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-animal-details\n      description: Get complete details for a specific adoptable animal by ID\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rescuegroups.get-public-animal\n      with:\n        animal_id: tools.animal_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-animals-by-criteria\n      description: Search adoptable animals by breed, species, age, size, location, and distance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rescuegroups.search-public-animals\n      with:\n        view_name: tools.view_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-rescue-organizations\n      description: Find rescue organizations and shelters near\
  \ a location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rescuegroups.list-public-orgs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-organization-details\n      description: Get details for a specific rescue organization including adoption process and service areas\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rescuegroups.get-public-org\n      with:\n        org_id: tools.org_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-animal-breeds\n      description: Look up all available animal breed classifications\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rescuegroups.list-animal-breeds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-animal-species\n      description: Look up all available animal species classifications\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: rescuegroups.list-animal-species\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-animal-colors\n      description: Look up all available animal color classifications\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rescuegroups.list-animal-colors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-animal-patterns\n      description: Look up all available animal coat pattern classifications\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rescuegroups.list-animal-patterns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-org-pet-list\n      description: Get a rescue organization's pet list by keystring\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rescuegroups.get-pet-list\n      with:\n        keystring: tools.keystring\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n"
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
