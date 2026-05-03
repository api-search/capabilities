---
categories: []
consumed_apis: []
description: Workflow capability for AI Engineers to manage AI backends and LLM deployments through Azure API Management. Covers proxying chat completions, completions, and embeddings to Azure OpenAI and compatible backends with token rate limiting, semantic caching, load balancing, and MCP server integration.
layout: capability
name: AI Gateway Management
operations: []
personas: []
provider_name: Microsoft Azure API Management
provider_slug: microsoft-azure-api-management
search_terms:
- enterprise
- ai gateway
- machine learning
- llm operations
- api gateway
- token management
- api management
- mcp
- microsoft azure
- azure openai
slug: ai-gateway-management
source_filename: ai-gateway-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: AI Gateway Management\n  description: >-\n    Workflow capability for AI Engineers to manage AI backends and LLM deployments\n    through Azure API Management. Covers proxying chat completions, completions,\n    and embeddings to Azure OpenAI and compatible backends with token rate\n    limiting, semantic caching, load balancing, and MCP server integration.\n  tags:\n    - AI Gateway\n    - LLM Operations\n    - Azure OpenAI\n    - Machine Learning\n    - Token Management\n    - MCP\n  created: \"2026-04-21\"\n  modified: \"2026-04-21\"\ncapability:\n  consumes:\n    - type: http\n      namespace: azure-apim-ai-gateway\n      baseUri: https://{service-name}.azure-api.net\n      auth:\n        type: apiKey\n        in: header\n        name: api-key\n      resources:\n        - name: chat-completions\n          label: Chat Completions\n          path: /deployments/{deployment-id}/chat/completions\n          operations:\n            -\
  \ name: AIGateway_ChatCompletions\n              label: Chat Completions Via AI Gateway\n              method: POST\n        - name: completions\n          label: Completions\n          path: /deployments/{deployment-id}/completions\n          operations:\n            - name: AIGateway_Completions\n              label: Completions Via AI Gateway\n              method: POST\n        - name: embeddings\n          label: Embeddings\n          path: /deployments/{deployment-id}/embeddings\n          operations:\n            - name: AIGateway_Embeddings\n              label: Embeddings Via AI Gateway\n              method: POST\n        - name: mcp\n          label: MCP Server\n          path: /mcp\n          operations:\n            - name: AIGateway_MCP\n              label: MCP Server Request Via AI Gateway\n              method: POST\n    - type: http\n      namespace: azure-apim-rest\n      baseUri: https://management.azure.com\n      auth:\n        type: oauth2\n        scopes:\n    \
  \      - user_impersonation\n      resources:\n        - name: backend\n          label: AI Backends\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/backends/{backendId}\n          operations:\n            - name: Backend_ListByService\n              label: List Backends\n              method: GET\n            - name: Backend_Get\n              label: Get Backend\n              method: GET\n            - name: Backend_CreateOrUpdate\n              label: Create Or Update Backend\n              method: PUT\n            - name: Backend_Update\n              label: Update Backend\n              method: PATCH\n            - name: Backend_Delete\n              label: Delete Backend\n              method: DELETE\n            - name: Backend_Reconnect\n              label: Reconnect Backend\n              method: POST\n        - name: api\n          label: AI APIs\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/apis/{apiId}\n\
  \          operations:\n            - name: Api_ListByService\n              label: List APIs\n              method: GET\n            - name: Api_Get\n              label: Get API\n              method: GET\n            - name: Api_CreateOrUpdate\n              label: Create Or Update API\n              method: PUT\n            - name: Api_Delete\n              label: Delete API\n              method: DELETE\n        - name: api-policy\n          label: AI API Policies\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/apis/{apiId}/policies/{policyId}\n          operations:\n            - name: ApiPolicy_ListByApi\n              label: List API Policies\n              method: GET\n            - name: ApiPolicy_Get\n              label: Get API Policy\n              method: GET\n            - name: ApiPolicy_CreateOrUpdate\n              label: Create Or Update API Policy\n              method: PUT\n\
  \            - name: ApiPolicy_Delete\n              label: Delete API Policy\n              method: DELETE\n        - name: api-diagnostic\n          label: AI API Diagnostics\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/apis/{apiId}/diagnostics/{diagnosticId}\n          operations:\n            - name: ApiDiagnostic_ListByService\n              label: List API Diagnostics\n              method: GET\n            - name: ApiDiagnostic_Get\n              label: Get API Diagnostic\n              method: GET\n            - name: ApiDiagnostic_CreateOrUpdate\n              label: Create Or Update API Diagnostic\n              method: PUT\n            - name: ApiDiagnostic_Delete\n              label: Delete API Diagnostic\n              method: DELETE\n        - name: logger\n          label: AI Logging\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/loggers/{loggerId}\n\
  \          operations:\n            - name: Logger_ListByService\n              label: List Loggers\n              method: GET\n            - name: Logger_Get\n              label: Get Logger\n              method: GET\n            - name: Logger_CreateOrUpdate\n              label: Create Or Update Logger\n              method: PUT\n            - name: Logger_Delete\n              label: Delete Logger\n              method: DELETE\n        - name: product\n          label: AI Products\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/products/{productId}\n          operations:\n            - name: Product_ListByService\n              label: List Products\n              method: GET\n            - name: Product_CreateOrUpdate\n              label: Create Or Update Product\n              method: PUT\n        - name: subscription\n          label: AI Subscriptions\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/subscriptions/{sid}\n\
  \          operations:\n            - name: Subscription_List\n              label: List Subscriptions\n              method: GET\n            - name: Subscription_CreateOrUpdate\n              label: Create Or Update Subscription\n              method: PUT\n            - name: Subscription_ListSecrets\n              label: List Subscription Secrets\n              method: POST\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-api-management/refs/heads/main/capabilities/ai-gateway-management.yaml
tags:
- AI Gateway
- LLM Operations
- Azure OpenAI
- Machine Learning
- Token Management
- MCP
tools: []
---
