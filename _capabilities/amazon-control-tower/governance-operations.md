---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Governance Operations
operations: []
personas: []
provider_name: Amazon Control Tower
provider_slug: amazon-control-tower
search_terms:
- landing zone
- compliance
- multi-account
- aws
- controls
- governance
- security
slug: governance-operations
source_filename: governance-operations.yaml
source_heading: Capability Spec
source_yaml: "id: https://api-evangelist.github.io/amazon-control-tower/capabilities/governance-operations.yaml\nname: Cloud Governance Operations\ndescription: Workflow-oriented Naftiko capability for cloud governance and compliance operations using AWS Control Tower, covering landing zone management, control enforcement, and baseline registration across multi-account AWS environments.\nversion: 1.0.0-alpha1\nspecificationVersion: 1.0.0-alpha1\n\ntags:\n  - Governance\n  - Compliance\n  - Landing Zone\n  - Multi-Account\n  - Controls\n  - Baselines\n\nimports:\n  - url: capabilities/shared/control-tower.yaml\n    as: controlTower\n\npersonas:\n  - name: Cloud Administrator\n    description: Cloud platform administrator responsible for governing multi-account AWS environments using Control Tower\n  - name: Security Engineer\n    description: Security engineer responsible for enabling and managing compliance controls across organizational units\n  - name: Platform Engineer\n    description:\
  \ Platform engineer automating account provisioning and baseline registration\n\nworkflows:\n  - name: Landing Zone Setup\n    description: Provision a new AWS Control Tower landing zone for multi-account governance\n    steps:\n      - step: createLandingZone\n        capability: controlTower\n        description: Create the landing zone with governance manifest\n      - step: getLandingZoneOperation\n        capability: controlTower\n        description: Poll operation status until complete\n      - step: listLandingZones\n        capability: controlTower\n        description: Confirm landing zone is active\n    persona: Cloud Administrator\n\n  - name: Control Enablement\n    description: Enable compliance controls on organizational units\n    steps:\n      - step: listBaselines\n        capability: controlTower\n        description: Review available controls in the library\n      - step: enableControl\n        capability: controlTower\n        description: Enable a control on the target\
  \ OU\n      - step: getControlOperation\n        capability: controlTower\n        description: Monitor control enablement operation\n      - step: listEnabledControls\n        capability: controlTower\n        description: Verify control is enabled\n    persona: Security Engineer\n\n  - name: OU Baseline Registration\n    description: Register an organizational unit with Control Tower baselines\n    steps:\n      - step: listBaselines\n        capability: controlTower\n        description: Identify applicable baselines\n      - step: enableBaseline\n        capability: controlTower\n        description: Enable baseline on the target OU\n      - step: getBaselineOperation\n        capability: controlTower\n        description: Monitor baseline enablement operation\n      - step: listEnabledBaselines\n        capability: controlTower\n        description: Confirm OU is registered with baseline\n    persona: Platform Engineer\n\n  - name: Compliance Remediation\n    description: Remediate\
  \ a drifted control or baseline by resetting it\n    steps:\n      - step: listEnabledControls\n        capability: controlTower\n        description: Identify controls with drift\n      - step: resetEnabledControl\n        capability: controlTower\n        description: Reset the drifted control\n      - step: getControlOperation\n        capability: controlTower\n        description: Monitor reset operation\n    persona: Security Engineer\n\nrest:\n  port: 8080\n  baseURL: https://controltower.amazonaws.com\n  auth:\n    type: aws-signature-v4\n    service: controltower\n\nmcp:\n  port: 9090\n  tools:\n    - name: setup_landing_zone\n      description: Create and configure an AWS Control Tower landing zone\n      workflow: Landing Zone Setup\n    - name: enable_compliance_control\n      description: Enable a compliance control on an organizational unit\n      workflow: Control Enablement\n    - name: register_ou_baseline\n      description: Register an organizational unit with a Control\
  \ Tower baseline\n      workflow: OU Baseline Registration\n    - name: remediate_control_drift\n      description: Reset a drifted control to restore compliance\n      workflow: Compliance Remediation\n    - name: list_landing_zones\n      description: List all landing zones in the AWS environment\n      operationId: listLandingZones\n    - name: list_enabled_controls\n      description: List controls enabled on organizational units\n      operationId: listEnabledControls\n    - name: list_enabled_baselines\n      description: List baselines enabled on organizational units\n      operationId: listEnabledBaselines\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-control-tower/refs/heads/main/capabilities/governance-operations.yaml
tags: []
tools: []
---
