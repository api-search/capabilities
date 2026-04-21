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
- list content views.
- launch job template
- list recommendation topics.
- managed hosts from satellite.
- ansible get job template
- cloud
- satellite list hosts
- list hosts managed by satellite.
- list content views
- containers
- list job templates
- ansible
- satellite list errata
- list systems
- get details of a job execution.
- insights list topics
- ansible get job
- cancel a running job.
- ansible cancel job
- list all available errata.
- list advisor detection rules.
- automation
- ansible list job templates
- get details of an ansible job template.
- host-level errata.
- kubernetes
- enterprise
- ansible job templates.
- list registered systems.
- list rules
- content views.
- insights get system stats
- advisor rules.
- insights list rules
- get a specific satellite host.
- satellite
- launch an ansible job template.
- insights list systems
- linux
- ansible launch job template
- list ansible inventories.
- ansible list inventories
- list ansible job templates.
- get aggregate system health statistics.
- hybrid cloud
- list software repositories.
- list job templates.
- launch a job template.
- list host errata
- get details for a system in insights.
- open source
- list managed hosts.
- satellite list content views
- list systems registered with insights.
- list hosts
- list jobs.
- list jobs
- automation jobs.
- list advisor rules.
- list automation job executions.
- satellite list repositories
- list errata.
- red hat
- satellite get host
- insights
- list errata applicable to a host.
- insights get system
- launch automation jobs.
- errata advisories.
- satellite list host errata
- list errata
- ansible list jobs
- insights-registered systems.
- list errata for a host.
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
