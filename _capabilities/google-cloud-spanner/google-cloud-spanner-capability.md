---
categories: []
consumed_apis: []
description: The Cloud Spanner API provides programmatic access to Google Cloud Spanner, a globally distributed, strongly consistent relational database service. It enables management of instances, databases, sessions, and execution of SQL queries and DML statements with full ACID transaction support.
layout: capability
name: Google Cloud Spanner API
operations:
- description: Google Cloud Spanner List instances
  method: GET
  name: listinstances
  path: /projects/{project}/instances
- description: Google Cloud Spanner Create an instance
  method: POST
  name: createinstance
  path: /projects/{project}/instances
- description: Google Cloud Spanner Get an instance
  method: GET
  name: getinstance
  path: /projects/{project}/instances/{instance}
- description: Google Cloud Spanner Update an instance
  method: PATCH
  name: updateinstance
  path: /projects/{project}/instances/{instance}
- description: Google Cloud Spanner Delete an instance
  method: DELETE
  name: deleteinstance
  path: /projects/{project}/instances/{instance}
- description: Google Cloud Spanner List databases
  method: GET
  name: listdatabases
  path: /projects/{project}/instances/{instance}/databases
- description: Google Cloud Spanner Create a database
  method: POST
  name: createdatabase
  path: /projects/{project}/instances/{instance}/databases
- description: Google Cloud Spanner Get a database
  method: GET
  name: getdatabase
  path: /projects/{project}/instances/{instance}/databases/{database}
- description: Google Cloud Spanner Drop a database
  method: DELETE
  name: dropdatabase
  path: /projects/{project}/instances/{instance}/databases/{database}
- description: Google Cloud Spanner Create a session
  method: POST
  name: createsession
  path: /projects/{project}/instances/{instance}/databases/{database}/sessions
personas: []
provider_name: Google Cloud Spanner
provider_slug: google-cloud-spanner
search_terms:
- google cloud spanner create a database
- google cloud spanner drop a database
- deleteinstance
- google cloud spanner list instances
- distributed
- dropdatabase
- cloud
- google cloud spanner delete an instance
- google
- google cloud spanner get a database
- createinstance
- sql
- updateinstance
- getdatabase
- getinstance
- google cloud spanner create a session
- relational
- database
- createdatabase
- api
- google cloud spanner create an instance
- listinstances
- spanner
- createsession
- google cloud spanner update an instance
- google cloud spanner get an instance
- listdatabases
- google cloud spanner list databases
- google cloud
slug: google-cloud-spanner-capability
source_filename: google-cloud-spanner-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Spanner API\n  description: The Cloud Spanner API provides programmatic access to Google Cloud Spanner, a globally distributed, strongly\n    consistent relational database service. It enables management of instances, databases, sessions, and execution of SQL\n    queries and DML statements with full ACID transaction support.\n  tags:\n  - Google\n  - Cloud\n  - Spanner\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-spanner\n    baseUri: https://spanner.googleapis.com/v1\n    description: Google Cloud Spanner API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_SPANNER_TOKEN}}'\n    resources:\n    - name: projects-project-instances\n      path: /projects/{project}/instances\n      operations:\n      - name: listinstances\n        method: GET\n        description: Google Cloud Spanner List instances\n       \
  \ inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createinstance\n        method: POST\n        description: Google Cloud Spanner Create an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance\n      path: /projects/{project}/instances/{instance}\n      operations:\n      - name: getinstance\n        method: GET\n        description:\
  \ Google Cloud Spanner Get an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateinstance\n        method: PATCH\n        description: Google Cloud Spanner Update an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinstance\n        method: DELETE\n        description: Google Cloud Spanner Delete an instance\n        inputParameters:\n        - name:\
  \ project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance-databases\n      path: /projects/{project}/instances/{instance}/databases\n      operations:\n      - name: listdatabases\n        method: GET\n        description: Google Cloud Spanner List databases\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n      - name: createdatabase\n        method: POST\n        description: Google Cloud Spanner Create a database\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance-databases-da\n      path: /projects/{project}/instances/{instance}/databases/{database}\n      operations:\n      - name: getdatabase\n        method: GET\n        description: Google Cloud Spanner Get a database\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        - name: database\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: dropdatabase\n        method: DELETE\n        description: Google Cloud Spanner Drop a database\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        - name: database\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance-databases-da\n      path: /projects/{project}/instances/{instance}/databases/{database}/sessions\n      operations:\n      - name: createsession\n        method: POST\n        description: Google Cloud Spanner\
  \ Create a session\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        - name: database\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-spanner-rest\n    description: REST adapter for Google Cloud Spanner API.\n    resources:\n    - path: /projects/{project}/instances\n      name: listinstances\n      operations:\n      - method: GET\n        name: listinstances\n        description: Google Cloud Spanner List instances\n        call: google-cloud-spanner.listinstances\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /projects/{project}/instances\n      name: createinstance\n      operations:\n      - method: POST\n        name: createinstance\n        description: Google Cloud Spanner Create an instance\n        call: google-cloud-spanner.createinstance\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}\n      name: getinstance\n      operations:\n      - method: GET\n        name: getinstance\n        description: Google Cloud Spanner Get an instance\n        call: google-cloud-spanner.getinstance\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}\n      name: updateinstance\n      operations:\n      - method: PATCH\n        name: updateinstance\n        description: Google Cloud Spanner Update an instance\n      \
  \  call: google-cloud-spanner.updateinstance\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}\n      name: deleteinstance\n      operations:\n      - method: DELETE\n        name: deleteinstance\n        description: Google Cloud Spanner Delete an instance\n        call: google-cloud-spanner.deleteinstance\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/databases\n      name: listdatabases\n      operations:\n      - method: GET\n        name: listdatabases\n        description: Google Cloud Spanner List databases\n        call: google-cloud-spanner.listdatabases\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/databases\n      name: createdatabase\n      operations:\n      - method: POST\n        name: createdatabase\n        description: Google Cloud Spanner Create a database\n        call: google-cloud-spanner.createdatabase\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/databases/{database}\n      name: getdatabase\n      operations:\n      - method: GET\n        name: getdatabase\n        description: Google Cloud Spanner Get a database\n        call: google-cloud-spanner.getdatabase\n        with:\n          project: rest.project\n          instance: rest.instance\n          database: rest.database\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/databases/{database}\n\
  \      name: dropdatabase\n      operations:\n      - method: DELETE\n        name: dropdatabase\n        description: Google Cloud Spanner Drop a database\n        call: google-cloud-spanner.dropdatabase\n        with:\n          project: rest.project\n          instance: rest.instance\n          database: rest.database\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/databases/{database}/sessions\n      name: createsession\n      operations:\n      - method: POST\n        name: createsession\n        description: Google Cloud Spanner Create a session\n        call: google-cloud-spanner.createsession\n        with:\n          project: rest.project\n          instance: rest.instance\n          database: rest.database\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-spanner-mcp\n    transport: http\n    description: MCP adapter\
  \ for Google Cloud Spanner API for AI agent use.\n    tools:\n    - name: listinstances\n      description: Google Cloud Spanner List instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-spanner.listinstances\n      with:\n        project: tools.project\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        filter: tools.filter\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: filter\n        type: string\n        description: filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinstance\n      description: Google Cloud Spanner Create an instance\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: google-cloud-spanner.createinstance\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstance\n      description: Google Cloud Spanner Get an instance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-spanner.getinstance\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateinstance\n      description: Google Cloud Spanner Update an instance\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-spanner.updateinstance\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteinstance\n      description: Google Cloud Spanner Delete an instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-spanner.deleteinstance\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatabases\n      description: Google Cloud Spanner List databases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-spanner.listdatabases\n      with:\n        project: tools.project\n        instance: tools.instance\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdatabase\n      description: Google Cloud Spanner Create a database\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-spanner.createdatabase\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatabase\n      description: Google Cloud Spanner Get a database\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-spanner.getdatabase\n      with:\n        project: tools.project\n        instance: tools.instance\n        database: tools.database\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n     \
  \   type: string\n        description: instance\n        required: true\n      - name: database\n        type: string\n        description: database\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dropdatabase\n      description: Google Cloud Spanner Drop a database\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-spanner.dropdatabase\n      with:\n        project: tools.project\n        instance: tools.instance\n        database: tools.database\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      - name: database\n        type: string\n        description: database\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsession\n  \
  \    description: Google Cloud Spanner Create a session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-spanner.createsession\n      with:\n        project: tools.project\n        instance: tools.instance\n        database: tools.database\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      - name: database\n        type: string\n        description: database\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_SPANNER_TOKEN: GOOGLE_CLOUD_SPANNER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-spanner/refs/heads/main/capabilities/google-cloud-spanner-capability.yaml
tags:
- Google
- Cloud
- Spanner
- API
tools:
- description: Google Cloud Spanner List instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstances
- description: Google Cloud Spanner Create an instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinstance
- description: Google Cloud Spanner Get an instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstance
- description: Google Cloud Spanner Update an instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateinstance
- description: Google Cloud Spanner Delete an instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinstance
- description: Google Cloud Spanner List databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatabases
- description: Google Cloud Spanner Create a database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatabase
- description: Google Cloud Spanner Get a database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatabase
- description: Google Cloud Spanner Drop a database
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: dropdatabase
- description: Google Cloud Spanner Create a session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsession
---
