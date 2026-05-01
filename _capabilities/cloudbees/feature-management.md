---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Feature Management
operations: []
personas: []
provider_name: CloudBees
provider_slug: cloudbees
search_terms:
- feature flags
- ci/cd
- continuous integration
- software delivery
- devops
- jenkins
- feature management
- continuous delivery
- release orchestration
slug: feature-management
source_filename: feature-management.yaml
source_heading: Capability Spec
source_yaml: "# Naftiko capabilities profile for CloudBees Feature Management.\n# Maps verbs against the CloudBees Feature Management REST API\n# (formerly Rollout) for applications, environments, feature flags,\n# target groups, experiments, audit log, and users.\nprovider: cloudbees\nname: CloudBees Feature Management\ndescription: >-\n  Capabilities cover managing applications and environments, defining and\n  toggling feature flags, configuring target groups and experiments, and\n  reading audit history. Authentication is via bearer token; the API\n  enforces one request per second per IP.\ncapabilities:\n  - id: cloudbees.fm.applications.list\n    name: List applications\n    description: Return all applications visible to the calling token.\n    api: cloudbees:feature-management\n    outputs:\n      - items\n\n  - id: cloudbees.fm.environments.list\n    name: List environments\n    description: Return all environments under a specific application.\n    api: cloudbees:feature-management\n\
  \    inputs:\n      - application_id\n    outputs:\n      - items\n\n  - id: cloudbees.fm.environments.create\n    name: Create environment\n    description: Add a new environment to an application, optionally returning the SDK key.\n    api: cloudbees:feature-management\n    inputs:\n      - application_id\n      - name\n      - description\n    outputs:\n      - environment_key\n      - status\n\n  - id: cloudbees.fm.environments.update\n    name: Update environment\n    description: Modify an existing environment's properties.\n    api: cloudbees:feature-management\n    inputs:\n      - application_id\n      - environment_key\n      - name\n      - description\n    outputs:\n      - status\n\n  - id: cloudbees.fm.environments.delete\n    name: Delete environment\n    description: Remove an environment from an application.\n    api: cloudbees:feature-management\n    inputs:\n      - application_id\n      - environment_key\n    outputs:\n      - status\n\n  - id: cloudbees.fm.flags.list\n\
  \    name: List feature flags\n    description: Return all feature flags under an application.\n    api: cloudbees:feature-management\n    inputs:\n      - application_id\n      - environment_key\n    outputs:\n      - items\n\n  - id: cloudbees.fm.flags.create\n    name: Create feature flag\n    description: Define a new feature flag with type and default value.\n    api: cloudbees:feature-management\n    inputs:\n      - application_id\n      - name\n      - type\n      - default_value\n      - is_permanent\n    outputs:\n      - id\n      - status\n\n  - id: cloudbees.fm.flags.update\n    name: Update feature flag value\n    description: Update a flag's value for a given environment.\n    api: cloudbees:feature-management\n    inputs:\n      - application_id\n      - environment_key\n      - flag_id\n      - value\n      - target_groups\n    outputs:\n      - status\n\n  - id: cloudbees.fm.target-groups.list\n    name: List target groups\n    description: Return target groups for an\
  \ application.\n    api: cloudbees:feature-management\n    inputs:\n      - application_id\n    outputs:\n      - items\n\n  - id: cloudbees.fm.experiments.list\n    name: List experiments\n    description: Return active experiments for an application.\n    api: cloudbees:feature-management\n    inputs:\n      - application_id\n    outputs:\n      - items\n\n  - id: cloudbees.fm.audit.list\n    name: List audit events\n    description: Return audit log entries for an application.\n    api: cloudbees:feature-management\n    inputs:\n      - application_id\n      - from_date\n      - to_date\n    outputs:\n      - items\n\n  - id: cloudbees.ci.builds.trigger\n    name: Trigger Jenkins build (CloudBees CI)\n    description: Trigger a job on a CloudBees CI controller via the Jenkins remote API.\n    api: cloudbees:ci\n    inputs:\n      - controller_url\n      - job_name\n      - parameters\n      - token\n    outputs:\n      - queue_id\n\n  - id: cloudbees.ci.builds.status\n    name: Get\
  \ Jenkins build status\n    description: Retrieve build status, duration and console URL.\n    api: cloudbees:ci\n    inputs:\n      - controller_url\n      - job_name\n      - build_number\n    outputs:\n      - result\n      - duration\n      - url\n\n  - id: cloudbees.cd.pipelines.run\n    name: Run CD/RO pipeline\n    description: Launch a CloudBees CD/RO pipeline run for a project.\n    api: cloudbees:cd-ro\n    inputs:\n      - project_name\n      - pipeline_name\n      - parameters\n    outputs:\n      - flow_runtime_id\n      - status\n\n  - id: cloudbees.cd.releases.run\n    name: Run CD/RO release\n    description: Start a release in CloudBees CD/RO.\n    api: cloudbees:cd-ro\n    inputs:\n      - project_name\n      - release_name\n    outputs:\n      - flow_runtime_id\n      - status\n\n  - id: cloudbees.cd.deployments.status\n    name: Get deployment status\n    description: Retrieve deployment progress for an application instance.\n    api: cloudbees:cd-ro\n    inputs:\n\
  \      - project_name\n      - deployment_id\n    outputs:\n      - status\n      - environment\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloudbees/refs/heads/main/capabilities/feature-management.yaml
tags: []
tools: []
---
