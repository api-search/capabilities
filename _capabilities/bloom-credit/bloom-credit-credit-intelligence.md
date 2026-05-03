---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Bloom Credit Credit Intelligence
operations: []
personas: []
provider_name: Bloom Credit
provider_slug: bloom-credit
search_terms:
- credit scores
- credit reports
- credit bureau
- fintech
- lending
- personal finance
slug: bloom-credit-credit-intelligence
source_filename: bloom-credit-credit-intelligence.yaml
source_heading: Capability Spec
source_yaml: "name: Bloom Credit Credit Intelligence\ndescription: >-\n  End-to-end credit intelligence capability for fintech applications, lenders,\n  and financial services platforms. Enables consumer registration, tri-bureau\n  credit report retrieval, score analysis, trade line inspection, and real-time\n  credit monitoring with webhook alerts.\nversion: \"1.0\"\npersona:\n  - Fintech Developers\n  - Lenders and Underwriters\n  - Credit Counselors\n  - Consumer Finance Apps\nservers:\n  rest:\n    url: http://localhost:8080\n    protocol: rest\n  mcp:\n    url: http://localhost:9090\n    protocol: mcp\ntools:\n  - name: create-consumer\n    operationId: create-consumer\n    source:\n      capability: capabilities/shared/bloom-credit-api.yaml\n    description: Register a consumer for credit data access.\n  - name: get-consumer\n    operationId: get-consumer\n    source:\n      capability: capabilities/shared/bloom-credit-api.yaml\n    description: Retrieve a consumer's profile and status.\n\
  \  - name: get-credit-reports\n    operationId: get-credit-reports\n    source:\n      capability: capabilities/shared/bloom-credit-api.yaml\n    description: Pull full credit reports from Equifax, Experian, and/or TransUnion.\n  - name: get-credit-scores\n    operationId: get-credit-scores\n    source:\n      capability: capabilities/shared/bloom-credit-api.yaml\n    description: Retrieve FICO or VantageScore credit scores from one or more bureaus.\n  - name: get-trade-lines\n    operationId: get-trade-lines\n    source:\n      capability: capabilities/shared/bloom-credit-api.yaml\n    description: Retrieve individual account and trade line data for credit analysis.\n  - name: enroll-monitoring\n    operationId: enroll-monitoring\n    source:\n      capability: capabilities/shared/bloom-credit-api.yaml\n    description: Enroll a consumer in credit monitoring to receive real-time alerts.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bloom-credit/refs/heads/main/capabilities/bloom-credit-credit-intelligence.yaml
tags: []
tools: []
---
