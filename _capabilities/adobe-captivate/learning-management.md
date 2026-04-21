---
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
- list skills
- list learners, managers, authors, and admin users in adobe learning manager.
- list all skills.
- list all available learning objects.
- list enrollments
- enroll learner
- list content catalogs organizing learning objects for targeted delivery.
- authoring
- L&D Administrator
- create a new user account in adobe learning manager for a new learner or employee.
- learning content catalog management.
- learning and development professional managing course catalogs, enrollments, and compliance tracking.
- bulk import/export job management.
- create a new user account.
- scorm
- skill tracking and management.
- lms
- list all certifications.
- developer integrating hris systems with adobe learning manager for user provisioning and data sync.
- create bulk export job
- list all available courses, learning programs, certifications, and job aids in adobe learning manager.
- training
- badge and achievement management.
- HR Integration Developer
- enroll a learner in a course, certification, or learning program.
- education
- single learning object details.
- xapi
- create a bulk data import or export job.
- get details of a specific learning object.
- create a bulk export job for learner transcripts or training reports.
- core lms functionality including course delivery, enrollment, and progress tracking.
- list certification programs for compliance and credential tracking.
- list certifications
- list all badges.
- list all users in the account.
- learning management
- list badges and achievements available to learners.
- retrieve account-level configuration and settings for adobe learning manager.
- get detailed information about a specific learning object including instances, skills, and prerequisites.
- courses, learning programs, certifications, and job aids.
- learner and admin user management.
- list all enrollments.
- compliance
- certification program management.
- list learner enrollments across all learning objects.
- learner enrollment management.
- get account
- list badges
- enroll a learner in a learning object.
- learner progress, skill attainment, and completion reporting.
- list catalogs
- real-time webhook events for downstream integrations.
- adobe captivate
- unified workflow for managing learning objects, enrollments, users, and compliance.
- list learning objects
- create bulk job
- list all skills defined in the account for skill gap analysis.
- certification and mandatory training compliance tracking.
- list all catalogs.
- elearning
- get learning object
- list users
- create user
slug: learning-management
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
