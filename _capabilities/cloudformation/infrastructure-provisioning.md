---
categories: []
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
- update stack
- stack drift detection
- cloud control
- list resources by type
- template validation
- list exports
- stack resources
- get resource request status
- describe stacks
- single stack operations
- detect drift
- stack events
- describe change set
- delete a resource
- update a stack
- list stack exports
- get the template for a stack
- cloudformation
- execute a change set
- validate a template
- describe a change set
- list stack sets
- create a cloud resource
- describe stack events
- cancel an in-progress resource operation
- list resources in a stack
- describe cloudformation stacks
- cloud resources
- infrastructure as code
- create resource
- create stack
- stack management
- create a stack
- cloudformation stack operations
- get a resource
- detect drift on a stack
- create a cloudformation stack
- create a cloud resource via cloud control
- get template
- delete a stack
- delete stack
- validate template
- describe a stack
- provisioning
- list types
- delete a cloud resource via cloud control
- create change set
- delete resource
- cancel resource request
- update resource
- list resources of a specified type
- read a cloud resource via cloud control
- automation
- get stack events
- detect stack drift
- describe stack
- list stack resources
- list stacks
- cloud control resource operations
- list resources
- create a change set for a stack
- update a cloud resource via cloud control
- single resource operations
- get resource
- list registry extension types
- iac
- single change set
- execute change set
- get status of a resource operation
- validate a cloudformation template
- change set operations
- update a resource
- create a change set
- aws
- list all stacks
slug: infrastructure-provisioning
source_filename: infrastructure-provisioning.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AWS Infrastructure Provisioning\"\n  description: \"Unified workflow for AWS infrastructure provisioning combining CloudFormation stack management with Cloud Control API resource operations. Used by cloud engineers and platform teams to define, deploy, and manage infrastructure as code.\"\n  tags:\n    - AWS\n    - CloudFormation\n    - Cloud Control\n    - Infrastructure As Code\n    - Provisioning\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: cloudformation\n      location: ./shared/cloudformation.yaml\n    - import: cloud-control\n      location: ./shared/cloud-control.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: infra-provisioning-api\n      description: \"Unified REST API for AWS infrastructure provisioning combining\
  \ CloudFormation and Cloud Control.\"\n      resources:\n        - path: /v1/stacks\n          name: stacks\n          description: \"CloudFormation stack operations\"\n          operations:\n            - method: GET\n              name: list-stacks\n              description: \"List all stacks\"\n              call: \"cloudformation.list-stacks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-stack\n              description: \"Create a stack\"\n              call: \"cloudformation.create-stack\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stacks/{stackName}\n          name: stack\n          description: \"Single stack operations\"\n          operations:\n            - method: GET\n              name: describe-stack\n              description: \"Describe a stack\"\n              call: \"cloudformation.describe-stacks\"\
  \n              with:\n                StackName: \"rest.stackName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-stack\n              description: \"Update a stack\"\n              call: \"cloudformation.update-stack\"\n              with:\n                StackName: \"rest.stackName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-stack\n              description: \"Delete a stack\"\n              call: \"cloudformation.delete-stack\"\n              with:\n                StackName: \"rest.stackName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stacks/{stackName}/events\n          name: stack-events\n          description: \"Stack events\"\n          operations:\n            - method: GET\n\
  \              name: describe-stack-events\n              description: \"Get stack events\"\n              call: \"cloudformation.describe-stack-events\"\n              with:\n                StackName: \"rest.stackName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stacks/{stackName}/resources\n          name: stack-resources\n          description: \"Stack resources\"\n          operations:\n            - method: GET\n              name: list-stack-resources\n              description: \"List resources in a stack\"\n              call: \"cloudformation.list-stack-resources\"\n              with:\n                StackName: \"rest.stackName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stacks/{stackName}/drift\n          name: stack-drift\n          description: \"Stack drift detection\"\n          operations:\n            - method:\
  \ POST\n              name: detect-drift\n              description: \"Detect drift on a stack\"\n              call: \"cloudformation.detect-stack-drift\"\n              with:\n                StackName: \"rest.stackName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/change-sets\n          name: change-sets\n          description: \"Change set operations\"\n          operations:\n            - method: POST\n              name: create-change-set\n              description: \"Create a change set\"\n              call: \"cloudformation.create-change-set\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/change-sets/{changeSetName}\n          name: change-set\n          description: \"Single change set\"\n          operations:\n            - method: GET\n              name: describe-change-set\n              description: \"Describe a change\
  \ set\"\n              call: \"cloudformation.describe-change-set\"\n              with:\n                ChangeSetName: \"rest.changeSetName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/templates/validate\n          name: template-validation\n          description: \"Template validation\"\n          operations:\n            - method: POST\n              name: validate-template\n              description: \"Validate a template\"\n              call: \"cloudformation.validate-template\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/resources\n          name: resources\n          description: \"Cloud Control resource operations\"\n          operations:\n            - method: POST\n              name: create-resource\n              description: \"Create a cloud resource\"\n              call: \"cloud-control.create-resource\"\n      \
  \        outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-resources\n              description: \"List resources by type\"\n              call: \"cloud-control.list-resources\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/resources/{typeName}/{identifier}\n          name: resource\n          description: \"Single resource operations\"\n          operations:\n            - method: GET\n              name: get-resource\n              description: \"Get a resource\"\n              call: \"cloud-control.get-resource\"\n              with:\n                TypeName: \"rest.typeName\"\n                Identifier: \"rest.identifier\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-resource\n              description: \"Update\
  \ a resource\"\n              call: \"cloud-control.update-resource\"\n              with:\n                TypeName: \"rest.typeName\"\n                Identifier: \"rest.identifier\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-resource\n              description: \"Delete a resource\"\n              call: \"cloud-control.delete-resource\"\n              with:\n                TypeName: \"rest.typeName\"\n                Identifier: \"rest.identifier\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: infra-provisioning-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AWS infrastructure provisioning.\"\n      tools:\n        - name: create-stack\n          description: \"Create a CloudFormation stack\"\n          hints:\n            readOnly:\
  \ false\n          call: \"cloudformation.create-stack\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-stacks\n          description: \"Describe CloudFormation stacks\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudformation.describe-stacks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-stacks\n          description: \"List all stacks\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudformation.list-stacks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-stack\n          description: \"Update a stack\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"cloudformation.update-stack\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: delete-stack\n          description: \"Delete a stack\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"cloudformation.delete-stack\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-stack-events\n          description: \"Get stack events\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudformation.describe-stack-events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-stack-resources\n          description: \"List resources in a stack\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudformation.list-stack-resources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: detect-stack-drift\n\
  \          description: \"Detect drift on a stack\"\n          hints:\n            readOnly: true\n          call: \"cloudformation.detect-stack-drift\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-change-set\n          description: \"Create a change set for a stack\"\n          hints:\n            readOnly: false\n          call: \"cloudformation.create-change-set\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-change-set\n          description: \"Describe a change set\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudformation.describe-change-set\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: execute-change-set\n          description: \"Execute a change set\"\n          hints:\n            readOnly: false\n          call: \"cloudformation.execute-change-set\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: validate-template\n          description: \"Validate a CloudFormation template\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudformation.validate-template\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-template\n          description: \"Get the template for a stack\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudformation.get-template\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-exports\n          description: \"List stack exports\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudformation.list-exports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n\n        - name: list-stack-sets\n          description: \"List stack sets\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudformation.list-stack-sets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-types\n          description: \"List registry extension types\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudformation.list-types\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-resource\n          description: \"Create a cloud resource via Cloud Control\"\n          hints:\n            readOnly: false\n          call: \"cloud-control.create-resource\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-resource\n          description: \"Read a cloud resource via Cloud Control\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"cloud-control.get-resource\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-resource\n          description: \"Update a cloud resource via Cloud Control\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"cloud-control.update-resource\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-resource\n          description: \"Delete a cloud resource via Cloud Control\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"cloud-control.delete-resource\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-resources\n          description: \"List resources of a specified type\"\n          hints:\n            readOnly:\
  \ true\n            idempotent: true\n          call: \"cloud-control.list-resources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-resource-request-status\n          description: \"Get status of a resource operation\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloud-control.get-resource-request-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-resource-request\n          description: \"Cancel an in-progress resource operation\"\n          hints:\n            readOnly: false\n          call: \"cloud-control.cancel-resource-request\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloudformation/refs/heads/main/capabilities/infrastructure-provisioning.yaml
tags:
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
