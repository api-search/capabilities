---
categories: []
consumed_apis: []
description: REST API for uploading, validating, publishing, and dropping deployment bundles on the Sonatype Central Portal. Replaces the legacy OSSRH staging workflow for releasing open source libraries to Maven Central.
layout: capability
name: Sonatype Central Portal Publishing API
operations:
- description: Upload a deployment bundle
  method: POST
  name: uploadbundle
  path: /upload
- description: Get deployment status
  method: POST
  name: getdeploymentstatus
  path: /status
- description: Publish a deployment
  method: POST
  name: publishdeployment
  path: /deployment/{deploymentId}
- description: Drop a deployment
  method: DELETE
  name: dropdeployment
  path: /deployment/{deploymentId}
- description: Download from a specific deployment
  method: GET
  name: downloaddeploymentfile
  path: /deployment/{deploymentId}/download/{relativePath}
- description: Download from any validated deployment
  method: GET
  name: downloadvalidatedfile
  path: /deployments/download/{relativePath}
personas: []
provider_name: Maven
provider_slug: maven
search_terms:
- publishdeployment
- download from a specific deployment
- java
- artifacts
- upload a deployment bundle
- package management
- downloadvalidatedfile
- dropdeployment
- build tools
- getdeploymentstatus
- api
- get deployment status
- download from any validated deployment
- repository
- publish a deployment
- downloaddeploymentfile
- maven
- uploadbundle
- drop a deployment
slug: maven-capability
source_filename: maven-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sonatype Central Portal Publishing API\n  description: REST API for uploading, validating, publishing, and dropping deployment bundles on the Sonatype Central Portal.\n    Replaces the legacy OSSRH staging workflow for releasing open source libraries to Maven Central.\n  tags:\n  - Maven\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: maven\n    baseUri: https://central.sonatype.com/api/v1/publisher\n    description: Sonatype Central Portal Publishing API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MAVEN_TOKEN}}'\n    resources:\n    - name: upload\n      path: /upload\n      operations:\n      - name: uploadbundle\n        method: POST\n        description: Upload a deployment bundle\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Human-readable deployment name.\n        - name:\
  \ publishingType\n          in: query\n          type: string\n          description: Whether to auto-publish on validation success.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status\n      path: /status\n      operations:\n      - name: getdeploymentstatus\n        method: POST\n        description: Get deployment status\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: Deployment identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment-deploymentid\n      path: /deployment/{deploymentId}\n      operations:\n      - name: publishdeployment\n        method: POST\n        description: Publish a deployment\n        inputParameters:\n        - name: deploymentId\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: dropdeployment\n        method: DELETE\n        description: Drop a deployment\n        inputParameters:\n        - name: deploymentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment-deploymentid-download-relativepath\n      path: /deployment/{deploymentId}/download/{relativePath}\n      operations:\n      - name: downloaddeploymentfile\n        method: GET\n        description: Download from a specific deployment\n        inputParameters:\n        - name: deploymentId\n          in: path\n          type: string\n          required: true\n        - name: relativePath\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments-download-relativepath\n      path: /deployments/download/{relativePath}\n      operations:\n      - name: downloadvalidatedfile\n        method: GET\n        description: Download from any validated deployment\n        inputParameters:\n        - name: relativePath\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: maven-rest\n    description: REST adapter for Sonatype Central Portal Publishing API.\n    resources:\n    - path: /upload\n      name: uploadbundle\n      operations:\n      - method: POST\n        name: uploadbundle\n        description: Upload a deployment bundle\n        call: maven.uploadbundle\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /status\n      name: getdeploymentstatus\n      operations:\n      - method: POST\n        name: getdeploymentstatus\n        description: Get deployment status\n        call: maven.getdeploymentstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployment/{deploymentId}\n      name: publishdeployment\n      operations:\n      - method: POST\n        name: publishdeployment\n        description: Publish a deployment\n        call: maven.publishdeployment\n        with:\n          deploymentId: rest.deploymentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployment/{deploymentId}\n      name: dropdeployment\n      operations:\n      - method: DELETE\n        name: dropdeployment\n        description: Drop a deployment\n        call: maven.dropdeployment\n        with:\n          deploymentId: rest.deploymentId\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /deployment/{deploymentId}/download/{relativePath}\n      name: downloaddeploymentfile\n      operations:\n      - method: GET\n        name: downloaddeploymentfile\n        description: Download from a specific deployment\n        call: maven.downloaddeploymentfile\n        with:\n          deploymentId: rest.deploymentId\n          relativePath: rest.relativePath\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deployments/download/{relativePath}\n      name: downloadvalidatedfile\n      operations:\n      - method: GET\n        name: downloadvalidatedfile\n        description: Download from any validated deployment\n        call: maven.downloadvalidatedfile\n        with:\n          relativePath: rest.relativePath\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: maven-mcp\n    transport: http\n    description: MCP adapter for Sonatype Central\
  \ Portal Publishing API for AI agent use.\n    tools:\n    - name: uploadbundle\n      description: Upload a deployment bundle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: maven.uploadbundle\n      with:\n        name: tools.name\n        publishingType: tools.publishingType\n      inputParameters:\n      - name: name\n        type: string\n        description: Human-readable deployment name.\n      - name: publishingType\n        type: string\n        description: Whether to auto-publish on validation success.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdeploymentstatus\n      description: Get deployment status\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: maven.getdeploymentstatus\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: Deployment identifier.\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publishdeployment\n      description: Publish a deployment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: maven.publishdeployment\n      with:\n        deploymentId: tools.deploymentId\n      inputParameters:\n      - name: deploymentId\n        type: string\n        description: deploymentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dropdeployment\n      description: Drop a deployment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: maven.dropdeployment\n      with:\n        deploymentId: tools.deploymentId\n      inputParameters:\n      - name: deploymentId\n        type: string\n        description: deploymentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: downloaddeploymentfile\n      description: Download from a specific deployment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: maven.downloaddeploymentfile\n      with:\n        deploymentId: tools.deploymentId\n        relativePath: tools.relativePath\n      inputParameters:\n      - name: deploymentId\n        type: string\n        description: deploymentId\n        required: true\n      - name: relativePath\n        type: string\n        description: relativePath\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: downloadvalidatedfile\n      description: Download from any validated deployment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: maven.downloadvalidatedfile\n      with:\n        relativePath: tools.relativePath\n      inputParameters:\n      - name: relativePath\n        type: string\n        description:\
  \ relativePath\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MAVEN_TOKEN: MAVEN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/maven/refs/heads/main/capabilities/maven-capability.yaml
tags:
- Maven
- API
tools:
- description: Upload a deployment bundle
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadbundle
- description: Get deployment status
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getdeploymentstatus
- description: Publish a deployment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishdeployment
- description: Drop a deployment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: dropdeployment
- description: Download from a specific deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloaddeploymentfile
- description: Download from any validated deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadvalidatedfile
---
