---
categories: []
consumed_apis: []
description: API for managing organizational change initiatives using Prosci's research-based change management methodology. Provides access to change projects, ADKAR assessments, PCT (Prosci Change Triangle) assessments, stakeholder analyses, change plans, and training resources.
layout: capability
name: Prosci Change Management API
operations:
- description: Prosci List change projects
  method: GET
  name: listprojects
  path: /projects
- description: Prosci Create a change project
  method: POST
  name: createproject
  path: /projects
- description: Prosci Get a change project
  method: GET
  name: getproject
  path: /projects/{projectId}
- description: Prosci Update a change project
  method: PUT
  name: updateproject
  path: /projects/{projectId}
- description: Prosci Delete a change project
  method: DELETE
  name: deleteproject
  path: /projects/{projectId}
- description: Prosci List ADKAR assessments
  method: GET
  name: listadkarassessments
  path: /projects/{projectId}/adkar-assessments
- description: Prosci Create an ADKAR assessment
  method: POST
  name: createadkarassessment
  path: /projects/{projectId}/adkar-assessments
- description: Prosci Get an ADKAR assessment
  method: GET
  name: getadkarassessment
  path: /projects/{projectId}/adkar-assessments/{assessmentId}
- description: Prosci Update an ADKAR assessment
  method: PUT
  name: updateadkarassessment
  path: /projects/{projectId}/adkar-assessments/{assessmentId}
- description: Prosci List PCT assessments
  method: GET
  name: listpctassessments
  path: /projects/{projectId}/pct-assessments
- description: Prosci Create a PCT assessment
  method: POST
  name: createpctassessment
  path: /projects/{projectId}/pct-assessments
- description: Prosci List stakeholders
  method: GET
  name: liststakeholders
  path: /projects/{projectId}/stakeholders
- description: Prosci Add a stakeholder
  method: POST
  name: createstakeholder
  path: /projects/{projectId}/stakeholders
- description: Prosci List change plans
  method: GET
  name: listchangeplans
  path: /projects/{projectId}/change-plans
- description: Prosci Create a change plan
  method: POST
  name: createchangeplan
  path: /projects/{projectId}/change-plans
- description: Prosci Get a change plan
  method: GET
  name: getchangeplan
  path: /projects/{projectId}/change-plans/{planId}
- description: Prosci Update a change plan
  method: PUT
  name: updatechangeplan
  path: /projects/{projectId}/change-plans/{planId}
- description: Prosci Get project risk assessment
  method: GET
  name: getriskassessment
  path: /projects/{projectId}/risk-assessment
- description: Prosci Update project risk assessment
  method: PUT
  name: updateriskassessment
  path: /projects/{projectId}/risk-assessment
- description: Prosci List training programs
  method: GET
  name: listtrainingprograms
  path: /training/programs
- description: Prosci List training enrollments
  method: GET
  name: listenrollments
  path: /training/enrollments
- description: Prosci Enroll in a training program
  method: POST
  name: createenrollment
  path: /training/enrollments
- description: Prosci Get change management maturity
  method: GET
  name: getorganizationmaturity
  path: /organizations/{organizationId}/maturity
personas: []
provider_name: Prosci
provider_slug: prosci
search_terms:
- getproject
- liststakeholders
- prosci get a change plan
- prosci list adkar assessments
- prosci get a change project
- listenrollments
- api
- getriskassessment
- prosci update a change plan
- prosci enroll in a training program
- prosci get an adkar assessment
- prosci update a change project
- prosci create a change plan
- updateadkarassessment
- listpctassessments
- updatechangeplan
- updateproject
- prosci delete a change project
- getchangeplan
- createstakeholder
- prosci list pct assessments
- methodology
- prosci list stakeholders
- createchangeplan
- updateriskassessment
- change management
- prosci list training programs
- prosci
- createpctassessment
- createadkarassessment
- deleteproject
- training
- prosci create a pct assessment
- listtrainingprograms
- prosci update an adkar assessment
- listadkarassessments
- prosci create a change project
- listchangeplans
- prosci update project risk assessment
- prosci list training enrollments
- createenrollment
- prosci get change management maturity
- getadkarassessment
- listprojects
- prosci list change plans
- prosci create an adkar assessment
- prosci list change projects
- prosci add a stakeholder
- getorganizationmaturity
- prosci get project risk assessment
- createproject
slug: prosci-capability
source_filename: prosci-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Prosci Change Management API\n  description: API for managing organizational change initiatives using Prosci's research-based change management methodology.\n    Provides access to change projects, ADKAR assessments, PCT (Prosci Change Triangle) assessments, stakeholder analyses,\n    change plans, and training resources.\n  tags:\n  - Prosci\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: prosci\n    baseUri: https://api.prosci.com/v1\n    description: Prosci Change Management API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PROSCI_TOKEN}}'\n    resources:\n    - name: projects\n      path: /projects\n      operations:\n      - name: listprojects\n        method: GET\n        description: Prosci List change projects\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter projects\
  \ by status\n        - name: sponsorId\n          in: query\n          type: string\n          description: Filter projects by executive sponsor identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Prosci Create a change project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid\n      path: /projects/{projectId}\n      operations:\n      - name: getproject\n        method: GET\n        description: Prosci Get a change project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PUT\n        description: Prosci Update a change project\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: deleteproject\n        method: DELETE\n        description: Prosci Delete a change project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-adkar-assessments\n      path: /projects/{projectId}/adkar-assessments\n      operations:\n      - name: listadkarassessments\n        method: GET\n        description: Prosci List ADKAR assessments\n        inputParameters:\n        - name: stakeholderId\n          in: query\n          type: string\n          description: Filter assessments by stakeholder identifier\n        - name: groupId\n          in: query\n          type: string\n          description: Filter assessments by impacted group identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createadkarassessment\n   \
  \     method: POST\n        description: Prosci Create an ADKAR assessment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-adkar-assessments-assessmenti\n      path: /projects/{projectId}/adkar-assessments/{assessmentId}\n      operations:\n      - name: getadkarassessment\n        method: GET\n        description: Prosci Get an ADKAR assessment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateadkarassessment\n        method: PUT\n        description: Prosci Update an ADKAR assessment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-pct-assessments\n      path: /projects/{projectId}/pct-assessments\n      operations:\n      - name: listpctassessments\n        method: GET\n\
  \        description: Prosci List PCT assessments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpctassessment\n        method: POST\n        description: Prosci Create a PCT assessment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-stakeholders\n      path: /projects/{projectId}/stakeholders\n      operations:\n      - name: liststakeholders\n        method: GET\n        description: Prosci List stakeholders\n        inputParameters:\n        - name: role\n          in: query\n          type: string\n          description: Filter stakeholders by role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createstakeholder\n        method: POST\n        description: Prosci Add a stakeholder\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-change-plans\n      path: /projects/{projectId}/change-plans\n      operations:\n      - name: listchangeplans\n        method: GET\n        description: Prosci List change plans\n        inputParameters:\n        - name: planType\n          in: query\n          type: string\n          description: Filter by plan type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createchangeplan\n        method: POST\n        description: Prosci Create a change plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-change-plans-planid\n      path: /projects/{projectId}/change-plans/{planId}\n      operations:\n      - name: getchangeplan\n    \
  \    method: GET\n        description: Prosci Get a change plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatechangeplan\n        method: PUT\n        description: Prosci Update a change plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-risk-assessment\n      path: /projects/{projectId}/risk-assessment\n      operations:\n      - name: getriskassessment\n        method: GET\n        description: Prosci Get project risk assessment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateriskassessment\n        method: PUT\n        description: Prosci Update project risk assessment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: training-programs\n      path: /training/programs\n      operations:\n      - name: listtrainingprograms\n        method: GET\n        description: Prosci List training programs\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: Filter by delivery format\n        - name: programType\n          in: query\n          type: string\n          description: Filter by program type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: training-enrollments\n      path: /training/enrollments\n      operations:\n      - name: listenrollments\n        method: GET\n        description: Prosci List training enrollments\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by enrollment status\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createenrollment\n        method: POST\n        description: Prosci Enroll in a training program\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organizationid-maturity\n      path: /organizations/{organizationId}/maturity\n      operations:\n      - name: getorganizationmaturity\n        method: GET\n        description: Prosci Get change management maturity\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: prosci-rest\n    description: REST adapter for Prosci Change Management\
  \ API.\n    resources:\n    - path: /projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: Prosci List change projects\n        call: prosci.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Prosci Create a change project\n        call: prosci.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Prosci Get a change project\n        call: prosci.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}\n      name: updateproject\n      operations:\n      - method: PUT\n        name: updateproject\n   \
  \     description: Prosci Update a change project\n        call: prosci.updateproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}\n      name: deleteproject\n      operations:\n      - method: DELETE\n        name: deleteproject\n        description: Prosci Delete a change project\n        call: prosci.deleteproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/adkar-assessments\n      name: listadkarassessments\n      operations:\n      - method: GET\n        name: listadkarassessments\n        description: Prosci List ADKAR assessments\n        call: prosci.listadkarassessments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/adkar-assessments\n      name: createadkarassessment\n      operations:\n      - method: POST\n        name: createadkarassessment\n        description: Prosci Create an ADKAR\
  \ assessment\n        call: prosci.createadkarassessment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/adkar-assessments/{assessmentId}\n      name: getadkarassessment\n      operations:\n      - method: GET\n        name: getadkarassessment\n        description: Prosci Get an ADKAR assessment\n        call: prosci.getadkarassessment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/adkar-assessments/{assessmentId}\n      name: updateadkarassessment\n      operations:\n      - method: PUT\n        name: updateadkarassessment\n        description: Prosci Update an ADKAR assessment\n        call: prosci.updateadkarassessment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/pct-assessments\n      name: listpctassessments\n      operations:\n      - method: GET\n        name: listpctassessments\n        description:\
  \ Prosci List PCT assessments\n        call: prosci.listpctassessments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/pct-assessments\n      name: createpctassessment\n      operations:\n      - method: POST\n        name: createpctassessment\n        description: Prosci Create a PCT assessment\n        call: prosci.createpctassessment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/stakeholders\n      name: liststakeholders\n      operations:\n      - method: GET\n        name: liststakeholders\n        description: Prosci List stakeholders\n        call: prosci.liststakeholders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/stakeholders\n      name: createstakeholder\n      operations:\n      - method: POST\n        name: createstakeholder\n        description: Prosci Add a stakeholder\n        call: prosci.createstakeholder\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/change-plans\n      name: listchangeplans\n      operations:\n      - method: GET\n        name: listchangeplans\n        description: Prosci List change plans\n        call: prosci.listchangeplans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/change-plans\n      name: createchangeplan\n      operations:\n      - method: POST\n        name: createchangeplan\n        description: Prosci Create a change plan\n        call: prosci.createchangeplan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/change-plans/{planId}\n      name: getchangeplan\n      operations:\n      - method: GET\n        name: getchangeplan\n        description: Prosci Get a change plan\n        call: prosci.getchangeplan\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /projects/{projectId}/change-plans/{planId}\n      name: updatechangeplan\n      operations:\n      - method: PUT\n        name: updatechangeplan\n        description: Prosci Update a change plan\n        call: prosci.updatechangeplan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/risk-assessment\n      name: getriskassessment\n      operations:\n      - method: GET\n        name: getriskassessment\n        description: Prosci Get project risk assessment\n        call: prosci.getriskassessment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/risk-assessment\n      name: updateriskassessment\n      operations:\n      - method: PUT\n        name: updateriskassessment\n        description: Prosci Update project risk assessment\n        call: prosci.updateriskassessment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /training/programs\n      name: listtrainingprograms\n      operations:\n      - method: GET\n        name: listtrainingprograms\n        description: Prosci List training programs\n        call: prosci.listtrainingprograms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /training/enrollments\n      name: listenrollments\n      operations:\n      - method: GET\n        name: listenrollments\n        description: Prosci List training enrollments\n        call: prosci.listenrollments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /training/enrollments\n      name: createenrollment\n      operations:\n      - method: POST\n        name: createenrollment\n        description: Prosci Enroll in a training program\n        call: prosci.createenrollment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organizationId}/maturity\n      name: getorganizationmaturity\n\
  \      operations:\n      - method: GET\n        name: getorganizationmaturity\n        description: Prosci Get change management maturity\n        call: prosci.getorganizationmaturity\n        with:\n          organizationId: rest.organizationId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: prosci-mcp\n    transport: http\n    description: MCP adapter for Prosci Change Management API for AI agent use.\n    tools:\n    - name: listprojects\n      description: Prosci List change projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prosci.listprojects\n      with:\n        status: tools.status\n        sponsorId: tools.sponsorId\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter projects by status\n      - name: sponsorId\n        type: string\n        description: Filter projects by executive sponsor identifier\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproject\n      description: Prosci Create a change project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: prosci.createproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: Prosci Get a change project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prosci.getproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproject\n      description: Prosci Update a change project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: prosci.updateproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproject\n      description: Prosci Delete a change project\n      hints:\n        readOnly: false\n   \
  \     destructive: true\n        idempotent: true\n      call: prosci.deleteproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listadkarassessments\n      description: Prosci List ADKAR assessments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prosci.listadkarassessments\n      with:\n        stakeholderId: tools.stakeholderId\n        groupId: tools.groupId\n      inputParameters:\n      - name: stakeholderId\n        type: string\n        description: Filter assessments by stakeholder identifier\n      - name: groupId\n        type: string\n        description: Filter assessments by impacted group identifier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createadkarassessment\n      description: Prosci Create an ADKAR assessment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: prosci.createadkarassessment\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getadkarassessment\n      description: Prosci Get an ADKAR assessment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prosci.getadkarassessment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateadkarassessment\n      description: Prosci Update an ADKAR assessment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: prosci.updateadkarassessment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpctassessments\n      description: Prosci List PCT assessments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prosci.listpctassessments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpctassessment\n      description: Prosci Create a PCT assessment\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: prosci.createpctassessment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststakeholders\n      description: Prosci List stakeholders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prosci.liststakeholders\n      with:\n        role: tools.role\n      inputParameters:\n      - name: role\n        type: string\n        description: Filter stakeholders by role\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createstakeholder\n      description: Prosci Add a stakeholder\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: prosci.createstakeholder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listchangeplans\n      description: Prosci List change plans\n      hints:\n     \
  \   readOnly: true\n        destructive: false\n        idempotent: true\n      call: prosci.listchangeplans\n      with:\n        planType: tools.planType\n      inputParameters:\n      - name: planType\n        type: string\n        description: Filter by plan type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createchangeplan\n      description: Prosci Create a change plan\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: prosci.createchangeplan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getchangeplan\n      description: Prosci Get a change plan\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prosci.getchangeplan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatechangeplan\n      description: Prosci Update a change plan\n      hints:\n        readOnly: false\n  \
  \      destructive: false\n        idempotent: true\n      call: prosci.updatechangeplan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getriskassessment\n      description: Prosci Get project risk assessment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prosci.getriskassessment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateriskassessment\n      description: Prosci Update project risk assessment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: prosci.updateriskassessment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtrainingprograms\n      description: Prosci List training programs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prosci.listtrainingprograms\n      with:\n        format: tools.format\n   \
  \     programType: tools.programType\n      inputParameters:\n      - name: format\n        type: string\n        description: Filter by delivery format\n      - name: programType\n        type: string\n        description: Filter by program type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listenrollments\n      description: Prosci List training enrollments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prosci.listenrollments\n      with:\n        status: tools.status\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by enrollment status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createenrollment\n      description: Prosci Enroll in a training program\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: prosci.createenrollment\n      outputParameters:\n  \
  \    - type: object\n        mapping: $.\n    - name: getorganizationmaturity\n      description: Prosci Get change management maturity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prosci.getorganizationmaturity\n      with:\n        organizationId: tools.organizationId\n      inputParameters:\n      - name: organizationId\n        type: string\n        description: Unique identifier for the organization\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PROSCI_TOKEN: PROSCI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/prosci/refs/heads/main/capabilities/prosci-capability.yaml
tags:
- Prosci
- API
tools:
- description: Prosci List change projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Prosci Create a change project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Prosci Get a change project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Prosci Update a change project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproject
- description: Prosci Delete a change project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproject
- description: Prosci List ADKAR assessments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadkarassessments
- description: Prosci Create an ADKAR assessment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createadkarassessment
- description: Prosci Get an ADKAR assessment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadkarassessment
- description: Prosci Update an ADKAR assessment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateadkarassessment
- description: Prosci List PCT assessments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpctassessments
- description: Prosci Create a PCT assessment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpctassessment
- description: Prosci List stakeholders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststakeholders
- description: Prosci Add a stakeholder
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createstakeholder
- description: Prosci List change plans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchangeplans
- description: Prosci Create a change plan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchangeplan
- description: Prosci Get a change plan
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchangeplan
- description: Prosci Update a change plan
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatechangeplan
- description: Prosci Get project risk assessment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getriskassessment
- description: Prosci Update project risk assessment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateriskassessment
- description: Prosci List training programs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtrainingprograms
- description: Prosci List training enrollments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listenrollments
- description: Prosci Enroll in a training program
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createenrollment
- description: Prosci Get change management maturity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationmaturity
---
