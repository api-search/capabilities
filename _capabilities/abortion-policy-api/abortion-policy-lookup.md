---
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
- lookup gestational limits zip
- gestational limit policies for all states.
- get gestational limits for all states.
- insurance coverage restrictions for a state.
- get gestational limits by state
- get insurance coverage for a state.
- list abortion waiting period restrictions across all us states.
- get gestational limits by zip
- list all waiting periods
- get waiting periods all states
- gestational limit policy for a state.
- lookup waiting periods zip
- list all insurance coverage
- us state laws governing abortion access including gestational limits, insurance, minors, and waiting periods
- lookup gestational limits
- get waiting periods by state
- look up abortion insurance coverage restrictions for a specific us state.
- lookup minors restrictions
- lookup insurance coverage zip
- get insurance coverage for all states.
- abortion
- Patient Advocate
- Legal Aid
- lookup minors restrictions zip
- all abortion policies for a specific state.
- lookup insurance coverage
- insurance coverage restrictions for all states.
- get insurance coverage by state
- get waiting periods for a state.
- look up abortion gestational limit policy for a specific us state or zip code.
- minors restrictions for all states.
- waiting period restrictions for all states.
- list abortion insurance coverage restrictions for all us states.
- get gestational limits all states
- government data
- minors abortion restrictions for a state.
- get minors all states
- get waiting periods for all states.
- Healthcare Provider
- abortion policy
- get gestational limit policy for a zip code.
- waiting period restrictions for a state.
- list abortion restrictions for minors across all us states.
- look up abortion gestational limit policy for a specific zip code.
- list all gestational limits
- look up abortion waiting period requirements for a specific zip code.
- unified workflow for looking up us state abortion policies across all four data tables
- government
- legal aid organizations advising clients on state abortion law
- patient advocacy
- look up abortion restrictions for minors in a specific us state.
- look up abortion restrictions for minors in a specific zip code.
- list all minors restrictions
- lookup waiting periods
- get minors by state
- all abortion policies for a specific zip code.
- get insurance coverage all states
- advocates helping patients understand abortion access options in their state
- get gestational limits for a state.
- developers building conversational tools that answer abortion policy questions
- policies
- list abortion gestational limit policies for all us states.
- Chatbot Developer
- get minors restrictions for all states.
- look up abortion waiting period requirements for a specific us state.
- get gestational limit policy for a state.
- get minors restrictions for a state.
- healthcare
- medical providers advising patients on state-specific abortion access restrictions
- look up abortion insurance coverage restrictions for a specific zip code.
slug: abortion-policy-lookup
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
