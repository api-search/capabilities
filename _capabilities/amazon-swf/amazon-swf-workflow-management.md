---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Amazon Swf Workflow Management
operations: []
personas: []
provider_name: Amazon Simple Workflow Service
provider_slug: amazon-swf
search_terms:
- workflow
- task coordination
- automation
- aws
slug: amazon-swf-workflow-management
source_filename: amazon-swf-workflow-management.yaml
source_heading: Capability Spec
source_yaml: "id: amazon-swf-workflow-management\nname: Amazon SWF Workflow Management\ndescription: Manage workflow types, executions, and monitor workflow history in Amazon SWF.\ntags:\n- AWS\n- Workflow\n- Automation\nconsumes:\n- ref: capabilities/shared/amazon-swf-shared.yaml\n  operations:\n  - RegisterWorkflowType\n  - StartWorkflowExecution\n  - ListOpenWorkflowExecutions\n  - GetWorkflowExecutionHistory\n  - TerminateWorkflowExecution\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-swf/refs/heads/main/capabilities/amazon-swf-workflow-management.yaml
tags: []
tools: []
---
