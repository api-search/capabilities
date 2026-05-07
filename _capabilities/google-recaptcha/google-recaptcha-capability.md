---
categories: []
consumed_apis: []
description: The reCAPTCHA Enterprise API provides bot detection and fraud prevention by creating assessments for user interaction tokens. It supports managing site keys, creating and annotating assessments, and configuring firewall policies.
layout: capability
name: Google reCAPTCHA reCAPTCHA Enterprise API
operations:
- description: Google reCAPTCHA Create assessment
  method: POST
  name: createassessment
  path: /projects/{projectId}/assessments
- description: Google reCAPTCHA Annotate assessment
  method: POST
  name: annotateassessment
  path: /projects/{projectId}/assessments/{assessmentId}:annotate
- description: Google reCAPTCHA List keys
  method: GET
  name: listkeys
  path: /projects/{projectId}/keys
- description: Google reCAPTCHA Create key
  method: POST
  name: createkey
  path: /projects/{projectId}/keys
- description: Google reCAPTCHA Get key
  method: GET
  name: getkey
  path: /projects/{projectId}/keys/{keyId}
- description: Google reCAPTCHA Delete key
  method: DELETE
  name: deletekey
  path: /projects/{projectId}/keys/{keyId}
personas: []
provider_name: Google reCAPTCHA
provider_slug: google-recaptcha
search_terms:
- recaptcha
- api
- google recaptcha delete key
- google recaptcha create key
- google
- captcha
- bot detection
- createassessment
- google recaptcha list keys
- annotateassessment
- deletekey
- listkeys
- fraud prevention
- getkey
- google recaptcha annotate assessment
- google recaptcha get key
- google recaptcha create assessment
- createkey
- abuse prevention
- google cloud
- security
slug: google-recaptcha-capability
source_filename: google-recaptcha-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google reCAPTCHA reCAPTCHA Enterprise API\n  description: The reCAPTCHA Enterprise API provides bot detection and fraud prevention by creating assessments for user interaction\n    tokens. It supports managing site keys, creating and annotating assessments, and configuring firewall policies.\n  tags:\n  - Google\n  - Recaptcha\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-recaptcha\n    baseUri: https://recaptchaenterprise.googleapis.com/v1\n    description: Google reCAPTCHA reCAPTCHA Enterprise API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_RECAPTCHA_TOKEN}}'\n    resources:\n    - name: projects-projectid-assessments\n      path: /projects/{projectId}/assessments\n      operations:\n      - name: createassessment\n        method: POST\n        description: Google reCAPTCHA Create assessment\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-assessments-assessmentid-anno\n      path: /projects/{projectId}/assessments/{assessmentId}:annotate\n      operations:\n      - name: annotateassessment\n        method: POST\n        description: Google reCAPTCHA Annotate assessment\n        inputParameters:\n        - name: assessmentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-keys\n      path: /projects/{projectId}/keys\n      operations:\n      - name: listkeys\n        method: GET\n        description: Google reCAPTCHA List keys\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createkey\n        method: POST\n        description: Google reCAPTCHA Create key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-keys-keyid\n      path: /projects/{projectId}/keys/{keyId}\n      operations:\n      - name: getkey\n        method: GET\n        description: Google reCAPTCHA Get key\n        inputParameters:\n        - name: keyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletekey\n        method: DELETE\n        description: Google reCAPTCHA Delete key\n        inputParameters:\n        - name: keyId\n          in: path\n          type: string\n          required: true\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-recaptcha-rest\n    description: REST adapter for Google reCAPTCHA reCAPTCHA Enterprise API.\n    resources:\n    - path: /projects/{projectId}/assessments\n      name: createassessment\n      operations:\n      - method: POST\n        name: createassessment\n        description: Google reCAPTCHA Create assessment\n        call: google-recaptcha.createassessment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/assessments/{assessmentId}:annotate\n      name: annotateassessment\n      operations:\n      - method: POST\n        name: annotateassessment\n        description: Google reCAPTCHA Annotate assessment\n        call: google-recaptcha.annotateassessment\n        with:\n          assessmentId: rest.assessmentId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/keys\n      name: listkeys\n      operations:\n      - method: GET\n        name: listkeys\n        description: Google reCAPTCHA List keys\n        call: google-recaptcha.listkeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/keys\n      name: createkey\n      operations:\n      - method: POST\n        name: createkey\n        description: Google reCAPTCHA Create key\n        call: google-recaptcha.createkey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/keys/{keyId}\n      name: getkey\n      operations:\n      - method: GET\n        name: getkey\n        description: Google reCAPTCHA Get key\n        call: google-recaptcha.getkey\n        with:\n          keyId: rest.keyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/keys/{keyId}\n\
  \      name: deletekey\n      operations:\n      - method: DELETE\n        name: deletekey\n        description: Google reCAPTCHA Delete key\n        call: google-recaptcha.deletekey\n        with:\n          keyId: rest.keyId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-recaptcha-mcp\n    transport: http\n    description: MCP adapter for Google reCAPTCHA reCAPTCHA Enterprise API for AI agent use.\n    tools:\n    - name: createassessment\n      description: Google reCAPTCHA Create assessment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-recaptcha.createassessment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: annotateassessment\n      description: Google reCAPTCHA Annotate assessment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-recaptcha.annotateassessment\n\
  \      with:\n        assessmentId: tools.assessmentId\n      inputParameters:\n      - name: assessmentId\n        type: string\n        description: assessmentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listkeys\n      description: Google reCAPTCHA List keys\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-recaptcha.listkeys\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createkey\n      description: Google reCAPTCHA Create key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-recaptcha.createkey\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: getkey\n      description: Google reCAPTCHA Get key\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-recaptcha.getkey\n      with:\n        keyId: tools.keyId\n      inputParameters:\n      - name: keyId\n        type: string\n        description: keyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletekey\n      description: Google reCAPTCHA Delete key\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-recaptcha.deletekey\n      with:\n        keyId: tools.keyId\n      inputParameters:\n      - name: keyId\n        type: string\n        description: keyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_RECAPTCHA_TOKEN: GOOGLE_RECAPTCHA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-recaptcha/refs/heads/main/capabilities/google-recaptcha-capability.yaml
tags:
- Google
- Recaptcha
- API
tools:
- description: Google reCAPTCHA Create assessment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createassessment
- description: Google reCAPTCHA Annotate assessment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: annotateassessment
- description: Google reCAPTCHA List keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listkeys
- description: Google reCAPTCHA Create key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createkey
- description: Google reCAPTCHA Get key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getkey
- description: Google reCAPTCHA Delete key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletekey
---
