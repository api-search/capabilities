---
categories: []
consumed_apis: []
description: The Cloud SQL Admin API provides programmatic access to manage Cloud SQL instances, databases, users, and related resources. It supports MySQL, PostgreSQL, and SQL Server database engines, enabling automated provisioning, configuration, backup management, and monitoring of managed relational database instances.
layout: capability
name: Google Cloud SQL Admin API
operations:
- description: Google Cloud SQL List instances
  method: GET
  name: listinstances
  path: /projects/{project}/instances
- description: Google Cloud SQL Create an instance
  method: POST
  name: insertinstance
  path: /projects/{project}/instances
- description: Google Cloud SQL Get an instance
  method: GET
  name: getinstance
  path: /projects/{project}/instances/{instance}
- description: Google Cloud SQL Update an instance
  method: PATCH
  name: patchinstance
  path: /projects/{project}/instances/{instance}
- description: Google Cloud SQL Delete an instance
  method: DELETE
  name: deleteinstance
  path: /projects/{project}/instances/{instance}
- description: Google Cloud SQL List databases
  method: GET
  name: listdatabases
  path: /projects/{project}/instances/{instance}/databases
- description: Google Cloud SQL Create a database
  method: POST
  name: insertdatabase
  path: /projects/{project}/instances/{instance}/databases
- description: Google Cloud SQL Get a database
  method: GET
  name: getdatabase
  path: /projects/{project}/instances/{instance}/databases/{database}
- description: Google Cloud SQL Delete a database
  method: DELETE
  name: deletedatabase
  path: /projects/{project}/instances/{instance}/databases/{database}
- description: Google Cloud SQL List users
  method: GET
  name: listusers
  path: /projects/{project}/instances/{instance}/users
- description: Google Cloud SQL Create a user
  method: POST
  name: insertuser
  path: /projects/{project}/instances/{instance}/users
- description: Google Cloud SQL List backup runs
  method: GET
  name: listbackupruns
  path: /projects/{project}/instances/{instance}/backupRuns
personas: []
provider_name: Google Cloud SQL
provider_slug: google-cloud-sql
search_terms:
- google cloud sql get an instance
- google cloud sql get a database
- google cloud sql create a user
- insertuser
- google cloud sql list users
- patchinstance
- google cloud sql list backup runs
- api
- google cloud sql create an instance
- google cloud sql list instances
- google cloud sql delete a database
- deleteinstance
- deletedatabase
- google
- getinstance
- sql
- google cloud sql delete an instance
- insertinstance
- google cloud sql list databases
- listbackupruns
- database
- cloud
- listdatabases
- mysql
- google cloud sql update an instance
- postgresql
- listusers
- relational
- getdatabase
- google cloud
- listinstances
- google cloud sql create a database
- insertdatabase
slug: google-cloud-sql-capability
source_filename: google-cloud-sql-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud SQL Admin API\n  description: The Cloud SQL Admin API provides programmatic access to manage Cloud SQL instances, databases, users, and related\n    resources. It supports MySQL, PostgreSQL, and SQL Server database engines, enabling automated provisioning, configuration,\n    backup management, and monitoring of managed relational database instances.\n  tags:\n  - Google\n  - Cloud\n  - Sql\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-sql\n    baseUri: https://sqladmin.googleapis.com/v1\n    description: Google Cloud SQL Admin API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_SQL_TOKEN}}'\n    resources:\n    - name: projects-project-instances\n      path: /projects/{project}/instances\n      operations:\n      - name: listinstances\n        method: GET\n        description: Google Cloud SQL List instances\n\
  \        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertinstance\n        method: POST\n        description: Google Cloud SQL Create an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance\n      path: /projects/{project}/instances/{instance}\n      operations:\n      - name: getinstance\n        method: GET\n       \
  \ description: Google Cloud SQL Get an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchinstance\n        method: PATCH\n        description: Google Cloud SQL Update an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinstance\n        method: DELETE\n        description: Google Cloud SQL Delete an instance\n        inputParameters:\n        - name:\
  \ project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance-databases\n      path: /projects/{project}/instances/{instance}/databases\n      operations:\n      - name: listdatabases\n        method: GET\n        description: Google Cloud SQL List databases\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertdatabase\n        method: POST\n        description: Google Cloud SQL Create a database\n\
  \        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance-databases-da\n      path: /projects/{project}/instances/{instance}/databases/{database}\n      operations:\n      - name: getdatabase\n        method: GET\n        description: Google Cloud SQL Get a database\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        - name: database\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n      - name: deletedatabase\n        method: DELETE\n        description: Google Cloud SQL Delete a database\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        - name: database\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance-users\n      path: /projects/{project}/instances/{instance}/users\n      operations:\n      - name: listusers\n        method: GET\n        description: Google Cloud SQL List users\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n      \
  \    type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertuser\n        method: POST\n        description: Google Cloud SQL Create a user\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance-backupruns\n      path: /projects/{project}/instances/{instance}/backupRuns\n      operations:\n      - name: listbackupruns\n        method: GET\n        description: Google Cloud SQL List backup runs\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name:\
  \ instance\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-sql-rest\n    description: REST adapter for Google Cloud SQL Admin API.\n    resources:\n    - path: /projects/{project}/instances\n      name: listinstances\n      operations:\n      - method: GET\n        name: listinstances\n        description: Google Cloud SQL List instances\n        call: google-cloud-sql.listinstances\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances\n      name: insertinstance\n      operations:\n      - method: POST\n        name:\
  \ insertinstance\n        description: Google Cloud SQL Create an instance\n        call: google-cloud-sql.insertinstance\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}\n      name: getinstance\n      operations:\n      - method: GET\n        name: getinstance\n        description: Google Cloud SQL Get an instance\n        call: google-cloud-sql.getinstance\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}\n      name: patchinstance\n      operations:\n      - method: PATCH\n        name: patchinstance\n        description: Google Cloud SQL Update an instance\n        call: google-cloud-sql.patchinstance\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}\n      name: deleteinstance\n      operations:\n      - method: DELETE\n        name: deleteinstance\n        description: Google Cloud SQL Delete an instance\n        call: google-cloud-sql.deleteinstance\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/databases\n      name: listdatabases\n      operations:\n      - method: GET\n        name: listdatabases\n        description: Google Cloud SQL List databases\n        call: google-cloud-sql.listdatabases\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/databases\n      name: insertdatabase\n      operations:\n      -\
  \ method: POST\n        name: insertdatabase\n        description: Google Cloud SQL Create a database\n        call: google-cloud-sql.insertdatabase\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/databases/{database}\n      name: getdatabase\n      operations:\n      - method: GET\n        name: getdatabase\n        description: Google Cloud SQL Get a database\n        call: google-cloud-sql.getdatabase\n        with:\n          project: rest.project\n          instance: rest.instance\n          database: rest.database\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/databases/{database}\n      name: deletedatabase\n      operations:\n      - method: DELETE\n        name: deletedatabase\n        description: Google Cloud SQL Delete a database\n  \
  \      call: google-cloud-sql.deletedatabase\n        with:\n          project: rest.project\n          instance: rest.instance\n          database: rest.database\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: Google Cloud SQL List users\n        call: google-cloud-sql.listusers\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/users\n      name: insertuser\n      operations:\n      - method: POST\n        name: insertuser\n        description: Google Cloud SQL Create a user\n        call: google-cloud-sql.insertuser\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/backupRuns\n      name: listbackupruns\n      operations:\n      - method: GET\n        name: listbackupruns\n        description: Google Cloud SQL List backup runs\n        call: google-cloud-sql.listbackupruns\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-sql-mcp\n    transport: http\n    description: MCP adapter for Google Cloud SQL Admin API for AI agent use.\n    tools:\n    - name: listinstances\n      description: Google Cloud SQL List instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-sql.listinstances\n      with:\n        project: tools.project\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n        filter: tools.filter\n\
  \      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: filter\n        type: string\n        description: filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertinstance\n      description: Google Cloud SQL Create an instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-sql.insertinstance\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstance\n      description: Google Cloud SQL Get an instance\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: google-cloud-sql.getinstance\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchinstance\n      description: Google Cloud SQL Update an instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-sql.patchinstance\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: deleteinstance\n      description: Google Cloud SQL Delete an instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-sql.deleteinstance\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatabases\n      description: Google Cloud SQL List databases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-sql.listdatabases\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n\
  \        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertdatabase\n      description: Google Cloud SQL Create a database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-sql.insertdatabase\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatabase\n      description: Google Cloud SQL Get a database\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-sql.getdatabase\n\
  \      with:\n        project: tools.project\n        instance: tools.instance\n        database: tools.database\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      - name: database\n        type: string\n        description: database\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedatabase\n      description: Google Cloud SQL Delete a database\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-sql.deletedatabase\n      with:\n        project: tools.project\n        instance: tools.instance\n        database: tools.database\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type:\
  \ string\n        description: instance\n        required: true\n      - name: database\n        type: string\n        description: database\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: Google Cloud SQL List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-sql.listusers\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertuser\n      description: Google Cloud SQL Create a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-sql.insertuser\n\
  \      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbackupruns\n      description: Google Cloud SQL List backup runs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-sql.listbackupruns\n      with:\n        project: tools.project\n        instance: tools.instance\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      - name: maxResults\n     \
  \   type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_SQL_TOKEN: GOOGLE_CLOUD_SQL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-sql/refs/heads/main/capabilities/google-cloud-sql-capability.yaml
tags:
- Google
- Cloud
- Sql
- API
tools:
- description: Google Cloud SQL List instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstances
- description: Google Cloud SQL Create an instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertinstance
- description: Google Cloud SQL Get an instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstance
- description: Google Cloud SQL Update an instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchinstance
- description: Google Cloud SQL Delete an instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinstance
- description: Google Cloud SQL List databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatabases
- description: Google Cloud SQL Create a database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertdatabase
- description: Google Cloud SQL Get a database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatabase
- description: Google Cloud SQL Delete a database
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatabase
- description: Google Cloud SQL List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Google Cloud SQL Create a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertuser
- description: Google Cloud SQL List backup runs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbackupruns
---
