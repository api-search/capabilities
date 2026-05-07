---
categories: []
consumed_apis: []
description: The IBM Cloud Object Storage API provides a RESTful interface compatible with S3 for storing and retrieving objects in buckets. It supports features such as multipart uploads, versioning, lifecycle policies, and server-side encryption.
layout: capability
name: International Business Machines IBM Cloud Object Storage API
operations:
- description: International Business Machines List buckets
  method: GET
  name: listbuckets
  path: /
- description: International Business Machines Create a bucket
  method: PUT
  name: createbucket
  path: /{bucket}
- description: International Business Machines Delete a bucket
  method: DELETE
  name: deletebucket
  path: /{bucket}
- description: International Business Machines List objects in a bucket
  method: GET
  name: listobjects
  path: /{bucket}
- description: International Business Machines Upload an object
  method: PUT
  name: putobject
  path: /{bucket}/{key}
- description: International Business Machines Get an object
  method: GET
  name: getobject
  path: /{bucket}/{key}
- description: International Business Machines Delete an object
  method: DELETE
  name: deleteobject
  path: /{bucket}/{key}
personas: []
provider_name: International Business Machines
provider_slug: international-business-machines
search_terms:
- ibm
- listobjects
- international business machines get an object
- api
- international business machines delete a bucket
- listbuckets
- international
- artificial intelligence
- putobject
- international business machines delete an object
- business
- deleteobject
- createbucket
- enterprise
- international business machines list objects in a bucket
- cloud
- international business machines upload an object
- machines
- international business machines list buckets
- international business machines create a bucket
- deletebucket
- getobject
slug: international-business-machines-capability
source_filename: international-business-machines-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: International Business Machines IBM Cloud Object Storage API\n  description: The IBM Cloud Object Storage API provides a RESTful interface compatible with S3 for storing and retrieving\n    objects in buckets. It supports features such as multipart uploads, versioning, lifecycle policies, and server-side encryption.\n  tags:\n  - International\n  - Business\n  - Machines\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: international-business-machines\n    baseUri: https://s3.us-south.cloud-object-storage.appdomain.cloud\n    description: International Business Machines IBM Cloud Object Storage API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{INTERNATIONAL_BUSINESS_MACHINES_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: listbuckets\n        method: GET\n        description: International Business Machines\
  \ List buckets\n        inputParameters:\n        - name: ibm-service-instance-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket\n      path: /{bucket}\n      operations:\n      - name: createbucket\n        method: PUT\n        description: International Business Machines Create a bucket\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n        - name: ibm-service-instance-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebucket\n        method: DELETE\n        description: International Business Machines Delete a bucket\n        inputParameters:\n        - name: bucket\n    \
  \      in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listobjects\n        method: GET\n        description: International Business Machines List objects in a bucket\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n        - name: prefix\n          in: query\n          type: string\n        - name: max-keys\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket-key\n      path: /{bucket}/{key}\n      operations:\n      - name: putobject\n        method: PUT\n        description: International Business Machines Upload an object\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n       \
  \   required: true\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getobject\n        method: GET\n        description: International Business Machines Get an object\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteobject\n        method: DELETE\n        description: International Business Machines Delete an object\n        inputParameters:\n        - name: bucket\n          in: path\n          type: string\n          required: true\n        - name: key\n          in: path\n          type: string\n \
  \         required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: international-business-machines-rest\n    description: REST adapter for International Business Machines IBM Cloud Object Storage API.\n    resources:\n    - path: /\n      name: listbuckets\n      operations:\n      - method: GET\n        name: listbuckets\n        description: International Business Machines List buckets\n        call: international-business-machines.listbuckets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{bucket}\n      name: createbucket\n      operations:\n      - method: PUT\n        name: createbucket\n        description: International Business Machines Create a bucket\n        call: international-business-machines.createbucket\n        with:\n          bucket: rest.bucket\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /{bucket}\n      name: deletebucket\n      operations:\n      - method: DELETE\n        name: deletebucket\n        description: International Business Machines Delete a bucket\n        call: international-business-machines.deletebucket\n        with:\n          bucket: rest.bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{bucket}\n      name: listobjects\n      operations:\n      - method: GET\n        name: listobjects\n        description: International Business Machines List objects in a bucket\n        call: international-business-machines.listobjects\n        with:\n          bucket: rest.bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{bucket}/{key}\n      name: putobject\n      operations:\n      - method: PUT\n        name: putobject\n        description: International Business Machines Upload an object\n        call: international-business-machines.putobject\n\
  \        with:\n          bucket: rest.bucket\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{bucket}/{key}\n      name: getobject\n      operations:\n      - method: GET\n        name: getobject\n        description: International Business Machines Get an object\n        call: international-business-machines.getobject\n        with:\n          bucket: rest.bucket\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{bucket}/{key}\n      name: deleteobject\n      operations:\n      - method: DELETE\n        name: deleteobject\n        description: International Business Machines Delete an object\n        call: international-business-machines.deleteobject\n        with:\n          bucket: rest.bucket\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: international-business-machines-mcp\n\
  \    transport: http\n    description: MCP adapter for International Business Machines IBM Cloud Object Storage API for AI agent use.\n    tools:\n    - name: listbuckets\n      description: International Business Machines List buckets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: international-business-machines.listbuckets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbucket\n      description: International Business Machines Create a bucket\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: international-business-machines.createbucket\n      with:\n        bucket: tools.bucket\n      inputParameters:\n      - name: bucket\n        type: string\n        description: bucket\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebucket\n      description: International Business Machines\
  \ Delete a bucket\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: international-business-machines.deletebucket\n      with:\n        bucket: tools.bucket\n      inputParameters:\n      - name: bucket\n        type: string\n        description: bucket\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listobjects\n      description: International Business Machines List objects in a bucket\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: international-business-machines.listobjects\n      with:\n        bucket: tools.bucket\n        prefix: tools.prefix\n        max-keys: tools.max-keys\n      inputParameters:\n      - name: bucket\n        type: string\n        description: bucket\n        required: true\n      - name: prefix\n        type: string\n        description: prefix\n      - name: max-keys\n        type: integer\n\
  \        description: max-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putobject\n      description: International Business Machines Upload an object\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: international-business-machines.putobject\n      with:\n        bucket: tools.bucket\n        key: tools.key\n      inputParameters:\n      - name: bucket\n        type: string\n        description: bucket\n        required: true\n      - name: key\n        type: string\n        description: key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getobject\n      description: International Business Machines Get an object\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: international-business-machines.getobject\n      with:\n        bucket: tools.bucket\n        key: tools.key\n      inputParameters:\n\
  \      - name: bucket\n        type: string\n        description: bucket\n        required: true\n      - name: key\n        type: string\n        description: key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteobject\n      description: International Business Machines Delete an object\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: international-business-machines.deleteobject\n      with:\n        bucket: tools.bucket\n        key: tools.key\n      inputParameters:\n      - name: bucket\n        type: string\n        description: bucket\n        required: true\n      - name: key\n        type: string\n        description: key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    INTERNATIONAL_BUSINESS_MACHINES_TOKEN: INTERNATIONAL_BUSINESS_MACHINES_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/international-business-machines/refs/heads/main/capabilities/international-business-machines-capability.yaml
tags:
- International
- Business
- Machines
- API
tools:
- description: International Business Machines List buckets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuckets
- description: International Business Machines Create a bucket
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createbucket
- description: International Business Machines Delete a bucket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucket
- description: International Business Machines List objects in a bucket
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listobjects
- description: International Business Machines Upload an object
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putobject
- description: International Business Machines Get an object
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getobject
- description: International Business Machines Delete an object
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteobject
---
