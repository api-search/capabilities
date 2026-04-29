---
categories:
- machine-learning
consumed_apis: []
description: Workflow capability for managing human-in-the-loop review of machine learning predictions using Amazon Augmented AI.
layout: capability
name: Human Review Workflow
operations:
- description: Start a human review loop
  method: POST
  name: start-human-loop
  path: /v1/human-loops
- description: List human review loops
  method: GET
  name: list-human-loops
  path: /v1/human-loops
personas: []
provider_name: Amazon Augmented AI
provider_slug: amazon-augmented-ai
search_terms:
- human review loop management
- start human loop
- list human loops
- describe human loop
- stop human loop
- ai review
- machine learning
- start a human review loop
- list human review loops
- aws
- amazon augmented ai
- list all human review loops to track review progress and status.
- get the current status and output of a specific human review loop.
- initiate human review of an ml prediction by starting a new human loop.
- stop an in-progress human review loop when review is no longer needed.
- human in the loop
slug: human-review-workflow
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Human Review Workflow\n  description: Workflow capability for managing human-in-the-loop review of machine learning predictions using Amazon Augmented AI.\n  tags:\n    - Amazon Augmented AI\n    - Human In The Loop\n    - Machine Learning\n    - AI Review\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nimports:\n  - namespace: a2i\n    from: shared/a2i-api.yaml\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: human-review-rest\n      resources:\n        - path: /v1/human-loops\n          name: human-loops\n          description: Human review loop management\n          operations:\n            - method: POST\n              name: start-human-loop\n              description: Start a human review loop\n              call: \"a2i.start-human-loop\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n       \
  \       name: list-human-loops\n              description: List human review loops\n              call: \"a2i.list-human-loops\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: human-review-mcp\n      transport: http\n      tools:\n        - name: start-human-loop\n          description: Initiate human review of an ML prediction by starting a new human loop.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"a2i.start-human-loop\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-human-loops\n          description: List all human review loops to track review progress and status.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"a2i.list-human-loops\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: describe-human-loop\n          description: Get the current status and output of a specific human review loop.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"a2i.describe-human-loop\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: stop-human-loop\n          description: Stop an in-progress human review loop when review is no longer needed.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"a2i.stop-human-loop\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\npersonas:\n  - name: ML Engineer\n    description: Integrates human review into ML workflows to improve prediction quality.\n    tools:\n      - start-human-loop\n      - list-human-loops\n      - describe-human-loop\n      - stop-human-loop\n\n  - name: Operations Manager\n    description: Monitors human review queues\
  \ and manages reviewer workloads.\n    tools:\n      - list-human-loops\n      - describe-human-loop\n      - stop-human-loop\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-augmented-ai/refs/heads/main/capabilities/human-review-workflow.yaml
tags:
- Amazon Augmented AI
- Human In The Loop
- Machine Learning
- AI Review
- AWS
tools:
- description: Initiate human review of an ML prediction by starting a new human loop.
  hints:
    openWorld: false
    readOnly: false
  name: start-human-loop
- description: List all human review loops to track review progress and status.
  hints:
    openWorld: true
    readOnly: true
  name: list-human-loops
- description: Get the current status and output of a specific human review loop.
  hints:
    openWorld: true
    readOnly: true
  name: describe-human-loop
- description: Stop an in-progress human review loop when review is no longer needed.
  hints:
    openWorld: false
    readOnly: false
  name: stop-human-loop
---
