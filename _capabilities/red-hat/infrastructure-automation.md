---
categories:
- automation
consumed_apis: []
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
- ansible cancel job
- satellite get host
- linux
- advisor rules.
- satellite list errata
- satellite list host errata
- get details of an ansible job template.
- list errata
- list jobs
- satellite list repositories
- ansible get job template
- list all available errata.
- insights get system
- content views.
- launch an ansible job template.
- cancel a running job.
- errata advisories.
- list host errata
- get details for a system in insights.
- list automation job executions.
- ansible get job
- red hat
- get details of a job execution.
- managed hosts from satellite.
- hybrid cloud
- insights
- get aggregate system health statistics.
- list content views
- list job templates.
- cloud
- list ansible inventories.
- containers
- enterprise
- automation jobs.
- list errata.
- host-level errata.
- satellite
- list systems
- ansible launch job template
- list content views.
- satellite list content views
- insights-registered systems.
- satellite list hosts
- list hosts managed by satellite.
- kubernetes
- launch job template
- list software repositories.
- launch automation jobs.
- list systems registered with insights.
- insights list rules
- launch a job template.
- list jobs.
- list registered systems.
- ansible list inventories
- insights list systems
- insights list topics
- list advisor rules.
- get a specific satellite host.
- ansible list jobs
- list managed hosts.
- ansible
- list job templates
- list hosts
- list advisor detection rules.
- open source
- ansible job templates.
- list ansible job templates.
- list rules
- insights get system stats
- ansible list job templates
- list errata applicable to a host.
- list recommendation topics.
- list errata for a host.
- automation
slug: infrastructure-automation
source_filename: infrastructure-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Red Hat Infrastructure Automation\n  description: Unified workflow combining Ansible automation, Satellite content management, and Insights analytics for infrastructure\n    operations teams managing RHEL environments at scale.\n  tags:\n  - Red Hat\n  - Ansible\n  - Satellite\n  - Insights\n  - Automation\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RED_HAT_BEARER_TOKEN: RED_HAT_BEARER_TOKEN\n    SATELLITE_USERNAME: SATELLITE_USERNAME\n    SATELLITE_PASSWORD: SATELLITE_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: ansible-automation\n    baseUri: https://ansible-platform.example.com\n    description: Red Hat Ansible Automation Platform API for managing automation jobs and infrastructure.\n    authentication:\n      type: bearer\n      token: '{{RED_HAT_BEARER_TOKEN}}'\n    resources:\n    - name: job-templates\n      path: /api/v2/job_templates\n      description: Manage\
  \ job templates that define parameterized playbook runs.\n      operations:\n      - name: list-job-templates\n        method: GET\n        description: List all job templates.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-job-template\n        method: POST\n        description: Create a new job template.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            project: '{{tools.project}}'\n            playbook: '{{tools.playbook}}'\n            inventory: '{{tools.inventory}}'\n      - name: get-job-template\n        method: GET\n        description: Retrieve a specific job template by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Job template ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-job-template\n        method: PATCH\n        description: Update an existing job template.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Job template ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-job-template\n        method: DELETE\n        description: Delete a job template.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Job template ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: launch-job-template\n        method: POST\n        description: Launch a job from a job template.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Job template ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            extra_vars: '{{tools.extra_vars}}'\n\
  \    - name: jobs\n      path: /api/v2/jobs\n      description: Monitor and manage automation job executions.\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List all jobs.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job\n        method: GET\n        description: Retrieve a specific job by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-job\n        method: POST\n        description: Cancel a running job.\n        inputParameters:\n        - name:\
  \ id\n          in: path\n          type: integer\n          required: true\n          description: Job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventories\n      path: /api/v2/inventories\n      description: Manage inventories of hosts for automation targeting.\n      operations:\n      - name: list-inventories\n        method: GET\n        description: List all inventories.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-inventory\n        method: POST\n        description: Create a new inventory.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            organization: '{{tools.organization}}'\n    - name: projects\n      path: /api/v2/projects\n      description: Manage projects representing Ansible playbook collections.\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all projects.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credentials\n      path: /api/v2/credentials\n      description: Manage credentials for automation jobs.\n      operations:\n      - name: list-credentials\n        method: GET\n        description: List all credentials.\n        inputParameters:\n        - name: page\n          in: query\n       \
  \   type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-job-templates\n      path: /api/v2/workflow_job_templates\n      description: Manage workflow job templates for orchestrated automation.\n      operations:\n      - name: list-workflow-job-templates\n        method: GET\n        description: List all workflow job templates.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n      path: /api/v2/organizations\n      description: Manage organizations for multi-tenancy.\n      operations:\n      - name: list-organizations\n        method: GET\n        description:\
  \ List all organizations.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: satellite\n    baseUri: https://satellite.example.com\n    description: Red Hat Satellite API for infrastructure and content management.\n    authentication:\n      type: basic\n      username: '{{SATELLITE_USERNAME}}'\n      password: '{{SATELLITE_PASSWORD}}'\n    resources:\n    - name: hosts\n      path: /api/v2/hosts\n      description: Manage hosts registered with Satellite.\n      operations:\n      - name: list-hosts\n        method: GET\n        description: List all managed hosts.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n    \
  \    - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-host\n        method: GET\n        description: Get a specific host.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Host ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-host\n        method: PUT\n        description: Update a host.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Host ID\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            host:\n              name: '{{tools.name}}'\n      - name: delete-host\n        method: DELETE\n        description: Delete a host.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Host ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-host-errata\n        method: GET\n        description: List errata applicable to a host.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Host ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-views\n\
  \      path: /katello/api/v2/content_views\n      description: Manage content views for controlled content delivery.\n      operations:\n      - name: list-content-views\n        method: GET\n        description: List all content views.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-content-view\n        method: POST\n        description: Create a new content view.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            organization_id: '{{tools.organization_id}}'\n    - name: environments\n      path: /katello/api/v2/organizations/{organization_id}/environments\n      description: Manage lifecycle environments.\n      operations:\n      - name: list-environments\n\
  \        method: GET\n        description: List lifecycle environments.\n        inputParameters:\n        - name: organization_id\n          in: path\n          type: integer\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories\n      path: /katello/api/v2/repositories\n      description: Manage software repositories.\n      operations:\n      - name: list-repositories\n        method: GET\n        description: List all repositories.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n      path: /api/v2/organizations\n      description: Manage organizations.\n      operations:\n      - name: list-organizations\n        method: GET\n        description: List all organizations.\n        inputParameters:\
  \ []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: host-groups\n      path: /api/v2/hostgroups\n      description: Manage host groups.\n      operations:\n      - name: list-host-groups\n        method: GET\n        description: List all host groups.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: errata\n      path: /katello/api/v2/errata\n      description: Manage errata advisories.\n      operations:\n      - name: list-errata\n        method: GET\n        description: List all available errata.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: insights\n    baseUri: https://console.redhat.com/api\n    description: Red Hat Insights API\
  \ for predictive analytics and remediation.\n    authentication:\n      type: bearer\n      token: '{{RED_HAT_BEARER_TOKEN}}'\n    resources:\n    - name: systems\n      path: /insights/v1/system\n      description: Manage registered RHEL systems.\n      operations:\n      - name: list-systems\n        method: GET\n        description: List all registered RHEL systems.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: display_name\n          in: query\n          type: string\n          required: false\n          description: Filter by display name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-system\n        method:\
  \ GET\n        description: Retrieve a specific system by ID.\n        inputParameters:\n        - name: system_id\n          in: path\n          type: string\n          required: true\n          description: System UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rules\n      path: /insights/v1/rule\n      description: Manage Advisor rules for issue detection.\n      operations:\n      - name: list-rules\n        method: GET\n        description: List all Advisor rules.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-rule\n        method: GET\n        description: Retrieve a specific rule.\n        inputParameters:\n      \
  \  - name: rule_id\n          in: path\n          type: string\n          required: true\n          description: Rule ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-rule-systems\n        method: GET\n        description: List systems affected by a specific rule.\n        inputParameters:\n        - name: rule_id\n          in: path\n          type: string\n          required: true\n          description: Rule ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topics\n      path: /insights/v1/topic\n      description: Curated topics grouping related recommendations.\n      operations:\n      - name: list-topics\n        method: GET\n        description: List all curated topics.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: stats\n      path: /insights/v1/stats\n      description: Aggregate statistics about system health.\n      operations:\n      - name: get-system-stats\n        method: GET\n        description: Get aggregate system statistics.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-rule-stats\n        method: GET\n        description: Get aggregate rule statistics.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: infrastructure-automation-api\n    description: Unified REST API for RHEL infrastructure automation, content management, and analytics.\n    resources:\n    - path: /v1/job-templates\n      name: job-templates\n      description: Ansible job templates.\n\
  \      operations:\n      - method: GET\n        name: list-job-templates\n        description: List job templates.\n        call: ansible-automation.list-job-templates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/job-templates/{id}/launch\n      name: launch-job\n      description: Launch automation jobs.\n      operations:\n      - method: POST\n        name: launch-job-template\n        description: Launch a job template.\n        call: ansible-automation.launch-job-template\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Automation jobs.\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List jobs.\n        call: ansible-automation.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hosts\n      name: hosts\n      description: Managed\
  \ hosts from Satellite.\n      operations:\n      - method: GET\n        name: list-hosts\n        description: List managed hosts.\n        call: satellite.list-hosts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hosts/{id}/errata\n      name: host-errata\n      description: Host-level errata.\n      operations:\n      - method: GET\n        name: list-host-errata\n        description: List errata for a host.\n        call: satellite.list-host-errata\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content-views\n      name: content-views\n      description: Content views.\n      operations:\n      - method: GET\n        name: list-content-views\n        description: List content views.\n        call: satellite.list-content-views\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/errata\n      name: errata\n      description:\
  \ Errata advisories.\n      operations:\n      - method: GET\n        name: list-errata\n        description: List errata.\n        call: satellite.list-errata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/systems\n      name: systems\n      description: Insights-registered systems.\n      operations:\n      - method: GET\n        name: list-systems\n        description: List registered systems.\n        call: insights.list-systems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rules\n      name: rules\n      description: Advisor rules.\n      operations:\n      - method: GET\n        name: list-rules\n        description: List advisor rules.\n        call: insights.list-rules\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: infrastructure-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted RHEL infrastructure\
  \ automation.\n    tools:\n    - name: ansible-list-job-templates\n      description: List Ansible job templates.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ansible-automation.list-job-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ansible-get-job-template\n      description: Get details of an Ansible job template.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ansible-automation.get-job-template\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ansible-launch-job-template\n      description: Launch an Ansible job template.\n      hints:\n        readOnly: false\n      call: ansible-automation.launch-job-template\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ansible-list-jobs\n      description: List automation job executions.\n      hints:\n    \
  \    readOnly: true\n      call: ansible-automation.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ansible-get-job\n      description: Get details of a job execution.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ansible-automation.get-job\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ansible-cancel-job\n      description: Cancel a running job.\n      hints:\n        readOnly: false\n        destructive: true\n      call: ansible-automation.cancel-job\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ansible-list-inventories\n      description: List Ansible inventories.\n      hints:\n        readOnly: true\n      call: ansible-automation.list-inventories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: satellite-list-hosts\n      description: List\
  \ hosts managed by Satellite.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: satellite.list-hosts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: satellite-get-host\n      description: Get a specific Satellite host.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: satellite.get-host\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: satellite-list-host-errata\n      description: List errata applicable to a host.\n      hints:\n        readOnly: true\n      call: satellite.list-host-errata\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: satellite-list-content-views\n      description: List content views.\n      hints:\n        readOnly: true\n      call: satellite.list-content-views\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: satellite-list-errata\n\
  \      description: List all available errata.\n      hints:\n        readOnly: true\n      call: satellite.list-errata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: satellite-list-repositories\n      description: List software repositories.\n      hints:\n        readOnly: true\n      call: satellite.list-repositories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insights-list-systems\n      description: List systems registered with Insights.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: insights.list-systems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insights-get-system\n      description: Get details for a system in Insights.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: insights.get-system\n      with:\n        system_id: tools.system_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ insights-list-rules\n      description: List Advisor detection rules.\n      hints:\n        readOnly: true\n      call: insights.list-rules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insights-get-system-stats\n      description: Get aggregate system health statistics.\n      hints:\n        readOnly: true\n      call: insights.get-system-stats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insights-list-topics\n      description: List recommendation topics.\n      hints:\n        readOnly: true\n      call: insights.list-topics\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
