---
categories:
- content-management
consumed_apis:
- pluralsight-content-catalog
- pluralsight-content-slug
- pluralsight-course-catalog
- pluralsight-public-course-catalog
- pluralsight-channels
- pluralsight-learning-paths
- pluralsight-programs
- pluralsight-labs
- pluralsight-tags
description: Unified workflow for L&D managers and content administrators to browse, organize, and manage learning content across courses, channels, learning paths, programs, labs, and tags. Combines content catalog, course catalog, public catalog, channels, learning paths, programs, labs, content slugs, and tags APIs.
layout: capability
name: Pluralsight Learning Content Management
operations:
- description: Query the general content catalog
  method: POST
  name: query-content-catalog
  path: /v1/content-catalog
- description: Resolve content slugs to internal identifiers
  method: POST
  name: query-content-slugs
  path: /v1/content-slugs
- description: Query the course catalog
  method: POST
  name: query-course-catalog
  path: /v1/course-catalog
- description: Retrieve the full public course catalog
  method: GET
  name: get-public-course-catalog
  path: /v1/public-courses
- description: Query and manage content channels
  method: POST
  name: manage-channels
  path: /v1/channels
- description: Query learning path catalog data
  method: POST
  name: query-learning-paths
  path: /v1/learning-paths
- description: Query the program catalog
  method: POST
  name: query-programs
  path: /v1/programs
- description: Query lab catalog and activity data
  method: POST
  name: query-labs
  path: /v1/labs
- description: Query content tags and taxonomy data
  method: POST
  name: query-tags
  path: /v1/tags
personas: []
provider_name: Pluralsight
provider_slug: pluralsight
search_terms:
- retrieve the full public course catalog
- query the program catalog
- query learning path catalog data including structured sequences of courses and content organized around specific skills and roles.
- channels
- content management
- course catalog with titles, descriptions, authors, and metadata
- manage channels
- query the general content catalog
- query content tags and taxonomy data
- query content catalog
- learning
- hands-on labs and practical exercises
- structured learning programs and curriculum offerings
- resolve content slugs to internal identifiers for content lookup by human-readable url slugs.
- query course catalog information including titles, descriptions, authors, duration, release dates, and retirement status.
- query content tags and taxonomy data used to categorize and organize learning content.
- query learning paths
- query the program catalog including structured learning programs and curriculum offerings.
- resolve content slugs to internal identifiers
- general content catalog including videos, guides, and interactive courses
- query the course catalog
- education
- learning content
- query tags
- learning paths
- query course catalog
- query labs
- engineering metrics
- query and manage content channels including creating channels, managing members and groups, organizing content sections, and tracking channel progress.
- retrieve the full public course catalog including course ids, titles, durations, release dates, and retirement status.
- query lab catalog and lab activity data for hands-on learning experiences and practical exercises.
- public course catalog accessible without authentication
- structured sequences of courses organized around skills and roles
- skills assessment
- query and manage content channels
- get public course catalog
- content tags and taxonomy for categorization
- query lab catalog and activity data
- query learning path catalog data
- courses
- query the general content catalog including videos, guides, interactive courses, and other content types.
- content channels for organizing and curating learning content
- pluralsight
- technology
- query content slugs
- query programs
- video training
slug: learning-content-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Pluralsight Learning Content Management\"\n  description: \"Unified workflow for L&D managers and content administrators to browse, organize, and manage learning content across courses, channels, learning paths, programs, labs, and tags. Combines content catalog, course catalog, public catalog, channels, learning paths, programs, labs, content slugs, and tags APIs.\"\n  tags:\n    - Pluralsight\n    - Learning Content\n    - Content Management\n    - Courses\n    - Channels\n    - Learning Paths\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PLURALSIGHT_BEARER_TOKEN: PLURALSIGHT_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: pluralsight-content-catalog\n      location: ./shared/content-catalog.yaml\n    - import: pluralsight-content-slug\n      location: ./shared/content-slug.yaml\n    - import: pluralsight-course-catalog\n      location: ./shared/course-catalog.yaml\n\
  \    - import: pluralsight-public-course-catalog\n      location: ./shared/public-course-catalog-rest.yaml\n    - import: pluralsight-channels\n      location: ./shared/channels.yaml\n    - import: pluralsight-learning-paths\n      location: ./shared/learning-paths.yaml\n    - import: pluralsight-programs\n      location: ./shared/programs.yaml\n    - import: pluralsight-labs\n      location: ./shared/labs.yaml\n    - import: pluralsight-tags\n      location: ./shared/tags.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: learning-content-api\n      description: \"Unified REST API for browsing and managing Pluralsight learning content across all content types.\"\n      resources:\n        - path: /v1/content-catalog\n          name: content-catalog\n          description: \"General content catalog including videos, guides, and interactive courses\"\n          operations:\n            - method: POST\n              name: query-content-catalog\n              description:\
  \ \"Query the general content catalog\"\n              call: \"pluralsight-content-catalog.query-content-catalog\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content-slugs\n          name: content-slugs\n          description: \"Resolve content slugs to internal identifiers\"\n          operations:\n            - method: POST\n              name: query-content-slugs\n              description: \"Resolve content slugs to internal identifiers\"\n              call: \"pluralsight-content-slug.query-content-slugs\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n              \
  \    mapping: \"$.\"\n        - path: /v1/course-catalog\n          name: course-catalog\n          description: \"Course catalog with titles, descriptions, authors, and metadata\"\n          operations:\n            - method: POST\n              name: query-course-catalog\n              description: \"Query the course catalog\"\n              call: \"pluralsight-course-catalog.query-course-catalog\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/public-courses\n          name: public-courses\n          description: \"Public course catalog accessible without authentication\"\n          operations:\n            - method: GET\n              name: get-public-course-catalog\n              description: \"Retrieve the full public course catalog\"\n           \
  \   call: \"pluralsight-public-course-catalog.get-public-course-catalog\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/channels\n          name: channels\n          description: \"Content channels for organizing and curating learning content\"\n          operations:\n            - method: POST\n              name: manage-channels\n              description: \"Query and manage content channels\"\n              call: \"pluralsight-channels.manage-channels\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/learning-paths\n          name: learning-paths\n          description: \"Structured sequences of courses organized around skills and roles\"\n          operations:\n            - method:\
  \ POST\n              name: query-learning-paths\n              description: \"Query learning path catalog data\"\n              call: \"pluralsight-learning-paths.query-learning-paths\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/programs\n          name: programs\n          description: \"Structured learning programs and curriculum offerings\"\n          operations:\n            - method: POST\n              name: query-programs\n              description: \"Query the program catalog\"\n              call: \"pluralsight-programs.query-programs\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n          \
  \      - type: object\n                  mapping: \"$.\"\n        - path: /v1/labs\n          name: labs\n          description: \"Hands-on labs and practical exercises\"\n          operations:\n            - method: POST\n              name: query-labs\n              description: \"Query lab catalog and activity data\"\n              call: \"pluralsight-labs.query-labs\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tags\n          name: tags\n          description: \"Content tags and taxonomy for categorization\"\n          operations:\n            - method: POST\n              name: query-tags\n              description: \"Query content tags and taxonomy data\"\n              call: \"pluralsight-tags.query-tags\"\n              with:\n              \
  \  query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: learning-content-mcp\n      transport: http\n      description: \"MCP server for AI-assisted learning content management across all Pluralsight content types.\"\n      tools:\n        - name: query-content-catalog\n          description: \"Query the general content catalog including videos, guides, interactive courses, and other content types.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-content-catalog.query-content-catalog\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: query-content-slugs\n          description: \"Resolve content slugs to internal identifiers for content lookup by human-readable URL slugs.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-content-slug.query-content-slugs\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-course-catalog\n          description: \"Query course catalog information including titles, descriptions, authors, duration, release dates, and retirement status.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call:\
  \ \"pluralsight-course-catalog.query-course-catalog\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-public-course-catalog\n          description: \"Retrieve the full public course catalog including course IDs, titles, durations, release dates, and retirement status.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-public-course-catalog.get-public-course-catalog\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: manage-channels\n          description: \"Query and manage content channels including creating channels, managing members and groups, organizing content sections, and tracking channel progress.\"\n\
  \          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          call: \"pluralsight-channels.manage-channels\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-learning-paths\n          description: \"Query learning path catalog data including structured sequences of courses and content organized around specific skills and roles.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-learning-paths.query-learning-paths\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: query-programs\n          description: \"Query the program catalog including structured learning programs and curriculum offerings.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-programs.query-programs\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-labs\n          description: \"Query lab catalog and lab activity data for hands-on learning experiences and practical exercises.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-labs.query-labs\"\n          with:\n\
  \            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-tags\n          description: \"Query content tags and taxonomy data used to categorize and organize learning content.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-tags.query-tags\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/capabilities/learning-content-management.yaml
tags:
- Pluralsight
- Learning Content
- Content Management
- Courses
- Channels
- Learning Paths
tools:
- description: Query the general content catalog including videos, guides, interactive courses, and other content types.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-content-catalog
- description: Resolve content slugs to internal identifiers for content lookup by human-readable URL slugs.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-content-slugs
- description: Query course catalog information including titles, descriptions, authors, duration, release dates, and retirement status.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-course-catalog
- description: Retrieve the full public course catalog including course IDs, titles, durations, release dates, and retirement status.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-public-course-catalog
- description: Query and manage content channels including creating channels, managing members and groups, organizing content sections, and tracking channel progress.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: manage-channels
- description: Query learning path catalog data including structured sequences of courses and content organized around specific skills and roles.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-learning-paths
- description: Query the program catalog including structured learning programs and curriculum offerings.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-programs
- description: Query lab catalog and lab activity data for hands-on learning experiences and practical exercises.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-labs
- description: Query content tags and taxonomy data used to categorize and organize learning content.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-tags
---
