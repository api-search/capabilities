---
categories: []
consumed_apis:
- compute
- networking
- object-storage
description: Unified workflow for managing compute instances, networking, and storage resources across OCI. Used by cloud administrators and DevOps engineers.
layout: capability
name: Oracle Cloud Infrastructure Management
operations: []
personas: []
provider_name: Oracle Cloud Infrastructure
provider_slug: oracle-cloud
search_terms:
- unified workflow for managing compute instances, networking, and storage resources across oci. used by cloud administrators and devops engineers.
- workflow for building and deploying containerized and serverless applications on oci. used by application developers.
- oracle
- workflow for managing identity, access control, and monitoring across oci. used by security engineers.
- infrastructure management
- cloud computing
- manages databases and data pipelines
- workflow for managing databases, data storage, and data processing across oci. used by data engineers and dbas.
- builds cloud-native applications
- manages security and compliance
- platform as a service
- enterprise cloud
- infrastructure as a service
- oracle cloud
- manages oci infrastructure resources
slug: infrastructure-management
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Oracle Cloud Infrastructure Management\n  description: Unified workflow for managing compute instances, networking, and storage resources across OCI. Used by cloud administrators and DevOps engineers.\n  tags:\n  - Oracle Cloud\n  - Infrastructure Management\n  created: '2026-04-18'\n  modified: '2026-04-18'\nbinds:\n- namespace: env\n  keys:\n    OCI_API_KEY: OCI_API_KEY\n    OCI_TENANCY_OCID: OCI_TENANCY_OCID\ncapability:\n  consumes:\n  - import: compute\n    location: ./shared/compute.yaml\n  - import: networking\n    location: ./shared/networking.yaml\n  - import: object-storage\n    location: ./shared/object-storage.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: infrastructure-management-api\n    description: Unified REST API for unified workflow for managing compute instances, networking, and storage resources across oci.\n  - type: mcp\n    port: 9090\n    namespace: infrastructure-management-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted infrastructure management.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-cloud/refs/heads/main/capabilities/infrastructure-management.yaml
tags:
- Oracle Cloud
- Infrastructure Management
tools: []
---
