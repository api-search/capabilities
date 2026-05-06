---
categories: []
consumed_apis: []
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
- list all minors restrictions
- gestational limit policies for all states.
- get gestational limit policy for a zip code.
- list all waiting periods
- get waiting periods for all states.
- unified workflow for looking up us state abortion policies across all four data tables
- legal aid organizations advising clients on state abortion law
- look up abortion insurance coverage restrictions for a specific zip code.
- insurance coverage restrictions for all states.
- get gestational limits all states
- list abortion gestational limit policies for all us states.
- list abortion waiting period restrictions across all us states.
- lookup waiting periods zip
- lookup insurance coverage
- Patient Advocate
- get waiting periods by state
- government
- healthcare
- look up abortion restrictions for minors in a specific zip code.
- lookup gestational limits zip
- get minors all states
- get insurance coverage for a state.
- insurance coverage restrictions for a state.
- get minors restrictions for a state.
- abortion policy
- developers building conversational tools that answer abortion policy questions
- get gestational limits by state
- look up abortion waiting period requirements for a specific us state.
- waiting period restrictions for all states.
- look up abortion restrictions for minors in a specific us state.
- lookup waiting periods
- get insurance coverage for all states.
- minors abortion restrictions for a state.
- get waiting periods for a state.
- get minors by state
- government data
- look up abortion gestational limit policy for a specific us state or zip code.
- all abortion policies for a specific zip code.
- Healthcare Provider
- look up abortion waiting period requirements for a specific zip code.
- lookup gestational limits
- Chatbot Developer
- advocates helping patients understand abortion access options in their state
- us state laws governing abortion access including gestational limits, insurance, minors, and waiting periods
- get gestational limits by zip
- get gestational limits for a state.
- get waiting periods all states
- list abortion insurance coverage restrictions for all us states.
- patient advocacy
- lookup minors restrictions zip
- gestational limit policy for a state.
- lookup insurance coverage zip
- list abortion restrictions for minors across all us states.
- Legal Aid
- list all gestational limits
- abortion
- get insurance coverage all states
- minors restrictions for all states.
- get gestational limits for all states.
- look up abortion insurance coverage restrictions for a specific us state.
- get insurance coverage by state
- policies
- get gestational limit policy for a state.
- get minors restrictions for all states.
- all abortion policies for a specific state.
- list all insurance coverage
- medical providers advising patients on state-specific abortion access restrictions
- look up abortion gestational limit policy for a specific zip code.
- lookup minors restrictions
- waiting period restrictions for a state.
slug: abortion-policy-lookup
source_filename: abortion-policy-lookup.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Abortion Policy Lookup\n  description: Unified workflow for looking up US state abortion policies across gestational limits, insurance coverage, minors\n    restrictions, and waiting periods. Designed for healthcare providers, patient advocates, chatbots, and legal aid organizations\n    needing comprehensive state-specific abortion access information.\n  tags:\n  - Abortion Policy\n  - Healthcare\n  - Government Data\n  - Patient Advocacy\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ABORTION_POLICY_API_TOKEN: ABORTION_POLICY_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: abortion-policy-api\n    baseUri: https://api.abortionpolicyapi.com/v1\n    description: Abortion Policy API providing US state abortion law data.\n    authentication:\n      type: apikey\n      key: token\n      value: '{{ABORTION_POLICY_API_TOKEN}}'\n      placement: header\n    resources:\n    - name:\
  \ gestational-limits\n      path: /gestational_limits\n      description: Gestational limit abortion policies by state or zip code.\n      operations:\n      - name: get-gestational-limits-all-states\n        method: GET\n        description: Get gestational limits for all US states.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-gestational-limits-by-state\n        method: GET\n        description: Get gestational limits for a specific US state.\n        inputParameters:\n        - name: state\n          in: path\n          type: string\n          required: true\n          description: State name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-gestational-limits-by-zip\n        method: GET\n        description: Get gestational limits for a specific zip code.\n        inputParameters:\n     \
  \   - name: zip\n          in: path\n          type: string\n          required: true\n          description: 5-digit zip code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insurance-coverage\n      path: /insurance_coverage\n      description: Abortion insurance coverage restrictions by state or zip code.\n      operations:\n      - name: get-insurance-coverage-all-states\n        method: GET\n        description: Get insurance coverage restrictions for all US states.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-insurance-coverage-by-state\n        method: GET\n        description: Get insurance coverage restrictions for a specific US state.\n        inputParameters:\n        - name: state\n          in: path\n          type: string\n          required: true\n          description: State name\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-insurance-coverage-by-zip\n        method: GET\n        description: Get insurance coverage restrictions for a specific zip code.\n        inputParameters:\n        - name: zip\n          in: path\n          type: string\n          required: true\n          description: 5-digit zip code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: minors\n      path: /minors\n      description: Abortion restrictions targeting minors by state or zip code.\n      operations:\n      - name: get-minors-all-states\n        method: GET\n        description: Get minors abortion restrictions for all US states.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-minors-by-state\n  \
  \      method: GET\n        description: Get minors abortion restrictions for a specific US state.\n        inputParameters:\n        - name: state\n          in: path\n          type: string\n          required: true\n          description: State name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-minors-by-zip\n        method: GET\n        description: Get minors abortion restrictions for a specific zip code.\n        inputParameters:\n        - name: zip\n          in: path\n          type: string\n          required: true\n          description: 5-digit zip code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: waiting-periods\n      path: /waiting_periods\n      description: Abortion waiting period restrictions by state or zip code.\n      operations:\n      - name: get-waiting-periods-all-states\n\
  \        method: GET\n        description: Get waiting period restrictions for all US states.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-waiting-periods-by-state\n        method: GET\n        description: Get waiting period restrictions for a specific US state.\n        inputParameters:\n        - name: state\n          in: path\n          type: string\n          required: true\n          description: State name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-waiting-periods-by-zip\n        method: GET\n        description: Get waiting period restrictions for a specific zip code.\n        inputParameters:\n        - name: zip\n          in: path\n          type: string\n          required: true\n          description: 5-digit zip code\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: abortion-policy-lookup-api\n    description: Unified REST API for comprehensive abortion policy lookups by state or zip code.\n    resources:\n    - path: /v1/policies/{state}\n      name: state-policies\n      description: All abortion policies for a specific state.\n      operations:\n      - method: GET\n        name: get-gestational-limits-by-state\n        description: Get gestational limit policy for a state.\n        call: abortion-policy-api.get-gestational-limits-by-state\n        with:\n          state: rest.state\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies/zip/{zip}\n      name: zip-policies\n      description: All abortion policies for a specific zip code.\n      operations:\n      - method: GET\n        name: get-gestational-limits-by-zip\n        description: Get gestational limit policy for\
  \ a zip code.\n        call: abortion-policy-api.get-gestational-limits-by-zip\n        with:\n          zip: rest.zip\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gestational-limits/{state}\n      name: gestational-limits-state\n      description: Gestational limit policy for a state.\n      operations:\n      - method: GET\n        name: get-gestational-limits-by-state\n        description: Get gestational limits for a state.\n        call: abortion-policy-api.get-gestational-limits-by-state\n        with:\n          state: rest.state\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/insurance-coverage/{state}\n      name: insurance-coverage-state\n      description: Insurance coverage restrictions for a state.\n      operations:\n      - method: GET\n        name: get-insurance-coverage-by-state\n        description: Get insurance coverage for a state.\n        call: abortion-policy-api.get-insurance-coverage-by-state\n\
  \        with:\n          state: rest.state\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/minors/{state}\n      name: minors-state\n      description: Minors abortion restrictions for a state.\n      operations:\n      - method: GET\n        name: get-minors-by-state\n        description: Get minors restrictions for a state.\n        call: abortion-policy-api.get-minors-by-state\n        with:\n          state: rest.state\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/waiting-periods/{state}\n      name: waiting-periods-state\n      description: Waiting period restrictions for a state.\n      operations:\n      - method: GET\n        name: get-waiting-periods-by-state\n        description: Get waiting periods for a state.\n        call: abortion-policy-api.get-waiting-periods-by-state\n        with:\n          state: rest.state\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/all-states/gestational-limits\n      name: all-gestational-limits\n      description: Gestational limit policies for all states.\n      operations:\n      - method: GET\n        name: get-gestational-limits-all-states\n        description: Get gestational limits for all states.\n        call: abortion-policy-api.get-gestational-limits-all-states\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/all-states/insurance-coverage\n      name: all-insurance-coverage\n      description: Insurance coverage restrictions for all states.\n      operations:\n      - method: GET\n        name: get-insurance-coverage-all-states\n        description: Get insurance coverage for all states.\n        call: abortion-policy-api.get-insurance-coverage-all-states\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/all-states/minors\n      name: all-minors\n      description: Minors restrictions for all states.\n\
  \      operations:\n      - method: GET\n        name: get-minors-all-states\n        description: Get minors restrictions for all states.\n        call: abortion-policy-api.get-minors-all-states\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/all-states/waiting-periods\n      name: all-waiting-periods\n      description: Waiting period restrictions for all states.\n      operations:\n      - method: GET\n        name: get-waiting-periods-all-states\n        description: Get waiting periods for all states.\n        call: abortion-policy-api.get-waiting-periods-all-states\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: abortion-policy-lookup-mcp\n    transport: http\n    description: MCP server for AI-assisted abortion policy lookups for healthcare and patient advocacy applications.\n    tools:\n    - name: lookup-gestational-limits\n      description: Look up abortion gestational\
  \ limit policy for a specific US state or zip code.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abortion-policy-api.get-gestational-limits-by-state\n      with:\n        state: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-gestational-limits-zip\n      description: Look up abortion gestational limit policy for a specific zip code.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abortion-policy-api.get-gestational-limits-by-zip\n      with:\n        zip: tools.zip\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-insurance-coverage\n      description: Look up abortion insurance coverage restrictions for a specific US state.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abortion-policy-api.get-insurance-coverage-by-state\n      with:\n        state: tools.state\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: lookup-insurance-coverage-zip\n      description: Look up abortion insurance coverage restrictions for a specific zip code.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abortion-policy-api.get-insurance-coverage-by-zip\n      with:\n        zip: tools.zip\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-minors-restrictions\n      description: Look up abortion restrictions for minors in a specific US state.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abortion-policy-api.get-minors-by-state\n      with:\n        state: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-minors-restrictions-zip\n      description: Look up abortion restrictions for minors in a specific zip code.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abortion-policy-api.get-minors-by-zip\n      with:\n\
  \        zip: tools.zip\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-waiting-periods\n      description: Look up abortion waiting period requirements for a specific US state.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abortion-policy-api.get-waiting-periods-by-state\n      with:\n        state: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-waiting-periods-zip\n      description: Look up abortion waiting period requirements for a specific zip code.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abortion-policy-api.get-waiting-periods-by-zip\n      with:\n        zip: tools.zip\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-all-gestational-limits\n      description: List abortion gestational limit policies for all US states.\n      hints:\n        readOnly: true\n        openWorld: false\n \
  \     call: abortion-policy-api.get-gestational-limits-all-states\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-all-insurance-coverage\n      description: List abortion insurance coverage restrictions for all US states.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abortion-policy-api.get-insurance-coverage-all-states\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-all-minors-restrictions\n      description: List abortion restrictions for minors across all US states.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abortion-policy-api.get-minors-all-states\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-all-waiting-periods\n      description: List abortion waiting period restrictions across all US states.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: abortion-policy-api.get-waiting-periods-all-states\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
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
