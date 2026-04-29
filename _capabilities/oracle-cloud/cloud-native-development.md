---
categories: []
consumed_apis:
- oke
- functions
description: Workflow for building and deploying containerized and serverless applications on OCI. Used by application developers.
layout: capability
name: Oracle Cloud Cloud Native Development
operations: []
personas: []
provider_name: Oracle Cloud Infrastructure
provider_slug: oracle-cloud
search_terms:
- cloud computing
- enterprise cloud
- oracle
- unified workflow for managing compute instances, networking, and storage resources across oci. used by cloud administrators and devops engineers.
- oracle cloud
- builds cloud-native applications
- infrastructure as a service
- cloud native development
- workflow for building and deploying containerized and serverless applications on oci. used by application developers.
- manages oci infrastructure resources
- platform as a service
- workflow for managing databases, data storage, and data processing across oci. used by data engineers and dbas.
- workflow for managing identity, access control, and monitoring across oci. used by security engineers.
- manages security and compliance
- manages databases and data pipelines
slug: cloud-native-development
source_filename: cloud-native-development.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Oracle Cloud Cloud Native Development\n  description: Workflow for building and deploying containerized and serverless applications on OCI. Used by application developers.\n  tags:\n  - Oracle Cloud\n  - Cloud Native Development\n  created: '2026-04-18'\n  modified: '2026-04-18'\nbinds:\n- namespace: env\n  keys:\n    OCI_API_KEY: OCI_API_KEY\n    OCI_TENANCY_OCID: OCI_TENANCY_OCID\ncapability:\n  consumes:\n  - import: oke\n    location: ./shared/oke.yaml\n  - import: functions\n    location: ./shared/functions.yaml\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: cloud-native-development-api\n    description: Unified REST API for workflow for building and deploying containerized and serverless applications on oci.\n  - type: mcp\n    port: 9092\n    namespace: cloud-native-development-mcp\n    transport: http\n    description: MCP server for AI-assisted cloud native development.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-cloud/refs/heads/main/capabilities/cloud-native-development.yaml
tags:
- Oracle Cloud
- Cloud Native Development
tools: []
---
