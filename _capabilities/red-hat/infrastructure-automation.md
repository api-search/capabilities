---
categories:
- automation
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
- list all available errata.
- list errata for a host.
- list managed hosts.
- insights-registered systems.
- list systems
- get details of a job execution.
- advisor rules.
- ansible cancel job
- automation
- launch job template
- managed hosts from satellite.
- satellite list hosts
- red hat
- errata advisories.
- launch a job template.
- ansible list job templates
- list hosts managed by satellite.
- get a specific satellite host.
- satellite list host errata
- cloud
- list rules
- hybrid cloud
- list job templates.
- linux
- insights list topics
- list content views.
- list systems registered with insights.
- list jobs
- list errata applicable to a host.
- insights get system stats
- list registered systems.
- content views.
- automation jobs.
- insights
- satellite list repositories
- ansible
- list ansible job templates.
- get aggregate system health statistics.
- launch an ansible job template.
- satellite list errata
- containers
- ansible job templates.
- list errata
- list software repositories.
- ansible get job template
- ansible get job
- insights list systems
- cancel a running job.
- list hosts
- list host errata
- list advisor detection rules.
- insights list rules
- kubernetes
- launch automation jobs.
- get details for a system in insights.
- satellite get host
- list advisor rules.
- get details of an ansible job template.
- list errata.
- insights get system
- list recommendation topics.
- host-level errata.
- list job templates
- list content views
- list automation job executions.
- ansible list inventories
- enterprise
- list ansible inventories.
- satellite
- ansible launch job template
- open source
- list jobs.
- ansible list jobs
- satellite list content views
slug: infrastructure-automation
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Red Hat Infrastructure Automation\"\n  description: \"Unified workflow combining Ansible automation, Satellite content management, and Insights analytics for infrastructure operations teams managing RHEL environments at scale.\"\n  tags:\n    - Red Hat\n    - Ansible\n    - Satellite\n    - Insights\n    - Automation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      RED_HAT_BEARER_TOKEN: RED_HAT_BEARER_TOKEN\n      SATELLITE_USERNAME: SATELLITE_USERNAME\n      SATELLITE_PASSWORD: SATELLITE_PASSWORD\n\ncapability:\n  consumes:\n    - import: ansible-automation\n      location: ./shared/ansible-automation.yaml\n    - import: satellite\n      location: ./shared/satellite.yaml\n    - import: insights\n      location: ./shared/insights.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: infrastructure-automation-api\n      description: \"Unified REST API for RHEL\
  \ infrastructure automation, content management, and analytics.\"\n      resources:\n        - path: /v1/job-templates\n          name: job-templates\n          description: \"Ansible job templates.\"\n          operations:\n            - method: GET\n              name: list-job-templates\n              description: \"List job templates.\"\n              call: \"ansible-automation.list-job-templates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-templates/{id}/launch\n          name: launch-job\n          description: \"Launch automation jobs.\"\n          operations:\n            - method: POST\n              name: launch-job-template\n              description: \"Launch a job template.\"\n              call: \"ansible-automation.launch-job-template\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \        - path: /v1/jobs\n          name: jobs\n          description: \"Automation jobs.\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List jobs.\"\n              call: \"ansible-automation.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hosts\n          name: hosts\n          description: \"Managed hosts from Satellite.\"\n          operations:\n            - method: GET\n              name: list-hosts\n              description: \"List managed hosts.\"\n              call: \"satellite.list-hosts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hosts/{id}/errata\n          name: host-errata\n          description: \"Host-level errata.\"\n          operations:\n            - method: GET\n              name: list-host-errata\n              description: \"List errata\
  \ for a host.\"\n              call: \"satellite.list-host-errata\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content-views\n          name: content-views\n          description: \"Content views.\"\n          operations:\n            - method: GET\n              name: list-content-views\n              description: \"List content views.\"\n              call: \"satellite.list-content-views\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/errata\n          name: errata\n          description: \"Errata advisories.\"\n          operations:\n            - method: GET\n              name: list-errata\n              description: \"List errata.\"\n              call: \"satellite.list-errata\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n        - path: /v1/systems\n          name: systems\n          description: \"Insights-registered systems.\"\n          operations:\n            - method: GET\n              name: list-systems\n              description: \"List registered systems.\"\n              call: \"insights.list-systems\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rules\n          name: rules\n          description: \"Advisor rules.\"\n          operations:\n            - method: GET\n              name: list-rules\n              description: \"List advisor rules.\"\n              call: \"insights.list-rules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: infrastructure-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted RHEL infrastructure automation.\"\n      tools:\n        - name: ansible-list-job-templates\n\
  \          description: \"List Ansible job templates.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ansible-automation.list-job-templates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ansible-get-job-template\n          description: \"Get details of an Ansible job template.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ansible-automation.get-job-template\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ansible-launch-job-template\n          description: \"Launch an Ansible job template.\"\n          hints:\n            readOnly: false\n          call: \"ansible-automation.launch-job-template\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: ansible-list-jobs\n          description: \"List automation job executions.\"\n          hints:\n            readOnly: true\n          call: \"ansible-automation.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ansible-get-job\n          description: \"Get details of a job execution.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ansible-automation.get-job\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ansible-cancel-job\n          description: \"Cancel a running job.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"ansible-automation.cancel-job\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ansible-list-inventories\n\
  \          description: \"List Ansible inventories.\"\n          hints:\n            readOnly: true\n          call: \"ansible-automation.list-inventories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: satellite-list-hosts\n          description: \"List hosts managed by Satellite.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"satellite.list-hosts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: satellite-get-host\n          description: \"Get a specific Satellite host.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"satellite.get-host\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: satellite-list-host-errata\n          description: \"List errata applicable to a host.\"\
  \n          hints:\n            readOnly: true\n          call: \"satellite.list-host-errata\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: satellite-list-content-views\n          description: \"List content views.\"\n          hints:\n            readOnly: true\n          call: \"satellite.list-content-views\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: satellite-list-errata\n          description: \"List all available errata.\"\n          hints:\n            readOnly: true\n          call: \"satellite.list-errata\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: satellite-list-repositories\n          description: \"List software repositories.\"\n          hints:\n            readOnly: true\n          call: \"satellite.list-repositories\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: insights-list-systems\n          description: \"List systems registered with Insights.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"insights.list-systems\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: insights-get-system\n          description: \"Get details for a system in Insights.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"insights.get-system\"\n          with:\n            system_id: \"tools.system_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: insights-list-rules\n          description: \"List Advisor detection rules.\"\n          hints:\n            readOnly: true\n          call: \"insights.list-rules\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: insights-get-system-stats\n          description: \"Get aggregate system health statistics.\"\n          hints:\n            readOnly: true\n          call: \"insights.get-system-stats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: insights-list-topics\n          description: \"List recommendation topics.\"\n          hints:\n            readOnly: true\n          call: \"insights.list-topics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/red-hat/refs/heads/main/capabilities/infrastructure-automation.yaml
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
