---
categories: []
consumed_apis:
- database
- object-storage
description: Workflow for managing databases, data storage, and data processing across OCI. Used by data engineers and DBAs.
layout: capability
name: Oracle Cloud Data Platform
operations: []
personas: []
provider_name: Oracle Cloud Infrastructure
provider_slug: oracle-cloud
search_terms:
- workflow for building and deploying containerized and serverless applications on oci. used by application developers.
- manages databases and data pipelines
- cloud computing
- oracle
- oracle cloud
- manages oci infrastructure resources
- builds cloud-native applications
- data platform
- workflow for managing identity, access control, and monitoring across oci. used by security engineers.
- platform as a service
- workflow for managing databases, data storage, and data processing across oci. used by data engineers and dbas.
- enterprise cloud
- infrastructure as a service
- unified workflow for managing compute instances, networking, and storage resources across oci. used by cloud administrators and devops engineers.
- manages security and compliance
slug: data-platform
source_filename: data-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Oracle Cloud Data Platform\n  description: Workflow for managing databases, data storage, and data processing across OCI. Used by data engineers and DBAs.\n  tags:\n  - Oracle Cloud\n  - Data Platform\n  created: '2026-04-18'\n  modified: '2026-04-18'\nbinds:\n- namespace: env\n  keys:\n    OCI_API_KEY: OCI_API_KEY\n    OCI_TENANCY_OCID: OCI_TENANCY_OCID\ncapability:\n  consumes:\n  - import: database\n    location: ./shared/database.yaml\n  - import: object-storage\n    location: ./shared/object-storage.yaml\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: data-platform-api\n    description: Unified REST API for workflow for managing databases, data storage, and data processing across oci.\n  - type: mcp\n    port: 9091\n    namespace: data-platform-mcp\n    transport: http\n    description: MCP server for AI-assisted data platform.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-cloud/refs/heads/main/capabilities/data-platform.yaml
tags:
- Oracle Cloud
- Data Platform
tools: []
---
