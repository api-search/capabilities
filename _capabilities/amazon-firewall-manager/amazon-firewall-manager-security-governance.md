---
categories:
- security
consumed_apis: []
description: Centrally manage WAF, Shield, Network Firewall, and security group policies across AWS accounts.
layout: capability
name: Amazon Firewall Manager Security Governance
operations: []
personas: []
provider_name: Amazon Firewall Manager
provider_slug: amazon-firewall-manager
search_terms:
- security
- multi-account
- compliance
- network security
- aws organizations
- firewall
slug: amazon-firewall-manager-security-governance
source_filename: amazon-firewall-manager-security-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Firewall Manager Security Governance\n  description: Centrally manage WAF, Shield, Network Firewall, and security group policies across AWS accounts.\n  tags:\n  - Security\n  - Firewall\n  - Compliance\n  - Multi-Account\n  - AWS Organizations\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - namespace: fms\n    ref: capabilities/shared/firewall-manager.yaml\n  exposes:\n  - type: rest\n    port: 8080\n  - type: mcp\n    port: 9090\n  tools:\n  - name: listPolicies\n    description: List all Firewall Manager policies\n    inputSchema:\n      type: object\n      properties:\n        maxResults:\n          type: integer\n        nextToken:\n          type: string\n  - name: putPolicy\n    description: Create or update a Firewall Manager policy\n    inputSchema:\n      type: object\n      properties:\n\
  \        Policy:\n          type: object\n        TagList:\n          type: array\n      required:\n      - Policy\n  - name: getPolicy\n    description: Get details for a Firewall Manager policy\n    inputSchema:\n      type: object\n      properties:\n        policyId:\n          type: string\n      required:\n      - policyId\n  - name: deletePolicy\n    description: Delete a Firewall Manager policy\n    inputSchema:\n      type: object\n      properties:\n        policyId:\n          type: string\n        deleteAllPolicyResources:\n          type: boolean\n      required:\n      - policyId\n  - name: getComplianceDetail\n    description: Get compliance detail for a member account\n    inputSchema:\n      type: object\n      properties:\n        policyId:\n          type: string\n        memberAccountId:\n          type: string\n      required:\n      - policyId\n      - memberAccountId\n  - name: getAdminAccount\n    description: Get the Firewall Manager administrator account\n   \
  \ inputSchema:\n      type: object\n      properties: {}\n  - name: associateAdminAccount\n    description: Associate an account as Firewall Manager administrator\n    inputSchema:\n      type: object\n      properties:\n        AdminAccount:\n          type: string\n      required:\n      - AdminAccount\n  - name: disassociateAdminAccount\n    description: Disassociate the Firewall Manager administrator account\n    inputSchema:\n      type: object\n      properties: {}\n  - name: listMemberAccounts\n    description: List all member accounts in the organization\n    inputSchema:\n      type: object\n      properties:\n        nextToken:\n          type: string\n        maxResults:\n          type: integer\n  - name: putResourceSet\n    description: Create or update a resource set\n    inputSchema:\n      type: object\n      properties:\n        ResourceSet:\n          type: object\n      required:\n      - ResourceSet\n  - name: listResourceSets\n    description: List all resource sets\n\
  \    inputSchema:\n      type: object\n      properties:\n        NextToken:\n          type: string\n        MaxResults:\n          type: integer\n  - name: listTagsForResource\n    description: List tags for a Firewall Manager resource\n    inputSchema:\n      type: object\n      properties:\n        resourceArn:\n          type: string\n      required:\n      - resourceArn\n  - name: tagResource\n    description: Add tags to a Firewall Manager resource\n    inputSchema:\n      type: object\n      properties:\n        resourceArn:\n          type: string\n        TagList:\n          type: array\n      required:\n      - resourceArn\n      - TagList\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-firewall-manager/refs/heads/main/capabilities/amazon-firewall-manager-security-governance.yaml
tags:
- Security
- Firewall
- Compliance
- Multi-Account
- AWS Organizations
tools: []
---
