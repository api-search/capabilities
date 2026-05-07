---
categories: []
consumed_apis: []
description: <fullname>Step Functions</fullname> <p>Step Functions is a service that lets you coordinate the components of distributed applications and microservices using visual workflows.</p> <p>You can use Step Functions to build applications from individual components, each of which performs a discrete function, or <i>task</i>, allowing you to scale and change applications quickly. Step Functions provides a console that helps visualize the components of your application as a series of steps. Step Functions automatically triggers and tracks each step, and retries steps when there are errors, so your app
layout: capability
name: AWS Step Functions
operations:
- description: AWS Step Functions - Create Activity
  method: POST
  name: createactivity
  path: /#X-Amz-Target=AWSStepFunctions.CreateActivity
- description: AWS Step Functions - Create State Machine
  method: POST
  name: createstatemachine
  path: /#X-Amz-Target=AWSStepFunctions.CreateStateMachine
- description: AWS Step Functions - Delete Activity
  method: POST
  name: deleteactivity
  path: /#X-Amz-Target=AWSStepFunctions.DeleteActivity
- description: AWS Step Functions - Delete State Machine
  method: POST
  name: deletestatemachine
  path: /#X-Amz-Target=AWSStepFunctions.DeleteStateMachine
- description: AWS Step Functions - Describe Activity
  method: POST
  name: describeactivity
  path: /#X-Amz-Target=AWSStepFunctions.DescribeActivity
- description: AWS Step Functions - Describe Execution
  method: POST
  name: describeexecution
  path: /#X-Amz-Target=AWSStepFunctions.DescribeExecution
- description: AWS Step Functions - Describe Map Run
  method: POST
  name: describemaprun
  path: /#X-Amz-Target=AWSStepFunctions.DescribeMapRun
- description: AWS Step Functions - Describe State Machine
  method: POST
  name: describestatemachine
  path: /#X-Amz-Target=AWSStepFunctions.DescribeStateMachine
- description: AWS Step Functions - Describe State Machine for Execution
  method: POST
  name: describestatemachineforexecution
  path: /#X-Amz-Target=AWSStepFunctions.DescribeStateMachineForExecution
- description: AWS Step Functions - Get Activity Task
  method: POST
  name: getactivitytask
  path: /#X-Amz-Target=AWSStepFunctions.GetActivityTask
- description: AWS Step Functions - Get Execution History
  method: POST
  name: getexecutionhistory
  path: /#X-Amz-Target=AWSStepFunctions.GetExecutionHistory
- description: AWS Step Functions - List Activities
  method: POST
  name: listactivities
  path: /#X-Amz-Target=AWSStepFunctions.ListActivities
- description: AWS Step Functions - List Executions
  method: POST
  name: listexecutions
  path: /#X-Amz-Target=AWSStepFunctions.ListExecutions
- description: AWS Step Functions - List Map Runs
  method: POST
  name: listmapruns
  path: /#X-Amz-Target=AWSStepFunctions.ListMapRuns
- description: AWS Step Functions - List State Machines
  method: POST
  name: liststatemachines
  path: /#X-Amz-Target=AWSStepFunctions.ListStateMachines
- description: AWS Step Functions - List Tags for Resource
  method: POST
  name: listtagsforresource
  path: /#X-Amz-Target=AWSStepFunctions.ListTagsForResource
- description: AWS Step Functions - Send Task Failure
  method: POST
  name: sendtaskfailure
  path: /#X-Amz-Target=AWSStepFunctions.SendTaskFailure
- description: AWS Step Functions - Send Task Heartbeat
  method: POST
  name: sendtaskheartbeat
  path: /#X-Amz-Target=AWSStepFunctions.SendTaskHeartbeat
- description: AWS Step Functions - Send Task Success
  method: POST
  name: sendtasksuccess
  path: /#X-Amz-Target=AWSStepFunctions.SendTaskSuccess
- description: AWS Step Functions - Start Execution
  method: POST
  name: startexecution
  path: /#X-Amz-Target=AWSStepFunctions.StartExecution
- description: AWS Step Functions - Start Sync Execution
  method: POST
  name: startsyncexecution
  path: /#X-Amz-Target=AWSStepFunctions.StartSyncExecution
- description: AWS Step Functions - Stop Execution
  method: POST
  name: stopexecution
  path: /#X-Amz-Target=AWSStepFunctions.StopExecution
- description: AWS Step Functions - Tag Resource
  method: POST
  name: tagresource
  path: /#X-Amz-Target=AWSStepFunctions.TagResource
- description: AWS Step Functions - Untag Resource
  method: POST
  name: untagresource
  path: /#X-Amz-Target=AWSStepFunctions.UntagResource
- description: AWS Step Functions - Update Map Run
  method: POST
  name: updatemaprun
  path: /#X-Amz-Target=AWSStepFunctions.UpdateMapRun
- description: AWS Step Functions - Update State Machine
  method: POST
  name: updatestatemachine
  path: /#X-Amz-Target=AWSStepFunctions.UpdateStateMachine
personas: []
provider_name: AWS Step Functions
provider_slug: aws-step-functions
search_terms:
- listtagsforresource
- startexecution
- aws step functions - describe state machine
- getactivitytask
- updatestatemachine
- api
- aws step functions - start sync execution
- aws step functions - list state machines
- aws step functions - create state machine
- aws step functions - create activity
- sendtaskheartbeat
- aws step functions - send task success
- getexecutionhistory
- aws step functions - start execution
- startsyncexecution
- aws step functions - delete state machine
- listmapruns
- aws step functions - send task heartbeat
- aws step functions - get execution history
- updatemaprun
- orchestration
- aws step functions - get activity task
- serverless
- aws step functions - list map runs
- describestatemachine
- describeexecution
- tagresource
- listactivities
- createactivity
- ipaas
- aws step functions - update state machine
- aws step functions - delete activity
- listexecutions
- sendtasksuccess
- aws step functions - list activities
- aws step functions - send task failure
- aws step functions - stop execution
- aws step functions - update map run
- aws step functions - describe activity
- sendtaskfailure
- describeactivity
- deletestatemachine
- describemaprun
- stopexecution
- untagresource
- aws step functions - describe map run
- aws step functions - untag resource
- aws
- step
- aws step functions - list tags for resource
- describestatemachineforexecution
- aws step functions - describe execution
- aws step functions - describe state machine for execution
- liststatemachines
- deleteactivity
- aws step functions - tag resource
- createstatemachine
- functions
- aws step functions - list executions
slug: aws-step-functions-capability
source_filename: aws-step-functions-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AWS Step Functions\n  description: <fullname>Step Functions</fullname> <p>Step Functions is a service that lets you coordinate the components\n    of distributed applications and microservices using visual workflows.</p> <p>You can use Step Functions to build applications\n    from individual components, each of which performs a discrete function, or <i>task</i>, allowing you to scale and change\n    applications quickly. Step Functions provides a console that helps visualize the components of your application as a series\n    of steps. Step Functions automatically triggers and tracks each step, and retries steps when there are errors, so your\n    app\n  tags:\n  - Aws\n  - Step\n  - Functions\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: aws-step-functions\n    baseUri: http://states.us-east-1.amazonaws.com\n    description: AWS Step Functions HTTP API.\n    authentication:\n\
  \      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AWS_STEP_FUNCTIONS_TOKEN}}'\n    resources:\n    - name: x-amz-target-awsstepfunctions-createactivity\n      path: /#X-Amz-Target=AWSStepFunctions.CreateActivity\n      operations:\n      - name: createactivity\n        method: POST\n        description: AWS Step Functions - Create Activity\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-createstatemachine\n      path: /#X-Amz-Target=AWSStepFunctions.CreateStateMachine\n      operations:\n      - name: createstatemachine\n        method: POST\n        description: AWS Step Functions - Create State Machine\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n  \
  \        required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-deleteactivity\n      path: /#X-Amz-Target=AWSStepFunctions.DeleteActivity\n      operations:\n      - name: deleteactivity\n        method: POST\n        description: AWS Step Functions - Delete Activity\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-deletestatemachine\n      path: /#X-Amz-Target=AWSStepFunctions.DeleteStateMachine\n      operations:\n      - name: deletestatemachine\n        method: POST\n        description: AWS Step Functions - Delete State Machine\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n \
  \         type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-describeactivity\n      path: /#X-Amz-Target=AWSStepFunctions.DescribeActivity\n      operations:\n      - name: describeactivity\n        method: POST\n        description: AWS Step Functions - Describe Activity\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-describeexecution\n      path: /#X-Amz-Target=AWSStepFunctions.DescribeExecution\n      operations:\n      - name: describeexecution\n        method: POST\n        description: AWS Step Functions - Describe Execution\n        inputParameters:\n        - name: X-Amz-Target\n\
  \          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-describemaprun\n      path: /#X-Amz-Target=AWSStepFunctions.DescribeMapRun\n      operations:\n      - name: describemaprun\n        method: POST\n        description: AWS Step Functions - Describe Map Run\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-describestatemachi\n      path: /#X-Amz-Target=AWSStepFunctions.DescribeStateMachine\n      operations:\n      - name: describestatemachine\n        method: POST\n        description: AWS Step Functions - Describe State Machine\n        inputParameters:\n\
  \        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-describestatemachi\n      path: /#X-Amz-Target=AWSStepFunctions.DescribeStateMachineForExecution\n      operations:\n      - name: describestatemachineforexecution\n        method: POST\n        description: AWS Step Functions - Describe State Machine for Execution\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-getactivitytask\n      path: /#X-Amz-Target=AWSStepFunctions.GetActivityTask\n      operations:\n      - name: getactivitytask\n        method: POST\n        description:\
  \ AWS Step Functions - Get Activity Task\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-getexecutionhistor\n      path: /#X-Amz-Target=AWSStepFunctions.GetExecutionHistory\n      operations:\n      - name: getexecutionhistory\n        method: POST\n        description: AWS Step Functions - Get Execution History\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: string\n          description: Pagination limit\n        - name: nextToken\n          in: query\n          type: string\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-listactivities\n      path: /#X-Amz-Target=AWSStepFunctions.ListActivities\n      operations:\n      - name: listactivities\n        method: POST\n        description: AWS Step Functions - List Activities\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: string\n          description: Pagination limit\n        - name: nextToken\n          in: query\n          type: string\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-listexecutions\n      path: /#X-Amz-Target=AWSStepFunctions.ListExecutions\n      operations:\n      - name: listexecutions\n        method: POST\n        description: AWS Step Functions\
  \ - List Executions\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: string\n          description: Pagination limit\n        - name: nextToken\n          in: query\n          type: string\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-listmapruns\n      path: /#X-Amz-Target=AWSStepFunctions.ListMapRuns\n      operations:\n      - name: listmapruns\n        method: POST\n        description: AWS Step Functions - List Map Runs\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: string\n          description: Pagination limit\n        - name: nextToken\n          in: query\n          type: string\n          description: Pagination token\n      \
  \  - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-liststatemachines\n      path: /#X-Amz-Target=AWSStepFunctions.ListStateMachines\n      operations:\n      - name: liststatemachines\n        method: POST\n        description: AWS Step Functions - List State Machines\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: string\n          description: Pagination limit\n        - name: nextToken\n          in: query\n          type: string\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-listtagsforresourc\n\
  \      path: /#X-Amz-Target=AWSStepFunctions.ListTagsForResource\n      operations:\n      - name: listtagsforresource\n        method: POST\n        description: AWS Step Functions - List Tags for Resource\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-sendtaskfailure\n      path: /#X-Amz-Target=AWSStepFunctions.SendTaskFailure\n      operations:\n      - name: sendtaskfailure\n        method: POST\n        description: AWS Step Functions - Send Task Failure\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-sendtaskheartbeat\n\
  \      path: /#X-Amz-Target=AWSStepFunctions.SendTaskHeartbeat\n      operations:\n      - name: sendtaskheartbeat\n        method: POST\n        description: AWS Step Functions - Send Task Heartbeat\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-sendtasksuccess\n      path: /#X-Amz-Target=AWSStepFunctions.SendTaskSuccess\n      operations:\n      - name: sendtasksuccess\n        method: POST\n        description: AWS Step Functions - Send Task Success\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-startexecution\n\
  \      path: /#X-Amz-Target=AWSStepFunctions.StartExecution\n      operations:\n      - name: startexecution\n        method: POST\n        description: AWS Step Functions - Start Execution\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-startsyncexecution\n      path: /#X-Amz-Target=AWSStepFunctions.StartSyncExecution\n      operations:\n      - name: startsyncexecution\n        method: POST\n        description: AWS Step Functions - Start Sync Execution\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-stopexecution\n\
  \      path: /#X-Amz-Target=AWSStepFunctions.StopExecution\n      operations:\n      - name: stopexecution\n        method: POST\n        description: AWS Step Functions - Stop Execution\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-tagresource\n      path: /#X-Amz-Target=AWSStepFunctions.TagResource\n      operations:\n      - name: tagresource\n        method: POST\n        description: AWS Step Functions - Tag Resource\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-untagresource\n      path:\
  \ /#X-Amz-Target=AWSStepFunctions.UntagResource\n      operations:\n      - name: untagresource\n        method: POST\n        description: AWS Step Functions - Untag Resource\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-updatemaprun\n      path: /#X-Amz-Target=AWSStepFunctions.UpdateMapRun\n      operations:\n      - name: updatemaprun\n        method: POST\n        description: AWS Step Functions - Update Map Run\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-awsstepfunctions-updatestatemachine\n      path:\
  \ /#X-Amz-Target=AWSStepFunctions.UpdateStateMachine\n      operations:\n      - name: updatestatemachine\n        method: POST\n        description: AWS Step Functions - Update State Machine\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: aws-step-functions-rest\n    description: REST adapter for AWS Step Functions.\n    resources:\n    - path: /#X-Amz-Target=AWSStepFunctions.CreateActivity\n      name: createactivity\n      operations:\n      - method: POST\n        name: createactivity\n        description: AWS Step Functions - Create Activity\n        call: aws-step-functions.createactivity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.CreateStateMachine\n\
  \      name: createstatemachine\n      operations:\n      - method: POST\n        name: createstatemachine\n        description: AWS Step Functions - Create State Machine\n        call: aws-step-functions.createstatemachine\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.DeleteActivity\n      name: deleteactivity\n      operations:\n      - method: POST\n        name: deleteactivity\n        description: AWS Step Functions - Delete Activity\n        call: aws-step-functions.deleteactivity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.DeleteStateMachine\n      name: deletestatemachine\n      operations:\n      - method: POST\n        name: deletestatemachine\n        description: AWS Step Functions - Delete State Machine\n        call: aws-step-functions.deletestatemachine\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /#X-Amz-Target=AWSStepFunctions.DescribeActivity\n      name: describeactivity\n      operations:\n      - method: POST\n        name: describeactivity\n        description: AWS Step Functions - Describe Activity\n        call: aws-step-functions.describeactivity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.DescribeExecution\n      name: describeexecution\n      operations:\n      - method: POST\n        name: describeexecution\n        description: AWS Step Functions - Describe Execution\n        call: aws-step-functions.describeexecution\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.DescribeMapRun\n      name: describemaprun\n      operations:\n      - method: POST\n        name: describemaprun\n        description: AWS Step Functions - Describe Map Run\n        call: aws-step-functions.describemaprun\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.DescribeStateMachine\n      name: describestatemachine\n      operations:\n      - method: POST\n        name: describestatemachine\n        description: AWS Step Functions - Describe State Machine\n        call: aws-step-functions.describestatemachine\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.DescribeStateMachineForExecution\n      name: describestatemachineforexecution\n      operations:\n      - method: POST\n        name: describestatemachineforexecution\n        description: AWS Step Functions - Describe State Machine for Execution\n        call: aws-step-functions.describestatemachineforexecution\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.GetActivityTask\n      name: getactivitytask\n      operations:\n      - method: POST\n        name: getactivitytask\n\
  \        description: AWS Step Functions - Get Activity Task\n        call: aws-step-functions.getactivitytask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.GetExecutionHistory\n      name: getexecutionhistory\n      operations:\n      - method: POST\n        name: getexecutionhistory\n        description: AWS Step Functions - Get Execution History\n        call: aws-step-functions.getexecutionhistory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.ListActivities\n      name: listactivities\n      operations:\n      - method: POST\n        name: listactivities\n        description: AWS Step Functions - List Activities\n        call: aws-step-functions.listactivities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.ListExecutions\n      name: listexecutions\n      operations:\n\
  \      - method: POST\n        name: listexecutions\n        description: AWS Step Functions - List Executions\n        call: aws-step-functions.listexecutions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.ListMapRuns\n      name: listmapruns\n      operations:\n      - method: POST\n        name: listmapruns\n        description: AWS Step Functions - List Map Runs\n        call: aws-step-functions.listmapruns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.ListStateMachines\n      name: liststatemachines\n      operations:\n      - method: POST\n        name: liststatemachines\n        description: AWS Step Functions - List State Machines\n        call: aws-step-functions.liststatemachines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.ListTagsForResource\n      name: listtagsforresource\n\
  \      operations:\n      - method: POST\n        name: listtagsforresource\n        description: AWS Step Functions - List Tags for Resource\n        call: aws-step-functions.listtagsforresource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.SendTaskFailure\n      name: sendtaskfailure\n      operations:\n      - method: POST\n        name: sendtaskfailure\n        description: AWS Step Functions - Send Task Failure\n        call: aws-step-functions.sendtaskfailure\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.SendTaskHeartbeat\n      name: sendtaskheartbeat\n      operations:\n      - method: POST\n        name: sendtaskheartbeat\n        description: AWS Step Functions - Send Task Heartbeat\n        call: aws-step-functions.sendtaskheartbeat\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.SendTaskSuccess\n\
  \      name: sendtasksuccess\n      operations:\n      - method: POST\n        name: sendtasksuccess\n        description: AWS Step Functions - Send Task Success\n        call: aws-step-functions.sendtasksuccess\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.StartExecution\n      name: startexecution\n      operations:\n      - method: POST\n        name: startexecution\n        description: AWS Step Functions - Start Execution\n        call: aws-step-functions.startexecution\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.StartSyncExecution\n      name: startsyncexecution\n      operations:\n      - method: POST\n        name: startsyncexecution\n        description: AWS Step Functions - Start Sync Execution\n        call: aws-step-functions.startsyncexecution\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /#X-Amz-Target=AWSStepFunctions.StopExecution\n      name: stopexecution\n      operations:\n      - method: POST\n        name: stopexecution\n        description: AWS Step Functions - Stop Execution\n        call: aws-step-functions.stopexecution\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.TagResource\n      name: tagresource\n      operations:\n      - method: POST\n        name: tagresource\n        description: AWS Step Functions - Tag Resource\n        call: aws-step-functions.tagresource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.UntagResource\n      name: untagresource\n      operations:\n      - method: POST\n        name: untagresource\n        description: AWS Step Functions - Untag Resource\n        call: aws-step-functions.untagresource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /#X-Amz-Target=AWSStepFunctions.UpdateMapRun\n      name: updatemaprun\n      operations:\n      - method: POST\n        name: updatemaprun\n        description: AWS Step Functions - Update Map Run\n        call: aws-step-functions.updatemaprun\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AWSStepFunctions.UpdateStateMachine\n      name: updatestatemachine\n      operations:\n      - method: POST\n        name: updatestatemachine\n        description: AWS Step Functions - Update State Machine\n        call: aws-step-functions.updatestatemachine\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: aws-step-functions-mcp\n    transport: http\n    description: MCP adapter for AWS Step Functions for AI agent use.\n    tools:\n    - name: createactivity\n      description: AWS Step Functions - Create Activity\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: aws-step-functions.createactivity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createstatemachine\n      description: AWS Step Functions - Create State Machine\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.createstatemachine\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteactivity\n      description: AWS Step Functions - Delete Activity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.deleteactivity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletestatemachine\n      description: AWS Step Functions - Delete State Machine\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.deletestatemachine\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: describeactivity\n      description: AWS Step Functions - Describe Activity\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.describeactivity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeexecution\n      description: AWS Step Functions - Describe Execution\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.describeexecution\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describemaprun\n      description: AWS Step Functions - Describe Map Run\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.describemaprun\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describestatemachine\n      description: AWS Step\
  \ Functions - Describe State Machine\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.describestatemachine\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describestatemachineforexecution\n      description: AWS Step Functions - Describe State Machine for Execution\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.describestatemachineforexecution\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getactivitytask\n      description: AWS Step Functions - Get Activity Task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.getactivitytask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getexecutionhistory\n      description: AWS Step Functions - Get Execution History\n \
  \     hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.getexecutionhistory\n      with:\n        maxResults: tools.maxResults\n        nextToken: tools.nextToken\n      inputParameters:\n      - name: maxResults\n        type: string\n        description: Pagination limit\n      - name: nextToken\n        type: string\n        description: Pagination token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listactivities\n      description: AWS Step Functions - List Activities\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.listactivities\n      with:\n        maxResults: tools.maxResults\n        nextToken: tools.nextToken\n      inputParameters:\n      - name: maxResults\n        type: string\n        description: Pagination limit\n      - name: nextToken\n        type: string\n        description: Pagination\
  \ token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listexecutions\n      description: AWS Step Functions - List Executions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.listexecutions\n      with:\n        maxResults: tools.maxResults\n        nextToken: tools.nextToken\n      inputParameters:\n      - name: maxResults\n        type: string\n        description: Pagination limit\n      - name: nextToken\n        type: string\n        description: Pagination token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmapruns\n      description: AWS Step Functions - List Map Runs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.listmapruns\n      with:\n        maxResults: tools.maxResults\n        nextToken: tools.nextToken\n      inputParameters:\n      - name: maxResults\n\
  \        type: string\n        description: Pagination limit\n      - name: nextToken\n        type: string\n        description: Pagination token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststatemachines\n      description: AWS Step Functions - List State Machines\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.liststatemachines\n      with:\n        maxResults: tools.maxResults\n        nextToken: tools.nextToken\n      inputParameters:\n      - name: maxResults\n        type: string\n        description: Pagination limit\n      - name: nextToken\n        type: string\n        description: Pagination token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtagsforresource\n      description: AWS Step Functions - List Tags for Resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n    \
  \  call: aws-step-functions.listtagsforresource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendtaskfailure\n      description: AWS Step Functions - Send Task Failure\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.sendtaskfailure\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendtaskheartbeat\n      description: AWS Step Functions - Send Task Heartbeat\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.sendtaskheartbeat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendtasksuccess\n      description: AWS Step Functions - Send Task Success\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.sendtasksuccess\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: startexecution\n      description: AWS Step Functions - Start Execution\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.startexecution\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startsyncexecution\n      description: AWS Step Functions - Start Sync Execution\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.startsyncexecution\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopexecution\n      description: AWS Step Functions - Stop Execution\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.stopexecution\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tagresource\n      description: AWS Step Functions - Tag Resource\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.tagresource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: untagresource\n      description: AWS Step Functions - Untag Resource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-step-functions.untagresource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatemaprun\n      description: AWS Step Functions - Update Map Run\n      hints:\n        readOnly: false\n       \n\n# --- truncated at 32 KB (32 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/aws-step-functions/refs/heads/main/capabilities/aws-step-functions-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-step-functions/refs/heads/main/capabilities/aws-step-functions-capability.yaml
tags:
- Aws
- Step
- Functions
- API
tools:
- description: AWS Step Functions - Create Activity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createactivity
- description: AWS Step Functions - Create State Machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createstatemachine
- description: AWS Step Functions - Delete Activity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deleteactivity
- description: AWS Step Functions - Delete State Machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletestatemachine
- description: AWS Step Functions - Describe Activity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describeactivity
- description: AWS Step Functions - Describe Execution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describeexecution
- description: AWS Step Functions - Describe Map Run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describemaprun
- description: AWS Step Functions - Describe State Machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describestatemachine
- description: AWS Step Functions - Describe State Machine for Execution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describestatemachineforexecution
- description: AWS Step Functions - Get Activity Task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getactivitytask
- description: AWS Step Functions - Get Execution History
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getexecutionhistory
- description: AWS Step Functions - List Activities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listactivities
- description: AWS Step Functions - List Executions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listexecutions
- description: AWS Step Functions - List Map Runs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listmapruns
- description: AWS Step Functions - List State Machines
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: liststatemachines
- description: AWS Step Functions - List Tags for Resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listtagsforresource
- description: AWS Step Functions - Send Task Failure
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendtaskfailure
- description: AWS Step Functions - Send Task Heartbeat
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendtaskheartbeat
- description: AWS Step Functions - Send Task Success
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendtasksuccess
- description: AWS Step Functions - Start Execution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startexecution
- description: AWS Step Functions - Start Sync Execution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startsyncexecution
- description: AWS Step Functions - Stop Execution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopexecution
- description: AWS Step Functions - Tag Resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: tagresource
- description: AWS Step Functions - Untag Resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: untagresource
- description: AWS Step Functions - Update Map Run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatemaprun
- description: AWS Step Functions - Update State Machine
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatestatemachine
---
