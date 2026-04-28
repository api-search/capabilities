---
categories:
- payroll-hr
consumed_apis:
- acadia
description: Unified workforce development workflow using Acadia's Connected Worker Platform for managing employee training, skills matrices, work instructions, and quizzes. Used by HR managers, training coordinators, and operations managers to track and improve frontline worker capabilities.
layout: capability
name: Acadia Workforce Development
operations:
- description: List all digital work instructions
  method: GET
  name: list-work-instructions
  path: /v1/work-instructions
- description: List all employees with training completion data
  method: GET
  name: list-employees
  path: /v1/employees
- description: Get skills matrix for a specific employee
  method: GET
  name: get-employee-skills
  path: /v1/employees/{id}/skills
- description: List all job roles with training requirements
  method: GET
  name: list-roles
  path: /v1/roles
personas:
- description: HR professional managing employee training records, skills matrices, and role requirements
  id: hr-manager
  name: HR Manager
- description: Professional responsible for creating and assigning work instructions and quizzes
  id: training-coordinator
  name: Training Coordinator
- description: Manager monitoring team skill gaps, compliance, and training completion rates
  id: operations-manager
  name: Operations Manager
provider_name: Acadia
provider_slug: acadia
search_terms:
- get employee skills
- digital work instructions, employee skills, quizzes, and role management
- hr manager
- hr professional managing employee training records, skills matrices, and role requirements
- connected worker
- list all digital work instructions with status and category filtering
- list employees with training completion percentages, filtered by role or department
- training management
- list quizzes
- create a new digital work instruction with title, category, and steps
- get the complete skills matrix for an employee showing required and completed skills
- list employees and their training status
- list employees
- acadia
- end-to-end employee training management from work instructions to skill validation
- training coordinator
- tracking and managing employee skills, roles, and career development
- get employee skills matrix
- workforce development
- manufacturing
- list all job roles with training requirements and completion rates
- list all employees with training completion data
- get skills matrix for a specific employee
- manage digital work instructions
- training
- list roles
- operations manager
- list all digital work instructions
- skills management
- professional responsible for creating and assigning work instructions and quizzes
- create work instruction
- list job roles and training requirements
- knowledge management
- list work instructions
- manager monitoring team skill gaps, compliance, and training completion rates
- list all active quizzes and assessments available in the platform
- list all job roles with training requirements
slug: workforce-development
tags:
- Acadia
- Workforce Development
- Connected Worker
- Training Management
tools:
- description: List all digital work instructions with status and category filtering
  hints:
    openWorld: false
    readOnly: true
  name: list-work-instructions
- description: Create a new digital work instruction with title, category, and steps
  hints:
    openWorld: false
    readOnly: false
  name: create-work-instruction
- description: List employees with training completion percentages, filtered by role or department
  hints:
    openWorld: false
    readOnly: true
  name: list-employees
- description: Get the complete skills matrix for an employee showing required and completed skills
  hints:
    openWorld: false
    readOnly: true
  name: get-employee-skills
- description: List all active quizzes and assessments available in the platform
  hints:
    openWorld: false
    readOnly: true
  name: list-quizzes
- description: List all job roles with training requirements and completion rates
  hints:
    openWorld: false
    readOnly: true
  name: list-roles
---
