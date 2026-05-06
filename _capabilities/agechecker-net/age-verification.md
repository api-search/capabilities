---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Age Verification
operations: []
personas:
- description: Regulatory compliance officer ensuring age verification requirements are met for restricted product sales.
  id: compliance-officer
  name: Compliance Officer
- description: Developer integrating age verification into online checkout flows for age-restricted products.
  id: e-commerce-developer
  name: E-Commerce Developer
provider_name: AgeChecker.Net
provider_slug: agechecker-net
search_terms:
- regulatory compliance officer ensuring age verification requirements are met for restricted product sales.
- tracking and auditing age verification session history.
- identity
- end-to-end age verification workflow for e-commerce businesses selling age-restricted products.
- age verification
- compliance
- compliance officer
- customer age verification for regulated product purchases.
- e-commerce
- developer integrating age verification into online checkout flows for age-restricted products.
- e commerce developer
- webhook-based real-time notifications for verification outcomes.
- regulatory
slug: age-verification
source_filename: age-verification.yaml
source_heading: Capability Spec
source_yaml: "name: Age Verification\ndescription: \"End-to-end age verification workflow for e-commerce businesses selling age-restricted products.\"\napisComposed:\n  - agechecker-net-age-verification-api\ntools:\n  - name: verify-customer-age\n    description: \"Verify a customer's age before allowing purchase of age-restricted products. Returns pass/fail and whether photo ID upload is required.\"\n    sharedTool: agechecker-net-age-verification-api/verify-age\n  - name: check-verification-status\n    description: \"Check the status of a pending age verification session to determine if the customer has completed photo ID upload.\"\n    sharedTool: agechecker-net-age-verification-api/get-verification-session\n  - name: list-recent-verifications\n    description: \"List recent verification sessions to audit age verification compliance for regulatory reporting.\"\n    sharedTool: agechecker-net-age-verification-api/list-verification-sessions\n  - name: setup-verification-webhook\n    description:\
  \ \"Configure webhook notifications to receive real-time alerts when age verification completes or fails.\"\n    sharedTool: agechecker-net-age-verification-api/configure-webhook\npersonas:\n  - compliance-officer\n  - e-commerce-developer\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/agechecker-net/refs/heads/main/capabilities/age-verification.yaml
tags: []
tools: []
---
