---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Absence Management Absentify
operations: []
personas: []
provider_name: Absentify
provider_slug: absentify
search_terms:
- microsoft teams
- leave management
- human resources
- hr
- absence management
slug: absence-management-absentify
source_filename: absence-management-absentify.yaml
source_heading: Capability Spec
source_yaml: "$schema: https://naftiko.com/schemas/capability/v1\n$id: https://raw.githubusercontent.com/api-evangelist/absentify/main/capabilities/absence-management-absentify.yaml\ntitle: Absence Management with Absentify\ndescription: >-\n  Workflow-oriented capability compositions for managing employee absences using the\n  Absentify API. Provides MCP tools for submitting, reviewing, and reporting on\n  leave requests.\nprovider: absentify\nversion: \"1.0\"\n\ntools:\n  - name: absentify_list_members\n    title: List Absentify Members\n    description: Retrieve all workspace members for absence tracking\n    capability: list-members\n    inputs:\n      - name: page\n        type: integer\n        description: Page number for pagination\n      - name: limit\n        type: integer\n        description: Number of members per page\n\n  - name: absentify_get_member\n    title: Get Absentify Member\n    description: Retrieve a specific member's profile and leave settings\n    capability: get-member\n\
  \    inputs:\n      - name: id\n        type: string\n        required: true\n        description: The member's unique identifier\n\n  - name: absentify_create_member\n    title: Create Absentify Member\n    description: Add a new employee to the workspace\n    capability: create-member\n    inputs:\n      - name: name\n        type: string\n        required: true\n      - name: email\n        type: string\n        required: true\n      - name: department_id\n        type: string\n      - name: employment_start\n        type: string\n        format: date\n\n  - name: absentify_list_departments\n    title: List Absentify Departments\n    description: Retrieve all organizational departments\n    capability: list-departments\n\n  - name: absentify_list_leave_types\n    title: List Absentify Leave Types\n    description: Retrieve all configured leave categories with their rules\n    capability: list-leave-types\n\n  - name: absentify_list_requests\n    title: List Absence Requests\n    description:\
  \ Retrieve leave requests with optional filtering by member, status, or date range\n    capability: list-requests\n    inputs:\n      - name: member_id\n        type: string\n        description: Filter by specific member\n      - name: status\n        type: string\n        enum: [pending, approved, declined, cancelled]\n        description: Filter by request status\n      - name: start\n        type: string\n        format: date\n        description: Filter requests starting from this date\n      - name: end\n        type: string\n        format: date\n        description: Filter requests ending on this date\n\n  - name: absentify_create_request\n    title: Create Absence Request\n    description: Submit a new leave request on behalf of a member\n    capability: create-request\n    inputs:\n      - name: member_id\n        type: string\n        required: true\n      - name: leave_type_id\n        type: string\n        required: true\n      - name: start\n        type: string\n       \
  \ format: date\n        required: true\n      - name: end\n        type: string\n        format: date\n        required: true\n      - name: reason\n        type: string\n        description: Optional reason for the leave request\n\n  - name: absentify_approve_request\n    title: Approve Absence Request\n    description: Approve a pending leave request\n    capability: update-request-status\n    inputs:\n      - name: id\n        type: string\n        required: true\n        description: The request's unique identifier\n      - name: status\n        type: string\n        enum: [approved]\n        default: approved\n\n  - name: absentify_decline_request\n    title: Decline Absence Request\n    description: Decline a pending leave request with optional reason\n    capability: update-request-status\n    inputs:\n      - name: id\n        type: string\n        required: true\n      - name: status\n        type: string\n        enum: [declined]\n        default: declined\n      - name: reason\n\
  \        type: string\n        description: Reason for declining the request\n\n  - name: absentify_list_absences_per_day\n    title: List Daily Absences\n    description: Retrieve individual absence days for a date range for reporting and payroll\n    capability: list-absences-per-day\n    inputs:\n      - name: start\n        type: string\n        format: date\n        required: true\n        description: Start date of the reporting period\n      - name: end\n        type: string\n        format: date\n        required: true\n        description: End date of the reporting period\n\n  - name: absentify_get_workspace\n    title: Get Absentify Workspace\n    description: Retrieve workspace configuration including plan, settings, and fiscal year\n    capability: get-workspace\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/absentify/refs/heads/main/capabilities/absence-management-absentify.yaml
tags: []
tools: []
---
