---
consumed_apis:
- cloudformation
- cloud-control
description: Unified workflow for AWS infrastructure provisioning combining CloudFormation stack management with Cloud Control API resource operations. Used by cloud engineers and platform teams to define, deploy, and manage infrastructure as code.
layout: capability
name: AWS Infrastructure Provisioning
operations:
- description: List all stacks
  method: GET
  name: list-stacks
  path: /v1/stacks
- description: Create a stack
  method: POST
  name: create-stack
  path: /v1/stacks
- description: Describe a stack
  method: GET
  name: describe-stack
  path: /v1/stacks/{stackName}
- description: Update a stack
  method: PUT
  name: update-stack
  path: /v1/stacks/{stackName}
- description: Delete a stack
  method: DELETE
  name: delete-stack
  path: /v1/stacks/{stackName}
- description: Get stack events
  method: GET
  name: describe-stack-events
  path: /v1/stacks/{stackName}/events
- description: List resources in a stack
  method: GET
  name: list-stack-resources
  path: /v1/stacks/{stackName}/resources
- description: Detect drift on a stack
  method: POST
  name: detect-drift
  path: /v1/stacks/{stackName}/drift
- description: Create a change set
  method: POST
  name: create-change-set
  path: /v1/change-sets
- description: Describe a change set
  method: GET
  name: describe-change-set
  path: /v1/change-sets/{changeSetName}
- description: Validate a template
  method: POST
  name: validate-template
  path: /v1/templates/validate
- description: Create a cloud resource
  method: POST
  name: create-resource
  path: /v1/resources
- description: List resources by type
  method: GET
  name: list-resources
  path: /v1/resources
- description: Get a resource
  method: GET
  name: get-resource
  path: /v1/resources/{typeName}/{identifier}
- description: Update a resource
  method: PATCH
  name: update-resource
  path: /v1/resources/{typeName}/{identifier}
- description: Delete a resource
  method: DELETE
  name: delete-resource
  path: /v1/resources/{typeName}/{identifier}
personas: []
provider_name: AWS CloudFormation
provider_slug: cloudformation
search_terms:
- execute change set
- update resource
- list resources
- list exports
- list all stacks
- create a stack
- cloudformation stack operations
- cancel an in-progress resource operation
- get template
- delete a stack
- delete resource
- cancel resource request
- cloud control resource operations
- describe cloudformation stacks
- automation
- list resources in a stack
- cloud control
- execute a change set
- create resource
- get the template for a stack
- create a cloud resource via cloud control
- update a resource
- get status of a resource operation
- validate a cloudformation template
- create stack
- stack drift detection
- single change set
- cloudformation
- validate template
- create change set
- update a cloud resource via cloud control
- update stack
- list resources by type
- change set operations
- detect stack drift
- list stack exports
- cloud resources
- describe a change set
- delete a resource
- list registry extension types
- get resource request status
- describe a stack
- get a resource
- stack events
- list stacks
- stack management
- validate a template
- create a cloudformation stack
- delete stack
- create a change set
- get resource
- detect drift
- template validation
- stack resources
- describe stack
- single stack operations
- provisioning
- update a stack
- list stack resources
- detect drift on a stack
- list stack sets
- create a cloud resource
- list types
- read a cloud resource via cloud control
- describe stacks
- aws
- describe change set
- delete a cloud resource via cloud control
- create a change set for a stack
- describe stack events
- single resource operations
- list resources of a specified type
- iac
- get stack events
- infrastructure as code
slug: infrastructure-provisioning
tags:
- AWS
- CloudFormation
- Cloud Control
- Infrastructure As Code
- Provisioning
tools:
- description: Create a CloudFormation stack
  hints:
    readOnly: false
  name: create-stack
- description: Describe CloudFormation stacks
  hints:
    idempotent: true
    readOnly: true
  name: describe-stacks
- description: List all stacks
  hints:
    idempotent: true
    readOnly: true
  name: list-stacks
- description: Update a stack
  hints:
    idempotent: true
    readOnly: false
  name: update-stack
- description: Delete a stack
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-stack
- description: Get stack events
  hints:
    idempotent: true
    readOnly: true
  name: describe-stack-events
- description: List resources in a stack
  hints:
    idempotent: true
    readOnly: true
  name: list-stack-resources
- description: Detect drift on a stack
  hints:
    readOnly: true
  name: detect-stack-drift
- description: Create a change set for a stack
  hints:
    readOnly: false
  name: create-change-set
- description: Describe a change set
  hints:
    idempotent: true
    readOnly: true
  name: describe-change-set
- description: Execute a change set
  hints:
    readOnly: false
  name: execute-change-set
- description: Validate a CloudFormation template
  hints:
    idempotent: true
    readOnly: true
  name: validate-template
- description: Get the template for a stack
  hints:
    idempotent: true
    readOnly: true
  name: get-template
- description: List stack exports
  hints:
    idempotent: true
    readOnly: true
  name: list-exports
- description: List stack sets
  hints:
    idempotent: true
    readOnly: true
  name: list-stack-sets
- description: List registry extension types
  hints:
    idempotent: true
    readOnly: true
  name: list-types
- description: Create a cloud resource via Cloud Control
  hints:
    readOnly: false
  name: create-resource
- description: Read a cloud resource via Cloud Control
  hints:
    idempotent: true
    readOnly: true
  name: get-resource
- description: Update a cloud resource via Cloud Control
  hints:
    idempotent: true
    readOnly: false
  name: update-resource
- description: Delete a cloud resource via Cloud Control
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-resource
- description: List resources of a specified type
  hints:
    idempotent: true
    readOnly: true
  name: list-resources
- description: Get status of a resource operation
  hints:
    idempotent: true
    readOnly: true
  name: get-resource-request-status
- description: Cancel an in-progress resource operation
  hints:
    readOnly: false
  name: cancel-resource-request
---
