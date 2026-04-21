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
- list lens reviews for a specific workload.
- get workload
- list workloads
- list lens reviews
- designs and reviews cloud workload architectures against aws best practices.
- list lens reviews for a workload.
- generate a consolidated architectural review report across workloads.
- regulatory and organizational policy adherence
- list profiles.
- list lenses
- well-architected
- workload profiles.
- consolidated governance reports.
- manage workloads under architectural review.
- create a new workload to begin an architectural review.
- list answers
- architecture
- get consolidated architectural review report.
- list profiles
- list available aws and custom lenses for architectural reviews.
- create milestone
- cloud governance
- oversight and compliance of cloud architecture decisions
- create a new workload for architectural review.
- list answers for a workload lens review.
- architectural review answers.
- lens catalog for architectural reviews.
- create a milestone to capture review state.
- list all workloads under architectural review in the aws account.
- list architectural review answers for a workload and lens.
- best practices
- compliance
- lens reviews for workloads.
- oversees architectural compliance and risk across the cloud portfolio.
- unified workflow for cloud architects and governance teams to manage workloads, run lens reviews, track answers, create milestones, and generate reports.
- get workload details.
- list all workloads in the account.
- get consolidated report
- single workload management.
- cloud workload design and best practices
- aws
- list available lenses.
- create workload
- get details and metadata for a specific workload.
- workload review milestones.
- save a milestone snapshot of the current workload review state.
- Governance Team
- list workload profiles used to customize reviews.
- Cloud Architect
- workloads
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
