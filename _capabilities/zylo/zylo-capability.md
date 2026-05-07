---
categories: []
consumed_apis: []
description: The Zylo Enterprise API provides a modern, RESTful API to work with your SaaS subscription data. The API is built using resource-oriented URLs that are protected by HTTPS transport security and authenticated via secure tokens. It enables the export of SaaS usage and subscription data to reporting tools outside of Zylo, as well as the import of additional unintegrated usage data.
layout: capability
name: Zylo Enterprise API
operations:
- description: Zylo List subscriptions
  method: GET
  name: listsubscriptions
  path: /subscriptions
- description: Zylo Get a subscription
  method: GET
  name: getsubscription
  path: /subscriptions/{subscriptionId}
- description: Zylo List applications
  method: GET
  name: listapplications
  path: /applications
- description: Zylo Get an application
  method: GET
  name: getapplication
  path: /applications/{applicationId}
- description: Zylo Update an application
  method: PUT
  name: updateapplication
  path: /applications/{applicationId}
- description: Zylo Create an export job
  method: POST
  name: createexportjob
  path: /subscriptions/-/exportJobs
- description: Zylo Get an export job
  method: GET
  name: getexportjob
  path: /subscriptions/-/exportJobs/{exportJobId}
- description: Zylo List import jobs
  method: GET
  name: listimportjobs
  path: /subscriptions/{subscriptionId}/importJob
- description: Zylo Create an import job
  method: POST
  name: createimportjob
  path: /subscriptions/{subscriptionId}/importJob
- description: Zylo Get an import job
  method: GET
  name: getimportjob
  path: /subscriptions/{subscriptionId}/importJob/{importJobId}
personas: []
provider_name: Zylo
provider_slug: zylo
search_terms:
- zylo get an import job
- getexportjob
- getimportjob
- zylo update an application
- zylo create an import job
- api
- listsubscriptions
- zylo list import jobs
- zylo list applications
- createexportjob
- getsubscription
- saas management
- spend
- getapplication
- zylo get an application
- updateapplication
- zylo
- listimportjobs
- createimportjob
- listapplications
- budgets
- zylo get a subscription
- zylo create an export job
- zylo get an export job
- zylo list subscriptions
slug: zylo-capability
source_filename: zylo-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Zylo Enterprise API\n  description: The Zylo Enterprise API provides a modern, RESTful API to work with your SaaS subscription data. The API is\n    built using resource-oriented URLs that are protected by HTTPS transport security and authenticated via secure tokens.\n    It enables the export of SaaS usage and subscription data to reporting tools outside of Zylo, as well as the import of\n    additional unintegrated usage data.\n  tags:\n  - Zylo\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: zylo\n    baseUri: https://api.zylo.com/v1\n    description: Zylo Enterprise API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ZYLO_TOKEN}}'\n    resources:\n    - name: subscriptions\n      path: /subscriptions\n      operations:\n      - name: listsubscriptions\n        method: GET\n        description: Zylo List subscriptions\n        inputParameters:\n\
  \        - name: pageSize\n          in: query\n          type: integer\n          description: The maximum number of results to return per page.\n        - name: pageToken\n          in: query\n          type: string\n          description: A token returned from a previous list request to retrieve the next page of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid\n      path: /subscriptions/{subscriptionId}\n      operations:\n      - name: getsubscription\n        method: GET\n        description: Zylo Get a subscription\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the subscription.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n\
  \      path: /applications\n      operations:\n      - name: listapplications\n        method: GET\n        description: Zylo List applications\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          description: The maximum number of results to return per page.\n        - name: pageToken\n          in: query\n          type: string\n          description: A token returned from a previous list request to retrieve the next page of results.\n        - name: custom_fields\n          in: query\n          type: object\n          description: Filter applications by custom field values. Uses bracket notation such as custom_fields[boolean]=true.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationid\n      path: /applications/{applicationId}\n      operations:\n      - name: getapplication\n        method: GET\n        description:\
  \ Zylo Get an application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapplication\n        method: PUT\n        description: Zylo Update an application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-exportjobs\n      path: /subscriptions/-/exportJobs\n      operations:\n      - name: createexportjob\n        method: POST\n        description: Zylo Create an export job\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-exportjobs-exportjobid\n      path: /subscriptions/-/exportJobs/{exportJobId}\n      operations:\n      - name: getexportjob\n        method: GET\n        description: Zylo Get an export job\n        inputParameters:\n        - name: exportJobId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the export job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-importjob\n      path: /subscriptions/{subscriptionId}/importJob\n      operations:\n      - name: listimportjobs\n        method: GET\n        description: Zylo List import jobs\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description:\
  \ The unique identifier of the subscription.\n        - name: pageSize\n          in: query\n          type: integer\n          description: The maximum number of results to return per page.\n        - name: pageToken\n          in: query\n          type: string\n          description: A token returned from a previous list request to retrieve the next page of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createimportjob\n        method: POST\n        description: Zylo Create an import job\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the subscription.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-importjob-importjob\n      path: /subscriptions/{subscriptionId}/importJob/{importJobId}\n\
  \      operations:\n      - name: getimportjob\n        method: GET\n        description: Zylo Get an import job\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the subscription.\n        - name: importJobId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the import job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: zylo-rest\n    description: REST adapter for Zylo Enterprise API.\n    resources:\n    - path: /subscriptions\n      name: listsubscriptions\n      operations:\n      - method: GET\n        name: listsubscriptions\n        description: Zylo List subscriptions\n        call: zylo.listsubscriptions\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}\n      name: getsubscription\n      operations:\n      - method: GET\n        name: getsubscription\n        description: Zylo Get a subscription\n        call: zylo.getsubscription\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications\n      name: listapplications\n      operations:\n      - method: GET\n        name: listapplications\n        description: Zylo List applications\n        call: zylo.listapplications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationId}\n      name: getapplication\n      operations:\n      - method: GET\n        name: getapplication\n        description: Zylo Get an application\n        call: zylo.getapplication\n        with:\n          applicationId: rest.applicationId\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /applications/{applicationId}\n      name: updateapplication\n      operations:\n      - method: PUT\n        name: updateapplication\n        description: Zylo Update an application\n        call: zylo.updateapplication\n        with:\n          applicationId: rest.applicationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/-/exportJobs\n      name: createexportjob\n      operations:\n      - method: POST\n        name: createexportjob\n        description: Zylo Create an export job\n        call: zylo.createexportjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/-/exportJobs/{exportJobId}\n      name: getexportjob\n      operations:\n      - method: GET\n        name: getexportjob\n        description: Zylo Get an export job\n        call: zylo.getexportjob\n        with:\n          exportJobId: rest.exportJobId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/importJob\n      name: listimportjobs\n      operations:\n      - method: GET\n        name: listimportjobs\n        description: Zylo List import jobs\n        call: zylo.listimportjobs\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/importJob\n      name: createimportjob\n      operations:\n      - method: POST\n        name: createimportjob\n        description: Zylo Create an import job\n        call: zylo.createimportjob\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/importJob/{importJobId}\n      name: getimportjob\n      operations:\n      - method: GET\n        name: getimportjob\n        description: Zylo Get an import job\n\
  \        call: zylo.getimportjob\n        with:\n          subscriptionId: rest.subscriptionId\n          importJobId: rest.importJobId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: zylo-mcp\n    transport: http\n    description: MCP adapter for Zylo Enterprise API for AI agent use.\n    tools:\n    - name: listsubscriptions\n      description: Zylo List subscriptions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zylo.listsubscriptions\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: The maximum number of results to return per page.\n      - name: pageToken\n        type: string\n        description: A token returned from a previous list request to retrieve the next page of results.\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getsubscription\n      description: Zylo Get a subscription\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zylo.getsubscription\n      with:\n        subscriptionId: tools.subscriptionId\n      inputParameters:\n      - name: subscriptionId\n        type: string\n        description: The unique identifier of the subscription.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapplications\n      description: Zylo List applications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zylo.listapplications\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        custom_fields: tools.custom_fields\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: The maximum number of results to return per page.\n      - name: pageToken\n\
  \        type: string\n        description: A token returned from a previous list request to retrieve the next page of results.\n      - name: custom_fields\n        type: object\n        description: Filter applications by custom field values. Uses bracket notation such as custom_fields[boolean]=true.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapplication\n      description: Zylo Get an application\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zylo.getapplication\n      with:\n        applicationId: tools.applicationId\n      inputParameters:\n      - name: applicationId\n        type: string\n        description: The unique identifier of the application.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapplication\n      description: Zylo Update an application\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: true\n      call: zylo.updateapplication\n      with:\n        applicationId: tools.applicationId\n      inputParameters:\n      - name: applicationId\n        type: string\n        description: The unique identifier of the application.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createexportjob\n      description: Zylo Create an export job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zylo.createexportjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getexportjob\n      description: Zylo Get an export job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zylo.getexportjob\n      with:\n        exportJobId: tools.exportJobId\n      inputParameters:\n      - name: exportJobId\n        type: string\n        description: The unique identifier of the export job.\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listimportjobs\n      description: Zylo List import jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zylo.listimportjobs\n      with:\n        subscriptionId: tools.subscriptionId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: subscriptionId\n        type: string\n        description: The unique identifier of the subscription.\n        required: true\n      - name: pageSize\n        type: integer\n        description: The maximum number of results to return per page.\n      - name: pageToken\n        type: string\n        description: A token returned from a previous list request to retrieve the next page of results.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createimportjob\n      description: Zylo Create an import job\n  \
  \    hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zylo.createimportjob\n      with:\n        subscriptionId: tools.subscriptionId\n      inputParameters:\n      - name: subscriptionId\n        type: string\n        description: The unique identifier of the subscription.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getimportjob\n      description: Zylo Get an import job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zylo.getimportjob\n      with:\n        subscriptionId: tools.subscriptionId\n        importJobId: tools.importJobId\n      inputParameters:\n      - name: subscriptionId\n        type: string\n        description: The unique identifier of the subscription.\n        required: true\n      - name: importJobId\n        type: string\n        description: The unique identifier of the import job.\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ZYLO_TOKEN: ZYLO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zylo/refs/heads/main/capabilities/zylo-capability.yaml
tags:
- Zylo
- API
tools:
- description: Zylo List subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubscriptions
- description: Zylo Get a subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubscription
- description: Zylo List applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplications
- description: Zylo Get an application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplication
- description: Zylo Update an application
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapplication
- description: Zylo Create an export job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createexportjob
- description: Zylo Get an export job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexportjob
- description: Zylo List import jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listimportjobs
- description: Zylo Create an import job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createimportjob
- description: Zylo Get an import job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getimportjob
---
