---
categories: []
consumed_apis: []
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
- policy management
- list workspaces
- devops
- list runs for a workspace
- list teams in a terraform organization
- list modules
- hashicorp
- list all accessible organizations
- runs
- list the run history for a terraform workspace
- list and manage workspaces
- list governance policies (sentinel/opa) in an organization
- list teams in an organization
- team management
- lock a terraform workspace to prevent runs
- get module version
- create run
- apply a terraform run that is pending approval
- list workspace runs
- open source
- search terraform registry modules
- list workspaces in an organization
- list teams
- create workspace
- get workspace details
- manage terraform organizations
- search modules
- list all terraform organizations accessible with the current token
- unlock a terraform workspace to allow runs
- apply run
- terraform module discovery
- list state versions for a workspace
- list available versions of a terraform module
- create a new terraform workspace
- get details of a specific terraform workspace
- discard a pending terraform run
- discard run
- unlock workspace
- trigger a new terraform infrastructure run
- list organizations
- list policies
- list state versions for a terraform workspace
- cloud infrastructure
- list terraform workspaces in an organization
- single workspace operations
- infrastructure as code
- workspace state version history
- lock workspace
- search terraform registry for reusable infrastructure modules
- trigger a terraform run
- workspace run history
- create a new workspace
- list module versions
- list governance policies
- workspaces
- get details for a specific version of a terraform module
- list state versions
- terraform
- terraform run management
- get run
- browse terraform modules from the registry
- get workspace
- get the status and details of a terraform run
- platform engineering
slug: infrastructure-automation
source_filename: infrastructure-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Terraform Infrastructure Automation\n  description: 'Unified workflow capability for infrastructure automation with Terraform. Combines HCP Terraform workspace\n    management and run orchestration with module discovery from the Terraform Registry. Enables platform engineers, DevOps\n    teams, and SREs to manage the full infrastructure lifecycle: discover modules, provision workspaces, trigger runs, and\n    manage state.'\n  tags:\n  - Terraform\n  - Infrastructure As Code\n  - DevOps\n  - Platform Engineering\n  - HashiCorp\n  - Workspaces\n  - Runs\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HCP_TERRAFORM_TOKEN: HCP_TERRAFORM_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: hcp-terraform\n    baseUri: https://app.terraform.io/api/v2\n    description: HCP Terraform REST API using JSON API spec\n    authentication:\n      type: bearer\n      token: '{{HCP_TERRAFORM_TOKEN}}'\n\
  \    resources:\n    - name: organizations\n      path: /organizations\n      description: Manage HCP Terraform organizations\n      operations:\n      - name: list-organizations\n        method: GET\n        description: List all organizations accessible by the current token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-organization\n        method: POST\n        description: Create a new organization\n        body:\n          type: json\n          data:\n            data:\n              type: organizations\n              attributes:\n                name: '{{tools.name}}'\n                email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization\n      path: /organizations/{organization_name}\n      description: Manage a specific organization\n      operations:\n \
  \     - name: get-organization\n        method: GET\n        description: Get details of a specific organization\n        inputParameters:\n        - name: organization_name\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-organization\n        method: DELETE\n        description: Delete an organization\n        inputParameters:\n        - name: organization_name\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /organizations/{organization_name}/workspaces\n      description: Manage workspaces within an organization\n      operations:\n      - name: list-workspaces\n\
  \        method: GET\n        description: List all workspaces in an organization\n        inputParameters:\n        - name: organization_name\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        - name: search[name]\n          in: query\n          type: string\n          required: false\n          description: Filter workspaces by name\n        - name: page[number]\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: page[size]\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-workspace\n        method: POST\n        description: Create a new workspace\n        inputParameters:\n        - name: organization_name\n          in: path\n          type:\
  \ string\n          required: true\n          description: Organization name\n        body:\n          type: json\n          data:\n            data:\n              type: workspaces\n              attributes:\n                name: '{{tools.name}}'\n                description: '{{tools.description}}'\n                auto-apply: '{{tools.auto_apply}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspace\n      path: /workspaces/{workspace_id}\n      description: Manage a specific workspace\n      operations:\n      - name: get-workspace\n        method: GET\n        description: Get details of a specific workspace\n        inputParameters:\n        - name: workspace_id\n          in: path\n          type: string\n          required: true\n          description: Workspace ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n      - name: delete-workspace\n        method: DELETE\n        description: Delete a workspace\n        inputParameters:\n        - name: workspace_id\n          in: path\n          type: string\n          required: true\n          description: Workspace ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspace-lock\n      path: /workspaces/{workspace_id}/actions/lock\n      description: Lock a workspace to prevent runs\n      operations:\n      - name: lock-workspace\n        method: POST\n        description: Lock a workspace\n        inputParameters:\n        - name: workspace_id\n          in: path\n          type: string\n          required: true\n          description: Workspace ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspace-unlock\n      path: /workspaces/{workspace_id}/actions/unlock\n\
  \      description: Unlock a workspace to allow runs\n      operations:\n      - name: unlock-workspace\n        method: POST\n        description: Unlock a workspace\n        inputParameters:\n        - name: workspace_id\n          in: path\n          type: string\n          required: true\n          description: Workspace ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runs\n      path: /runs\n      description: Create Terraform runs\n      operations:\n      - name: create-run\n        method: POST\n        description: Create a new Terraform run for a workspace\n        body:\n          type: json\n          data:\n            data:\n              type: runs\n              attributes:\n                message: '{{tools.message}}'\n                is-destroy: '{{tools.is_destroy}}'\n              relationships:\n                workspace:\n                  data:\n                    type:\
  \ workspaces\n                    id: '{{tools.workspace_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: run\n      path: /runs/{run_id}\n      description: Manage a specific run\n      operations:\n      - name: get-run\n        method: GET\n        description: Get details of a specific run\n        inputParameters:\n        - name: run_id\n          in: path\n          type: string\n          required: true\n          description: Run ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: run-apply\n      path: /runs/{run_id}/actions/apply\n      description: Apply a run\n      operations:\n      - name: apply-run\n        method: POST\n        description: Apply a run that is pending confirmation\n        inputParameters:\n        - name: run_id\n          in: path\n          type: string\n        \
  \  required: true\n          description: Run ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: run-discard\n      path: /runs/{run_id}/actions/discard\n      description: Discard a run\n      operations:\n      - name: discard-run\n        method: POST\n        description: Discard a run that has not yet been applied\n        inputParameters:\n        - name: run_id\n          in: path\n          type: string\n          required: true\n          description: Run ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspace-runs\n      path: /workspaces/{workspace_id}/runs\n      description: List runs for a workspace\n      operations:\n      - name: list-workspace-runs\n        method: GET\n        description: List all runs for a given workspace\n        inputParameters:\n        - name: workspace_id\n\
  \          in: path\n          type: string\n          required: true\n          description: Workspace ID\n        - name: filter[status]\n          in: query\n          type: string\n          required: false\n          description: Filter by run status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: state-versions\n      path: /workspaces/{workspace_id}/state-versions\n      description: Manage workspace state versions\n      operations:\n      - name: list-state-versions\n        method: GET\n        description: List state versions for a workspace\n        inputParameters:\n        - name: workspace_id\n          in: path\n          type: string\n          required: true\n          description: Workspace ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /organizations/{organization_name}/teams\n\
  \      description: Manage organization teams\n      operations:\n      - name: list-teams\n        method: GET\n        description: List all teams in an organization\n        inputParameters:\n        - name: organization_name\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-team\n        method: POST\n        description: Create a new team\n        inputParameters:\n        - name: organization_name\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        body:\n          type: json\n          data:\n            data:\n              type: teams\n              attributes:\n                name: '{{tools.name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: policies\n      path: /organizations/{organization_name}/policies\n      description: Manage Sentinel and OPA policies\n      operations:\n      - name: list-policies\n        method: GET\n        description: List all policies in an organization\n        inputParameters:\n        - name: organization_name\n          in: path\n          type: string\n          required: true\n          description: Organization name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: terraform-registry\n    baseUri: https://registry.terraform.io\n    description: Terraform Public Registry API (no authentication required)\n    resources:\n    - name: modules\n      path: /v1/modules\n      description: List all modules in the registry\n      operations:\n      - name: list-modules\n        method: GET\n        description: List modules with optional filtering\n   \
  \     inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: provider\n          in: query\n          type: string\n          required: false\n          description: Filter by provider\n        - name: verified\n          in: query\n          type: boolean\n          required: false\n          description: Show only verified modules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: modules-search\n      path: /v1/modules/search\n      description: Search modules by keyword\n      operations:\n      - name: search-modules\n        method: GET\n        description: Search modules by keyword or phrase\n        inputParameters:\n        - name: q\n\
  \          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: provider\n          in: query\n          type: string\n          required: false\n          description: Filter by provider\n        - name: verified\n          in: query\n          type: boolean\n          required: false\n          description: Show only verified modules\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: module-versions\n      path: /v1/modules/{namespace}/{name}/{provider}/versions\n      description: List versions of a specific module\n      operations:\n      - name: list-module-versions\n        method: GET\n        description: List all available versions of a module\n        inputParameters:\n        - name: namespace\n \
  \         in: path\n          type: string\n          required: true\n          description: Module namespace\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Module name\n        - name: provider\n          in: path\n          type: string\n          required: true\n          description: Provider name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: module-version\n      path: /v1/modules/{namespace}/{name}/{provider}/{version}\n      description: Get a specific module version\n      operations:\n      - name: get-module-version\n        method: GET\n        description: Get details for a specific module version\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Module namespace\n        - name: name\n          in: path\n          type:\
  \ string\n          required: true\n          description: Module name\n        - name: provider\n          in: path\n          type: string\n          required: true\n          description: Provider name\n        - name: version\n          in: path\n          type: string\n          required: true\n          description: Version number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: terraform-automation-api\n    description: Unified REST API for Terraform infrastructure automation workflows.\n    resources:\n    - path: /v1/organizations\n      name: organizations\n      description: Manage Terraform organizations\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List all accessible organizations\n        call: hcp-terraform.list-organizations\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /v1/workspaces\n      name: workspaces\n      description: List and manage workspaces\n      operations:\n      - method: GET\n        name: list-workspaces\n        description: List workspaces in an organization\n        call: hcp-terraform.list-workspaces\n        with:\n          organization_name: rest.organization_name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-workspace\n        description: Create a new workspace\n        call: hcp-terraform.create-workspace\n        with:\n          organization_name: rest.organization_name\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces/{workspace_id}\n      name: workspace\n      description: Single workspace operations\n      operations:\n      - method: GET\n        name: get-workspace\n        description: Get workspace details\n        call: hcp-terraform.get-workspace\n\
  \        with:\n          workspace_id: rest.workspace_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs\n      name: runs\n      description: Terraform run management\n      operations:\n      - method: POST\n        name: create-run\n        description: Trigger a Terraform run\n        call: hcp-terraform.create-run\n        with:\n          workspace_id: rest.workspace_id\n          message: rest.message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces/{workspace_id}/runs\n      name: workspace-runs\n      description: Workspace run history\n      operations:\n      - method: GET\n        name: list-workspace-runs\n        description: List runs for a workspace\n        call: hcp-terraform.list-workspace-runs\n        with:\n          workspace_id: rest.workspace_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces/{workspace_id}/state-versions\n\
  \      name: state-versions\n      description: Workspace state version history\n      operations:\n      - method: GET\n        name: list-state-versions\n        description: List state versions for a workspace\n        call: hcp-terraform.list-state-versions\n        with:\n          workspace_id: rest.workspace_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/modules\n      name: modules\n      description: Terraform module discovery\n      operations:\n      - method: GET\n        name: list-modules\n        description: Browse Terraform modules from the registry\n        call: terraform-registry.list-modules\n        with:\n          provider: rest.provider\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/modules/search\n      name: module-search\n      description: Search modules\n      operations:\n      - method: GET\n        name: search-modules\n        description: Search Terraform registry\
  \ modules\n        call: terraform-registry.search-modules\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams\n      name: teams\n      description: Team management\n      operations:\n      - method: GET\n        name: list-teams\n        description: List teams in an organization\n        call: hcp-terraform.list-teams\n        with:\n          organization_name: rest.organization_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies\n      name: policies\n      description: Policy management\n      operations:\n      - method: GET\n        name: list-policies\n        description: List governance policies\n        call: hcp-terraform.list-policies\n        with:\n          organization_name: rest.organization_name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: terraform-automation-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted Terraform infrastructure automation.\n    tools:\n    - name: list-organizations\n      description: List all Terraform organizations accessible with the current token\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hcp-terraform.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n      description: List Terraform workspaces in an organization\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hcp-terraform.list-workspaces\n      with:\n        organization_name: tools.organization_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workspace\n      description: Get details of a specific Terraform workspace\n      hints:\n        readOnly: true\n        openWorld: false\n      call: hcp-terraform.get-workspace\n      with:\n        workspace_id: tools.workspace_id\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workspace\n      description: Create a new Terraform workspace\n      hints:\n        readOnly: false\n        destructive: false\n      call: hcp-terraform.create-workspace\n      with:\n        organization_name: tools.organization_name\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lock-workspace\n      description: Lock a Terraform workspace to prevent runs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hcp-terraform.lock-workspace\n      with:\n        workspace_id: tools.workspace_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unlock-workspace\n      description: Unlock a Terraform workspace to allow runs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hcp-terraform.unlock-workspace\n\
  \      with:\n        workspace_id: tools.workspace_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-run\n      description: Trigger a new Terraform infrastructure run\n      hints:\n        readOnly: false\n        destructive: false\n      call: hcp-terraform.create-run\n      with:\n        workspace_id: tools.workspace_id\n        message: tools.message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-run\n      description: Get the status and details of a Terraform run\n      hints:\n        readOnly: true\n        openWorld: false\n      call: hcp-terraform.get-run\n      with:\n        run_id: tools.run_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: apply-run\n      description: Apply a Terraform run that is pending approval\n      hints:\n        readOnly: false\n        destructive: false\n      call: hcp-terraform.apply-run\n      with:\n        run_id: tools.run_id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: discard-run\n      description: Discard a pending Terraform run\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: false\n      call: hcp-terraform.discard-run\n      with:\n        run_id: tools.run_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspace-runs\n      description: List the run history for a Terraform workspace\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hcp-terraform.list-workspace-runs\n      with:\n        workspace_id: tools.workspace_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-state-versions\n      description: List state versions for a Terraform workspace\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hcp-terraform.list-state-versions\n      with:\n        workspace_id: tools.workspace_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-teams\n      description: List teams in a Terraform organization\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hcp-terraform.list-teams\n      with:\n        organization_name: tools.organization_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-policies\n      description: List governance policies (Sentinel/OPA) in an organization\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hcp-terraform.list-policies\n      with:\n        organization_name: tools.organization_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-modules\n      description: Search Terraform Registry for reusable infrastructure modules\n      hints:\n        readOnly: true\n        openWorld: true\n      call: terraform-registry.search-modules\n      with:\n        q: tools.q\n        provider: tools.provider\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-module-versions\n      description: List available versions of a Terraform module\n      hints:\n        readOnly: true\n        openWorld: false\n      call: terraform-registry.list-module-versions\n      with:\n        namespace: tools.namespace\n        name: tools.name\n        provider: tools.provider\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-module-version\n      description: Get details for a specific version of a Terraform module\n      hints:\n        readOnly: true\n        openWorld: false\n      call: terraform-registry.get-module-version\n      with:\n        namespace: tools.namespace\n        name: tools.name\n        provider: tools.provider\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
