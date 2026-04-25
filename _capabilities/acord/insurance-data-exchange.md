---
consumed_apis:
- acord-ngds
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
- issue a new acord-compliant insurance policy
- submit a first notice of loss
- submit an insurance application for underwriting review using acord ngds
- register a new insurance party in the acord ngds party registry
- risk assessment and policy issuance decision workflows
- individual claim operations
- update policy
- underwriting
- list registered parties
- Insurance Carrier
- retrieve full acord claim details including reserves and payment history
- reinsurance company accessing cedant data for risk assessment and settlement
- acord
- list insurance parties (insureds, agents, brokers, carriers) from acord registry
- full lifecycle management of insurance policies from issuance to expiration
- register a new party
- claims
- claims intake and inquiry
- registry of all insurance parties including insureds, agents, and carriers
- get claim
- list parties
- apply endorsements or amendments to an acord policy
- policy administration
- create policy
- underwriting application submission
- insurance
- submit claim
- list claims with filtering
- standards
- list insurance claims with acord ngds filtering by policy, status, and loss date range
- get policy
- first notice of loss, reserves, and payment tracking for insurance claims
- submit underwriting
- Broker
- submit an application for underwriting review
- get full policy details
- primary insurer managing policy issuance, claims, and underwriting
- list claims
- create party
- list policies
- unified acord ngds workflow for policy, claims, party, and underwriting
- Reinsurer
- retrieve full acord policy details including coverages and insured party
- issue a new insurance policy
- insurance party registry
- intermediary managing client policies, claims submissions, and party records
- policy
- list policies with filtering
- individual policy operations
- insurance policy lifecycle management
- get claim details and payment history
- endorse or amend a policy
- claims management
- list insurance policies using acord ngds standards with filtering by number, line of business, and status
- submit a first notice of loss (fnol) using acord ngds claims transaction model
slug: insurance-data-exchange
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
