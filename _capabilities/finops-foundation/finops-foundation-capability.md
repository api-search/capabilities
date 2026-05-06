---
categories: []
consumed_apis: []
description: An API modeled on the FinOps Open Cost and Usage Specification (FOCUS) v1.3, which defines a standard schema for cloud, SaaS, and other technology billing data. FOCUS normalizes billing datasets across providers to reduce complexity for FinOps practitioners. This specification models the Cost and Usage dataset and the Contract Commitment dataset defined by the FOCUS standard, enabling programmatic access to FOCUS-compliant billing data. The FOCUS specification is maintained by the FinOps Foundation under the Linux Foundation.
layout: capability
name: FinOps Foundation FOCUS Cost and Usage API
operations:
- description: FinOps Foundation List cost and usage records
  method: GET
  name: listcostandusage
  path: /cost-and-usage
- description: FinOps Foundation Export cost and usage data
  method: POST
  name: exportcostandusage
  path: /cost-and-usage/export
- description: FinOps Foundation Get cost and usage export job status
  method: GET
  name: getcostandusageexportstatus
  path: /cost-and-usage/export/{jobId}
- description: FinOps Foundation List contract commitment records
  method: GET
  name: listcontractcommitments
  path: /contract-commitments
- description: FinOps Foundation Get FOCUS schema metadata
  method: GET
  name: getschemametadata
  path: /schema
personas: []
provider_name: FinOps Foundation
provider_slug: finops-foundation
search_terms:
- finops foundation get focus schema metadata
- listcontractcommitments
- finops foundation list contract commitment records
- costs
- api
- foundation
- finops foundation get cost and usage export job status
- getschemametadata
- finops foundation list cost and usage records
- finops
- listcostandusage
- budgets
- getcostandusageexportstatus
- finops foundation export cost and usage data
- exportcostandusage
slug: finops-foundation-capability
source_filename: finops-foundation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FinOps Foundation FOCUS Cost and Usage API\n  description: An API modeled on the FinOps Open Cost and Usage Specification (FOCUS) v1.3, which defines a standard schema\n    for cloud, SaaS, and other technology billing data. FOCUS normalizes billing datasets across providers to reduce complexity\n    for FinOps practitioners. This specification models the Cost and Usage dataset and the Contract Commitment dataset defined\n    by the FOCUS standard, enabling programmatic access to FOCUS-compliant billing data. The FOCUS specification is maintained\n    by the FinOps Foundation under the Linux Foundation.\n  tags:\n  - Finops\n  - Foundation\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: finops-foundation\n    baseUri: https://api.example.com/focus/v1\n    description: FinOps Foundation FOCUS Cost and Usage API HTTP API.\n    authentication:\n      type: bearer\n    \
  \  token: '{{FINOPS_FOUNDATION_TOKEN}}'\n    resources:\n    - name: cost-and-usage\n      path: /cost-and-usage\n      operations:\n      - name: listcostandusage\n        method: GET\n        description: FinOps Foundation List cost and usage records\n        inputParameters:\n        - name: billingPeriodStart\n          in: query\n          type: string\n          description: Filter by billing period start date (inclusive). Format is date-time per RFC 3339.\n        - name: billingPeriodEnd\n          in: query\n          type: string\n          description: Filter by billing period end date (exclusive). Format is date-time per RFC 3339.\n        - name: chargeCategory\n          in: query\n          type: string\n          description: Filter by charge category (e.g., Usage, Purchase, Tax, Credit, Adjustment).\n        - name: providerName\n          in: query\n          type: string\n          description: Filter by the name of the entity that made the resource or service available.\n\
  \        - name: serviceName\n          in: query\n          type: string\n          description: Filter by the display name of the service that was purchased.\n        - name: serviceCategory\n          in: query\n          type: string\n          description: Filter by the highest-level classification of a service (e.g., Compute, Storage, Networking, Database).\n        - name: region\n          in: query\n          type: string\n          description: Filter by the isolated geographic area where a resource is provisioned or a service is provided.\n        - name: resourceId\n          in: query\n          type: string\n          description: Filter by unique identifier assigned to a resource by the provider.\n        - name: subAccountId\n          in: query\n          type: string\n          description: Filter by the identifier for a sub account.\n        - name: billingCurrency\n          in: query\n          type: string\n          description: Filter by the currency that a charge\
  \ was billed in.\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of records to return per page.\n        - name: pageToken\n          in: query\n          type: string\n          description: Token for retrieving the next page of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cost-and-usage-export\n      path: /cost-and-usage/export\n      operations:\n      - name: exportcostandusage\n        method: POST\n        description: FinOps Foundation Export cost and usage data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cost-and-usage-export-jobid\n      path: /cost-and-usage/export/{jobId}\n      operations:\n      - name: getcostandusageexportstatus\n        method: GET\n        description: FinOps Foundation Get cost and usage export job status\n\
  \        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the export job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contract-commitments\n      path: /contract-commitments\n      operations:\n      - name: listcontractcommitments\n        method: GET\n        description: FinOps Foundation List contract commitment records\n        inputParameters:\n        - name: commitmentDiscountId\n          in: query\n          type: string\n          description: Filter by the identifier assigned to a commitment discount by the provider.\n        - name: billingAccountId\n          in: query\n          type: string\n          description: Filter by the unique identifier for a billing account.\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number\
  \ of records to return per page.\n        - name: pageToken\n          in: query\n          type: string\n          description: Token for retrieving the next page of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema\n      path: /schema\n      operations:\n      - name: getschemametadata\n        method: GET\n        description: FinOps Foundation Get FOCUS schema metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: finops-foundation-rest\n    description: REST adapter for FinOps Foundation FOCUS Cost and Usage API.\n    resources:\n    - path: /cost-and-usage\n      name: listcostandusage\n      operations:\n      - method: GET\n        name: listcostandusage\n        description: FinOps Foundation List cost and usage records\n        call:\
  \ finops-foundation.listcostandusage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cost-and-usage/export\n      name: exportcostandusage\n      operations:\n      - method: POST\n        name: exportcostandusage\n        description: FinOps Foundation Export cost and usage data\n        call: finops-foundation.exportcostandusage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cost-and-usage/export/{jobId}\n      name: getcostandusageexportstatus\n      operations:\n      - method: GET\n        name: getcostandusageexportstatus\n        description: FinOps Foundation Get cost and usage export job status\n        call: finops-foundation.getcostandusageexportstatus\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contract-commitments\n      name: listcontractcommitments\n      operations:\n      - method: GET\n        name: listcontractcommitments\n\
  \        description: FinOps Foundation List contract commitment records\n        call: finops-foundation.listcontractcommitments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schema\n      name: getschemametadata\n      operations:\n      - method: GET\n        name: getschemametadata\n        description: FinOps Foundation Get FOCUS schema metadata\n        call: finops-foundation.getschemametadata\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: finops-foundation-mcp\n    transport: http\n    description: MCP adapter for FinOps Foundation FOCUS Cost and Usage API for AI agent use.\n    tools:\n    - name: listcostandusage\n      description: FinOps Foundation List cost and usage records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finops-foundation.listcostandusage\n      with:\n        billingPeriodStart: tools.billingPeriodStart\n\
  \        billingPeriodEnd: tools.billingPeriodEnd\n        chargeCategory: tools.chargeCategory\n        providerName: tools.providerName\n        serviceName: tools.serviceName\n        serviceCategory: tools.serviceCategory\n        region: tools.region\n        resourceId: tools.resourceId\n        subAccountId: tools.subAccountId\n        billingCurrency: tools.billingCurrency\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: billingPeriodStart\n        type: string\n        description: Filter by billing period start date (inclusive). Format is date-time per RFC 3339.\n      - name: billingPeriodEnd\n        type: string\n        description: Filter by billing period end date (exclusive). Format is date-time per RFC 3339.\n      - name: chargeCategory\n        type: string\n        description: Filter by charge category (e.g., Usage, Purchase, Tax, Credit, Adjustment).\n      - name: providerName\n        type: string\n  \
  \      description: Filter by the name of the entity that made the resource or service available.\n      - name: serviceName\n        type: string\n        description: Filter by the display name of the service that was purchased.\n      - name: serviceCategory\n        type: string\n        description: Filter by the highest-level classification of a service (e.g., Compute, Storage, Networking, Database).\n      - name: region\n        type: string\n        description: Filter by the isolated geographic area where a resource is provisioned or a service is provided.\n      - name: resourceId\n        type: string\n        description: Filter by unique identifier assigned to a resource by the provider.\n      - name: subAccountId\n        type: string\n        description: Filter by the identifier for a sub account.\n      - name: billingCurrency\n        type: string\n        description: Filter by the currency that a charge was billed in.\n      - name: pageSize\n        type: integer\n\
  \        description: Number of records to return per page.\n      - name: pageToken\n        type: string\n        description: Token for retrieving the next page of results.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exportcostandusage\n      description: FinOps Foundation Export cost and usage data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: finops-foundation.exportcostandusage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcostandusageexportstatus\n      description: FinOps Foundation Get cost and usage export job status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finops-foundation.getcostandusageexportstatus\n      with:\n        jobId: tools.jobId\n      inputParameters:\n      - name: jobId\n        type: string\n        description: The unique identifier for the export job.\n      \
  \  required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontractcommitments\n      description: FinOps Foundation List contract commitment records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finops-foundation.listcontractcommitments\n      with:\n        commitmentDiscountId: tools.commitmentDiscountId\n        billingAccountId: tools.billingAccountId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: commitmentDiscountId\n        type: string\n        description: Filter by the identifier assigned to a commitment discount by the provider.\n      - name: billingAccountId\n        type: string\n        description: Filter by the unique identifier for a billing account.\n      - name: pageSize\n        type: integer\n        description: Number of records to return per page.\n      - name: pageToken\n        type: string\n \
  \       description: Token for retrieving the next page of results.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getschemametadata\n      description: FinOps Foundation Get FOCUS schema metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finops-foundation.getschemametadata\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FINOPS_FOUNDATION_TOKEN: FINOPS_FOUNDATION_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/finops-foundation/refs/heads/main/capabilities/finops-foundation-capability.yaml
tags:
- Finops
- Foundation
- API
tools:
- description: FinOps Foundation List cost and usage records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcostandusage
- description: FinOps Foundation Export cost and usage data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exportcostandusage
- description: FinOps Foundation Get cost and usage export job status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcostandusageexportstatus
- description: FinOps Foundation List contract commitment records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontractcommitments
- description: FinOps Foundation Get FOCUS schema metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getschemametadata
---
