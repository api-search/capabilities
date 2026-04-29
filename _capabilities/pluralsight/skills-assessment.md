---
categories: []
consumed_apis:
- pluralsight-skills-assessment
- pluralsight-role-iq
- pluralsight-practice-exams
description: Unified workflow for L&D managers and developers to assess skills through Skill IQ, Role IQ, and practice exams. Combines skills assessment, role IQ, and practice exams APIs for comprehensive competency measurement.
layout: capability
name: Pluralsight Skills Assessment
operations:
- description: Query skill assessments and Skill IQ scores
  method: POST
  name: query-skills-assessment
  path: /v1/skills-assessments
- description: Query and manage Role IQ assessments and role associations
  method: POST
  name: manage-role-iq
  path: /v1/role-iq
- description: Query practice exam attempt data and results
  method: POST
  name: query-practice-exams
  path: /v1/practice-exams
personas: []
provider_name: Pluralsight
provider_slug: pluralsight
search_terms:
- skills assessment
- query skill assessments and skill iq scores
- courses
- query skill assessments, skill iq scores, assessment catalogs, and competency measurements.
- query practice exam attempt data and results
- pluralsight
- video training
- learning
- query practice exam attempt data including scores and results.
- manage role iq
- query practice exams
- education
- practice exam attempts, scores, and results
- engineering metrics
- skill iq
- query and manage role iq assessments, role catalogs, skill assignments, and user/team role associations.
- role iq
- practice exams
- technology
- query skills assessment
- skill iq assessments, scores, and competency measurements
- role iq assessments, role catalogs, and skill assignments
- query and manage role iq assessments and role associations
slug: skills-assessment
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Pluralsight Skills Assessment\"\n  description: \"Unified workflow for L&D managers and developers to assess skills through Skill IQ, Role IQ, and practice exams. Combines skills assessment, role IQ, and practice exams APIs for comprehensive competency measurement.\"\n  tags:\n    - Pluralsight\n    - Skills Assessment\n    - Skill IQ\n    - Role IQ\n    - Practice Exams\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PLURALSIGHT_BEARER_TOKEN: PLURALSIGHT_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: pluralsight-skills-assessment\n      location: ./shared/skills-assessment.yaml\n    - import: pluralsight-role-iq\n      location: ./shared/role-iq.yaml\n    - import: pluralsight-practice-exams\n      location: ./shared/practice-exams.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: skills-assessment-api\n      description: \"Unified REST API\
  \ for Pluralsight skills assessment including Skill IQ, Role IQ, and practice exams.\"\n      resources:\n        - path: /v1/skills-assessments\n          name: skills-assessments\n          description: \"Skill IQ assessments, scores, and competency measurements\"\n          operations:\n            - method: POST\n              name: query-skills-assessment\n              description: \"Query skill assessments and Skill IQ scores\"\n              call: \"pluralsight-skills-assessment.query-skills-assessment\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/role-iq\n          name: role-iq\n          description: \"Role IQ assessments, role catalogs, and skill assignments\"\n          operations:\n            - method: POST\n              name: manage-role-iq\n\
  \              description: \"Query and manage Role IQ assessments and role associations\"\n              call: \"pluralsight-role-iq.manage-role-iq\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/practice-exams\n          name: practice-exams\n          description: \"Practice exam attempts, scores, and results\"\n          operations:\n            - method: POST\n              name: query-practice-exams\n              description: \"Query practice exam attempt data and results\"\n              call: \"pluralsight-practice-exams.query-practice-exams\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n       \
  \         - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: skills-assessment-mcp\n      transport: http\n      description: \"MCP server for AI-assisted skills assessment including Skill IQ, Role IQ, and practice exams.\"\n      tools:\n        - name: query-skills-assessment\n          description: \"Query skill assessments, Skill IQ scores, assessment catalogs, and competency measurements.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-skills-assessment.query-skills-assessment\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: manage-role-iq\n          description: \"Query and manage Role IQ assessments, role\
  \ catalogs, skill assignments, and user/team role associations.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          call: \"pluralsight-role-iq.manage-role-iq\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-practice-exams\n          description: \"Query practice exam attempt data including scores and results.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-practice-exams.query-practice-exams\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/capabilities/skills-assessment.yaml
tags:
- Pluralsight
- Skills Assessment
- Skill IQ
- Role IQ
- Practice Exams
tools:
- description: Query skill assessments, Skill IQ scores, assessment catalogs, and competency measurements.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-skills-assessment
- description: Query and manage Role IQ assessments, role catalogs, skill assignments, and user/team role associations.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: manage-role-iq
- description: Query practice exam attempt data including scores and results.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-practice-exams
---
