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
- test migration operations
- start production cutover to aws
- monitor all migration jobs
- amazon application migration service
- review migration application groupings to track which servers belong to each application.
- describe jobs
- list all source servers with lifecycle state
- start cutover
- list applications
- list waves
- launch test instances for source servers
- start test
- list all source servers and their current migration lifecycle state to understand readiness.
- execute the production cutover to migrate source servers to aws with minimal downtime.
- finalize the cutover to disconnect replication and complete the migration.
- describe source servers
- cloud migration
- get launch configuration
- launch test instances to validate migration without impacting production source servers.
- migration jobs
- source servers to migrate
- finalize cutover
- review launch settings for a source server to verify target instance type and licensing.
- migration
- terminate test instances
- review replication settings for a source server to ensure correct staging area configuration.
- terminate test instances after validation to avoid unnecessary costs.
- track migration progress at the wave level for large-scale migrations.
- get replication configuration
- aws
- monitor all migration jobs to track progress and identify any failures.
- lift and shift
- cutover migration operations
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
