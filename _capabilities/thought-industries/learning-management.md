---
categories: []
consumed_apis: []
description: Unified learning management capability combining user lifecycle, course administration, enrollment management, and reporting for B2B learning platforms. Used by L&D teams, platform administrators, and HR integration workflows to manage learner experiences at scale.
layout: capability
name: Thought Industries Learning Management
operations:
- description: List all learners with optional email filter
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new learner account
  method: POST
  name: create-user
  path: /v1/users
- description: Get learner details by ID
  method: GET
  name: get-user
  path: /v1/users/{id}
- description: Update learner profile or deactivate account
  method: PUT
  name: update-user
  path: /v1/users/{id}
- description: Get all course enrollments for a learner
  method: GET
  name: get-user-enrollments
  path: /v1/users/{id}/enrollments
- description: List all courses in the catalog
  method: GET
  name: list-courses
  path: /v1/courses
- description: Get course details
  method: GET
  name: get-course
  path: /v1/courses/{courseId}
- description: Enroll a learner in a course
  method: POST
  name: enroll-user
  path: /v1/courses/{courseId}/enrollments
- description: Remove multiple learners from a course
  method: POST
  name: bulk-remove-enrollments
  path: /v1/courses/{courseId}/enrollments/bulk-remove
- description: List all learner groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: Add learner to a group
  method: POST
  name: add-user-to-group
  path: /v1/groups/{groupId}/users
- description: Get learning path enrollment actions report
  method: GET
  name: get-learning-path-actions-report
  path: /v1/reports/learning-path-actions
personas: []
provider_name: Thought Industries
provider_slug: thought-industries
search_terms:
- remove multiple learners from a course
- list courses
- hr integration
- update learner profile or deactivate account
- get all course enrollments for a learner
- learning path actions report
- update learner profile or activate/deactivate account
- list groups
- course catalog
- list all learner groups in the platform
- update user
- bulk remove enrollments
- list all courses in the catalog
- lms
- lxp
- list all learner groups
- get detailed information about a specific course
- remove multiple learners from a course or learning path
- get learner details and profile by user id
- single user operations
- add user to group
- learner groups
- list all learners in the platform with optional email filter
- add a learner to a specific group
- create a new learner account
- learning
- get course
- get learning path actions report
- get learning path enrollment actions and completion report
- list users
- e-learning
- get course details
- enroll user
- add learner to a group
- bulk remove course access
- get user enrollments
- single course details
- course enrollment management
- training
- get user
- group membership
- education
- create user
- learner user management
- get all course enrollments and progress for a learner
- get learner details by id
- enroll a learner in a course
- list all available courses in the catalog with status filter
- list all learners with optional email filter
- user enrollment history
- create a new learner account in the platform
- get learning path enrollment actions report
slug: learning-management
source_filename: learning-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Thought Industries Learning Management\n  description: Unified learning management capability combining user lifecycle, course administration, enrollment management,\n    and reporting for B2B learning platforms. Used by L&D teams, platform administrators, and HR integration workflows to\n    manage learner experiences at scale.\n  tags:\n  - Education\n  - Learning\n  - LMS\n  - LXP\n  - Training\n  - HR Integration\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    THOUGHT_INDUSTRIES_API_KEY: THOUGHT_INDUSTRIES_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: thought-industries\n    baseUri: https://{subdomain}.thoughtindustries.com/incoming/api/v1\n    description: Thought Industries REST API v1\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{THOUGHT_INDUSTRIES_API_KEY}}'\n      placement: header\n    resources:\n    - name: users\n      path: /users\n\
  \      description: User lifecycle management\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users with pagination\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Records per page (max 100)\n        - name: email\n          in: query\n          type: string\n          required: false\n          description: Filter by email address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n   \
  \       data:\n            email: '{{tools.email}}'\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n            active: '{{tools.active}}'\n      - name: get-user\n        method: GET\n        description: Get a single user by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PUT\n        description: Update a user record\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            active: '{{tools.active}}'\n\
  \            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n    - name: courses\n      path: /courses\n      description: Course management\n      operations:\n      - name: list-courses\n        method: GET\n        description: List all courses\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status (published, draft, archived)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-course\n        method: GET\n        description: Get a specific course\n        inputParameters:\n        -\
  \ name: courseId\n          in: path\n          type: string\n          required: true\n          description: Course ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enrollments\n      path: /courses/{courseId}/enrollments\n      description: Course enrollment management\n      operations:\n      - name: get-user-enrollments\n        method: GET\n        description: Get enrollments for a user\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: enroll-user\n        method: POST\n        description: Enroll a user in a course\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Course ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            user_id: '{{tools.user_id}}'\n      - name: bulk-remove-enrollments\n        method: POST\n        description: Bulk remove user access from a course\n        inputParameters:\n        - name: courseId\n          in: path\n          type: string\n          required: true\n          description: Course ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            user_ids: '{{tools.user_ids}}'\n    - name: groups\n      path: /groups\n      description: User group management\n      operations:\n      - name: list-groups\n        method: GET\n        description: List all user groups\n        inputParameters:\n        - name: page\n          in: query\n\
  \          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-user-to-group\n        method: POST\n        description: Add a user to a group\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            user_id: '{{tools.user_id}}'\n    - name: reports\n      path: /reports\n      description: Analytics and reporting\n      operations:\n      - name: get-learning-path-actions-report\n        method: GET\n        description: Get learning path actions report\n        inputParameters:\n        - name: start_date\n          in: query\n  \
  \        type: string\n          required: false\n          description: Report start date\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: Report end date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: learning-management-api\n    description: Unified REST API for learning management workflows.\n    resources:\n    - path: /v1/users\n      name: users\n      description: Learner user management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all learners with optional email filter\n        call: thought-industries.list-users\n        with:\n          email: rest.email\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new learner\
  \ account\n        call: thought-industries.create-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{id}\n      name: user\n      description: Single user operations\n      operations:\n      - method: GET\n        name: get-user\n        description: Get learner details by ID\n        call: thought-industries.get-user\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-user\n        description: Update learner profile or deactivate account\n        call: thought-industries.update-user\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{id}/enrollments\n      name: user-enrollments\n      description: User enrollment history\n      operations:\n      - method: GET\n        name: get-user-enrollments\n        description: Get all course enrollments for\
  \ a learner\n        call: thought-industries.get-user-enrollments\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses\n      name: courses\n      description: Course catalog\n      operations:\n      - method: GET\n        name: list-courses\n        description: List all courses in the catalog\n        call: thought-industries.list-courses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}\n      name: course\n      description: Single course details\n      operations:\n      - method: GET\n        name: get-course\n        description: Get course details\n        call: thought-industries.get-course\n        with:\n          courseId: rest.courseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/enrollments\n      name: course-enrollments\n      description: Course enrollment management\n\
  \      operations:\n      - method: POST\n        name: enroll-user\n        description: Enroll a learner in a course\n        call: thought-industries.enroll-user\n        with:\n          courseId: rest.courseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/courses/{courseId}/enrollments/bulk-remove\n      name: bulk-remove-enrollments\n      description: Bulk remove course access\n      operations:\n      - method: POST\n        name: bulk-remove-enrollments\n        description: Remove multiple learners from a course\n        call: thought-industries.bulk-remove-enrollments\n        with:\n          courseId: rest.courseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Learner groups\n      operations:\n      - method: GET\n        name: list-groups\n        description: List all learner groups\n        call: thought-industries.list-groups\n     \
  \   outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups/{groupId}/users\n      name: group-members\n      description: Group membership\n      operations:\n      - method: POST\n        name: add-user-to-group\n        description: Add learner to a group\n        call: thought-industries.add-user-to-group\n        with:\n          groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/learning-path-actions\n      name: learning-path-report\n      description: Learning path actions report\n      operations:\n      - method: GET\n        name: get-learning-path-actions-report\n        description: Get learning path enrollment actions report\n        call: thought-industries.get-learning-path-actions-report\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: learning-management-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted learning management and L&D workflows.\n    tools:\n    - name: list-users\n      description: List all learners in the platform with optional email filter\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thought-industries.list-users\n      with:\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new learner account in the platform\n      hints:\n        readOnly: false\n        destructive: false\n      call: thought-industries.create-user\n      with:\n        email: tools.email\n        first_name: tools.first_name\n        last_name: tools.last_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get learner details and profile by user ID\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thought-industries.get-user\n      with:\n        id: tools.id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-user\n      description: Update learner profile or activate/deactivate account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: thought-industries.update-user\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user-enrollments\n      description: Get all course enrollments and progress for a learner\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thought-industries.get-user-enrollments\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-courses\n      description: List all available courses in the catalog with status filter\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thought-industries.list-courses\n      outputParameters:\n      - type: object\n  \
  \      mapping: $.\n    - name: get-course\n      description: Get detailed information about a specific course\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thought-industries.get-course\n      with:\n        courseId: tools.courseId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enroll-user\n      description: Enroll a learner in a course\n      hints:\n        readOnly: false\n        destructive: false\n      call: thought-industries.enroll-user\n      with:\n        courseId: tools.courseId\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bulk-remove-enrollments\n      description: Remove multiple learners from a course or learning path\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: thought-industries.bulk-remove-enrollments\n      with:\n        courseId: tools.courseId\n        user_ids: tools.user_ids\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List all learner groups in the platform\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thought-industries.list-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-user-to-group\n      description: Add a learner to a specific group\n      hints:\n        readOnly: false\n        destructive: false\n      call: thought-industries.add-user-to-group\n      with:\n        groupId: tools.groupId\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-learning-path-actions-report\n      description: Get learning path enrollment actions and completion report\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thought-industries.get-learning-path-actions-report\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/thought-industries/refs/heads/main/capabilities/learning-management.yaml
tags:
- Education
- Learning
- LMS
- LXP
- Training
- HR Integration
tools:
- description: List all learners in the platform with optional email filter
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new learner account in the platform
  hints:
    destructive: false
    readOnly: false
  name: create-user
- description: Get learner details and profile by user ID
  hints:
    openWorld: true
    readOnly: true
  name: get-user
- description: Update learner profile or activate/deactivate account
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-user
- description: Get all course enrollments and progress for a learner
  hints:
    openWorld: true
    readOnly: true
  name: get-user-enrollments
- description: List all available courses in the catalog with status filter
  hints:
    openWorld: true
    readOnly: true
  name: list-courses
- description: Get detailed information about a specific course
  hints:
    openWorld: true
    readOnly: true
  name: get-course
- description: Enroll a learner in a course
  hints:
    destructive: false
    readOnly: false
  name: enroll-user
- description: Remove multiple learners from a course or learning path
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: bulk-remove-enrollments
- description: List all learner groups in the platform
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: Add a learner to a specific group
  hints:
    destructive: false
    readOnly: false
  name: add-user-to-group
- description: Get learning path enrollment actions and completion report
  hints:
    openWorld: true
    readOnly: true
  name: get-learning-path-actions-report
---
