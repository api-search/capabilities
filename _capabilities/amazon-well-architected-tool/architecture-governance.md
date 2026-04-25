---
consumed_apis:
- well-architected-tool
description: Unified workflow for architecture governance using the AWS Well-Architected Tool. Enables cloud architects and governance teams to manage workloads, run lens reviews, track answers, create milestones, and generate consolidated reports across the organization's cloud portfolio.
layout: capability
name: Amazon Well-Architected Tool Architecture Governance
operations:
- description: List all workloads in the account.
  method: GET
  name: list-workloads
  path: /v1/workloads
- description: Create a new workload for architectural review.
  method: POST
  name: create-workload
  path: /v1/workloads
- description: Get workload details.
  method: GET
  name: get-workload
  path: /v1/workloads/{id}
- description: List available lenses.
  method: GET
  name: list-lenses
  path: /v1/lenses
- description: List lens reviews for a workload.
  method: GET
  name: list-lens-reviews
  path: /v1/reviews
- description: List answers for a workload lens review.
  method: GET
  name: list-answers
  path: /v1/answers
- description: Create a milestone to capture review state.
  method: POST
  name: create-milestone
  path: /v1/milestones
- description: List profiles.
  method: GET
  name: list-profiles
  path: /v1/profiles
- description: Get consolidated architectural review report.
  method: GET
  name: get-consolidated-report
  path: /v1/reports
personas: []
provider_name: Amazon Well-Architected Tool
provider_slug: amazon-well-architected-tool
search_terms:
- list lens reviews for a workload.
- unified workflow for cloud architects and governance teams to manage workloads, run lens reviews, track answers, create milestones, and generate reports.
- Cloud Architect
- list lens reviews for a specific workload.
- generate a consolidated architectural review report across workloads.
- list lens reviews
- list profiles
- oversight and compliance of cloud architecture decisions
- oversees architectural compliance and risk across the cloud portfolio.
- create workload
- Governance Team
- list all workloads in the account.
- get workload details.
- get details and metadata for a specific workload.
- cloud governance
- list available aws and custom lenses for architectural reviews.
- list answers
- designs and reviews cloud workload architectures against aws best practices.
- list lenses
- create milestone
- get workload
- get consolidated report
- cloud workload design and best practices
- workload profiles.
- list profiles.
- compliance
- list workloads
- create a new workload to begin an architectural review.
- regulatory and organizational policy adherence
- lens reviews for workloads.
- well-architected
- lens catalog for architectural reviews.
- architectural review answers.
- create a new workload for architectural review.
- consolidated governance reports.
- save a milestone snapshot of the current workload review state.
- best practices
- workloads
- list workload profiles used to customize reviews.
- workload review milestones.
- single workload management.
- aws
- create a milestone to capture review state.
- get consolidated architectural review report.
- manage workloads under architectural review.
- list answers for a workload lens review.
- list architectural review answers for a workload and lens.
- architecture
- list all workloads under architectural review in the aws account.
- list available lenses.
slug: architecture-governance
tags:
- Architecture
- AWS
- Cloud Governance
- Well-Architected
- Compliance
tools:
- description: List all workloads under architectural review in the AWS account.
  hints:
    openWorld: true
    readOnly: true
  name: list-workloads
- description: Get details and metadata for a specific workload.
  hints:
    openWorld: false
    readOnly: true
  name: get-workload
- description: Create a new workload to begin an architectural review.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-workload
- description: List available AWS and custom lenses for architectural reviews.
  hints:
    openWorld: true
    readOnly: true
  name: list-lenses
- description: List lens reviews for a specific workload.
  hints:
    openWorld: false
    readOnly: true
  name: list-lens-reviews
- description: List architectural review answers for a workload and lens.
  hints:
    openWorld: false
    readOnly: true
  name: list-answers
- description: Save a milestone snapshot of the current workload review state.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-milestone
- description: List workload profiles used to customize reviews.
  hints:
    openWorld: true
    readOnly: true
  name: list-profiles
- description: Generate a consolidated architectural review report across workloads.
  hints:
    openWorld: true
    readOnly: true
  name: get-consolidated-report
---
