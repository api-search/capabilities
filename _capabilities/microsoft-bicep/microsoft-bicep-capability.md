---
categories: []
consumed_apis: []
description: Azure Resource Manager Deployments REST API used by Microsoft Bicep to deploy infrastructure as code templates. Provides operations for creating, validating, and managing ARM/Bicep template deployments at resource group, subscription, management group, and tenant scopes.
layout: capability
name: Microsoft Bicep Deployments API
operations:
- description: Microsoft Bicep Create or update a deployment
  method: PUT
  name: deployments-createorupdate
  path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}
- description: Microsoft Bicep Get a deployment
  method: GET
  name: deployments-get
  path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}
- description: Microsoft Bicep Delete a deployment
  method: DELETE
  name: deployments-delete
  path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}
- description: Microsoft Bicep Validate a deployment template
  method: POST
  name: deployments-validate
  path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/validate
- description: Microsoft Bicep Cancel a running deployment
  method: POST
  name: deployments-cancel
  path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/cancel
- description: Microsoft Bicep Export a deployment template
  method: POST
  name: deployments-exporttemplate
  path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/exportTemplate
- description: Microsoft Bicep Run what-if analysis
  method: POST
  name: deployments-whatif
  path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/whatIf
- description: Microsoft Bicep List deployments by resource group
  method: GET
  name: deployments-listbyresourcegroup
  path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments
- description: Microsoft Bicep Create or update a deployment at subscription scope
  method: PUT
  name: deployments-createorupdateatsubscriptionscope
  path: /subscriptions/{subscriptionId}/providers/Microsoft.Resources/deployments/{deploymentName}
- description: Microsoft Bicep Get a deployment at subscription scope
  method: GET
  name: deployments-getatsubscriptionscope
  path: /subscriptions/{subscriptionId}/providers/Microsoft.Resources/deployments/{deploymentName}
- description: Microsoft Bicep Validate a deployment at subscription scope
  method: POST
  name: deployments-validateatsubscriptionscope
  path: /subscriptions/{subscriptionId}/providers/Microsoft.Resources/deployments/{deploymentName}/validate
- description: Microsoft Bicep Calculate template hash
  method: POST
  name: deployments-calculatetemplatehash
  path: /providers/Microsoft.Resources/calculateTemplateHash
personas: []
provider_name: Microsoft Bicep
provider_slug: microsoft-bicep
search_terms:
- devops
- microsoft bicep create or update a deployment at subscription scope
- deployments validateatsubscriptionscope
- deployments whatif
- api
- arm templates
- microsoft bicep list deployments by resource group
- deployments cancel
- bicep
- microsoft bicep run what-if analysis
- microsoft bicep create or update a deployment
- deployments getatsubscriptionscope
- deployments calculatetemplatehash
- deployment
- microsoft
- microsoft bicep cancel a running deployment
- deployments createorupdate
- deployments createorupdateatsubscriptionscope
- microsoft bicep get a deployment
- cloud
- infrastructure as code
- deployments get
- microsoft bicep export a deployment template
- microsoft bicep validate a deployment template
- azure
- deployments delete
- microsoft bicep get a deployment at subscription scope
- deployments exporttemplate
- microsoft bicep delete a deployment
- microsoft bicep calculate template hash
- deployments validate
- microsoft bicep validate a deployment at subscription scope
- deployments listbyresourcegroup
slug: microsoft-bicep-capability
source_filename: microsoft-bicep-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Bicep Deployments API\n  description: Azure Resource Manager Deployments REST API used by Microsoft Bicep to deploy infrastructure as code templates.\n    Provides operations for creating, validating, and managing ARM/Bicep template deployments at resource group, subscription,\n    management group, and tenant scopes.\n  tags:\n  - Microsoft\n  - Bicep\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-bicep\n    baseUri: https://management.azure.com\n    description: Microsoft Bicep Deployments API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_BICEP_TOKEN}}'\n    resources:\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}\n      operations:\n      - name: deployments-createorupdate\n\
  \        method: PUT\n        description: Microsoft Bicep Create or update a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deployments-get\n        method: GET\n        description: Microsoft Bicep Get a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deployments-delete\n        method: DELETE\n        description: Microsoft Bicep Delete a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/validate\n      operations:\n      - name: deployments-validate\n        method: POST\n        description:\
  \ Microsoft Bicep Validate a deployment template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/cancel\n      operations:\n      - name: deployments-cancel\n        method: POST\n        description: Microsoft Bicep Cancel a running deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/exportTemplate\n      operations:\n      - name: deployments-exporttemplate\n        method: POST\n        description: Microsoft Bicep Export a deployment\
  \ template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/whatIf\n      operations:\n      - name: deployments-whatif\n        method: POST\n        description: Microsoft Bicep Run what-if analysis\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-resourcegroups-reso\n      path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments\n      operations:\n      - name: deployments-listbyresourcegroup\n        method: GET\n        description: Microsoft Bicep List deployments by resource group\n        inputParameters:\n        - name: $filter\n\
  \          in: query\n          type: string\n          description: OData filter expression to apply\n        - name: $top\n          in: query\n          type: integer\n          description: Maximum number of results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-providers-microsoft\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Resources/deployments/{deploymentName}\n      operations:\n      - name: deployments-createorupdateatsubscriptionscope\n        method: PUT\n        description: Microsoft Bicep Create or update a deployment at subscription scope\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deployments-getatsubscriptionscope\n        method: GET\n        description: Microsoft Bicep Get a deployment at subscription scope\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid-providers-microsoft\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Resources/deployments/{deploymentName}/validate\n      operations:\n      - name: deployments-validateatsubscriptionscope\n        method: POST\n        description: Microsoft Bicep Validate a deployment at subscription scope\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: providers-microsoft-resources-calculatetemplateh\n      path: /providers/Microsoft.Resources/calculateTemplateHash\n      operations:\n      - name: deployments-calculatetemplatehash\n        method: POST\n        description: Microsoft Bicep Calculate template hash\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: microsoft-bicep-rest\n    description: REST adapter for Microsoft Bicep Deployments API.\n    resources:\n    - path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}\n      name: deployments-createorupdate\n      operations:\n      - method: PUT\n        name: deployments-createorupdate\n        description: Microsoft Bicep Create or update a deployment\n        call: microsoft-bicep.deployments-createorupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}\n      name: deployments-get\n      operations:\n      - method: GET\n        name: deployments-get\n        description: Microsoft Bicep Get a deployment\n        call: microsoft-bicep.deployments-get\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}\n      name: deployments-delete\n      operations:\n      - method: DELETE\n        name: deployments-delete\n        description: Microsoft Bicep Delete a deployment\n        call: microsoft-bicep.deployments-delete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/validate\n      name: deployments-validate\n      operations:\n      - method: POST\n        name: deployments-validate\n        description: Microsoft Bicep Validate a deployment template\n        call: microsoft-bicep.deployments-validate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/cancel\n\
  \      name: deployments-cancel\n      operations:\n      - method: POST\n        name: deployments-cancel\n        description: Microsoft Bicep Cancel a running deployment\n        call: microsoft-bicep.deployments-cancel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/exportTemplate\n      name: deployments-exporttemplate\n      operations:\n      - method: POST\n        name: deployments-exporttemplate\n        description: Microsoft Bicep Export a deployment template\n        call: microsoft-bicep.deployments-exporttemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/whatIf\n      name: deployments-whatif\n      operations:\n      - method: POST\n      \
  \  name: deployments-whatif\n        description: Microsoft Bicep Run what-if analysis\n        call: microsoft-bicep.deployments-whatif\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments\n      name: deployments-listbyresourcegroup\n      operations:\n      - method: GET\n        name: deployments-listbyresourcegroup\n        description: Microsoft Bicep List deployments by resource group\n        call: microsoft-bicep.deployments-listbyresourcegroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/providers/Microsoft.Resources/deployments/{deploymentName}\n      name: deployments-createorupdateatsubscriptionscope\n      operations:\n      - method: PUT\n        name: deployments-createorupdateatsubscriptionscope\n        description: Microsoft Bicep Create or update a deployment\
  \ at subscription scope\n        call: microsoft-bicep.deployments-createorupdateatsubscriptionscope\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/providers/Microsoft.Resources/deployments/{deploymentName}\n      name: deployments-getatsubscriptionscope\n      operations:\n      - method: GET\n        name: deployments-getatsubscriptionscope\n        description: Microsoft Bicep Get a deployment at subscription scope\n        call: microsoft-bicep.deployments-getatsubscriptionscope\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}/providers/Microsoft.Resources/deployments/{deploymentName}/validate\n      name: deployments-validateatsubscriptionscope\n      operations:\n      - method: POST\n        name: deployments-validateatsubscriptionscope\n        description: Microsoft Bicep Validate a deployment at subscription scope\n        call: microsoft-bicep.deployments-validateatsubscriptionscope\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /providers/Microsoft.Resources/calculateTemplateHash\n      name: deployments-calculatetemplatehash\n      operations:\n      - method: POST\n        name: deployments-calculatetemplatehash\n        description: Microsoft Bicep Calculate template hash\n        call: microsoft-bicep.deployments-calculatetemplatehash\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-bicep-mcp\n    transport: http\n    description: MCP adapter for Microsoft Bicep Deployments API for AI agent use.\n    tools:\n    - name: deployments-createorupdate\n      description: Microsoft Bicep Create or update a deployment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: microsoft-bicep.deployments-createorupdate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-get\n\
  \      description: Microsoft Bicep Get a deployment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-bicep.deployments-get\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-delete\n      description: Microsoft Bicep Delete a deployment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-bicep.deployments-delete\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-validate\n      description: Microsoft Bicep Validate a deployment template\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-bicep.deployments-validate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-cancel\n      description: Microsoft Bicep Cancel a running deployment\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: microsoft-bicep.deployments-cancel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-exporttemplate\n      description: Microsoft Bicep Export a deployment template\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-bicep.deployments-exporttemplate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-whatif\n      description: Microsoft Bicep Run what-if analysis\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-bicep.deployments-whatif\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-listbyresourcegroup\n      description: Microsoft Bicep List deployments by resource group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: microsoft-bicep.deployments-listbyresourcegroup\n      with:\n        $filter: tools.$filter\n        $top: tools.$top\n      inputParameters:\n      - name: $filter\n        type: string\n        description: OData filter expression to apply\n      - name: $top\n        type: integer\n        description: Maximum number of results to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-createorupdateatsubscriptionscope\n      description: Microsoft Bicep Create or update a deployment at subscription scope\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: microsoft-bicep.deployments-createorupdateatsubscriptionscope\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-getatsubscriptionscope\n      description: Microsoft Bicep Get a deployment at subscription scope\n      hints:\n        readOnly: true\n        destructive: false\n \
  \       idempotent: true\n      call: microsoft-bicep.deployments-getatsubscriptionscope\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-validateatsubscriptionscope\n      description: Microsoft Bicep Validate a deployment at subscription scope\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-bicep.deployments-validateatsubscriptionscope\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deployments-calculatetemplatehash\n      description: Microsoft Bicep Calculate template hash\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-bicep.deployments-calculatetemplatehash\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_BICEP_TOKEN: MICROSOFT_BICEP_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-bicep/refs/heads/main/capabilities/microsoft-bicep-capability.yaml
tags:
- Microsoft
- Bicep
- API
tools:
- description: Microsoft Bicep Create or update a deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: deployments-createorupdate
- description: Microsoft Bicep Get a deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: deployments-get
- description: Microsoft Bicep Delete a deployment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deployments-delete
- description: Microsoft Bicep Validate a deployment template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deployments-validate
- description: Microsoft Bicep Cancel a running deployment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deployments-cancel
- description: Microsoft Bicep Export a deployment template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deployments-exporttemplate
- description: Microsoft Bicep Run what-if analysis
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deployments-whatif
- description: Microsoft Bicep List deployments by resource group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: deployments-listbyresourcegroup
- description: Microsoft Bicep Create or update a deployment at subscription scope
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: deployments-createorupdateatsubscriptionscope
- description: Microsoft Bicep Get a deployment at subscription scope
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: deployments-getatsubscriptionscope
- description: Microsoft Bicep Validate a deployment at subscription scope
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deployments-validateatsubscriptionscope
- description: Microsoft Bicep Calculate template hash
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deployments-calculatetemplatehash
---
