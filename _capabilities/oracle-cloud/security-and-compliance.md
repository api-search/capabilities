---
categories: []
consumed_apis:
- iam
- monitoring
description: Workflow for managing identity, access control, and monitoring across OCI. Used by security engineers.
layout: capability
name: Oracle Cloud Security and Compliance
operations: []
personas: []
provider_name: Oracle Cloud Infrastructure
provider_slug: oracle-cloud
search_terms:
- security and compliance
- manages databases and data pipelines
- workflow for building and deploying containerized and serverless applications on oci. used by application developers.
- workflow for managing databases, data storage, and data processing across oci. used by data engineers and dbas.
- manages oci infrastructure resources
- workflow for managing identity, access control, and monitoring across oci. used by security engineers.
- enterprise cloud
- oracle
- infrastructure as a service
- unified workflow for managing compute instances, networking, and storage resources across oci. used by cloud administrators and devops engineers.
- oracle cloud
- builds cloud-native applications
- manages security and compliance
- platform as a service
- cloud computing
slug: security-and-compliance
source_filename: security-and-compliance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Oracle Cloud Security and Compliance\n  description: Workflow for managing identity, access control, and monitoring across OCI. Used by security engineers.\n  tags:\n  - Oracle Cloud\n  - Security And Compliance\n  created: '2026-04-18'\n  modified: '2026-04-18'\nbinds:\n- namespace: env\n  keys:\n    OCI_API_KEY: OCI_API_KEY\n    OCI_TENANCY_OCID: OCI_TENANCY_OCID\ncapability:\n  consumes:\n  - import: iam\n    location: ./shared/iam.yaml\n  - import: monitoring\n    location: ./shared/monitoring.yaml\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: security-and-compliance-api\n    description: Unified REST API for workflow for managing identity, access control, and monitoring across oci.\n  - type: mcp\n    port: 9093\n    namespace: security-and-compliance-mcp\n    transport: http\n    description: MCP server for AI-assisted security and compliance.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-cloud/refs/heads/main/capabilities/security-and-compliance.yaml
tags:
- Oracle Cloud
- Security And Compliance
tools: []
---
