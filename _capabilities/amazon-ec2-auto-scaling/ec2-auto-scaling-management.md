---
categories: []
consumed_apis:
- ec2-auto-scaling
description: Unified capability for managing EC2 Auto Scaling groups, scaling policies, and lifecycle hooks for cloud operations engineers.
layout: capability
name: Amazon EC2 Auto Scaling Auto Scaling Group Management
operations:
- description: Amazon EC2 Auto Scaling GET_ Attach Instances
  method: GET
  name: GET_AttachInstances
  path: /v1/resource
- description: Amazon EC2 Auto Scaling POST_ Attach Instances
  method: POST
  name: POST_AttachInstances
  path: /v1/resource
- description: Amazon EC2 Auto Scaling GET_ Attach Load Balancer Target Groups
  method: GET
  name: GET_AttachLoadBalancerTargetGroups
  path: /v1/resource
- description: Amazon EC2 Auto Scaling POST_ Attach Load Balancer Target Groups
  method: POST
  name: POST_AttachLoadBalancerTargetGroups
  path: /v1/resource
- description: Amazon EC2 Auto Scaling GET_ Attach Load Balancers
  method: GET
  name: GET_AttachLoadBalancers
  path: /v1/resource
- description: Amazon EC2 Auto Scaling POST_ Attach Load Balancers
  method: POST
  name: POST_AttachLoadBalancers
  path: /v1/resource
- description: Amazon EC2 Auto Scaling GET_ Attach Traffic Sources
  method: GET
  name: GET_AttachTrafficSources
  path: /v1/resource
- description: Amazon EC2 Auto Scaling POST_ Attach Traffic Sources
  method: POST
  name: POST_AttachTrafficSources
  path: /v1/resource
- description: Amazon EC2 Auto Scaling GET_ Batch Delete Scheduled Action
  method: GET
  name: GET_BatchDeleteScheduledAction
  path: /v1/resource
- description: Amazon EC2 Auto Scaling POST_ Batch Delete Scheduled Action
  method: POST
  name: POST_BatchDeleteScheduledAction
  path: /v1/resource
personas: []
provider_name: Amazon EC2 Auto Scaling
provider_slug: amazon-ec2-auto-scaling
search_terms:
- post_ attach load balancers
- get_ batch delete scheduled action
- amazon ec2 auto scaling get_ attach traffic sources
- amazon ec2 auto scaling post_ attach instances
- POST_AttachInstances
- amazon ec2 auto scaling get_ batch delete scheduled action
- get_ attach instances
- auto scaling management business domain.
- amazon ec2 auto scaling get_ attach instances
- get_ attach load balancers
- post_ attach traffic sources
- aws
- amazon ec2 auto scaling
- post_ batch delete scheduled action
- ec2
- amazon ec2 auto scaling post_ attach load balancers
- GET_AttachLoadBalancerTargetGroups
- amazon ec2 auto scaling get_ attach load balancers
- compute
- scaling
- GET_AttachLoadBalancers
- post_ attach load balancer target groups
- amazon ec2 auto scaling get_ attach load balancer target groups
- amazon ec2 auto scaling post_ attach traffic sources
- get_ attach traffic sources
- POST_BatchDeleteScheduledAction
- post_ attach instances
- auto scaling
- get_ attach load balancer target groups
- engineers managing ec2 auto scaling fleets.
- GET_AttachTrafficSources
- POST_AttachLoadBalancerTargetGroups
- GET_AttachInstances
- POST_AttachLoadBalancers
- POST_AttachTrafficSources
- amazon web services
- amazon ec2 auto scaling post_ attach load balancer target groups
- workflow for auto scaling management.
- amazon ec2 auto scaling post_ batch delete scheduled action
- high availability
- GET_BatchDeleteScheduledAction
slug: ec2-auto-scaling-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon EC2 Auto Scaling Auto Scaling Group Management\"\n  description: \"Unified capability for managing EC2 Auto Scaling groups, scaling policies, and lifecycle hooks for cloud operations engineers.\"\n  tags:\n    - Amazon EC2 Auto Scaling\n    - AWS\n    - Compute\n    - Auto Scaling\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: ec2-auto-scaling\n      location: ./shared/ec2-auto-scaling.yaml\n\n  exposes:\n    - type: rest\n      port: 8087\n      namespace: ec2-auto-scaling-api\n      description: \"Unified REST API for Auto Scaling Group Management.\"\n      resources:\n        - path: /v1/resource\n          name: GET_AttachInstances\n          description: \"Amazon EC2 Auto Scaling GET_ Attach Instances\"\n          operations:\n   \
  \         - method: GET\n              name: GET_AttachInstances\n              description: \"Amazon EC2 Auto Scaling GET_ Attach Instances\"\n              call: \"ec2-auto-scaling.GET_AttachInstances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resource\n          name: POST_AttachInstances\n          description: \"Amazon EC2 Auto Scaling POST_ Attach Instances\"\n          operations:\n            - method: POST\n              name: POST_AttachInstances\n              description: \"Amazon EC2 Auto Scaling POST_ Attach Instances\"\n              call: \"ec2-auto-scaling.POST_AttachInstances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resource\n          name: GET_AttachLoadBalancerTargetGroups\n          description: \"Amazon EC2 Auto Scaling GET_ Attach Load Balancer Target Groups\"\n          operations:\n            - method:\
  \ GET\n              name: GET_AttachLoadBalancerTargetGroups\n              description: \"Amazon EC2 Auto Scaling GET_ Attach Load Balancer Target Groups\"\n              call: \"ec2-auto-scaling.GET_AttachLoadBalancerTargetGroups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resource\n          name: POST_AttachLoadBalancerTargetGroups\n          description: \"Amazon EC2 Auto Scaling POST_ Attach Load Balancer Target Groups\"\n          operations:\n            - method: POST\n              name: POST_AttachLoadBalancerTargetGroups\n              description: \"Amazon EC2 Auto Scaling POST_ Attach Load Balancer Target Groups\"\n              call: \"ec2-auto-scaling.POST_AttachLoadBalancerTargetGroups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resource\n          name: GET_AttachLoadBalancers\n          description: \"Amazon EC2\
  \ Auto Scaling GET_ Attach Load Balancers\"\n          operations:\n            - method: GET\n              name: GET_AttachLoadBalancers\n              description: \"Amazon EC2 Auto Scaling GET_ Attach Load Balancers\"\n              call: \"ec2-auto-scaling.GET_AttachLoadBalancers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resource\n          name: POST_AttachLoadBalancers\n          description: \"Amazon EC2 Auto Scaling POST_ Attach Load Balancers\"\n          operations:\n            - method: POST\n              name: POST_AttachLoadBalancers\n              description: \"Amazon EC2 Auto Scaling POST_ Attach Load Balancers\"\n              call: \"ec2-auto-scaling.POST_AttachLoadBalancers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resource\n          name: GET_AttachTrafficSources\n          description: \"Amazon EC2 Auto\
  \ Scaling GET_ Attach Traffic Sources\"\n          operations:\n            - method: GET\n              name: GET_AttachTrafficSources\n              description: \"Amazon EC2 Auto Scaling GET_ Attach Traffic Sources\"\n              call: \"ec2-auto-scaling.GET_AttachTrafficSources\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resource\n          name: POST_AttachTrafficSources\n          description: \"Amazon EC2 Auto Scaling POST_ Attach Traffic Sources\"\n          operations:\n            - method: POST\n              name: POST_AttachTrafficSources\n              description: \"Amazon EC2 Auto Scaling POST_ Attach Traffic Sources\"\n              call: \"ec2-auto-scaling.POST_AttachTrafficSources\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resource\n          name: GET_BatchDeleteScheduledAction\n          description: \"Amazon\
  \ EC2 Auto Scaling GET_ Batch Delete Scheduled Action\"\n          operations:\n            - method: GET\n              name: GET_BatchDeleteScheduledAction\n              description: \"Amazon EC2 Auto Scaling GET_ Batch Delete Scheduled Action\"\n              call: \"ec2-auto-scaling.GET_BatchDeleteScheduledAction\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resource\n          name: POST_BatchDeleteScheduledAction\n          description: \"Amazon EC2 Auto Scaling POST_ Batch Delete Scheduled Action\"\n          operations:\n            - method: POST\n              name: POST_BatchDeleteScheduledAction\n              description: \"Amazon EC2 Auto Scaling POST_ Batch Delete Scheduled Action\"\n              call: \"ec2-auto-scaling.POST_BatchDeleteScheduledAction\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9097\n  \
  \    namespace: ec2-auto-scaling-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Auto Scaling Group Management.\"\n      tools:\n        - name: get_-attach-instances\n          description: \"Amazon EC2 Auto Scaling GET_ Attach Instances\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2-auto-scaling.GET_AttachInstances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: post_-attach-instances\n          description: \"Amazon EC2 Auto Scaling POST_ Attach Instances\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-auto-scaling.POST_AttachInstances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get_-attach-load-balancer-target-groups\n          description: \"Amazon EC2 Auto Scaling GET_ Attach Load Balancer Target Groups\"\n          hints:\n\
  \            readOnly: true\n            destructive: false\n          call: \"ec2-auto-scaling.GET_AttachLoadBalancerTargetGroups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: post_-attach-load-balancer-target-groups\n          description: \"Amazon EC2 Auto Scaling POST_ Attach Load Balancer Target Groups\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-auto-scaling.POST_AttachLoadBalancerTargetGroups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get_-attach-load-balancers\n          description: \"Amazon EC2 Auto Scaling GET_ Attach Load Balancers\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2-auto-scaling.GET_AttachLoadBalancers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: post_-attach-load-balancers\n\
  \          description: \"Amazon EC2 Auto Scaling POST_ Attach Load Balancers\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-auto-scaling.POST_AttachLoadBalancers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get_-attach-traffic-sources\n          description: \"Amazon EC2 Auto Scaling GET_ Attach Traffic Sources\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2-auto-scaling.GET_AttachTrafficSources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: post_-attach-traffic-sources\n          description: \"Amazon EC2 Auto Scaling POST_ Attach Traffic Sources\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-auto-scaling.POST_AttachTrafficSources\"\n          outputParameters:\n            - type: object\n       \
  \       mapping: \"$.\"\n        - name: get_-batch-delete-scheduled-action\n          description: \"Amazon EC2 Auto Scaling GET_ Batch Delete Scheduled Action\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"ec2-auto-scaling.GET_BatchDeleteScheduledAction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: post_-batch-delete-scheduled-action\n          description: \"Amazon EC2 Auto Scaling POST_ Batch Delete Scheduled Action\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"ec2-auto-scaling.POST_BatchDeleteScheduledAction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-ec2-auto-scaling/refs/heads/main/capabilities/ec2-auto-scaling-management.yaml
tags:
- Amazon EC2 Auto Scaling
- AWS
- Compute
- Auto Scaling
tools:
- description: Amazon EC2 Auto Scaling GET_ Attach Instances
  hints:
    destructive: false
    readOnly: true
  name: get_-attach-instances
- description: Amazon EC2 Auto Scaling POST_ Attach Instances
  hints:
    destructive: false
    readOnly: false
  name: post_-attach-instances
- description: Amazon EC2 Auto Scaling GET_ Attach Load Balancer Target Groups
  hints:
    destructive: false
    readOnly: true
  name: get_-attach-load-balancer-target-groups
- description: Amazon EC2 Auto Scaling POST_ Attach Load Balancer Target Groups
  hints:
    destructive: false
    readOnly: false
  name: post_-attach-load-balancer-target-groups
- description: Amazon EC2 Auto Scaling GET_ Attach Load Balancers
  hints:
    destructive: false
    readOnly: true
  name: get_-attach-load-balancers
- description: Amazon EC2 Auto Scaling POST_ Attach Load Balancers
  hints:
    destructive: false
    readOnly: false
  name: post_-attach-load-balancers
- description: Amazon EC2 Auto Scaling GET_ Attach Traffic Sources
  hints:
    destructive: false
    readOnly: true
  name: get_-attach-traffic-sources
- description: Amazon EC2 Auto Scaling POST_ Attach Traffic Sources
  hints:
    destructive: false
    readOnly: false
  name: post_-attach-traffic-sources
- description: Amazon EC2 Auto Scaling GET_ Batch Delete Scheduled Action
  hints:
    destructive: false
    readOnly: true
  name: get_-batch-delete-scheduled-action
- description: Amazon EC2 Auto Scaling POST_ Batch Delete Scheduled Action
  hints:
    destructive: false
    readOnly: false
  name: post_-batch-delete-scheduled-action
---
