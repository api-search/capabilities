---
categories: []
consumed_apis: []
description: PingOne is a cloud-based framework for secure identity access management. The PingOne API gives developers the tools to integrate enterprise and third-party applications with the PingOne platform.
layout: capability
name: PingOne Platform API
operations:
- description: GET /environments
  method: GET
  name: getenvironments
  path: /environments
- description: POST /environments
  method: POST
  name: createenvironment
  path: /environments
- description: GET /environments/{environmentID}
  method: GET
  name: getenvironmentbyid
  path: /environments/{environmentID}
- description: PUT /environments/{environmentID}
  method: PUT
  name: replaceenvironmentbyid
  path: /environments/{environmentID}
- description: DELETE /environments/{environmentID}
  method: DELETE
  name: deleteenvironmentbyid
  path: /environments/{environmentID}
- description: GET /environments/{environmentID}/billOfMaterials
  method: GET
  name: getbillofmaterialsbyenvironmentid
  path: /environments/{environmentID}/billOfMaterials
- description: PUT /environments/{environmentID}/billOfMaterials
  method: PUT
  name: replacebillofmaterialsbyenvironmentid
  path: /environments/{environmentID}/billOfMaterials
- description: GET /environments/{environmentID}/connectorInstances
  method: GET
  name: getconnectorinstances
  path: /environments/{environmentID}/connectorInstances
- description: POST /environments/{environmentID}/connectorInstances
  method: POST
  name: createconnectorinstance
  path: /environments/{environmentID}/connectorInstances
- description: GET /environments/{environmentID}/connectorInstances/{connectorInstanceID}
  method: GET
  name: getconnectorinstancebyid
  path: /environments/{environmentID}/connectorInstances/{connectorInstanceID}
- description: POST /environments/{environmentID}/connectorInstances/{connectorInstanceID}
  method: POST
  name: createconnectorinstancebyid
  path: /environments/{environmentID}/connectorInstances/{connectorInstanceID}
- description: PUT /environments/{environmentID}/connectorInstances/{connectorInstanceID}
  method: PUT
  name: replaceconnectorinstancebyid
  path: /environments/{environmentID}/connectorInstances/{connectorInstanceID}
- description: DELETE /environments/{environmentID}/connectorInstances/{connectorInstanceID}
  method: DELETE
  name: deleteconnectorinstancebyid
  path: /environments/{environmentID}/connectorInstances/{connectorInstanceID}
- description: GET /environments/{environmentID}/connectors
  method: GET
  name: getconnectors
  path: /environments/{environmentID}/connectors
- description: GET /environments/{environmentID}/connectors/{connectorID}
  method: GET
  name: getconnectorbyid
  path: /environments/{environmentID}/connectors/{connectorID}
- description: GET /environments/{environmentID}/connectors/{connectorID}/details
  method: GET
  name: getdetailsbyconnectorid
  path: /environments/{environmentID}/connectors/{connectorID}/details
- description: GET /environments/{environmentID}/davinciApplications
  method: GET
  name: getdavinciapplications
  path: /environments/{environmentID}/davinciApplications
- description: POST /environments/{environmentID}/davinciApplications
  method: POST
  name: createdavinciapplication
  path: /environments/{environmentID}/davinciApplications
- description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}
  method: GET
  name: getdavinciapplicationbyid
  path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}
- description: PUT /environments/{environmentID}/davinciApplications/{davinciApplicationID}
  method: PUT
  name: replacedavinciapplicationbyid
  path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}
- description: DELETE /environments/{environmentID}/davinciApplications/{davinciApplicationID}
  method: DELETE
  name: deletedavinciapplicationbyid
  path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}
- description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies
  method: GET
  name: getflowpoliciesbydavinciapplicationid
  path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies
- description: POST /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies
  method: POST
  name: createflowpolicybydavinciapplicationid
  path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies
- description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}
  method: GET
  name: getflowpolicybyidusingdavinciapplicationid
  path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}
- description: PUT /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}
  method: PUT
  name: replaceflowpolicybyidusingdavinciapplicationid
  path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}
- description: DELETE /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}
  method: DELETE
  name: deleteflowpolicybyidusingdavinciapplicationid
  path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}
- description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}/events
  method: GET
  name: geteventsbydavinciapplicationidandflowpolicyid
  path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}/events
- description: POST /environments/{environmentID}/davinciApplications/{davinciApplicationID}/key
  method: POST
  name: rotatekeybydavinciapplicationid
  path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/key
- description: POST /environments/{environmentID}/davinciApplications/{davinciApplicationID}/secret
  method: POST
  name: rotatesecretbydavinciapplicationid
  path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/secret
- description: GET /environments/{environmentID}/flowPolicies/{flowPolicyID}
  method: GET
  name: getflowpolicybyid
  path: /environments/{environmentID}/flowPolicies/{flowPolicyID}
- description: GET /environments/{environmentID}/flows
  method: GET
  name: getflows
  path: /environments/{environmentID}/flows
- description: POST /environments/{environmentID}/flows
  method: POST
  name: createflow
  path: /environments/{environmentID}/flows
- description: GET /environments/{environmentID}/flows/{flowID}
  method: GET
  name: getflowbyid
  path: /environments/{environmentID}/flows/{flowID}
- description: PUT /environments/{environmentID}/flows/{flowID}
  method: PUT
  name: replaceflowbyid
  path: /environments/{environmentID}/flows/{flowID}
- description: DELETE /environments/{environmentID}/flows/{flowID}
  method: DELETE
  name: deleteflowbyid
  path: /environments/{environmentID}/flows/{flowID}
- description: POST /environments/{environmentID}/flows/{flowID}#clone+json
  method: POST
  name: cloneflowbyidasclonejson
  path: /environments/{environmentID}/flows/{flowID}#clone+json
- description: POST /environments/{environmentID}/flows/{flowID}#deploy+json
  method: POST
  name: deployflowbyidasdeployjson
  path: /environments/{environmentID}/flows/{flowID}#deploy+json
- description: POST /environments/{environmentID}/flows/{flowID}#validate+json
  method: POST
  name: validateflowbyidasvalidatejson
  path: /environments/{environmentID}/flows/{flowID}#validate+json
- description: PUT /environments/{environmentID}/flows/{flowID}/enabled
  method: PUT
  name: updateenabledbyflowid
  path: /environments/{environmentID}/flows/{flowID}/enabled
- description: GET /environments/{environmentID}/flows/{flowID}/versions
  method: GET
  name: getversionsbyflowid
  path: /environments/{environmentID}/flows/{flowID}/versions
- description: GET /environments/{environmentID}/flows/{flowID}/versions/{versionID}
  method: GET
  name: getversionbyidusingflowid
  path: /environments/{environmentID}/flows/{flowID}/versions/{versionID}
- description: DELETE /environments/{environmentID}/flows/{flowID}/versions/{versionID}
  method: DELETE
  name: deleteversionbyidusingflowid
  path: /environments/{environmentID}/flows/{flowID}/versions/{versionID}
- description: PUT /environments/{environmentID}/flows/{flowID}/versions/{versionID}/alias
  method: PUT
  name: replacealiasbyflowidandversionid
  path: /environments/{environmentID}/flows/{flowID}/versions/{versionID}/alias
- description: GET /environments/{environmentID}/flows/{flowID}/versions/{versionID}/details
  method: GET
  name: getdetailsbyflowidandversionid
  path: /environments/{environmentID}/flows/{flowID}/versions/{versionID}/details
- description: POST /environments/{environmentID}/snapshots
  method: POST
  name: createsnapshot
  path: /environments/{environmentID}/snapshots
- description: GET /environments/{environmentID}/snapshots/{snapshotID}
  method: GET
  name: getsnapshotbyid
  path: /environments/{environmentID}/snapshots/{snapshotID}
- description: GET /environments/{environmentID}/snapshots/{snapshotID}/versions
  method: GET
  name: getversionsbysnapshotid
  path: /environments/{environmentID}/snapshots/{snapshotID}/versions
- description: GET /environments/{environmentID}/snapshots/{snapshotID}/versions/{versionID}
  method: GET
  name: getversionbyidusingsnapshotid
  path: /environments/{environmentID}/snapshots/{snapshotID}/versions/{versionID}
- description: GET /environments/{environmentID}/totalIdentities
  method: GET
  name: gettotalidentities
  path: /environments/{environmentID}/totalIdentities
- description: GET /environments/{environmentID}/variables
  method: GET
  name: getvariables
  path: /environments/{environmentID}/variables
- description: POST /environments/{environmentID}/variables
  method: POST
  name: createvariable
  path: /environments/{environmentID}/variables
- description: GET /environments/{environmentID}/variables/{variableID}
  method: GET
  name: getvariablebyid
  path: /environments/{environmentID}/variables/{variableID}
- description: PUT /environments/{environmentID}/variables/{variableID}
  method: PUT
  name: replacevariablebyid
  path: /environments/{environmentID}/variables/{variableID}
- description: DELETE /environments/{environmentID}/variables/{variableID}
  method: DELETE
  name: deletevariablebyid
  path: /environments/{environmentID}/variables/{variableID}
personas: []
provider_name: Ping Identity
provider_slug: ping-identity
search_terms:
- createdavinciapplication
- post /environments/{environmentid}/flows/{flowid}#clone+json
- get /environments/{environmentid}/variables
- get /environments/{environmentid}/davinciapplications/{davinciapplicationid}/flowpolicies
- delete /environments/{environmentid}/flows/{flowid}
- deletevariablebyid
- deleteconnectorinstancebyid
- replacealiasbyflowidandversionid
- get /environments/{environmentid}/davinciapplications/{davinciapplicationid}/flowpolicies/{flowpolicyid}
- get /environments/{environmentid}/flows/{flowid}/versions/{versionid}
- deleteflowbyid
- getconnectorinstances
- getversionbyidusingsnapshotid
- replacebillofmaterialsbyenvironmentid
- deletedavinciapplicationbyid
- get /environments/{environmentid}/davinciapplications
- get /environments/{environmentid}/snapshots/{snapshotid}/versions
- get /environments/{environmentid}/totalidentities
- api
- replaceenvironmentbyid
- get /environments/{environmentid}/davinciapplications/{davinciapplicationid}/flowpolicies/{flowpolicyid}/events
- authorization
- getdetailsbyconnectorid
- put /environments/{environmentid}/billofmaterials
- delete /environments/{environmentid}/davinciapplications/{davinciapplicationid}/flowpolicies/{flowpolicyid}
- post /environments/{environmentid}/davinciapplications/{davinciapplicationid}/key
- getconnectorbyid
- put /environments/{environmentid}/flows/{flowid}/versions/{versionid}/alias
- createflowpolicybydavinciapplicationid
- createconnectorinstancebyid
- deployflowbyidasdeployjson
- validateflowbyidasvalidatejson
- put /environments/{environmentid}/davinciapplications/{davinciapplicationid}/flowpolicies/{flowpolicyid}
- getenvironments
- put /environments/{environmentid}
- deleteversionbyidusingflowid
- getversionsbyflowid
- identity
- get /environments/{environmentid}/flows/{flowid}
- getvariablebyid
- createflow
- get /environments/{environmentid}/flows
- geteventsbydavinciapplicationidandflowpolicyid
- cloneflowbyidasclonejson
- put /environments/{environmentid}/flows/{flowid}
- delete /environments/{environmentid}/connectorinstances/{connectorinstanceid}
- authentication
- deleteflowpolicybyidusingdavinciapplicationid
- replaceconnectorinstancebyid
- get /environments/{environmentid}/davinciapplications/{davinciapplicationid}
- post /environments/{environmentid}/davinciapplications/{davinciapplicationid}/secret
- post /environments
- deleteenvironmentbyid
- delete /environments/{environmentid}/flows/{flowid}/versions/{versionid}
- post /environments/{environmentid}/variables
- getdetailsbyflowidandversionid
- rotatekeybydavinciapplicationid
- get /environments/{environmentid}/connectorinstances
- get /environments/{environmentid}/billofmaterials
- createenvironment
- updateenabledbyflowid
- delete /environments/{environmentid}/davinciapplications/{davinciapplicationid}
- createsnapshot
- createconnectorinstance
- post /environments/{environmentid}/davinciapplications/{davinciapplicationid}/flowpolicies
- get /environments/{environmentid}/connectors
- createvariable
- getflows
- getenvironmentbyid
- sso
- post /environments/{environmentid}/davinciapplications
- get /environments/{environmentid}/connectorinstances/{connectorinstanceid}
- getflowpolicybyidusingdavinciapplicationid
- getconnectorinstancebyid
- getflowpoliciesbydavinciapplicationid
- post /environments/{environmentid}/flows
- get /environments/{environmentid}/variables/{variableid}
- get /environments/{environmentid}/flows/{flowid}/versions
- rotatesecretbydavinciapplicationid
- get /environments/{environmentid}
- get /environments
- getconnectors
- get /environments/{environmentid}/connectors/{connectorid}
- post /environments/{environmentid}/flows/{flowid}#validate+json
- getbillofmaterialsbyenvironmentid
- replaceflowpolicybyidusingdavinciapplicationid
- getversionsbysnapshotid
- post /environments/{environmentid}/connectorinstances
- gettotalidentities
- replacevariablebyid
- delete /environments/{environmentid}/variables/{variableid}
- getflowbyid
- get /environments/{environmentid}/flows/{flowid}/versions/{versionid}/details
- put /environments/{environmentid}/connectorinstances/{connectorinstanceid}
- get /environments/{environmentid}/flowpolicies/{flowpolicyid}
- getflowpolicybyid
- put /environments/{environmentid}/davinciapplications/{davinciapplicationid}
- get /environments/{environmentid}/snapshots/{snapshotid}/versions/{versionid}
- mfa
- get /environments/{environmentid}/snapshots/{snapshotid}
- put /environments/{environmentid}/flows/{flowid}/enabled
- post /environments/{environmentid}/connectorinstances/{connectorinstanceid}
- getvariables
- getsnapshotbyid
- getversionbyidusingflowid
- get /environments/{environmentid}/connectors/{connectorid}/details
- put /environments/{environmentid}/variables/{variableid}
- getdavinciapplications
- ping
- delete /environments/{environmentid}
- replacedavinciapplicationbyid
- post /environments/{environmentid}/snapshots
- post /environments/{environmentid}/flows/{flowid}#deploy+json
- getdavinciapplicationbyid
- replaceflowbyid
slug: ping-identity-capability
source_filename: ping-identity-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PingOne Platform API\n  description: PingOne is a cloud-based framework for secure identity access management. The PingOne API gives developers\n    the tools to integrate enterprise and third-party applications with the PingOne platform.\n  tags:\n  - Ping\n  - Identity\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ping-identity\n    baseUri: https://api.pingone.com/v1\n    description: PingOne Platform API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PING_IDENTITY_TOKEN}}'\n    resources:\n    - name: environments\n      path: /environments\n      operations:\n      - name: getenvironments\n        method: GET\n        description: GET /environments\n        inputParameters:\n        - name: expand\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        - name: order\n     \
  \     in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createenvironment\n        method: POST\n        description: POST /environments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid\n      path: /environments/{environmentID}\n      operations:\n      - name: getenvironmentbyid\n        method: GET\n        description: GET /environments/{environmentID}\n        inputParameters:\n        - name: expand\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replaceenvironmentbyid\n\
  \        method: PUT\n        description: PUT /environments/{environmentID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteenvironmentbyid\n        method: DELETE\n        description: DELETE /environments/{environmentID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-billofmaterials\n      path: /environments/{environmentID}/billOfMaterials\n      operations:\n      - name: getbillofmaterialsbyenvironmentid\n        method: GET\n        description: GET /environments/{environmentID}/billOfMaterials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacebillofmaterialsbyenvironmentid\n        method: PUT\n        description: PUT /environments/{environmentID}/billOfMaterials\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-connectorinstances\n      path: /environments/{environmentID}/connectorInstances\n      operations:\n      - name: getconnectorinstances\n        method: GET\n        description: GET /environments/{environmentID}/connectorInstances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createconnectorinstance\n        method: POST\n        description: POST /environments/{environmentID}/connectorInstances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-connectorinstances-co\n      path: /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n      operations:\n      - name: getconnectorinstancebyid\n  \
  \      method: GET\n        description: GET /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createconnectorinstancebyid\n        method: POST\n        description: POST /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replaceconnectorinstancebyid\n        method: PUT\n        description: PUT /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteconnectorinstancebyid\n        method: DELETE\n        description: DELETE /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-connectors\n      path: /environments/{environmentID}/connectors\n      operations:\n      - name: getconnectors\n        method: GET\n        description: GET /environments/{environmentID}/connectors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-connectors-connectori\n      path: /environments/{environmentID}/connectors/{connectorID}\n      operations:\n      - name: getconnectorbyid\n        method: GET\n        description: GET /environments/{environmentID}/connectors/{connectorID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-connectors-connectori\n      path: /environments/{environmentID}/connectors/{connectorID}/details\n\
  \      operations:\n      - name: getdetailsbyconnectorid\n        method: GET\n        description: GET /environments/{environmentID}/connectors/{connectorID}/details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-davinciapplications\n      path: /environments/{environmentID}/davinciApplications\n      operations:\n      - name: getdavinciapplications\n        method: GET\n        description: GET /environments/{environmentID}/davinciApplications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdavinciapplication\n        method: POST\n        description: POST /environments/{environmentID}/davinciApplications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-davinciapplications-d\n\
  \      path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}\n      operations:\n      - name: getdavinciapplicationbyid\n        method: GET\n        description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacedavinciapplicationbyid\n        method: PUT\n        description: PUT /environments/{environmentID}/davinciApplications/{davinciApplicationID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedavinciapplicationbyid\n        method: DELETE\n        description: DELETE /environments/{environmentID}/davinciApplications/{davinciApplicationID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-davinciapplications-d\n\
  \      path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies\n      operations:\n      - name: getflowpoliciesbydavinciapplicationid\n        method: GET\n        description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createflowpolicybydavinciapplicationid\n        method: POST\n        description: POST /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-davinciapplications-d\n      path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}\n      operations:\n      - name: getflowpolicybyidusingdavinciapplicationid\n\
  \        method: GET\n        description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replaceflowpolicybyidusingdavinciapplicationid\n        method: PUT\n        description: PUT /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteflowpolicybyidusingdavinciapplicationid\n        method: DELETE\n        description: DELETE /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-davinciapplications-d\n\
  \      path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}/events\n      operations:\n      - name: geteventsbydavinciapplicationidandflowpolicyid\n        method: GET\n        description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}/events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-davinciapplications-d\n      path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/key\n      operations:\n      - name: rotatekeybydavinciapplicationid\n        method: POST\n        description: POST /environments/{environmentID}/davinciApplications/{davinciApplicationID}/key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-davinciapplications-d\n\
  \      path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/secret\n      operations:\n      - name: rotatesecretbydavinciapplicationid\n        method: POST\n        description: POST /environments/{environmentID}/davinciApplications/{davinciApplicationID}/secret\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-flowpolicies-flowpoli\n      path: /environments/{environmentID}/flowPolicies/{flowPolicyID}\n      operations:\n      - name: getflowpolicybyid\n        method: GET\n        description: GET /environments/{environmentID}/flowPolicies/{flowPolicyID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-flows\n      path: /environments/{environmentID}/flows\n      operations:\n      - name: getflows\n        method: GET\n    \
  \    description: GET /environments/{environmentID}/flows\n        inputParameters:\n        - name: attributes\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createflow\n        method: POST\n        description: POST /environments/{environmentID}/flows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-flows-flowid\n      path: /environments/{environmentID}/flows/{flowID}\n      operations:\n      - name: getflowbyid\n        method: GET\n        description: GET /environments/{environmentID}/flows/{flowID}\n        inputParameters:\n        - name: attributes\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: replaceflowbyid\n        method: PUT\n        description: PUT /environments/{environmentID}/flows/{flowID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteflowbyid\n        method: DELETE\n        description: DELETE /environments/{environmentID}/flows/{flowID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-flows-flowid-clone-js\n      path: /environments/{environmentID}/flows/{flowID}#clone+json\n      operations:\n      - name: cloneflowbyidasclonejson\n        method: POST\n        description: POST /environments/{environmentID}/flows/{flowID}#clone+json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-flows-flowid-deploy-j\n      path:\
  \ /environments/{environmentID}/flows/{flowID}#deploy+json\n      operations:\n      - name: deployflowbyidasdeployjson\n        method: POST\n        description: POST /environments/{environmentID}/flows/{flowID}#deploy+json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-flows-flowid-validate\n      path: /environments/{environmentID}/flows/{flowID}#validate+json\n      operations:\n      - name: validateflowbyidasvalidatejson\n        method: POST\n        description: POST /environments/{environmentID}/flows/{flowID}#validate+json\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-flows-flowid-enabled\n      path: /environments/{environmentID}/flows/{flowID}/enabled\n      operations:\n      - name: updateenabledbyflowid\n        method: PUT\n       \
  \ description: PUT /environments/{environmentID}/flows/{flowID}/enabled\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-flows-flowid-versions\n      path: /environments/{environmentID}/flows/{flowID}/versions\n      operations:\n      - name: getversionsbyflowid\n        method: GET\n        description: GET /environments/{environmentID}/flows/{flowID}/versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-flows-flowid-versions\n      path: /environments/{environmentID}/flows/{flowID}/versions/{versionID}\n      operations:\n      - name: getversionbyidusingflowid\n        method: GET\n        description: GET /environments/{environmentID}/flows/{flowID}/versions/{versionID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: deleteversionbyidusingflowid\n        method: DELETE\n        description: DELETE /environments/{environmentID}/flows/{flowID}/versions/{versionID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-flows-flowid-versions\n      path: /environments/{environmentID}/flows/{flowID}/versions/{versionID}/alias\n      operations:\n      - name: replacealiasbyflowidandversionid\n        method: PUT\n        description: PUT /environments/{environmentID}/flows/{flowID}/versions/{versionID}/alias\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-flows-flowid-versions\n      path: /environments/{environmentID}/flows/{flowID}/versions/{versionID}/details\n      operations:\n      - name: getdetailsbyflowidandversionid\n\
  \        method: GET\n        description: GET /environments/{environmentID}/flows/{flowID}/versions/{versionID}/details\n        inputParameters:\n        - name: expand\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-snapshots\n      path: /environments/{environmentID}/snapshots\n      operations:\n      - name: createsnapshot\n        method: POST\n        description: POST /environments/{environmentID}/snapshots\n        inputParameters:\n        - name: expand\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-snapshots-snapshotid\n      path: /environments/{environmentID}/snapshots/{snapshotID}\n      operations:\n      - name: getsnapshotbyid\n        method:\
  \ GET\n        description: GET /environments/{environmentID}/snapshots/{snapshotID}\n        inputParameters:\n        - name: expand\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-snapshots-snapshotid-\n      path: /environments/{environmentID}/snapshots/{snapshotID}/versions\n      operations:\n      - name: getversionsbysnapshotid\n        method: GET\n        description: GET /environments/{environmentID}/snapshots/{snapshotID}/versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-snapshots-snapshotid-\n      path: /environments/{environmentID}/snapshots/{snapshotID}/versions/{versionID}\n      operations:\n      - name: getversionbyidusingsnapshotid\n\
  \        method: GET\n        description: GET /environments/{environmentID}/snapshots/{snapshotID}/versions/{versionID}\n        inputParameters:\n        - name: expand\n          in: query\n          type: string\n        - name: attributes\n          in: query\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-totalidentities\n      path: /environments/{environmentID}/totalIdentities\n      operations:\n      - name: gettotalidentities\n        method: GET\n        description: GET /environments/{environmentID}/totalIdentities\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: environments-environmentid-variables\n      path: /environments/{environmentID}/variables\n      operations:\n      - name: getvariables\n        method: GET\n        description: GET /environments/{environmentID}/variables\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: cursor\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvariable\n        method: POST\n        description: POST /environments/{environmentID}/variables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments-environmentid-variables-variableid\n      path: /environments/{environmentID}/variables/{variableID}\n      operations:\n      - name: getvariablebyid\n\
  \        method: GET\n        description: GET /environments/{environmentID}/variables/{variableID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacevariablebyid\n        method: PUT\n        description: PUT /environments/{environmentID}/variables/{variableID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletevariablebyid\n        method: DELETE\n        description: DELETE /environments/{environmentID}/variables/{variableID}\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ping-identity-rest\n    description: REST adapter for PingOne Platform API.\n    resources:\n    - path: /environments\n      name: getenvironments\n      operations:\n      - method:\
  \ GET\n        name: getenvironments\n        description: GET /environments\n        call: ping-identity.getenvironments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments\n      name: createenvironment\n      operations:\n      - method: POST\n        name: createenvironment\n        description: POST /environments\n        call: ping-identity.createenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}\n      name: getenvironmentbyid\n      operations:\n      - method: GET\n        name: getenvironmentbyid\n        description: GET /environments/{environmentID}\n        call: ping-identity.getenvironmentbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}\n      name: replaceenvironmentbyid\n      operations:\n      - method: PUT\n        name: replaceenvironmentbyid\n        description: PUT\
  \ /environments/{environmentID}\n        call: ping-identity.replaceenvironmentbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}\n      name: deleteenvironmentbyid\n      operations:\n      - method: DELETE\n        name: deleteenvironmentbyid\n        description: DELETE /environments/{environmentID}\n        call: ping-identity.deleteenvironmentbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/billOfMaterials\n      name: getbillofmaterialsbyenvironmentid\n      operations:\n      - method: GET\n        name: getbillofmaterialsbyenvironmentid\n        description: GET /environments/{environmentID}/billOfMaterials\n        call: ping-identity.getbillofmaterialsbyenvironmentid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/billOfMaterials\n      name: replacebillofmaterialsbyenvironmentid\n\
  \      operations:\n      - method: PUT\n        name: replacebillofmaterialsbyenvironmentid\n        description: PUT /environments/{environmentID}/billOfMaterials\n        call: ping-identity.replacebillofmaterialsbyenvironmentid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/connectorInstances\n      name: getconnectorinstances\n      operations:\n      - method: GET\n        name: getconnectorinstances\n        description: GET /environments/{environmentID}/connectorInstances\n        call: ping-identity.getconnectorinstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/connectorInstances\n      name: createconnectorinstance\n      operations:\n      - method: POST\n        name: createconnectorinstance\n        description: POST /environments/{environmentID}/connectorInstances\n        call: ping-identity.createconnectorinstance\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n      name: getconnectorinstancebyid\n      operations:\n      - method: GET\n        name: getconnectorinstancebyid\n        description: GET /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n        call: ping-identity.getconnectorinstancebyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n      name: createconnectorinstancebyid\n      operations:\n      - method: POST\n        name: createconnectorinstancebyid\n        description: POST /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n        call: ping-identity.createconnectorinstancebyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n  \
  \    name: replaceconnectorinstancebyid\n      operations:\n      - method: PUT\n        name: replaceconnectorinstancebyid\n        description: PUT /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n        call: ping-identity.replaceconnectorinstancebyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n      name: deleteconnectorinstancebyid\n      operations:\n      - method: DELETE\n        name: deleteconnectorinstancebyid\n        description: DELETE /environments/{environmentID}/connectorInstances/{connectorInstanceID}\n        call: ping-identity.deleteconnectorinstancebyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/connectors\n      name: getconnectors\n      operations:\n      - method: GET\n        name: getconnectors\n        description: GET /environments/{environmentID}/connectors\n\
  \        call: ping-identity.getconnectors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/connectors/{connectorID}\n      name: getconnectorbyid\n      operations:\n      - method: GET\n        name: getconnectorbyid\n        description: GET /environments/{environmentID}/connectors/{connectorID}\n        call: ping-identity.getconnectorbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/connectors/{connectorID}/details\n      name: getdetailsbyconnectorid\n      operations:\n      - method: GET\n        name: getdetailsbyconnectorid\n        description: GET /environments/{environmentID}/connectors/{connectorID}/details\n        call: ping-identity.getdetailsbyconnectorid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/davinciApplications\n      name: getdavinciapplications\n   \
  \   operations:\n      - method: GET\n        name: getdavinciapplications\n        description: GET /environments/{environmentID}/davinciApplications\n        call: ping-identity.getdavinciapplications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/davinciApplications\n      name: createdavinciapplication\n      operations:\n      - method: POST\n        name: createdavinciapplication\n        description: POST /environments/{environmentID}/davinciApplications\n        call: ping-identity.createdavinciapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}\n      name: getdavinciapplicationbyid\n      operations:\n      - method: GET\n        name: getdavinciapplicationbyid\n        description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}\n        call: ping-identity.getdavinciapplicationbyid\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}\n      name: replacedavinciapplicationbyid\n      operations:\n      - method: PUT\n        name: replacedavinciapplicationbyid\n        description: PUT /environments/{environmentID}/davinciApplications/{davinciApplicationID}\n        call: ping-identity.replacedavinciapplicationbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}\n      name: deletedavinciapplicationbyid\n      operations:\n      - method: DELETE\n        name: deletedavinciapplicationbyid\n        description: DELETE /environments/{environmentID}/davinciApplications/{davinciApplicationID}\n        call: ping-identity.deletedavinciapplicationbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies\n\
  \      name: getflowpoliciesbydavinciapplicationid\n      operations:\n      - method: GET\n        name: getflowpoliciesbydavinciapplicationid\n        description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies\n        call: ping-identity.getflowpoliciesbydavinciapplicationid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies\n      name: createflowpolicybydavinciapplicationid\n      operations:\n      - method: POST\n        name: createflowpolicybydavinciapplicationid\n        description: POST /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies\n        call: ping-identity.createflowpolicybydavinciapplicationid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}\n\
  \      name: getflowpolicybyidusingdavinciapplicationid\n      operations:\n      - method: GET\n        name: getflowpolicybyidusingdavinciapplicationid\n        description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}\n        call: ping-identity.getflowpolicybyidusingdavinciapplicationid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}\n      name: replaceflowpolicybyidusingdavinciapplicationid\n      operations:\n      - method: PUT\n        name: replaceflowpolicybyidusingdavinciapplicationid\n        description: PUT /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}\n        call: ping-identity.replaceflowpolicybyidusingdavinciapplicationid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}\n\
  \      name: deleteflowpolicybyidusingdavinciapplicationid\n      operations:\n      - method: DELETE\n        name: deleteflowpolicybyidusingdavinciapplicationid\n        description: DELETE /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}\n        call: ping-identity.deleteflowpolicybyidusingdavinciapplicationid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}/events\n      name: geteventsbydavinciapplicationidandflowpolicyid\n      operations:\n      - method: GET\n        name: geteventsbydavinciapplicationidandflowpolicyid\n        description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}/events\n        call: ping-identity.geteventsbydavinciapplicationidandflowpolicyid\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /environments/{environmentID}/davinciApplications/{davinciApplicationID}/key\n      name: rotatekeybydavinciapplicationid\n      operations:\n      - method: POST\n        name: rotatekeybydavinciapplicationid\n        description: POST /environments/{env\n\n# --- truncated at 32 KB (61 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/ping-identity/refs/heads/main/capabilities/ping-identity-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ping-identity/refs/heads/main/capabilities/ping-identity-capability.yaml
tags:
- Ping
- Identity
- API
tools:
- description: GET /environments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironments
- description: POST /environments
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createenvironment
- description: GET /environments/{environmentID}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironmentbyid
- description: PUT /environments/{environmentID}
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replaceenvironmentbyid
- description: DELETE /environments/{environmentID}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteenvironmentbyid
- description: GET /environments/{environmentID}/billOfMaterials
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbillofmaterialsbyenvironmentid
- description: PUT /environments/{environmentID}/billOfMaterials
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacebillofmaterialsbyenvironmentid
- description: GET /environments/{environmentID}/connectorInstances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnectorinstances
- description: POST /environments/{environmentID}/connectorInstances
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconnectorinstance
- description: GET /environments/{environmentID}/connectorInstances/{connectorInstanceID}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnectorinstancebyid
- description: POST /environments/{environmentID}/connectorInstances/{connectorInstanceID}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconnectorinstancebyid
- description: PUT /environments/{environmentID}/connectorInstances/{connectorInstanceID}
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replaceconnectorinstancebyid
- description: DELETE /environments/{environmentID}/connectorInstances/{connectorInstanceID}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteconnectorinstancebyid
- description: GET /environments/{environmentID}/connectors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnectors
- description: GET /environments/{environmentID}/connectors/{connectorID}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnectorbyid
- description: GET /environments/{environmentID}/connectors/{connectorID}/details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdetailsbyconnectorid
- description: GET /environments/{environmentID}/davinciApplications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdavinciapplications
- description: POST /environments/{environmentID}/davinciApplications
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdavinciapplication
- description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdavinciapplicationbyid
- description: PUT /environments/{environmentID}/davinciApplications/{davinciApplicationID}
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacedavinciapplicationbyid
- description: DELETE /environments/{environmentID}/davinciApplications/{davinciApplicationID}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedavinciapplicationbyid
- description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getflowpoliciesbydavinciapplicationid
- description: POST /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createflowpolicybydavinciapplicationid
- description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getflowpolicybyidusingdavinciapplicationid
- description: PUT /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replaceflowpolicybyidusingdavinciapplicationid
- description: DELETE /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteflowpolicybyidusingdavinciapplicationid
- description: GET /environments/{environmentID}/davinciApplications/{davinciApplicationID}/flowPolicies/{flowPolicyID}/events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteventsbydavinciapplicationidandflowpolicyid
- description: POST /environments/{environmentID}/davinciApplications/{davinciApplicationID}/key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rotatekeybydavinciapplicationid
- description: POST /environments/{environmentID}/davinciApplications/{davinciApplicationID}/secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rotatesecretbydavinciapplicationid
- description: GET /environments/{environmentID}/flowPolicies/{flowPolicyID}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getflowpolicybyid
- description: GET /environments/{environmentID}/flows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getflows
- description: POST /environments/{environmentID}/flows
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createflow
- description: GET /environments/{environmentID}/flows/{flowID}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getflowbyid
- description: PUT /environments/{environmentID}/flows/{flowID}
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replaceflowbyid
- description: DELETE /environments/{environmentID}/flows/{flowID}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteflowbyid
- description: POST /environments/{environmentID}/flows/{flowID}#clone+json
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cloneflowbyidasclonejson
- description: POST /environments/{environmentID}/flows/{flowID}#deploy+json
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deployflowbyidasdeployjson
- description: POST /environments/{environmentID}/flows/{flowID}#validate+json
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: validateflowbyidasvalidatejson
- description: PUT /environments/{environmentID}/flows/{flowID}/enabled
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateenabledbyflowid
- description: GET /environments/{environmentID}/flows/{flowID}/versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getversionsbyflowid
- description: GET /environments/{environmentID}/flows/{flowID}/versions/{versionID}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getversionbyidusingflowid
- description: DELETE /environments/{environmentID}/flows/{flowID}/versions/{versionID}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteversionbyidusingflowid
- description: PUT /environments/{environmentID}/flows/{flowID}/versions/{versionID}/alias
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacealiasbyflowidandversionid
- description: GET /environments/{environmentID}/flows/{flowID}/versions/{versionID}/details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdetailsbyflowidandversionid
- description: POST /environments/{environmentID}/snapshots
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsnapshot
- description: GET /environments/{environmentID}/snapshots/{snapshotID}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsnapshotbyid
- description: GET /environments/{environmentID}/snapshots/{snapshotID}/versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getversionsbysnapshotid
- description: GET /environments/{environmentID}/snapshots/{snapshotID}/versions/{versionID}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getversionbyidusingsnapshotid
- description: GET /environments/{environmentID}/totalIdentities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettotalidentities
- description: GET /environments/{environmentID}/variables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvariables
- description: POST /environments/{environmentID}/variables
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvariable
- description: GET /environments/{environmentID}/variables/{variableID}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvariablebyid
- description: PUT /environments/{environmentID}/variables/{variableID}
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacevariablebyid
- description: DELETE /environments/{environmentID}/variables/{variableID}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletevariablebyid
---
