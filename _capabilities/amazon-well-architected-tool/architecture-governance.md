---
categories:
- compliance
consumed_apis: []
description: Unified workflow for architecture governance using the AWS Well-Architected Tool. Enables cloud architects and governance teams to manage workloads, run lens reviews, track answers, create milestones, and generate consolidated reports across the organization's cloud portfolio.
layout: capability
name: Amazon Well-Architected Tool Architecture Governance
operations:
- description: List all workloads in the account.
  method: GET
  name: list-workloads
  path: /v1/workloads
- description: Create a new workload for architectural review.
  method: POST
  name: create-workload
  path: /v1/workloads
- description: Get workload details.
  method: GET
  name: get-workload
  path: /v1/workloads/{id}
- description: List available lenses.
  method: GET
  name: list-lenses
  path: /v1/lenses
- description: List lens reviews for a workload.
  method: GET
  name: list-lens-reviews
  path: /v1/reviews
- description: List answers for a workload lens review.
  method: GET
  name: list-answers
  path: /v1/answers
- description: Create a milestone to capture review state.
  method: POST
  name: create-milestone
  path: /v1/milestones
- description: List profiles.
  method: GET
  name: list-profiles
  path: /v1/profiles
- description: Get consolidated architectural review report.
  method: GET
  name: get-consolidated-report
  path: /v1/reports
personas: []
provider_name: Amazon Well-Architected Tool
provider_slug: amazon-well-architected-tool
search_terms:
- get consolidated report
- designs and reviews cloud workload architectures against aws best practices.
- Cloud Architect
- list profiles.
- manage workloads under architectural review.
- list lens reviews for a specific workload.
- list workload profiles used to customize reviews.
- well-architected
- oversight and compliance of cloud architecture decisions
- Governance Team
- workload profiles.
- create a milestone to capture review state.
- list profiles
- unified workflow for cloud architects and governance teams to manage workloads, run lens reviews, track answers, create milestones, and generate reports.
- create a new workload for architectural review.
- list lens reviews
- get workload
- compliance
- list all workloads under architectural review in the aws account.
- create milestone
- cloud governance
- regulatory and organizational policy adherence
- consolidated governance reports.
- get consolidated architectural review report.
- best practices
- list all workloads in the account.
- architecture
- cloud workload design and best practices
- architectural review answers.
- get details and metadata for a specific workload.
- create workload
- list architectural review answers for a workload and lens.
- save a milestone snapshot of the current workload review state.
- generate a consolidated architectural review report across workloads.
- list available lenses.
- list lenses
- list lens reviews for a workload.
- single workload management.
- list answers
- list workloads
- list answers for a workload lens review.
- aws
- oversees architectural compliance and risk across the cloud portfolio.
- workloads
- get workload details.
- workload review milestones.
- lens reviews for workloads.
- lens catalog for architectural reviews.
- list available aws and custom lenses for architectural reviews.
- create a new workload to begin an architectural review.
slug: architecture-governance
source_filename: architecture-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Well-Architected Tool Architecture Governance\n  description: Unified workflow for architecture governance using the AWS Well-Architected Tool. Enables cloud architects\n    and governance teams to manage workloads, run lens reviews, track answers, create milestones, and generate consolidated\n    reports across the organization's cloud portfolio.\n  tags:\n  - Architecture\n  - AWS\n  - Cloud Governance\n  - Well-Architected\n  - Compliance\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: well-architected-tool\n    baseUri: https://wellarchitected.us-east-1.amazonaws.com\n    description: AWS Well-Architected Tool REST API for architecture reviews and governance.\n    authentication:\n      type: apikey\n      key: Authorization\n\
  \      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: workloads\n      path: /workloads\n      description: Manage workloads under architectural review.\n      operations:\n      - name: list-workloads\n        method: POST\n        description: List workloads in the account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-workload\n        method: POST\n        description: Create a new workload for architectural review.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            WorkloadName: '{{tools.workload_name}}'\n            Description: '{{tools.description}}'\n            Environment: '{{tools.environment}}'\n            ReviewOwner: '{{tools.review_owner}}'\n    - name: workload-detail\n      path: /workloads/{WorkloadId}\n\
  \      description: Manage a specific workload by ID.\n      operations:\n      - name: get-workload\n        method: GET\n        description: Get details of a specific workload.\n        inputParameters:\n        - name: WorkloadId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workload.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-workload\n        method: PATCH\n        description: Update workload properties.\n        inputParameters:\n        - name: WorkloadId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workload.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            WorkloadName: '{{tools.workload_name}}'\n\
  \      - name: delete-workload\n        method: DELETE\n        description: Delete a workload.\n        inputParameters:\n        - name: WorkloadId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the workload.\n        - name: ClientRequestToken\n          in: query\n          type: string\n          required: true\n          description: Idempotency token for the delete request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lens-reviews\n      path: /workloads/{WorkloadId}/lensReviews\n      description: Manage lens reviews for a workload.\n      operations:\n      - name: list-lens-reviews\n        method: GET\n        description: List lens reviews for a workload.\n        inputParameters:\n        - name: WorkloadId\n          in: path\n          type: string\n          required: true\n          description: The workload\
  \ identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-lens-review\n        method: GET\n        description: Get a specific lens review for a workload.\n        inputParameters:\n        - name: WorkloadId\n          in: path\n          type: string\n          required: true\n          description: The workload identifier.\n        - name: LensAlias\n          in: path\n          type: string\n          required: true\n          description: The lens alias.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: answers\n      path: /workloads/{WorkloadId}/lensReviews/{LensAlias}/answers\n      description: Manage review answers for a workload lens.\n      operations:\n      - name: list-answers\n        method: GET\n        description: List answers for a workload lens review.\n        inputParameters:\n\
  \        - name: WorkloadId\n          in: path\n          type: string\n          required: true\n          description: The workload identifier.\n        - name: LensAlias\n          in: path\n          type: string\n          required: true\n          description: The lens alias.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: milestones\n      path: /workloads/{WorkloadId}/milestones\n      description: Manage workload milestones.\n      operations:\n      - name: create-milestone\n        method: POST\n        description: Create a milestone to capture workload review state.\n        inputParameters:\n        - name: WorkloadId\n          in: path\n          type: string\n          required: true\n          description: The workload identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n    \
  \      type: json\n          data:\n            MilestoneName: '{{tools.milestone_name}}'\n    - name: lenses\n      path: /lenses\n      description: Manage lenses available in the account.\n      operations:\n      - name: list-lenses\n        method: GET\n        description: List available lenses.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles\n      path: /profiles\n      description: Manage workload profiles.\n      operations:\n      - name: list-profiles\n        method: GET\n        description: List profiles in the account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-profile\n        method: POST\n        description: Create a new profile.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      \
  \  body:\n          type: json\n          data:\n            ProfileName: '{{tools.profile_name}}'\n            ProfileDescription: '{{tools.description}}'\n    - name: consolidated-report\n      path: /consolidatedReport\n      description: Generate consolidated reports across workloads.\n      operations:\n      - name: get-consolidated-report\n        method: GET\n        description: Get a consolidated architectural review report.\n        inputParameters:\n        - name: Format\n          in: query\n          type: string\n          required: true\n          description: The report format (PDF or JSON).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: architecture-governance-api\n    description: Unified REST API for AWS Well-Architected Tool architecture governance workflows.\n    resources:\n    - path: /v1/workloads\n      name: workloads\n\
  \      description: Manage workloads under architectural review.\n      operations:\n      - method: GET\n        name: list-workloads\n        description: List all workloads in the account.\n        call: well-architected-tool.list-workloads\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-workload\n        description: Create a new workload for architectural review.\n        call: well-architected-tool.create-workload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workloads/{id}\n      name: workload-detail\n      description: Single workload management.\n      operations:\n      - method: GET\n        name: get-workload\n        description: Get workload details.\n        call: well-architected-tool.get-workload\n        with:\n          WorkloadId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lenses\n      name: lenses\n\
  \      description: Lens catalog for architectural reviews.\n      operations:\n      - method: GET\n        name: list-lenses\n        description: List available lenses.\n        call: well-architected-tool.list-lenses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reviews\n      name: reviews\n      description: Lens reviews for workloads.\n      operations:\n      - method: GET\n        name: list-lens-reviews\n        description: List lens reviews for a workload.\n        call: well-architected-tool.list-lens-reviews\n        with:\n          WorkloadId: rest.workload_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/answers\n      name: answers\n      description: Architectural review answers.\n      operations:\n      - method: GET\n        name: list-answers\n        description: List answers for a workload lens review.\n        call: well-architected-tool.list-answers\n        with:\n    \
  \      WorkloadId: rest.workload_id\n          LensAlias: rest.lens_alias\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/milestones\n      name: milestones\n      description: Workload review milestones.\n      operations:\n      - method: POST\n        name: create-milestone\n        description: Create a milestone to capture review state.\n        call: well-architected-tool.create-milestone\n        with:\n          WorkloadId: rest.workload_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/profiles\n      name: profiles\n      description: Workload profiles.\n      operations:\n      - method: GET\n        name: list-profiles\n        description: List profiles.\n        call: well-architected-tool.list-profiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Consolidated governance reports.\n      operations:\n\
  \      - method: GET\n        name: get-consolidated-report\n        description: Get consolidated architectural review report.\n        call: well-architected-tool.get-consolidated-report\n        with:\n          Format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: architecture-governance-mcp\n    transport: http\n    description: MCP server for AI-assisted AWS Well-Architected Tool architecture governance.\n    tools:\n    - name: list-workloads\n      description: List all workloads under architectural review in the AWS account.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: well-architected-tool.list-workloads\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workload\n      description: Get details and metadata for a specific workload.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: well-architected-tool.get-workload\n\
  \      with:\n        WorkloadId: tools.workload_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workload\n      description: Create a new workload to begin an architectural review.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: well-architected-tool.create-workload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-lenses\n      description: List available AWS and custom lenses for architectural reviews.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: well-architected-tool.list-lenses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-lens-reviews\n      description: List lens reviews for a specific workload.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: well-architected-tool.list-lens-reviews\n      with:\n        WorkloadId: tools.workload_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-answers\n      description: List architectural review answers for a workload and lens.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: well-architected-tool.list-answers\n      with:\n        WorkloadId: tools.workload_id\n        LensAlias: tools.lens_alias\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-milestone\n      description: Save a milestone snapshot of the current workload review state.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: well-architected-tool.create-milestone\n      with:\n        WorkloadId: tools.workload_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-profiles\n      description: List workload profiles used to customize reviews.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: well-architected-tool.list-profiles\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-consolidated-report\n      description: Generate a consolidated architectural review report across workloads.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: well-architected-tool.get-consolidated-report\n      with:\n        Format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-well-architected-tool/refs/heads/main/capabilities/architecture-governance.yaml
tags:
- Architecture
- Cloud Governance
- Well-Architected
- Compliance
tools:
- description: List all workloads under architectural review in the AWS account.
  hints:
    openWorld: true
    readOnly: true
  name: list-workloads
- description: Get details and metadata for a specific workload.
  hints:
    openWorld: false
    readOnly: true
  name: get-workload
- description: Create a new workload to begin an architectural review.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-workload
- description: List available AWS and custom lenses for architectural reviews.
  hints:
    openWorld: true
    readOnly: true
  name: list-lenses
- description: List lens reviews for a specific workload.
  hints:
    openWorld: false
    readOnly: true
  name: list-lens-reviews
- description: List architectural review answers for a workload and lens.
  hints:
    openWorld: false
    readOnly: true
  name: list-answers
- description: Save a milestone snapshot of the current workload review state.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-milestone
- description: List workload profiles used to customize reviews.
  hints:
    openWorld: true
    readOnly: true
  name: list-profiles
- description: Generate a consolidated architectural review report across workloads.
  hints:
    openWorld: true
    readOnly: true
  name: get-consolidated-report
---
