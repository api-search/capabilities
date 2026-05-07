---
categories: []
consumed_apis: []
description: ParseHub is a visual web scraping tool. The v2 API allows you to start runs, check run status, retrieve scraped data, and manage projects and runs.
layout: capability
name: ParseHub API
operations:
- description: List projects
  method: GET
  name: listprojects
  path: /projects
- description: Get a project
  method: GET
  name: getproject
  path: /projects/{project_token}
- description: Start a run
  method: POST
  name: startrun
  path: /projects/{project_token}/run
- description: Get data for the last ready run
  method: GET
  name: getlastreadyrundata
  path: /projects/{project_token}/last_ready_run/data
- description: Get a run
  method: GET
  name: getrun
  path: /runs/{run_token}
- description: Delete a run
  method: DELETE
  name: deleterun
  path: /runs/{run_token}
- description: Get run data
  method: GET
  name: getrundata
  path: /runs/{run_token}/data
- description: Cancel a run
  method: POST
  name: cancelrun
  path: /runs/{run_token}/cancel
personas: []
provider_name: ParseHub
provider_slug: parsehub
search_terms:
- getlastreadyrundata
- getproject
- get data for the last ready run
- deleterun
- visual scraping
- api
- getrun
- get a project
- get a run
- delete a run
- get run data
- startrun
- data extraction
- list projects
- scraping
- start a run
- cancelrun
- cancel a run
- listprojects
- getrundata
- parsehub
slug: parsehub-capability
source_filename: parsehub-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ParseHub API\n  description: ParseHub is a visual web scraping tool. The v2 API allows you to start runs, check run status, retrieve scraped\n    data, and manage projects and runs.\n  tags:\n  - Parsehub\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: parsehub\n    baseUri: https://www.parsehub.com/api/v2\n    description: ParseHub API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: api_key\n      value: '{{PARSEHUB_TOKEN}}'\n    resources:\n    - name: projects\n      path: /projects\n      operations:\n      - name: listprojects\n        method: GET\n        description: List projects\n        inputParameters:\n        - name: api_key\n          in: query\n          type: string\n          required: true\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type:\
  \ integer\n        - name: include_options\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-token\n      path: /projects/{project_token}\n      operations:\n      - name: getproject\n        method: GET\n        description: Get a project\n        inputParameters:\n        - name: project_token\n          in: path\n          type: string\n          required: true\n        - name: api_key\n          in: query\n          type: string\n          required: true\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-token-run\n      path: /projects/{project_token}/run\n      operations:\n      - name: startrun\n        method: POST\n        description: Start a run\n   \
  \     inputParameters:\n        - name: project_token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-token-last-ready-run-data\n      path: /projects/{project_token}/last_ready_run/data\n      operations:\n      - name: getlastreadyrundata\n        method: GET\n        description: Get data for the last ready run\n        inputParameters:\n        - name: project_token\n          in: path\n          type: string\n          required: true\n        - name: api_key\n          in: query\n          type: string\n          required: true\n        - name: format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runs-run-token\n      path: /runs/{run_token}\n      operations:\n      -\
  \ name: getrun\n        method: GET\n        description: Get a run\n        inputParameters:\n        - name: run_token\n          in: path\n          type: string\n          required: true\n        - name: api_key\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterun\n        method: DELETE\n        description: Delete a run\n        inputParameters:\n        - name: run_token\n          in: path\n          type: string\n          required: true\n        - name: api_key\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runs-run-token-data\n      path: /runs/{run_token}/data\n      operations:\n      - name: getrundata\n        method: GET\n        description:\
  \ Get run data\n        inputParameters:\n        - name: run_token\n          in: path\n          type: string\n          required: true\n        - name: api_key\n          in: query\n          type: string\n          required: true\n        - name: format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runs-run-token-cancel\n      path: /runs/{run_token}/cancel\n      operations:\n      - name: cancelrun\n        method: POST\n        description: Cancel a run\n        inputParameters:\n        - name: run_token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: parsehub-rest\n    description: REST adapter for ParseHub API.\n    resources:\n    -\
  \ path: /projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: List projects\n        call: parsehub.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_token}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Get a project\n        call: parsehub.getproject\n        with:\n          project_token: rest.project_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_token}/run\n      name: startrun\n      operations:\n      - method: POST\n        name: startrun\n        description: Start a run\n        call: parsehub.startrun\n        with:\n          project_token: rest.project_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_token}/last_ready_run/data\n      name: getlastreadyrundata\n\
  \      operations:\n      - method: GET\n        name: getlastreadyrundata\n        description: Get data for the last ready run\n        call: parsehub.getlastreadyrundata\n        with:\n          project_token: rest.project_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runs/{run_token}\n      name: getrun\n      operations:\n      - method: GET\n        name: getrun\n        description: Get a run\n        call: parsehub.getrun\n        with:\n          run_token: rest.run_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runs/{run_token}\n      name: deleterun\n      operations:\n      - method: DELETE\n        name: deleterun\n        description: Delete a run\n        call: parsehub.deleterun\n        with:\n          run_token: rest.run_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runs/{run_token}/data\n      name: getrundata\n      operations:\n\
  \      - method: GET\n        name: getrundata\n        description: Get run data\n        call: parsehub.getrundata\n        with:\n          run_token: rest.run_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /runs/{run_token}/cancel\n      name: cancelrun\n      operations:\n      - method: POST\n        name: cancelrun\n        description: Cancel a run\n        call: parsehub.cancelrun\n        with:\n          run_token: rest.run_token\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: parsehub-mcp\n    transport: http\n    description: MCP adapter for ParseHub API for AI agent use.\n    tools:\n    - name: listprojects\n      description: List projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: parsehub.listprojects\n      with:\n        api_key: tools.api_key\n        offset: tools.offset\n        limit:\
  \ tools.limit\n        include_options: tools.include_options\n      inputParameters:\n      - name: api_key\n        type: string\n        description: api_key\n        required: true\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      - name: include_options\n        type: integer\n        description: include_options\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Get a project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: parsehub.getproject\n      with:\n        project_token: tools.project_token\n        api_key: tools.api_key\n        offset: tools.offset\n      inputParameters:\n      - name: project_token\n        type: string\n        description: project_token\n        required: true\n      - name: api_key\n        type: string\n        description: api_key\n\
  \        required: true\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startrun\n      description: Start a run\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: parsehub.startrun\n      with:\n        project_token: tools.project_token\n      inputParameters:\n      - name: project_token\n        type: string\n        description: project_token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlastreadyrundata\n      description: Get data for the last ready run\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: parsehub.getlastreadyrundata\n      with:\n        project_token: tools.project_token\n        api_key: tools.api_key\n        format: tools.format\n      inputParameters:\n      - name: project_token\n  \
  \      type: string\n        description: project_token\n        required: true\n      - name: api_key\n        type: string\n        description: api_key\n        required: true\n      - name: format\n        type: string\n        description: format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrun\n      description: Get a run\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: parsehub.getrun\n      with:\n        run_token: tools.run_token\n        api_key: tools.api_key\n      inputParameters:\n      - name: run_token\n        type: string\n        description: run_token\n        required: true\n      - name: api_key\n        type: string\n        description: api_key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterun\n      description: Delete a run\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: parsehub.deleterun\n      with:\n        run_token: tools.run_token\n        api_key: tools.api_key\n      inputParameters:\n      - name: run_token\n        type: string\n        description: run_token\n        required: true\n      - name: api_key\n        type: string\n        description: api_key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrundata\n      description: Get run data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: parsehub.getrundata\n      with:\n        run_token: tools.run_token\n        api_key: tools.api_key\n        format: tools.format\n      inputParameters:\n      - name: run_token\n        type: string\n        description: run_token\n        required: true\n      - name: api_key\n        type: string\n        description: api_key\n        required: true\n      - name: format\n        type: string\n        description: format\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelrun\n      description: Cancel a run\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: parsehub.cancelrun\n      with:\n        run_token: tools.run_token\n      inputParameters:\n      - name: run_token\n        type: string\n        description: run_token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PARSEHUB_TOKEN: PARSEHUB_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/parsehub/refs/heads/main/capabilities/parsehub-capability.yaml
tags:
- Parsehub
- API
tools:
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Get a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Start a run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startrun
- description: Get data for the last ready run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlastreadyrundata
- description: Get a run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrun
- description: Delete a run
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterun
- description: Get run data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrundata
- description: Cancel a run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelrun
---
