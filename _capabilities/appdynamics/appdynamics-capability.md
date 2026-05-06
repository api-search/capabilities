---
categories: []
consumed_apis: []
description: The AppDynamics Alert and Respond API enables programmatic management of health rules, policies, and actions within the AppDynamics Controller. Developers can create, update, and delete health rules that define performance thresholds, configure alerting policies that determine how violations are handled, and set up automated response actions. This API is essential for automating incident response workflows and integrating AppDynamics alerting with external notification and ticketing systems.
layout: capability
name: AppDynamics Alert and Respond API
operations:
- description: List health rules for an application
  method: GET
  name: listhealthrules
  path: /alerting/rest/v1/applications/{applicationId}/health-rules
- description: Create a health rule
  method: POST
  name: createhealthrule
  path: /alerting/rest/v1/applications/{applicationId}/health-rules
- description: Get a specific health rule
  method: GET
  name: gethealthrule
  path: /alerting/rest/v1/applications/{applicationId}/health-rules/{healthRuleId}
- description: Update a health rule
  method: PUT
  name: updatehealthrule
  path: /alerting/rest/v1/applications/{applicationId}/health-rules/{healthRuleId}
- description: Delete a health rule
  method: DELETE
  name: deletehealthrule
  path: /alerting/rest/v1/applications/{applicationId}/health-rules/{healthRuleId}
- description: List policies for an application
  method: GET
  name: listpolicies
  path: /alerting/rest/v1/applications/{applicationId}/policies
- description: Create a policy
  method: POST
  name: createpolicy
  path: /alerting/rest/v1/applications/{applicationId}/policies
- description: Get a specific policy
  method: GET
  name: getpolicy
  path: /alerting/rest/v1/applications/{applicationId}/policies/{policyId}
- description: Update a policy
  method: PUT
  name: updatepolicy
  path: /alerting/rest/v1/applications/{applicationId}/policies/{policyId}
- description: Delete a policy
  method: DELETE
  name: deletepolicy
  path: /alerting/rest/v1/applications/{applicationId}/policies/{policyId}
- description: List actions for an application
  method: GET
  name: listactions
  path: /alerting/rest/v1/applications/{applicationId}/actions
- description: Create an action
  method: POST
  name: createaction
  path: /alerting/rest/v1/applications/{applicationId}/actions
- description: Get a specific action
  method: GET
  name: getaction
  path: /alerting/rest/v1/applications/{applicationId}/actions/{actionId}
- description: Update an action
  method: PUT
  name: updateaction
  path: /alerting/rest/v1/applications/{applicationId}/actions/{actionId}
- description: Delete an action
  method: DELETE
  name: deleteaction
  path: /alerting/rest/v1/applications/{applicationId}/actions/{actionId}
personas: []
provider_name: AppDynamics
provider_slug: appdynamics
search_terms:
- update a health rule
- apm
- get a specific policy
- list actions for an application
- updatehealthrule
- createpolicy
- list health rules for an application
- get a specific action
- devops
- createaction
- application performance monitoring
- delete a policy
- getaction
- listpolicies
- cisco
- listactions
- monitoring
- updatepolicy
- createhealthrule
- create an action
- getpolicy
- opentelemetry
- update an action
- get a specific health rule
- list policies for an application
- api
- create a health rule
- observability
- create a policy
- cloud observability
- appdynamics
- updateaction
- delete a health rule
- deletepolicy
- update a policy
- gethealthrule
- deletehealthrule
- deleteaction
- delete an action
- listhealthrules
slug: appdynamics-capability
source_filename: appdynamics-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AppDynamics Alert and Respond API\n  description: The AppDynamics Alert and Respond API enables programmatic management of health rules, policies, and actions\n    within the AppDynamics Controller. Developers can create, update, and delete health rules that define performance thresholds,\n    configure alerting policies that determine how violations are handled, and set up automated response actions. This API\n    is essential for automating incident response workflows and integrating AppDynamics alerting with external notification\n    and ticketing systems.\n  tags:\n  - Appdynamics\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: appdynamics\n    baseUri: https://example.saas.appdynamics.com/controller\n    description: AppDynamics Alert and Respond API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{APPDYNAMICS_TOKEN}}'\n    resources:\n    -\
  \ name: alerting-rest-v1-applications-applicationid-heal\n      path: /alerting/rest/v1/applications/{applicationId}/health-rules\n      operations:\n      - name: listhealthrules\n        method: GET\n        description: List health rules for an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createhealthrule\n        method: POST\n        description: Create a health rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerting-rest-v1-applications-applicationid-heal\n      path: /alerting/rest/v1/applications/{applicationId}/health-rules/{healthRuleId}\n      operations:\n      - name: gethealthrule\n        method: GET\n        description: Get a specific health rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: updatehealthrule\n        method: PUT\n        description: Update a health rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletehealthrule\n        method: DELETE\n        description: Delete a health rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerting-rest-v1-applications-applicationid-poli\n      path: /alerting/rest/v1/applications/{applicationId}/policies\n      operations:\n      - name: listpolicies\n        method: GET\n        description: List policies for an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpolicy\n        method: POST\n        description: Create a policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: alerting-rest-v1-applications-applicationid-poli\n      path: /alerting/rest/v1/applications/{applicationId}/policies/{policyId}\n      operations:\n      - name: getpolicy\n        method: GET\n        description: Get a specific policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepolicy\n        method: PUT\n        description: Update a policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepolicy\n        method: DELETE\n        description: Delete a policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerting-rest-v1-applications-applicationid-acti\n      path: /alerting/rest/v1/applications/{applicationId}/actions\n      operations:\n\
  \      - name: listactions\n        method: GET\n        description: List actions for an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createaction\n        method: POST\n        description: Create an action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerting-rest-v1-applications-applicationid-acti\n      path: /alerting/rest/v1/applications/{applicationId}/actions/{actionId}\n      operations:\n      - name: getaction\n        method: GET\n        description: Get a specific action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaction\n        method: PUT\n        description: Update an action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: deleteaction\n        method: DELETE\n        description: Delete an action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: appdynamics-rest\n    description: REST adapter for AppDynamics Alert and Respond API.\n    resources:\n    - path: /alerting/rest/v1/applications/{applicationId}/health-rules\n      name: listhealthrules\n      operations:\n      - method: GET\n        name: listhealthrules\n        description: List health rules for an application\n        call: appdynamics.listhealthrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/health-rules\n      name: createhealthrule\n      operations:\n      - method: POST\n        name: createhealthrule\n        description: Create a health rule\n        call:\
  \ appdynamics.createhealthrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/health-rules/{healthRuleId}\n      name: gethealthrule\n      operations:\n      - method: GET\n        name: gethealthrule\n        description: Get a specific health rule\n        call: appdynamics.gethealthrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/health-rules/{healthRuleId}\n      name: updatehealthrule\n      operations:\n      - method: PUT\n        name: updatehealthrule\n        description: Update a health rule\n        call: appdynamics.updatehealthrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/health-rules/{healthRuleId}\n      name: deletehealthrule\n      operations:\n      - method: DELETE\n        name: deletehealthrule\n \
  \       description: Delete a health rule\n        call: appdynamics.deletehealthrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/policies\n      name: listpolicies\n      operations:\n      - method: GET\n        name: listpolicies\n        description: List policies for an application\n        call: appdynamics.listpolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/policies\n      name: createpolicy\n      operations:\n      - method: POST\n        name: createpolicy\n        description: Create a policy\n        call: appdynamics.createpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/policies/{policyId}\n      name: getpolicy\n      operations:\n      - method: GET\n        name: getpolicy\n        description: Get\
  \ a specific policy\n        call: appdynamics.getpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/policies/{policyId}\n      name: updatepolicy\n      operations:\n      - method: PUT\n        name: updatepolicy\n        description: Update a policy\n        call: appdynamics.updatepolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/policies/{policyId}\n      name: deletepolicy\n      operations:\n      - method: DELETE\n        name: deletepolicy\n        description: Delete a policy\n        call: appdynamics.deletepolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/actions\n      name: listactions\n      operations:\n      - method: GET\n        name: listactions\n        description: List actions for an application\n\
  \        call: appdynamics.listactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/actions\n      name: createaction\n      operations:\n      - method: POST\n        name: createaction\n        description: Create an action\n        call: appdynamics.createaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/actions/{actionId}\n      name: getaction\n      operations:\n      - method: GET\n        name: getaction\n        description: Get a specific action\n        call: appdynamics.getaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/actions/{actionId}\n      name: updateaction\n      operations:\n      - method: PUT\n        name: updateaction\n        description: Update an action\n        call: appdynamics.updateaction\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerting/rest/v1/applications/{applicationId}/actions/{actionId}\n      name: deleteaction\n      operations:\n      - method: DELETE\n        name: deleteaction\n        description: Delete an action\n        call: appdynamics.deleteaction\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: appdynamics-mcp\n    transport: http\n    description: MCP adapter for AppDynamics Alert and Respond API for AI agent use.\n    tools:\n    - name: listhealthrules\n      description: List health rules for an application\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: appdynamics.listhealthrules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createhealthrule\n      description: Create a health rule\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: appdynamics.createhealthrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethealthrule\n      description: Get a specific health rule\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: appdynamics.gethealthrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatehealthrule\n      description: Update a health rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: appdynamics.updatehealthrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletehealthrule\n      description: Delete a health rule\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: appdynamics.deletehealthrule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpolicies\n      description:\
  \ List policies for an application\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: appdynamics.listpolicies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpolicy\n      description: Create a policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: appdynamics.createpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpolicy\n      description: Get a specific policy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: appdynamics.getpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepolicy\n      description: Update a policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: appdynamics.updatepolicy\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: deletepolicy\n      description: Delete a policy\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: appdynamics.deletepolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listactions\n      description: List actions for an application\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: appdynamics.listactions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createaction\n      description: Create an action\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: appdynamics.createaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaction\n      description: Get a specific action\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: appdynamics.getaction\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateaction\n      description: Update an action\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: appdynamics.updateaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteaction\n      description: Delete an action\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: appdynamics.deleteaction\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    APPDYNAMICS_TOKEN: APPDYNAMICS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/appdynamics/refs/heads/main/capabilities/appdynamics-capability.yaml
tags:
- Appdynamics
- API
tools:
- description: List health rules for an application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listhealthrules
- description: Create a health rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createhealthrule
- description: Get a specific health rule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealthrule
- description: Update a health rule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatehealthrule
- description: Delete a health rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletehealthrule
- description: List policies for an application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpolicies
- description: Create a policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpolicy
- description: Get a specific policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpolicy
- description: Update a policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepolicy
- description: Delete a policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepolicy
- description: List actions for an application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listactions
- description: Create an action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaction
- description: Get a specific action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaction
- description: Update an action
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateaction
- description: Delete an action
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaction
---
