---
categories:
- security
consumed_apis: []
description: Unified capability for security teams to manage access analyzers, review findings, validate policies, and enforce least-privilege access controls across AWS accounts.
layout: capability
name: Amazon IAM Access Analyzer - Access Security Management
operations:
- description: List all access analyzers in the account
  method: GET
  name: list-analyzers
  path: /v1/analyzers
- description: Create a new access analyzer
  method: POST
  name: create-analyzer
  path: /v1/analyzers
- description: List findings from an analyzer
  method: GET
  name: list-findings
  path: /v1/findings
- description: Validate an IAM policy for best practices
  method: POST
  name: validate-policy
  path: /v1/policies/validate
- description: Start generating a policy based on CloudTrail activity
  method: POST
  name: start-policy-generation
  path: /v1/policies/generate
personas: []
provider_name: Amazon IAM Access Analyzer
provider_slug: amazon-iam-access-analyzer
search_terms:
- policy management
- ensuring access controls meet security standards
- list findings from an analyzer
- validate policy
- get details of a specific access finding
- create analyzer
- preview access changes before deploying permission changes
- reviews access findings and remediates unintended access
- list findings
- list all iam access analyzers configured in the account
- Cloud Security Engineer
- creating, validating, and optimizing iam policies
- list archive rules for an analyzer
- compliance
- start policy generation
- access control
- managing who can access what resources
- validate an iam policy for best practices
- create a new iam access analyzer for an account or organization
- manage analyzers, findings, validate policies, and generate least-privilege policies
- Security Engineer
- list security findings from an access analyzer
- review access analyzer findings
- create a new access analyzer
- IAM Administrator
- iam
- create access preview
- generate an iam policy based on cloudtrail access activity logs
- list archive rules
- manage access analyzers
- get generated policy
- start generating a policy based on cloudtrail activity
- retrieve a policy generated from cloudtrail activity
- validate iam policies
- generate iam policies from activity logs
- list all access analyzers in the account
- aws
- validate an iam policy document for best practices and security issues
- list analyzers
- security
- get finding
- manages iam policies, roles, and access controls
slug: access-security-management
source_filename: access-security-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon IAM Access Analyzer - Access Security Management\n  description: Unified capability for security teams to manage access analyzers, review findings, validate policies, and enforce\n    least-privilege access controls across AWS accounts.\n  tags:\n  - AWS\n  - IAM\n  - Security\n  - Access Control\n  - Compliance\n  - Policy Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: iam-access-analyzer\n    baseUri: https://access-analyzer.amazonaws.com\n    description: AWS IAM Access Analyzer REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: AccessAnalyzer\n      path: /\n      description: AccessAnalyzer operations\n      operations:\n\
  \      - name: applyarchiverule\n        method: PUT\n        description: Amazon IAM Access Analyzer Apply Archive Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: getgeneratedpolicy\n        method: GET\n        description: Amazon IAM Access Analyzer Get Generated Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The <code>JobId</code> that is returned by the <code>StartPolicyGeneration</code> operation. The <code>JobId</code>\n            can be used with <code>GetGeneratedPolicy</code> to retrieve the generated policies or used with <code>CancelPolicyGeneration</code>\n            to cancel the policy generation\
  \ request.\n        - name: includeResourcePlaceholders\n          in: query\n          type: boolean\n          required: false\n          description: <p>The level of detail that you want to generate. You can specify whether to generate policies with\n            placeholders for resource ARNs for actions that support resource level granularity in policies.</p> <p>For example,\n            in the resource section of a policy, you can receive a placeholder such as <code>\"Resource\":\"arn:aws:s3:::${BucketName}\"</code>\n            instead of <code>\"*\"</code>.</p>\n        - name: includeServiceLevelTemplate\n          in: query\n          type: boolean\n          required: false\n          description: <p>The level of detail that you want to generate. You can specify whether to generate service-level\n            policies. </p> <p>IAM Access Analyzer uses <code>iam:servicelastaccessed</code> to identify services that have\n            been used recently to create this service-level\
  \ template.</p>\n      - name: cancelpolicygeneration\n        method: PUT\n        description: Amazon IAM Access Analyzer Cancel Policy Generation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The <code>JobId</code> that is returned by the <code>StartPolicyGeneration</code> operation. The <code>JobId</code>\n            can be used with <code>GetGeneratedPolicy</code> to retrieve the generated policies or used with <code>CancelPolicyGeneration</code>\n            to cancel the policy generation request.\n      - name: createaccesspreview\n        method: PUT\n        description: Amazon IAM Access Analyzer Create Access Preview\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data: {}\n      - name: listanalyzers\n        method: GET\n        description: Amazon IAM Access Analyzer List Analyzers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: A token used for pagination of results returned.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of results to return in the response.\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: The type of analyzer.\n      - name: createanalyzer\n        method: PUT\n        description: Amazon IAM Access Analyzer Create Analyzer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: listarchiverules\n        method: GET\n        description: Amazon IAM Access Analyzer List Archive Rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: analyzerName\n          in: path\n          type: string\n          required: true\n          description: The name of the analyzer to retrieve rules from.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: A token used for pagination of results returned.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of results to return in the request.\n      - name: createarchiverule\n        method: PUT\n        description: Amazon IAM Access Analyzer\
  \ Create Archive Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: analyzerName\n          in: path\n          type: string\n          required: true\n          description: The name of the created analyzer.\n        body:\n          type: json\n          data: {}\n      - name: getanalyzer\n        method: GET\n        description: Amazon IAM Access Analyzer Get Analyzer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: analyzerName\n          in: path\n          type: string\n          required: true\n          description: The name of the analyzer retrieved.\n      - name: deleteanalyzer\n        method: DELETE\n        description: Amazon IAM Access Analyzer Delete Analyzer\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: analyzerName\n          in: path\n          type: string\n          required: true\n          description: The name of the analyzer to delete.\n        - name: clientToken\n          in: query\n          type: string\n          required: false\n          description: A client token.\n      - name: getarchiverule\n        method: GET\n        description: Amazon IAM Access Analyzer Get Archive Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: analyzerName\n          in: path\n          type: string\n          required: true\n          description: The name of the analyzer to retrieve rules from.\n        - name: ruleName\n          in: path\n          type: string\n          required: true\n          description: The name of the rule to retrieve.\n      - name: updatearchiverule\n\
  \        method: PUT\n        description: Amazon IAM Access Analyzer Update Archive Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: analyzerName\n          in: path\n          type: string\n          required: true\n          description: The name of the analyzer to update the archive rules for.\n        - name: ruleName\n          in: path\n          type: string\n          required: true\n          description: The name of the rule to update.\n        body:\n          type: json\n          data: {}\n      - name: deletearchiverule\n        method: DELETE\n        description: Amazon IAM Access Analyzer Delete Archive Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: analyzerName\n          in: path\n          type: string\n          required:\
  \ true\n          description: The name of the analyzer that associated with the archive rule to delete.\n        - name: ruleName\n          in: path\n          type: string\n          required: true\n          description: The name of the rule to delete.\n        - name: clientToken\n          in: query\n          type: string\n          required: false\n          description: A client token.\n      - name: getaccesspreview\n        method: GET\n        description: Amazon IAM Access Analyzer Get Access Preview\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: accessPreviewId\n          in: path\n          type: string\n          required: true\n          description: The unique ID for the access preview.\n        - name: analyzerArn\n          in: query\n          type: string\n          required: true\n          description: The <a href=\"https://docs.aws.amazon.com/IAM/latest/UserGuide/access-analyzer-getting-started.html#permission-resources\"\
  >ARN\n            of the analyzer</a> used to generate the access preview.\n      - name: getanalyzedresource\n        method: GET\n        description: Amazon IAM Access Analyzer Get Analyzed Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: analyzerArn\n          in: query\n          type: string\n          required: true\n          description: The <a href=\"https://docs.aws.amazon.com/IAM/latest/UserGuide/access-analyzer-getting-started.html#permission-resources\">ARN\n            of the analyzer</a> to retrieve information from.\n        - name: resourceArn\n          in: query\n          type: string\n          required: true\n          description: The ARN of the resource to retrieve information about.\n      - name: getfinding\n        method: GET\n        description: Amazon IAM Access Analyzer Get Finding\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: analyzerArn\n          in: query\n          type: string\n          required: true\n          description: The <a href=\"https://docs.aws.amazon.com/IAM/latest/UserGuide/access-analyzer-getting-started.html#permission-resources\">ARN\n            of the analyzer</a> that generated the finding.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The ID of the finding to retrieve.\n      - name: listaccesspreviewfindings\n        method: POST\n        description: Amazon IAM Access Analyzer List Access Preview Findings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: accessPreviewId\n          in: path\n          type: string\n          required: true\n          description: The unique ID for the access\
  \ preview.\n        - name: maxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        body:\n          type: json\n          data: {}\n      - name: listaccesspreviews\n        method: GET\n        description: Amazon IAM Access Analyzer List Access Previews\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: analyzerArn\n          in: query\n          type: string\n          required: true\n          description: The <a href=\"https://docs.aws.amazon.com/IAM/latest/UserGuide/access-analyzer-getting-started.html#permission-resources\">ARN\n            of the analyzer</a> used to generate the access preview.\n        - name: nextToken\n          in: query\n  \
  \        type: string\n          required: false\n          description: A token used for pagination of results returned.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of results to return in the response.\n      - name: listanalyzedresources\n        method: POST\n        description: Amazon IAM Access Analyzer List Analyzed Resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        body:\n          type: json\n          data: {}\n      - name: listfindings\n        method: POST\n        description: Amazon\
  \ IAM Access Analyzer List Findings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: string\n          required: false\n          description: Pagination limit\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        body:\n          type: json\n          data: {}\n      - name: updatefindings\n        method: PUT\n        description: Amazon IAM Access Analyzer Update Findings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: listpolicygenerations\n        method: GET\n        description: Amazon IAM Access Analyzer List Policy Generations\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: principalArn\n          in: query\n          type: string\n          required: false\n          description: The ARN of the IAM entity (user or role) for which you are generating a policy. Use this with <code>ListGeneratedPolicies</code>\n            to filter the results to only include results for a specific principal.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of results to return in the response.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: A token used for pagination of results returned.\n      - name: startpolicygeneration\n        method: PUT\n        description: Amazon IAM Access Analyzer Start Policy Generation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: listtagsforresource\n        method: GET\n        description: Amazon IAM Access Analyzer List Tags for Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the resource to retrieve tags from.\n      - name: tagresource\n        method: POST\n        description: Amazon IAM Access Analyzer Tag Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the resource to add the tag to.\n        body:\n\
  \          type: json\n          data: {}\n      - name: startresourcescan\n        method: POST\n        description: Amazon IAM Access Analyzer Start Resource Scan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: untagresource\n        method: DELETE\n        description: Amazon IAM Access Analyzer Untag Resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The ARN of the resource to remove the tag from.\n        - name: tagKeys\n          in: query\n          type: array\n          required: true\n          description: The key for the tag to add.\n      - name: validatepolicy\n        method: POST\n        description:\
  \ Amazon IAM Access Analyzer Validate Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: The maximum number of results to return in the response.\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: A token used for pagination of results returned.\n        body:\n          type: json\n          data: {}\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: access-security-api\n    description: Unified REST API for access security management.\n    resources:\n    - path: /v1/analyzers\n      name: analyzers\n      description: Manage access analyzers\n      operations:\n      - method: GET\n        name: list-analyzers\n        description: List all access analyzers in the account\n\
  \        call: iam-access-analyzer.listanalyzers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-analyzer\n        description: Create a new access analyzer\n        call: iam-access-analyzer.createanalyzer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/findings\n      name: findings\n      description: Review access analyzer findings\n      operations:\n      - method: GET\n        name: list-findings\n        description: List findings from an analyzer\n        call: iam-access-analyzer.listfindings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies/validate\n      name: policy-validation\n      description: Validate IAM policies\n      operations:\n      - method: POST\n        name: validate-policy\n        description: Validate an IAM policy for best practices\n        call: iam-access-analyzer.validatepolicy\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/policies/generate\n      name: policy-generation\n      description: Generate IAM policies from activity logs\n      operations:\n      - method: POST\n        name: start-policy-generation\n        description: Start generating a policy based on CloudTrail activity\n        call: iam-access-analyzer.startpolicygeneration\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: access-security-mcp\n    transport: http\n    description: MCP server for AI-assisted access security management.\n    tools:\n    - name: list-analyzers\n      description: List all IAM Access Analyzers configured in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iam-access-analyzer.listanalyzers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-analyzer\n      description: Create a new IAM Access Analyzer for\
  \ an account or organization\n      hints:\n        readOnly: false\n      call: iam-access-analyzer.createanalyzer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-findings\n      description: List security findings from an access analyzer\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iam-access-analyzer.listfindings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-finding\n      description: Get details of a specific access finding\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iam-access-analyzer.getfinding\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-policy\n      description: Validate an IAM policy document for best practices and security issues\n      hints:\n        readOnly: true\n        openWorld: false\n      call: iam-access-analyzer.validatepolicy\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: start-policy-generation\n      description: Generate an IAM policy based on CloudTrail access activity logs\n      hints:\n        readOnly: false\n      call: iam-access-analyzer.startpolicygeneration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-generated-policy\n      description: Retrieve a policy generated from CloudTrail activity\n      hints:\n        readOnly: true\n        openWorld: false\n      call: iam-access-analyzer.getgeneratedpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-access-preview\n      description: Preview access changes before deploying permission changes\n      hints:\n        readOnly: false\n      call: iam-access-analyzer.createaccesspreview\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-archive-rules\n      description: List archive rules for an analyzer\n      hints:\n        readOnly: true\n       \
  \ openWorld: true\n      call: iam-access-analyzer.listarchiveruless\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iam-access-analyzer/refs/heads/main/capabilities/access-security-management.yaml
tags:
- IAM
- Security
- Access Control
- Compliance
- Policy Management
tools:
- description: List all IAM Access Analyzers configured in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-analyzers
- description: Create a new IAM Access Analyzer for an account or organization
  hints:
    readOnly: false
  name: create-analyzer
- description: List security findings from an access analyzer
  hints:
    openWorld: true
    readOnly: true
  name: list-findings
- description: Get details of a specific access finding
  hints:
    openWorld: true
    readOnly: true
  name: get-finding
- description: Validate an IAM policy document for best practices and security issues
  hints:
    openWorld: false
    readOnly: true
  name: validate-policy
- description: Generate an IAM policy based on CloudTrail access activity logs
  hints:
    readOnly: false
  name: start-policy-generation
- description: Retrieve a policy generated from CloudTrail activity
  hints:
    openWorld: false
    readOnly: true
  name: get-generated-policy
- description: Preview access changes before deploying permission changes
  hints:
    readOnly: false
  name: create-access-preview
- description: List archive rules for an analyzer
  hints:
    openWorld: true
    readOnly: true
  name: list-archive-rules
---
