---
categories: []
consumed_apis: []
description: Workflow capability for managing Apache CloudStack infrastructure resources including virtual machine lifecycle, network configuration, storage volumes, and zone administration.
layout: capability
name: Cloudstack Iaas Management
operations: []
personas: []
provider_name: Apache CloudStack
provider_slug: apache-cloudstack
search_terms:
- open source
- apache
- virtualization
- iaas
- infrastructure
- cloud
slug: cloudstack-iaas-management
source_filename: cloudstack-iaas-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  title: Apache CloudStack IaaS Management\n  description: >-\n    Workflow capability for managing Apache CloudStack infrastructure resources including\n    virtual machine lifecycle, network configuration, storage volumes, and zone administration.\n  version: 4.19.0\n  contact:\n    name: Apache CloudStack Community\n    url: https://cloudstack.apache.org/\n\nservers:\n  rest:\n    url: http://localhost:8080/client/api\n    port: 8080\n  mcp:\n    port: 9090\n\ntools:\n  - name: manage-virtual-machines\n    description: Deploy, start, stop, and list virtual machines in a CloudStack zone.\n    operations:\n      - $ref: shared/cloudstack-api.yaml#/operations/deployVirtualMachine\n      - $ref: shared/cloudstack-api.yaml#/operations/listVirtualMachines\n      - $ref: shared/cloudstack-api.yaml#/operations/startVirtualMachine\n      - $ref: shared/cloudstack-api.yaml#/operations/stopVirtualMachine\n\n  - name: poll-async-jobs\n    description: Poll\
  \ the status of asynchronous CloudStack operations until completion.\n    operations:\n      - $ref: shared/cloudstack-api.yaml#/operations/queryAsyncJobResult\n\n  - name: list-networks\n    description: Browse available networks in a CloudStack zone for VM placement.\n    operations:\n      - $ref: shared/cloudstack-api.yaml#/operations/listNetworks\n\n  - name: manage-volumes\n    description: List and inspect storage volumes attached to virtual machines.\n    operations:\n      - $ref: shared/cloudstack-api.yaml#/operations/listVolumes\n\n  - name: browse-zones\n    description: List all availability zones to identify where to deploy resources.\n    operations:\n      - $ref: shared/cloudstack-api.yaml#/operations/listZones\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-cloudstack/refs/heads/main/capabilities/cloudstack-iaas-management.yaml
tags: []
tools: []
---
