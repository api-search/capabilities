---
consumed_apis: []
description: Workflow capability for executing lift-and-shift migrations from on-premises to AWS using Application Migration Service.
layout: capability
name: Lift And Shift Migration Workflow
operations:
- description: List all source servers with lifecycle state
  method: GET
  name: describe-source-servers
  path: /v1/source-servers
- description: Launch test instances for source servers
  method: POST
  name: start-test
  path: /v1/test
- description: Start production cutover to AWS
  method: POST
  name: start-cutover
  path: /v1/cutover
- description: Monitor all migration jobs
  method: GET
  name: describe-jobs
  path: /v1/jobs
personas: []
provider_name: Amazon Application Migration Service
provider_slug: amazon-application-migration-service
search_terms:
- list all source servers with lifecycle state
- execute the production cutover to migrate source servers to aws with minimal downtime.
- launch test instances to validate migration without impacting production source servers.
- source servers to migrate
- start cutover
- finalize the cutover to disconnect replication and complete the migration.
- describe jobs
- amazon application migration service
- test migration operations
- list waves
- cloud migration
- start production cutover to aws
- list applications
- cutover migration operations
- finalize cutover
- lift and shift
- get launch configuration
- track migration progress at the wave level for large-scale migrations.
- monitor all migration jobs to track progress and identify any failures.
- monitor all migration jobs
- terminate test instances
- review migration application groupings to track which servers belong to each application.
- migration jobs
- aws
- migration
- get replication configuration
- describe source servers
- start test
- review launch settings for a source server to verify target instance type and licensing.
- launch test instances for source servers
- review replication settings for a source server to ensure correct staging area configuration.
- terminate test instances after validation to avoid unnecessary costs.
- list all source servers and their current migration lifecycle state to understand readiness.
slug: lift-and-shift-migration
tags:
- Amazon Application Migration Service
- Migration
- Lift And Shift
- AWS
- Cloud Migration
tools:
- description: List all source servers and their current migration lifecycle state to understand readiness.
  hints:
    openWorld: true
    readOnly: true
  name: describe-source-servers
- description: Review replication settings for a source server to ensure correct staging area configuration.
  hints:
    openWorld: true
    readOnly: true
  name: get-replication-configuration
- description: Review launch settings for a source server to verify target instance type and licensing.
  hints:
    openWorld: true
    readOnly: true
  name: get-launch-configuration
- description: Launch test instances to validate migration without impacting production source servers.
  hints:
    openWorld: false
    readOnly: false
  name: start-test
- description: Terminate test instances after validation to avoid unnecessary costs.
  hints:
    openWorld: false
    readOnly: false
  name: terminate-test-instances
- description: Execute the production cutover to migrate source servers to AWS with minimal downtime.
  hints:
    openWorld: false
    readOnly: false
  name: start-cutover
- description: Finalize the cutover to disconnect replication and complete the migration.
  hints:
    openWorld: false
    readOnly: false
  name: finalize-cutover
- description: Monitor all migration jobs to track progress and identify any failures.
  hints:
    openWorld: true
    readOnly: true
  name: describe-jobs
- description: Review migration application groupings to track which servers belong to each application.
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Track migration progress at the wave level for large-scale migrations.
  hints:
    openWorld: true
    readOnly: true
  name: list-waves
---
