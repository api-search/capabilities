---
categories:
- compliance
consumed_apis: []
description: Unified workflow capability for managing learning objects, enrollments, completions, and compliance tracking using Adobe Learning Manager APIs. Designed for L&D administrators and HR integration developers.
layout: capability
name: Adobe Captivate Learning Management
operations:
- description: List all available learning objects.
  method: GET
  name: list-learning-objects
  path: /v1/learning-objects
- description: Get details of a specific learning object.
  method: GET
  name: get-learning-object
  path: /v1/learning-objects/{learningObjectId}
- description: List all users in the account.
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user account.
  method: POST
  name: create-user
  path: /v1/users
- description: List all enrollments.
  method: GET
  name: list-enrollments
  path: /v1/enrollments
- description: Enroll a learner in a learning object.
  method: POST
  name: enroll-learner
  path: /v1/enrollments
- description: List all skills.
  method: GET
  name: list-skills
  path: /v1/skills
- description: List all badges.
  method: GET
  name: list-badges
  path: /v1/badges
- description: List all certifications.
  method: GET
  name: list-certifications
  path: /v1/certifications
- description: List all catalogs.
  method: GET
  name: list-catalogs
  path: /v1/catalogs
- description: Create a bulk data import or export job.
  method: POST
  name: create-bulk-job
  path: /v1/jobs
personas: []
provider_name: Adobe Captivate
provider_slug: adobe-captivate
search_terms:
- learning management
- get learning object
- list enrollments
- learner enrollment management.
- get account
- badge and achievement management.
- enroll a learner in a course, certification, or learning program.
- list certification programs for compliance and credential tracking.
- retrieve account-level configuration and settings for adobe learning manager.
- L&D Administrator
- list certifications
- unified workflow for managing learning objects, enrollments, users, and compliance.
- learner progress, skill attainment, and completion reporting.
- list all enrollments.
- elearning
- learner and admin user management.
- learning content catalog management.
- learning and development professional managing course catalogs, enrollments, and compliance tracking.
- real-time webhook events for downstream integrations.
- bulk import/export job management.
- lms
- compliance
- single learning object details.
- list catalogs
- list badges and achievements available to learners.
- scorm
- list all available courses, learning programs, certifications, and job aids in adobe learning manager.
- list content catalogs organizing learning objects for targeted delivery.
- developer integrating hris systems with adobe learning manager for user provisioning and data sync.
- enroll a learner in a learning object.
- list users
- authoring
- certification and mandatory training compliance tracking.
- list all catalogs.
- list all available learning objects.
- list all skills defined in the account for skill gap analysis.
- create a new user account in adobe learning manager for a new learner or employee.
- get detailed information about a specific learning object including instances, skills, and prerequisites.
- create a new user account.
- certification program management.
- create a bulk export job for learner transcripts or training reports.
- xapi
- HR Integration Developer
- training
- create a bulk data import or export job.
- list all users in the account.
- create bulk export job
- enroll learner
- education
- create user
- list skills
- list all badges.
- get details of a specific learning object.
- list all certifications.
- list badges
- create bulk job
- list learner enrollments across all learning objects.
- courses, learning programs, certifications, and job aids.
- adobe captivate
- skill tracking and management.
- list all skills.
- list learners, managers, authors, and admin users in adobe learning manager.
- core lms functionality including course delivery, enrollment, and progress tracking.
- list learning objects
slug: learning-management
source_filename: learning-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Captivate Learning Management\n  description: Unified workflow capability for managing learning objects, enrollments, completions, and compliance tracking\n    using Adobe Learning Manager APIs. Designed for L&D administrators and HR integration developers.\n  tags:\n  - Adobe Captivate\n  - Learning Management\n  - LMS\n  - Compliance\n  - Training\n  - Education\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_CAPTIVATE_ACCESS_TOKEN: ADOBE_CAPTIVATE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: captivate-prime\n    baseUri: https://learningmanager.adobe.com/primeapi/v2\n    description: Adobe Learning Manager REST API v2 for programmatic LMS management.\n    authentication:\n      type: bearer\n      token: '{{ADOBE_CAPTIVATE_ACCESS_TOKEN}}'\n    resources:\n    - name: learning-objects\n      path: /learningObjects\n      description: Manage courses, learning\
  \ programs, certifications, and job aids.\n      operations:\n      - name: list-learning-objects\n        method: GET\n        description: List learning objects with filtering by type, catalog, skill, and state.\n        inputParameters:\n        - name: filter.loTypes\n          in: query\n          type: string\n          required: false\n          description: Comma-separated learning object types to filter by.\n        - name: page.offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: page.limit\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-learning-object\n        method: GET\n        description: Retrieve a single learning object by ID.\n        inputParameters:\n        -\
  \ name: learningObjectId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the learning object.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: Manage learner, manager, author, and admin user accounts.\n      operations:\n      - name: list-users\n        method: GET\n        description: List users with filtering by role, active status, and user group.\n        inputParameters:\n        - name: filter.role\n          in: query\n          type: string\n          required: false\n          description: Filter users by role (learner, manager, author, admin).\n        - name: filter.isActive\n          in: query\n          type: boolean\n          required: false\n          description: Filter by active status.\n        - name: page.offset\n          in: query\n          type: integer\n  \
  \        required: false\n          description: Pagination offset.\n        - name: page.limit\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-user\n        method: GET\n        description: Retrieve a single user by ID.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type:\
  \ json\n          data:\n            data:\n              type: user\n              attributes:\n                name: '{{tools.name}}'\n                email: '{{tools.email}}'\n    - name: enrollments\n      path: /enrollments\n      description: Manage learner enrollments in learning objects.\n      operations:\n      - name: list-enrollments\n        method: GET\n        description: List enrollments with optional filters.\n        inputParameters:\n        - name: page.offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: page.limit\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-enrollment\n        method: POST\n        description: Enroll a learner in a learning object.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data:\n              type: enrollment\n              relationships:\n                learningObject:\n                  data:\n                    id: '{{tools.learningObjectId}}'\n                    type: learningObject\n    - name: skills\n      path: /skills\n      description: Manage skills and skill levels associated with learning content.\n      operations:\n      - name: list-skills\n        method: GET\n        description: List all skills defined in the account.\n        inputParameters:\n        - name: page.offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: badges\n      path:\
  \ /badges\n      description: Manage badges awarded to learners for achievements.\n      operations:\n      - name: list-badges\n        method: GET\n        description: List all badges defined in the account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certifications\n      path: /certifications\n      description: Manage certification programs and compliance tracking.\n      operations:\n      - name: list-certifications\n        method: GET\n        description: List all certification programs.\n        inputParameters:\n        - name: page.offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: catalogs\n      path: /catalogs\n      description: Manage content catalogs that organize\
  \ learning objects.\n      operations:\n      - name: list-catalogs\n        method: GET\n        description: List all catalogs in the account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /jobs\n      description: Manage bulk import/export jobs for data operations.\n      operations:\n      - name: create-job\n        method: POST\n        description: Create a bulk import or export job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data:\n              type: job\n              attributes:\n                jobType: '{{tools.jobType}}'\n    - name: account\n      path: /account\n      description: Retrieve account-level settings and configuration.\n      operations:\n      - name: get-account\n        method: GET\n        description:\
  \ Retrieve account details and configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: learning-management-api\n    description: Unified REST API for Adobe Learning Manager — learning objects, users, enrollments, skills, badges, and compliance.\n    resources:\n    - path: /v1/learning-objects\n      name: learning-objects\n      description: Courses, learning programs, certifications, and job aids.\n      operations:\n      - method: GET\n        name: list-learning-objects\n        description: List all available learning objects.\n        call: captivate-prime.list-learning-objects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/learning-objects/{learningObjectId}\n      name: learning-object\n      description: Single learning object details.\n      operations:\n      - method: GET\n        name:\
  \ get-learning-object\n        description: Get details of a specific learning object.\n        call: captivate-prime.get-learning-object\n        with:\n          learningObjectId: rest.learningObjectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Learner and admin user management.\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users in the account.\n        call: captivate-prime.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new user account.\n        call: captivate-prime.create-user\n        with:\n          name: rest.name\n          email: rest.email\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/enrollments\n      name: enrollments\n      description: Learner enrollment management.\n\
  \      operations:\n      - method: GET\n        name: list-enrollments\n        description: List all enrollments.\n        call: captivate-prime.list-enrollments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: enroll-learner\n        description: Enroll a learner in a learning object.\n        call: captivate-prime.create-enrollment\n        with:\n          learningObjectId: rest.learningObjectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/skills\n      name: skills\n      description: Skill tracking and management.\n      operations:\n      - method: GET\n        name: list-skills\n        description: List all skills.\n        call: captivate-prime.list-skills\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/badges\n      name: badges\n      description: Badge and achievement management.\n      operations:\n      - method: GET\n  \
  \      name: list-badges\n        description: List all badges.\n        call: captivate-prime.list-badges\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/certifications\n      name: certifications\n      description: Certification program management.\n      operations:\n      - method: GET\n        name: list-certifications\n        description: List all certifications.\n        call: captivate-prime.list-certifications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalogs\n      name: catalogs\n      description: Learning content catalog management.\n      operations:\n      - method: GET\n        name: list-catalogs\n        description: List all catalogs.\n        call: captivate-prime.list-catalogs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Bulk import/export job management.\n      operations:\n      - method:\
  \ POST\n        name: create-bulk-job\n        description: Create a bulk data import or export job.\n        call: captivate-prime.create-job\n        with:\n          jobType: rest.jobType\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: learning-management-mcp\n    transport: http\n    description: MCP server for AI-assisted learning management — discover courses, manage enrollments, track compliance,\n      and analyze learner progress.\n    tools:\n    - name: list-learning-objects\n      description: List all available courses, learning programs, certifications, and job aids in Adobe Learning Manager.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: captivate-prime.list-learning-objects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-learning-object\n      description: Get detailed information about a specific learning object including instances,\
  \ skills, and prerequisites.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: captivate-prime.get-learning-object\n      with:\n        learningObjectId: tools.learningObjectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List learners, managers, authors, and admin users in Adobe Learning Manager.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: captivate-prime.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new user account in Adobe Learning Manager for a new learner or employee.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: captivate-prime.create-user\n      with:\n        name: tools.name\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-enrollments\n     \
  \ description: List learner enrollments across all learning objects.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: captivate-prime.list-enrollments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enroll-learner\n      description: Enroll a learner in a course, certification, or learning program.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: captivate-prime.create-enrollment\n      with:\n        learningObjectId: tools.learningObjectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-skills\n      description: List all skills defined in the account for skill gap analysis.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: captivate-prime.list-skills\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-badges\n      description: List badges and achievements available to learners.\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: captivate-prime.list-badges\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-certifications\n      description: List certification programs for compliance and credential tracking.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: captivate-prime.list-certifications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-catalogs\n      description: List content catalogs organizing learning objects for targeted delivery.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: captivate-prime.list-catalogs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bulk-export-job\n      description: Create a bulk export job for learner transcripts or training reports.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ captivate-prime.create-job\n      with:\n        jobType: tools.jobType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Retrieve account-level configuration and settings for Adobe Learning Manager.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: captivate-prime.get-account\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-captivate/refs/heads/main/capabilities/learning-management.yaml
tags:
- Adobe Captivate
- Learning Management
- LMS
- Compliance
- Training
- Education
tools:
- description: List all available courses, learning programs, certifications, and job aids in Adobe Learning Manager.
  hints:
    openWorld: true
    readOnly: true
  name: list-learning-objects
- description: Get detailed information about a specific learning object including instances, skills, and prerequisites.
  hints:
    openWorld: false
    readOnly: true
  name: get-learning-object
- description: List learners, managers, authors, and admin users in Adobe Learning Manager.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new user account in Adobe Learning Manager for a new learner or employee.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-user
- description: List learner enrollments across all learning objects.
  hints:
    openWorld: true
    readOnly: true
  name: list-enrollments
- description: Enroll a learner in a course, certification, or learning program.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: enroll-learner
- description: List all skills defined in the account for skill gap analysis.
  hints:
    openWorld: true
    readOnly: true
  name: list-skills
- description: List badges and achievements available to learners.
  hints:
    openWorld: true
    readOnly: true
  name: list-badges
- description: List certification programs for compliance and credential tracking.
  hints:
    openWorld: true
    readOnly: true
  name: list-certifications
- description: List content catalogs organizing learning objects for targeted delivery.
  hints:
    openWorld: true
    readOnly: true
  name: list-catalogs
- description: Create a bulk export job for learner transcripts or training reports.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-bulk-export-job
- description: Retrieve account-level configuration and settings for Adobe Learning Manager.
  hints:
    openWorld: false
    readOnly: true
  name: get-account
---
