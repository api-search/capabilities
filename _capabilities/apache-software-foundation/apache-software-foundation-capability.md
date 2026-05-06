---
categories: []
consumed_apis: []
description: The Apache Software Foundation Projects API provides read-only access to JSON data about ASF projects, committees, releases, and podlings. The data is served as static JSON files from projects.apache.org and includes comprehensive information about the foundation's structure, project metadata, committee membership, release histories, and incubating podlings.
layout: capability
name: Apache Software Foundation Projects API
operations:
- description: Apache Software Foundation Get Foundation Groups
  method: GET
  name: getgroups
  path: /foundation/groups.json
- description: Apache Software Foundation Get All Committees
  method: GET
  name: getcommittees
  path: /foundation/committees.json
- description: Apache Software Foundation Get All Projects
  method: GET
  name: getprojects
  path: /foundation/projects.json
- description: Apache Software Foundation Get All Releases
  method: GET
  name: getreleases
  path: /foundation/releases.json
- description: Apache Software Foundation Get All Podlings
  method: GET
  name: getpodlings
  path: /foundation/podlings.json
- description: Apache Software Foundation Get People
  method: GET
  name: getpeople
  path: /foundation/people.json
- description: Apache Software Foundation Get People Names
  method: GET
  name: getpeoplenames
  path: /foundation/people_name.json
personas: []
provider_name: Apache Software Foundation
provider_slug: apache-software-foundation
search_terms:
- software
- apache software foundation get all podlings
- projects
- apache software foundation get people
- asf
- apache software foundation get all committees
- getreleases
- getpodlings
- apache
- getpeoplenames
- open source
- apache software foundation get foundation groups
- apache software foundation get all projects
- getgroups
- foundation
- api
- getpeople
- getprojects
- apache software foundation get all releases
- getcommittees
- governance
- apache software foundation get people names
slug: apache-software-foundation-capability
source_filename: apache-software-foundation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Software Foundation Projects API\n  description: The Apache Software Foundation Projects API provides read-only access to JSON data about ASF projects, committees,\n    releases, and podlings. The data is served as static JSON files from projects.apache.org and includes comprehensive information\n    about the foundation's structure, project metadata, committee membership, release histories, and incubating podlings.\n  tags:\n  - Apache\n  - Software\n  - Foundation\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: apache-software-foundation\n    baseUri: https://projects.apache.org/json\n    description: Apache Software Foundation Projects API HTTP API.\n    resources:\n    - name: foundation-groups-json\n      path: /foundation/groups.json\n      operations:\n      - name: getgroups\n        method: GET\n        description: Apache Software Foundation Get Foundation\
  \ Groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: foundation-committees-json\n      path: /foundation/committees.json\n      operations:\n      - name: getcommittees\n        method: GET\n        description: Apache Software Foundation Get All Committees\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: foundation-projects-json\n      path: /foundation/projects.json\n      operations:\n      - name: getprojects\n        method: GET\n        description: Apache Software Foundation Get All Projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: foundation-releases-json\n      path: /foundation/releases.json\n      operations:\n      - name: getreleases\n        method: GET\n        description: Apache Software\
  \ Foundation Get All Releases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: foundation-podlings-json\n      path: /foundation/podlings.json\n      operations:\n      - name: getpodlings\n        method: GET\n        description: Apache Software Foundation Get All Podlings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: foundation-people-json\n      path: /foundation/people.json\n      operations:\n      - name: getpeople\n        method: GET\n        description: Apache Software Foundation Get People\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: foundation-people-name-json\n      path: /foundation/people_name.json\n      operations:\n      - name: getpeoplenames\n        method: GET\n        description: Apache\
  \ Software Foundation Get People Names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: apache-software-foundation-rest\n    description: REST adapter for Apache Software Foundation Projects API.\n    resources:\n    - path: /foundation/groups.json\n      name: getgroups\n      operations:\n      - method: GET\n        name: getgroups\n        description: Apache Software Foundation Get Foundation Groups\n        call: apache-software-foundation.getgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /foundation/committees.json\n      name: getcommittees\n      operations:\n      - method: GET\n        name: getcommittees\n        description: Apache Software Foundation Get All Committees\n        call: apache-software-foundation.getcommittees\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /foundation/projects.json\n      name: getprojects\n      operations:\n      - method: GET\n        name: getprojects\n        description: Apache Software Foundation Get All Projects\n        call: apache-software-foundation.getprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /foundation/releases.json\n      name: getreleases\n      operations:\n      - method: GET\n        name: getreleases\n        description: Apache Software Foundation Get All Releases\n        call: apache-software-foundation.getreleases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /foundation/podlings.json\n      name: getpodlings\n      operations:\n      - method: GET\n        name: getpodlings\n        description: Apache Software Foundation Get All Podlings\n        call: apache-software-foundation.getpodlings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /foundation/people.json\n\
  \      name: getpeople\n      operations:\n      - method: GET\n        name: getpeople\n        description: Apache Software Foundation Get People\n        call: apache-software-foundation.getpeople\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /foundation/people_name.json\n      name: getpeoplenames\n      operations:\n      - method: GET\n        name: getpeoplenames\n        description: Apache Software Foundation Get People Names\n        call: apache-software-foundation.getpeoplenames\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apache-software-foundation-mcp\n    transport: http\n    description: MCP adapter for Apache Software Foundation Projects API for AI agent use.\n    tools:\n    - name: getgroups\n      description: Apache Software Foundation Get Foundation Groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: apache-software-foundation.getgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcommittees\n      description: Apache Software Foundation Get All Committees\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-software-foundation.getcommittees\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprojects\n      description: Apache Software Foundation Get All Projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-software-foundation.getprojects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreleases\n      description: Apache Software Foundation Get All Releases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-software-foundation.getreleases\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getpodlings\n      description: Apache Software Foundation Get All Podlings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-software-foundation.getpodlings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpeople\n      description: Apache Software Foundation Get People\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-software-foundation.getpeople\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpeoplenames\n      description: Apache Software Foundation Get People Names\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-software-foundation.getpeoplenames\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-software-foundation/refs/heads/main/capabilities/apache-software-foundation-capability.yaml
tags:
- Apache
- Software
- Foundation
- API
tools:
- description: Apache Software Foundation Get Foundation Groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroups
- description: Apache Software Foundation Get All Committees
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcommittees
- description: Apache Software Foundation Get All Projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojects
- description: Apache Software Foundation Get All Releases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreleases
- description: Apache Software Foundation Get All Podlings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpodlings
- description: Apache Software Foundation Get People
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpeople
- description: Apache Software Foundation Get People Names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpeoplenames
---
