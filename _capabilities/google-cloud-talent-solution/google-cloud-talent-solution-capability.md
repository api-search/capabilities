---
categories: []
consumed_apis: []
description: The Cloud Talent Solution API provides job search, job posting management, company profiles, and tenant administration for building intelligent talent acquisition applications powered by machine learning.
layout: capability
name: Google Cloud Talent Solution API
operations:
- description: Google Cloud Talent Solution List tenants
  method: GET
  name: listtenants
  path: /projects/{projectId}/tenants
- description: Google Cloud Talent Solution Create a tenant
  method: POST
  name: createtenant
  path: /projects/{projectId}/tenants
- description: Google Cloud Talent Solution Get a tenant
  method: GET
  name: gettenant
  path: /projects/{projectId}/tenants/{tenantId}
- description: Google Cloud Talent Solution Delete a tenant
  method: DELETE
  name: deletetenant
  path: /projects/{projectId}/tenants/{tenantId}
- description: Google Cloud Talent Solution List companies
  method: GET
  name: listcompanies
  path: /projects/{projectId}/tenants/{tenantId}/companies
- description: Google Cloud Talent Solution Create a company
  method: POST
  name: createcompany
  path: /projects/{projectId}/tenants/{tenantId}/companies
- description: Google Cloud Talent Solution List jobs
  method: GET
  name: listjobs
  path: /projects/{projectId}/tenants/{tenantId}/jobs
- description: Google Cloud Talent Solution Create a job
  method: POST
  name: createjob
  path: /projects/{projectId}/tenants/{tenantId}/jobs
- description: Google Cloud Talent Solution Get a job
  method: GET
  name: getjob
  path: /projects/{projectId}/tenants/{tenantId}/jobs/{jobId}
- description: Google Cloud Talent Solution Update a job
  method: PATCH
  name: updatejob
  path: /projects/{projectId}/tenants/{tenantId}/jobs/{jobId}
- description: Google Cloud Talent Solution Delete a job
  method: DELETE
  name: deletejob
  path: /projects/{projectId}/tenants/{tenantId}/jobs/{jobId}
- description: Google Cloud Talent Solution Search jobs
  method: POST
  name: searchjobs
  path: /projects/{projectId}/tenants/{tenantId}/jobs:search
personas: []
provider_name: Google Cloud Talent Solution
provider_slug: google-cloud-talent-solution
search_terms:
- google cloud talent solution list tenants
- google cloud talent solution create a company
- google cloud talent solution update a job
- google cloud talent solution create a job
- google cloud talent solution search jobs
- google cloud talent solution list jobs
- api
- talent
- createtenant
- google cloud talent solution get a tenant
- listjobs
- solution
- google
- updatejob
- gettenant
- google cloud talent solution list companies
- machine learning
- deletetenant
- google cloud talent solution create a tenant
- listcompanies
- google cloud talent solution delete a job
- recruitment
- searchjobs
- listtenants
- cloud
- deletejob
- getjob
- jobs
- search
- google cloud talent solution get a job
- google cloud
- google cloud talent solution delete a tenant
- createjob
- createcompany
slug: google-cloud-talent-solution-capability
source_filename: google-cloud-talent-solution-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Talent Solution API\n  description: The Cloud Talent Solution API provides job search, job posting management, company profiles, and tenant administration\n    for building intelligent talent acquisition applications powered by machine learning.\n  tags:\n  - Google\n  - Cloud\n  - Talent\n  - Solution\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-talent-solution\n    baseUri: https://jobs.googleapis.com/v4\n    description: Google Cloud Talent Solution API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_TALENT_SOLUTION_TOKEN}}'\n    resources:\n    - name: projects-projectid-tenants\n      path: /projects/{projectId}/tenants\n      operations:\n      - name: listtenants\n        method: GET\n        description: Google Cloud Talent Solution List tenants\n        inputParameters:\n        - name: projectId\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtenant\n        method: POST\n        description: Google Cloud Talent Solution Create a tenant\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-tenants-tenantid\n      path: /projects/{projectId}/tenants/{tenantId}\n      operations:\n      - name: gettenant\n        method: GET\n        description: Google Cloud Talent Solution Get a tenant\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: tenantId\n          in: path\n          type: string\n         \
  \ required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetenant\n        method: DELETE\n        description: Google Cloud Talent Solution Delete a tenant\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: tenantId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-tenants-tenantid-companies\n      path: /projects/{projectId}/tenants/{tenantId}/companies\n      operations:\n      - name: listcompanies\n        method: GET\n        description: Google Cloud Talent Solution List companies\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        -\
  \ name: tenantId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcompany\n        method: POST\n        description: Google Cloud Talent Solution Create a company\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: tenantId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-tenants-tenantid-jobs\n      path: /projects/{projectId}/tenants/{tenantId}/jobs\n      operations:\n      - name: listjobs\n        method: GET\n        description: Google Cloud Talent Solution List jobs\n        inputParameters:\n        - name: projectId\n          in: path\n        \
  \  type: string\n          required: true\n        - name: tenantId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createjob\n        method: POST\n        description: Google Cloud Talent Solution Create a job\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: tenantId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-tenants-tenantid-jobs-jobid\n      path: /projects/{projectId}/tenants/{tenantId}/jobs/{jobId}\n      operations:\n      - name: getjob\n        method: GET\n        description: Google Cloud Talent Solution Get a job\n        inputParameters:\n\
  \        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: tenantId\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatejob\n        method: PATCH\n        description: Google Cloud Talent Solution Update a job\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: tenantId\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletejob\n        method:\
  \ DELETE\n        description: Google Cloud Talent Solution Delete a job\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: tenantId\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-tenants-tenantid-jobs-search\n      path: /projects/{projectId}/tenants/{tenantId}/jobs:search\n      operations:\n      - name: searchjobs\n        method: POST\n        description: Google Cloud Talent Solution Search jobs\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: tenantId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-talent-solution-rest\n    description: REST adapter for Google Cloud Talent Solution API.\n    resources:\n    - path: /projects/{projectId}/tenants\n      name: listtenants\n      operations:\n      - method: GET\n        name: listtenants\n        description: Google Cloud Talent Solution List tenants\n        call: google-cloud-talent-solution.listtenants\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/tenants\n      name: createtenant\n      operations:\n      - method: POST\n        name: createtenant\n        description: Google Cloud Talent Solution Create a tenant\n        call: google-cloud-talent-solution.createtenant\n        with:\n          projectId: rest.projectId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/tenants/{tenantId}\n      name: gettenant\n      operations:\n      - method: GET\n        name: gettenant\n        description: Google Cloud Talent Solution Get a tenant\n        call: google-cloud-talent-solution.gettenant\n        with:\n          projectId: rest.projectId\n          tenantId: rest.tenantId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/tenants/{tenantId}\n      name: deletetenant\n      operations:\n      - method: DELETE\n        name: deletetenant\n        description: Google Cloud Talent Solution Delete a tenant\n        call: google-cloud-talent-solution.deletetenant\n        with:\n          projectId: rest.projectId\n          tenantId: rest.tenantId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/tenants/{tenantId}/companies\n      name: listcompanies\n   \
  \   operations:\n      - method: GET\n        name: listcompanies\n        description: Google Cloud Talent Solution List companies\n        call: google-cloud-talent-solution.listcompanies\n        with:\n          projectId: rest.projectId\n          tenantId: rest.tenantId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/tenants/{tenantId}/companies\n      name: createcompany\n      operations:\n      - method: POST\n        name: createcompany\n        description: Google Cloud Talent Solution Create a company\n        call: google-cloud-talent-solution.createcompany\n        with:\n          projectId: rest.projectId\n          tenantId: rest.tenantId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/tenants/{tenantId}/jobs\n      name: listjobs\n      operations:\n      - method: GET\n        name: listjobs\n        description: Google Cloud Talent Solution List\
  \ jobs\n        call: google-cloud-talent-solution.listjobs\n        with:\n          projectId: rest.projectId\n          tenantId: rest.tenantId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/tenants/{tenantId}/jobs\n      name: createjob\n      operations:\n      - method: POST\n        name: createjob\n        description: Google Cloud Talent Solution Create a job\n        call: google-cloud-talent-solution.createjob\n        with:\n          projectId: rest.projectId\n          tenantId: rest.tenantId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/tenants/{tenantId}/jobs/{jobId}\n      name: getjob\n      operations:\n      - method: GET\n        name: getjob\n        description: Google Cloud Talent Solution Get a job\n        call: google-cloud-talent-solution.getjob\n        with:\n          projectId: rest.projectId\n          tenantId: rest.tenantId\n  \
  \        jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/tenants/{tenantId}/jobs/{jobId}\n      name: updatejob\n      operations:\n      - method: PATCH\n        name: updatejob\n        description: Google Cloud Talent Solution Update a job\n        call: google-cloud-talent-solution.updatejob\n        with:\n          projectId: rest.projectId\n          tenantId: rest.tenantId\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/tenants/{tenantId}/jobs/{jobId}\n      name: deletejob\n      operations:\n      - method: DELETE\n        name: deletejob\n        description: Google Cloud Talent Solution Delete a job\n        call: google-cloud-talent-solution.deletejob\n        with:\n          projectId: rest.projectId\n          tenantId: rest.tenantId\n          jobId: rest.jobId\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /projects/{projectId}/tenants/{tenantId}/jobs:search\n      name: searchjobs\n      operations:\n      - method: POST\n        name: searchjobs\n        description: Google Cloud Talent Solution Search jobs\n        call: google-cloud-talent-solution.searchjobs\n        with:\n          projectId: rest.projectId\n          tenantId: rest.tenantId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-talent-solution-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Talent Solution API for AI agent use.\n    tools:\n    - name: listtenants\n      description: Google Cloud Talent Solution List tenants\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-talent-solution.listtenants\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n \
  \       type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtenant\n      description: Google Cloud Talent Solution Create a tenant\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-talent-solution.createtenant\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettenant\n      description: Google Cloud Talent Solution Get a tenant\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-talent-solution.gettenant\n      with:\n        projectId: tools.projectId\n        tenantId: tools.tenantId\n      inputParameters:\n      - name: projectId\n        type:\
  \ string\n        description: projectId\n        required: true\n      - name: tenantId\n        type: string\n        description: tenantId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetenant\n      description: Google Cloud Talent Solution Delete a tenant\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-talent-solution.deletetenant\n      with:\n        projectId: tools.projectId\n        tenantId: tools.tenantId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: tenantId\n        type: string\n        description: tenantId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcompanies\n      description: Google Cloud Talent Solution List companies\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: google-cloud-talent-solution.listcompanies\n      with:\n        projectId: tools.projectId\n        tenantId: tools.tenantId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: tenantId\n        type: string\n        description: tenantId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcompany\n      description: Google Cloud Talent Solution Create a company\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-talent-solution.createcompany\n      with:\n        projectId: tools.projectId\n        tenantId: tools.tenantId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: tenantId\n        type: string\n        description: tenantId\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjobs\n      description: Google Cloud Talent Solution List jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-talent-solution.listjobs\n      with:\n        projectId: tools.projectId\n        tenantId: tools.tenantId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: tenantId\n        type: string\n        description: tenantId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createjob\n      description: Google Cloud Talent Solution Create a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-talent-solution.createjob\n      with:\n        projectId: tools.projectId\n        tenantId: tools.tenantId\n\
  \      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: tenantId\n        type: string\n        description: tenantId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjob\n      description: Google Cloud Talent Solution Get a job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-talent-solution.getjob\n      with:\n        projectId: tools.projectId\n        tenantId: tools.tenantId\n        jobId: tools.jobId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: tenantId\n        type: string\n        description: tenantId\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: updatejob\n      description: Google Cloud Talent Solution Update a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-talent-solution.updatejob\n      with:\n        projectId: tools.projectId\n        tenantId: tools.tenantId\n        jobId: tools.jobId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: tenantId\n        type: string\n        description: tenantId\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletejob\n      description: Google Cloud Talent Solution Delete a job\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-talent-solution.deletejob\n      with:\n   \
  \     projectId: tools.projectId\n        tenantId: tools.tenantId\n        jobId: tools.jobId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: tenantId\n        type: string\n        description: tenantId\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchjobs\n      description: Google Cloud Talent Solution Search jobs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-talent-solution.searchjobs\n      with:\n        projectId: tools.projectId\n        tenantId: tools.tenantId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: tenantId\n        type: string\n        description: tenantId\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_TALENT_SOLUTION_TOKEN: GOOGLE_CLOUD_TALENT_SOLUTION_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-talent-solution/refs/heads/main/capabilities/google-cloud-talent-solution-capability.yaml
tags:
- Google
- Cloud
- Talent
- Solution
- API
tools:
- description: Google Cloud Talent Solution List tenants
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtenants
- description: Google Cloud Talent Solution Create a tenant
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtenant
- description: Google Cloud Talent Solution Get a tenant
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettenant
- description: Google Cloud Talent Solution Delete a tenant
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetenant
- description: Google Cloud Talent Solution List companies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcompanies
- description: Google Cloud Talent Solution Create a company
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcompany
- description: Google Cloud Talent Solution List jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: Google Cloud Talent Solution Create a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createjob
- description: Google Cloud Talent Solution Get a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjob
- description: Google Cloud Talent Solution Update a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatejob
- description: Google Cloud Talent Solution Delete a job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletejob
- description: Google Cloud Talent Solution Search jobs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchjobs
---
