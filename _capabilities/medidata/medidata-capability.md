---
categories: []
consumed_apis: []
description: Medidata Rave provides electronic data capture (EDC) APIs for clinical trial data collection and management. APIs enable access to study designs, case report forms, patient data, queries, and audit trails for clinical research organizations and pharmaceutical companies.
layout: capability
name: Medidata Rave EDC REST API
operations:
- description: List studies
  method: GET
  name: liststudies
  path: /
- description: List subjects in a study
  method: GET
  name: listsubjects
  path: /{studyOID}/Subjects
- description: Create or update a subject
  method: POST
  name: createsubject
  path: /{studyOID}/Subjects
- description: Get subject details
  method: GET
  name: getsubject
  path: /{studyOID}/Subjects/{subjectKey}
- description: Get clinical data (CRF data) for a subject
  method: GET
  name: getsubjectclinicaldata
  path: /{studyOID}/Subjects/{subjectKey}/ClinicalData
- description: Submit clinical data for a subject
  method: POST
  name: submitclinicaldata
  path: /{studyOID}/Subjects/{subjectKey}/ClinicalData
- description: List data queries
  method: GET
  name: listqueries
  path: /{studyOID}/Queries
- description: Get audit trail records
  method: GET
  name: getauditrecords
  path: /{studyOID}/AuditRecords
- description: List study sites
  method: GET
  name: listsites
  path: /{studyOID}/Sites
personas: []
provider_name: medidata
provider_slug: medidata
search_terms:
- create or update a subject
- liststudies
- api
- get subject details
- listsites
- list study sites
- getauditrecords
- list subjects in a study
- medidata
- list data queries
- submitclinicaldata
- submit clinical data for a subject
- createsubject
- getsubject
- listsubjects
- list studies
- get clinical data (crf data) for a subject
- getsubjectclinicaldata
- get audit trail records
- listqueries
slug: medidata-capability
source_filename: medidata-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Medidata Rave EDC REST API\n  description: Medidata Rave provides electronic data capture (EDC) APIs for clinical trial data collection and management.\n    APIs enable access to study designs, case report forms, patient data, queries, and audit trails for clinical research\n    organizations and pharmaceutical companies.\n  tags:\n  - Medidata\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: medidata\n    baseUri: https://medidatatrials.medidata.com/RaveWebServices/studies\n    description: Medidata Rave EDC REST API HTTP API.\n    authentication:\n      type: basic\n      username: '{{MEDIDATA_USERNAME}}'\n      password: '{{MEDIDATA_PASSWORD}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: liststudies\n        method: GET\n        description: List studies\n        inputParameters:\n        - name: include\n          in: query\n\
  \          type: string\n          description: Include additional metadata (e.g., include=subjectCount)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: studyoid-subjects\n      path: /{studyOID}/Subjects\n      operations:\n      - name: listsubjects\n        method: GET\n        description: List subjects in a study\n        inputParameters:\n        - name: studyOID\n          in: path\n          type: string\n          required: true\n          description: Study OID (e.g., Mediflex(Dev))\n        - name: Status\n          in: query\n          type: string\n        - name: SiteID\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsubject\n        method: POST\n        description: Create or update a subject\n        inputParameters:\n        - name: studyOID\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: studyoid-subjects-subjectkey\n      path: /{studyOID}/Subjects/{subjectKey}\n      operations:\n      - name: getsubject\n        method: GET\n        description: Get subject details\n        inputParameters:\n        - name: studyOID\n          in: path\n          type: string\n          required: true\n        - name: subjectKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: studyoid-subjects-subjectkey-clinicaldata\n      path: /{studyOID}/Subjects/{subjectKey}/ClinicalData\n      operations:\n      - name: getsubjectclinicaldata\n        method: GET\n        description: Get clinical data (CRF data) for a subject\n\
  \        inputParameters:\n        - name: studyOID\n          in: path\n          type: string\n          required: true\n        - name: subjectKey\n          in: path\n          type: string\n          required: true\n        - name: formOID\n          in: query\n          type: string\n          description: Filter to a specific form OID\n        - name: EventRepeatKey\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submitclinicaldata\n        method: POST\n        description: Submit clinical data for a subject\n        inputParameters:\n        - name: studyOID\n          in: path\n          type: string\n          required: true\n        - name: subjectKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: studyoid-queries\n      path: /{studyOID}/Queries\n      operations:\n      - name: listqueries\n        method: GET\n        description: List data queries\n        inputParameters:\n        - name: studyOID\n          in: path\n          type: string\n          required: true\n        - name: Status\n          in: query\n          type: string\n        - name: SiteID\n          in: query\n          type: string\n        - name: SubjectKey\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: studyoid-auditrecords\n      path: /{studyOID}/AuditRecords\n      operations:\n      - name: getauditrecords\n        method: GET\n        description: Get audit trail records\n        inputParameters:\n        - name: studyOID\n          in: path\n          type: string\n          required: true\n        - name: SubjectKey\n          in: query\n  \
  \        type: string\n        - name: SiteID\n          in: query\n          type: string\n        - name: StartDate\n          in: query\n          type: string\n        - name: EndDate\n          in: query\n          type: string\n        - name: PageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: studyoid-sites\n      path: /{studyOID}/Sites\n      operations:\n      - name: listsites\n        method: GET\n        description: List study sites\n        inputParameters:\n        - name: studyOID\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: medidata-rest\n    description: REST adapter for Medidata Rave EDC REST API.\n    resources:\n \
  \   - path: /\n      name: liststudies\n      operations:\n      - method: GET\n        name: liststudies\n        description: List studies\n        call: medidata.liststudies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{studyOID}/Subjects\n      name: listsubjects\n      operations:\n      - method: GET\n        name: listsubjects\n        description: List subjects in a study\n        call: medidata.listsubjects\n        with:\n          studyOID: rest.studyOID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{studyOID}/Subjects\n      name: createsubject\n      operations:\n      - method: POST\n        name: createsubject\n        description: Create or update a subject\n        call: medidata.createsubject\n        with:\n          studyOID: rest.studyOID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{studyOID}/Subjects/{subjectKey}\n      name: getsubject\n\
  \      operations:\n      - method: GET\n        name: getsubject\n        description: Get subject details\n        call: medidata.getsubject\n        with:\n          studyOID: rest.studyOID\n          subjectKey: rest.subjectKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{studyOID}/Subjects/{subjectKey}/ClinicalData\n      name: getsubjectclinicaldata\n      operations:\n      - method: GET\n        name: getsubjectclinicaldata\n        description: Get clinical data (CRF data) for a subject\n        call: medidata.getsubjectclinicaldata\n        with:\n          studyOID: rest.studyOID\n          subjectKey: rest.subjectKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{studyOID}/Subjects/{subjectKey}/ClinicalData\n      name: submitclinicaldata\n      operations:\n      - method: POST\n        name: submitclinicaldata\n        description: Submit clinical data for a subject\n        call: medidata.submitclinicaldata\n\
  \        with:\n          studyOID: rest.studyOID\n          subjectKey: rest.subjectKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{studyOID}/Queries\n      name: listqueries\n      operations:\n      - method: GET\n        name: listqueries\n        description: List data queries\n        call: medidata.listqueries\n        with:\n          studyOID: rest.studyOID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{studyOID}/AuditRecords\n      name: getauditrecords\n      operations:\n      - method: GET\n        name: getauditrecords\n        description: Get audit trail records\n        call: medidata.getauditrecords\n        with:\n          studyOID: rest.studyOID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{studyOID}/Sites\n      name: listsites\n      operations:\n      - method: GET\n        name: listsites\n        description: List study sites\n    \
  \    call: medidata.listsites\n        with:\n          studyOID: rest.studyOID\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: medidata-mcp\n    transport: http\n    description: MCP adapter for Medidata Rave EDC REST API for AI agent use.\n    tools:\n    - name: liststudies\n      description: List studies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: medidata.liststudies\n      with:\n        include: tools.include\n      inputParameters:\n      - name: include\n        type: string\n        description: Include additional metadata (e.g., include=subjectCount)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsubjects\n      description: List subjects in a study\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: medidata.listsubjects\n      with:\n        studyOID:\
  \ tools.studyOID\n        Status: tools.Status\n        SiteID: tools.SiteID\n      inputParameters:\n      - name: studyOID\n        type: string\n        description: Study OID (e.g., Mediflex(Dev))\n        required: true\n      - name: Status\n        type: string\n        description: Status\n      - name: SiteID\n        type: string\n        description: SiteID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsubject\n      description: Create or update a subject\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: medidata.createsubject\n      with:\n        studyOID: tools.studyOID\n      inputParameters:\n      - name: studyOID\n        type: string\n        description: studyOID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubject\n      description: Get subject details\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: medidata.getsubject\n      with:\n        studyOID: tools.studyOID\n        subjectKey: tools.subjectKey\n      inputParameters:\n      - name: studyOID\n        type: string\n        description: studyOID\n        required: true\n      - name: subjectKey\n        type: string\n        description: subjectKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubjectclinicaldata\n      description: Get clinical data (CRF data) for a subject\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: medidata.getsubjectclinicaldata\n      with:\n        studyOID: tools.studyOID\n        subjectKey: tools.subjectKey\n        formOID: tools.formOID\n        EventRepeatKey: tools.EventRepeatKey\n      inputParameters:\n      - name: studyOID\n        type: string\n        description: studyOID\n        required: true\n      - name: subjectKey\n\
  \        type: string\n        description: subjectKey\n        required: true\n      - name: formOID\n        type: string\n        description: Filter to a specific form OID\n      - name: EventRepeatKey\n        type: string\n        description: EventRepeatKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submitclinicaldata\n      description: Submit clinical data for a subject\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: medidata.submitclinicaldata\n      with:\n        studyOID: tools.studyOID\n        subjectKey: tools.subjectKey\n      inputParameters:\n      - name: studyOID\n        type: string\n        description: studyOID\n        required: true\n      - name: subjectKey\n        type: string\n        description: subjectKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listqueries\n      description: List data queries\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: medidata.listqueries\n      with:\n        studyOID: tools.studyOID\n        Status: tools.Status\n        SiteID: tools.SiteID\n        SubjectKey: tools.SubjectKey\n      inputParameters:\n      - name: studyOID\n        type: string\n        description: studyOID\n        required: true\n      - name: Status\n        type: string\n        description: Status\n      - name: SiteID\n        type: string\n        description: SiteID\n      - name: SubjectKey\n        type: string\n        description: SubjectKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getauditrecords\n      description: Get audit trail records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: medidata.getauditrecords\n      with:\n        studyOID: tools.studyOID\n        SubjectKey: tools.SubjectKey\n        SiteID: tools.SiteID\n\
  \        StartDate: tools.StartDate\n        EndDate: tools.EndDate\n        PageSize: tools.PageSize\n      inputParameters:\n      - name: studyOID\n        type: string\n        description: studyOID\n        required: true\n      - name: SubjectKey\n        type: string\n        description: SubjectKey\n      - name: SiteID\n        type: string\n        description: SiteID\n      - name: StartDate\n        type: string\n        description: StartDate\n      - name: EndDate\n        type: string\n        description: EndDate\n      - name: PageSize\n        type: integer\n        description: PageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsites\n      description: List study sites\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: medidata.listsites\n      with:\n        studyOID: tools.studyOID\n      inputParameters:\n      - name: studyOID\n        type: string\n        description:\
  \ studyOID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MEDIDATA_USERNAME: MEDIDATA_USERNAME\n    MEDIDATA_PASSWORD: MEDIDATA_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/medidata/refs/heads/main/capabilities/medidata-capability.yaml
tags:
- Medidata
- API
tools:
- description: List studies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststudies
- description: List subjects in a study
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubjects
- description: Create or update a subject
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubject
- description: Get subject details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubject
- description: Get clinical data (CRF data) for a subject
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubjectclinicaldata
- description: Submit clinical data for a subject
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitclinicaldata
- description: List data queries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listqueries
- description: Get audit trail records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauditrecords
- description: List study sites
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsites
---
