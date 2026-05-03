---
categories: []
consumed_apis: []
description: Workflow capability for API Developers to discover, test, and subscribe to APIs through the developer portal and management plane. Covers user registration, API discovery, product subscription, API key management, and interactive API testing.
layout: capability
name: Developer Onboarding
operations: []
personas: []
provider_name: Microsoft Azure API Management
provider_slug: microsoft-azure-api-management
search_terms:
- enterprise
- subscriptions
- ai gateway
- api discovery
- self service
- onboarding
- developer experience
- api management
- api gateway
- microsoft azure
slug: developer-onboarding
source_filename: developer-onboarding.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Developer Onboarding\n  description: >-\n    Workflow capability for API Developers to discover, test, and subscribe to\n    APIs through the developer portal and management plane. Covers user\n    registration, API discovery, product subscription, API key management,\n    and interactive API testing.\n  tags:\n    - Developer Experience\n    - API Discovery\n    - Onboarding\n    - Self Service\n    - Subscriptions\n  created: \"2026-04-21\"\n  modified: \"2026-04-21\"\ncapability:\n  consumes:\n    - type: http\n      namespace: azure-apim-dev-portal\n      baseUri: https://{service-name}.developer.azure-api.net\n      resources:\n        - name: portal\n          label: Portal Home\n          path: /\n          operations:\n            - name: DevPortal_Home\n              label: Developer Portal Home Page\n              method: GET\n        - name: apis\n          label: API Catalog\n          path: /apis/{api-id}\n          operations:\n\
  \            - name: DevPortal_ListApis\n              label: List Available APIs\n              method: GET\n            - name: DevPortal_GetApi\n              label: Get API Details\n              method: GET\n        - name: products\n          label: Products\n          path: /products\n          operations:\n            - name: DevPortal_ListProducts\n              label: List Available Products\n              method: GET\n        - name: authentication\n          label: Authentication\n          path: /signin\n          operations:\n            - name: DevPortal_SignIn\n              label: Sign In\n              method: GET\n            - name: DevPortal_SignUp\n              label: Sign Up\n              method: GET\n        - name: profile\n          label: User Profile\n          path: /profile\n          operations:\n            - name: DevPortal_Profile\n              label: User Profile And Subscriptions\n              method: GET\n    - type: http\n      namespace: azure-apim-rest\n\
  \      baseUri: https://management.azure.com\n      auth:\n        type: oauth2\n        scopes:\n          - user_impersonation\n      resources:\n        - name: user\n          label: Users\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/users/{userId}\n          operations:\n            - name: User_ListByService\n              label: List Users\n              method: GET\n            - name: User_Get\n              label: Get User\n              method: GET\n            - name: User_CreateOrUpdate\n              label: Create Or Update User\n              method: PUT\n            - name: User_Delete\n              label: Delete User\n              method: DELETE\n            - name: User_GenerateSsoUrl\n              label: Generate SSO URL\n              method: POST\n            - name: User_GetSharedAccessToken\n              label: Get Shared Access Token\n              method: POST\n \
  \       - name: group\n          label: Groups\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/groups/{groupId}\n          operations:\n            - name: Group_ListByService\n              label: List Groups\n              method: GET\n            - name: Group_Get\n              label: Get Group\n              method: GET\n            - name: Group_CreateOrUpdate\n              label: Create Or Update Group\n              method: PUT\n            - name: Group_Delete\n              label: Delete Group\n              method: DELETE\n        - name: group-user\n          label: Group Users\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/groups/{groupId}/users/{userId}\n          operations:\n            - name: GroupUser_List\n              label: List Group Users\n              method: GET\n           \
  \ - name: GroupUser_Create\n              label: Add User To Group\n              method: PUT\n            - name: GroupUser_Delete\n              label: Remove User From Group\n              method: DELETE\n        - name: subscription\n          label: Subscriptions\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/subscriptions/{sid}\n          operations:\n            - name: Subscription_List\n              label: List Subscriptions\n              method: GET\n            - name: Subscription_Get\n              label: Get Subscription\n              method: GET\n            - name: Subscription_CreateOrUpdate\n              label: Create Or Update Subscription\n              method: PUT\n            - name: Subscription_Delete\n              label: Delete Subscription\n              method: DELETE\n            - name: Subscription_ListSecrets\n              label: List Subscription Secrets\n\
  \              method: POST\n            - name: Subscription_RegeneratePrimaryKey\n              label: Regenerate Primary Key\n              method: POST\n            - name: Subscription_RegenerateSecondaryKey\n              label: Regenerate Secondary Key\n              method: POST\n        - name: product\n          label: Products\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/products/{productId}\n          operations:\n            - name: Product_ListByService\n              label: List Products\n              method: GET\n            - name: Product_Get\n              label: Get Product\n              method: GET\n        - name: product-group\n          label: Product Groups\n          path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ApiManagement/service/{serviceName}/products/{productId}/groups/{groupId}\n          operations:\n         \
  \   - name: ProductGroup_ListByProduct\n              label: List Product Groups\n              method: GET\n            - name: ProductGroup_CreateOrUpdate\n              label: Add Group To Product\n              method: PUT\n            - name: ProductGroup_Delete\n              label: Remove Group From Product\n              method: DELETE\n    - type: http\n      namespace: azure-apim-gateway\n      baseUri: https://{service-name}.azure-api.net\n      auth:\n        type: apiKey\n        in: header\n        name: Ocp-Apim-Subscription-Key\n      resources:\n        - name: proxy\n          label: API Testing\n          path: /{api-path}\n          operations:\n            - name: Gateway_ProxyGet\n              label: Test GET Request\n              method: GET\n            - name: Gateway_ProxyPost\n              label: Test POST Request\n              method: POST\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-api-management/refs/heads/main/capabilities/developer-onboarding.yaml
tags:
- Developer Experience
- API Discovery
- Onboarding
- Self Service
- Subscriptions
tools: []
---
