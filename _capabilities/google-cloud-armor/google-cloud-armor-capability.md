---
categories: []
consumed_apis: []
description: Provides programmatic access to manage security policies, rules, and threat intelligence configurations for protecting applications from DDoS attacks and web-based threats.
layout: capability
name: Google Cloud Armor API
operations:
- description: Google Cloud Armor List security policies
  method: GET
  name: listsecuritypolicies
  path: /projects/{project}/global/securityPolicies
- description: Google Cloud Armor Create a security policy
  method: POST
  name: createsecuritypolicy
  path: /projects/{project}/global/securityPolicies
- description: Google Cloud Armor Get a security policy
  method: GET
  name: getsecuritypolicy
  path: /projects/{project}/global/securityPolicies/{securityPolicy}
- description: Google Cloud Armor Update a security policy
  method: PATCH
  name: patchsecuritypolicy
  path: /projects/{project}/global/securityPolicies/{securityPolicy}
- description: Google Cloud Armor Delete a security policy
  method: DELETE
  name: deletesecuritypolicy
  path: /projects/{project}/global/securityPolicies/{securityPolicy}
- description: Google Cloud Armor Add a rule to a security policy
  method: POST
  name: addsecuritypolicyrule
  path: /projects/{project}/global/securityPolicies/{securityPolicy}/addRule
- description: Google Cloud Armor Remove a rule from a security policy
  method: POST
  name: removesecuritypolicyrule
  path: /projects/{project}/global/securityPolicies/{securityPolicy}/removeRule
personas: []
provider_name: Google Cloud Armor
provider_slug: google-cloud-armor
search_terms:
- google cloud armor add a rule to a security policy
- ddos protection
- listsecuritypolicies
- api
- waf
- armor
- google
- google cloud armor list security policies
- removesecuritypolicyrule
- patchsecuritypolicy
- createsecuritypolicy
- deletesecuritypolicy
- google cloud armor create a security policy
- cloud
- addsecuritypolicyrule
- google cloud armor remove a rule from a security policy
- firewall
- google cloud armor get a security policy
- google cloud armor delete a security policy
- google cloud armor update a security policy
- google cloud
- security
- getsecuritypolicy
slug: google-cloud-armor-capability
source_filename: google-cloud-armor-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Armor API\n  description: Provides programmatic access to manage security policies, rules, and threat intelligence configurations for\n    protecting applications from DDoS attacks and web-based threats.\n  tags:\n  - Google\n  - Cloud\n  - Armor\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-armor\n    baseUri: https://compute.googleapis.com/compute/v1\n    description: Google Cloud Armor API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_ARMOR_TOKEN}}'\n    resources:\n    - name: projects-project-global-securitypolicies\n      path: /projects/{project}/global/securityPolicies\n      operations:\n      - name: listsecuritypolicies\n        method: GET\n        description: Google Cloud Armor List security policies\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsecuritypolicy\n        method: POST\n        description: Google Cloud Armor Create a security policy\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-securitypolicies-securit\n      path: /projects/{project}/global/securityPolicies/{securityPolicy}\n      operations:\n      - name: getsecuritypolicy\n        method: GET\n        description: Google Cloud Armor Get a security policy\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: securityPolicy\n          in: path\n          type: string\n    \
  \      required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchsecuritypolicy\n        method: PATCH\n        description: Google Cloud Armor Update a security policy\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: securityPolicy\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesecuritypolicy\n        method: DELETE\n        description: Google Cloud Armor Delete a security policy\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: securityPolicy\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-securitypolicies-securit\n      path: /projects/{project}/global/securityPolicies/{securityPolicy}/addRule\n      operations:\n      - name: addsecuritypolicyrule\n        method: POST\n        description: Google Cloud Armor Add a rule to a security policy\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: securityPolicy\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-securitypolicies-securit\n      path: /projects/{project}/global/securityPolicies/{securityPolicy}/removeRule\n      operations:\n      - name: removesecuritypolicyrule\n        method: POST\n        description: Google Cloud\
  \ Armor Remove a rule from a security policy\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: securityPolicy\n          in: path\n          type: string\n          required: true\n        - name: priority\n          in: query\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-armor-rest\n    description: REST adapter for Google Cloud Armor API.\n    resources:\n    - path: /projects/{project}/global/securityPolicies\n      name: listsecuritypolicies\n      operations:\n      - method: GET\n        name: listsecuritypolicies\n        description: Google Cloud Armor List security policies\n        call: google-cloud-armor.listsecuritypolicies\n        with:\n          project: rest.project\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/securityPolicies\n      name: createsecuritypolicy\n      operations:\n      - method: POST\n        name: createsecuritypolicy\n        description: Google Cloud Armor Create a security policy\n        call: google-cloud-armor.createsecuritypolicy\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/securityPolicies/{securityPolicy}\n      name: getsecuritypolicy\n      operations:\n      - method: GET\n        name: getsecuritypolicy\n        description: Google Cloud Armor Get a security policy\n        call: google-cloud-armor.getsecuritypolicy\n        with:\n          project: rest.project\n          securityPolicy: rest.securityPolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/securityPolicies/{securityPolicy}\n    \
  \  name: patchsecuritypolicy\n      operations:\n      - method: PATCH\n        name: patchsecuritypolicy\n        description: Google Cloud Armor Update a security policy\n        call: google-cloud-armor.patchsecuritypolicy\n        with:\n          project: rest.project\n          securityPolicy: rest.securityPolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/securityPolicies/{securityPolicy}\n      name: deletesecuritypolicy\n      operations:\n      - method: DELETE\n        name: deletesecuritypolicy\n        description: Google Cloud Armor Delete a security policy\n        call: google-cloud-armor.deletesecuritypolicy\n        with:\n          project: rest.project\n          securityPolicy: rest.securityPolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/securityPolicies/{securityPolicy}/addRule\n      name: addsecuritypolicyrule\n      operations:\n\
  \      - method: POST\n        name: addsecuritypolicyrule\n        description: Google Cloud Armor Add a rule to a security policy\n        call: google-cloud-armor.addsecuritypolicyrule\n        with:\n          project: rest.project\n          securityPolicy: rest.securityPolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/securityPolicies/{securityPolicy}/removeRule\n      name: removesecuritypolicyrule\n      operations:\n      - method: POST\n        name: removesecuritypolicyrule\n        description: Google Cloud Armor Remove a rule from a security policy\n        call: google-cloud-armor.removesecuritypolicyrule\n        with:\n          project: rest.project\n          securityPolicy: rest.securityPolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-armor-mcp\n    transport: http\n    description: MCP adapter for Google Cloud\
  \ Armor API for AI agent use.\n    tools:\n    - name: listsecuritypolicies\n      description: Google Cloud Armor List security policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-armor.listsecuritypolicies\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsecuritypolicy\n      description: Google Cloud Armor Create a security policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-armor.createsecuritypolicy\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: getsecuritypolicy\n      description: Google Cloud Armor Get a security policy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-armor.getsecuritypolicy\n      with:\n        project: tools.project\n        securityPolicy: tools.securityPolicy\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: securityPolicy\n        type: string\n        description: securityPolicy\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchsecuritypolicy\n      description: Google Cloud Armor Update a security policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-armor.patchsecuritypolicy\n      with:\n        project: tools.project\n        securityPolicy: tools.securityPolicy\n      inputParameters:\n      - name:\
  \ project\n        type: string\n        description: project\n        required: true\n      - name: securityPolicy\n        type: string\n        description: securityPolicy\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesecuritypolicy\n      description: Google Cloud Armor Delete a security policy\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-armor.deletesecuritypolicy\n      with:\n        project: tools.project\n        securityPolicy: tools.securityPolicy\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: securityPolicy\n        type: string\n        description: securityPolicy\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addsecuritypolicyrule\n      description: Google Cloud Armor Add a rule to a security\
  \ policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-armor.addsecuritypolicyrule\n      with:\n        project: tools.project\n        securityPolicy: tools.securityPolicy\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: securityPolicy\n        type: string\n        description: securityPolicy\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removesecuritypolicyrule\n      description: Google Cloud Armor Remove a rule from a security policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-armor.removesecuritypolicyrule\n      with:\n        project: tools.project\n        securityPolicy: tools.securityPolicy\n        priority: tools.priority\n      inputParameters:\n      - name: project\n        type:\
  \ string\n        description: project\n        required: true\n      - name: securityPolicy\n        type: string\n        description: securityPolicy\n        required: true\n      - name: priority\n        type: integer\n        description: priority\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_ARMOR_TOKEN: GOOGLE_CLOUD_ARMOR_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-armor/refs/heads/main/capabilities/google-cloud-armor-capability.yaml
tags:
- Google
- Cloud
- Armor
- API
tools:
- description: Google Cloud Armor List security policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsecuritypolicies
- description: Google Cloud Armor Create a security policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsecuritypolicy
- description: Google Cloud Armor Get a security policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsecuritypolicy
- description: Google Cloud Armor Update a security policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchsecuritypolicy
- description: Google Cloud Armor Delete a security policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesecuritypolicy
- description: Google Cloud Armor Add a rule to a security policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addsecuritypolicyrule
- description: Google Cloud Armor Remove a rule from a security policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: removesecuritypolicyrule
---
