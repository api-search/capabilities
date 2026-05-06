---
categories: []
consumed_apis: []
description: 'This document specifies a **RESTful API** for WSO2 **API Manager** - **Admin Portal**. Please see [full OpenAPI Specification](https://raw.githubusercontent.com/wso2/carbon-apimgt/master/components/apimgt/org.wso2.carbon.apimgt.rest.api.admin.v1/src/main/resources/admin-api.yaml) of the API which is written using [OAS 3.0](http://swagger.io/) specification. # Authentication The Admin REST API is protected using OAuth2 and access control is achieved through scopes. Before you start invoking the the API you need to obtain an access token with the required scopes. This guide will walk you through'
layout: capability
name: WSO2 API Manager - Admin
operations:
- description: Retrieve/Search Throttling Policies
  method: GET
  name: throttlingpolicysearch
  path: /throttling/policies/search
- description: Get all Application Throttling Policies
  method: GET
  name: get-throttling-policies-application
  path: /throttling/policies/application
- description: Add an Application Throttling Policy
  method: POST
  name: post-throttling-policies-application
  path: /throttling/policies/application
- description: Get an Application Throttling Policy
  method: GET
  name: get-throttling-policies-application-policyid
  path: /throttling/policies/application/{policyId}
- description: Update an Application Throttling policy
  method: PUT
  name: put-throttling-policies-application-policyid
  path: /throttling/policies/application/{policyId}
- description: Delete an Application Throttling policy
  method: DELETE
  name: delete-throttling-policies-application-policyid
  path: /throttling/policies/application/{policyId}
- description: Get all Subscription Throttling Policies
  method: GET
  name: get-throttling-policies-subscription
  path: /throttling/policies/subscription
- description: Add a Subscription Throttling Policy
  method: POST
  name: post-throttling-policies-subscription
  path: /throttling/policies/subscription
- description: Get a Subscription Policy
  method: GET
  name: get-throttling-policies-subscription-policyid
  path: /throttling/policies/subscription/{policyId}
- description: Update a Subscription Policy
  method: PUT
  name: put-throttling-policies-subscription-policyid
  path: /throttling/policies/subscription/{policyId}
- description: Delete a Subscription Policy
  method: DELETE
  name: delete-throttling-policies-subscription-policyid
  path: /throttling/policies/subscription/{policyId}
- description: Get all Custom Rules
  method: GET
  name: get-throttling-policies-custom
  path: /throttling/policies/custom
- description: Add a Custom Rule
  method: POST
  name: post-throttling-policies-custom
  path: /throttling/policies/custom
- description: Get a Custom Rule
  method: GET
  name: get-throttling-policies-custom-ruleid
  path: /throttling/policies/custom/{ruleId}
- description: Update a Custom Rule
  method: PUT
  name: put-throttling-policies-custom-ruleid
  path: /throttling/policies/custom/{ruleId}
- description: Delete a Custom Rule
  method: DELETE
  name: delete-throttling-policies-custom-ruleid
  path: /throttling/policies/custom/{ruleId}
- description: Get all Advanced Throttling Policies
  method: GET
  name: get-throttling-policies-advanced
  path: /throttling/policies/advanced
- description: Add an Advanced Throttling Policy
  method: POST
  name: post-throttling-policies-advanced
  path: /throttling/policies/advanced
- description: Get an Advanced Throttling Policy
  method: GET
  name: get-throttling-policies-advanced-policyid
  path: /throttling/policies/advanced/{policyId}
- description: Update an Advanced Throttling Policy
  method: PUT
  name: put-throttling-policies-advanced-policyid
  path: /throttling/policies/advanced/{policyId}
- description: Delete an Advanced Throttling Policy
  method: DELETE
  name: delete-throttling-policies-advanced-policyid
  path: /throttling/policies/advanced/{policyId}
- description: Export a Throttling Policy
  method: GET
  name: exportthrottlingpolicy
  path: /throttling/policies/export
- description: Import a Throttling Policy
  method: POST
  name: importthrottlingpolicy
  path: /throttling/policies/import
- description: Get all Deny Policies
  method: GET
  name: get-throttling-deny-policies
  path: /throttling/deny-policies
- description: Add a deny policy
  method: POST
  name: post-throttling-deny-policies
  path: /throttling/deny-policies
- description: Get a Deny Policy
  method: GET
  name: get-throttling-deny-policy-conditionid
  path: /throttling/deny-policy/{conditionId}
- description: Delete a Deny Policy
  method: DELETE
  name: delete-throttling-deny-policy-conditionid
  path: /throttling/deny-policy/{conditionId}
- description: Update a Deny Policy
  method: PATCH
  name: patch-throttling-deny-policy-conditionid
  path: /throttling/deny-policy/{conditionId}
- description: Retrieve/Search Applications
  method: GET
  name: get-applications
  path: /applications
- description: Get the details of an Application
  method: GET
  name: get-applications-applicationid
  path: /applications/{applicationId}
- description: Delete an Application
  method: DELETE
  name: delete-applications-applicationid
  path: /applications/{applicationId}
- description: Update Application Settings
  method: POST
  name: updateapplicationsettings
  path: /applications/{applicationId}/change-settings
- description: Change Application Owner
  method: POST
  name: post-applications-applicationid-change-owner
  path: /applications/{applicationId}/change-owner
- description: Get all AI Service providers
  method: GET
  name: getaiserviceproviders
  path: /ai-service-providers
- description: Add a AI Service provider
  method: POST
  name: addaiserviceprovider
  path: /ai-service-providers
- description: Update an AI Service provider
  method: PUT
  name: updateaiserviceprovider
  path: /ai-service-providers/{aiServiceProviderId}
- description: Delete a AI Service Provider
  method: DELETE
  name: deleteaiserviceprovider
  path: /ai-service-providers/{aiServiceProviderId}
- description: Get AI Service Provider
  method: GET
  name: getaiserviceprovider
  path: /ai-service-providers/{aiServiceProviderId}
- description: Get all LLM providers
  method: GET
  name: getllmproviders
  path: /llm-providers
- description: Add a LLM provider
  method: POST
  name: addllmprovider
  path: /llm-providers
- description: Update an LLM provider
  method: PUT
  name: updatellmprovider
  path: /llm-providers/{llmProviderId}
- description: Delete a LLM Provider
  method: DELETE
  name: deletellmprovider
  path: /llm-providers/{llmProviderId}
- description: Get LLM Provider
  method: GET
  name: getllmprovider
  path: /llm-providers/{llmProviderId}
- description: Get all registered Environments
  method: GET
  name: get-environments
  path: /environments
- description: Add an Environment
  method: POST
  name: post-environments
  path: /environments
- description: Get a Gateway Environment Configuration
  method: GET
  name: get-environments-environmentid
  path: /environments/{environmentId}
- description: Update an Environment
  method: PUT
  name: put-environments-environmentid
  path: /environments/{environmentId}
- description: Delete an Environment
  method: DELETE
  name: delete-environments-environmentid
  path: /environments/{environmentId}
- description: Get Gateway Instances in a Gateway Environment
  method: GET
  name: get-environments-environmentid-gateways
  path: /environments/{environmentId}/gateways
- description: Get all platform gateways
  method: GET
  name: getplatformgateways
  path: /gateways
- description: Register a platform gateway
  method: POST
  name: createplatformgateway
  path: /gateways
- description: Regenerate registration token for a platform gateway
  method: POST
  name: regenerateplatformgatewaytoken
  path: /gateways/{gatewayId}/regenerate-token
- description: Update a platform gateway
  method: PUT
  name: updateplatformgateway
  path: /gateways/{gatewayId}
- description: Delete a platform gateway
  method: DELETE
  name: deleteplatformgateway
  path: /gateways/{gatewayId}
- description: Get all registered Organizations
  method: GET
  name: get-organizations
  path: /organizations
- description: Add an Organizations
  method: POST
  name: post-organizations
  path: /organizations
- description: Get an Organization
  method: GET
  name: get-organizations-organizationid
  path: /organizations/{organizationId}
- description: Update an Organization
  method: PUT
  name: put-organizations-organizationid
  path: /organizations/{organizationId}
- description: Delete an Organization
  method: DELETE
  name: delete-organizations-organizationid
  path: /organizations/{organizationId}
- description: Get the Organization information of the user
  method: GET
  name: organizationinformation
  path: /me/organization-information
personas: []
provider_name: WSO2
provider_slug: wso2
search_terms:
- get throttling policies advanced
- add a llm provider
- post organizations
- delete a subscription policy
- post throttling policies application
- get gateway instances in a gateway environment
- get all platform gateways
- createplatformgateway
- get throttling deny policy conditionid
- api
- updatellmprovider
- patch throttling deny policy conditionid
- delete throttling deny policy conditionid
- retrieve/search applications
- delete an application throttling policy
- get an organization
- api management
- get throttling policies application
- get all advanced throttling policies
- get an application throttling policy
- delete organizations organizationid
- get the organization information of the user
- get ai service provider
- get all registered organizations
- throttlingpolicysearch
- get all registered environments
- get environments environmentid gateways
- organizationinformation
- delete an environment
- put throttling policies custom ruleid
- post throttling policies advanced
- post throttling deny policies
- get environments environmentid
- add a subscription throttling policy
- add a custom rule
- delete an advanced throttling policy
- importthrottlingpolicy
- get throttling policies custom ruleid
- get throttling policies application policyid
- getllmprovider
- update an organization
- put throttling policies subscription policyid
- delete a llm provider
- api lifecycle
- update a platform gateway
- add a deny policy
- open source
- delete an application
- delete throttling policies application policyid
- deleteplatformgateway
- get all llm providers
- get a deny policy
- delete environments environmentid
- updateplatformgateway
- delete a deny policy
- getplatformgateways
- put throttling policies advanced policyid
- get all deny policies
- update a subscription policy
- add an environment
- add an organizations
- add an advanced throttling policy
- get all custom rules
- soap
- update application settings
- post environments
- getllmproviders
- delete applications applicationid
- update an environment
- regenerate registration token for a platform gateway
- import a throttling policy
- update an llm provider
- get applications applicationid
- get all ai service providers
- get llm provider
- delete throttling policies custom ruleid
- get organizations organizationid
- get an advanced throttling policy
- get applications
- update an ai service provider
- add a ai service provider
- add an application throttling policy
- delete a platform gateway
- get a custom rule
- get a subscription policy
- get throttling deny policies
- delete a ai service provider
- get all subscription throttling policies
- addaiserviceprovider
- get organizations
- post applications applicationid change owner
- get throttling policies custom
- register a platform gateway
- get throttling policies advanced policyid
- get throttling policies subscription
- exportthrottlingpolicy
- gateways
- rest
- update an advanced throttling policy
- deleteaiserviceprovider
- update a custom rule
- delete throttling policies advanced policyid
- export a throttling policy
- post throttling policies custom
- put organizations organizationid
- updateaiserviceprovider
- getaiserviceprovider
- graphql
- update a deny policy
- get environments
- get throttling policies subscription policyid
- change application owner
- get the details of an application
- post throttling policies subscription
- put environments environmentid
- wso2
- delete throttling policies subscription policyid
- addllmprovider
- deletellmprovider
- get all application throttling policies
- delete an organization
- retrieve/search throttling policies
- getaiserviceproviders
- regenerateplatformgatewaytoken
- update an application throttling policy
- delete a custom rule
- updateapplicationsettings
- get a gateway environment configuration
- put throttling policies application policyid
slug: wso2-capability
source_filename: wso2-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WSO2 API Manager - Admin\n  description: 'This document specifies a **RESTful API** for WSO2 **API Manager** - **Admin Portal**. Please see [full OpenAPI\n    Specification](https://raw.githubusercontent.com/wso2/carbon-apimgt/master/components/apimgt/org.wso2.carbon.apimgt.rest.api.admin.v1/src/main/resources/admin-api.yaml)\n    of the API which is written using [OAS 3.0](http://swagger.io/) specification. # Authentication The Admin REST API is\n    protected using OAuth2 and access control is achieved through scopes. Before you start invoking the the API you need to\n    obtain an access token with the required scopes. This guide will walk you through'\n  tags:\n  - Wso2\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: wso2\n    baseUri: https://apis.wso2.com/api/am/admin/v4\n    description: WSO2 API Manager - Admin HTTP API.\n    authentication:\n      type: bearer\n\
  \      token: '{{WSO2_TOKEN}}'\n    resources:\n    - name: throttling-policies-search\n      path: /throttling/policies/search\n      operations:\n      - name: throttlingpolicysearch\n        method: GET\n        description: Retrieve/Search Throttling Policies\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          description: '**Search**. You can search by providing a keyword. Allowed to search by type and name only.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: throttling-policies-application\n      path: /throttling/policies/application\n      operations:\n      - name: get-throttling-policies-application\n        method: GET\n        description: Get all Application Throttling Policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-throttling-policies-application\n\
  \        method: POST\n        description: Add an Application Throttling Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: throttling-policies-application-policyid\n      path: /throttling/policies/application/{policyId}\n      operations:\n      - name: get-throttling-policies-application-policyid\n        method: GET\n        description: Get an Application Throttling Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-throttling-policies-application-policyid\n        method: PUT\n        description: Update an Application Throttling policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-throttling-policies-application-policyid\n        method: DELETE\n        description: Delete an Application\
  \ Throttling policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: throttling-policies-subscription\n      path: /throttling/policies/subscription\n      operations:\n      - name: get-throttling-policies-subscription\n        method: GET\n        description: Get all Subscription Throttling Policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-throttling-policies-subscription\n        method: POST\n        description: Add a Subscription Throttling Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: throttling-policies-subscription-policyid\n      path: /throttling/policies/subscription/{policyId}\n      operations:\n      - name: get-throttling-policies-subscription-policyid\n        method: GET\n \
  \       description: Get a Subscription Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-throttling-policies-subscription-policyid\n        method: PUT\n        description: Update a Subscription Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-throttling-policies-subscription-policyid\n        method: DELETE\n        description: Delete a Subscription Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: throttling-policies-custom\n      path: /throttling/policies/custom\n      operations:\n      - name: get-throttling-policies-custom\n        method: GET\n        description: Get all Custom Rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: post-throttling-policies-custom\n        method: POST\n        description: Add a Custom Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: throttling-policies-custom-ruleid\n      path: /throttling/policies/custom/{ruleId}\n      operations:\n      - name: get-throttling-policies-custom-ruleid\n        method: GET\n        description: Get a Custom Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-throttling-policies-custom-ruleid\n        method: PUT\n        description: Update a Custom Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-throttling-policies-custom-ruleid\n        method: DELETE\n        description: Delete a Custom Rule\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: throttling-policies-advanced\n      path: /throttling/policies/advanced\n      operations:\n      - name: get-throttling-policies-advanced\n        method: GET\n        description: Get all Advanced Throttling Policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-throttling-policies-advanced\n        method: POST\n        description: Add an Advanced Throttling Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: throttling-policies-advanced-policyid\n      path: /throttling/policies/advanced/{policyId}\n      operations:\n      - name: get-throttling-policies-advanced-policyid\n        method: GET\n        description: Get an Advanced Throttling Policy\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-throttling-policies-advanced-policyid\n        method: PUT\n        description: Update an Advanced Throttling Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-throttling-policies-advanced-policyid\n        method: DELETE\n        description: Delete an Advanced Throttling Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: throttling-policies-export\n      path: /throttling/policies/export\n      operations:\n      - name: exportthrottlingpolicy\n        method: GET\n        description: Export a Throttling Policy\n        inputParameters:\n        - name: policyId\n          in: query\n          type: string\n          description: UUID of the\
  \ ThrottlingPolicy\n        - name: name\n          in: query\n          type: string\n          description: Throttling Policy Name\n        - name: type\n          in: query\n          type: string\n          description: Type of the Throttling Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: throttling-policies-import\n      path: /throttling/policies/import\n      operations:\n      - name: importthrottlingpolicy\n        method: POST\n        description: Import a Throttling Policy\n        inputParameters:\n        - name: overwrite\n          in: query\n          type: boolean\n          description: Update an existing throttlingpolicy with the same name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: throttling-deny-policies\n      path: /throttling/deny-policies\n      operations:\n      -\
  \ name: get-throttling-deny-policies\n        method: GET\n        description: Get all Deny Policies\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          description: '**Search condition**. You can search in attributes by using **\"conditionType:\"** modifier and **\"conditionValue:\"**\n            modifier. Eg. The entry \"conditionType:API\" '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-throttling-deny-policies\n        method: POST\n        description: Add a deny policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: throttling-deny-policy-conditionid\n      path: /throttling/deny-policy/{conditionId}\n      operations:\n      - name: get-throttling-deny-policy-conditionid\n        method: GET\n        description: Get a Deny Policy\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-throttling-deny-policy-conditionid\n        method: DELETE\n        description: Delete a Deny Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-throttling-deny-policy-conditionid\n        method: PATCH\n        description: Update a Deny Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /applications\n      operations:\n      - name: get-applications\n        method: GET\n        description: Retrieve/Search Applications\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Application Name\n        - name: tenantDomain\n          in: query\n          type:\
  \ string\n          description: Tenant domain of the applications to get. This has to be specified only if it is required to get applications\n            of a tenant other than the requester's tenant. So,\n        - name: sortBy\n          in: query\n          type: string\n        - name: sortOrder\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationid\n      path: /applications/{applicationId}\n      operations:\n      - name: get-applications-applicationid\n        method: GET\n        description: Get the details of an Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-applications-applicationid\n        method: DELETE\n        description: Delete an Application\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationid-change-settings\n      path: /applications/{applicationId}/change-settings\n      operations:\n      - name: updateapplicationsettings\n        method: POST\n        description: Update Application Settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-applicationid-change-owner\n      path: /applications/{applicationId}/change-owner\n      operations:\n      - name: post-applications-applicationid-change-owner\n        method: POST\n        description: Change Application Owner\n        inputParameters:\n        - name: owner\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ai-service-providers\n      path: /ai-service-providers\n\
  \      operations:\n      - name: getaiserviceproviders\n        method: GET\n        description: Get all AI Service providers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addaiserviceprovider\n        method: POST\n        description: Add a AI Service provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ai-service-providers-aiserviceproviderid\n      path: /ai-service-providers/{aiServiceProviderId}\n      operations:\n      - name: updateaiserviceprovider\n        method: PUT\n        description: Update an AI Service provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteaiserviceprovider\n        method: DELETE\n        description: Delete a AI Service Provider\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getaiserviceprovider\n        method: GET\n        description: Get AI Service Provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: llm-providers\n      path: /llm-providers\n      operations:\n      - name: getllmproviders\n        method: GET\n        description: Get all LLM providers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addllmprovider\n        method: POST\n        description: Add a LLM provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: llm-providers-llmproviderid\n      path: /llm-providers/{llmProviderId}\n      operations:\n      - name: updatellmprovider\n        method: PUT\n\
  \        description: Update an LLM provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletellmprovider\n        method: DELETE\n        description: Delete a LLM Provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getllmprovider\n        method: GET\n        description: Get LLM Provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments\n      path: /environments\n      operations:\n      - name: get-environments\n        method: GET\n        description: Get all registered Environments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-environments\n        method: POST\n        description:\
  \ Add an Environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid\n      path: /environments/{environmentId}\n      operations:\n      - name: get-environments-environmentid\n        method: GET\n        description: Get a Gateway Environment Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-environments-environmentid\n        method: PUT\n        description: Update an Environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-environments-environmentid\n        method: DELETE\n        description: Delete an Environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ environments-environmentid-gateways\n      path: /environments/{environmentId}/gateways\n      operations:\n      - name: get-environments-environmentid-gateways\n        method: GET\n        description: Get Gateway Instances in a Gateway Environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gateways\n      path: /gateways\n      operations:\n      - name: getplatformgateways\n        method: GET\n        description: Get all platform gateways\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createplatformgateway\n        method: POST\n        description: Register a platform gateway\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gateways-gatewayid-regenerate-token\n      path: /gateways/{gatewayId}/regenerate-token\n\
  \      operations:\n      - name: regenerateplatformgatewaytoken\n        method: POST\n        description: Regenerate registration token for a platform gateway\n        inputParameters:\n        - name: gatewayId\n          in: path\n          type: string\n          required: true\n          description: Gateway UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gateways-gatewayid\n      path: /gateways/{gatewayId}\n      operations:\n      - name: updateplatformgateway\n        method: PUT\n        description: Update a platform gateway\n        inputParameters:\n        - name: gatewayId\n          in: path\n          type: string\n          required: true\n          description: Gateway UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteplatformgateway\n        method: DELETE\n        description:\
  \ Delete a platform gateway\n        inputParameters:\n        - name: gatewayId\n          in: path\n          type: string\n          required: true\n          description: Gateway UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n      path: /organizations\n      operations:\n      - name: get-organizations\n        method: GET\n        description: Get all registered Organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-organizations\n        method: POST\n        description: Add an Organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organizationid\n      path: /organizations/{organizationId}\n      operations:\n      - name: get-organizations-organizationid\n\
  \        method: GET\n        description: Get an Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-organizations-organizationid\n        method: PUT\n        description: Update an Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-organizations-organizationid\n        method: DELETE\n        description: Delete an Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: me-organization-information\n      path: /me/organization-information\n      operations:\n      - name: organizationinformation\n        method: GET\n        description: Get the Organization information of the user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wso2-rest\n    description: REST adapter for WSO2 API Manager - Admin.\n    resources:\n    - path: /throttling/policies/search\n      name: throttlingpolicysearch\n      operations:\n      - method: GET\n        name: throttlingpolicysearch\n        description: Retrieve/Search Throttling Policies\n        call: wso2.throttlingpolicysearch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/application\n      name: get-throttling-policies-application\n      operations:\n      - method: GET\n        name: get-throttling-policies-application\n        description: Get all Application Throttling Policies\n        call: wso2.get-throttling-policies-application\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/application\n      name: post-throttling-policies-application\n      operations:\n\
  \      - method: POST\n        name: post-throttling-policies-application\n        description: Add an Application Throttling Policy\n        call: wso2.post-throttling-policies-application\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/application/{policyId}\n      name: get-throttling-policies-application-policyid\n      operations:\n      - method: GET\n        name: get-throttling-policies-application-policyid\n        description: Get an Application Throttling Policy\n        call: wso2.get-throttling-policies-application-policyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/application/{policyId}\n      name: put-throttling-policies-application-policyid\n      operations:\n      - method: PUT\n        name: put-throttling-policies-application-policyid\n        description: Update an Application Throttling policy\n        call: wso2.put-throttling-policies-application-policyid\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/application/{policyId}\n      name: delete-throttling-policies-application-policyid\n      operations:\n      - method: DELETE\n        name: delete-throttling-policies-application-policyid\n        description: Delete an Application Throttling policy\n        call: wso2.delete-throttling-policies-application-policyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/subscription\n      name: get-throttling-policies-subscription\n      operations:\n      - method: GET\n        name: get-throttling-policies-subscription\n        description: Get all Subscription Throttling Policies\n        call: wso2.get-throttling-policies-subscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/subscription\n      name: post-throttling-policies-subscription\n      operations:\n\
  \      - method: POST\n        name: post-throttling-policies-subscription\n        description: Add a Subscription Throttling Policy\n        call: wso2.post-throttling-policies-subscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/subscription/{policyId}\n      name: get-throttling-policies-subscription-policyid\n      operations:\n      - method: GET\n        name: get-throttling-policies-subscription-policyid\n        description: Get a Subscription Policy\n        call: wso2.get-throttling-policies-subscription-policyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/subscription/{policyId}\n      name: put-throttling-policies-subscription-policyid\n      operations:\n      - method: PUT\n        name: put-throttling-policies-subscription-policyid\n        description: Update a Subscription Policy\n        call: wso2.put-throttling-policies-subscription-policyid\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/subscription/{policyId}\n      name: delete-throttling-policies-subscription-policyid\n      operations:\n      - method: DELETE\n        name: delete-throttling-policies-subscription-policyid\n        description: Delete a Subscription Policy\n        call: wso2.delete-throttling-policies-subscription-policyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/custom\n      name: get-throttling-policies-custom\n      operations:\n      - method: GET\n        name: get-throttling-policies-custom\n        description: Get all Custom Rules\n        call: wso2.get-throttling-policies-custom\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/custom\n      name: post-throttling-policies-custom\n      operations:\n      - method: POST\n        name: post-throttling-policies-custom\n\
  \        description: Add a Custom Rule\n        call: wso2.post-throttling-policies-custom\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/custom/{ruleId}\n      name: get-throttling-policies-custom-ruleid\n      operations:\n      - method: GET\n        name: get-throttling-policies-custom-ruleid\n        description: Get a Custom Rule\n        call: wso2.get-throttling-policies-custom-ruleid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/custom/{ruleId}\n      name: put-throttling-policies-custom-ruleid\n      operations:\n      - method: PUT\n        name: put-throttling-policies-custom-ruleid\n        description: Update a Custom Rule\n        call: wso2.put-throttling-policies-custom-ruleid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/custom/{ruleId}\n      name: delete-throttling-policies-custom-ruleid\n\
  \      operations:\n      - method: DELETE\n        name: delete-throttling-policies-custom-ruleid\n        description: Delete a Custom Rule\n        call: wso2.delete-throttling-policies-custom-ruleid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/advanced\n      name: get-throttling-policies-advanced\n      operations:\n      - method: GET\n        name: get-throttling-policies-advanced\n        description: Get all Advanced Throttling Policies\n        call: wso2.get-throttling-policies-advanced\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/advanced\n      name: post-throttling-policies-advanced\n      operations:\n      - method: POST\n        name: post-throttling-policies-advanced\n        description: Add an Advanced Throttling Policy\n        call: wso2.post-throttling-policies-advanced\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /throttling/policies/advanced/{policyId}\n      name: get-throttling-policies-advanced-policyid\n      operations:\n      - method: GET\n        name: get-throttling-policies-advanced-policyid\n        description: Get an Advanced Throttling Policy\n        call: wso2.get-throttling-policies-advanced-policyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/advanced/{policyId}\n      name: put-throttling-policies-advanced-policyid\n      operations:\n      - method: PUT\n        name: put-throttling-policies-advanced-policyid\n        description: Update an Advanced Throttling Policy\n        call: wso2.put-throttling-policies-advanced-policyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/advanced/{policyId}\n      name: delete-throttling-policies-advanced-policyid\n      operations:\n      - method: DELETE\n        name: delete-throttling-policies-advanced-policyid\n\
  \        description: Delete an Advanced Throttling Policy\n        call: wso2.delete-throttling-policies-advanced-policyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/export\n      name: exportthrottlingpolicy\n      operations:\n      - method: GET\n        name: exportthrottlingpolicy\n        description: Export a Throttling Policy\n        call: wso2.exportthrottlingpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/policies/import\n      name: importthrottlingpolicy\n      operations:\n      - method: POST\n        name: importthrottlingpolicy\n        description: Import a Throttling Policy\n        call: wso2.importthrottlingpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/deny-policies\n      name: get-throttling-deny-policies\n      operations:\n      - method: GET\n        name: get-throttling-deny-policies\n\
  \        description: Get all Deny Policies\n        call: wso2.get-throttling-deny-policies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/deny-policies\n      name: post-throttling-deny-policies\n      operations:\n      - method: POST\n        name: post-throttling-deny-policies\n        description: Add a deny policy\n        call: wso2.post-throttling-deny-policies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/deny-policy/{conditionId}\n      name: get-throttling-deny-policy-conditionid\n      operations:\n      - method: GET\n        name: get-throttling-deny-policy-conditionid\n        description: Get a Deny Policy\n        call: wso2.get-throttling-deny-policy-conditionid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/deny-policy/{conditionId}\n      name: delete-throttling-deny-policy-conditionid\n      operations:\n    \
  \  - method: DELETE\n        name: delete-throttling-deny-policy-conditionid\n        description: Delete a Deny Policy\n        call: wso2.delete-throttling-deny-policy-conditionid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /throttling/deny-policy/{conditionId}\n      name: patch-throttling-deny-policy-conditionid\n      operations:\n      - method: PATCH\n        name: patch-throttling-deny-policy-conditionid\n        description: Update a Deny Policy\n        call: wso2.patch-throttling-deny-policy-conditionid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications\n      name: get-applications\n      operations:\n      - method: GET\n        name: get-applications\n        description: Retrieve/Search Applications\n        call: wso2.get-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationId}\n      name: get-applications-applicationid\n\
  \      operations:\n      - method: GET\n        name: get-applications-applicationid\n        description: Get the details of an Application\n        call: wso2.get-applications-applicationid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationId}\n      name: delete-applications-applicationid\n      operations:\n      - method: DELETE\n        name: delete-applications-applicationid\n        description: Delete an Application\n        call: wso2.delete-applications-applicationid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationId}/change-settings\n      name: updateapplicationsettings\n      operations:\n      - method: POST\n        name: updateapplicationsettings\n        description: Update Application Settings\n        call: wso2.updateapplicationsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{applicationId}/change-owner\n\
  \      name: post-applications-applicationid-change-owner\n      operations:\n      - method: POST\n        name: post-applications-applicationid-change-owner\n        description: Change Application Owner\n        call: wso2.post-applications-applicationid-change-owner\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ai-service-providers\n      name: getaiserviceproviders\n      operations:\n      - method: GET\n        name: getaiserviceproviders\n        description: Get all AI Service providers\n        call: wso2.getaiserviceproviders\n        outputParameters:\n \n\n# --- truncated at 32 KB (59 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/wso2/refs/heads/main/capabilities/wso2-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wso2/refs/heads/main/capabilities/wso2-capability.yaml
tags:
- Wso2
- API
tools:
- description: Retrieve/Search Throttling Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: throttlingpolicysearch
- description: Get all Application Throttling Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-throttling-policies-application
- description: Add an Application Throttling Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-throttling-policies-application
- description: Get an Application Throttling Policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-throttling-policies-application-policyid
- description: Update an Application Throttling policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-throttling-policies-application-policyid
- description: Delete an Application Throttling policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-throttling-policies-application-policyid
- description: Get all Subscription Throttling Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-throttling-policies-subscription
- description: Add a Subscription Throttling Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-throttling-policies-subscription
- description: Get a Subscription Policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-throttling-policies-subscription-policyid
- description: Update a Subscription Policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-throttling-policies-subscription-policyid
- description: Delete a Subscription Policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-throttling-policies-subscription-policyid
- description: Get all Custom Rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-throttling-policies-custom
- description: Add a Custom Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-throttling-policies-custom
- description: Get a Custom Rule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-throttling-policies-custom-ruleid
- description: Update a Custom Rule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-throttling-policies-custom-ruleid
- description: Delete a Custom Rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-throttling-policies-custom-ruleid
- description: Get all Advanced Throttling Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-throttling-policies-advanced
- description: Add an Advanced Throttling Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-throttling-policies-advanced
- description: Get an Advanced Throttling Policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-throttling-policies-advanced-policyid
- description: Update an Advanced Throttling Policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-throttling-policies-advanced-policyid
- description: Delete an Advanced Throttling Policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-throttling-policies-advanced-policyid
- description: Export a Throttling Policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: exportthrottlingpolicy
- description: Import a Throttling Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: importthrottlingpolicy
- description: Get all Deny Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-throttling-deny-policies
- description: Add a deny policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-throttling-deny-policies
- description: Get a Deny Policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-throttling-deny-policy-conditionid
- description: Delete a Deny Policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-throttling-deny-policy-conditionid
- description: Update a Deny Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-throttling-deny-policy-conditionid
- description: Retrieve/Search Applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-applications
- description: Get the details of an Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-applications-applicationid
- description: Delete an Application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-applications-applicationid
- description: Update Application Settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapplicationsettings
- description: Change Application Owner
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-applications-applicationid-change-owner
- description: Get all AI Service providers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaiserviceproviders
- description: Add a AI Service provider
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addaiserviceprovider
- description: Update an AI Service provider
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateaiserviceprovider
- description: Delete a AI Service Provider
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaiserviceprovider
- description: Get AI Service Provider
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaiserviceprovider
- description: Get all LLM providers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getllmproviders
- description: Add a LLM provider
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addllmprovider
- description: Update an LLM provider
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatellmprovider
- description: Delete a LLM Provider
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletellmprovider
- description: Get LLM Provider
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getllmprovider
- description: Get all registered Environments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-environments
- description: Add an Environment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-environments
- description: Get a Gateway Environment Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-environments-environmentid
- description: Update an Environment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-environments-environmentid
- description: Delete an Environment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-environments-environmentid
- description: Get Gateway Instances in a Gateway Environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-environments-environmentid-gateways
- description: Get all platform gateways
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getplatformgateways
- description: Register a platform gateway
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createplatformgateway
- description: Regenerate registration token for a platform gateway
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: regenerateplatformgatewaytoken
- description: Update a platform gateway
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateplatformgateway
- description: Delete a platform gateway
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteplatformgateway
- description: Get all registered Organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-organizations
- description: Add an Organizations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-organizations
- description: Get an Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-organizations-organizationid
- description: Update an Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-organizations-organizationid
- description: Delete an Organization
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-organizations-organizationid
- description: Get the Organization information of the user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: organizationinformation
---
