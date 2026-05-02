---
categories: []
consumed_apis:
- elastic_load_balancing
description: Unified capability for managing Amazon Elastic Load Balancing resources. Combines Amazon Elastic Load Balancing APIs for Cloud Architect workflows in Network Traffic Management.
layout: capability
name: Amazon Elastic Load Balancing Management
operations:
- description: Amazon Elastic Load Balancing Create a Load Balancer
  method: GET
  name: createLoadBalancer
  path: /v1/createLoadBalancer
- description: Amazon Elastic Load Balancing Describe Load Balancers
  method: GET
  name: describeLoadBalancers
  path: /v1/describeLoadBalancers
- description: Amazon Elastic Load Balancing Delete a Load Balancer
  method: GET
  name: deleteLoadBalancer
  path: /v1/deleteLoadBalancer
- description: Amazon Elastic Load Balancing Modify Load Balancer Attributes
  method: GET
  name: modifyLoadBalancerAttributes
  path: /v1/modifyLoadBalancerAttributes
- description: Amazon Elastic Load Balancing Create a Target Group
  method: GET
  name: createTargetGroup
  path: /v1/createTargetGroup
- description: Amazon Elastic Load Balancing Describe Target Groups
  method: GET
  name: describeTargetGroups
  path: /v1/describeTargetGroups
- description: Amazon Elastic Load Balancing Register Targets with a Target Group
  method: GET
  name: registerTargets
  path: /v1/registerTargets
- description: Amazon Elastic Load Balancing Deregister Targets from a Target Group
  method: GET
  name: deregisterTargets
  path: /v1/deregisterTargets
- description: Amazon Elastic Load Balancing Describe Target Health
  method: GET
  name: describeTargetHealth
  path: /v1/describeTargetHealth
- description: Amazon Elastic Load Balancing Create a Listener
  method: GET
  name: createListener
  path: /v1/createListener
- description: Amazon Elastic Load Balancing Describe Listeners
  method: GET
  name: describeListeners
  path: /v1/describeListeners
- description: Amazon Elastic Load Balancing Create a Listener Rule
  method: GET
  name: createRule
  path: /v1/createRule
- description: Amazon Elastic Load Balancing Describe Listener Rules
  method: GET
  name: describeRules
  path: /v1/describeRules
personas: []
provider_name: Amazon Elastic Load Balancing
provider_slug: amazon-elastic-load-balancing
search_terms:
- networking
- createListener
- amazon elastic load balancing describe target health
- amazon elastic load balancing delete a load balancer
- scalability
- createTargetGroup
- amazon elastic load balancing describe load balancers
- describeTargetHealth
- describeTargetGroups
- operations teams managing amazon elastic load balancing infrastructure
- distribute incoming traffic across multiple targets for high availability
- describeLoadBalancers
- modifyLoadBalancerAttributes
- describeListeners
- createRule
- amazon elastic load balancing describe listener rules
- developers building applications using amazon elastic load balancing
- amazon elastic load balancing create a load balancer
- load balancing
- createLoadBalancer
- amazon elastic load balancing create a listener
- amazon elastic load balancing register targets with a target group
- amazon elastic load balancing create a listener rule
- amazon elastic load balancing modify load balancer attributes
- amazon elastic load balancing create a target group
- amazon elastic load balancing deregister targets from a target group
- amazon web services
- deleteLoadBalancer
- amazon elastic load balancing describe listeners
- high availability
- unified capability for managing amazon elastic load balancing resources. combines amazon elastic load balancing apis for cloud architect workflows in network traffic management.
- amazon elastic load balancing describe target groups
- registerTargets
- describeRules
- deregisterTargets
slug: amazon-elastic-load-balancing-capability
source_filename: amazon-elastic-load-balancing-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Elastic Load Balancing Management\n  description: Unified capability for managing Amazon Elastic Load Balancing resources. Combines Amazon Elastic Load Balancing APIs for Cloud Architect workflows in Network Traffic Management.\n  tags:\n  - Amazon Web Services\n  - Load Balancing\n  - Networking\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_API_KEY: AWS_API_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: elastic_load_balancing\n    location: ./shared/elastic-load-balancing.yaml\n  exposes:\n  - type: rest\n    port: 8182\n    namespace: amazon-elastic-load-balancing-workflow-api\n    description: Unified REST API for Amazon Elastic Load Balancing management.\n    resources:\n    - path: /v1/createLoadBalancer\n      name: createLoadBalancer\n      description: Amazon Elastic Load Balancing Create a Load Balancer\n      operations:\n      - method: GET\n   \
  \     name: createLoadBalancer\n        description: Amazon Elastic Load Balancing Create a Load Balancer\n        call: api.createLoadBalancer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/describeLoadBalancers\n      name: describeLoadBalancers\n      description: Amazon Elastic Load Balancing Describe Load Balancers\n      operations:\n      - method: GET\n        name: describeLoadBalancers\n        description: Amazon Elastic Load Balancing Describe Load Balancers\n        call: api.describeLoadBalancers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deleteLoadBalancer\n      name: deleteLoadBalancer\n      description: Amazon Elastic Load Balancing Delete a Load Balancer\n      operations:\n      - method: GET\n        name: deleteLoadBalancer\n        description: Amazon Elastic Load Balancing Delete a Load Balancer\n        call: api.deleteLoadBalancer\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /v1/modifyLoadBalancerAttributes\n      name: modifyLoadBalancerAttributes\n      description: Amazon Elastic Load Balancing Modify Load Balancer Attributes\n      operations:\n      - method: GET\n        name: modifyLoadBalancerAttributes\n        description: Amazon Elastic Load Balancing Modify Load Balancer Attributes\n        call: api.modifyLoadBalancerAttributes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/createTargetGroup\n      name: createTargetGroup\n      description: Amazon Elastic Load Balancing Create a Target Group\n      operations:\n      - method: GET\n        name: createTargetGroup\n        description: Amazon Elastic Load Balancing Create a Target Group\n        call: api.createTargetGroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/describeTargetGroups\n      name: describeTargetGroups\n      description: Amazon Elastic\
  \ Load Balancing Describe Target Groups\n      operations:\n      - method: GET\n        name: describeTargetGroups\n        description: Amazon Elastic Load Balancing Describe Target Groups\n        call: api.describeTargetGroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/registerTargets\n      name: registerTargets\n      description: Amazon Elastic Load Balancing Register Targets with a Target Group\n      operations:\n      - method: GET\n        name: registerTargets\n        description: Amazon Elastic Load Balancing Register Targets with a Target Group\n        call: api.registerTargets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deregisterTargets\n      name: deregisterTargets\n      description: Amazon Elastic Load Balancing Deregister Targets from a Target Group\n      operations:\n      - method: GET\n        name: deregisterTargets\n        description: Amazon Elastic Load Balancing\
  \ Deregister Targets from a Target Group\n        call: api.deregisterTargets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/describeTargetHealth\n      name: describeTargetHealth\n      description: Amazon Elastic Load Balancing Describe Target Health\n      operations:\n      - method: GET\n        name: describeTargetHealth\n        description: Amazon Elastic Load Balancing Describe Target Health\n        call: api.describeTargetHealth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/createListener\n      name: createListener\n      description: Amazon Elastic Load Balancing Create a Listener\n      operations:\n      - method: GET\n        name: createListener\n        description: Amazon Elastic Load Balancing Create a Listener\n        call: api.createListener\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/describeListeners\n      name: describeListeners\n\
  \      description: Amazon Elastic Load Balancing Describe Listeners\n      operations:\n      - method: GET\n        name: describeListeners\n        description: Amazon Elastic Load Balancing Describe Listeners\n        call: api.describeListeners\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/createRule\n      name: createRule\n      description: Amazon Elastic Load Balancing Create a Listener Rule\n      operations:\n      - method: GET\n        name: createRule\n        description: Amazon Elastic Load Balancing Create a Listener Rule\n        call: api.createRule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/describeRules\n      name: describeRules\n      description: Amazon Elastic Load Balancing Describe Listener Rules\n      operations:\n      - method: GET\n        name: describeRules\n        description: Amazon Elastic Load Balancing Describe Listener Rules\n        call: api.describeRules\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9192\n    namespace: amazon-elastic-load-balancing-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Elastic Load Balancing management.\n    tools:\n    - name: createLoadBalancer\n      description: Amazon Elastic Load Balancing Create a Load Balancer\n      hints:\n        readOnly: true\n      call: api.createLoadBalancer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeLoadBalancers\n      description: Amazon Elastic Load Balancing Describe Load Balancers\n      hints:\n        readOnly: true\n      call: api.describeLoadBalancers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteLoadBalancer\n      description: Amazon Elastic Load Balancing Delete a Load Balancer\n      hints:\n        readOnly: true\n      call: api.deleteLoadBalancer\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: modifyLoadBalancerAttributes\n      description: Amazon Elastic Load Balancing Modify Load Balancer Attributes\n      hints:\n        readOnly: true\n      call: api.modifyLoadBalancerAttributes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createTargetGroup\n      description: Amazon Elastic Load Balancing Create a Target Group\n      hints:\n        readOnly: true\n      call: api.createTargetGroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeTargetGroups\n      description: Amazon Elastic Load Balancing Describe Target Groups\n      hints:\n        readOnly: true\n      call: api.describeTargetGroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: registerTargets\n      description: Amazon Elastic Load Balancing Register Targets with a Target Group\n      hints:\n        readOnly: true\n      call: api.registerTargets\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: deregisterTargets\n      description: Amazon Elastic Load Balancing Deregister Targets from a Target Group\n      hints:\n        readOnly: true\n      call: api.deregisterTargets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeTargetHealth\n      description: Amazon Elastic Load Balancing Describe Target Health\n      hints:\n        readOnly: true\n      call: api.describeTargetHealth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createListener\n      description: Amazon Elastic Load Balancing Create a Listener\n      hints:\n        readOnly: true\n      call: api.createListener\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeListeners\n      description: Amazon Elastic Load Balancing Describe Listeners\n      hints:\n        readOnly: true\n      call: api.describeListeners\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: createRule\n      description: Amazon Elastic Load Balancing Create a Listener Rule\n      hints:\n        readOnly: true\n      call: api.createRule\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeRules\n      description: Amazon Elastic Load Balancing Describe Listener Rules\n      hints:\n        readOnly: true\n      call: api.describeRules\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-elastic-load-balancing/refs/heads/main/capabilities/amazon-elastic-load-balancing-capability.yaml
tags:
- Amazon Web Services
- Load Balancing
- Networking
tools:
- description: Amazon Elastic Load Balancing Create a Load Balancer
  hints:
    readOnly: true
  name: createLoadBalancer
- description: Amazon Elastic Load Balancing Describe Load Balancers
  hints:
    readOnly: true
  name: describeLoadBalancers
- description: Amazon Elastic Load Balancing Delete a Load Balancer
  hints:
    readOnly: true
  name: deleteLoadBalancer
- description: Amazon Elastic Load Balancing Modify Load Balancer Attributes
  hints:
    readOnly: true
  name: modifyLoadBalancerAttributes
- description: Amazon Elastic Load Balancing Create a Target Group
  hints:
    readOnly: true
  name: createTargetGroup
- description: Amazon Elastic Load Balancing Describe Target Groups
  hints:
    readOnly: true
  name: describeTargetGroups
- description: Amazon Elastic Load Balancing Register Targets with a Target Group
  hints:
    readOnly: true
  name: registerTargets
- description: Amazon Elastic Load Balancing Deregister Targets from a Target Group
  hints:
    readOnly: true
  name: deregisterTargets
- description: Amazon Elastic Load Balancing Describe Target Health
  hints:
    readOnly: true
  name: describeTargetHealth
- description: Amazon Elastic Load Balancing Create a Listener
  hints:
    readOnly: true
  name: createListener
- description: Amazon Elastic Load Balancing Describe Listeners
  hints:
    readOnly: true
  name: describeListeners
- description: Amazon Elastic Load Balancing Create a Listener Rule
  hints:
    readOnly: true
  name: createRule
- description: Amazon Elastic Load Balancing Describe Listener Rules
  hints:
    readOnly: true
  name: describeRules
---
