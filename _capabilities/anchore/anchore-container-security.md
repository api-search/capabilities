---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Anchore Container Security
operations: []
personas: []
provider_name: Anchore
provider_slug: anchore
search_terms:
- engineers who manage kubernetes clusters with admission control policies
- software supply chain
- container security
- compliance professionals who require sbom and policy audit trails
- vulnerability scanning
- engineers who integrate security scanning into ci/cd pipelines
- containers
- sbom
- security professionals who review vulnerability reports and set policies
slug: anchore-container-security
source_yaml: "name: anchore-container-security\ndisplayName: Anchore Container Security\ndescription: >-\n  Workflow capability for container image vulnerability scanning, SBOM generation,\n  and policy-based compliance enforcement using the Anchore Enterprise API.\nversion: '1.0'\nprovider: Anchore\n\nshared:\n  anchore-image:\n    description: Container image analyzed by Anchore\n    schema:\n      $ref: '../json-schema/anchore-image-schema.json'\n  anchore-vulnerability:\n    description: Vulnerability found in analyzed image\n    schema:\n      $ref: '../json-schema/anchore-vulnerability-schema.json'\n  anchore-sbom:\n    description: Software Bill of Materials in CycloneDX format\n    schema:\n      $ref: '../json-schema/anchore-sbom-schema.json'\n\nworkflows:\n  - id: scan-and-report\n    name: Scan Image and Report Vulnerabilities\n    description: Analyze a container image and retrieve its vulnerability report\n    steps:\n      - id: add-image\n        operation: addImage\n    \
  \    description: Submit image for analysis\n      - id: check-status\n        operation: getImage\n        description: Poll image analysis status\n      - id: get-vulns\n        operation: getImageVulnerabilities\n        description: Retrieve vulnerability report\n        params:\n          vtype: all\n      - id: check-policy\n        operation: checkImagePolicy\n        description: Evaluate policy compliance\n\n  - id: generate-sbom\n    name: Generate SBOM\n    description: Analyze an image and retrieve its Software Bill of Materials\n    steps:\n      - id: add-image\n        operation: addImage\n      - id: get-sbom\n        operation: getImageSbom\n\nadapters:\n  rest:\n    baseUrl: https://anchore.example.com/v2\n    openapi: ../openapi/anchore-enterprise-api.yaml\n    auth:\n      type: basic\n  mcp:\n    port: 9090\n    tools:\n      - id: scan-image\n        operation: addImage\n        description: Submit a container image for vulnerability scanning\n      - id: get-vulnerabilities\n\
  \        operation: getImageVulnerabilities\n        description: Get vulnerabilities for a scanned image\n      - id: get-sbom\n        operation: getImageSbom\n        description: Get Software Bill of Materials for a scanned image\n      - id: check-policy\n        operation: checkImagePolicy\n        description: Check if an image passes security policies\n      - id: list-images\n        operation: listImages\n        description: List all analyzed container images\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/anchore/refs/heads/main/capabilities/anchore-container-security.yaml
tags: []
tools: []
---
