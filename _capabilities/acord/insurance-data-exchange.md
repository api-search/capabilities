---
categories: []
consumed_apis: []
description: Unified insurance data exchange workflow for policy administration, claims management, party registry, and underwriting using ACORD Next-Generation Digital Standards (NGDS). Used by insurance carriers, brokers, and reinsurers to automate policy lifecycle, claims processing, and underwriting workflows.
layout: capability
name: ACORD Insurance Data Exchange
operations:
- description: List policies with filtering
  method: GET
  name: list-policies
  path: /v1/policies
- description: Issue a new insurance policy
  method: POST
  name: create-policy
  path: /v1/policies
- description: Get full policy details
  method: GET
  name: get-policy
  path: /v1/policies/{policyId}
- description: Endorse or amend a policy
  method: PATCH
  name: update-policy
  path: /v1/policies/{policyId}
- description: List claims with filtering
  method: GET
  name: list-claims
  path: /v1/claims
- description: Submit a first notice of loss
  method: POST
  name: submit-claim
  path: /v1/claims
- description: Get claim details and payment history
  method: GET
  name: get-claim
  path: /v1/claims/{claimId}
- description: List registered parties
  method: GET
  name: list-parties
  path: /v1/parties
- description: Register a new party
  method: POST
  name: create-party
  path: /v1/parties
- description: Submit an application for underwriting review
  method: POST
  name: submit-underwriting
  path: /v1/underwriting/submissions
personas: []
provider_name: ACORD
provider_slug: acord
search_terms:
- underwriting application submission
- list policies
- submit a first notice of loss
- insurance party registry
- list insurance parties (insureds, agents, brokers, carriers) from acord registry
- get claim details and payment history
- submit underwriting
- submit an application for underwriting review
- full lifecycle management of insurance policies from issuance to expiration
- claims intake and inquiry
- list insurance claims with acord ngds filtering by policy, status, and loss date range
- list policies with filtering
- registry of all insurance parties including insureds, agents, and carriers
- reinsurance company accessing cedant data for risk assessment and settlement
- risk assessment and policy issuance decision workflows
- claims management
- insurance
- individual policy operations
- unified acord ngds workflow for policy, claims, party, and underwriting
- get full policy details
- intermediary managing client policies, claims submissions, and party records
- primary insurer managing policy issuance, claims, and underwriting
- first notice of loss, reserves, and payment tracking for insurance claims
- standards
- list claims
- Broker
- get claim
- retrieve full acord claim details including reserves and payment history
- Reinsurer
- submit an insurance application for underwriting review using acord ngds
- issue a new acord-compliant insurance policy
- issue a new insurance policy
- list parties
- acord
- submit claim
- create policy
- submit a first notice of loss (fnol) using acord ngds claims transaction model
- policy administration
- endorse or amend a policy
- list insurance policies using acord ngds standards with filtering by number, line of business, and status
- Insurance Carrier
- update policy
- list registered parties
- list claims with filtering
- apply endorsements or amendments to an acord policy
- individual claim operations
- create party
- get policy
- policy
- claims
- retrieve full acord policy details including coverages and insured party
- underwriting
- insurance policy lifecycle management
- register a new insurance party in the acord ngds party registry
- register a new party
slug: insurance-data-exchange
source_filename: insurance-data-exchange.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ACORD Insurance Data Exchange\n  description: Unified insurance data exchange workflow for policy administration, claims management, party registry, and\n    underwriting using ACORD Next-Generation Digital Standards (NGDS). Used by insurance carriers, brokers, and reinsurers\n    to automate policy lifecycle, claims processing, and underwriting workflows.\n  tags:\n  - ACORD\n  - Claims Management\n  - Insurance\n  - Policy Administration\n  - Standards\n  - Underwriting\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ACORD_BEARER_TOKEN: ACORD_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: acord-ngds\n    baseUri: https://api.insurer-internal.example.com/ngds\n    description: ACORD NGDS REST API for insurance data exchange\n    authentication:\n      type: bearer\n      token: '{{ACORD_BEARER_TOKEN}}'\n    resources:\n    - name: policies\n      path: /policies\n    \
  \  description: Insurance policy administration and management\n      operations:\n      - name: list-policies\n        method: GET\n        description: List policies with filtering by number, insured party, line of business, and status\n        inputParameters:\n        - name: policyNumber\n          in: query\n          type: string\n          required: false\n          description: Filter by policy number\n        - name: insuredPartyId\n          in: query\n          type: string\n          required: false\n          description: Filter by insured party identifier\n        - name: lineOfBusiness\n          in: query\n          type: string\n          required: false\n          description: Filter by line of business\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by policy status\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page\
  \ number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-policy\n        method: POST\n        description: Submit a new insurance policy for underwriting and issuance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            lineOfBusiness: '{{tools.lineOfBusiness}}'\n            effectiveDate: '{{tools.effectiveDate}}'\n            expirationDate: '{{tools.expirationDate}}'\n            premiumAmount: '{{tools.premiumAmount}}'\n    - name: policy-by-id\n      path: /policies/{policyId}\n      description: Single policy operations\n      operations:\n      - name: get-policy\n        method: GET\n        description:\
  \ Retrieve a single insurance policy by ID with all coverage details\n        inputParameters:\n        - name: policyId\n          in: path\n          type: string\n          required: true\n          description: Policy identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-policy\n        method: PATCH\n        description: Apply endorsements or amendments to an existing policy\n        inputParameters:\n        - name: policyId\n          in: path\n          type: string\n          required: true\n          description: Policy identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            expirationDate: '{{tools.expirationDate}}'\n    - name: claims\n      path: /claims\n      description: Insurance\
  \ claims inquiry and first notice of loss\n      operations:\n      - name: list-claims\n        method: GET\n        description: List claims with filtering by policy, status, or date range\n        inputParameters:\n        - name: policyId\n          in: query\n          type: string\n          required: false\n          description: Filter by policy identifier\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by claim status\n        - name: lossDateFrom\n          in: query\n          type: string\n          required: false\n          description: Loss date range start\n        - name: lossDateTo\n          in: query\n          type: string\n          required: false\n          description: Loss date range end\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-claim\n        method: POST\n        description:\
  \ Submit a first notice of loss (FNOL) using ACORD NGDS claims model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            policyId: '{{tools.policyId}}'\n            lossDate: '{{tools.lossDate}}'\n            lossDescription: '{{tools.lossDescription}}'\n    - name: claim-by-id\n      path: /claims/{claimId}\n      description: Single claim retrieval\n      operations:\n      - name: get-claim\n        method: GET\n        description: Retrieve full claim details including reserves and payment history\n        inputParameters:\n        - name: claimId\n          in: path\n          type: string\n          required: true\n          description: Claim identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: parties\n      path: /parties\n      description:\
  \ Insurance party registry (insureds, agents, brokers, carriers)\n      operations:\n      - name: list-parties\n        method: GET\n        description: List parties with optional filtering by type and name\n        inputParameters:\n        - name: partyType\n          in: query\n          type: string\n          required: false\n          description: Filter by party type\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-party\n        method: POST\n        description: Register a new party using the ACORD NGDS Party object model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            partyType: '{{tools.partyType}}'\n\
  \            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n    - name: underwriting\n      path: /underwriting/submissions\n      description: Underwriting application submission\n      operations:\n      - name: submit-underwriting\n        method: POST\n        description: Submit an insurance application for underwriting review\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            lineOfBusiness: '{{tools.lineOfBusiness}}'\n            requestedEffectiveDate: '{{tools.effectiveDate}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: acord-insurance-api\n    description: Unified REST API for ACORD-compliant insurance data exchange.\n    resources:\n    - path: /v1/policies\n      name: policies\n      description: Insurance policy lifecycle management\n      operations:\n      - method: GET\n        name:\
  \ list-policies\n        description: List policies with filtering\n        call: acord-ngds.list-policies\n        with:\n          policyNumber: rest.policyNumber\n          lineOfBusiness: rest.lineOfBusiness\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-policy\n        description: Issue a new insurance policy\n        call: acord-ngds.create-policy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies/{policyId}\n      name: policy\n      description: Individual policy operations\n      operations:\n      - method: GET\n        name: get-policy\n        description: Get full policy details\n        call: acord-ngds.get-policy\n        with:\n          policyId: rest.policyId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-policy\n        description: Endorse or amend\
  \ a policy\n        call: acord-ngds.update-policy\n        with:\n          policyId: rest.policyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/claims\n      name: claims\n      description: Claims intake and inquiry\n      operations:\n      - method: GET\n        name: list-claims\n        description: List claims with filtering\n        call: acord-ngds.list-claims\n        with:\n          policyId: rest.policyId\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: submit-claim\n        description: Submit a first notice of loss\n        call: acord-ngds.submit-claim\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/claims/{claimId}\n      name: claim\n      description: Individual claim operations\n      operations:\n      - method: GET\n        name: get-claim\n        description: Get claim details and payment\
  \ history\n        call: acord-ngds.get-claim\n        with:\n          claimId: rest.claimId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/parties\n      name: parties\n      description: Insurance party registry\n      operations:\n      - method: GET\n        name: list-parties\n        description: List registered parties\n        call: acord-ngds.list-parties\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-party\n        description: Register a new party\n        call: acord-ngds.create-party\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/underwriting/submissions\n      name: underwriting\n      description: Underwriting application submission\n      operations:\n      - method: POST\n        name: submit-underwriting\n        description: Submit an application for underwriting review\n        call: acord-ngds.submit-underwriting\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: acord-insurance-mcp\n    transport: http\n    description: MCP server for AI-assisted ACORD insurance data exchange workflows.\n    tools:\n    - name: list-policies\n      description: List insurance policies using ACORD NGDS standards with filtering by number, line of business, and status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: acord-ngds.list-policies\n      with:\n        policyNumber: tools.policyNumber\n        lineOfBusiness: tools.lineOfBusiness\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-policy\n      description: Issue a new ACORD-compliant insurance policy\n      hints:\n        readOnly: false\n        idempotent: false\n      call: acord-ngds.create-policy\n      with:\n        lineOfBusiness: tools.lineOfBusiness\n        effectiveDate: tools.effectiveDate\n\
  \        expirationDate: tools.expirationDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-policy\n      description: Retrieve full ACORD policy details including coverages and insured party\n      hints:\n        readOnly: true\n        idempotent: true\n      call: acord-ngds.get-policy\n      with:\n        policyId: tools.policyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-policy\n      description: Apply endorsements or amendments to an ACORD policy\n      hints:\n        readOnly: false\n        idempotent: true\n      call: acord-ngds.update-policy\n      with:\n        policyId: tools.policyId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-claims\n      description: List insurance claims with ACORD NGDS filtering by policy, status, and loss date range\n      hints:\n        readOnly: true\n        openWorld: true\n      call:\
  \ acord-ngds.list-claims\n      with:\n        policyId: tools.policyId\n        status: tools.status\n        lossDateFrom: tools.lossDateFrom\n        lossDateTo: tools.lossDateTo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-claim\n      description: Submit a first notice of loss (FNOL) using ACORD NGDS claims transaction model\n      hints:\n        readOnly: false\n        idempotent: false\n      call: acord-ngds.submit-claim\n      with:\n        policyId: tools.policyId\n        lossDate: tools.lossDate\n        lossDescription: tools.lossDescription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-claim\n      description: Retrieve full ACORD claim details including reserves and payment history\n      hints:\n        readOnly: true\n        idempotent: true\n      call: acord-ngds.get-claim\n      with:\n        claimId: tools.claimId\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: list-parties\n      description: List insurance parties (insureds, agents, brokers, carriers) from ACORD registry\n      hints:\n        readOnly: true\n        openWorld: true\n      call: acord-ngds.list-parties\n      with:\n        partyType: tools.partyType\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-party\n      description: Register a new insurance party in the ACORD NGDS party registry\n      hints:\n        readOnly: false\n        idempotent: false\n      call: acord-ngds.create-party\n      with:\n        partyType: tools.partyType\n        firstName: tools.firstName\n        lastName: tools.lastName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-underwriting\n      description: Submit an insurance application for underwriting review using ACORD NGDS\n      hints:\n        readOnly: false\n        idempotent: false\n      call: acord-ngds.submit-underwriting\n\
  \      with:\n        lineOfBusiness: tools.lineOfBusiness\n        requestedEffectiveDate: tools.effectiveDate\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/acord/refs/heads/main/capabilities/insurance-data-exchange.yaml
tags:
- ACORD
- Claims Management
- Insurance
- Policy Administration
- Standards
- Underwriting
tools:
- description: List insurance policies using ACORD NGDS standards with filtering by number, line of business, and status
  hints:
    openWorld: true
    readOnly: true
  name: list-policies
- description: Issue a new ACORD-compliant insurance policy
  hints:
    idempotent: false
    readOnly: false
  name: create-policy
- description: Retrieve full ACORD policy details including coverages and insured party
  hints:
    idempotent: true
    readOnly: true
  name: get-policy
- description: Apply endorsements or amendments to an ACORD policy
  hints:
    idempotent: true
    readOnly: false
  name: update-policy
- description: List insurance claims with ACORD NGDS filtering by policy, status, and loss date range
  hints:
    openWorld: true
    readOnly: true
  name: list-claims
- description: Submit a first notice of loss (FNOL) using ACORD NGDS claims transaction model
  hints:
    idempotent: false
    readOnly: false
  name: submit-claim
- description: Retrieve full ACORD claim details including reserves and payment history
  hints:
    idempotent: true
    readOnly: true
  name: get-claim
- description: List insurance parties (insureds, agents, brokers, carriers) from ACORD registry
  hints:
    openWorld: true
    readOnly: true
  name: list-parties
- description: Register a new insurance party in the ACORD NGDS party registry
  hints:
    idempotent: false
    readOnly: false
  name: create-party
- description: Submit an insurance application for underwriting review using ACORD NGDS
  hints:
    idempotent: false
    readOnly: false
  name: submit-underwriting
---
