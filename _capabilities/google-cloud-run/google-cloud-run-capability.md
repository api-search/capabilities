---
categories: []
consumed_apis: []
description: The Cloud Run Admin API deploys and manages user-provided container images as serverless services. It supports creating, updating, and deleting services, managing revisions and traffic splitting, executing jobs, and configuring domain mappings.
layout: capability
name: Google Cloud Run Admin API
operations:
- description: Google Cloud Run List services
  method: GET
  name: listservices
  path: /projects/{projectId}/locations/{location}/services
- description: Google Cloud Run Create a service
  method: POST
  name: createservice
  path: /projects/{projectId}/locations/{location}/services
- description: Google Cloud Run Get a service
  method: GET
  name: getservice
  path: /projects/{projectId}/locations/{location}/services/{serviceId}
- description: Google Cloud Run Update a service
  method: PATCH
  name: updateservice
  path: /projects/{projectId}/locations/{location}/services/{serviceId}
- description: Google Cloud Run Delete a service
  method: DELETE
  name: deleteservice
  path: /projects/{projectId}/locations/{location}/services/{serviceId}
- description: Google Cloud Run List revisions
  method: GET
  name: listrevisions
  path: /projects/{projectId}/locations/{location}/services/{serviceId}/revisions
- description: Google Cloud Run Get a revision
  method: GET
  name: getrevision
  path: /projects/{projectId}/locations/{location}/services/{serviceId}/revisions/{revisionId}
- description: Google Cloud Run Delete a revision
  method: DELETE
  name: deleterevision
  path: /projects/{projectId}/locations/{location}/services/{serviceId}/revisions/{revisionId}
- description: Google Cloud Run List jobs
  method: GET
  name: listjobs
  path: /projects/{projectId}/locations/{location}/jobs
- description: Google Cloud Run Create a job
  method: POST
  name: createjob
  path: /projects/{projectId}/locations/{location}/jobs
- description: Google Cloud Run Get a job
  method: GET
  name: getjob
  path: /projects/{projectId}/locations/{location}/jobs/{jobId}
- description: Google Cloud Run Update a job
  method: PATCH
  name: updatejob
  path: /projects/{projectId}/locations/{location}/jobs/{jobId}
- description: Google Cloud Run Delete a job
  method: DELETE
  name: deletejob
  path: /projects/{projectId}/locations/{location}/jobs/{jobId}
- description: Google Cloud Run Run a job
  method: POST
  name: runjob
  path: /projects/{projectId}/locations/{location}/jobs/{jobId}:run
personas: []
provider_name: Google Cloud Run
provider_slug: google-cloud-run
search_terms:
- getrevision
- google cloud run get a job
- updatejob
- runjob
- google cloud run list services
- listjobs
- google cloud run get a revision
- google cloud run list revisions
- google cloud run list jobs
- google cloud run delete a service
- serverless
- cloud
- listrevisions
- getservice
- google
- containers
- deleteservice
- google cloud run create a job
- google cloud run update a service
- google cloud
- google cloud run create a service
- api
- google cloud run delete a revision
- updateservice
- deletejob
- getjob
- deleterevision
- google cloud run run a job
- google cloud run get a service
- createjob
- listservices
- google cloud run update a job
- run
- createservice
- cloud run
- google cloud run delete a job
slug: google-cloud-run-capability
source_filename: google-cloud-run-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Run Admin API\n  description: The Cloud Run Admin API deploys and manages user-provided container images as serverless services. It supports\n    creating, updating, and deleting services, managing revisions and traffic splitting, executing jobs, and configuring domain\n    mappings.\n  tags:\n  - Google\n  - Cloud\n  - Run\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-run\n    baseUri: https://run.googleapis.com/v2\n    description: Google Cloud Run Admin API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_RUN_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-services\n      path: /projects/{projectId}/locations/{location}/services\n      operations:\n      - name: listservices\n        method: GET\n        description: Google Cloud Run List services\n        inputParameters:\n  \
  \      - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: showDeleted\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createservice\n        method: POST\n        description: Google Cloud Run Create a service\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: serviceId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-services-s\n      path: /projects/{projectId}/locations/{location}/services/{serviceId}\n      operations:\n      - name: getservice\n        method: GET\n        description: Google Cloud Run Get a service\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateservice\n        method: PATCH\n        description: Google Cloud Run Update a service\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n  \
  \        required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteservice\n        method: DELETE\n        description: Google Cloud Run Delete a service\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-services-s\n\
  \      path: /projects/{projectId}/locations/{location}/services/{serviceId}/revisions\n      operations:\n      - name: listrevisions\n        method: GET\n        description: Google Cloud Run List revisions\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: showDeleted\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-services-s\n      path: /projects/{projectId}/locations/{location}/services/{serviceId}/revisions/{revisionId}\n\
  \      operations:\n      - name: getrevision\n        method: GET\n        description: Google Cloud Run Get a revision\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n        - name: revisionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterevision\n        method: DELETE\n        description: Google Cloud Run Delete a revision\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n      \
  \  - name: serviceId\n          in: path\n          type: string\n          required: true\n        - name: revisionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-jobs\n      path: /projects/{projectId}/locations/{location}/jobs\n      operations:\n      - name: listjobs\n        method: GET\n        description: Google Cloud Run List jobs\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: showDeleted\n          in: query\n          type: boolean\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createjob\n        method: POST\n        description: Google Cloud Run Create a job\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-jobs-jobid\n      path: /projects/{projectId}/locations/{location}/jobs/{jobId}\n      operations:\n      - name: getjob\n        method: GET\n        description: Google Cloud Run Get a job\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required:\
  \ true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatejob\n        method: PATCH\n        description: Google Cloud Run Update a job\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletejob\n        method: DELETE\n        description: Google Cloud Run Delete a job\n        inputParameters:\n        -\
  \ name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-jobs-jobid\n      path: /projects/{projectId}/locations/{location}/jobs/{jobId}:run\n      operations:\n      - name: runjob\n        method: POST\n        description: Google Cloud Run Run a job\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: jobId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-run-rest\n    description: REST adapter for Google Cloud Run Admin API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: Google Cloud Run List services\n        call: google-cloud-run.listservices\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/services\n      name: createservice\n      operations:\n      - method: POST\n        name: createservice\n        description: Google Cloud Run Create a service\n        call: google-cloud-run.createservice\n        with:\n          projectId: rest.projectId\n          location:\
  \ rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/services/{serviceId}\n      name: getservice\n      operations:\n      - method: GET\n        name: getservice\n        description: Google Cloud Run Get a service\n        call: google-cloud-run.getservice\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/services/{serviceId}\n      name: updateservice\n      operations:\n      - method: PATCH\n        name: updateservice\n        description: Google Cloud Run Update a service\n        call: google-cloud-run.updateservice\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/services/{serviceId}\n      name: deleteservice\n      operations:\n      - method: DELETE\n        name: deleteservice\n        description: Google Cloud Run Delete a service\n        call: google-cloud-run.deleteservice\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/services/{serviceId}/revisions\n      name: listrevisions\n      operations:\n      - method: GET\n        name: listrevisions\n        description: Google Cloud Run List revisions\n        call: google-cloud-run.listrevisions\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/services/{serviceId}/revisions/{revisionId}\n\
  \      name: getrevision\n      operations:\n      - method: GET\n        name: getrevision\n        description: Google Cloud Run Get a revision\n        call: google-cloud-run.getrevision\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          serviceId: rest.serviceId\n          revisionId: rest.revisionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/services/{serviceId}/revisions/{revisionId}\n      name: deleterevision\n      operations:\n      - method: DELETE\n        name: deleterevision\n        description: Google Cloud Run Delete a revision\n        call: google-cloud-run.deleterevision\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          serviceId: rest.serviceId\n          revisionId: rest.revisionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/jobs\n\
  \      name: listjobs\n      operations:\n      - method: GET\n        name: listjobs\n        description: Google Cloud Run List jobs\n        call: google-cloud-run.listjobs\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/jobs\n      name: createjob\n      operations:\n      - method: POST\n        name: createjob\n        description: Google Cloud Run Create a job\n        call: google-cloud-run.createjob\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/jobs/{jobId}\n      name: getjob\n      operations:\n      - method: GET\n        name: getjob\n        description: Google Cloud Run Get a job\n        call: google-cloud-run.getjob\n        with:\n  \
  \        projectId: rest.projectId\n          location: rest.location\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/jobs/{jobId}\n      name: updatejob\n      operations:\n      - method: PATCH\n        name: updatejob\n        description: Google Cloud Run Update a job\n        call: google-cloud-run.updatejob\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/jobs/{jobId}\n      name: deletejob\n      operations:\n      - method: DELETE\n        name: deletejob\n        description: Google Cloud Run Delete a job\n        call: google-cloud-run.deletejob\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          jobId: rest.jobId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/jobs/{jobId}:run\n      name: runjob\n      operations:\n      - method: POST\n        name: runjob\n        description: Google Cloud Run Run a job\n        call: google-cloud-run.runjob\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-run-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Run Admin API for AI agent use.\n    tools:\n    - name: listservices\n      description: Google Cloud Run List services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-run.listservices\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken:\
  \ tools.pageToken\n        showDeleted: tools.showDeleted\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: showDeleted\n        type: boolean\n        description: showDeleted\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createservice\n      description: Google Cloud Run Create a service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-run.createservice\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        serviceId: tools.serviceId\n      inputParameters:\n      - name: projectId\n        type: string\n\
  \        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: serviceId\n        type: string\n        description: serviceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservice\n      description: Google Cloud Run Get a service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-run.getservice\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        serviceId: tools.serviceId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: serviceId\n        type: string\n        description: serviceId\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: updateservice\n      description: Google Cloud Run Update a service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-run.updateservice\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        serviceId: tools.serviceId\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: serviceId\n        type: string\n        description: serviceId\n        required: true\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteservice\n      description: Google Cloud Run Delete a service\n      hints:\n    \
  \    readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-run.deleteservice\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        serviceId: tools.serviceId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: serviceId\n        type: string\n        description: serviceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrevisions\n      description: Google Cloud Run List revisions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-run.listrevisions\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        serviceId: tools.serviceId\n        pageSize: tools.pageSize\n\
  \        pageToken: tools.pageToken\n        showDeleted: tools.showDeleted\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: serviceId\n        type: string\n        description: serviceId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: showDeleted\n        type: boolean\n        description: showDeleted\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrevision\n      description: Google Cloud Run Get a revision\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-run.getrevision\n      with:\n        projectId: tools.projectId\n        location: tools.location\n\
  \        serviceId: tools.serviceId\n        revisionId: tools.revisionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: serviceId\n        type: string\n        description: serviceId\n        required: true\n      - name: revisionId\n        type: string\n        description: revisionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterevision\n      description: Google Cloud Run Delete a revision\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-run.deleterevision\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        serviceId: tools.serviceId\n        revisionId: tools.revisionId\n      inputParameters:\n      - name: projectId\n\
  \        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: serviceId\n        type: string\n        description: serviceId\n        required: true\n      - name: revisionId\n        type: string\n        description: revisionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjobs\n      description: Google Cloud Run List jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-run.listjobs\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        showDeleted: tools.showDeleted\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n\
  \        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: showDeleted\n        type: boolean\n        description: showDeleted\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createjob\n      description: Google Cloud Run Create a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-run.createjob\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        jobId: tools.jobId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjob\n      description: Google Cloud Run Get a job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-run.getjob\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        jobId: tools.jobId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatejob\n      description: Google Cloud Run Update a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-run.updatejob\n \
  \     with:\n        projectId: tools.projectId\n        location: tools.location\n        jobId: tools.jobId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletejob\n      description: Google Cloud Run Delete a job\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-run.deletejob\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        jobId: tools.jobId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description:\
  \ location\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runjob\n      description: Google Cloud Run Run a job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-run.runjob\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        jobId: tools.jobId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: jobId\n        type: string\n        description: jobId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_RUN_TOKEN: GOOGLE_CLOUD_RUN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-run/refs/heads/main/capabilities/google-cloud-run-capability.yaml
tags:
- Google
- Cloud
- Run
- API
tools:
- description: Google Cloud Run List services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Google Cloud Run Create a service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createservice
- description: Google Cloud Run Get a service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: Google Cloud Run Update a service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateservice
- description: Google Cloud Run Delete a service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteservice
- description: Google Cloud Run List revisions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrevisions
- description: Google Cloud Run Get a revision
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrevision
- description: Google Cloud Run Delete a revision
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterevision
- description: Google Cloud Run List jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjobs
- description: Google Cloud Run Create a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createjob
- description: Google Cloud Run Get a job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjob
- description: Google Cloud Run Update a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatejob
- description: Google Cloud Run Delete a job
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletejob
- description: Google Cloud Run Run a job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runjob
---
