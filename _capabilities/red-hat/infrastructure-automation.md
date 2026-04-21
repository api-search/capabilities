---
consumed_apis:
- ansible-automation
- satellite
- insights
description: Unified workflow combining Ansible automation, Satellite content management, and Insights analytics for infrastructure operations teams managing RHEL environments at scale.
layout: capability
name: Red Hat Infrastructure Automation
operations:
- description: List job templates.
  method: GET
  name: list-job-templates
  path: /v1/job-templates
- description: Launch a job template.
  method: POST
  name: launch-job-template
  path: /v1/job-templates/{id}/launch
- description: List jobs.
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: List managed hosts.
  method: GET
  name: list-hosts
  path: /v1/hosts
- description: List errata for a host.
  method: GET
  name: list-host-errata
  path: /v1/hosts/{id}/errata
- description: List content views.
  method: GET
  name: list-content-views
  path: /v1/content-views
- description: List errata.
  method: GET
  name: list-errata
  path: /v1/errata
- description: List registered systems.
  method: GET
  name: list-systems
  path: /v1/systems
- description: List advisor rules.
  method: GET
  name: list-rules
  path: /v1/rules
personas: []
provider_name: Red Hat
provider_slug: red-hat
search_terms:
- insights-registered systems.
- content views.
- ansible list jobs
- ansible
- get details of a job execution.
- insights get system
- ansible job templates.
- managed hosts from satellite.
- list content views
- satellite list repositories
- list advisor rules.
- errata advisories.
- enterprise
- containers
- ansible launch job template
- satellite list host errata
- list hosts
- ansible cancel job
- satellite list hosts
- list recommendation topics.
- kubernetes
- cancel a running job.
- insights list rules
- ansible list job templates
- satellite get host
- list job templates.
- satellite
- advisor rules.
- ansible get job template
- ansible list inventories
- launch a job template.
- list content views.
- list advisor detection rules.
- linux
- launch an ansible job template.
- list rules
- list all available errata.
- list errata for a host.
- get details for a system in insights.
- list software repositories.
- insights
- list registered systems.
- list jobs.
- automation
- ansible get job
- list systems registered with insights.
- list jobs
- list host errata
- get aggregate system health statistics.
- insights list topics
- launch automation jobs.
- list managed hosts.
- get details of an ansible job template.
- list errata.
- red hat
- list automation job executions.
- hybrid cloud
- list systems
- insights get system stats
- cloud
- automation jobs.
- insights list systems
- satellite list errata
- get a specific satellite host.
- launch job template
- list hosts managed by satellite.
- list errata applicable to a host.
- list ansible inventories.
- list errata
- open source
- satellite list content views
- host-level errata.
- list job templates
- list ansible job templates.
slug: infrastructure-automation
tags:
- Red Hat
- Ansible
- Satellite
- Insights
- Automation
tools:
- description: List Ansible job templates.
  hints:
    openWorld: true
    readOnly: true
  name: ansible-list-job-templates
- description: Get details of an Ansible job template.
  hints:
    idempotent: true
    readOnly: true
  name: ansible-get-job-template
- description: Launch an Ansible job template.
  hints:
    readOnly: false
  name: ansible-launch-job-template
- description: List automation job executions.
  hints:
    readOnly: true
  name: ansible-list-jobs
- description: Get details of a job execution.
  hints:
    idempotent: true
    readOnly: true
  name: ansible-get-job
- description: Cancel a running job.
  hints:
    destructive: true
    readOnly: false
  name: ansible-cancel-job
- description: List Ansible inventories.
  hints:
    readOnly: true
  name: ansible-list-inventories
- description: List hosts managed by Satellite.
  hints:
    openWorld: true
    readOnly: true
  name: satellite-list-hosts
- description: Get a specific Satellite host.
  hints:
    idempotent: true
    readOnly: true
  name: satellite-get-host
- description: List errata applicable to a host.
  hints:
    readOnly: true
  name: satellite-list-host-errata
- description: List content views.
  hints:
    readOnly: true
  name: satellite-list-content-views
- description: List all available errata.
  hints:
    readOnly: true
  name: satellite-list-errata
- description: List software repositories.
  hints:
    readOnly: true
  name: satellite-list-repositories
- description: List systems registered with Insights.
  hints:
    openWorld: true
    readOnly: true
  name: insights-list-systems
- description: Get details for a system in Insights.
  hints:
    idempotent: true
    readOnly: true
  name: insights-get-system
- description: List Advisor detection rules.
  hints:
    readOnly: true
  name: insights-list-rules
- description: Get aggregate system health statistics.
  hints:
    readOnly: true
  name: insights-get-system-stats
- description: List recommendation topics.
  hints:
    readOnly: true
  name: insights-list-topics
---
