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
- architectural review answers.
- list lenses
- list lens reviews
- consolidated governance reports.
- get consolidated architectural review report.
- create a new workload to begin an architectural review.
- list available aws and custom lenses for architectural reviews.
- best practices
- create a milestone to capture review state.
- list profiles
- list workloads
- list lens reviews for a specific workload.
- cloud workload design and best practices
- well-architected
- save a milestone snapshot of the current workload review state.
- generate a consolidated architectural review report across workloads.
- create workload
- cloud governance
- create a new workload for architectural review.
- list all workloads under architectural review in the aws account.
- workload review milestones.
- workloads
- single workload management.
- architecture
- oversight and compliance of cloud architecture decisions
- list available lenses.
- list all workloads in the account.
- oversees architectural compliance and risk across the cloud portfolio.
- compliance
- get workload details.
- lens catalog for architectural reviews.
- unified workflow for cloud architects and governance teams to manage workloads, run lens reviews, track answers, create milestones, and generate reports.
- create milestone
- get details and metadata for a specific workload.
- get consolidated report
- list architectural review answers for a workload and lens.
- manage workloads under architectural review.
- lens reviews for workloads.
- designs and reviews cloud workload architectures against aws best practices.
- list workload profiles used to customize reviews.
- list profiles.
- aws
- Governance Team
- get workload
- list lens reviews for a workload.
- regulatory and organizational policy adherence
- list answers for a workload lens review.
- Cloud Architect
- workload profiles.
- list answers
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
