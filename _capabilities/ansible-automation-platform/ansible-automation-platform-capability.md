---
categories: []
consumed_apis: []
description: RESTful API for the Ansible Automation Controller providing programmatic access to job templates, workflows, inventories, credentials, projects, and job execution.
layout: capability
name: Ansible Automation Controller API
operations:
- description: Ansible List Job Templates
  method: GET
  name: listjobtemplates
  path: /job_templates/
- description: Ansible Launch Job Template
  method: POST
  name: launchjobtemplate
  path: /job_templates/{id}/launch/
- description: Ansible List Jobs
  method: GET
  name: listjobs
  path: /jobs/
- description: Ansible List Inventories
  method: GET
  name: listinventories
  path: /inventories/
- description: Ansible List Projects
  method: GET
  name: listprojects
  path: /projects/
personas: []
provider_name: Ansible Automation Platform
provider_slug: ansible-automation-platform
search_terms:
- ansible list projects
- configuration management
- ansible list inventories
- ansible list job templates
- devops
- listjobs
- listinventories
- automation
- listprojects
- ansible
- launchjobtemplate
- orchestration
- listjobtemplates
- api
- ansible list jobs
- platform
- infrastructure as code
- ansible launch job template
slug: ansible-automation-platform-capability
source_filename: ansible-automation-platform-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ansible Automation Controller API\n  description: RESTful API for the Ansible Automation Controller providing programmatic access to job templates, workflows,\n    inventories, credentials, projects, and job execution.\n  tags:\n  - Ansible\n  - Automation\n  - Platform\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ansible-automation-platform\n    baseUri: https://controller-host/api/v2\n    description: Ansible Automation Controller API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ANSIBLE_AUTOMATION_PLATFORM_TOKEN}}'\n    resources:\n    - name: job-templates\n      path: /job_templates/\n      operations:\n      - name: listjobtemplates\n        method: GET\n        description: Ansible List Job Templates\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n        - name: page_size\n          in: query\n\
  \          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-templates-id-launch\n      path: /job_templates/{id}/launch/\n      operations:\n      - name: launchjobtemplate\n        method: POST\n        description: Ansible Launch Job Template\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /jobs/\n      operations:\n      - name: listjobs\n        method: GET\n        description: Ansible List Jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventories\n      path: /inventories/\n      operations:\n      - name: listinventories\n        method: GET\n        description:\
  \ Ansible List Inventories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects/\n      operations:\n      - name: listprojects\n        method: GET\n        description: Ansible List Projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ansible-automation-platform-rest\n    description: REST adapter for Ansible Automation Controller API.\n    resources:\n    - path: /job_templates/\n      name: listjobtemplates\n      operations:\n      - method: GET\n        name: listjobtemplates\n        description: Ansible List Job Templates\n        call: ansible-automation-platform.listjobtemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /job_templates/{id}/launch/\n      name: launchjobtemplate\n\
  \      operations:\n      - method: POST\n        name: launchjobtemplate\n        description: Ansible Launch Job Template\n        call: ansible-automation-platform.launchjobtemplate\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /jobs/\n      name: listjobs\n      operations:\n      - method: GET\n        name: listjobs\n        description: Ansible List Jobs\n        call: ansible-automation-platform.listjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inventories/\n      name: listinventories\n      operations:\n      - method: GET\n        name: listinventories\n        description: Ansible List Inventories\n        call: ansible-automation-platform.listinventories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n    \
  \    description: Ansible List Projects\n        call: ansible-automation-platform.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ansible-automation-platform-mcp\n    transport: http\n    description: MCP adapter for Ansible Automation Controller API for AI agent use.\n    tools:\n    - name: listjobtemplates\n      description: Ansible List Job Templates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ansible-automation-platform.listjobtemplates\n      with:\n        page: tools.page\n        page_size: tools.page_size\n      inputParameters:\n      - name: page\n        type: integer\n        description: page\n      - name: page_size\n        type: integer\n        description: page_size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: launchjobtemplate\n      description: Ansible Launch Job Template\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ansible-automation-platform.launchjobtemplate\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjobs\n      description: Ansible List Jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ansible-automation-platform.listjobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinventories\n      description: Ansible List Inventories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ansible-automation-platform.listinventories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojects\n      description: Ansible List Projects\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ansible-automation-platform.listprojects\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ANSIBLE_AUTOMATION_PLATFORM_TOKEN: ANSIBLE_AUTOMATION_PLATFORM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ansible-automation-platform/refs/heads/main/capabilities/ansible-automation-platform-capability.yaml
tags:
- Ansible
- Automation
- Platform
- API
tools:
- description: Ansible List Job Templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobtemplates
- description: Ansible Launch Job Template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: launchjobtemplate
- description: Ansible List Jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: Ansible List Inventories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinventories
- description: Ansible List Projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
---
