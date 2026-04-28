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
- badge and achievement management.
- list learners, managers, authors, and admin users in adobe learning manager.
- get details of a specific learning object.
- learner and admin user management.
- list users
- list enrollments
- list all badges.
- create a bulk data import or export job.
- single learning object details.
- enroll a learner in a learning object.
- list learning objects
- list all users in the account.
- real-time webhook events for downstream integrations.
- list all available courses, learning programs, certifications, and job aids in adobe learning manager.
- learner progress, skill attainment, and completion reporting.
- compliance
- create a bulk export job for learner transcripts or training reports.
- lms
- create a new user account.
- list all available learning objects.
- skill tracking and management.
- create bulk job
- create a new user account in adobe learning manager for a new learner or employee.
- list skills
- core lms functionality including course delivery, enrollment, and progress tracking.
- certification program management.
- create bulk export job
- list badges and achievements available to learners.
- courses, learning programs, certifications, and job aids.
- create user
- list all skills defined in the account for skill gap analysis.
- unified workflow for managing learning objects, enrollments, users, and compliance.
- certification and mandatory training compliance tracking.
- developer integrating hris systems with adobe learning manager for user provisioning and data sync.
- list all catalogs.
- get detailed information about a specific learning object including instances, skills, and prerequisites.
- get learning object
- list all enrollments.
- bulk import/export job management.
- list all certifications.
- get account
- education
- list content catalogs organizing learning objects for targeted delivery.
- learning management
- learning and development professional managing course catalogs, enrollments, and compliance tracking.
- xapi
- learning content catalog management.
- enroll a learner in a course, certification, or learning program.
- list certifications
- training
- authoring
- learner enrollment management.
- L&D Administrator
- adobe captivate
- enroll learner
- HR Integration Developer
- scorm
- list certification programs for compliance and credential tracking.
- list badges
- list catalogs
- list learner enrollments across all learning objects.
- list all skills.
- elearning
- retrieve account-level configuration and settings for adobe learning manager.
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
