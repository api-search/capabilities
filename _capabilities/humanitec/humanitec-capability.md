---
categories: []
consumed_apis: []
description: '# Introduction The *Humanitec API* allows you to automate and integrate Humanitec into your developer and operational workflows. The API is a REST based API. It is based around a set of concepts: * Core * External Resources * Sets and Deltas ## Authentication Almost all requests made to the Humanitec API require Authentication. See our [Developer Docs on API Authentication](https://developer.humanitec.com/platform-orchestrator/reference/api-references/#authentication) for instructions. ## Content Types The Humanitec API, unless explicitly specified, only accepts content types of `application/j'
layout: capability
name: Humanitec API
operations:
- description: Register a new Agent under an Organization.
  method: POST
  name: createagent
  path: /orgs/{orgId}/agents
- description: List all the agents in an Organization.
  method: GET
  name: listagents
  path: /orgs/{orgId}/agents
- description: Delete an Agent (and its keys) stored under an Organization.
  method: DELETE
  name: deleteagent
  path: /orgs/{orgId}/agents/{agentId}
- description: Update the description of an Agent.
  method: PATCH
  name: patchagent
  path: /orgs/{orgId}/agents/{agentId}
- description: List all the keys registered under an Agent in an Organization.
  method: GET
  name: listkeysinagent
  path: /orgs/{orgId}/agents/{agentId}/keys
- description: Register a new Key under an Agent in an Organization.
  method: POST
  name: createkey
  path: /orgs/{orgId}/agents/{agentId}/keys
- description: Delete a key registered under a Agent.
  method: DELETE
  name: deletekeyinagent
  path: /orgs/{orgId}/agents/{agentId}/keys/{fingerprint}
- description: List all Applications in an Organization.
  method: GET
  name: listapplications
  path: /orgs/{orgId}/apps
- description: Add a new Application to an Organization
  method: POST
  name: createapplication
  path: /orgs/{orgId}/apps
- description: Get an existing Application
  method: GET
  name: getapplication
  path: /orgs/{orgId}/apps/{appId}
- description: Update metadata of an existing Application
  method: PATCH
  name: patchapplication
  path: /orgs/{orgId}/apps/{appId}
- description: Delete an Application
  method: DELETE
  name: deleteapplication
  path: /orgs/{orgId}/apps/{appId}
- description: List all Environments.
  method: GET
  name: listenvironments
  path: /orgs/{orgId}/apps/{appId}/envs
- description: Add a new Environment to an Application.
  method: POST
  name: createenvironment
  path: /orgs/{orgId}/apps/{appId}/envs
- description: Get a specific Environment.
  method: GET
  name: getenvironment
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}
- description: Update a specific Environment.
  method: PATCH
  name: updateenvironment
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}
- description: Delete a specific Environment.
  method: DELETE
  name: deleteenvironment
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}
- description: List Deployments in an Environment.
  method: GET
  name: listdeployments
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}/deploys
- description: Start a new Deployment.
  method: POST
  name: createdeployment
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}/deploys
- description: Get a specific Deployment.
  method: GET
  name: getdeployment
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}/deploys/{deployId}
- description: List errors that occurred in a Deployment.
  method: GET
  name: listdeploymenterrors
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}/deploys/{deployId}/errors
- description: Rebase to a different Deployment.
  method: PUT
  name: rebaseenvironment
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}/from_deploy_id
- description: List all Environment Types
  method: GET
  name: listenvironmenttypes
  path: /orgs/{orgId}/env-types
- description: Add a new Environment Type
  method: POST
  name: createenvironmenttype
  path: /orgs/{orgId}/env-types
- description: Get an Environment Type
  method: GET
  name: getenvironmenttype
  path: /orgs/{orgId}/env-types/{envTypeId}
- description: Deletes an Environment Type
  method: DELETE
  name: deleteenvironmenttype
  path: /orgs/{orgId}/env-types/{envTypeId}
- description: Updates Environment Type
  method: PATCH
  name: updateenvironmenttype
  path: /orgs/{orgId}/env-types/{envTypeId}
- description: List all Artefacts Versions in the org.
  method: GET
  name: listartefactversionsinorg
  path: /orgs/{orgId}/artefact-versions
- description: Register a new Artefact Version with your organization.
  method: POST
  name: createartefactversion
  path: /orgs/{orgId}/artefact-versions
- description: Get an Artefacts Versions.
  method: GET
  name: getartefactversion
  path: /orgs/{orgId}/artefact-versions/{artefactVersionId}
- description: Get the spec of this Workload Artefact Version
  method: GET
  name: getworkloadartefactversionspec
  path: /orgs/{orgId}/artefact-versions/{artefactVersionId}/workload-spec
- description: Get the Humanitec module definition of this Workload Artefact Version as a deployment set
  method: GET
  name: getworkloadartefactversiondeploymentset
  path: /orgs/{orgId}/artefact-versions/{artefactVersionId}/workload-deployment-set
- description: List all Artefacts.
  method: GET
  name: listartefacts
  path: /orgs/{orgId}/artefacts
- description: Delete Artefact and all related Artefact Versions
  method: DELETE
  name: deleteartefact
  path: /orgs/{orgId}/artefacts/{artefactId}
- description: List all Artefact Versions of an Artefact.
  method: GET
  name: listartefactversions
  path: /orgs/{orgId}/artefacts/{artefactId}/versions
- description: Update Version of an Artefact.
  method: PATCH
  name: patchartefactversion
  path: /orgs/{orgId}/artefacts/{artefactId}/versions/{versionId}
- description: List all Container Images
  method: GET
  name: listdeprecatedimages
  path: /orgs/{orgId}/images
- description: Get a specific Image Object
  method: GET
  name: getdeprecatedimage
  path: /orgs/{orgId}/images/{imageId}
- description: Lists all the Builds of an Image
  method: GET
  name: listdeprecatedimagebuilds
  path: /orgs/{orgId}/images/{imageId}/builds
- description: Add a new Image Build
  method: POST
  name: createdeprecatedimagebuild
  path: /orgs/{orgId}/images/{imageId}/builds
- description: Convert a Score specification, optional overrides, and extensions into the contents for a deployment set.
  method: POST
  name: convertscoretoset
  path: /orgs/{orgId}/artefact-versions/convert-score
- description: List audit log entries by Organization
  method: GET
  name: listauditlogentries
  path: /orgs/{orgId}/audit-logs
- description: List all Automation Rules in an Environment.
  method: GET
  name: listautomationrules
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}/rules
- description: Create a new Automation Rule for an Environment.
  method: POST
  name: createautomationrule
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}/rules
- description: Get a specific Automation Rule for an Environment.
  method: GET
  name: getautomationrule
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}/rules/{ruleId}
- description: Update an existing Automation Rule for an Environment.
  method: PUT
  name: updateautomationrule
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}/rules/{ruleId}
- description: Delete Automation Rule from an Environment.
  method: DELETE
  name: deleteautomationrule
  path: /orgs/{orgId}/apps/{appId}/envs/{envId}/rules/{ruleId}
- description: List Deltas in an Application
  method: GET
  name: listdeltas
  path: /orgs/{orgId}/apps/{appId}/deltas
- description: Create a new Delta
  method: POST
  name: createdelta
  path: /orgs/{orgId}/apps/{appId}/deltas
- description: Fetch an existing Delta
  method: GET
  name: getdelta
  path: /orgs/{orgId}/apps/{appId}/deltas/{deltaId}
- description: Update an existing Delta
  method: PATCH
  name: patchdelta
  path: /orgs/{orgId}/apps/{appId}/deltas/{deltaId}
- description: Update an existing Delta
  method: PUT
  name: putdelta
  path: /orgs/{orgId}/apps/{appId}/deltas/{deltaId}
- description: Mark a Delta as "archived"
  method: PUT
  name: archivedelta
  path: /orgs/{orgId}/apps/{appId}/deltas/{deltaId}/metadata/archived
- description: Change the Environment of a Delta
  method: PUT
  name: changeenvofdelta
  path: /orgs/{orgId}/apps/{appId}/deltas/{deltaId}/metadata/env_id
- description: Change the name of a Delta
  method: PUT
  name: changenameofdelta
  path: /orgs/{orgId}/apps/{appId}/deltas/{deltaId}/metadata/name
- description: Get all Deployment Sets
  method: GET
  name: listsets
  path: /orgs/{orgId}/apps/{appId}/sets
- description: Get a Deployment Set
  method: GET
  name: getset
  path: /orgs/{orgId}/apps/{appId}/sets/{setId}
- description: Apply a Deployment Delta to a Deployment Set
  method: POST
  name: updateset
  path: /orgs/{orgId}/apps/{appId}/sets/{setId}
- description: Get Resource Inputs for the given Deployment Set
  method: GET
  name: getsetresourceinputs
  path: /orgs/{orgId}/apps/{appId}/sets/{setId}/resources
- description: Get the difference between 2 Deployment Sets
  method: GET
  name: getdiff
  path: /orgs/{orgId}/apps/{appId}/sets/{setId}/diff/{sourceSetId}
personas: []
provider_name: Humanitec
provider_slug: humanitec
search_terms:
- get resource inputs for the given deployment set
- list errors that occurred in a deployment.
- get an artefacts versions.
- rebase to a different deployment.
- list all artefacts versions in the org.
- list audit log entries by organization
- list deltas in an application
- deployments
- listauditlogentries
- create a new delta
- get a specific automation rule for an environment.
- update an existing automation rule for an environment.
- list all the agents in an organization.
- update an existing delta
- list all automation rules in an environment.
- listagents
- change the name of a delta
- list all container images
- deletes an environment type
- listartefactversions
- getdiff
- api
- get a specific environment.
- getworkloadartefactversionspec
- createdeprecatedimagebuild
- changeenvofdelta
- listenvironments
- listdeltas
- get the humanitec module definition of this workload artefact version as a deployment set
- delete an agent (and its keys) stored under an organization.
- listdeploymenterrors
- lists all the builds of an image
- update the description of an agent.
- deleteenvironment
- listartefactversionsinorg
- getenvironment
- getdeprecatedimage
- deleteagent
- register a new agent under an organization.
- listkeysinagent
- register a new key under an agent in an organization.
- get the spec of this workload artefact version
- getworkloadartefactversiondeploymentset
- deleteenvironmenttype
- list all artefact versions of an artefact.
- createkey
- patchdelta
- listdeprecatedimages
- mark a delta as "archived"
- add a new image build
- delete an application
- patchagent
- get an environment type
- listdeployments
- createenvironmenttype
- list deployments in an environment.
- update metadata of an existing application
- start a new deployment.
- platform orchestrator
- listapplications
- register a new artefact version with your organization.
- delete automation rule from an environment.
- update version of an artefact.
- createdelta
- archivedelta
- list all applications in an organization.
- updateenvironmenttype
- changenameofdelta
- createenvironment
- delete a specific environment.
- list all artefacts.
- updateautomationrule
- list all environments.
- devops
- platform engineering
- get an existing application
- convert a score specification, optional overrides, and extensions into the contents for a deployment set.
- createartefactversion
- convertscoretoset
- listartefacts
- get a specific deployment.
- patchartefactversion
- create a new automation rule for an environment.
- deleteapplication
- change the environment of a delta
- listsets
- fetch an existing delta
- createagent
- getenvironmenttype
- get a specific image object
- listenvironmenttypes
- list all environment types
- updates environment type
- updateenvironment
- rebaseenvironment
- add a new environment to an application.
- apply a deployment delta to a deployment set
- get all deployment sets
- createapplication
- add a new environment type
- getautomationrule
- humanitec
- createautomationrule
- get the difference between 2 deployment sets
- internal developer platform
- getdelta
- updateset
- update a specific environment.
- add a new application to an organization
- getartefactversion
- getsetresourceinputs
- getset
- get a deployment set
- list all the keys registered under an agent in an organization.
- createdeployment
- delete a key registered under a agent.
- getapplication
- patchapplication
- listdeprecatedimagebuilds
- deleteartefact
- getdeployment
- deleteautomationrule
- listautomationrules
- delete artefact and all related artefact versions
- deletekeyinagent
- putdelta
slug: humanitec-capability
source_filename: humanitec-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Humanitec API\n  description: '# Introduction The *Humanitec API* allows you to automate and integrate Humanitec into your developer and\n    operational workflows. The API is a REST based API. It is based around a set of concepts: * Core * External Resources\n    * Sets and Deltas ## Authentication Almost all requests made to the Humanitec API require Authentication. See our [Developer\n    Docs on API Authentication](https://developer.humanitec.com/platform-orchestrator/reference/api-references/#authentication)\n    for instructions. ## Content Types The Humanitec API, unless explicitly specified, only accepts content types of `application/j'\n  tags:\n  - Humanitec\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: humanitec\n    baseUri: https://api.humanitec.io\n    description: Humanitec API HTTP API.\n    resources:\n    - name: orgs-orgid-agents\n      path: /orgs/{orgId}/agents\n\
  \      operations:\n      - name: createagent\n        method: POST\n        description: Register a new Agent under an Organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listagents\n        method: GET\n        description: List all the agents in an Organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-agents-agentid\n      path: /orgs/{orgId}/agents/{agentId}\n      operations:\n      - name: deleteagent\n        method: DELETE\n        description: Delete an Agent (and its keys) stored under an Organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchagent\n        method: PATCH\n        description: Update the description of an Agent.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-agents-agentid-keys\n      path: /orgs/{orgId}/agents/{agentId}/keys\n      operations:\n      - name: listkeysinagent\n        method: GET\n        description: List all the keys registered under an Agent in an Organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createkey\n        method: POST\n        description: Register a new Key under an Agent in an Organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-agents-agentid-keys-fingerprint\n      path: /orgs/{orgId}/agents/{agentId}/keys/{fingerprint}\n      operations:\n      - name: deletekeyinagent\n        method: DELETE\n        description: Delete a key registered under a Agent.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps\n      path: /orgs/{orgId}/apps\n      operations:\n      - name: listapplications\n        method: GET\n        description: List all Applications in an Organization.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapplication\n        method: POST\n        description: Add a new Application to an Organization\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: orgs-orgid-apps-appid\n      path: /orgs/{orgId}/apps/{appId}\n      operations:\n      - name: getapplication\n        method: GET\n        description: Get an existing Application\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchapplication\n        method: PATCH\n        description: Update metadata of an existing Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapplication\n        method: DELETE\n        description: Delete an Application\n        inputParameters:\n \
  \       - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-envs\n      path: /orgs/{orgId}/apps/{appId}/envs\n      operations:\n      - name: listenvironments\n        method: GET\n        description: List all Environments.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: createenvironment\n        method: POST\n        description: Add a new Environment to an Application.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-envs-envid\n      path: /orgs/{orgId}/apps/{appId}/envs/{envId}\n      operations:\n      - name: getenvironment\n        method: GET\n        description: Get a specific Environment.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: appId\n          in: path\n\
  \          type: string\n          required: true\n          description: The Application ID.\n        - name: envId\n          in: path\n          type: string\n          required: true\n          description: The Environment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateenvironment\n        method: PATCH\n        description: Update a specific Environment.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The Application ID.\n        - name: envId\n          in: path\n          type: string\n          required: true\n          description: The Environment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: deleteenvironment\n        method: DELETE\n        description: Delete a specific Environment.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The Application ID.\n        - name: envId\n          in: path\n          type: string\n          required: true\n          description: The Environment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-envs-envid-deploys\n      path: /orgs/{orgId}/apps/{appId}/envs/{envId}/deploys\n      operations:\n      - name: listdeployments\n        method: GET\n        description: List Deployments in an Environment.\n        inputParameters:\n        - name: orgId\n\
  \          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The Application ID.\n        - name: envId\n          in: path\n          type: string\n          required: true\n          description: The Environment ID.\n        - name: pipelineRunId\n          in: query\n          type: string\n          description: An optional filter by the Pipeline and Pipeline Run ID separated by a comma.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdeployment\n        method: POST\n        description: Start a new Deployment.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: appId\n          in: path\n\
  \          type: string\n          required: true\n          description: The Application ID.\n        - name: envId\n          in: path\n          type: string\n          required: true\n          description: The Environment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-envs-envid-deploys-deployi\n      path: /orgs/{orgId}/apps/{appId}/envs/{envId}/deploys/{deployId}\n      operations:\n      - name: getdeployment\n        method: GET\n        description: Get a specific Deployment.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The Application ID.\n        - name: envId\n          in: path\n          type: string\n          required: true\n\
  \          description: The Environment ID.\n        - name: deployId\n          in: path\n          type: string\n          required: true\n          description: The Deployment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-envs-envid-deploys-deployi\n      path: /orgs/{orgId}/apps/{appId}/envs/{envId}/deploys/{deployId}/errors\n      operations:\n      - name: listdeploymenterrors\n        method: GET\n        description: List errors that occurred in a Deployment.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The Application ID.\n        - name: envId\n          in: path\n          type: string\n          required: true\n          description:\
  \ The Environment ID.\n        - name: deployId\n          in: path\n          type: string\n          required: true\n          description: The Deployment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-envs-envid-from-deploy-id\n      path: /orgs/{orgId}/apps/{appId}/envs/{envId}/from_deploy_id\n      operations:\n      - name: rebaseenvironment\n        method: PUT\n        description: Rebase to a different Deployment.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: The Application ID.\n        - name: envId\n          in: path\n          type: string\n          required: true\n          description: The Environment ID.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-env-types\n      path: /orgs/{orgId}/env-types\n      operations:\n      - name: listenvironmenttypes\n        method: GET\n        description: List all Environment Types\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createenvironmenttype\n        method: POST\n        description: Add a new Environment Type\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ orgs-orgid-env-types-envtypeid\n      path: /orgs/{orgId}/env-types/{envTypeId}\n      operations:\n      - name: getenvironmenttype\n        method: GET\n        description: Get an Environment Type\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: envTypeId\n          in: path\n          type: string\n          required: true\n          description: ID of the Environment Type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteenvironmenttype\n        method: DELETE\n        description: Deletes an Environment Type\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: envTypeId\n          in: path\n          type: string\n          required:\
  \ true\n          description: ID of the Environment Type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateenvironmenttype\n        method: PATCH\n        description: Updates Environment Type\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The Organization ID.\n        - name: envTypeId\n          in: path\n          type: string\n          required: true\n          description: ID of the Environment Type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-artefact-versions\n      path: /orgs/{orgId}/artefact-versions\n      operations:\n      - name: listartefactversionsinorg\n        method: GET\n        description: List all Artefacts Versions in the org.\n        inputParameters:\n        -\
  \ name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        - name: name\n          in: query\n          type: string\n          description: (Optional) Filter Artefact Versions by name.\n        - name: reference\n          in: query\n          type: string\n          description: (Optional) Filter Artefact Versions by the reference to a Version of the same Artefact. This cannot\n            be used together with `name`.\n        - name: archived\n          in: query\n          type: boolean\n          description: (Optional) Filter for non-archived Artefact Versions. If no filter is defined only non-archived Artefact\n            Versions are returned, if the filter is true both archi\n        - name: type\n          in: query\n          type: string\n          description: (Optional) Filter by artefact type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: createartefactversion\n        method: POST\n        description: Register a new Artefact Version with your organization.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        - name: vcs\n          in: query\n          type: string\n          description: (Optional) Which version control system the version comes from. Default value is \"git\". If this parameter\n            is not supplied or its value is \"git\", the provided re\n        - name: dry_run\n          in: query\n          type: boolean\n          description: Optionally validate the request but do not persist the actual artefact. If the Accept type is set to\n            \"application/x.workload-deployment-set+json\" or \"applicatio\n        - name: Accept\n          in: header\n          type: string\n          description: Indicates which content types the client\
  \ is able to understand.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-artefact-versions-artefactversionid\n      path: /orgs/{orgId}/artefact-versions/{artefactVersionId}\n      operations:\n      - name: getartefactversion\n        method: GET\n        description: Get an Artefacts Versions.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        - name: artefactVersionId\n          in: path\n          type: string\n          required: true\n          description: The Artefact Version ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-artefact-versions-artefactversionid-w\n      path: /orgs/{orgId}/artefact-versions/{artefactVersionId}/workload-spec\n      operations:\n\
  \      - name: getworkloadartefactversionspec\n        method: GET\n        description: Get the spec of this Workload Artefact Version\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        - name: artefactVersionId\n          in: path\n          type: string\n          required: true\n          description: The Artefact Version ID.\n        - name: Accept\n          in: header\n          type: string\n          description: The accepted content type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-artefact-versions-artefactversionid-w\n      path: /orgs/{orgId}/artefact-versions/{artefactVersionId}/workload-deployment-set\n      operations:\n      - name: getworkloadartefactversiondeploymentset\n        method: GET\n        description: Get the Humanitec module definition\
  \ of this Workload Artefact Version as a deployment set\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        - name: artefactVersionId\n          in: path\n          type: string\n          required: true\n          description: The Artefact Version ID.\n        - name: Accept\n          in: header\n          type: string\n          description: The accepted content type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-artefacts\n      path: /orgs/{orgId}/artefacts\n      operations:\n      - name: listartefacts\n        method: GET\n        description: List all Artefacts.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        - name: type\n        \
  \  in: query\n          type: string\n          description: (Optional) Filter Artefacts by type.\n        - name: name\n          in: query\n          type: string\n          description: (Optional) Filter Artefacts by name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-artefacts-artefactid\n      path: /orgs/{orgId}/artefacts/{artefactId}\n      operations:\n      - name: deleteartefact\n        method: DELETE\n        description: Delete Artefact and all related Artefact Versions\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        - name: artefactId\n          in: path\n          type: string\n          required: true\n          description: The Artefact ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: orgs-orgid-artefacts-artefactid-versions\n      path: /orgs/{orgId}/artefacts/{artefactId}/versions\n      operations:\n      - name: listartefactversions\n        method: GET\n        description: List all Artefact Versions of an Artefact.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        - name: artefactId\n          in: path\n          type: string\n          required: true\n          description: The Artefact ID.\n        - name: archived\n          in: query\n          type: boolean\n          description: (Optional) Filter for non-archived Artefact Versions. If no filter is defined only non-archived Artefact\n            Versions are returned, if the filter is true both archi\n        - name: reference\n          in: query\n          type: string\n          description: (Optional) Filter Artefact Versions by by name including\
  \ a version or digest.\n        - name: limit\n          in: query\n          type: integer\n          description: (Optional) Limit the number of versions returned by the endpoint.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-artefacts-artefactid-versions-version\n      path: /orgs/{orgId}/artefacts/{artefactId}/versions/{versionId}\n      operations:\n      - name: patchartefactversion\n        method: PATCH\n        description: Update Version of an Artefact.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        - name: artefactId\n          in: path\n          type: string\n          required: true\n          description: The Artefact ID.\n        - name: versionId\n          in: path\n          type: string\n          required: true\n          description: The\
  \ Version ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-images\n      path: /orgs/{orgId}/images\n      operations:\n      - name: listdeprecatedimages\n        method: GET\n        description: List all Container Images\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-images-imageid\n      path: /orgs/{orgId}/images/{imageId}\n      operations:\n      - name: getdeprecatedimage\n        method: GET\n        description: Get a specific Image Object\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n      \
  \  - name: imageId\n          in: path\n          type: string\n          required: true\n          description: The Image ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-images-imageid-builds\n      path: /orgs/{orgId}/images/{imageId}/builds\n      operations:\n      - name: listdeprecatedimagebuilds\n        method: GET\n        description: Lists all the Builds of an Image\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        - name: imageId\n          in: path\n          type: string\n          required: true\n          description: The Image ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdeprecatedimagebuild\n        method: POST\n        description: Add\
  \ a new Image Build\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        - name: imageId\n          in: path\n          type: string\n          required: true\n          description: The Image ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-artefact-versions-convert-score\n      path: /orgs/{orgId}/artefact-versions/convert-score\n      operations:\n      - name: convertscoretoset\n        method: POST\n        description: Convert a Score specification, optional overrides, and extensions into the contents for a deployment\n          set.\n        inputParameters:\n        - name: orgId\n          in: path\n          type: string\n          required: true\n          description: The organization ID.\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-audit-logs\n      path: /orgs/{orgId}/audit-logs\n      operations:\n      - name: listauditlogentries\n        method: GET\n        description: List audit log entries by Organization\n        inputParameters:\n        - name: from\n          in: query\n          type: string\n          description: Optional filter for entries created after the given time.\n        - name: to\n          in: query\n          type: string\n          description: Optional filter for entries created before the given time.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-envs-envid-rules\n      path: /orgs/{orgId}/apps/{appId}/envs/{envId}/rules\n      operations:\n      - name: listautomationrules\n        method: GET\n        description: List all Automation Rules in an Environment.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createautomationrule\n        method: POST\n        description: Create a new Automation Rule for an Environment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-envs-envid-rules-ruleid\n      path: /orgs/{orgId}/apps/{appId}/envs/{envId}/rules/{ruleId}\n      operations:\n      - name: getautomationrule\n        method: GET\n        description: Get a specific Automation Rule for an Environment.\n        inputParameters:\n        - name: ruleId\n          in: path\n          type: string\n          required: true\n          description: The Automation Rule ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateautomationrule\n        method: PUT\n        description:\
  \ Update an existing Automation Rule for an Environment.\n        inputParameters:\n        - name: ruleId\n          in: path\n          type: string\n          required: true\n          description: The Automation Rule ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteautomationrule\n        method: DELETE\n        description: Delete Automation Rule from an Environment.\n        inputParameters:\n        - name: ruleId\n          in: path\n          type: string\n          required: true\n          description: The Automation Rule ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-deltas\n      path: /orgs/{orgId}/apps/{appId}/deltas\n      operations:\n      - name: listdeltas\n        method: GET\n        description: List Deltas in an Application\n        inputParameters:\n\
  \        - name: archived\n          in: query\n          type: boolean\n          description: If true, return archived Deltas.\n        - name: env\n          in: query\n          type: string\n          description: Only return Deltas associated with the specified Environment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdelta\n        method: POST\n        description: Create a new Delta\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-deltas-deltaid\n      path: /orgs/{orgId}/apps/{appId}/deltas/{deltaId}\n      operations:\n      - name: getdelta\n        method: GET\n        description: Fetch an existing Delta\n        inputParameters:\n        - name: deltaId\n          in: path\n          type: string\n          required: true\n          description: ID of the Delta\
  \ to fetch.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchdelta\n        method: PATCH\n        description: Update an existing Delta\n        inputParameters:\n        - name: deltaId\n          in: path\n          type: string\n          required: true\n          description: ID of the Delta to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putdelta\n        method: PUT\n        description: Update an existing Delta\n        inputParameters:\n        - name: deltaId\n          in: path\n          type: string\n          required: true\n          description: ID of the Delta to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-deltas-deltaid-metadata-ar\n      path:\
  \ /orgs/{orgId}/apps/{appId}/deltas/{deltaId}/metadata/archived\n      operations:\n      - name: archivedelta\n        method: PUT\n        description: Mark a Delta as \"archived\"\n        inputParameters:\n        - name: deltaId\n          in: path\n          type: string\n          required: true\n          description: ID of the Deployment Delta.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-deltas-deltaid-metadata-en\n      path: /orgs/{orgId}/apps/{appId}/deltas/{deltaId}/metadata/env_id\n      operations:\n      - name: changeenvofdelta\n        method: PUT\n        description: Change the Environment of a Delta\n        inputParameters:\n        - name: deltaId\n          in: path\n          type: string\n          required: true\n          description: ID of the Deployment Delta.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-deltas-deltaid-metadata-na\n      path: /orgs/{orgId}/apps/{appId}/deltas/{deltaId}/metadata/name\n      operations:\n      - name: changenameofdelta\n        method: PUT\n        description: Change the name of a Delta\n        inputParameters:\n        - name: deltaId\n          in: path\n          type: string\n          required: true\n          description: ID of the Deployment Delta.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-apps-appid-sets\n      path: /orgs/{orgId}/apps/{appId}/sets\n      operations:\n      - name: listsets\n        method: GET\n        description: Get all Deployment Sets\n        outpu\n\n# --- truncated at 32 KB (88 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/humanitec/refs/heads/main/capabilities/humanitec-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/humanitec/refs/heads/main/capabilities/humanitec-capability.yaml
tags:
- Humanitec
- API
tools:
- description: Register a new Agent under an Organization.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createagent
- description: List all the agents in an Organization.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listagents
- description: Delete an Agent (and its keys) stored under an Organization.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteagent
- description: Update the description of an Agent.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchagent
- description: List all the keys registered under an Agent in an Organization.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listkeysinagent
- description: Register a new Key under an Agent in an Organization.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createkey
- description: Delete a key registered under a Agent.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletekeyinagent
- description: List all Applications in an Organization.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplications
- description: Add a new Application to an Organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplication
- description: Get an existing Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplication
- description: Update metadata of an existing Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchapplication
- description: Delete an Application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplication
- description: List all Environments.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listenvironments
- description: Add a new Environment to an Application.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createenvironment
- description: Get a specific Environment.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironment
- description: Update a specific Environment.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateenvironment
- description: Delete a specific Environment.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteenvironment
- description: List Deployments in an Environment.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeployments
- description: Start a new Deployment.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeployment
- description: Get a specific Deployment.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeployment
- description: List errors that occurred in a Deployment.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeploymenterrors
- description: Rebase to a different Deployment.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: rebaseenvironment
- description: List all Environment Types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listenvironmenttypes
- description: Add a new Environment Type
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createenvironmenttype
- description: Get an Environment Type
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironmenttype
- description: Deletes an Environment Type
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteenvironmenttype
- description: Updates Environment Type
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateenvironmenttype
- description: List all Artefacts Versions in the org.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listartefactversionsinorg
- description: Register a new Artefact Version with your organization.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createartefactversion
- description: Get an Artefacts Versions.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getartefactversion
- description: Get the spec of this Workload Artefact Version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkloadartefactversionspec
- description: Get the Humanitec module definition of this Workload Artefact Version as a deployment set
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkloadartefactversiondeploymentset
- description: List all Artefacts.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listartefacts
- description: Delete Artefact and all related Artefact Versions
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteartefact
- description: List all Artefact Versions of an Artefact.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listartefactversions
- description: Update Version of an Artefact.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchartefactversion
- description: List all Container Images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeprecatedimages
- description: Get a specific Image Object
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeprecatedimage
- description: Lists all the Builds of an Image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeprecatedimagebuilds
- description: Add a new Image Build
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeprecatedimagebuild
- description: Convert a Score specification, optional overrides, and extensions into the contents for a deployment set.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: convertscoretoset
- description: List audit log entries by Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauditlogentries
- description: List all Automation Rules in an Environment.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listautomationrules
- description: Create a new Automation Rule for an Environment.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createautomationrule
- description: Get a specific Automation Rule for an Environment.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getautomationrule
- description: Update an existing Automation Rule for an Environment.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateautomationrule
- description: Delete Automation Rule from an Environment.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteautomationrule
- description: List Deltas in an Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeltas
- description: Create a new Delta
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdelta
- description: Fetch an existing Delta
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdelta
- description: Update an existing Delta
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchdelta
- description: Update an existing Delta
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putdelta
- description: Mark a Delta as "archived"
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: archivedelta
- description: Change the Environment of a Delta
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: changeenvofdelta
- description: Change the name of a Delta
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: changenameofdelta
- description: Get all Deployment Sets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsets
- description: Get a Deployment Set
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getset
- description: Apply a Deployment Delta to a Deployment Set
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateset
- description: Get Resource Inputs for the given Deployment Set
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsetresourceinputs
- description: Get the difference between 2 Deployment Sets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdiff
---
