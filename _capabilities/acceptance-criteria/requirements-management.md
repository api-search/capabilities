---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Requirements Management
operations: []
personas: []
provider_name: Acceptance Criteria
provider_slug: acceptance-criteria
search_terms:
- user stories
- quality assurance
- testing
- gherkin
- requirements
- behavior driven development
- agile
slug: requirements-management
source_filename: requirements-management.yaml
source_heading: Capability Spec
source_yaml: "apiVersion: naftiko.io/v1alpha1\nkind: WorkflowCapability\nmetadata:\n  name: requirements-management\n  version: 1.0.0\n  description: End-to-end requirements management workflow for defining acceptance criteria, automating BDD scenario generation, and validating stories through acceptance test execution\n  provider: Reference Implementation\n  tags:\n    - Acceptance Criteria\n    - Requirements\n    - BDD\n    - Agile\n    - Quality Assurance\nspec:\n  sharedCapabilities:\n    - acceptance-criteria-management\n  workflow:\n    name: Story to Verified Feature Workflow\n    description: Complete lifecycle from user story creation through acceptance criteria definition, BDD scenario authoring, test execution, and story sign-off\n    steps:\n      - id: create-story\n        name: Create User Story\n        description: Create a new user story with a title, description, and priority\n        operation: createUserStory\n      - id: define-criteria\n        name: Define Acceptance\
  \ Criteria\n        description: Add measurable acceptance criteria to the user story in Gherkin or plain-text format\n        operation: addAcceptanceCriterion\n        dependsOn: [create-story]\n      - id: create-scenarios\n        name: Create BDD Scenarios\n        description: Author Gherkin feature file scenarios linked to each acceptance criterion\n        operation: createScenario\n        dependsOn: [define-criteria]\n      - id: run-tests\n        name: Execute Acceptance Tests\n        description: Trigger a test run to execute all scenarios for the user story\n        operation: createTestRun\n        dependsOn: [create-scenarios]\n      - id: verify-results\n        name: Verify Test Results\n        description: Review test run results and update acceptance criterion status based on pass/fail\n        operation: listTestRuns\n        dependsOn: [run-tests]\n      - id: update-story\n        name: Update Story Status\n        description: Mark story as ready-for-review or\
  \ done based on acceptance criteria verification\n        operation: updateUserStory\n        dependsOn: [verify-results]\n  mcpTools:\n    - name: create_user_story\n      description: Create a new user story with title, description, priority, and story points\n      capability: acceptance-criteria-management\n      operation: createUserStory\n    - name: add_acceptance_criterion\n      description: Add a Gherkin or plain-text acceptance criterion to a user story\n      capability: acceptance-criteria-management\n      operation: addAcceptanceCriterion\n    - name: list_acceptance_criteria\n      description: Retrieve all acceptance criteria for a user story with their verification status\n      capability: acceptance-criteria-management\n      operation: listAcceptanceCriteria\n    - name: create_bdd_scenario\n      description: Create a Gherkin BDD scenario linked to an acceptance criterion for automated testing\n      capability: acceptance-criteria-management\n      operation: createScenario\n\
  \    - name: run_acceptance_tests\n      description: Trigger an acceptance test run for specified user stories or scenarios\n      capability: acceptance-criteria-management\n      operation: createTestRun\n    - name: get_test_results\n      description: Retrieve acceptance test run results with pass/fail counts and report URL\n      capability: acceptance-criteria-management\n      operation: listTestRuns\n    - name: get_user_story\n      description: Get a user story with all its acceptance criteria and current status\n      capability: acceptance-criteria-management\n      operation: getUserStory\n  ports:\n    http: 8080\n    grpc: 9090\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/acceptance-criteria/refs/heads/main/capabilities/requirements-management.yaml
tags: []
tools: []
---
