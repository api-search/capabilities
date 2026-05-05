---
categories: []
consumed_apis:
- streamlit-cloud
description: Unified capability for deploying and managing Streamlit applications on Community Cloud. Designed for data scientists and ML engineers who need to programmatically deploy, configure, and manage Streamlit data apps from GitHub repositories. Covers the full lifecycle from deployment through secrets management and operational monitoring.
layout: capability
name: Streamlit App Deployment
operations:
- description: List all deployed Streamlit apps
  method: GET
  name: list-apps
  path: /v1/apps
- description: Deploy a new app from GitHub
  method: POST
  name: deploy-app
  path: /v1/apps
- description: Get app details and status
  method: GET
  name: get-app
  path: /v1/apps/{appId}
- description: Delete an app
  method: DELETE
  name: delete-app
  path: /v1/apps/{appId}
- description: Restart a deployed app
  method: POST
  name: restart-app
  path: /v1/apps/{appId}/restart
- description: Get app secret keys
  method: GET
  name: get-secrets
  path: /v1/apps/{appId}/secrets
- description: Update app secrets
  method: PUT
  name: update-secrets
  path: /v1/apps/{appId}/secrets
- description: List accessible workspaces
  method: GET
  name: list-workspaces
  path: /v1/workspaces
personas: []
provider_name: Streamlit
provider_slug: streamlit
search_terms:
- list accessible workspaces
- app secrets management
- restart a streamlit app — use after updating secrets
- get current status and details of a streamlit app
- workspace management
- app restart operation
- restart app
- cloud
- deploy a new streamlit app from a github repository
- list streamlit community cloud workspaces
- open source
- get app secret keys
- get app secrets
- web applications
- update secrets for a streamlit app in toml format
- delete an app
- get app status
- update secrets
- data science
- list all deployed streamlit apps
- list apps
- delete a deployed streamlit app permanently
- single app management
- python
- app deployment and listing
- delete app
- machine learning
- list all streamlit apps deployed in the workspace
- deploy app
- list workspaces
- deploy a new app from github
- deployment
- get app details and status
- restart a deployed app
- get secrets
- get app
- list the secret keys configured for a streamlit app (values not returned)
- update app secrets
slug: app-deployment
source_filename: app-deployment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Streamlit App Deployment\"\n  description: >-\n    Unified capability for deploying and managing Streamlit applications on\n    Community Cloud. Designed for data scientists and ML engineers who need\n    to programmatically deploy, configure, and manage Streamlit data apps\n    from GitHub repositories. Covers the full lifecycle from deployment through\n    secrets management and operational monitoring.\n  tags:\n    - Cloud\n    - Data Science\n    - Deployment\n    - Machine Learning\n    - Open Source\n    - Python\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STREAMLIT_API_TOKEN: STREAMLIT_API_TOKEN\n\ncapability:\n  consumes:\n    - import: streamlit-cloud\n      location: ./shared/cloud-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: streamlit-app-deployment-api\n      description: \"Unified REST API for Streamlit app deployment and management.\"\
  \n      resources:\n        - path: /v1/apps\n          name: apps\n          description: \"App deployment and listing\"\n          operations:\n            - method: GET\n              name: list-apps\n              description: \"List all deployed Streamlit apps\"\n              call: \"streamlit-cloud.list-apps\"\n              with:\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: deploy-app\n              description: \"Deploy a new app from GitHub\"\n              call: \"streamlit-cloud.deploy-app\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apps/{appId}\n          name: app\n          description: \"Single app management\"\n          operations:\n            - method: GET\n              name: get-app\n              description:\
  \ \"Get app details and status\"\n              call: \"streamlit-cloud.get-app\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-app\n              description: \"Delete an app\"\n              call: \"streamlit-cloud.delete-app\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apps/{appId}/restart\n          name: app-restart\n          description: \"App restart operation\"\n          operations:\n            - method: POST\n              name: restart-app\n              description: \"Restart a deployed app\"\n              call: \"streamlit-cloud.restart-app\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/apps/{appId}/secrets\n          name: app-secrets\n          description: \"App secrets management\"\n          operations:\n            - method: GET\n              name: get-secrets\n              description: \"Get app secret keys\"\n              call: \"streamlit-cloud.get-app-secrets\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-secrets\n              description: \"Update app secrets\"\n              call: \"streamlit-cloud.update-app-secrets\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces\n          name: workspaces\n          description: \"Workspace management\"\n          operations:\n            - method: GET\n\
  \              name: list-workspaces\n              description: \"List accessible workspaces\"\n              call: \"streamlit-cloud.list-workspaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: streamlit-app-deployment-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Streamlit app deployment and management.\"\n      tools:\n        - name: list-apps\n          description: \"List all Streamlit apps deployed in the workspace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"streamlit-cloud.list-apps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deploy-app\n          description: \"Deploy a new Streamlit app from a GitHub repository\"\n          hints:\n            readOnly: false\n          call: \"streamlit-cloud.deploy-app\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-app-status\n          description: \"Get current status and details of a Streamlit app\"\n          hints:\n            readOnly: true\n          call: \"streamlit-cloud.get-app\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: restart-app\n          description: \"Restart a Streamlit app — use after updating secrets\"\n          hints:\n            readOnly: false\n          call: \"streamlit-cloud.restart-app\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-app-secrets\n          description: \"List the secret keys configured for a Streamlit app (values not returned)\"\n          hints:\n            readOnly: true\n          call: \"streamlit-cloud.get-app-secrets\"\n          with:\n\
  \            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-app-secrets\n          description: \"Update secrets for a Streamlit app in TOML format\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"streamlit-cloud.update-app-secrets\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-app\n          description: \"Delete a deployed Streamlit app permanently\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"streamlit-cloud.delete-app\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workspaces\n          description: \"List Streamlit Community Cloud workspaces\"\
  \n          hints:\n            readOnly: true\n          call: \"streamlit-cloud.list-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/streamlit/refs/heads/main/capabilities/app-deployment.yaml
tags:
- Cloud
- Data Science
- Deployment
- Machine Learning
- Open Source
- Python
tools:
- description: List all Streamlit apps deployed in the workspace
  hints:
    openWorld: true
    readOnly: true
  name: list-apps
- description: Deploy a new Streamlit app from a GitHub repository
  hints:
    readOnly: false
  name: deploy-app
- description: Get current status and details of a Streamlit app
  hints:
    readOnly: true
  name: get-app-status
- description: Restart a Streamlit app — use after updating secrets
  hints:
    readOnly: false
  name: restart-app
- description: List the secret keys configured for a Streamlit app (values not returned)
  hints:
    readOnly: true
  name: get-app-secrets
- description: Update secrets for a Streamlit app in TOML format
  hints:
    idempotent: true
    readOnly: false
  name: update-app-secrets
- description: Delete a deployed Streamlit app permanently
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-app
- description: List Streamlit Community Cloud workspaces
  hints:
    readOnly: true
  name: list-workspaces
---
