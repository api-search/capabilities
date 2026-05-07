---
categories: []
consumed_apis: []
description: AWS Resilience Hub provides a central place to define, validate, and track the resilience of your AWS applications, assessing against RTO and RPO targets and providing actionable recommendations.
layout: capability
name: Amazon Resilience Hub
operations:
- description: Amazon Resilience Hub Create App
  method: POST
  name: createapp
  path: /create-app
- description: Amazon Resilience Hub Describe App
  method: POST
  name: describeapp
  path: /describe-app
- description: Amazon Resilience Hub List Apps
  method: GET
  name: listapps
  path: /list-apps
- description: Amazon Resilience Hub Delete App
  method: DELETE
  name: deleteapp
  path: /delete-app
- description: Amazon Resilience Hub Start App Assessment
  method: POST
  name: startappassessment
  path: /start-app-assessment
- description: Amazon Resilience Hub Describe App Assessment
  method: POST
  name: describeappassessment
  path: /describe-app-assessment
- description: Amazon Resilience Hub List App Assessments
  method: GET
  name: listappassessments
  path: /list-app-assessments
- description: Amazon Resilience Hub Create Resiliency Policy
  method: POST
  name: createresiliencypolicy
  path: /create-resiliency-policy
- description: Amazon Resilience Hub Describe Resiliency Policy
  method: POST
  name: describeresiliencypolicy
  path: /describe-resiliency-policy
- description: Amazon Resilience Hub List Resiliency Policies
  method: GET
  name: listresiliencypolicies
  path: /list-resiliency-policies
- description: Amazon Resilience Hub List Alarm Recommendations
  method: POST
  name: listalarmrecommendations
  path: /list-alarm-recommendations
- description: Amazon Resilience Hub List SOP Recommendations
  method: POST
  name: listsoprecommendations
  path: /list-sop-recommendations
- description: Amazon Resilience Hub List Test Recommendations
  method: POST
  name: listtestrecommendations
  path: /list-test-recommendations
- description: Amazon Resilience Hub Add Draft App Version Resource Mappings
  method: POST
  name: adddraftappversionresourcemappings
  path: /add-draft-app-version-resource-mappings
- description: Amazon Resilience Hub Publish App Version
  method: POST
  name: publishappversion
  path: /publish-app-version
- description: Amazon Resilience Hub Import Resources to Draft App Version
  method: POST
  name: importresourcestodraftappversion
  path: /import-resources-to-draft-app-version
- description: Amazon Resilience Hub Resolve App Version Resources
  method: POST
  name: resolveappversionresources
  path: /resolve-app-version-resources
- description: Amazon Resilience Hub Tag Resource
  method: POST
  name: tagresource
  path: /tags/{resourceArn}
- description: Amazon Resilience Hub List Tags for Resource
  method: GET
  name: listtagsforresource
  path: /tags/{resourceArn}
- description: Amazon Resilience Hub List App Versions
  method: GET
  name: listappversions
  path: /list-app-versions
- description: Amazon Resilience Hub List Suggested Resiliency Policies
  method: GET
  name: listsuggestedresiliencypolicies
  path: /list-suggested-resiliency-policies
personas: []
provider_name: Amazon Resilience Hub
provider_slug: amazon-resilience-hub
search_terms:
- listsuggestedresiliencypolicies
- amazon resilience hub list resiliency policies
- amazon resilience hub list app assessments
- amazon resilience hub list alarm recommendations
- listtagsforresource
- operations
- amazon resilience hub list app versions
- amazon resilience hub describe resiliency policy
- createresiliencypolicy
- api
- amazon resilience hub list test recommendations
- listappversions
- amazon resilience hub describe app assessment
- amazon
- amazon resilience hub start app assessment
- amazon resilience hub create resiliency policy
- listtestrecommendations
- high availability
- amazon resilience hub import resources to draft app version
- amazon resilience hub create app
- amazon resilience hub list apps
- publishappversion
- listresiliencypolicies
- hub
- tagresource
- startappassessment
- amazon resilience hub tag resource
- adddraftappversionresourcemappings
- disaster recovery
- listsoprecommendations
- amazon resilience hub resolve app version resources
- amazon resilience hub list suggested resiliency policies
- deleteapp
- describeappassessment
- resolveappversionresources
- listappassessments
- resilience
- createapp
- amazon resilience hub delete app
- listalarmrecommendations
- amazon resilience hub add draft app version resource mappings
- amazon resilience hub describe app
- listapps
- amazon resilience hub list sop recommendations
- describeresiliencypolicy
- importresourcestodraftappversion
- describeapp
- amazon resilience hub publish app version
- amazon resilience hub list tags for resource
slug: amazon-resilience-hub-capability
source_filename: amazon-resilience-hub-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Resilience Hub\n  description: AWS Resilience Hub provides a central place to define, validate, and track the resilience of your AWS applications,\n    assessing against RTO and RPO targets and providing actionable recommendations.\n  tags:\n  - Amazon\n  - Resilience\n  - Hub\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-resilience-hub\n    baseUri: https://resiliencehub.amazonaws.com\n    description: Amazon Resilience Hub HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AMAZON_RESILIENCE_HUB_TOKEN}}'\n    resources:\n    - name: create-app\n      path: /create-app\n      operations:\n      - name: createapp\n        method: POST\n        description: Amazon Resilience Hub Create App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: describe-app\n      path: /describe-app\n      operations:\n      - name: describeapp\n        method: POST\n        description: Amazon Resilience Hub Describe App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-apps\n      path: /list-apps\n      operations:\n      - name: listapps\n        method: GET\n        description: Amazon Resilience Hub List Apps\n        inputParameters:\n        - name: appArn\n          in: query\n          type: string\n          description: The Amazon Resource Name (ARN) of the app.\n        - name: maxResults\n          in: query\n          type: integer\n          description: Maximum number of results to include in the response.\n        - name: nextToken\n          in: query\n          type: string\n          description: Null, or the token from a previous call to get the next set of results.\n        - name: name\n   \
  \       in: query\n          type: string\n          description: The name for the one of the listed applications.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: delete-app\n      path: /delete-app\n      operations:\n      - name: deleteapp\n        method: DELETE\n        description: Amazon Resilience Hub Delete App\n        inputParameters:\n        - name: appArn\n          in: query\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the application.\n        - name: forceDelete\n          in: query\n          type: boolean\n          description: A boolean option to override the failure when deleting an unprotected app.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: start-app-assessment\n      path: /start-app-assessment\n      operations:\n\
  \      - name: startappassessment\n        method: POST\n        description: Amazon Resilience Hub Start App Assessment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: describe-app-assessment\n      path: /describe-app-assessment\n      operations:\n      - name: describeappassessment\n        method: POST\n        description: Amazon Resilience Hub Describe App Assessment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-app-assessments\n      path: /list-app-assessments\n      operations:\n      - name: listappassessments\n        method: GET\n        description: Amazon Resilience Hub List App Assessments\n        inputParameters:\n        - name: appArn\n          in: query\n          type: string\n          description: Amazon Resource Name (ARN) of the application.\n        - name: assessmentName\n\
  \          in: query\n          type: string\n          description: The name for the assessment.\n        - name: assessmentStatus\n          in: query\n          type: array\n          description: The current status of the assessment for the resiliency policy.\n        - name: maxResults\n          in: query\n          type: integer\n        - name: nextToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create-resiliency-policy\n      path: /create-resiliency-policy\n      operations:\n      - name: createresiliencypolicy\n        method: POST\n        description: Amazon Resilience Hub Create Resiliency Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: describe-resiliency-policy\n      path: /describe-resiliency-policy\n      operations:\n      - name:\
  \ describeresiliencypolicy\n        method: POST\n        description: Amazon Resilience Hub Describe Resiliency Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-resiliency-policies\n      path: /list-resiliency-policies\n      operations:\n      - name: listresiliencypolicies\n        method: GET\n        description: Amazon Resilience Hub List Resiliency Policies\n        inputParameters:\n        - name: policyName\n          in: query\n          type: string\n          description: The name of the policy\n        - name: maxResults\n          in: query\n          type: integer\n        - name: nextToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-alarm-recommendations\n      path: /list-alarm-recommendations\n      operations:\n      - name:\
  \ listalarmrecommendations\n        method: POST\n        description: Amazon Resilience Hub List Alarm Recommendations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-sop-recommendations\n      path: /list-sop-recommendations\n      operations:\n      - name: listsoprecommendations\n        method: POST\n        description: Amazon Resilience Hub List SOP Recommendations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-test-recommendations\n      path: /list-test-recommendations\n      operations:\n      - name: listtestrecommendations\n        method: POST\n        description: Amazon Resilience Hub List Test Recommendations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: add-draft-app-version-resource-mappings\n\
  \      path: /add-draft-app-version-resource-mappings\n      operations:\n      - name: adddraftappversionresourcemappings\n        method: POST\n        description: Amazon Resilience Hub Add Draft App Version Resource Mappings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: publish-app-version\n      path: /publish-app-version\n      operations:\n      - name: publishappversion\n        method: POST\n        description: Amazon Resilience Hub Publish App Version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: import-resources-to-draft-app-version\n      path: /import-resources-to-draft-app-version\n      operations:\n      - name: importresourcestodraftappversion\n        method: POST\n        description: Amazon Resilience Hub Import Resources to Draft App Version\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resolve-app-version-resources\n      path: /resolve-app-version-resources\n      operations:\n      - name: resolveappversionresources\n        method: POST\n        description: Amazon Resilience Hub Resolve App Version Resources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags-resourcearn\n      path: /tags/{resourceArn}\n      operations:\n      - name: tagresource\n        method: POST\n        description: Amazon Resilience Hub Tag Resource\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listtagsforresource\n\
  \        method: GET\n        description: Amazon Resilience Hub List Tags for Resource\n        inputParameters:\n        - name: resourceArn\n          in: path\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-app-versions\n      path: /list-app-versions\n      operations:\n      - name: listappversions\n        method: GET\n        description: Amazon Resilience Hub List App Versions\n        inputParameters:\n        - name: appArn\n          in: query\n          type: string\n          required: true\n          description: The Amazon Resource Name (ARN) of the application.\n        - name: maxResults\n          in: query\n          type: integer\n        - name: nextToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: list-suggested-resiliency-policies\n      path: /list-suggested-resiliency-policies\n      operations:\n      - name: listsuggestedresiliencypolicies\n        method: GET\n        description: Amazon Resilience Hub List Suggested Resiliency Policies\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: integer\n        - name: nextToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-resilience-hub-rest\n    description: REST adapter for Amazon Resilience Hub.\n    resources:\n    - path: /create-app\n      name: createapp\n      operations:\n      - method: POST\n        name: createapp\n        description: Amazon Resilience Hub Create App\n        call: amazon-resilience-hub.createapp\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /describe-app\n      name: describeapp\n      operations:\n      - method: POST\n        name: describeapp\n        description: Amazon Resilience Hub Describe App\n        call: amazon-resilience-hub.describeapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /list-apps\n      name: listapps\n      operations:\n      - method: GET\n        name: listapps\n        description: Amazon Resilience Hub List Apps\n        call: amazon-resilience-hub.listapps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /delete-app\n      name: deleteapp\n      operations:\n      - method: DELETE\n        name: deleteapp\n        description: Amazon Resilience Hub Delete App\n        call: amazon-resilience-hub.deleteapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /start-app-assessment\n      name: startappassessment\n\
  \      operations:\n      - method: POST\n        name: startappassessment\n        description: Amazon Resilience Hub Start App Assessment\n        call: amazon-resilience-hub.startappassessment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /describe-app-assessment\n      name: describeappassessment\n      operations:\n      - method: POST\n        name: describeappassessment\n        description: Amazon Resilience Hub Describe App Assessment\n        call: amazon-resilience-hub.describeappassessment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /list-app-assessments\n      name: listappassessments\n      operations:\n      - method: GET\n        name: listappassessments\n        description: Amazon Resilience Hub List App Assessments\n        call: amazon-resilience-hub.listappassessments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /create-resiliency-policy\n \
  \     name: createresiliencypolicy\n      operations:\n      - method: POST\n        name: createresiliencypolicy\n        description: Amazon Resilience Hub Create Resiliency Policy\n        call: amazon-resilience-hub.createresiliencypolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /describe-resiliency-policy\n      name: describeresiliencypolicy\n      operations:\n      - method: POST\n        name: describeresiliencypolicy\n        description: Amazon Resilience Hub Describe Resiliency Policy\n        call: amazon-resilience-hub.describeresiliencypolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /list-resiliency-policies\n      name: listresiliencypolicies\n      operations:\n      - method: GET\n        name: listresiliencypolicies\n        description: Amazon Resilience Hub List Resiliency Policies\n        call: amazon-resilience-hub.listresiliencypolicies\n        outputParameters:\n     \
  \   - type: object\n          mapping: $.\n    - path: /list-alarm-recommendations\n      name: listalarmrecommendations\n      operations:\n      - method: POST\n        name: listalarmrecommendations\n        description: Amazon Resilience Hub List Alarm Recommendations\n        call: amazon-resilience-hub.listalarmrecommendations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /list-sop-recommendations\n      name: listsoprecommendations\n      operations:\n      - method: POST\n        name: listsoprecommendations\n        description: Amazon Resilience Hub List SOP Recommendations\n        call: amazon-resilience-hub.listsoprecommendations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /list-test-recommendations\n      name: listtestrecommendations\n      operations:\n      - method: POST\n        name: listtestrecommendations\n        description: Amazon Resilience Hub List Test Recommendations\n     \
  \   call: amazon-resilience-hub.listtestrecommendations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /add-draft-app-version-resource-mappings\n      name: adddraftappversionresourcemappings\n      operations:\n      - method: POST\n        name: adddraftappversionresourcemappings\n        description: Amazon Resilience Hub Add Draft App Version Resource Mappings\n        call: amazon-resilience-hub.adddraftappversionresourcemappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /publish-app-version\n      name: publishappversion\n      operations:\n      - method: POST\n        name: publishappversion\n        description: Amazon Resilience Hub Publish App Version\n        call: amazon-resilience-hub.publishappversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /import-resources-to-draft-app-version\n      name: importresourcestodraftappversion\n      operations:\n\
  \      - method: POST\n        name: importresourcestodraftappversion\n        description: Amazon Resilience Hub Import Resources to Draft App Version\n        call: amazon-resilience-hub.importresourcestodraftappversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /resolve-app-version-resources\n      name: resolveappversionresources\n      operations:\n      - method: POST\n        name: resolveappversionresources\n        description: Amazon Resilience Hub Resolve App Version Resources\n        call: amazon-resilience-hub.resolveappversionresources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{resourceArn}\n      name: tagresource\n      operations:\n      - method: POST\n        name: tagresource\n        description: Amazon Resilience Hub Tag Resource\n        call: amazon-resilience-hub.tagresource\n        with:\n          resourceArn: rest.resourceArn\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /tags/{resourceArn}\n      name: listtagsforresource\n      operations:\n      - method: GET\n        name: listtagsforresource\n        description: Amazon Resilience Hub List Tags for Resource\n        call: amazon-resilience-hub.listtagsforresource\n        with:\n          resourceArn: rest.resourceArn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /list-app-versions\n      name: listappversions\n      operations:\n      - method: GET\n        name: listappversions\n        description: Amazon Resilience Hub List App Versions\n        call: amazon-resilience-hub.listappversions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /list-suggested-resiliency-policies\n      name: listsuggestedresiliencypolicies\n      operations:\n      - method: GET\n        name: listsuggestedresiliencypolicies\n        description: Amazon Resilience Hub List Suggested Resiliency\
  \ Policies\n        call: amazon-resilience-hub.listsuggestedresiliencypolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-resilience-hub-mcp\n    transport: http\n    description: MCP adapter for Amazon Resilience Hub for AI agent use.\n    tools:\n    - name: createapp\n      description: Amazon Resilience Hub Create App\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.createapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeapp\n      description: Amazon Resilience Hub Describe App\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.describeapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapps\n      description: Amazon Resilience Hub List Apps\n      hints:\n    \
  \    readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-resilience-hub.listapps\n      with:\n        appArn: tools.appArn\n        maxResults: tools.maxResults\n        nextToken: tools.nextToken\n        name: tools.name\n      inputParameters:\n      - name: appArn\n        type: string\n        description: The Amazon Resource Name (ARN) of the app.\n      - name: maxResults\n        type: integer\n        description: Maximum number of results to include in the response.\n      - name: nextToken\n        type: string\n        description: Null, or the token from a previous call to get the next set of results.\n      - name: name\n        type: string\n        description: The name for the one of the listed applications.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteapp\n      description: Amazon Resilience Hub Delete App\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: amazon-resilience-hub.deleteapp\n      with:\n        appArn: tools.appArn\n        forceDelete: tools.forceDelete\n      inputParameters:\n      - name: appArn\n        type: string\n        description: The Amazon Resource Name (ARN) of the application.\n        required: true\n      - name: forceDelete\n        type: boolean\n        description: A boolean option to override the failure when deleting an unprotected app.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startappassessment\n      description: Amazon Resilience Hub Start App Assessment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.startappassessment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeappassessment\n      description: Amazon Resilience Hub Describe App Assessment\n      hints:\n        readOnly: false\n        destructive: false\n    \
  \    idempotent: false\n      call: amazon-resilience-hub.describeappassessment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listappassessments\n      description: Amazon Resilience Hub List App Assessments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-resilience-hub.listappassessments\n      with:\n        appArn: tools.appArn\n        assessmentName: tools.assessmentName\n        assessmentStatus: tools.assessmentStatus\n        maxResults: tools.maxResults\n        nextToken: tools.nextToken\n      inputParameters:\n      - name: appArn\n        type: string\n        description: Amazon Resource Name (ARN) of the application.\n      - name: assessmentName\n        type: string\n        description: The name for the assessment.\n      - name: assessmentStatus\n        type: array\n        description: The current status of the assessment for the resiliency policy.\n      - name: maxResults\n\
  \        type: integer\n        description: maxResults\n      - name: nextToken\n        type: string\n        description: nextToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createresiliencypolicy\n      description: Amazon Resilience Hub Create Resiliency Policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.createresiliencypolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeresiliencypolicy\n      description: Amazon Resilience Hub Describe Resiliency Policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.describeresiliencypolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listresiliencypolicies\n      description: Amazon Resilience Hub List Resiliency Policies\n      hints:\n        readOnly: true\n  \
  \      destructive: false\n        idempotent: true\n      call: amazon-resilience-hub.listresiliencypolicies\n      with:\n        policyName: tools.policyName\n        maxResults: tools.maxResults\n        nextToken: tools.nextToken\n      inputParameters:\n      - name: policyName\n        type: string\n        description: The name of the policy\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: nextToken\n        type: string\n        description: nextToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listalarmrecommendations\n      description: Amazon Resilience Hub List Alarm Recommendations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.listalarmrecommendations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsoprecommendations\n      description: Amazon Resilience Hub List SOP Recommendations\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.listsoprecommendations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtestrecommendations\n      description: Amazon Resilience Hub List Test Recommendations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.listtestrecommendations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: adddraftappversionresourcemappings\n      description: Amazon Resilience Hub Add Draft App Version Resource Mappings\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.adddraftappversionresourcemappings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publishappversion\n      description: Amazon Resilience Hub Publish App Version\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.publishappversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: importresourcestodraftappversion\n      description: Amazon Resilience Hub Import Resources to Draft App Version\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.importresourcestodraftappversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resolveappversionresources\n      description: Amazon Resilience Hub Resolve App Version Resources\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.resolveappversionresources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tagresource\n      description: Amazon Resilience Hub Tag Resource\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-resilience-hub.tagresource\n      with:\n        resourceArn: tools.resourceArn\n      inputParameters:\n      - name: resourceArn\n        type: string\n        description: The Amazon Resource Name (ARN) of the resource.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtagsforresource\n      description: Amazon Resilience Hub List Tags for Resource\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-resilience-hub.listtagsforresource\n      with:\n        resourceArn: tools.resourceArn\n      inputParameters:\n      - name: resourceArn\n        type: string\n        description: The Amazon Resource Name (ARN) of the resource.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listappversions\n      description: Amazon\
  \ Resilience Hub List App Versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-resilience-hub.listappversions\n      with:\n        appArn: tools.appArn\n        maxResults: tools.maxResults\n        nextToken: tools.nextToken\n      inputParameters:\n      - name: appArn\n        type: string\n        description: The Amazon Resource Name (ARN) of the application.\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: nextToken\n        type: string\n        description: nextToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsuggestedresiliencypolicies\n      description: Amazon Resilience Hub List Suggested Resiliency Policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amazon-resilience-hub.listsuggestedresiliencypolicies\n      with:\n        maxResults:\
  \ tools.maxResults\n        nextToken: tools.nextToken\n      inputParameters:\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: nextToken\n        type: string\n        description: nextToken\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AMAZON_RESILIENCE_HUB_TOKEN: AMAZON_RESILIENCE_HUB_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-resilience-hub/refs/heads/main/capabilities/amazon-resilience-hub-capability.yaml
tags:
- Amazon
- Resilience
- Hub
- API
tools:
- description: Amazon Resilience Hub Create App
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapp
- description: Amazon Resilience Hub Describe App
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describeapp
- description: Amazon Resilience Hub List Apps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapps
- description: Amazon Resilience Hub Delete App
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapp
- description: Amazon Resilience Hub Start App Assessment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startappassessment
- description: Amazon Resilience Hub Describe App Assessment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describeappassessment
- description: Amazon Resilience Hub List App Assessments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listappassessments
- description: Amazon Resilience Hub Create Resiliency Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createresiliencypolicy
- description: Amazon Resilience Hub Describe Resiliency Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describeresiliencypolicy
- description: Amazon Resilience Hub List Resiliency Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listresiliencypolicies
- description: Amazon Resilience Hub List Alarm Recommendations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listalarmrecommendations
- description: Amazon Resilience Hub List SOP Recommendations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listsoprecommendations
- description: Amazon Resilience Hub List Test Recommendations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listtestrecommendations
- description: Amazon Resilience Hub Add Draft App Version Resource Mappings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: adddraftappversionresourcemappings
- description: Amazon Resilience Hub Publish App Version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishappversion
- description: Amazon Resilience Hub Import Resources to Draft App Version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: importresourcestodraftappversion
- description: Amazon Resilience Hub Resolve App Version Resources
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resolveappversionresources
- description: Amazon Resilience Hub Tag Resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: tagresource
- description: Amazon Resilience Hub List Tags for Resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtagsforresource
- description: Amazon Resilience Hub List App Versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listappversions
- description: Amazon Resilience Hub List Suggested Resiliency Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsuggestedresiliencypolicies
---
