---
api_specs:
- filename: abortion-policy-api-openapi.yml
  format: yaml
  label: abortion-policy-api
  slug: abortion-policy-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/abortion-policy-api/refs/heads/main/openapi/abortion-policy-api-openapi.yml
categories: []
consumed_apis:
- abortion-policy-api
description: Unified workflow for looking up US state abortion policies across gestational limits, insurance coverage, minors restrictions, and waiting periods. Designed for healthcare providers, patient advocates, chatbots, and legal aid organizations needing comprehensive state-specific abortion access information.
layout: capability
name: Abortion Policy Lookup
operations:
- description: Get gestational limit policy for a state.
  method: GET
  name: get-gestational-limits-by-state
  path: /v1/policies/{state}
- description: Get gestational limit policy for a zip code.
  method: GET
  name: get-gestational-limits-by-zip
  path: /v1/policies/zip/{zip}
- description: Get gestational limits for a state.
  method: GET
  name: get-gestational-limits-by-state
  path: /v1/gestational-limits/{state}
- description: Get insurance coverage for a state.
  method: GET
  name: get-insurance-coverage-by-state
  path: /v1/insurance-coverage/{state}
- description: Get minors restrictions for a state.
  method: GET
  name: get-minors-by-state
  path: /v1/minors/{state}
- description: Get waiting periods for a state.
  method: GET
  name: get-waiting-periods-by-state
  path: /v1/waiting-periods/{state}
- description: Get gestational limits for all states.
  method: GET
  name: get-gestational-limits-all-states
  path: /v1/all-states/gestational-limits
- description: Get insurance coverage for all states.
  method: GET
  name: get-insurance-coverage-all-states
  path: /v1/all-states/insurance-coverage
- description: Get minors restrictions for all states.
  method: GET
  name: get-minors-all-states
  path: /v1/all-states/minors
- description: Get waiting periods for all states.
  method: GET
  name: get-waiting-periods-all-states
  path: /v1/all-states/waiting-periods
personas: []
provider_name: Abortion Policy API
provider_slug: abortion-policy-api
search_terms:
- get gestational limits all states
- lookup insurance coverage
- lookup waiting periods zip
- healthcare
- lookup minors restrictions zip
- look up abortion gestational limit policy for a specific us state or zip code.
- list all gestational limits
- list abortion waiting period restrictions across all us states.
- legal aid organizations advising clients on state abortion law
- get insurance coverage by state
- get gestational limits for a state.
- Healthcare Provider
- government
- get minors by state
- insurance coverage restrictions for all states.
- get gestational limits for all states.
- get gestational limit policy for a state.
- lookup gestational limits zip
- Legal Aid
- policies
- look up abortion insurance coverage restrictions for a specific us state.
- unified workflow for looking up us state abortion policies across all four data tables
- developers building conversational tools that answer abortion policy questions
- lookup gestational limits
- all abortion policies for a specific zip code.
- list all insurance coverage
- medical providers advising patients on state-specific abortion access restrictions
- get minors restrictions for all states.
- get gestational limit policy for a zip code.
- get insurance coverage all states
- look up abortion waiting period requirements for a specific us state.
- list all waiting periods
- waiting period restrictions for a state.
- lookup minors restrictions
- get minors all states
- lookup insurance coverage zip
- get waiting periods for a state.
- minors abortion restrictions for a state.
- abortion policy
- get waiting periods for all states.
- gestational limit policy for a state.
- government data
- get waiting periods all states
- Chatbot Developer
- look up abortion insurance coverage restrictions for a specific zip code.
- look up abortion waiting period requirements for a specific zip code.
- all abortion policies for a specific state.
- lookup waiting periods
- look up abortion restrictions for minors in a specific zip code.
- us state laws governing abortion access including gestational limits, insurance, minors, and waiting periods
- get waiting periods by state
- get gestational limits by zip
- Patient Advocate
- list all minors restrictions
- list abortion restrictions for minors across all us states.
- minors restrictions for all states.
- advocates helping patients understand abortion access options in their state
- abortion
- gestational limit policies for all states.
- list abortion gestational limit policies for all us states.
- list abortion insurance coverage restrictions for all us states.
- get gestational limits by state
- insurance coverage restrictions for a state.
- patient advocacy
- get insurance coverage for all states.
- get minors restrictions for a state.
- look up abortion restrictions for minors in a specific us state.
- get insurance coverage for a state.
- look up abortion gestational limit policy for a specific zip code.
- waiting period restrictions for all states.
slug: abortion-policy-lookup
source_filename: abortion-policy-lookup.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Abortion Policy Lookup\"\n  description: \"Unified workflow for looking up US state abortion policies across gestational limits, insurance coverage, minors restrictions, and waiting periods. Designed for healthcare providers, patient advocates, chatbots, and legal aid organizations needing comprehensive state-specific abortion access information.\"\n  tags:\n    - Abortion Policy\n    - Healthcare\n    - Government Data\n    - Patient Advocacy\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ABORTION_POLICY_API_TOKEN: ABORTION_POLICY_API_TOKEN\n\ncapability:\n  consumes:\n    - import: abortion-policy-api\n      location: ./shared/abortion-policy-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: abortion-policy-lookup-api\n      description: \"Unified REST API for comprehensive abortion policy lookups by state or zip code.\"\n      resources:\n   \
  \     - path: /v1/policies/{state}\n          name: state-policies\n          description: \"All abortion policies for a specific state.\"\n          operations:\n            - method: GET\n              name: get-gestational-limits-by-state\n              description: \"Get gestational limit policy for a state.\"\n              call: \"abortion-policy-api.get-gestational-limits-by-state\"\n              with:\n                state: \"rest.state\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/policies/zip/{zip}\n          name: zip-policies\n          description: \"All abortion policies for a specific zip code.\"\n          operations:\n            - method: GET\n              name: get-gestational-limits-by-zip\n              description: \"Get gestational limit policy for a zip code.\"\n              call: \"abortion-policy-api.get-gestational-limits-by-zip\"\n              with:\n                zip: \"rest.zip\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/gestational-limits/{state}\n          name: gestational-limits-state\n          description: \"Gestational limit policy for a state.\"\n          operations:\n            - method: GET\n              name: get-gestational-limits-by-state\n              description: \"Get gestational limits for a state.\"\n              call: \"abortion-policy-api.get-gestational-limits-by-state\"\n              with:\n                state: \"rest.state\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/insurance-coverage/{state}\n          name: insurance-coverage-state\n          description: \"Insurance coverage restrictions for a state.\"\n          operations:\n            - method: GET\n              name: get-insurance-coverage-by-state\n              description: \"Get insurance coverage for a state.\"\n\
  \              call: \"abortion-policy-api.get-insurance-coverage-by-state\"\n              with:\n                state: \"rest.state\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/minors/{state}\n          name: minors-state\n          description: \"Minors abortion restrictions for a state.\"\n          operations:\n            - method: GET\n              name: get-minors-by-state\n              description: \"Get minors restrictions for a state.\"\n              call: \"abortion-policy-api.get-minors-by-state\"\n              with:\n                state: \"rest.state\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/waiting-periods/{state}\n          name: waiting-periods-state\n          description: \"Waiting period restrictions for a state.\"\n          operations:\n            - method: GET\n              name: get-waiting-periods-by-state\n\
  \              description: \"Get waiting periods for a state.\"\n              call: \"abortion-policy-api.get-waiting-periods-by-state\"\n              with:\n                state: \"rest.state\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/all-states/gestational-limits\n          name: all-gestational-limits\n          description: \"Gestational limit policies for all states.\"\n          operations:\n            - method: GET\n              name: get-gestational-limits-all-states\n              description: \"Get gestational limits for all states.\"\n              call: \"abortion-policy-api.get-gestational-limits-all-states\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/all-states/insurance-coverage\n          name: all-insurance-coverage\n          description: \"Insurance coverage restrictions for all states.\"\n          operations:\n\
  \            - method: GET\n              name: get-insurance-coverage-all-states\n              description: \"Get insurance coverage for all states.\"\n              call: \"abortion-policy-api.get-insurance-coverage-all-states\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/all-states/minors\n          name: all-minors\n          description: \"Minors restrictions for all states.\"\n          operations:\n            - method: GET\n              name: get-minors-all-states\n              description: \"Get minors restrictions for all states.\"\n              call: \"abortion-policy-api.get-minors-all-states\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/all-states/waiting-periods\n          name: all-waiting-periods\n          description: \"Waiting period restrictions for all states.\"\n          operations:\n            - method: GET\n\
  \              name: get-waiting-periods-all-states\n              description: \"Get waiting periods for all states.\"\n              call: \"abortion-policy-api.get-waiting-periods-all-states\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: abortion-policy-lookup-mcp\n      transport: http\n      description: \"MCP server for AI-assisted abortion policy lookups for healthcare and patient advocacy applications.\"\n      tools:\n        - name: lookup-gestational-limits\n          description: \"Look up abortion gestational limit policy for a specific US state or zip code.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abortion-policy-api.get-gestational-limits-by-state\"\n          with:\n            state: \"tools.state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-gestational-limits-zip\n\
  \          description: \"Look up abortion gestational limit policy for a specific zip code.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abortion-policy-api.get-gestational-limits-by-zip\"\n          with:\n            zip: \"tools.zip\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-insurance-coverage\n          description: \"Look up abortion insurance coverage restrictions for a specific US state.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abortion-policy-api.get-insurance-coverage-by-state\"\n          with:\n            state: \"tools.state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-insurance-coverage-zip\n          description: \"Look up abortion insurance coverage restrictions for a specific zip code.\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: false\n          call: \"abortion-policy-api.get-insurance-coverage-by-zip\"\n          with:\n            zip: \"tools.zip\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-minors-restrictions\n          description: \"Look up abortion restrictions for minors in a specific US state.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abortion-policy-api.get-minors-by-state\"\n          with:\n            state: \"tools.state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-minors-restrictions-zip\n          description: \"Look up abortion restrictions for minors in a specific zip code.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abortion-policy-api.get-minors-by-zip\"\n          with:\n            zip: \"tools.zip\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: lookup-waiting-periods\n          description: \"Look up abortion waiting period requirements for a specific US state.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abortion-policy-api.get-waiting-periods-by-state\"\n          with:\n            state: \"tools.state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-waiting-periods-zip\n          description: \"Look up abortion waiting period requirements for a specific zip code.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abortion-policy-api.get-waiting-periods-by-zip\"\n          with:\n            zip: \"tools.zip\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-all-gestational-limits\n          description: \"List abortion gestational\
  \ limit policies for all US states.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abortion-policy-api.get-gestational-limits-all-states\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-all-insurance-coverage\n          description: \"List abortion insurance coverage restrictions for all US states.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abortion-policy-api.get-insurance-coverage-all-states\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-all-minors-restrictions\n          description: \"List abortion restrictions for minors across all US states.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abortion-policy-api.get-minors-all-states\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: list-all-waiting-periods\n          description: \"List abortion waiting period restrictions across all US states.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"abortion-policy-api.get-waiting-periods-all-states\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/abortion-policy-api/refs/heads/main/capabilities/abortion-policy-lookup.yaml
tags:
- Abortion Policy
- Healthcare
- Government Data
- Patient Advocacy
tools:
- description: Look up abortion gestational limit policy for a specific US state or zip code.
  hints:
    openWorld: false
    readOnly: true
  name: lookup-gestational-limits
- description: Look up abortion gestational limit policy for a specific zip code.
  hints:
    openWorld: false
    readOnly: true
  name: lookup-gestational-limits-zip
- description: Look up abortion insurance coverage restrictions for a specific US state.
  hints:
    openWorld: false
    readOnly: true
  name: lookup-insurance-coverage
- description: Look up abortion insurance coverage restrictions for a specific zip code.
  hints:
    openWorld: false
    readOnly: true
  name: lookup-insurance-coverage-zip
- description: Look up abortion restrictions for minors in a specific US state.
  hints:
    openWorld: false
    readOnly: true
  name: lookup-minors-restrictions
- description: Look up abortion restrictions for minors in a specific zip code.
  hints:
    openWorld: false
    readOnly: true
  name: lookup-minors-restrictions-zip
- description: Look up abortion waiting period requirements for a specific US state.
  hints:
    openWorld: false
    readOnly: true
  name: lookup-waiting-periods
- description: Look up abortion waiting period requirements for a specific zip code.
  hints:
    openWorld: false
    readOnly: true
  name: lookup-waiting-periods-zip
- description: List abortion gestational limit policies for all US states.
  hints:
    openWorld: false
    readOnly: true
  name: list-all-gestational-limits
- description: List abortion insurance coverage restrictions for all US states.
  hints:
    openWorld: false
    readOnly: true
  name: list-all-insurance-coverage
- description: List abortion restrictions for minors across all US states.
  hints:
    openWorld: false
    readOnly: true
  name: list-all-minors-restrictions
- description: List abortion waiting period restrictions across all US states.
  hints:
    openWorld: false
    readOnly: true
  name: list-all-waiting-periods
---
