---
categories: []
consumed_apis: []
description: Deploy, monitor, and manage CloudHub applications across the Anypoint Platform
layout: capability
name: Application Deployment Management
operations:
- description: ''
  method: GET
  name: ''
  path: /applications
- description: ''
  method: GET
  name: ''
  path: /applications/{domain}
- description: ''
  method: GET
  name: ''
  path: /applications/{domain}/status
personas: []
provider_name: MuleSoft
provider_slug: mulesoft
search_terms:
- get the current runtime status of a cloudhub application
- list all cloudhub applications with their runtime status and configuration
- get application status
- integration
- deploy a new mule application to cloudhub
- list all deployed cloudhub applications
- enterprise
- get configuration and runtime details for a specific cloudhub application
- deploy application
- get details for a specific cloudhub application
- update application
- delete application
- api gateway
- update configuration or redeploy a cloudhub application
- api management
- check the current deployment and runtime status of a cloudhub application
- get application
- list applications
- delete and undeploy a cloudhub application permanently
slug: application-deployment-management
source_filename: application-deployment-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  name: MuleSoft CloudHub Application Deployment Management\n  description: Deploy, monitor, and manage CloudHub applications across the Anypoint Platform\n  version: 1.0.0\n\nimport:\n  - name: cloudhub\n    location: shared/cloudhub.yaml\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8113\n      namespace: mulesoft-app-rest\n      resources:\n        - path: \"/applications\"\n          name: applications\n          label: \"List Applications\"\n          description: \"List all deployed CloudHub applications\"\n          operations:\n            - method: GET\n              call: cloudhub.listApplications\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n                  items:\n                    type: object\n\n        - path: \"/applications/{domain}\"\n          name: application\n          label: \"Get Application\"\n          description: \"Get details for a specific\
  \ CloudHub application\"\n          operations:\n            - method: GET\n              call: cloudhub.getApplication\n              inputParameters:\n                - name: domain\n                  in: path\n                  type: string\n                  required: true\n                  description: \"Application domain name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: \"/applications/{domain}/status\"\n          name: applicationStatus\n          label: \"Get Application Status\"\n          description: \"Get the current runtime status of a CloudHub application\"\n          operations:\n            - method: GET\n              call: cloudhub.getApplicationStatus\n              inputParameters:\n                - name: domain\n                  in: path\n                  type: string\n                  required: true\n                  description: \"Application domain name\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      address: \"0.0.0.0\"\n      port: 9113\n      namespace: mulesoft-applications\n      description: \"MuleSoft CloudHub application deployment and lifecycle management — deploy, update, monitor, and undeploy Mule applications\"\n      tools:\n        - name: list-applications\n          description: \"List all CloudHub applications with their runtime status and configuration\"\n          hints:\n            readOnly: true\n          call: cloudhub.listApplications\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n              items:\n                type: object\n\n        - name: get-application\n          description: \"Get configuration and runtime details for a specific CloudHub application\"\n          hints:\n            readOnly: true\n          call: cloudhub.getApplication\n          inputParameters:\n            - name: domain\n              type:\
  \ string\n              required: true\n              description: \"Application domain name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-application-status\n          description: \"Check the current deployment and runtime status of a CloudHub application\"\n          hints:\n            readOnly: true\n          call: cloudhub.getApplicationStatus\n          inputParameters:\n            - name: domain\n              type: string\n              required: true\n              description: \"Application domain name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: deploy-application\n          description: \"Deploy a new Mule application to CloudHub\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: cloudhub.createApplication\n          inputParameters:\n            - name: body\n    \
  \          type: object\n              required: true\n              description: \"Application deployment configuration including domain, muleVersion, and workers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-application\n          description: \"Update configuration or redeploy a CloudHub application\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: cloudhub.updateApplication\n          inputParameters:\n            - name: domain\n              type: string\n              required: true\n              description: \"Application domain name\"\n            - name: body\n              type: object\n              required: true\n              description: \"Updated application configuration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-application\n          description: \"\
  Delete and undeploy a CloudHub application permanently\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: cloudhub.deleteApplication\n          inputParameters:\n            - name: domain\n              type: string\n              required: true\n              description: \"Application domain name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mulesoft/refs/heads/main/capabilities/application-deployment-management.yaml
tags: []
tools:
- description: List all CloudHub applications with their runtime status and configuration
  hints:
    readOnly: true
  name: list-applications
- description: Get configuration and runtime details for a specific CloudHub application
  hints:
    readOnly: true
  name: get-application
- description: Check the current deployment and runtime status of a CloudHub application
  hints:
    readOnly: true
  name: get-application-status
- description: Deploy a new Mule application to CloudHub
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-application
- description: Update configuration or redeploy a CloudHub application
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-application
- description: Delete and undeploy a CloudHub application permanently
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-application
---
