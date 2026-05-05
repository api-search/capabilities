---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Ranger Workflow
operations: []
personas: []
provider_name: Apache Ranger
provider_slug: apache-ranger
search_terms:
- administrator managing access control policies
- workflow for reviewing access audit logs
- authorization
- policy management
- audit logging and regulatory compliance
- security
- access control
- apache
- engineer integrating ranger with hadoop services
- access control and policy enforcement
- hadoop
- end-to-end workflow for creating and managing security policies
- officer reviewing audit logs for compliance reporting
- open source
slug: ranger-workflow
source_filename: ranger-workflow.yaml
source_heading: Capability Spec
source_yaml: "name: Apache Ranger Security Policy Workflow\ndescription: Workflow capability for managing security policies, services, and audit logs in Apache Ranger.\nversion: 1.0.0-alpha1\napis:\n  - name: Apache Ranger REST API\n    url: https://raw.githubusercontent.com/api-evangelist/apache-ranger/refs/heads/main/apis.yml\nshared:\n  - url: capabilities/shared/ranger-api.yaml\nworkflow:\n  name: ranger-workflow\n  description: Manage Ranger security policies, services, users, and audit logs.\n  steps:\n    - name: list-services\n      description: List registered Ranger services\n      api: Apache Ranger REST API\n      operation: listServices\n    - name: create-policy\n      description: Create a new security policy\n      api: Apache Ranger REST API\n      operation: createPolicy\n    - name: get-policy\n      description: Retrieve policy details\n      api: Apache Ranger REST API\n      operation: getPolicy\n    - name: audit-access\n      description: Review access audit logs\n\
  \      api: Apache Ranger REST API\n      operation: getAccessAudit\nexposes:\n  - type: rest\n    port: 6080\n    paths:\n      - /service/plugins/policies\n      - /service/plugins/policies/{id}\n      - /service/plugins/services\n      - /service/xusers/users\n      - /service/xusers/groups\n      - /service/audit/access\n  - type: mcp\n    port: 9090\n    tools:\n      - name: list-policies\n        description: List security policies\n        operation: listPolicies\n      - name: create-policy\n        description: Create a security policy\n        operation: createPolicy\n      - name: update-policy\n        description: Update a security policy\n        operation: updatePolicy\n      - name: delete-policy\n        description: Delete a security policy\n        operation: deletePolicy\n      - name: list-services\n        description: List Ranger services\n        operation: listServices\n      - name: create-service\n        description: Register a service with Ranger\n       \
  \ operation: createService\n      - name: list-users\n        description: List Ranger users\n        operation: listUsers\n      - name: get-access-audit\n        description: Get access audit logs\n        operation: getAccessAudit\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-ranger/refs/heads/main/capabilities/ranger-workflow.yaml
tags: []
tools: []
---
