---
api_specs:
- filename: hcp-terraform-openapi.yml
  format: yaml
  label: hcp-terraform
  slug: hcp-terraform
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/terraform/refs/heads/main/openapi/hcp-terraform-openapi.yml
- filename: terraform-registry-openapi.yml
  format: yaml
  label: terraform-registry
  slug: terraform-registry
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/terraform/refs/heads/main/openapi/terraform-registry-openapi.yml
categories: []
consumed_apis:
- hcp-terraform
- terraform-registry
description: 'Unified workflow capability for infrastructure automation with Terraform. Combines HCP Terraform workspace management and run orchestration with module discovery from the Terraform Registry. Enables platform engineers, DevOps teams, and SREs to manage the full infrastructure lifecycle: discover modules, provision workspaces, trigger runs, and manage state.'
layout: capability
name: Terraform Infrastructure Automation
operations:
- description: List all accessible organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: List workspaces in an organization
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: Create a new workspace
  method: POST
  name: create-workspace
  path: /v1/workspaces
- description: Get workspace details
  method: GET
  name: get-workspace
  path: /v1/workspaces/{workspace_id}
- description: Trigger a Terraform run
  method: POST
  name: create-run
  path: /v1/runs
- description: List runs for a workspace
  method: GET
  name: list-workspace-runs
  path: /v1/workspaces/{workspace_id}/runs
- description: List state versions for a workspace
  method: GET
  name: list-state-versions
  path: /v1/workspaces/{workspace_id}/state-versions
- description: Browse Terraform modules from the registry
  method: GET
  name: list-modules
  path: /v1/modules
- description: Search Terraform registry modules
  method: GET
  name: search-modules
  path: /v1/modules/search
- description: List teams in an organization
  method: GET
  name: list-teams
  path: /v1/teams
- description: List governance policies
  method: GET
  name: list-policies
  path: /v1/policies
personas: []
provider_name: Terraform
provider_slug: terraform
search_terms:
- list state versions
- list terraform workspaces in an organization
- manage terraform organizations
- workspaces
- list organizations
- browse terraform modules from the registry
- policy management
- list governance policies (sentinel/opa) in an organization
- create a new workspace
- terraform run management
- workspace state version history
- list teams in an organization
- cloud infrastructure
- terraform
- list workspaces in an organization
- list modules
- get run
- open source
- list available versions of a terraform module
- apply a terraform run that is pending approval
- list and manage workspaces
- list all terraform organizations accessible with the current token
- single workspace operations
- list all accessible organizations
- get details of a specific terraform workspace
- trigger a new terraform infrastructure run
- platform engineering
- list state versions for a terraform workspace
- list state versions for a workspace
- list teams in a terraform organization
- create run
- devops
- lock workspace
- search terraform registry modules
- get workspace
- list governance policies
- lock a terraform workspace to prevent runs
- list module versions
- runs
- get module version
- list the run history for a terraform workspace
- apply run
- get details for a specific version of a terraform module
- list workspace runs
- list teams
- terraform module discovery
- search modules
- list workspaces
- team management
- get workspace details
- unlock a terraform workspace to allow runs
- unlock workspace
- discard run
- workspace run history
- discard a pending terraform run
- search terraform registry for reusable infrastructure modules
- create a new terraform workspace
- infrastructure as code
- trigger a terraform run
- hashicorp
- create workspace
- list runs for a workspace
- list policies
- get the status and details of a terraform run
slug: infrastructure-automation
source_filename: infrastructure-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Terraform Infrastructure Automation\"\n  description: >-\n    Unified workflow capability for infrastructure automation with Terraform.\n    Combines HCP Terraform workspace management and run orchestration with\n    module discovery from the Terraform Registry. Enables platform engineers,\n    DevOps teams, and SREs to manage the full infrastructure lifecycle:\n    discover modules, provision workspaces, trigger runs, and manage state.\n  tags:\n    - Terraform\n    - Infrastructure As Code\n    - DevOps\n    - Platform Engineering\n    - HashiCorp\n    - Workspaces\n    - Runs\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      HCP_TERRAFORM_TOKEN: HCP_TERRAFORM_TOKEN\n\ncapability:\n  consumes:\n    - import: hcp-terraform\n      location: ./shared/hcp-terraform.yaml\n    - import: terraform-registry\n      location: ./shared/terraform-registry.yaml\n\n  exposes:\n    - type:\
  \ rest\n      port: 8080\n      namespace: terraform-automation-api\n      description: \"Unified REST API for Terraform infrastructure automation workflows.\"\n      resources:\n        - path: /v1/organizations\n          name: organizations\n          description: \"Manage Terraform organizations\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List all accessible organizations\"\n              call: \"hcp-terraform.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces\n          name: workspaces\n          description: \"List and manage workspaces\"\n          operations:\n            - method: GET\n              name: list-workspaces\n              description: \"List workspaces in an organization\"\n              call: \"hcp-terraform.list-workspaces\"\n              with:\n                organization_name: \"\
  rest.organization_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workspace\n              description: \"Create a new workspace\"\n              call: \"hcp-terraform.create-workspace\"\n              with:\n                organization_name: \"rest.organization_name\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces/{workspace_id}\n          name: workspace\n          description: \"Single workspace operations\"\n          operations:\n            - method: GET\n              name: get-workspace\n              description: \"Get workspace details\"\n              call: \"hcp-terraform.get-workspace\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n              \
  \    mapping: \"$.\"\n        - path: /v1/runs\n          name: runs\n          description: \"Terraform run management\"\n          operations:\n            - method: POST\n              name: create-run\n              description: \"Trigger a Terraform run\"\n              call: \"hcp-terraform.create-run\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n                message: \"rest.message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces/{workspace_id}/runs\n          name: workspace-runs\n          description: \"Workspace run history\"\n          operations:\n            - method: GET\n              name: list-workspace-runs\n              description: \"List runs for a workspace\"\n              call: \"hcp-terraform.list-workspace-runs\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/workspaces/{workspace_id}/state-versions\n          name: state-versions\n          description: \"Workspace state version history\"\n          operations:\n            - method: GET\n              name: list-state-versions\n              description: \"List state versions for a workspace\"\n              call: \"hcp-terraform.list-state-versions\"\n              with:\n                workspace_id: \"rest.workspace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/modules\n          name: modules\n          description: \"Terraform module discovery\"\n          operations:\n            - method: GET\n              name: list-modules\n              description: \"Browse Terraform modules from the registry\"\n              call: \"terraform-registry.list-modules\"\n              with:\n                provider: \"rest.provider\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/modules/search\n          name: module-search\n          description: \"Search modules\"\n          operations:\n            - method: GET\n              name: search-modules\n              description: \"Search Terraform registry modules\"\n              call: \"terraform-registry.search-modules\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/teams\n          name: teams\n          description: \"Team management\"\n          operations:\n            - method: GET\n              name: list-teams\n              description: \"List teams in an organization\"\n              call: \"hcp-terraform.list-teams\"\n              with:\n                organization_name: \"rest.organization_name\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/policies\n          name: policies\n          description: \"Policy management\"\n          operations:\n            - method: GET\n              name: list-policies\n              description: \"List governance policies\"\n              call: \"hcp-terraform.list-policies\"\n              with:\n                organization_name: \"rest.organization_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: terraform-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Terraform infrastructure automation.\"\n      tools:\n        - name: list-organizations\n          description: \"List all Terraform organizations accessible with the current token\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcp-terraform.list-organizations\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: list-workspaces\n          description: \"List Terraform workspaces in an organization\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcp-terraform.list-workspaces\"\n          with:\n            organization_name: \"tools.organization_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workspace\n          description: \"Get details of a specific Terraform workspace\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"hcp-terraform.get-workspace\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workspace\n          description: \"Create a new Terraform workspace\"\n          hints:\n            readOnly: false\n            destructive: false\n  \
  \        call: \"hcp-terraform.create-workspace\"\n          with:\n            organization_name: \"tools.organization_name\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lock-workspace\n          description: \"Lock a Terraform workspace to prevent runs\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"hcp-terraform.lock-workspace\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: unlock-workspace\n          description: \"Unlock a Terraform workspace to allow runs\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"hcp-terraform.unlock-workspace\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-run\n          description: \"Trigger a new Terraform infrastructure run\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"hcp-terraform.create-run\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n            message: \"tools.message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-run\n          description: \"Get the status and details of a Terraform run\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"hcp-terraform.get-run\"\n          with:\n            run_id: \"tools.run_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: apply-run\n          description: \"Apply a Terraform run that is pending approval\"\n          hints:\n          \
  \  readOnly: false\n            destructive: false\n          call: \"hcp-terraform.apply-run\"\n          with:\n            run_id: \"tools.run_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: discard-run\n          description: \"Discard a pending Terraform run\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"hcp-terraform.discard-run\"\n          with:\n            run_id: \"tools.run_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workspace-runs\n          description: \"List the run history for a Terraform workspace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcp-terraform.list-workspace-runs\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n     \
  \         mapping: \"$.\"\n        - name: list-state-versions\n          description: \"List state versions for a Terraform workspace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcp-terraform.list-state-versions\"\n          with:\n            workspace_id: \"tools.workspace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-teams\n          description: \"List teams in a Terraform organization\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcp-terraform.list-teams\"\n          with:\n            organization_name: \"tools.organization_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-policies\n          description: \"List governance policies (Sentinel/OPA) in an organization\"\n          hints:\n            readOnly: true\n            openWorld: true\n  \
  \        call: \"hcp-terraform.list-policies\"\n          with:\n            organization_name: \"tools.organization_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-modules\n          description: \"Search Terraform Registry for reusable infrastructure modules\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"terraform-registry.search-modules\"\n          with:\n            q: \"tools.q\"\n            provider: \"tools.provider\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-module-versions\n          description: \"List available versions of a Terraform module\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"terraform-registry.list-module-versions\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n            provider:\
  \ \"tools.provider\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-module-version\n          description: \"Get details for a specific version of a Terraform module\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"terraform-registry.get-module-version\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n            provider: \"tools.provider\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/terraform/refs/heads/main/capabilities/infrastructure-automation.yaml
tags:
- Terraform
- Infrastructure As Code
- DevOps
- Platform Engineering
- HashiCorp
- Workspaces
- Runs
tools:
- description: List all Terraform organizations accessible with the current token
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List Terraform workspaces in an organization
  hints:
    openWorld: true
    readOnly: true
  name: list-workspaces
- description: Get details of a specific Terraform workspace
  hints:
    openWorld: false
    readOnly: true
  name: get-workspace
- description: Create a new Terraform workspace
  hints:
    destructive: false
    readOnly: false
  name: create-workspace
- description: Lock a Terraform workspace to prevent runs
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: lock-workspace
- description: Unlock a Terraform workspace to allow runs
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unlock-workspace
- description: Trigger a new Terraform infrastructure run
  hints:
    destructive: false
    readOnly: false
  name: create-run
- description: Get the status and details of a Terraform run
  hints:
    openWorld: false
    readOnly: true
  name: get-run
- description: Apply a Terraform run that is pending approval
  hints:
    destructive: false
    readOnly: false
  name: apply-run
- description: Discard a pending Terraform run
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: discard-run
- description: List the run history for a Terraform workspace
  hints:
    openWorld: true
    readOnly: true
  name: list-workspace-runs
- description: List state versions for a Terraform workspace
  hints:
    openWorld: true
    readOnly: true
  name: list-state-versions
- description: List teams in a Terraform organization
  hints:
    openWorld: true
    readOnly: true
  name: list-teams
- description: List governance policies (Sentinel/OPA) in an organization
  hints:
    openWorld: true
    readOnly: true
  name: list-policies
- description: Search Terraform Registry for reusable infrastructure modules
  hints:
    openWorld: true
    readOnly: true
  name: search-modules
- description: List available versions of a Terraform module
  hints:
    openWorld: false
    readOnly: true
  name: list-module-versions
- description: Get details for a specific version of a Terraform module
  hints:
    openWorld: false
    readOnly: true
  name: get-module-version
---
