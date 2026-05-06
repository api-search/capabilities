---
categories:
- content-management
consumed_apis: []
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
- public course catalog accessible without authentication
- courses
- content channels for organizing and curating learning content
- query the program catalog including structured learning programs and curriculum offerings.
- skills assessment
- hands-on labs and practical exercises
- structured sequences of courses organized around skills and roles
- query labs
- query content tags and taxonomy data
- query the general content catalog including videos, guides, interactive courses, and other content types.
- education
- query content catalog
- content tags and taxonomy for categorization
- resolve content slugs to internal identifiers for content lookup by human-readable url slugs.
- query and manage content channels
- learning content
- query course catalog
- course catalog with titles, descriptions, authors, and metadata
- video training
- query content slugs
- content management
- query lab catalog and lab activity data for hands-on learning experiences and practical exercises.
- retrieve the full public course catalog
- structured learning programs and curriculum offerings
- general content catalog including videos, guides, and interactive courses
- query the general content catalog
- query learning paths
- technology
- manage channels
- learning paths
- get public course catalog
- pluralsight
- query course catalog information including titles, descriptions, authors, duration, release dates, and retirement status.
- retrieve the full public course catalog including course ids, titles, durations, release dates, and retirement status.
- resolve content slugs to internal identifiers
- query the program catalog
- query learning path catalog data including structured sequences of courses and content organized around specific skills and roles.
- engineering metrics
- query and manage content channels including creating channels, managing members and groups, organizing content sections, and tracking channel progress.
- learning
- query tags
- query learning path catalog data
- query content tags and taxonomy data used to categorize and organize learning content.
- query programs
- query lab catalog and activity data
- query the course catalog
- channels
slug: learning-content-management
source_filename: learning-content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pluralsight Learning Content Management\n  description: Unified workflow for L&D managers and content administrators to browse, organize, and manage learning content\n    across courses, channels, learning paths, programs, labs, and tags. Combines content catalog, course catalog, public catalog,\n    channels, learning paths, programs, labs, content slugs, and tags APIs.\n  tags:\n  - Pluralsight\n  - Learning Content\n  - Content Management\n  - Courses\n  - Channels\n  - Learning Paths\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PLURALSIGHT_BEARER_TOKEN: PLURALSIGHT_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: pluralsight-content-catalog\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL query for accessing the general content catalog including videos, guides, interactive courses, and\n      other content types.\n    authentication:\n     \
  \ type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: content-catalog\n      path: /graphql\n      description: Content catalog queries via GraphQL\n      operations:\n      - name: query-content-catalog\n        method: POST\n        description: Execute GraphQL queries to retrieve the general content catalog including videos, guides, interactive\n          courses, and other content types.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n        - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n  - type: http\n    namespace: pluralsight-content-slug\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL query for resolving content slugs to internal identifiers, enabling lookup of content by human-readable\n      URL slugs.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: content-slugs\n      path: /graphql\n      description: Content slug resolution via GraphQL\n      operations:\n      - name: query-content-slugs\n        method: POST\n        description: Execute GraphQL queries to resolve content slugs to internal identifiers.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description:\
  \ The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n        - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n  - type: http\n    namespace: pluralsight-course-catalog\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL query for accessing course catalog information including titles, descriptions, authors, duration,\n      release dates, and retirement status.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n\
  \    resources:\n    - name: course-catalog\n      path: /graphql\n      description: Course catalog queries via GraphQL\n      operations:\n      - name: query-course-catalog\n        method: POST\n        description: Execute GraphQL queries to retrieve course catalog information including titles, descriptions, authors,\n          duration, release dates, and retirement status.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n        - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n       \
  \ body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n  - type: http\n    namespace: pluralsight-public-course-catalog\n    baseUri: https://paas-rest-api.pluralsight.com\n    description: Public REST API for accessing the full course catalog without authentication.\n    resources:\n    - name: courses\n      path: /courses\n      description: Public course catalog\n      operations:\n      - name: get-public-course-catalog\n        method: GET\n        description: Retrieve the full public course catalog without authentication. Returns course IDs, titles, durations,\n          release dates, and retirement status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: pluralsight-channels\n    baseUri: https://paas-api.pluralsight.com\n    description:\
  \ GraphQL queries and mutations for managing content channels including creating channels, managing members\n      and groups, organizing content sections, and tracking channel progress.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: channels\n      path: /graphql\n      description: Channel management via GraphQL\n      operations:\n      - name: manage-channels\n        method: POST\n        description: Execute GraphQL queries and mutations for managing content channels including creating channels, managing\n          members and groups, organizing content sections, and tracking channel progress.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n \
  \       - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n  - type: http\n    namespace: pluralsight-learning-paths\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL query for accessing learning path catalog data including structured sequences of courses and content\n      organized around specific skills and roles.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: learning-paths\n      path: /graphql\n      description: Learning path catalog queries via GraphQL\n      operations:\n    \
  \  - name: query-learning-paths\n        method: POST\n        description: Execute GraphQL queries to retrieve learning path catalog data including structured sequences of courses\n          and content organized around specific skills and roles.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n        - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n    \
  \        operationName: '{{tools.operationName}}'\n  - type: http\n    namespace: pluralsight-programs\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL query for accessing the program catalog including structured learning programs and curriculum offerings.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: programs\n      path: /graphql\n      description: Program catalog queries via GraphQL\n      operations:\n      - name: query-programs\n        method: POST\n        description: Execute GraphQL queries to access the program catalog including structured learning programs and curriculum\n          offerings.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables\
  \ for the GraphQL query\n        - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n  - type: http\n    namespace: pluralsight-labs\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL queries for accessing lab catalog and lab activity data for hands-on learning experiences and practical\n      exercises.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: labs\n      path: /graphql\n      description: Lab catalog and activity queries via GraphQL\n      operations:\n      - name: query-labs\n\
  \        method: POST\n        description: Execute GraphQL queries to access lab catalog and lab activity data for hands-on learning experiences\n          and practical exercises.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n        - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n  - type: http\n\
  \    namespace: pluralsight-tags\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL query for accessing content tags and taxonomy data used to categorize and organize learning content.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: tags\n      path: /graphql\n      description: Content tag queries via GraphQL\n      operations:\n      - name: query-tags\n        method: POST\n        description: Execute GraphQL queries to access content tags and taxonomy data used to categorize and organize learning\n          content.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n        - name: operationName\n          in: body\n         \
  \ type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: learning-content-api\n    description: Unified REST API for browsing and managing Pluralsight learning content across all content types.\n    resources:\n    - path: /v1/content-catalog\n      name: content-catalog\n      description: General content catalog including videos, guides, and interactive courses\n      operations:\n      - method: POST\n        name: query-content-catalog\n        description: Query the general content catalog\n        call: pluralsight-content-catalog.query-content-catalog\n        with:\n\
  \          query: rest.query\n          variables: rest.variables\n          operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content-slugs\n      name: content-slugs\n      description: Resolve content slugs to internal identifiers\n      operations:\n      - method: POST\n        name: query-content-slugs\n        description: Resolve content slugs to internal identifiers\n        call: pluralsight-content-slug.query-content-slugs\n        with:\n          query: rest.query\n          variables: rest.variables\n          operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/course-catalog\n      name: course-catalog\n      description: Course catalog with titles, descriptions, authors, and metadata\n      operations:\n      - method: POST\n        name: query-course-catalog\n        description: Query the course catalog\n        call: pluralsight-course-catalog.query-course-catalog\n\
  \        with:\n          query: rest.query\n          variables: rest.variables\n          operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/public-courses\n      name: public-courses\n      description: Public course catalog accessible without authentication\n      operations:\n      - method: GET\n        name: get-public-course-catalog\n        description: Retrieve the full public course catalog\n        call: pluralsight-public-course-catalog.get-public-course-catalog\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/channels\n      name: channels\n      description: Content channels for organizing and curating learning content\n      operations:\n      - method: POST\n        name: manage-channels\n        description: Query and manage content channels\n        call: pluralsight-channels.manage-channels\n        with:\n          query: rest.query\n          variables:\
  \ rest.variables\n          operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/learning-paths\n      name: learning-paths\n      description: Structured sequences of courses organized around skills and roles\n      operations:\n      - method: POST\n        name: query-learning-paths\n        description: Query learning path catalog data\n        call: pluralsight-learning-paths.query-learning-paths\n        with:\n          query: rest.query\n          variables: rest.variables\n          operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/programs\n      name: programs\n      description: Structured learning programs and curriculum offerings\n      operations:\n      - method: POST\n        name: query-programs\n        description: Query the program catalog\n        call: pluralsight-programs.query-programs\n        with:\n          query:\
  \ rest.query\n          variables: rest.variables\n          operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/labs\n      name: labs\n      description: Hands-on labs and practical exercises\n      operations:\n      - method: POST\n        name: query-labs\n        description: Query lab catalog and activity data\n        call: pluralsight-labs.query-labs\n        with:\n          query: rest.query\n          variables: rest.variables\n          operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tags\n      name: tags\n      description: Content tags and taxonomy for categorization\n      operations:\n      - method: POST\n        name: query-tags\n        description: Query content tags and taxonomy data\n        call: pluralsight-tags.query-tags\n        with:\n          query: rest.query\n          variables: rest.variables\n        \
  \  operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: learning-content-mcp\n    transport: http\n    description: MCP server for AI-assisted learning content management across all Pluralsight content types.\n    tools:\n    - name: query-content-catalog\n      description: Query the general content catalog including videos, guides, interactive courses, and other content types.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-content-catalog.query-content-catalog\n      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-content-slugs\n      description: Resolve content slugs to internal identifiers for content lookup by human-readable URL slugs.\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-content-slug.query-content-slugs\n      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-course-catalog\n      description: Query course catalog information including titles, descriptions, authors, duration, release dates, and\n        retirement status.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-course-catalog.query-course-catalog\n      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-public-course-catalog\n      description: Retrieve the full public\
  \ course catalog including course IDs, titles, durations, release dates, and retirement\n        status.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-public-course-catalog.get-public-course-catalog\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: manage-channels\n      description: Query and manage content channels including creating channels, managing members and groups, organizing\n        content sections, and tracking channel progress.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n        openWorld: true\n      call: pluralsight-channels.manage-channels\n      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-learning-paths\n      description: Query learning\
  \ path catalog data including structured sequences of courses and content organized around\n        specific skills and roles.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-learning-paths.query-learning-paths\n      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-programs\n      description: Query the program catalog including structured learning programs and curriculum offerings.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-programs.query-programs\n      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ query-labs\n      description: Query lab catalog and lab activity data for hands-on learning experiences and practical exercises.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-labs.query-labs\n      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-tags\n      description: Query content tags and taxonomy data used to categorize and organize learning content.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-tags.query-tags\n      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
