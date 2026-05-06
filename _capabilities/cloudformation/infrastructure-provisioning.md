---
categories: []
consumed_apis: []
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
- change set operations
- describe a change set
- cloudformation stack operations
- cloudformation
- aws
- create a change set for a stack
- cloud resources
- list stack resources
- detect drift on a stack
- infrastructure as code
- stack events
- delete a stack
- list resources of a specified type
- describe stacks
- describe stack
- update stack
- describe stack events
- get resource
- execute a change set
- update a cloud resource via cloud control
- get template
- single change set
- stack resources
- list stack sets
- read a cloud resource via cloud control
- create a change set
- list resources by type
- get status of a resource operation
- cancel an in-progress resource operation
- get resource request status
- single resource operations
- validate a template
- cloud control resource operations
- create a stack
- create resource
- execute change set
- get a resource
- list resources in a stack
- create a cloudformation stack
- create a cloud resource via cloud control
- cancel resource request
- detect drift
- update a stack
- stack drift detection
- list stacks
- list resources
- stack management
- create change set
- update resource
- delete resource
- list registry extension types
- iac
- update a resource
- template validation
- describe cloudformation stacks
- single stack operations
- detect stack drift
- list exports
- get the template for a stack
- describe change set
- get stack events
- delete stack
- validate template
- list types
- delete a cloud resource via cloud control
- validate a cloudformation template
- create stack
- provisioning
- list all stacks
- describe a stack
- delete a resource
- cloud control
- list stack exports
- create a cloud resource
- automation
slug: infrastructure-provisioning
source_filename: infrastructure-provisioning.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AWS Infrastructure Provisioning\n  description: Unified workflow for AWS infrastructure provisioning combining CloudFormation stack management with Cloud Control\n    API resource operations. Used by cloud engineers and platform teams to define, deploy, and manage infrastructure as code.\n  tags:\n  - AWS\n  - CloudFormation\n  - Cloud Control\n  - Infrastructure As Code\n  - Provisioning\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: cloudformation\n    baseUri: https://cloudformation.{region}.amazonaws.com\n    description: AWS CloudFormation API for infrastructure as code stack management.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: stacks\n\
  \      path: /\n      description: Stack lifecycle management operations.\n      operations:\n      - name: create-stack\n        method: POST\n        description: Creates a stack as specified in the template.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (CreateStack)\n        - name: StackName\n          in: query\n          type: string\n          required: true\n          description: The name of the stack\n        - name: TemplateBody\n          in: query\n          type: string\n          required: false\n          description: Template body JSON/YAML\n        - name: TemplateURL\n          in: query\n          type: string\n          required: false\n          description: S3 URL to template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-stack\n        method: POST\n  \
  \      description: Updates a stack as specified in the template.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (UpdateStack)\n        - name: StackName\n          in: query\n          type: string\n          required: true\n          description: The name of the stack\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-stack\n        method: POST\n        description: Deletes a specified stack.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DeleteStack)\n        - name: StackName\n          in: query\n          type: string\n          required: true\n          description: The name of the stack\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: describe-stacks\n        method: POST\n        description: Returns description of specified stacks.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DescribeStacks)\n        - name: StackName\n          in: query\n          type: string\n          required: false\n          description: Stack name or ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-stacks\n        method: POST\n        description: Returns summary information for stacks.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (ListStacks)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: describe-stack-events\n        method: POST\n        description: Returns all stack-related events for a specified stack.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DescribeStackEvents)\n        - name: StackName\n          in: query\n          type: string\n          required: true\n          description: Stack name or ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-stack-resources\n        method: POST\n        description: Returns AWS resource descriptions for a stack.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DescribeStackResources)\n        - name: StackName\n          in: query\n          type: string\n          required: true\n  \
  \        description: Stack name or ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-stack-resources\n        method: POST\n        description: Returns descriptions of resources in a stack.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (ListStackResources)\n        - name: StackName\n          in: query\n          type: string\n          required: true\n          description: Stack name or ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: detect-stack-drift\n        method: POST\n        description: Detects configuration drift for a stack.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API\
  \ action (DetectStackDrift)\n        - name: StackName\n          in: query\n          type: string\n          required: true\n          description: Stack name or ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-change-set\n        method: POST\n        description: Creates a list of changes for a stack.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (CreateChangeSet)\n        - name: StackName\n          in: query\n          type: string\n          required: true\n          description: Stack name or ID\n        - name: ChangeSetName\n          in: query\n          type: string\n          required: true\n          description: Change set name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: describe-change-set\n        method: POST\n        description: Returns information about a change set.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DescribeChangeSet)\n        - name: ChangeSetName\n          in: query\n          type: string\n          required: true\n          description: Change set name or ID\n        - name: StackName\n          in: query\n          type: string\n          required: false\n          description: Stack name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: execute-change-set\n        method: POST\n        description: Executes a change set.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (ExecuteChangeSet)\n        - name: ChangeSetName\n\
  \          in: query\n          type: string\n          required: true\n          description: Change set name or ID\n        - name: StackName\n          in: query\n          type: string\n          required: false\n          description: Stack name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: validate-template\n        method: POST\n        description: Validates a specified template.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (ValidateTemplate)\n        - name: TemplateBody\n          in: query\n          type: string\n          required: false\n          description: Template body\n        - name: TemplateURL\n          in: query\n          type: string\n          required: false\n          description: Template URL\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-template\n        method: POST\n        description: Returns the template body for a stack.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (GetTemplate)\n        - name: StackName\n          in: query\n          type: string\n          required: true\n          description: Stack name or ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-exports\n        method: POST\n        description: Lists stack exports.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (ListExports)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: create-stack-set\n        method: POST\n        description: Creates a stack set.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (CreateStackSet)\n        - name: StackSetName\n          in: query\n          type: string\n          required: true\n          description: Stack set name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-stack-sets\n        method: POST\n        description: Returns summary information about stack sets.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (ListStackSets)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-types\n        method:\
  \ POST\n        description: Returns summary information about extension types.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (ListTypes)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: cloud-control\n    baseUri: https://cloudcontrolapi.{region}.amazonaws.com\n    description: AWS Cloud Control API for uniform CRUDL resource management.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: resources\n      path: /\n      description: CRUDL operations for cloud resources.\n      operations:\n      - name: create-resource\n        method: POST\n        description: Creates the specified resource.\n        inputParameters:\n        - name: Action\n          in: query\n\
  \          type: string\n          required: true\n          description: API action (CreateResource)\n        - name: TypeName\n          in: query\n          type: string\n          required: true\n          description: Resource type name (e.g., AWS::EC2::Instance)\n        - name: DesiredState\n          in: query\n          type: string\n          required: true\n          description: JSON string of desired resource state\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-resource\n        method: POST\n        description: Returns current state of the specified resource.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (GetResource)\n        - name: TypeName\n          in: query\n          type: string\n          required: true\n          description: Resource type name\n        -\
  \ name: Identifier\n          in: query\n          type: string\n          required: true\n          description: Resource primary identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-resource\n        method: POST\n        description: Updates the specified resource properties.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (UpdateResource)\n        - name: TypeName\n          in: query\n          type: string\n          required: true\n          description: Resource type name\n        - name: Identifier\n          in: query\n          type: string\n          required: true\n          description: Resource primary identifier\n        - name: PatchDocument\n          in: query\n          type: string\n          required: true\n          description: JSON Patch document\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-resource\n        method: POST\n        description: Deletes the specified resource.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (DeleteResource)\n        - name: TypeName\n          in: query\n          type: string\n          required: true\n          description: Resource type name\n        - name: Identifier\n          in: query\n          type: string\n          required: true\n          description: Resource primary identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-resources\n        method: POST\n        description: Returns information about specified resources.\n        inputParameters:\n        - name: Action\n   \
  \       in: query\n          type: string\n          required: true\n          description: API action (ListResources)\n        - name: TypeName\n          in: query\n          type: string\n          required: true\n          description: Resource type name\n        - name: MaxResults\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-resource-request-status\n        method: POST\n        description: Returns status of a resource operation request.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (GetResourceRequestStatus)\n        - name: RequestToken\n          in: query\n          type: string\n          required: true\n          description: Request token\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-resource-requests\n        method: POST\n        description: Returns existing resource operation requests.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (ListResourceRequests)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-resource-request\n        method: POST\n        description: Cancels an in-progress resource operation request.\n        inputParameters:\n        - name: Action\n          in: query\n          type: string\n          required: true\n          description: API action (CancelResourceRequest)\n        - name: RequestToken\n          in: query\n          type: string\n          required: true\n          description: Request\
  \ token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: infra-provisioning-api\n    description: Unified REST API for AWS infrastructure provisioning combining CloudFormation and Cloud Control.\n    resources:\n    - path: /v1/stacks\n      name: stacks\n      description: CloudFormation stack operations\n      operations:\n      - method: GET\n        name: list-stacks\n        description: List all stacks\n        call: cloudformation.list-stacks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-stack\n        description: Create a stack\n        call: cloudformation.create-stack\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stacks/{stackName}\n      name: stack\n      description: Single stack operations\n      operations:\n      - method:\
  \ GET\n        name: describe-stack\n        description: Describe a stack\n        call: cloudformation.describe-stacks\n        with:\n          StackName: rest.stackName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-stack\n        description: Update a stack\n        call: cloudformation.update-stack\n        with:\n          StackName: rest.stackName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-stack\n        description: Delete a stack\n        call: cloudformation.delete-stack\n        with:\n          StackName: rest.stackName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stacks/{stackName}/events\n      name: stack-events\n      description: Stack events\n      operations:\n      - method: GET\n        name: describe-stack-events\n        description: Get stack events\n        call: cloudformation.describe-stack-events\n\
  \        with:\n          StackName: rest.stackName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stacks/{stackName}/resources\n      name: stack-resources\n      description: Stack resources\n      operations:\n      - method: GET\n        name: list-stack-resources\n        description: List resources in a stack\n        call: cloudformation.list-stack-resources\n        with:\n          StackName: rest.stackName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stacks/{stackName}/drift\n      name: stack-drift\n      description: Stack drift detection\n      operations:\n      - method: POST\n        name: detect-drift\n        description: Detect drift on a stack\n        call: cloudformation.detect-stack-drift\n        with:\n          StackName: rest.stackName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/change-sets\n      name: change-sets\n      description:\
  \ Change set operations\n      operations:\n      - method: POST\n        name: create-change-set\n        description: Create a change set\n        call: cloudformation.create-change-set\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/change-sets/{changeSetName}\n      name: change-set\n      description: Single change set\n      operations:\n      - method: GET\n        name: describe-change-set\n        description: Describe a change set\n        call: cloudformation.describe-change-set\n        with:\n          ChangeSetName: rest.changeSetName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/templates/validate\n      name: template-validation\n      description: Template validation\n      operations:\n      - method: POST\n        name: validate-template\n        description: Validate a template\n        call: cloudformation.validate-template\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /v1/resources\n      name: resources\n      description: Cloud Control resource operations\n      operations:\n      - method: POST\n        name: create-resource\n        description: Create a cloud resource\n        call: cloud-control.create-resource\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-resources\n        description: List resources by type\n        call: cloud-control.list-resources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/resources/{typeName}/{identifier}\n      name: resource\n      description: Single resource operations\n      operations:\n      - method: GET\n        name: get-resource\n        description: Get a resource\n        call: cloud-control.get-resource\n        with:\n          TypeName: rest.typeName\n          Identifier: rest.identifier\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: PATCH\n        name: update-resource\n        description: Update a resource\n        call: cloud-control.update-resource\n        with:\n          TypeName: rest.typeName\n          Identifier: rest.identifier\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-resource\n        description: Delete a resource\n        call: cloud-control.delete-resource\n        with:\n          TypeName: rest.typeName\n          Identifier: rest.identifier\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: infra-provisioning-mcp\n    transport: http\n    description: MCP server for AI-assisted AWS infrastructure provisioning.\n    tools:\n    - name: create-stack\n      description: Create a CloudFormation stack\n      hints:\n        readOnly: false\n      call: cloudformation.create-stack\n      outputParameters:\n      - type: object\n    \
  \    mapping: $.\n    - name: describe-stacks\n      description: Describe CloudFormation stacks\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloudformation.describe-stacks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-stacks\n      description: List all stacks\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloudformation.list-stacks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-stack\n      description: Update a stack\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloudformation.update-stack\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-stack\n      description: Delete a stack\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: cloudformation.delete-stack\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: describe-stack-events\n      description: Get stack events\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloudformation.describe-stack-events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-stack-resources\n      description: List resources in a stack\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloudformation.list-stack-resources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: detect-stack-drift\n      description: Detect drift on a stack\n      hints:\n        readOnly: true\n      call: cloudformation.detect-stack-drift\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-change-set\n      description: Create a change set for a stack\n      hints:\n        readOnly: false\n      call: cloudformation.create-change-set\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-change-set\n\
  \      description: Describe a change set\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloudformation.describe-change-set\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-change-set\n      description: Execute a change set\n      hints:\n        readOnly: false\n      call: cloudformation.execute-change-set\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-template\n      description: Validate a CloudFormation template\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloudformation.validate-template\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-template\n      description: Get the template for a stack\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloudformation.get-template\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-exports\n      description:\
  \ List stack exports\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloudformation.list-exports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-stack-sets\n      description: List stack sets\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloudformation.list-stack-sets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-types\n      description: List registry extension types\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloudformation.list-types\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-resource\n      description: Create a cloud resource via Cloud Control\n      hints:\n        readOnly: false\n      call: cloud-control.create-resource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-resource\n      description: Read a cloud resource via Cloud Control\n\
  \      hints:\n        readOnly: true\n        idempotent: true\n      call: cloud-control.get-resource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-resource\n      description: Update a cloud resource via Cloud Control\n      hints:\n        readOnly: false\n        idempotent: true\n      call: cloud-control.update-resource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-resource\n      description: Delete a cloud resource via Cloud Control\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: cloud-control.delete-resource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-resources\n      description: List resources of a specified type\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloud-control.list-resources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-resource-request-status\n      description: Get status of a resource operation\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cloud-control.get-resource-request-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-resource-request\n      description: Cancel an in-progress resource operation\n      hints:\n        readOnly: false\n      call: cloud-control.cancel-resource-request\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
