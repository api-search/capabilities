---
categories: []
consumed_apis: []
description: Workflow capability for data scientists and researchers to create HITs, manage worker assignments, approve work, and coordinate crowdsourced human intelligence tasks through Amazon Mechanical Turk.
layout: capability
name: Amazon Mechanical Turk - Crowdsourcing Workflow
operations:
- description: Create a new HIT for crowdsourced task execution.
  method: POST
  name: create-hit
  path: /v1/hits
- description: List all HITs in the requester account.
  method: GET
  name: list-hits
  path: /v1/hits
- description: List all assignments submitted for a HIT.
  method: GET
  name: list-assignments
  path: /v1/assignments
- description: Approve a completed assignment and release payment.
  method: POST
  name: approve-assignment
  path: /v1/assignments
- description: Send a bonus payment to a worker.
  method: POST
  name: send-bonus
  path: /v1/workers
- description: Get the current prepaid balance in the MTurk account.
  method: GET
  name: get-account-balance
  path: /v1/account
personas: []
provider_name: Amazon Mechanical Turk
provider_slug: amazon-mechanical-turk
search_terms:
- workflow for data scientists and researchers to manage hits and worker assignments on amazon mechanical turk.
- tasks
- get account balance
- human intelligence
- list all active and reviewable hits in the requester account.
- amazon
- list assignments
- list all worker assignments submitted for a specific hit for review.
- list assignments for hit
- create and manage human intelligence tasks.
- crowdsourcing
- create a new human intelligence task for crowdsourced annotation, transcription, or research.
- review and manage worker assignment submissions.
- mechanical turk
- send a bonus payment to a worker for exceptional task completion.
- get the current prepaid balance in the mturk account.
- approve assignment
- send notification messages to specific workers.
- create hit
- list all hits in the requester account.
- get hit
- approve a completed worker assignment and release payment.
- managing account balance and prepaid funds.
- machine learning
- academic or market researcher coordinating human intelligence tasks for studies and surveys.
- get the current prepaid balance available in the mturk requester account.
- list all assignments submitted for a hit.
- reject a completed worker assignment with feedback.
- get detailed information about a specific hit including status and completion metrics.
- approve a completed assignment and release payment.
- Data Scientist
- send a bonus payment to a worker.
- account balance and status.
- reject assignment
- Researcher
- create a new hit for crowdsourced task execution.
- data scientist using mturk for data labeling, annotation, and validation tasks.
- creating and managing hits for crowdsourced work.
- list qualification types used to filter and target the right worker pool.
- list qualification types
- send bonus
- list hits
- labor
- manage worker bonuses and notifications.
- managing worker qualifications, blocks, bonuses, and notifications.
- notify workers
slug: crowdsourcing-workflow
source_filename: crowdsourcing-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Mechanical Turk - Crowdsourcing Workflow\n  description: Workflow capability for data scientists and researchers to create HITs, manage worker assignments, approve\n    work, and coordinate crowdsourced human intelligence tasks through Amazon Mechanical Turk.\n  tags:\n  - Amazon\n  - Mechanical Turk\n  - Crowdsourcing\n  - Human Intelligence\n  - Tasks\n  - Machine Learning\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: mturk-requester\n    baseUri: https://mturk-requester.us-east-1.amazonaws.com\n    description: Amazon Mechanical Turk Requester API for managing HITs and worker tasks.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n\
  \    resources:\n    - name: hits\n      path: /\n      description: Human Intelligence Tasks (HITs) - the core unit of work in MTurk.\n      operations:\n      - name: create-hit\n        method: POST\n        description: Create a new HIT.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n            reward: '{{tools.reward}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-hit\n        method: POST\n        description: Get details of a specific HIT.\n        body:\n          type: json\n          data:\n            HITId: '{{tools.hitId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-hits\n        method: POST\n        description: List all HITs for the requester account.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-hit\n        method: POST\n        description: Delete a HIT that has been completed or abandoned.\n        body:\n          type: json\n          data:\n            HITId: '{{tools.hitId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assignments\n      path: /\n      description: Worker assignments submitted for HITs.\n      operations:\n      - name: list-assignments-for-hit\n        method: POST\n        description: List all assignments for a specific HIT.\n        body:\n          type: json\n          data:\n            HITId: '{{tools.hitId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-assignment\n        method: POST\n        description: Get details of a specific\
  \ assignment.\n        body:\n          type: json\n          data:\n            AssignmentId: '{{tools.assignmentId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: approve-assignment\n        method: POST\n        description: Approve a completed assignment and release payment to the worker.\n        body:\n          type: json\n          data:\n            AssignmentId: '{{tools.assignmentId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reject-assignment\n        method: POST\n        description: Reject a completed assignment.\n        body:\n          type: json\n          data:\n            AssignmentId: '{{tools.assignmentId}}'\n            RequesterFeedback: '{{tools.feedback}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n    - name: qualifications\n      path: /\n      description: Qualification types and worker qualification management.\n      operations:\n      - name: create-qualification-type\n        method: POST\n        description: Create a new qualification type.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-qualification-types\n        method: POST\n        description: List all qualification types for the requester.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-qualification-type\n        method: POST\n        description: Get details of a specific qualification type.\n        body:\n          type: json\n          data:\n            QualificationTypeId:\
  \ '{{tools.qualificationTypeId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workers\n      path: /\n      description: Worker management including blocks, bonuses, and notifications.\n      operations:\n      - name: list-bonus-payments\n        method: POST\n        description: List bonus payments made to workers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-bonus\n        method: POST\n        description: Pay a bonus to a worker for a completed assignment.\n        body:\n          type: json\n          data:\n            WorkerId: '{{tools.workerId}}'\n            BonusAmount: '{{tools.bonusAmount}}'\n            AssignmentId: '{{tools.assignmentId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: notify-workers\n        method: POST\n        description: Send notification messages to workers.\n        body:\n          type: json\n          data:\n            Subject: '{{tools.subject}}'\n            MessageText: '{{tools.messageText}}'\n            WorkerIds: '{{tools.workerIds}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account-balance\n        method: POST\n        description: Get the prepaid balance in the requester's MTurk account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mturk-crowdsourcing-api\n    description: Unified REST API for Amazon Mechanical Turk crowdsourcing workflows.\n    resources:\n    - path: /v1/hits\n      name: hits\n      description: Create and manage Human Intelligence Tasks.\n      operations:\n\
  \      - method: POST\n        name: create-hit\n        description: Create a new HIT for crowdsourced task execution.\n        call: mturk-requester.create-hit\n        with:\n          title: rest.title\n          description: rest.description\n          reward: rest.reward\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-hits\n        description: List all HITs in the requester account.\n        call: mturk-requester.list-hits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assignments\n      name: assignments\n      description: Review and manage worker assignment submissions.\n      operations:\n      - method: GET\n        name: list-assignments\n        description: List all assignments submitted for a HIT.\n        call: mturk-requester.list-assignments-for-hit\n        with:\n          hitId: rest.hitId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: POST\n        name: approve-assignment\n        description: Approve a completed assignment and release payment.\n        call: mturk-requester.approve-assignment\n        with:\n          assignmentId: rest.assignmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workers\n      name: workers\n      description: Manage worker bonuses and notifications.\n      operations:\n      - method: POST\n        name: send-bonus\n        description: Send a bonus payment to a worker.\n        call: mturk-requester.send-bonus\n        with:\n          workerId: rest.workerId\n          bonusAmount: rest.bonusAmount\n          assignmentId: rest.assignmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/account\n      name: account\n      description: Account balance and status.\n      operations:\n      - method: GET\n        name: get-account-balance\n        description: Get the current\
  \ prepaid balance in the MTurk account.\n        call: mturk-requester.get-account-balance\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mturk-crowdsourcing-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Mechanical Turk crowdsourcing task management.\n    tools:\n    - name: create-hit\n      description: Create a new Human Intelligence Task for crowdsourced annotation, transcription, or research.\n      hints:\n        readOnly: false\n      call: mturk-requester.create-hit\n      with:\n        title: tools.title\n        description: tools.description\n        reward: tools.reward\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-hits\n      description: List all active and reviewable HITs in the requester account.\n      hints:\n        readOnly: true\n      call: mturk-requester.list-hits\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n    - name: get-hit\n      description: Get detailed information about a specific HIT including status and completion metrics.\n      hints:\n        readOnly: true\n      call: mturk-requester.get-hit\n      with:\n        hitId: tools.hitId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-assignments-for-hit\n      description: List all worker assignments submitted for a specific HIT for review.\n      hints:\n        readOnly: true\n      call: mturk-requester.list-assignments-for-hit\n      with:\n        hitId: tools.hitId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: approve-assignment\n      description: Approve a completed worker assignment and release payment.\n      hints:\n        readOnly: false\n      call: mturk-requester.approve-assignment\n      with:\n        assignmentId: tools.assignmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reject-assignment\n\
  \      description: Reject a completed worker assignment with feedback.\n      hints:\n        readOnly: false\n      call: mturk-requester.reject-assignment\n      with:\n        assignmentId: tools.assignmentId\n        feedback: tools.feedback\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-bonus\n      description: Send a bonus payment to a worker for exceptional task completion.\n      hints:\n        readOnly: false\n      call: mturk-requester.send-bonus\n      with:\n        workerId: tools.workerId\n        bonusAmount: tools.bonusAmount\n        assignmentId: tools.assignmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: notify-workers\n      description: Send notification messages to specific workers.\n      hints:\n        readOnly: false\n      call: mturk-requester.notify-workers\n      with:\n        subject: tools.subject\n        messageText: tools.messageText\n        workerIds: tools.workerIds\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-balance\n      description: Get the current prepaid balance available in the MTurk requester account.\n      hints:\n        readOnly: true\n      call: mturk-requester.get-account-balance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-qualification-types\n      description: List qualification types used to filter and target the right worker pool.\n      hints:\n        readOnly: true\n      call: mturk-requester.list-qualification-types\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-mechanical-turk/refs/heads/main/capabilities/crowdsourcing-workflow.yaml
tags:
- Amazon
- Mechanical Turk
- Crowdsourcing
- Human Intelligence
- Tasks
- Machine Learning
tools:
- description: Create a new Human Intelligence Task for crowdsourced annotation, transcription, or research.
  hints:
    readOnly: false
  name: create-hit
- description: List all active and reviewable HITs in the requester account.
  hints:
    readOnly: true
  name: list-hits
- description: Get detailed information about a specific HIT including status and completion metrics.
  hints:
    readOnly: true
  name: get-hit
- description: List all worker assignments submitted for a specific HIT for review.
  hints:
    readOnly: true
  name: list-assignments-for-hit
- description: Approve a completed worker assignment and release payment.
  hints:
    readOnly: false
  name: approve-assignment
- description: Reject a completed worker assignment with feedback.
  hints:
    readOnly: false
  name: reject-assignment
- description: Send a bonus payment to a worker for exceptional task completion.
  hints:
    readOnly: false
  name: send-bonus
- description: Send notification messages to specific workers.
  hints:
    readOnly: false
  name: notify-workers
- description: Get the current prepaid balance available in the MTurk requester account.
  hints:
    readOnly: true
  name: get-account-balance
- description: List qualification types used to filter and target the right worker pool.
  hints:
    readOnly: true
  name: list-qualification-types
---
