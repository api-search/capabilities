---
categories:
- compliance
consumed_apis:
- captivate-prime
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
- list all skills defined in the account for skill gap analysis.
- courses, learning programs, certifications, and job aids.
- learning management
- developer integrating hris systems with adobe learning manager for user provisioning and data sync.
- retrieve account-level configuration and settings for adobe learning manager.
- list all certifications.
- create bulk export job
- list catalogs
- list certifications
- elearning
- HR Integration Developer
- scorm
- list content catalogs organizing learning objects for targeted delivery.
- real-time webhook events for downstream integrations.
- badge and achievement management.
- list badges
- list learner enrollments across all learning objects.
- get account
- certification and mandatory training compliance tracking.
- education
- learner and admin user management.
- list all catalogs.
- enroll a learner in a course, certification, or learning program.
- xapi
- list skills
- get learning object
- create a new user account in adobe learning manager for a new learner or employee.
- learner enrollment management.
- list learning objects
- adobe captivate
- create user
- single learning object details.
- list badges and achievements available to learners.
- authoring
- get details of a specific learning object.
- skill tracking and management.
- list learners, managers, authors, and admin users in adobe learning manager.
- list all available learning objects.
- bulk import/export job management.
- list users
- unified workflow for managing learning objects, enrollments, users, and compliance.
- lms
- list all badges.
- core lms functionality including course delivery, enrollment, and progress tracking.
- list all skills.
- create a new user account.
- compliance
- enroll a learner in a learning object.
- create a bulk export job for learner transcripts or training reports.
- learner progress, skill attainment, and completion reporting.
- list all enrollments.
- certification program management.
- create a bulk data import or export job.
- list certification programs for compliance and credential tracking.
- create bulk job
- learning and development professional managing course catalogs, enrollments, and compliance tracking.
- get detailed information about a specific learning object including instances, skills, and prerequisites.
- training
- list all available courses, learning programs, certifications, and job aids in adobe learning manager.
- list all users in the account.
- list enrollments
- L&D Administrator
- enroll learner
- learning content catalog management.
slug: learning-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adobe Captivate Learning Management\"\n  description: \"Unified workflow capability for managing learning objects, enrollments, completions, and compliance tracking using Adobe Learning Manager APIs. Designed for L&D administrators and HR integration developers.\"\n  tags:\n    - Adobe Captivate\n    - Learning Management\n    - LMS\n    - Compliance\n    - Training\n    - Education\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADOBE_CAPTIVATE_ACCESS_TOKEN: ADOBE_CAPTIVATE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: captivate-prime\n      location: ./shared/captivate-prime-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: learning-management-api\n      description: \"Unified REST API for Adobe Learning Manager — learning objects, users, enrollments, skills, badges, and compliance.\"\n      resources:\n        - path: /v1/learning-objects\n\
  \          name: learning-objects\n          description: \"Courses, learning programs, certifications, and job aids.\"\n          operations:\n            - method: GET\n              name: list-learning-objects\n              description: \"List all available learning objects.\"\n              call: \"captivate-prime.list-learning-objects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/learning-objects/{learningObjectId}\n          name: learning-object\n          description: \"Single learning object details.\"\n          operations:\n            - method: GET\n              name: get-learning-object\n              description: \"Get details of a specific learning object.\"\n              call: \"captivate-prime.get-learning-object\"\n              with:\n                learningObjectId: \"rest.learningObjectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n        - path: /v1/users\n          name: users\n          description: \"Learner and admin user management.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all users in the account.\"\n              call: \"captivate-prime.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a new user account.\"\n              call: \"captivate-prime.create-user\"\n              with:\n                name: \"rest.name\"\n                email: \"rest.email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/enrollments\n          name: enrollments\n          description: \"Learner enrollment management.\"\n          operations:\n            - method: GET\n              name: list-enrollments\n    \
  \          description: \"List all enrollments.\"\n              call: \"captivate-prime.list-enrollments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: enroll-learner\n              description: \"Enroll a learner in a learning object.\"\n              call: \"captivate-prime.create-enrollment\"\n              with:\n                learningObjectId: \"rest.learningObjectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/skills\n          name: skills\n          description: \"Skill tracking and management.\"\n          operations:\n            - method: GET\n              name: list-skills\n              description: \"List all skills.\"\n              call: \"captivate-prime.list-skills\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/badges\n\
  \          name: badges\n          description: \"Badge and achievement management.\"\n          operations:\n            - method: GET\n              name: list-badges\n              description: \"List all badges.\"\n              call: \"captivate-prime.list-badges\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/certifications\n          name: certifications\n          description: \"Certification program management.\"\n          operations:\n            - method: GET\n              name: list-certifications\n              description: \"List all certifications.\"\n              call: \"captivate-prime.list-certifications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/catalogs\n          name: catalogs\n          description: \"Learning content catalog management.\"\n          operations:\n            - method: GET\n              name:\
  \ list-catalogs\n              description: \"List all catalogs.\"\n              call: \"captivate-prime.list-catalogs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name: jobs\n          description: \"Bulk import/export job management.\"\n          operations:\n            - method: POST\n              name: create-bulk-job\n              description: \"Create a bulk data import or export job.\"\n              call: \"captivate-prime.create-job\"\n              with:\n                jobType: \"rest.jobType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: learning-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted learning management — discover courses, manage enrollments, track compliance, and analyze learner progress.\"\n      tools:\n        - name:\
  \ list-learning-objects\n          description: \"List all available courses, learning programs, certifications, and job aids in Adobe Learning Manager.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"captivate-prime.list-learning-objects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-learning-object\n          description: \"Get detailed information about a specific learning object including instances, skills, and prerequisites.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"captivate-prime.get-learning-object\"\n          with:\n            learningObjectId: \"tools.learningObjectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List learners, managers, authors, and admin users in Adobe Learning Manager.\"\n          hints:\n   \
  \         readOnly: true\n            openWorld: true\n          call: \"captivate-prime.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"Create a new user account in Adobe Learning Manager for a new learner or employee.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"captivate-prime.create-user\"\n          with:\n            name: \"tools.name\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-enrollments\n          description: \"List learner enrollments across all learning objects.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"captivate-prime.list-enrollments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n \
  \       - name: enroll-learner\n          description: \"Enroll a learner in a course, certification, or learning program.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"captivate-prime.create-enrollment\"\n          with:\n            learningObjectId: \"tools.learningObjectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-skills\n          description: \"List all skills defined in the account for skill gap analysis.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"captivate-prime.list-skills\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-badges\n          description: \"List badges and achievements available to learners.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"captivate-prime.list-badges\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-certifications\n          description: \"List certification programs for compliance and credential tracking.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"captivate-prime.list-certifications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-catalogs\n          description: \"List content catalogs organizing learning objects for targeted delivery.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"captivate-prime.list-catalogs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bulk-export-job\n          description: \"Create a bulk export job for learner transcripts or training reports.\"\n          hints:\n            readOnly: false\n            destructive: false\n\
  \            idempotent: false\n          call: \"captivate-prime.create-job\"\n          with:\n            jobType: \"tools.jobType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account\n          description: \"Retrieve account-level configuration and settings for Adobe Learning Manager.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"captivate-prime.get-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
