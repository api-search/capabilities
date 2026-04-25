---
consumed_apis:
- amazon-guardduty
description: Workflow capability for security teams using Amazon GuardDuty for AWS threat detection and response. Covers finding management, detector configuration, threat intelligence integration, and automated response workflows.
layout: capability
name: Amazon GuardDuty Threat Detection
operations:
- description: List all GuardDuty detectors
  method: GET
  name: list-detectors
  path: /v1/detectors
- description: Enable GuardDuty for an account
  method: POST
  name: create-detector
  path: /v1/detectors
- description: List threat findings
  method: GET
  name: list-findings
  path: /v1/findings
- description: Archive reviewed findings
  method: POST
  name: archive-findings
  path: /v1/findings
- description: Create a finding filter
  method: POST
  name: create-filter
  path: /v1/filters
- description: List threat intelligence sets
  method: GET
  name: list-threat-intel-sets
  path: /v1/threat-intel
personas: []
provider_name: Amazon GuardDuty
provider_slug: amazon-guardduty
search_terms:
- list threat intelligence sets used for enhanced detection
- get the configuration and status of a guardduty detector
- list all active guardduty detectors across the account
- get finding statistics and severity counts for security posture overview
- amazon guardduty
- enable guardduty for an account
- create detector
- create a trusted ip set to exclude known safe ips from alerts
- threat findings from guardduty analysis
- anomaly detection
- guardduty detector management
- list threat findings
- list trusted ip sets
- create a suppression filter to reduce noise from benign findings
- monitoring
- list finding filters
- archive threat findings that have been reviewed and resolved
- list active threat findings detected by guardduty with severity filters
- create a finding filter
- list all guardduty detectors
- list threat intel sets
- get findings statistics
- Cloud Security Engineer
- security operations
- compliance
- archive reviewed findings
- machine learning
- list trusted ip address sets excluded from threat detection
- list findings
- security
- threat detection
- threat intelligence feeds
- list threat intelligence sets
- list detectors
- configures guardduty detectors and threat intelligence feeds
- archive findings
- incident response
- get detailed information about specific threat findings including full context
- create filter
- Security Analyst
- get detector status
- SOC Engineer
- list all finding suppression filters
- investigates and responds to threat findings from guardduty
- get finding details
- list member accounts monitored by this guardduty administrator account
- list members
- aws
- monitors security alerts and manages threat response workflows
- create trusted ip set
- create finding filter
- finding suppression filters
slug: amazon-guardduty-threat-detection
tags:
- Amazon GuardDuty
- Threat Detection
- Security Operations
- Incident Response
- AWS
tools:
- description: List all active GuardDuty detectors across the account
  hints:
    openWorld: true
    readOnly: true
  name: list-detectors
- description: Get the configuration and status of a GuardDuty detector
  hints:
    readOnly: true
  name: get-detector-status
- description: List active threat findings detected by GuardDuty with severity filters
  hints:
    readOnly: true
  name: list-threat-findings
- description: Get detailed information about specific threat findings including full context
  hints:
    readOnly: true
  name: get-finding-details
- description: Archive threat findings that have been reviewed and resolved
  hints:
    readOnly: false
  name: archive-findings
- description: Create a suppression filter to reduce noise from benign findings
  hints:
    readOnly: false
  name: create-finding-filter
- description: List all finding suppression filters
  hints:
    readOnly: true
  name: list-finding-filters
- description: List trusted IP address sets excluded from threat detection
  hints:
    readOnly: true
  name: list-trusted-ip-sets
- description: Create a trusted IP set to exclude known safe IPs from alerts
  hints:
    readOnly: false
  name: create-trusted-ip-set
- description: List threat intelligence sets used for enhanced detection
  hints:
    readOnly: true
  name: list-threat-intel-sets
- description: Get finding statistics and severity counts for security posture overview
  hints:
    readOnly: true
  name: get-findings-statistics
- description: List member accounts monitored by this GuardDuty administrator account
  hints:
    readOnly: true
  name: list-members
---
