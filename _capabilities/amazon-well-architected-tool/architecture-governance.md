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
- Governance Team
- oversight and compliance of cloud architecture decisions
- regulatory and organizational policy adherence
- list all workloads in the account.
- create milestone
- get details and metadata for a specific workload.
- list all workloads under architectural review in the aws account.
- lens catalog for architectural reviews.
- create a new workload to begin an architectural review.
- oversees architectural compliance and risk across the cloud portfolio.
- lens reviews for workloads.
- generate a consolidated architectural review report across workloads.
- single workload management.
- architecture
- manage workloads under architectural review.
- workload profiles.
- list lenses
- best practices
- save a milestone snapshot of the current workload review state.
- create a milestone to capture review state.
- cloud workload design and best practices
- well-architected
- unified workflow for cloud architects and governance teams to manage workloads, run lens reviews, track answers, create milestones, and generate reports.
- create a new workload for architectural review.
- list workload profiles used to customize reviews.
- Cloud Architect
- aws
- workloads
- list lens reviews
- designs and reviews cloud workload architectures against aws best practices.
- list profiles.
- get workload
- list profiles
- cloud governance
- workload review milestones.
- consolidated governance reports.
- list lens reviews for a specific workload.
- architectural review answers.
- get consolidated architectural review report.
- create workload
- list answers for a workload lens review.
- list lens reviews for a workload.
- list available aws and custom lenses for architectural reviews.
- list available lenses.
- get workload details.
- get consolidated report
- list architectural review answers for a workload and lens.
- list workloads
- list answers
- compliance
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
