---
categories: []
consumed_apis: []
description: Workflow capability for SOC analysts and security engineers to conduct end-to-end security investigations using Amazon Detective. Combines behavior graph management, member account administration, investigation lifecycle management, and indicator analysis into a unified workflow for threat hunting and security forensics.
layout: capability
name: Amazon Detective Security Investigation
operations:
- description: List all behavior graphs
  method: GET
  name: list-graphs
  path: /v1/graphs
- description: Create a new behavior graph
  method: POST
  name: create-graph
  path: /v1/graphs
- description: List member accounts contributing to the behavior graph
  method: GET
  name: list-members
  path: /v1/graphs/{graphArn}/members
- description: Invite AWS accounts to become member accounts
  method: POST
  name: create-members
  path: /v1/graphs/{graphArn}/members
- description: Remove member accounts from the behavior graph
  method: DELETE
  name: delete-members
  path: /v1/graphs/{graphArn}/members
- description: List all investigations in a behavior graph
  method: GET
  name: list-investigations
  path: /v1/investigations
- description: Start a new investigation on an IAM user or role
  method: POST
  name: start-investigation
  path: /v1/investigations
- description: Get results and status of an investigation
  method: GET
  name: get-investigation
  path: /v1/investigations/{investigationId}
- description: Archive or reactivate an investigation
  method: PUT
  name: update-investigation-state
  path: /v1/investigations/{investigationId}
- description: Get indicators of compromise from an investigation
  method: GET
  name: list-indicators
  path: /v1/investigations/{investigationId}/indicators
- description: List data source packages in the behavior graph
  method: GET
  name: list-datasource-packages
  path: /v1/datasources
personas: []
provider_name: Amazon Detective
provider_slug: amazon-detective
search_terms:
- list data source packages in the behavior graph
- security investigation
- list member accounts contributing data to a behavior graph
- soc
- archive or reactivate an investigation
- create graph
- security investigation lifecycle management
- get investigation
- list all security investigations with filtering by severity, status, and state
- get the organization behavior graph configuration including auto-enable settings
- delete members
- security operations center analyst using detective to investigate alerts and hunt threats
- create members
- invite aws accounts to contribute data to a behavior graph
- list all investigations in a behavior graph
- amazon detective
- get the results, severity, and status of a security investigation
- update datasource packages
- end-to-end security investigation using machine learning and graph analysis
- start a new investigation on an iam user or role
- invite aws accounts to become member accounts
- list members
- list all behavior graphs
- data source package management
- list organization admin accounts
- initiate a detective investigation on a suspicious iam user or role
- get indicators of compromise (ttps, flagged ips, impossible travel) from an investigation
- managing the detective behavior graph and contributing member accounts
- Security Engineer
- list graphs
- security engineer managing the detective behavior graph, member accounts, and data sources
- enable additional data source packages like eks audit logs or ad audit logs
- update investigation state
- list all amazon detective behavior graphs
- investigation
- remove member accounts from a behavior graph
- get members
- get detailed membership information for specific accounts
- end-to-end security investigation workflow for soc analysts
- describe organization configuration
- start investigation
- list indicators
- threat hunting
- list data source packages and their ingest status in a behavior graph
- get results and status of an investigation
- behavior graph management for security investigation
- forensics
- multi-account security management via aws organizations integration
- list datasource packages
- list detective administrator accounts in the organization
- aws
- indicators of compromise from an investigation
- list investigations
- archive a completed investigation or reactivate an archived one
- list member accounts contributing to the behavior graph
- create a new behavior graph
- create a new amazon detective behavior graph to begin security monitoring
- SOC Analyst
- remove member accounts from the behavior graph
- security
- get indicators of compromise from an investigation
- member account management for the behavior graph
- individual investigation management
slug: security-investigation
source_filename: security-investigation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Detective Security Investigation\n  description: Workflow capability for SOC analysts and security engineers to conduct end-to-end security investigations using\n    Amazon Detective. Combines behavior graph management, member account administration, investigation lifecycle management,\n    and indicator analysis into a unified workflow for threat hunting and security forensics.\n  tags:\n  - Amazon Detective\n  - Security Investigation\n  - Forensics\n  - Threat Hunting\n  - SOC\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_SESSION_TOKEN: AWS_SESSION_TOKEN\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: detective\n    baseUri: https://api.detective.us-east-1.amazonaws.com\n    description: Amazon Detective REST API for security investigation and\
  \ behavior graph management.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: graph\n      path: /graph\n      description: Behavior graph management\n      operations:\n      - name: create-graph\n        method: POST\n        description: Creates a new behavior graph for the calling account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: graphs-list\n      path: /graphs/list\n      description: List behavior graphs\n      operations:\n      - name: list-graphs\n        method: POST\n        description: Returns the list of behavior graphs the calling account administers\n        inputParameters:\n        - name: NextToken\n          in: body\n          type: string\n          required: false\n          description: Pagination token\n        - name: MaxResults\n          in: body\n    \
  \      type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: members\n      path: /graph/members\n      description: Member account management\n      operations:\n      - name: create-members\n        method: POST\n        description: Sends invitations to AWS accounts to become member accounts\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: Accounts\n          in: body\n          type: array\n          required: true\n          description: List of AWS accounts to invite\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: members-removal\n      path: /graph/members/removal\n      description:\
  \ Remove member accounts\n      operations:\n      - name: delete-members\n        method: POST\n        description: Removes the specified member accounts from the behavior graph\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: AccountIds\n          in: body\n          type: array\n          required: true\n          description: List of account IDs to remove\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: members-get\n      path: /graph/members/get\n      description: Get member details\n      operations:\n      - name: get-members\n        method: POST\n        description: Returns membership details for specified member accounts\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n   \
  \       description: ARN of the behavior graph\n        - name: AccountIds\n          in: body\n          type: array\n          required: true\n          description: List of account IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: members-list\n      path: /graph/members/list\n      description: List member accounts\n      operations:\n      - name: list-members\n        method: POST\n        description: Retrieves the list of member accounts for a behavior graph\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: MaxResults\n          in: body\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: monitoring-enable\n      path: /graph/members/monitoringEnable\n      description: Start monitoring a member account\n      operations:\n      - name: start-monitoring-member\n        method: POST\n        description: Starts monitoring a member account with ACCEPTED_BUT_DISABLED status\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: AccountId\n          in: body\n          type: string\n          required: true\n          description: Account ID of the member to enable\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invitation\n      path: /invitation\n      description: Manage behavior graph invitations\n      operations:\n      - name: accept-invitation\n        method: PUT\n        description: Accepts an invitation to contribute\
  \ data to a behavior graph\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invitation-removal\n      path: /invitation/removal\n      description: Reject a behavior graph invitation\n      operations:\n      - name: reject-invitation\n        method: PUT\n        description: Rejects an invitation to contribute data to a behavior graph\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invitations-list\n      path: /invitations/list\n      description: List invitations\n\
  \      operations:\n      - name: list-invitations\n        method: POST\n        description: Lists open and accepted behavior graph invitations for the member account\n        inputParameters:\n        - name: MaxResults\n          in: body\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: membership-removal\n      path: /membership/removal\n      description: Leave a behavior graph\n      operations:\n      - name: disassociate-membership\n        method: POST\n        description: Removes the member account from the specified behavior graph\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph to leave\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: datasources-list\n      path: /graph/datasources/list\n      description: List datasource packages\n      operations:\n      - name: list-datasource-packages\n        method: POST\n        description: Lists data source packages in the behavior graph\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasources-get\n      path: /graph/datasources/get\n      description: Get datasource details for behavior graph members\n      operations:\n      - name: batch-get-graph-member-datasources\n        method: POST\n        description: Gets data source package information for behavior graph members\n        inputParameters:\n        - name: GraphArn\n          in: body\n      \
  \    type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: AccountIds\n          in: body\n          type: array\n          required: true\n          description: List of account IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: membership-datasources\n      path: /membership/datasources/get\n      description: Get membership datasource history\n      operations:\n      - name: batch-get-membership-datasources\n        method: POST\n        description: Gets data source package history for an account\n        inputParameters:\n        - name: GraphArns\n          in: body\n          type: array\n          required: true\n          description: List of behavior graph ARNs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasources-update\n      path: /graph/datasources/update\n\
  \      description: Update datasource packages\n      operations:\n      - name: update-datasource-packages\n        method: POST\n        description: Starts a data source packages for the specified behavior graph\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: DatasourcePackages\n          in: body\n          type: array\n          required: true\n          description: Datasource packages to enable\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: start-investigation\n      path: /investigations/startInvestigation\n      description: Start a security investigation\n      operations:\n      - name: start-investigation\n        method: POST\n        description: Initiates a Detective investigation on an entity\n        inputParameters:\n        - name: GraphArn\n\
  \          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: EntityArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the IAM user or role to investigate\n        - name: ScopeStartTime\n          in: body\n          type: string\n          required: true\n          description: Investigation scope start time\n        - name: ScopeEndTime\n          in: body\n          type: string\n          required: true\n          description: Investigation scope end time\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-investigation\n      path: /investigations/getInvestigation\n      description: Get investigation results\n      operations:\n      - name: get-investigation\n        method: POST\n        description: Returns the investigation results of an investigation for a\
  \ behavior graph\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: InvestigationId\n          in: body\n          type: string\n          required: true\n          description: The investigation ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-investigations\n      path: /investigations/listInvestigations\n      description: List investigations\n      operations:\n      - name: list-investigations\n        method: POST\n        description: Lists investigations for a behavior graph\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: MaxResults\n          in: body\n          type: integer\n          required: false\n \
  \         description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update-investigation-state\n      path: /investigations/updateInvestigationState\n      description: Update investigation state\n      operations:\n      - name: update-investigation-state\n        method: POST\n        description: Updates the state of an investigation\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: InvestigationId\n          in: body\n          type: string\n          required: true\n          description: The investigation ID\n        - name: State\n          in: body\n          type: string\n          required: true\n          description: New state (ACTIVE or ARCHIVED)\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: list-indicators\n      path: /investigations/listIndicators\n      description: List investigation indicators\n      operations:\n      - name: list-indicators\n        method: POST\n        description: Gets the indicators of compromise from an investigation\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: InvestigationId\n          in: body\n          type: string\n          required: true\n          description: The investigation ID\n        - name: IndicatorType\n          in: body\n          type: string\n          required: false\n          description: Filter by indicator type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: org-enable-admin\n      path: /orgs/enableAdminAccount\n     \
  \ description: Enable organization admin account\n      operations:\n      - name: enable-organization-admin-account\n        method: POST\n        description: Designates the Detective administrator account for the organization\n        inputParameters:\n        - name: AccountId\n          in: body\n          type: string\n          required: true\n          description: AWS account to designate as Detective admin\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: org-disable-admin\n      path: /orgs/disableAdminAccount\n      description: Disable organization admin account\n      operations:\n      - name: disable-organization-admin-account\n        method: POST\n        description: Removes the Detective administrator account in the current Region\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: org-describe-config\n\
  \      path: /orgs/describeOrganizationConfiguration\n      description: Describe organization configuration\n      operations:\n      - name: describe-organization-configuration\n        method: POST\n        description: Returns information about the configuration for the organization behavior graph\n        inputParameters:\n        - name: GraphArn\n          in: body\n          type: string\n          required: true\n          description: ARN of the organization behavior graph\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: org-update-config\n      path: /orgs/updateOrganizationConfiguration\n      description: Update organization configuration\n      operations:\n      - name: update-organization-configuration\n        method: POST\n        description: Updates the configuration for the organization behavior graph\n        inputParameters:\n        - name: GraphArn\n          in: body\n \
  \         type: string\n          required: true\n          description: ARN of the organization behavior graph\n        - name: AutoEnable\n          in: body\n          type: boolean\n          required: false\n          description: Whether to auto-enable new org accounts as members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: org-list-admins\n      path: /orgs/listAdminAccounts\n      description: List organization admin accounts\n      operations:\n      - name: list-organization-admin-accounts\n        method: POST\n        description: Lists the Detective administrator accounts in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags/{resourceArn}\n      description: Resource tagging\n      operations:\n      - name: list-tags-for-resource\n        method: GET\n\
  \        description: Returns the tag values assigned to a behavior graph\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: tag-resource\n        method: POST\n        description: Applies tag values to a behavior graph\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: Tags\n          in: body\n          type: object\n          required: true\n          description: Tags to apply\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: untag-resource\n        method: DELETE\n        description: Removes\
  \ tags from a behavior graph\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: ARN of the behavior graph\n        - name: tagKeys\n          in: query\n          type: array\n          required: true\n          description: Tag keys to remove\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: security-investigation-api\n    description: Unified REST API for Amazon Detective security investigation workflows.\n    resources:\n    - path: /v1/graphs\n      name: graphs\n      description: Behavior graph management for security investigation\n      operations:\n      - method: GET\n        name: list-graphs\n        description: List all behavior graphs\n        call: detective.list-graphs\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: POST\n        name: create-graph\n        description: Create a new behavior graph\n        call: detective.create-graph\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/graphs/{graphArn}/members\n      name: members\n      description: Member account management for the behavior graph\n      operations:\n      - method: GET\n        name: list-members\n        description: List member accounts contributing to the behavior graph\n        call: detective.list-members\n        with:\n          GraphArn: rest.graphArn\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-members\n        description: Invite AWS accounts to become member accounts\n        call: detective.create-members\n        with:\n          GraphArn: rest.graphArn\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-members\n  \
  \      description: Remove member accounts from the behavior graph\n        call: detective.delete-members\n        with:\n          GraphArn: rest.graphArn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/investigations\n      name: investigations\n      description: Security investigation lifecycle management\n      operations:\n      - method: GET\n        name: list-investigations\n        description: List all investigations in a behavior graph\n        call: detective.list-investigations\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: start-investigation\n        description: Start a new investigation on an IAM user or role\n        call: detective.start-investigation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/investigations/{investigationId}\n      name: investigation\n      description: Individual investigation management\n   \
  \   operations:\n      - method: GET\n        name: get-investigation\n        description: Get results and status of an investigation\n        call: detective.get-investigation\n        with:\n          InvestigationId: rest.investigationId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-investigation-state\n        description: Archive or reactivate an investigation\n        call: detective.update-investigation-state\n        with:\n          InvestigationId: rest.investigationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/investigations/{investigationId}/indicators\n      name: indicators\n      description: Indicators of compromise from an investigation\n      operations:\n      - method: GET\n        name: list-indicators\n        description: Get indicators of compromise from an investigation\n        call: detective.list-indicators\n        with:\n          InvestigationId:\
  \ rest.investigationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datasources\n      name: datasources\n      description: Data source package management\n      operations:\n      - method: GET\n        name: list-datasource-packages\n        description: List data source packages in the behavior graph\n        call: detective.list-datasource-packages\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: security-investigation-mcp\n    transport: http\n    description: MCP server for AI-assisted security investigation and threat hunting with Amazon Detective.\n    tools:\n    - name: list-graphs\n      description: List all Amazon Detective behavior graphs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: detective.list-graphs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-graph\n      description: Create a\
  \ new Amazon Detective behavior graph to begin security monitoring\n      hints:\n        readOnly: false\n        destructive: false\n      call: detective.create-graph\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-members\n      description: List member accounts contributing data to a behavior graph\n      hints:\n        readOnly: true\n        openWorld: true\n      call: detective.list-members\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-members\n      description: Get detailed membership information for specific accounts\n      hints:\n        readOnly: true\n        openWorld: false\n      call: detective.get-members\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-members\n      description: Invite AWS accounts to contribute data to a behavior graph\n      hints:\n        readOnly: false\n        destructive: false\n      call: detective.create-members\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: delete-members\n      description: Remove member accounts from a behavior graph\n      hints:\n        readOnly: false\n        destructive: true\n      call: detective.delete-members\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-investigation\n      description: Initiate a Detective investigation on a suspicious IAM user or role\n      hints:\n        readOnly: false\n        destructive: false\n      call: detective.start-investigation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-investigation\n      description: Get the results, severity, and status of a security investigation\n      hints:\n        readOnly: true\n        openWorld: false\n      call: detective.get-investigation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-investigations\n      description: List all security investigations with filtering by\
  \ severity, status, and state\n      hints:\n        readOnly: true\n        openWorld: true\n      call: detective.list-investigations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-investigation-state\n      description: Archive a completed investigation or reactivate an archived one\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: detective.update-investigation-state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-indicators\n      description: Get indicators of compromise (TTPs, flagged IPs, impossible travel) from an investigation\n      hints:\n        readOnly: true\n        openWorld: true\n      call: detective.list-indicators\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-datasource-packages\n      description: List data source packages and their ingest status in a behavior graph\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: detective.list-datasource-packages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-datasource-packages\n      description: Enable additional data source packages like EKS audit logs or AD audit logs\n      hints:\n        readOnly: false\n        destructive: false\n      call: detective.update-datasource-packages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-organization-configuration\n      description: Get the organization behavior graph configuration including auto-enable settings\n      hints:\n        readOnly: true\n        openWorld: false\n      call: detective.describe-organization-configuration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-organization-admin-accounts\n      description: List Detective administrator accounts in the organization\n      hints:\n        readOnly: true\n        openWorld: true\n \
  \     call: detective.list-organization-admin-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-detective/refs/heads/main/capabilities/security-investigation.yaml
tags:
- Amazon Detective
- Security Investigation
- Forensics
- Threat Hunting
- SOC
tools:
- description: List all Amazon Detective behavior graphs
  hints:
    openWorld: true
    readOnly: true
  name: list-graphs
- description: Create a new Amazon Detective behavior graph to begin security monitoring
  hints:
    destructive: false
    readOnly: false
  name: create-graph
- description: List member accounts contributing data to a behavior graph
  hints:
    openWorld: true
    readOnly: true
  name: list-members
- description: Get detailed membership information for specific accounts
  hints:
    openWorld: false
    readOnly: true
  name: get-members
- description: Invite AWS accounts to contribute data to a behavior graph
  hints:
    destructive: false
    readOnly: false
  name: create-members
- description: Remove member accounts from a behavior graph
  hints:
    destructive: true
    readOnly: false
  name: delete-members
- description: Initiate a Detective investigation on a suspicious IAM user or role
  hints:
    destructive: false
    readOnly: false
  name: start-investigation
- description: Get the results, severity, and status of a security investigation
  hints:
    openWorld: false
    readOnly: true
  name: get-investigation
- description: List all security investigations with filtering by severity, status, and state
  hints:
    openWorld: true
    readOnly: true
  name: list-investigations
- description: Archive a completed investigation or reactivate an archived one
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-investigation-state
- description: Get indicators of compromise (TTPs, flagged IPs, impossible travel) from an investigation
  hints:
    openWorld: true
    readOnly: true
  name: list-indicators
- description: List data source packages and their ingest status in a behavior graph
  hints:
    openWorld: true
    readOnly: true
  name: list-datasource-packages
- description: Enable additional data source packages like EKS audit logs or AD audit logs
  hints:
    destructive: false
    readOnly: false
  name: update-datasource-packages
- description: Get the organization behavior graph configuration including auto-enable settings
  hints:
    openWorld: false
    readOnly: true
  name: describe-organization-configuration
- description: List Detective administrator accounts in the organization
  hints:
    openWorld: true
    readOnly: true
  name: list-organization-admin-accounts
---
