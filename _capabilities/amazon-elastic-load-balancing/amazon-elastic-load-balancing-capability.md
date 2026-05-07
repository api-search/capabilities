---
categories: []
consumed_apis: []
description: Amazon Elastic Load Balancing automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, IP addresses, and Lambda functions. It supports Application Load Balancers, Network Load Balancers, and Gateway Load Balancers.
layout: capability
name: Amazon Elastic Load Balancing v2 API
operations:
- description: Amazon Elastic Load Balancing Create a Load Balancer
  method: GET
  name: createloadbalancer
  path: /?Action=CreateLoadBalancer
- description: Amazon Elastic Load Balancing Describe Load Balancers
  method: GET
  name: describeloadbalancers
  path: /?Action=DescribeLoadBalancers
- description: Amazon Elastic Load Balancing Delete a Load Balancer
  method: GET
  name: deleteloadbalancer
  path: /?Action=DeleteLoadBalancer
- description: Amazon Elastic Load Balancing Modify Load Balancer Attributes
  method: GET
  name: modifyloadbalancerattributes
  path: /?Action=ModifyLoadBalancerAttributes
- description: Amazon Elastic Load Balancing Create a Target Group
  method: GET
  name: createtargetgroup
  path: /?Action=CreateTargetGroup
- description: Amazon Elastic Load Balancing Describe Target Groups
  method: GET
  name: describetargetgroups
  path: /?Action=DescribeTargetGroups
- description: Amazon Elastic Load Balancing Register Targets with a Target Group
  method: GET
  name: registertargets
  path: /?Action=RegisterTargets
- description: Amazon Elastic Load Balancing Deregister Targets from a Target Group
  method: GET
  name: deregistertargets
  path: /?Action=DeregisterTargets
- description: Amazon Elastic Load Balancing Describe Target Health
  method: GET
  name: describetargethealth
  path: /?Action=DescribeTargetHealth
- description: Amazon Elastic Load Balancing Create a Listener
  method: GET
  name: createlistener
  path: /?Action=CreateListener
- description: Amazon Elastic Load Balancing Describe Listeners
  method: GET
  name: describelisteners
  path: /?Action=DescribeListeners
- description: Amazon Elastic Load Balancing Create a Listener Rule
  method: GET
  name: createrule
  path: /?Action=CreateRule
- description: Amazon Elastic Load Balancing Describe Listener Rules
  method: GET
  name: describerules
  path: /?Action=DescribeRules
personas: []
provider_name: Amazon Elastic Load Balancing
provider_slug: amazon-elastic-load-balancing
search_terms:
- amazon elastic load balancing describe listener rules
- networking
- amazon web services
- describelisteners
- amazon elastic load balancing describe load balancers
- describetargetgroups
- api
- distribute incoming traffic across multiple targets for high availability
- scalability
- amazon elastic load balancing create a listener rule
- registertargets
- amazon
- high availability
- amazon elastic load balancing describe target groups
- createlistener
- elastic
- unified capability for managing amazon elastic load balancing resources. combines amazon elastic load balancing apis for cloud architect workflows in network traffic management.
- describeloadbalancers
- deregistertargets
- amazon elastic load balancing create a target group
- describetargethealth
- load balancing
- amazon elastic load balancing register targets with a target group
- amazon elastic load balancing describe listeners
- amazon elastic load balancing create a load balancer
- deleteloadbalancer
- balancing
- operations teams managing amazon elastic load balancing infrastructure
- describerules
- amazon elastic load balancing describe target health
- amazon elastic load balancing create a listener
- createrule
- createloadbalancer
- modifyloadbalancerattributes
- amazon elastic load balancing delete a load balancer
- createtargetgroup
- amazon elastic load balancing modify load balancer attributes
- developers building applications using amazon elastic load balancing
- load
- amazon elastic load balancing deregister targets from a target group
slug: amazon-elastic-load-balancing-capability
source_filename: amazon-elastic-load-balancing-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Elastic Load Balancing v2 API\n  description: Amazon Elastic Load Balancing automatically distributes incoming application traffic across multiple targets,\n    such as Amazon EC2 instances, containers, IP addresses, and Lambda functions. It supports Application Load Balancers,\n    Network Load Balancers, and Gateway Load Balancers.\n  tags:\n  - Amazon\n  - Elastic\n  - Load\n  - Balancing\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-elastic-load-balancing\n    baseUri: https://elasticloadbalancing.us-east-1.amazonaws.com\n    description: Amazon Elastic Load Balancing v2 API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AMAZON_ELASTIC_LOAD_BALANCING_TOKEN}}'\n    resources:\n    - name: action-createloadbalancer\n      path: /?Action=CreateLoadBalancer\n      operations:\n      - name:\
  \ createloadbalancer\n        method: GET\n        description: Amazon Elastic Load Balancing Create a Load Balancer\n        inputParameters:\n        - name: Name\n          in: query\n          type: string\n          required: true\n          description: The name of the load balancer. Must be unique per region per account, can have a maximum of 32 characters.\n        - name: Subnets\n          in: query\n          type: array\n          description: The IDs of the subnets. You can specify only one subnet per Availability Zone.\n        - name: SecurityGroups\n          in: query\n          type: array\n          description: The IDs of the security groups for the load balancer\n        - name: Scheme\n          in: query\n          type: string\n          description: The scheme for the load balancer. An internet-facing load balancer routes requests from clients to\n            targets over the internet. An internal load balancer routes r\n        - name: Type\n          in: query\n\
  \          type: string\n          description: The type of load balancer\n        - name: IpAddressType\n          in: query\n          type: string\n          description: The type of IP addresses used by the subnets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: action-describeloadbalancers\n      path: /?Action=DescribeLoadBalancers\n      operations:\n      - name: describeloadbalancers\n        method: GET\n        description: Amazon Elastic Load Balancing Describe Load Balancers\n        inputParameters:\n        - name: LoadBalancerArns\n          in: query\n          type: array\n          description: The Amazon Resource Names (ARN) of the load balancers\n        - name: Names\n          in: query\n          type: array\n          description: The names of the load balancers\n        - name: Marker\n          in: query\n          type: string\n          description: The marker for the\
  \ next set of results\n        - name: PageSize\n          in: query\n          type: integer\n          description: The maximum number of results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: action-deleteloadbalancer\n      path: /?Action=DeleteLoadBalancer\n      operations:\n      - name: deleteloadbalancer\n        method: GET\n        description: Amazon Elastic Load Balancing Delete a Load Balancer\n        inputParameters:\n        - name: LoadBalancerArn\n          in: query\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the load balancer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: action-modifyloadbalancerattributes\n      path: /?Action=ModifyLoadBalancerAttributes\n      operations:\n      - name: modifyloadbalancerattributes\n\
  \        method: GET\n        description: Amazon Elastic Load Balancing Modify Load Balancer Attributes\n        inputParameters:\n        - name: LoadBalancerArn\n          in: query\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the load balancer\n        - name: Attributes.member.1.Key\n          in: query\n          type: string\n          description: The name of the attribute\n        - name: Attributes.member.1.Value\n          in: query\n          type: string\n          description: The value of the attribute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: action-createtargetgroup\n      path: /?Action=CreateTargetGroup\n      operations:\n      - name: createtargetgroup\n        method: GET\n        description: Amazon Elastic Load Balancing Create a Target Group\n        inputParameters:\n        - name: Name\n          in:\
  \ query\n          type: string\n          required: true\n          description: The name of the target group. Must be unique per region per account.\n        - name: Protocol\n          in: query\n          type: string\n          description: The protocol to use for routing traffic to the targets\n        - name: Port\n          in: query\n          type: integer\n          description: The port on which the targets receive traffic\n        - name: VpcId\n          in: query\n          type: string\n          description: The identifier of the VPC for the targets\n        - name: HealthCheckProtocol\n          in: query\n          type: string\n          description: The protocol to use for health checks\n        - name: HealthCheckPort\n          in: query\n          type: string\n          description: The port to use for health checks\n        - name: HealthCheckPath\n          in: query\n          type: string\n          description: The destination for health checks on the targets\n\
  \        - name: TargetType\n          in: query\n          type: string\n          description: The type of target to register with the target group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: action-describetargetgroups\n      path: /?Action=DescribeTargetGroups\n      operations:\n      - name: describetargetgroups\n        method: GET\n        description: Amazon Elastic Load Balancing Describe Target Groups\n        inputParameters:\n        - name: LoadBalancerArn\n          in: query\n          type: string\n          description: The ARN of the load balancer\n        - name: TargetGroupArns\n          in: query\n          type: array\n          description: The ARNs of the target groups\n        - name: Names\n          in: query\n          type: array\n          description: The names of the target groups\n        - name: Marker\n          in: query\n          type: string\n       \
  \   description: The marker for the next set of results\n        - name: PageSize\n          in: query\n          type: integer\n          description: The maximum number of results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: action-registertargets\n      path: /?Action=RegisterTargets\n      operations:\n      - name: registertargets\n        method: GET\n        description: Amazon Elastic Load Balancing Register Targets with a Target Group\n        inputParameters:\n        - name: TargetGroupArn\n          in: query\n          type: string\n          required: true\n          description: The ARN of the target group\n        - name: Targets.member.1.Id\n          in: query\n          type: string\n          required: true\n          description: The ID of the target (instance ID, IP address, or Lambda ARN)\n        - name: Targets.member.1.Port\n          in: query\n          type:\
  \ integer\n          description: The port on which the target is listening\n        - name: Targets.member.1.AvailabilityZone\n          in: query\n          type: string\n          description: The Availability Zone where the target is located\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: action-deregistertargets\n      path: /?Action=DeregisterTargets\n      operations:\n      - name: deregistertargets\n        method: GET\n        description: Amazon Elastic Load Balancing Deregister Targets from a Target Group\n        inputParameters:\n        - name: TargetGroupArn\n          in: query\n          type: string\n          required: true\n          description: The ARN of the target group\n        - name: Targets.member.1.Id\n          in: query\n          type: string\n          required: true\n          description: The ID of the target\n        - name: Targets.member.1.Port\n          in:\
  \ query\n          type: integer\n          description: The port on which the target is listening\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: action-describetargethealth\n      path: /?Action=DescribeTargetHealth\n      operations:\n      - name: describetargethealth\n        method: GET\n        description: Amazon Elastic Load Balancing Describe Target Health\n        inputParameters:\n        - name: TargetGroupArn\n          in: query\n          type: string\n          required: true\n          description: The ARN of the target group\n        - name: Targets.member.1.Id\n          in: query\n          type: string\n          description: The ID of the target\n        - name: Targets.member.1.Port\n          in: query\n          type: integer\n          description: The port on which the target is listening\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: action-createlistener\n      path: /?Action=CreateListener\n      operations:\n      - name: createlistener\n        method: GET\n        description: Amazon Elastic Load Balancing Create a Listener\n        inputParameters:\n        - name: LoadBalancerArn\n          in: query\n          type: string\n          required: true\n          description: The ARN of the load balancer\n        - name: Protocol\n          in: query\n          type: string\n          description: The protocol for connections from clients to the load balancer\n        - name: Port\n          in: query\n          type: integer\n          required: true\n          description: The port on which the load balancer is listening\n        - name: SslPolicy\n          in: query\n          type: string\n          description: The security policy that defines which protocols and ciphers are supported\n        - name: DefaultActions.member.1.Type\n          in: query\n\
  \          type: string\n          required: true\n          description: The type of action\n        - name: DefaultActions.member.1.TargetGroupArn\n          in: query\n          type: string\n          description: The ARN of the target group for forward actions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: action-describelisteners\n      path: /?Action=DescribeListeners\n      operations:\n      - name: describelisteners\n        method: GET\n        description: Amazon Elastic Load Balancing Describe Listeners\n        inputParameters:\n        - name: LoadBalancerArn\n          in: query\n          type: string\n          description: The ARN of the load balancer\n        - name: ListenerArns\n          in: query\n          type: array\n          description: The ARNs of the listeners\n        - name: Marker\n          in: query\n          type: string\n          description: The marker\
  \ for the next set of results\n        - name: PageSize\n          in: query\n          type: integer\n          description: The maximum number of results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: action-createrule\n      path: /?Action=CreateRule\n      operations:\n      - name: createrule\n        method: GET\n        description: Amazon Elastic Load Balancing Create a Listener Rule\n        inputParameters:\n        - name: ListenerArn\n          in: query\n          type: string\n          required: true\n          description: The ARN of the listener\n        - name: Priority\n          in: query\n          type: integer\n          required: true\n          description: The rule priority. Must be unique within the listener.\n        - name: Conditions.member.1.Field\n          in: query\n          type: string\n          description: The name of the field (host-header, path-pattern,\
  \ etc.)\n        - name: Conditions.member.1.Values\n          in: query\n          type: array\n          description: The condition values\n        - name: Actions.member.1.Type\n          in: query\n          type: string\n          required: true\n          description: The type of action\n        - name: Actions.member.1.TargetGroupArn\n          in: query\n          type: string\n          description: The ARN of the target group for forward actions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: action-describerules\n      path: /?Action=DescribeRules\n      operations:\n      - name: describerules\n        method: GET\n        description: Amazon Elastic Load Balancing Describe Listener Rules\n        inputParameters:\n        - name: ListenerArn\n          in: query\n          type: string\n          description: The ARN of the listener\n        - name: RuleArns\n          in: query\n \
  \         type: array\n          description: The ARNs of the rules\n        - name: Marker\n          in: query\n          type: string\n          description: The marker for the next set of results\n        - name: PageSize\n          in: query\n          type: integer\n          description: The maximum number of results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-elastic-load-balancing-rest\n    description: REST adapter for Amazon Elastic Load Balancing v2 API.\n    resources:\n    - path: /?Action=CreateLoadBalancer\n      name: createloadbalancer\n      operations:\n      - method: GET\n        name: createloadbalancer\n        description: Amazon Elastic Load Balancing Create a Load Balancer\n        call: amazon-elastic-load-balancing.createloadbalancer\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /?Action=DescribeLoadBalancers\n      name: describeloadbalancers\n      operations:\n      - method: GET\n        name: describeloadbalancers\n        description: Amazon Elastic Load Balancing Describe Load Balancers\n        call: amazon-elastic-load-balancing.describeloadbalancers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?Action=DeleteLoadBalancer\n      name: deleteloadbalancer\n      operations:\n      - method: GET\n        name: deleteloadbalancer\n        description: Amazon Elastic Load Balancing Delete a Load Balancer\n        call: amazon-elastic-load-balancing.deleteloadbalancer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?Action=ModifyLoadBalancerAttributes\n      name: modifyloadbalancerattributes\n      operations:\n      - method: GET\n        name: modifyloadbalancerattributes\n        description: Amazon Elastic Load Balancing Modify Load Balancer Attributes\n\
  \        call: amazon-elastic-load-balancing.modifyloadbalancerattributes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?Action=CreateTargetGroup\n      name: createtargetgroup\n      operations:\n      - method: GET\n        name: createtargetgroup\n        description: Amazon Elastic Load Balancing Create a Target Group\n        call: amazon-elastic-load-balancing.createtargetgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?Action=DescribeTargetGroups\n      name: describetargetgroups\n      operations:\n      - method: GET\n        name: describetargetgroups\n        description: Amazon Elastic Load Balancing Describe Target Groups\n        call: amazon-elastic-load-balancing.describetargetgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?Action=RegisterTargets\n      name: registertargets\n      operations:\n      - method: GET\n        name: registertargets\n\
  \        description: Amazon Elastic Load Balancing Register Targets with a Target Group\n        call: amazon-elastic-load-balancing.registertargets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?Action=DeregisterTargets\n      name: deregistertargets\n      operations:\n      - method: GET\n        name: deregistertargets\n        description: Amazon Elastic Load Balancing Deregister Targets from a Target Group\n        call: amazon-elastic-load-balancing.deregistertargets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?Action=DescribeTargetHealth\n      name: describetargethealth\n      operations:\n      - method: GET\n        name: describetargethealth\n        description: Amazon Elastic Load Balancing Describe Target Health\n        call: amazon-elastic-load-balancing.describetargethealth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?Action=CreateListener\n\
  \      name: createlistener\n      operations:\n      - method: GET\n        name: createlistener\n        description: Amazon Elastic Load Balancing Create a Listener\n        call: amazon-elastic-load-balancing.createlistener\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?Action=DescribeListeners\n      name: describelisteners\n      operations:\n      - method: GET\n        name: describelisteners\n        description: Amazon Elastic Load Balancing Describe Listeners\n        call: amazon-elastic-load-balancing.describelisteners\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?Action=CreateRule\n      name: createrule\n      operations:\n      - method: GET\n        name: createrule\n        description: Amazon Elastic Load Balancing Create a Listener Rule\n        call: amazon-elastic-load-balancing.createrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /?Action=DescribeRules\n\
  \      name: describerules\n      operations:\n      - method: GET\n        name: describerules\n        description: Amazon Elastic Load Balancing Describe Listener Rules\n        call: amazon-elastic-load-balancing.describerules\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-elastic-load-balancing-mcp\n    transport: http\n    description: MCP adapter for Amazon Elastic Load Balancing v2 API for AI agent use.\n    tools:\n    - name: createloadbalancer\n      description: Amazon Elastic Load Balancing Create a Load Balancer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.createloadbalancer\n      with:\n        Name: tools.Name\n        Subnets: tools.Subnets\n        SecurityGroups: tools.SecurityGroups\n        Scheme: tools.Scheme\n        Type: tools.Type\n        IpAddressType: tools.IpAddressType\n      inputParameters:\n\
  \      - name: Name\n        type: string\n        description: The name of the load balancer. Must be unique per region per account, can have a maximum of 32 characters.\n        required: true\n      - name: Subnets\n        type: array\n        description: The IDs of the subnets. You can specify only one subnet per Availability Zone.\n      - name: SecurityGroups\n        type: array\n        description: The IDs of the security groups for the load balancer\n      - name: Scheme\n        type: string\n        description: The scheme for the load balancer. An internet-facing load balancer routes requests from clients to targets\n          over the internet. An internal load balancer routes r\n      - name: Type\n        type: string\n        description: The type of load balancer\n      - name: IpAddressType\n        type: string\n        description: The type of IP addresses used by the subnets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeloadbalancers\n\
  \      description: Amazon Elastic Load Balancing Describe Load Balancers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.describeloadbalancers\n      with:\n        LoadBalancerArns: tools.LoadBalancerArns\n        Names: tools.Names\n        Marker: tools.Marker\n        PageSize: tools.PageSize\n      inputParameters:\n      - name: LoadBalancerArns\n        type: array\n        description: The Amazon Resource Names (ARN) of the load balancers\n      - name: Names\n        type: array\n        description: The names of the load balancers\n      - name: Marker\n        type: string\n        description: The marker for the next set of results\n      - name: PageSize\n        type: integer\n        description: The maximum number of results to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteloadbalancer\n      description: Amazon Elastic Load Balancing Delete\
  \ a Load Balancer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.deleteloadbalancer\n      with:\n        LoadBalancerArn: tools.LoadBalancerArn\n      inputParameters:\n      - name: LoadBalancerArn\n        type: string\n        description: The Amazon Resource Name (ARN) of the load balancer\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modifyloadbalancerattributes\n      description: Amazon Elastic Load Balancing Modify Load Balancer Attributes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.modifyloadbalancerattributes\n      with:\n        LoadBalancerArn: tools.LoadBalancerArn\n        Attributes.member.1.Key: tools.Attributes.member.1.Key\n        Attributes.member.1.Value: tools.Attributes.member.1.Value\n      inputParameters:\n      - name: LoadBalancerArn\n\
  \        type: string\n        description: The Amazon Resource Name (ARN) of the load balancer\n        required: true\n      - name: Attributes.member.1.Key\n        type: string\n        description: The name of the attribute\n      - name: Attributes.member.1.Value\n        type: string\n        description: The value of the attribute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtargetgroup\n      description: Amazon Elastic Load Balancing Create a Target Group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.createtargetgroup\n      with:\n        Name: tools.Name\n        Protocol: tools.Protocol\n        Port: tools.Port\n        VpcId: tools.VpcId\n        HealthCheckProtocol: tools.HealthCheckProtocol\n        HealthCheckPort: tools.HealthCheckPort\n        HealthCheckPath: tools.HealthCheckPath\n        TargetType: tools.TargetType\n      inputParameters:\n\
  \      - name: Name\n        type: string\n        description: The name of the target group. Must be unique per region per account.\n        required: true\n      - name: Protocol\n        type: string\n        description: The protocol to use for routing traffic to the targets\n      - name: Port\n        type: integer\n        description: The port on which the targets receive traffic\n      - name: VpcId\n        type: string\n        description: The identifier of the VPC for the targets\n      - name: HealthCheckProtocol\n        type: string\n        description: The protocol to use for health checks\n      - name: HealthCheckPort\n        type: string\n        description: The port to use for health checks\n      - name: HealthCheckPath\n        type: string\n        description: The destination for health checks on the targets\n      - name: TargetType\n        type: string\n        description: The type of target to register with the target group\n      outputParameters:\n  \
  \    - type: object\n        mapping: $.\n    - name: describetargetgroups\n      description: Amazon Elastic Load Balancing Describe Target Groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.describetargetgroups\n      with:\n        LoadBalancerArn: tools.LoadBalancerArn\n        TargetGroupArns: tools.TargetGroupArns\n        Names: tools.Names\n        Marker: tools.Marker\n        PageSize: tools.PageSize\n      inputParameters:\n      - name: LoadBalancerArn\n        type: string\n        description: The ARN of the load balancer\n      - name: TargetGroupArns\n        type: array\n        description: The ARNs of the target groups\n      - name: Names\n        type: array\n        description: The names of the target groups\n      - name: Marker\n        type: string\n        description: The marker for the next set of results\n      - name: PageSize\n        type: integer\n        description:\
  \ The maximum number of results to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: registertargets\n      description: Amazon Elastic Load Balancing Register Targets with a Target Group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.registertargets\n      with:\n        TargetGroupArn: tools.TargetGroupArn\n        Targets.member.1.Id: tools.Targets.member.1.Id\n        Targets.member.1.Port: tools.Targets.member.1.Port\n        Targets.member.1.AvailabilityZone: tools.Targets.member.1.AvailabilityZone\n      inputParameters:\n      - name: TargetGroupArn\n        type: string\n        description: The ARN of the target group\n        required: true\n      - name: Targets.member.1.Id\n        type: string\n        description: The ID of the target (instance ID, IP address, or Lambda ARN)\n        required: true\n      - name: Targets.member.1.Port\n        type:\
  \ integer\n        description: The port on which the target is listening\n      - name: Targets.member.1.AvailabilityZone\n        type: string\n        description: The Availability Zone where the target is located\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deregistertargets\n      description: Amazon Elastic Load Balancing Deregister Targets from a Target Group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.deregistertargets\n      with:\n        TargetGroupArn: tools.TargetGroupArn\n        Targets.member.1.Id: tools.Targets.member.1.Id\n        Targets.member.1.Port: tools.Targets.member.1.Port\n      inputParameters:\n      - name: TargetGroupArn\n        type: string\n        description: The ARN of the target group\n        required: true\n      - name: Targets.member.1.Id\n        type: string\n        description: The ID of the target\n        required:\
  \ true\n      - name: Targets.member.1.Port\n        type: integer\n        description: The port on which the target is listening\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describetargethealth\n      description: Amazon Elastic Load Balancing Describe Target Health\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.describetargethealth\n      with:\n        TargetGroupArn: tools.TargetGroupArn\n        Targets.member.1.Id: tools.Targets.member.1.Id\n        Targets.member.1.Port: tools.Targets.member.1.Port\n      inputParameters:\n      - name: TargetGroupArn\n        type: string\n        description: The ARN of the target group\n        required: true\n      - name: Targets.member.1.Id\n        type: string\n        description: The ID of the target\n      - name: Targets.member.1.Port\n        type: integer\n        description: The port on which the target is\
  \ listening\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createlistener\n      description: Amazon Elastic Load Balancing Create a Listener\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.createlistener\n      with:\n        LoadBalancerArn: tools.LoadBalancerArn\n        Protocol: tools.Protocol\n        Port: tools.Port\n        SslPolicy: tools.SslPolicy\n        DefaultActions.member.1.Type: tools.DefaultActions.member.1.Type\n        DefaultActions.member.1.TargetGroupArn: tools.DefaultActions.member.1.TargetGroupArn\n      inputParameters:\n      - name: LoadBalancerArn\n        type: string\n        description: The ARN of the load balancer\n        required: true\n      - name: Protocol\n        type: string\n        description: The protocol for connections from clients to the load balancer\n      - name: Port\n        type: integer\n        description: The\
  \ port on which the load balancer is listening\n        required: true\n      - name: SslPolicy\n        type: string\n        description: The security policy that defines which protocols and ciphers are supported\n      - name: DefaultActions.member.1.Type\n        type: string\n        description: The type of action\n        required: true\n      - name: DefaultActions.member.1.TargetGroupArn\n        type: string\n        description: The ARN of the target group for forward actions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describelisteners\n      description: Amazon Elastic Load Balancing Describe Listeners\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.describelisteners\n      with:\n        LoadBalancerArn: tools.LoadBalancerArn\n        ListenerArns: tools.ListenerArns\n        Marker: tools.Marker\n        PageSize: tools.PageSize\n      inputParameters:\n\
  \      - name: LoadBalancerArn\n        type: string\n        description: The ARN of the load balancer\n      - name: ListenerArns\n        type: array\n        description: The ARNs of the listeners\n      - name: Marker\n        type: string\n        description: The marker for the next set of results\n      - name: PageSize\n        type: integer\n        description: The maximum number of results to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createrule\n      description: Amazon Elastic Load Balancing Create a Listener Rule\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.createrule\n      with:\n        ListenerArn: tools.ListenerArn\n        Priority: tools.Priority\n        Conditions.member.1.Field: tools.Conditions.member.1.Field\n        Conditions.member.1.Values: tools.Conditions.member.1.Values\n        Actions.member.1.Type: tools.Actions.member.1.Type\n\
  \        Actions.member.1.TargetGroupArn: tools.Actions.member.1.TargetGroupArn\n      inputParameters:\n      - name: ListenerArn\n        type: string\n        description: The ARN of the listener\n        required: true\n      - name: Priority\n        type: integer\n        description: The rule priority. Must be unique within the listener.\n        required: true\n      - name: Conditions.member.1.Field\n        type: string\n        description: The name of the field (host-header, path-pattern, etc.)\n      - name: Conditions.member.1.Values\n        type: array\n        description: The condition values\n      - name: Actions.member.1.Type\n        type: string\n        description: The type of action\n        required: true\n      - name: Actions.member.1.TargetGroupArn\n        type: string\n        description: The ARN of the target group for forward actions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describerules\n      description: Amazon\
  \ Elastic Load Balancing Describe Listener Rules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-elastic-load-balancing.describerules\n      with:\n        ListenerArn: tools.ListenerArn\n        RuleArns: tools.RuleArns\n        Marker: tools.Marker\n        PageSize: tools.PageSize\n      inputParameters:\n      - name: ListenerArn\n        type: string\n        description: The ARN of the listener\n      - name: RuleArns\n        type: array\n        description: The ARNs of the rules\n      - name: Marker\n        type: string\n        descript\n\n# --- truncated at 32 KB (32 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/amazon-elastic-load-balancing/refs/heads/main/capabilities/amazon-elastic-load-balancing-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-elastic-load-balancing/refs/heads/main/capabilities/amazon-elastic-load-balancing-capability.yaml
tags:
- Amazon
- Elastic
- Load
- Balancing
- API
tools:
- description: Amazon Elastic Load Balancing Create a Load Balancer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: createloadbalancer
- description: Amazon Elastic Load Balancing Describe Load Balancers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describeloadbalancers
- description: Amazon Elastic Load Balancing Delete a Load Balancer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: deleteloadbalancer
- description: Amazon Elastic Load Balancing Modify Load Balancer Attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: modifyloadbalancerattributes
- description: Amazon Elastic Load Balancing Create a Target Group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: createtargetgroup
- description: Amazon Elastic Load Balancing Describe Target Groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describetargetgroups
- description: Amazon Elastic Load Balancing Register Targets with a Target Group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: registertargets
- description: Amazon Elastic Load Balancing Deregister Targets from a Target Group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: deregistertargets
- description: Amazon Elastic Load Balancing Describe Target Health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describetargethealth
- description: Amazon Elastic Load Balancing Create a Listener
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: createlistener
- description: Amazon Elastic Load Balancing Describe Listeners
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describelisteners
- description: Amazon Elastic Load Balancing Create a Listener Rule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: createrule
- description: Amazon Elastic Load Balancing Describe Listener Rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: describerules
---
