---
categories: []
consumed_apis: []
description: The Cloud Bigtable Admin API provides programmatic access to manage Cloud Bigtable instances, clusters, tables, and related resources. It allows administrators to create and configure Bigtable infrastructure for high-throughput, low-latency NoSQL workloads.
layout: capability
name: Google Cloud Bigtable Admin API
operations:
- description: Google Cloud Bigtable List instances
  method: GET
  name: listinstances
  path: /projects/{project}/instances
- description: Google Cloud Bigtable Create an instance
  method: POST
  name: createinstance
  path: /projects/{project}/instances
- description: Google Cloud Bigtable Get an instance
  method: GET
  name: getinstance
  path: /projects/{project}/instances/{instance}
- description: Google Cloud Bigtable Update an instance
  method: PUT
  name: updateinstance
  path: /projects/{project}/instances/{instance}
- description: Google Cloud Bigtable Delete an instance
  method: DELETE
  name: deleteinstance
  path: /projects/{project}/instances/{instance}
- description: Google Cloud Bigtable List tables
  method: GET
  name: listtables
  path: /projects/{project}/instances/{instance}/tables
- description: Google Cloud Bigtable Create a table
  method: POST
  name: createtable
  path: /projects/{project}/instances/{instance}/tables
- description: Google Cloud Bigtable Get a table
  method: GET
  name: gettable
  path: /projects/{project}/instances/{instance}/tables/{table}
- description: Google Cloud Bigtable Delete a table
  method: DELETE
  name: deletetable
  path: /projects/{project}/instances/{instance}/tables/{table}
- description: Google Cloud Bigtable List clusters
  method: GET
  name: listclusters
  path: /projects/{project}/instances/{instance}/clusters
personas: []
provider_name: Google Cloud Bigtable
provider_slug: google-cloud-bigtable
search_terms:
- listclusters
- google cloud bigtable list tables
- google cloud bigtable get a table
- deleteinstance
- wide column
- createtable
- google cloud bigtable delete an instance
- google cloud bigtable create a table
- cloud
- google
- google cloud bigtable list instances
- createinstance
- google cloud bigtable update an instance
- google cloud
- updateinstance
- nosql
- getinstance
- gettable
- bigtable
- database
- google cloud bigtable delete a table
- api
- google cloud bigtable list clusters
- deletetable
- listinstances
- listtables
- google cloud bigtable create an instance
- google cloud bigtable get an instance
slug: google-cloud-bigtable-capability
source_filename: google-cloud-bigtable-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Bigtable Admin API\n  description: The Cloud Bigtable Admin API provides programmatic access to manage Cloud Bigtable instances, clusters, tables,\n    and related resources. It allows administrators to create and configure Bigtable infrastructure for high-throughput, low-latency\n    NoSQL workloads.\n  tags:\n  - Google\n  - Cloud\n  - Bigtable\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-bigtable\n    baseUri: https://bigtableadmin.googleapis.com/v2\n    description: Google Cloud Bigtable Admin API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_BIGTABLE_TOKEN}}'\n    resources:\n    - name: projects-project-instances\n      path: /projects/{project}/instances\n      operations:\n      - name: listinstances\n        method: GET\n        description: Google Cloud Bigtable List instances\n        inputParameters:\n\
  \        - name: project\n          in: path\n          type: string\n          required: true\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createinstance\n        method: POST\n        description: Google Cloud Bigtable Create an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance\n      path: /projects/{project}/instances/{instance}\n      operations:\n      - name: getinstance\n        method: GET\n        description: Google Cloud Bigtable Get an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required:\
  \ true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateinstance\n        method: PUT\n        description: Google Cloud Bigtable Update an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinstance\n        method: DELETE\n        description: Google Cloud Bigtable Delete an instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n  \
  \        required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance-tables\n      path: /projects/{project}/instances/{instance}/tables\n      operations:\n      - name: listtables\n        method: GET\n        description: Google Cloud Bigtable List tables\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtable\n        method: POST\n        description: Google Cloud Bigtable Create a table\n        inputParameters:\n        - name: project\n          in: path\n          type:\
  \ string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance-tables-table\n      path: /projects/{project}/instances/{instance}/tables/{table}\n      operations:\n      - name: gettable\n        method: GET\n        description: Google Cloud Bigtable Get a table\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        - name: table\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetable\n        method: DELETE\n \
  \       description: Google Cloud Bigtable Delete a table\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        - name: table\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-instances-instance-clusters\n      path: /projects/{project}/instances/{instance}/clusters\n      operations:\n      - name: listclusters\n        method: GET\n        description: Google Cloud Bigtable List clusters\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-bigtable-rest\n    description: REST adapter for Google Cloud Bigtable Admin API.\n    resources:\n    - path: /projects/{project}/instances\n      name: listinstances\n      operations:\n      - method: GET\n        name: listinstances\n        description: Google Cloud Bigtable List instances\n        call: google-cloud-bigtable.listinstances\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances\n      name: createinstance\n      operations:\n      - method: POST\n        name: createinstance\n        description: Google Cloud Bigtable Create an instance\n        call: google-cloud-bigtable.createinstance\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /projects/{project}/instances/{instance}\n      name: getinstance\n      operations:\n      - method: GET\n        name: getinstance\n        description: Google Cloud Bigtable Get an instance\n        call: google-cloud-bigtable.getinstance\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}\n      name: updateinstance\n      operations:\n      - method: PUT\n        name: updateinstance\n        description: Google Cloud Bigtable Update an instance\n        call: google-cloud-bigtable.updateinstance\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}\n      name: deleteinstance\n      operations:\n      - method: DELETE\n        name: deleteinstance\n        description:\
  \ Google Cloud Bigtable Delete an instance\n        call: google-cloud-bigtable.deleteinstance\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/tables\n      name: listtables\n      operations:\n      - method: GET\n        name: listtables\n        description: Google Cloud Bigtable List tables\n        call: google-cloud-bigtable.listtables\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/tables\n      name: createtable\n      operations:\n      - method: POST\n        name: createtable\n        description: Google Cloud Bigtable Create a table\n        call: google-cloud-bigtable.createtable\n        with:\n          project: rest.project\n          instance: rest.instance\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/tables/{table}\n      name: gettable\n      operations:\n      - method: GET\n        name: gettable\n        description: Google Cloud Bigtable Get a table\n        call: google-cloud-bigtable.gettable\n        with:\n          project: rest.project\n          instance: rest.instance\n          table: rest.table\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/tables/{table}\n      name: deletetable\n      operations:\n      - method: DELETE\n        name: deletetable\n        description: Google Cloud Bigtable Delete a table\n        call: google-cloud-bigtable.deletetable\n        with:\n          project: rest.project\n          instance: rest.instance\n          table: rest.table\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/instances/{instance}/clusters\n\
  \      name: listclusters\n      operations:\n      - method: GET\n        name: listclusters\n        description: Google Cloud Bigtable List clusters\n        call: google-cloud-bigtable.listclusters\n        with:\n          project: rest.project\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-bigtable-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Bigtable Admin API for AI agent use.\n    tools:\n    - name: listinstances\n      description: Google Cloud Bigtable List instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-bigtable.listinstances\n      with:\n        project: tools.project\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: pageToken\n\
  \        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinstance\n      description: Google Cloud Bigtable Create an instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-bigtable.createinstance\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstance\n      description: Google Cloud Bigtable Get an instance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-bigtable.getinstance\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n       \
  \ required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateinstance\n      description: Google Cloud Bigtable Update an instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-cloud-bigtable.updateinstance\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteinstance\n      description: Google Cloud Bigtable Delete an instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-bigtable.deleteinstance\n\
  \      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtables\n      description: Google Cloud Bigtable List tables\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-bigtable.listtables\n      with:\n        project: tools.project\n        instance: tools.instance\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      - name: pageToken\n        type: string\n        description: pageToken\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtable\n      description: Google Cloud Bigtable Create a table\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-bigtable.createtable\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettable\n      description: Google Cloud Bigtable Get a table\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-bigtable.gettable\n      with:\n        project: tools.project\n        instance: tools.instance\n        table: tools.table\n      inputParameters:\n\
  \      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      - name: table\n        type: string\n        description: table\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetable\n      description: Google Cloud Bigtable Delete a table\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-bigtable.deletetable\n      with:\n        project: tools.project\n        instance: tools.instance\n        table: tools.table\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      - name: table\n        type: string\n        description: table\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclusters\n      description: Google Cloud Bigtable List clusters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-bigtable.listclusters\n      with:\n        project: tools.project\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_BIGTABLE_TOKEN: GOOGLE_CLOUD_BIGTABLE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-bigtable/refs/heads/main/capabilities/google-cloud-bigtable-capability.yaml
tags:
- Google
- Cloud
- Bigtable
- API
tools:
- description: Google Cloud Bigtable List instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstances
- description: Google Cloud Bigtable Create an instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinstance
- description: Google Cloud Bigtable Get an instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstance
- description: Google Cloud Bigtable Update an instance
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateinstance
- description: Google Cloud Bigtable Delete an instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinstance
- description: Google Cloud Bigtable List tables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtables
- description: Google Cloud Bigtable Create a table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtable
- description: Google Cloud Bigtable Get a table
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettable
- description: Google Cloud Bigtable Delete a table
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetable
- description: Google Cloud Bigtable List clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusters
---
