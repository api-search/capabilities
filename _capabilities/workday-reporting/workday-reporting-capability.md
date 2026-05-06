---
categories: []
consumed_apis: []
description: REST API for accessing Workday custom and standard reports as RESTful web services. Enables external systems to consume report data in JSON, CSV, or XML formats. Reports must be configured as Advanced type reports with web service enabled in Workday before they can be accessed through this API. Supports prompt-based filtering through query parameters matching report prompt names configured in the report definition.
layout: capability
name: Workday Reporting Workday Report-as-a-Service (RaaS) API
operations:
- description: Workday Reporting Get report data
  method: GET
  name: getreport
  path: /{reportOwner}/{reportName}
- description: Workday Reporting Get report field metadata
  method: GET
  name: getreportmetadata
  path: /{reportOwner}/{reportName}/fields
personas: []
provider_name: Workday Reporting
provider_slug: workday-reporting
search_terms:
- business intelligence
- getreport
- workday reporting get report data
- workday reporting get report field metadata
- financial reporting
- hr data
- api
- reporting
- analytics
- workday
- getreportmetadata
slug: workday-reporting-capability
source_filename: workday-reporting-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Reporting Workday Report-as-a-Service (RaaS) API\n  description: REST API for accessing Workday custom and standard reports as RESTful web services. Enables external systems\n    to consume report data in JSON, CSV, or XML formats. Reports must be configured as Advanced type reports with web service\n    enabled in Workday before they can be accessed through this API. Supports prompt-based filtering through query parameters\n    matching report prompt names configured in the report definition.\n  tags:\n  - Workday\n  - Reporting\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: workday-reporting\n    baseUri: https://wd2-impl-services1.workday.com/ccx/service/customreport2/mycompany\n    description: Workday Reporting Workday Report-as-a-Service (RaaS) API HTTP API.\n    authentication:\n      type: basic\n      username: '{{WORKDAY_REPORTING_USERNAME}}'\n   \
  \   password: '{{WORKDAY_REPORTING_PASSWORD}}'\n    resources:\n    - name: reportowner-reportname\n      path: /{reportOwner}/{reportName}\n      operations:\n      - name: getreport\n        method: GET\n        description: Workday Reporting Get report data\n        inputParameters:\n        - name: reportOwner\n          in: path\n          type: string\n          required: true\n          description: Username of the report owner in Workday, typically the integration system user (ISU) account that owns\n            the report\n        - name: reportName\n          in: path\n          type: string\n          required: true\n          description: Name of the custom report as defined in Workday. Must match the report name exactly, using underscores\n            in place of spaces.\n        - name: format\n          in: query\n          type: string\n          description: Response format for the report data. Determines the Content-Type of the response body.\n        - name: Employee_ID\n\
  \          in: query\n          type: string\n          description: Example prompt parameter for filtering by Employee ID. Actual parameters depend on the prompts configured\n            in the report definition.\n        - name: Effective_Date\n          in: query\n          type: string\n          description: Example prompt parameter for filtering by effective date in YYYY-MM-DD format. Actual parameters depend\n            on the prompts configured in the report definition.\n        - name: Organization\n          in: query\n          type: string\n          description: Example prompt parameter for filtering by organization WID or reference ID. Actual parameters depend\n            on the prompts configured in the report definition.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reportowner-reportname-fields\n      path: /{reportOwner}/{reportName}/fields\n      operations:\n      - name:\
  \ getreportmetadata\n        method: GET\n        description: Workday Reporting Get report field metadata\n        inputParameters:\n        - name: reportOwner\n          in: path\n          type: string\n          required: true\n          description: Username of the report owner\n        - name: reportName\n          in: path\n          type: string\n          required: true\n          description: Name of the custom report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workday-reporting-rest\n    description: REST adapter for Workday Reporting Workday Report-as-a-Service (RaaS) API.\n    resources:\n    - path: /{reportOwner}/{reportName}\n      name: getreport\n      operations:\n      - method: GET\n        name: getreport\n        description: Workday Reporting Get report data\n        call: workday-reporting.getreport\n        with:\n   \
  \       reportOwner: rest.reportOwner\n          reportName: rest.reportName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{reportOwner}/{reportName}/fields\n      name: getreportmetadata\n      operations:\n      - method: GET\n        name: getreportmetadata\n        description: Workday Reporting Get report field metadata\n        call: workday-reporting.getreportmetadata\n        with:\n          reportOwner: rest.reportOwner\n          reportName: rest.reportName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workday-reporting-mcp\n    transport: http\n    description: MCP adapter for Workday Reporting Workday Report-as-a-Service (RaaS) API for AI agent use.\n    tools:\n    - name: getreport\n      description: Workday Reporting Get report data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-reporting.getreport\n\
  \      with:\n        reportOwner: tools.reportOwner\n        reportName: tools.reportName\n        format: tools.format\n        Employee_ID: tools.Employee_ID\n        Effective_Date: tools.Effective_Date\n        Organization: tools.Organization\n      inputParameters:\n      - name: reportOwner\n        type: string\n        description: Username of the report owner in Workday, typically the integration system user (ISU) account that owns\n          the report\n        required: true\n      - name: reportName\n        type: string\n        description: Name of the custom report as defined in Workday. Must match the report name exactly, using underscores\n          in place of spaces.\n        required: true\n      - name: format\n        type: string\n        description: Response format for the report data. Determines the Content-Type of the response body.\n      - name: Employee_ID\n        type: string\n        description: Example prompt parameter for filtering by Employee ID.\
  \ Actual parameters depend on the prompts configured\n          in the report definition.\n      - name: Effective_Date\n        type: string\n        description: Example prompt parameter for filtering by effective date in YYYY-MM-DD format. Actual parameters depend\n          on the prompts configured in the report definition.\n      - name: Organization\n        type: string\n        description: Example prompt parameter for filtering by organization WID or reference ID. Actual parameters depend\n          on the prompts configured in the report definition.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreportmetadata\n      description: Workday Reporting Get report field metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: workday-reporting.getreportmetadata\n      with:\n        reportOwner: tools.reportOwner\n        reportName: tools.reportName\n      inputParameters:\n      - name:\
  \ reportOwner\n        type: string\n        description: Username of the report owner\n        required: true\n      - name: reportName\n        type: string\n        description: Name of the custom report\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_REPORTING_USERNAME: WORKDAY_REPORTING_USERNAME\n    WORKDAY_REPORTING_PASSWORD: WORKDAY_REPORTING_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-reporting/refs/heads/main/capabilities/workday-reporting-capability.yaml
tags:
- Workday
- Reporting
- API
tools:
- description: Workday Reporting Get report data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreport
- description: Workday Reporting Get report field metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreportmetadata
---
