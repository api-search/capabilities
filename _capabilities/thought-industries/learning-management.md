---
categories: []
consumed_apis:
- thought-industries
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
- lxp
- create user
- get detailed information about a specific course
- get course details
- list all learner groups
- add a learner to a specific group
- learner groups
- get all course enrollments for a learner
- list all available courses in the catalog with status filter
- course enrollment management
- single course details
- add learner to a group
- list all learner groups in the platform
- get all course enrollments and progress for a learner
- add user to group
- get course
- hr integration
- list all learners with optional email filter
- learning path actions report
- get learning path actions report
- get user
- get learning path enrollment actions and completion report
- create a new learner account in the platform
- get learning path enrollment actions report
- create a new learner account
- remove multiple learners from a course or learning path
- course catalog
- training
- education
- learner user management
- update learner profile or deactivate account
- list users
- list all learners in the platform with optional email filter
- e-learning
- group membership
- update user
- bulk remove course access
- list all courses in the catalog
- get learner details by id
- get learner details and profile by user id
- enroll user
- lms
- enroll a learner in a course
- list groups
- get user enrollments
- update learner profile or activate/deactivate account
- single user operations
- learning
- user enrollment history
- bulk remove enrollments
slug: learning-management
source_filename: learning-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Thought Industries Learning Management\"\n  description: >-\n    Unified learning management capability combining user lifecycle, course\n    administration, enrollment management, and reporting for B2B learning\n    platforms. Used by L&D teams, platform administrators, and HR integration\n    workflows to manage learner experiences at scale.\n  tags:\n    - Education\n    - Learning\n    - LMS\n    - LXP\n    - Training\n    - HR Integration\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      THOUGHT_INDUSTRIES_API_KEY: THOUGHT_INDUSTRIES_API_KEY\n\ncapability:\n  consumes:\n    - import: thought-industries\n      location: ./shared/rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: learning-management-api\n      description: \"Unified REST API for learning management workflows.\"\n      resources:\n        - path: /v1/users\n          name: users\n\
  \          description: Learner user management\n          operations:\n            - method: GET\n              name: list-users\n              description: List all learners with optional email filter\n              call: \"thought-industries.list-users\"\n              with:\n                email: \"rest.email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: Create a new learner account\n              call: \"thought-industries.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{id}\n          name: user\n          description: Single user operations\n          operations:\n            - method: GET\n              name: get-user\n              description: Get learner details by ID\n              call: \"thought-industries.get-user\"\n              with:\n\
  \                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-user\n              description: Update learner profile or deactivate account\n              call: \"thought-industries.update-user\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{id}/enrollments\n          name: user-enrollments\n          description: User enrollment history\n          operations:\n            - method: GET\n              name: get-user-enrollments\n              description: Get all course enrollments for a learner\n              call: \"thought-industries.get-user-enrollments\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/courses\n\
  \          name: courses\n          description: Course catalog\n          operations:\n            - method: GET\n              name: list-courses\n              description: List all courses in the catalog\n              call: \"thought-industries.list-courses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/courses/{courseId}\n          name: course\n          description: Single course details\n          operations:\n            - method: GET\n              name: get-course\n              description: Get course details\n              call: \"thought-industries.get-course\"\n              with:\n                courseId: \"rest.courseId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/courses/{courseId}/enrollments\n          name: course-enrollments\n          description: Course enrollment management\n          operations:\n         \
  \   - method: POST\n              name: enroll-user\n              description: Enroll a learner in a course\n              call: \"thought-industries.enroll-user\"\n              with:\n                courseId: \"rest.courseId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/courses/{courseId}/enrollments/bulk-remove\n          name: bulk-remove-enrollments\n          description: Bulk remove course access\n          operations:\n            - method: POST\n              name: bulk-remove-enrollments\n              description: Remove multiple learners from a course\n              call: \"thought-industries.bulk-remove-enrollments\"\n              with:\n                courseId: \"rest.courseId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: Learner groups\n          operations:\n \
  \           - method: GET\n              name: list-groups\n              description: List all learner groups\n              call: \"thought-industries.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups/{groupId}/users\n          name: group-members\n          description: Group membership\n          operations:\n            - method: POST\n              name: add-user-to-group\n              description: Add learner to a group\n              call: \"thought-industries.add-user-to-group\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/learning-path-actions\n          name: learning-path-report\n          description: Learning path actions report\n          operations:\n            - method: GET\n              name: get-learning-path-actions-report\n  \
  \            description: Get learning path enrollment actions report\n              call: \"thought-industries.get-learning-path-actions-report\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: learning-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted learning management and L&D workflows.\"\n      tools:\n        - name: list-users\n          description: List all learners in the platform with optional email filter\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thought-industries.list-users\"\n          with:\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: Create a new learner account in the platform\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n          call: \"thought-industries.create-user\"\n          with:\n            email: \"tools.email\"\n            first_name: \"tools.first_name\"\n            last_name: \"tools.last_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: Get learner details and profile by user ID\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thought-industries.get-user\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-user\n          description: Update learner profile or activate/deactivate account\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"thought-industries.update-user\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n           \
  \ - type: object\n              mapping: \"$.\"\n        - name: get-user-enrollments\n          description: Get all course enrollments and progress for a learner\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thought-industries.get-user-enrollments\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-courses\n          description: List all available courses in the catalog with status filter\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thought-industries.list-courses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-course\n          description: Get detailed information about a specific course\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thought-industries.get-course\"\n     \
  \     with:\n            courseId: \"tools.courseId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enroll-user\n          description: Enroll a learner in a course\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"thought-industries.enroll-user\"\n          with:\n            courseId: \"tools.courseId\"\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: bulk-remove-enrollments\n          description: Remove multiple learners from a course or learning path\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"thought-industries.bulk-remove-enrollments\"\n          with:\n            courseId: \"tools.courseId\"\n            user_ids: \"tools.user_ids\"\n          outputParameters:\n            - type: object\n     \
  \         mapping: \"$.\"\n        - name: list-groups\n          description: List all learner groups in the platform\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thought-industries.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-user-to-group\n          description: Add a learner to a specific group\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"thought-industries.add-user-to-group\"\n          with:\n            groupId: \"tools.groupId\"\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-learning-path-actions-report\n          description: Get learning path enrollment actions and completion report\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thought-industries.get-learning-path-actions-report\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
