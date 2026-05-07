---
categories: []
consumed_apis: []
description: The GDC API provides programmatic access to cancer genomic and clinical data hosted by the National Cancer Institute Genomic Data Commons. The API supports search and retrieval of projects, cases, files, and annotations, along with file download, BAM slicing, and data submission workflows.
layout: capability
name: NCI Genomic Data Commons (GDC) API
operations:
- description: Get API status
  method: GET
  name: getstatus
  path: /status
- description: Search projects
  method: GET
  name: searchprojects
  path: /projects
- description: Get project by ID
  method: GET
  name: getproject
  path: /projects/{project_id}
- description: Search cases
  method: GET
  name: searchcases
  path: /cases
- description: Get case by ID
  method: GET
  name: getcase
  path: /cases/{case_id}
- description: Search files
  method: GET
  name: searchfiles
  path: /files
- description: Get file metadata by ID
  method: GET
  name: getfile
  path: /files/{file_id}
- description: Search annotations
  method: GET
  name: searchannotations
  path: /annotations
- description: Download a file
  method: GET
  name: downloadfile
  path: /data/{file_id}
- description: Generate manifest
  method: GET
  name: getmanifest
  path: /manifest
- description: BAM slicing
  method: GET
  name: slicebam
  path: /slicing/view/{file_id}
- description: Get submission program/project resources
  method: GET
  name: getsubmissionproject
  path: /submission/{program}/{project}
personas: []
provider_name: National Cancer Institute
provider_slug: national-cancer-institute
search_terms:
- get project by id
- getproject
- download a file
- getsubmissionproject
- getstatus
- searchcases
- api
- getfile
- getmanifest
- get file metadata by id
- health
- generate manifest
- search annotations
- research
- get submission program/project resources
- cancer
- search projects
- searchprojects
- searchannotations
- getcase
- search cases
- bam slicing
- slicebam
- downloadfile
- get case by id
- searchfiles
- get api status
- federal government
- institute
- national
- search files
slug: national-cancer-institute-capability
source_filename: national-cancer-institute-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NCI Genomic Data Commons (GDC) API\n  description: The GDC API provides programmatic access to cancer genomic and clinical data hosted by the National Cancer\n    Institute Genomic Data Commons. The API supports search and retrieval of projects, cases, files, and annotations, along\n    with file download, BAM slicing, and data submission workflows.\n  tags:\n  - National\n  - Cancer\n  - Institute\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: national-cancer-institute\n    baseUri: https://api.gdc.cancer.gov\n    description: NCI Genomic Data Commons (GDC) API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Auth-Token\n      value: '{{NATIONAL_CANCER_INSTITUTE_TOKEN}}'\n    resources:\n    - name: status\n      path: /status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Get API status\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      operations:\n      - name: searchprojects\n        method: GET\n        description: Search projects\n        inputParameters:\n        - name: filters\n          in: query\n          type: string\n        - name: fields\n          in: query\n          type: string\n        - name: size\n          in: query\n          type: integer\n        - name: from\n          in: query\n          type: integer\n        - name: sort\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id\n      path: /projects/{project_id}\n      operations:\n      - name: getproject\n        method: GET\n        description: Get project by ID\n        inputParameters:\n        - name: project_id\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases\n      path: /cases\n      operations:\n      - name: searchcases\n        method: GET\n        description: Search cases\n        inputParameters:\n        - name: filters\n          in: query\n          type: string\n        - name: fields\n          in: query\n          type: string\n        - name: size\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases-case-id\n      path: /cases/{case_id}\n      operations:\n      - name: getcase\n        method: GET\n        description: Get case by ID\n        inputParameters:\n        - name: case_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files\n      path: /files\n      operations:\n      - name: searchfiles\n        method: GET\n        description: Search files\n        inputParameters:\n        - name: filters\n          in: query\n          type: string\n        - name: fields\n          in: query\n          type: string\n        - name: size\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-file-id\n      path: /files/{file_id}\n      operations:\n      - name: getfile\n        method: GET\n        description: Get file metadata by ID\n        inputParameters:\n        - name: file_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n    - name: annotations\n      path: /annotations\n      operations:\n      - name: searchannotations\n        method: GET\n        description: Search annotations\n        inputParameters:\n        - name: filters\n          in: query\n          type: string\n        - name: fields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-file-id\n      path: /data/{file_id}\n      operations:\n      - name: downloadfile\n        method: GET\n        description: Download a file\n        inputParameters:\n        - name: file_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: manifest\n      path: /manifest\n      operations:\n      - name: getmanifest\n        method: GET\n\
  \        description: Generate manifest\n        inputParameters:\n        - name: filters\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: slicing-view-file-id\n      path: /slicing/view/{file_id}\n      operations:\n      - name: slicebam\n        method: GET\n        description: BAM slicing\n        inputParameters:\n        - name: file_id\n          in: path\n          type: string\n          required: true\n        - name: region\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: submission-program-project\n      path: /submission/{program}/{project}\n      operations:\n      - name: getsubmissionproject\n        method: GET\n        description: Get submission program/project resources\n        inputParameters:\n\
  \        - name: program\n          in: path\n          type: string\n          required: true\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: national-cancer-institute-rest\n    description: REST adapter for NCI Genomic Data Commons (GDC) API.\n    resources:\n    - path: /status\n      name: getstatus\n      operations:\n      - method: GET\n        name: getstatus\n        description: Get API status\n        call: national-cancer-institute.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects\n      name: searchprojects\n      operations:\n      - method: GET\n        name: searchprojects\n        description: Search projects\n        call: national-cancer-institute.searchprojects\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{project_id}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Get project by ID\n        call: national-cancer-institute.getproject\n        with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cases\n      name: searchcases\n      operations:\n      - method: GET\n        name: searchcases\n        description: Search cases\n        call: national-cancer-institute.searchcases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cases/{case_id}\n      name: getcase\n      operations:\n      - method: GET\n        name: getcase\n        description: Get case by ID\n        call: national-cancer-institute.getcase\n        with:\n          case_id: rest.case_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /files\n      name: searchfiles\n      operations:\n      - method: GET\n        name: searchfiles\n        description: Search files\n        call: national-cancer-institute.searchfiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{file_id}\n      name: getfile\n      operations:\n      - method: GET\n        name: getfile\n        description: Get file metadata by ID\n        call: national-cancer-institute.getfile\n        with:\n          file_id: rest.file_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /annotations\n      name: searchannotations\n      operations:\n      - method: GET\n        name: searchannotations\n        description: Search annotations\n        call: national-cancer-institute.searchannotations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /data/{file_id}\n      name: downloadfile\n      operations:\n      - method: GET\n     \
  \   name: downloadfile\n        description: Download a file\n        call: national-cancer-institute.downloadfile\n        with:\n          file_id: rest.file_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /manifest\n      name: getmanifest\n      operations:\n      - method: GET\n        name: getmanifest\n        description: Generate manifest\n        call: national-cancer-institute.getmanifest\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /slicing/view/{file_id}\n      name: slicebam\n      operations:\n      - method: GET\n        name: slicebam\n        description: BAM slicing\n        call: national-cancer-institute.slicebam\n        with:\n          file_id: rest.file_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /submission/{program}/{project}\n      name: getsubmissionproject\n      operations:\n      - method: GET\n        name: getsubmissionproject\n\
  \        description: Get submission program/project resources\n        call: national-cancer-institute.getsubmissionproject\n        with:\n          program: rest.program\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: national-cancer-institute-mcp\n    transport: http\n    description: MCP adapter for NCI Genomic Data Commons (GDC) API for AI agent use.\n    tools:\n    - name: getstatus\n      description: Get API status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-cancer-institute.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchprojects\n      description: Search projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-cancer-institute.searchprojects\n      with:\n        filters: tools.filters\n\
  \        fields: tools.fields\n        size: tools.size\n        from: tools.from\n        sort: tools.sort\n      inputParameters:\n      - name: filters\n        type: string\n        description: filters\n      - name: fields\n        type: string\n        description: fields\n      - name: size\n        type: integer\n        description: size\n      - name: from\n        type: integer\n        description: from\n      - name: sort\n        type: string\n        description: sort\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Get project by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-cancer-institute.getproject\n      with:\n        project_id: tools.project_id\n      inputParameters:\n      - name: project_id\n        type: string\n        description: project_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: searchcases\n      description: Search cases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-cancer-institute.searchcases\n      with:\n        filters: tools.filters\n        fields: tools.fields\n        size: tools.size\n      inputParameters:\n      - name: filters\n        type: string\n        description: filters\n      - name: fields\n        type: string\n        description: fields\n      - name: size\n        type: integer\n        description: size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcase\n      description: Get case by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-cancer-institute.getcase\n      with:\n        case_id: tools.case_id\n      inputParameters:\n      - name: case_id\n        type: string\n        description: case_id\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: searchfiles\n      description: Search files\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-cancer-institute.searchfiles\n      with:\n        filters: tools.filters\n        fields: tools.fields\n        size: tools.size\n      inputParameters:\n      - name: filters\n        type: string\n        description: filters\n      - name: fields\n        type: string\n        description: fields\n      - name: size\n        type: integer\n        description: size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfile\n      description: Get file metadata by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-cancer-institute.getfile\n      with:\n        file_id: tools.file_id\n      inputParameters:\n      - name: file_id\n        type: string\n        description: file_id\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchannotations\n      description: Search annotations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-cancer-institute.searchannotations\n      with:\n        filters: tools.filters\n        fields: tools.fields\n      inputParameters:\n      - name: filters\n        type: string\n        description: filters\n      - name: fields\n        type: string\n        description: fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: downloadfile\n      description: Download a file\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-cancer-institute.downloadfile\n      with:\n        file_id: tools.file_id\n      inputParameters:\n      - name: file_id\n        type: string\n        description: file_id\n        required: true\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmanifest\n      description: Generate manifest\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-cancer-institute.getmanifest\n      with:\n        filters: tools.filters\n      inputParameters:\n      - name: filters\n        type: string\n        description: filters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: slicebam\n      description: BAM slicing\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-cancer-institute.slicebam\n      with:\n        file_id: tools.file_id\n        region: tools.region\n      inputParameters:\n      - name: file_id\n        type: string\n        description: file_id\n        required: true\n      - name: region\n        type: string\n        description: region\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getsubmissionproject\n      description: Get submission program/project resources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-cancer-institute.getsubmissionproject\n      with:\n        program: tools.program\n        project: tools.project\n      inputParameters:\n      - name: program\n        type: string\n        description: program\n        required: true\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NATIONAL_CANCER_INSTITUTE_TOKEN: NATIONAL_CANCER_INSTITUTE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/national-cancer-institute/refs/heads/main/capabilities/national-cancer-institute-capability.yaml
tags:
- National
- Cancer
- Institute
- API
tools:
- description: Get API status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
- description: Search projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchprojects
- description: Get project by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Search cases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcases
- description: Get case by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcase
- description: Search files
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchfiles
- description: Get file metadata by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfile
- description: Search annotations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchannotations
- description: Download a file
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadfile
- description: Generate manifest
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmanifest
- description: BAM slicing
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: slicebam
- description: Get submission program/project resources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubmissionproject
---
