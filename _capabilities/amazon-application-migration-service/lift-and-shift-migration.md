---
categories: []
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
- monitor all migration jobs to track progress and identify any failures.
- start test
- review launch settings for a source server to verify target instance type and licensing.
- execute the production cutover to migrate source servers to aws with minimal downtime.
- test migration operations
- cutover migration operations
- track migration progress at the wave level for large-scale migrations.
- get launch configuration
- start production cutover to aws
- describe source servers
- list applications
- list all source servers and their current migration lifecycle state to understand readiness.
- aws
- get replication configuration
- finalize the cutover to disconnect replication and complete the migration.
- describe jobs
- cloud migration
- review replication settings for a source server to ensure correct staging area configuration.
- migration jobs
- launch test instances to validate migration without impacting production source servers.
- list waves
- list all source servers with lifecycle state
- start cutover
- finalize cutover
- migration
- lift and shift
- monitor all migration jobs
- amazon application migration service
- terminate test instances after validation to avoid unnecessary costs.
- launch test instances for source servers
- source servers to migrate
- review migration application groupings to track which servers belong to each application.
- terminate test instances
slug: lift-and-shift-migration
source_filename: lift-and-shift-migration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Lift And Shift Migration Workflow\n  description: Workflow capability for executing lift-and-shift migrations from on-premises to AWS using Application Migration Service.\n  tags:\n    - Amazon Application Migration Service\n    - Migration\n    - Lift And Shift\n    - AWS\n    - Cloud Migration\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nimports:\n  - namespace: mgn\n    from: shared/application-migration-service-api.yaml\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: lift-shift-rest\n      resources:\n        - path: /v1/source-servers\n          name: source-servers\n          description: Source servers to migrate\n          operations:\n            - method: GET\n              name: describe-source-servers\n              description: List all source servers with lifecycle state\n              call: \"mgn.describe-source-servers\"\n              outputParameters:\n             \
  \   - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/test\n          name: test-migration\n          description: Test migration operations\n          operations:\n            - method: POST\n              name: start-test\n              description: Launch test instances for source servers\n              call: \"mgn.start-test\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cutover\n          name: cutover\n          description: Cutover migration operations\n          operations:\n            - method: POST\n              name: start-cutover\n              description: Start production cutover to AWS\n              call: \"mgn.start-cutover\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/jobs\n          name: jobs\n          description: Migration jobs\n          operations:\n            - method: GET\n     \
  \         name: describe-jobs\n              description: Monitor all migration jobs\n              call: \"mgn.describe-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: lift-shift-mcp\n      transport: http\n      tools:\n        - name: describe-source-servers\n          description: List all source servers and their current migration lifecycle state to understand readiness.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mgn.describe-source-servers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-replication-configuration\n          description: Review replication settings for a source server to ensure correct staging area configuration.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mgn.get-replication-configuration\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-launch-configuration\n          description: Review launch settings for a source server to verify target instance type and licensing.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mgn.get-launch-configuration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-test\n          description: Launch test instances to validate migration without impacting production source servers.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"mgn.start-test\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: terminate-test-instances\n          description: Terminate test instances after validation to avoid unnecessary costs.\n          hints:\n            readOnly: false\n          \
  \  openWorld: false\n          call: \"mgn.terminate-target-instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-cutover\n          description: Execute the production cutover to migrate source servers to AWS with minimal downtime.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"mgn.start-cutover\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: finalize-cutover\n          description: Finalize the cutover to disconnect replication and complete the migration.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"mgn.finalize-cutover\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-jobs\n          description: Monitor all migration jobs to track progress and identify any failures.\n          hints:\n \
  \           readOnly: true\n            openWorld: true\n          call: \"mgn.describe-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-applications\n          description: Review migration application groupings to track which servers belong to each application.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mgn.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-waves\n          description: Track migration progress at the wave level for large-scale migrations.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mgn.list-waves\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\npersonas:\n  - name: Migration Engineer\n    description: Executes day-to-day migration tasks including testing and cutover operations.\n\
  \    tools:\n      - describe-source-servers\n      - get-replication-configuration\n      - get-launch-configuration\n      - start-test\n      - terminate-test-instances\n      - start-cutover\n      - finalize-cutover\n      - describe-jobs\n\n  - name: Migration Project Manager\n    description: Oversees migration progress across applications and waves.\n    tools:\n      - describe-source-servers\n      - describe-jobs\n      - list-applications\n      - list-waves\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-application-migration-service/refs/heads/main/capabilities/lift-and-shift-migration.yaml
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
