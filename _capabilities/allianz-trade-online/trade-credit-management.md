---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Trade Credit Management
operations: []
personas: []
provider_name: Allianz Trade
provider_slug: allianz-trade-online
search_terms:
- credit insurance
- trade credit
- risk management
- insurance
- e-commerce
- surety
slug: trade-credit-management
source_filename: trade-credit-management.yaml
source_heading: Capability Spec
source_yaml: "name: Trade Credit Management\ndescription: >-\n  Workflow capability composition for end-to-end trade credit insurance management\n  using the Allianz Trade APIs. Supports the complete credit risk lifecycle from\n  policy management through overdue reporting and claims declaration.\nversion: 1.0.0\ncapabilities:\n  - shared/payment-overdues.yaml\n  - shared/company-grade.yaml\n  - shared/claims.yaml\n  - shared/policy.yaml\nworkflows:\n  - id: credit-risk-monitoring\n    name: Credit Risk Monitoring\n    description: Monitor buyer creditworthiness and respond to payment defaults\n    steps:\n      - step: grade-buyer\n        capability: company-grade\n        operation: requestCompanyGrade\n        description: Request creditworthiness grade for a buyer\n      - step: poll-grade-job\n        capability: company-grade\n        operation: getJobStatus\n        description: Wait for grade assessment to complete\n      - step: report-overdue\n        capability: payment-overdues\n\
  \        operation: reportOverdue\n        description: Report payment default using OVD category code\n      - step: poll-overdue-job\n        capability: payment-overdues\n        operation: getJobStatus\n        description: Wait for overdue report to be processed\n  - id: claims-declaration\n    name: Claims Declaration\n    description: Declare an insurance claim after payment default\n    steps:\n      - step: verify-overdue\n        capability: payment-overdues\n        operation: getOverdue\n        description: Retrieve overdue record to reference in claim\n      - step: submit-claim\n        capability: claims\n        operation: submitClaim\n        description: Submit insurance claim referencing the overdue\n      - step: poll-claim-job\n        capability: claims\n        operation: getJobStatus\n        description: Wait for claim submission to be processed\n      - step: track-claim\n        capability: claims\n        operation: getClaim\n        description: Monitor claim\
  \ status through resolution\n  - id: policy-onboarding\n    name: Policy Onboarding\n    description: Onboard subsidiaries as joint insureds under a policy\n    steps:\n      - step: list-policies\n        capability: policy\n        operation: listPolicies\n        description: Retrieve the policy portfolio\n      - step: add-joint-insured\n        capability: policy\n        operation: addJointInsured\n        description: Add subsidiary as joint insured\n      - step: poll-joint-insured-job\n        capability: policy\n        operation: getJobStatus\n        description: Wait for joint insured registration to complete\ntools:\n  - id: list-overdues\n    capability: payment-overdues\n    operation: listOverdues\n    description: Retrieve paginated payment overdues list\n  - id: report-overdue\n    capability: payment-overdues\n    operation: reportOverdue\n    description: Report a new payment default to Allianz Trade\n  - id: get-company-grade\n    capability: company-grade\n    operation:\
  \ getCompanyGrade\n    description: Retrieve a company creditworthiness grade\n  - id: request-grade\n    capability: company-grade\n    operation: requestCompanyGrade\n    description: Request a new company credit grade\n  - id: list-claims\n    capability: claims\n    operation: listClaims\n    description: Retrieve paginated insurance claims list\n  - id: submit-claim\n    capability: claims\n    operation: submitClaim\n    description: Submit a new insurance claim\n  - id: list-policies\n    capability: policy\n    operation: listPolicies\n    description: Retrieve paginated policy portfolio\n  - id: add-joint-insured\n    capability: policy\n    operation: addJointInsured\n    description: Add a joint insured to a policy\nrest_port: 8080\nmcp_port: 9090\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/allianz-trade-online/refs/heads/main/capabilities/trade-credit-management.yaml
tags: []
tools: []
---
