---
categories: []
consumed_apis: []
description: helicone-api API capability.
layout: capability
name: helicone-api
operations:
- description: DELETE /v1/api-keys/provider-key/{providerKeyId}
  method: DELETE
  name: deleteproviderkey
  path: /v1/api-keys/provider-key/{providerKeyId}
- description: GET /v1/api-keys/provider-key/{providerKeyId}
  method: GET
  name: getproviderkey
  path: /v1/api-keys/provider-key/{providerKeyId}
- description: PATCH /v1/api-keys/provider-key/{providerKeyId}
  method: PATCH
  name: updateproviderkey
  path: /v1/api-keys/provider-key/{providerKeyId}
- description: POST /v1/api-keys/provider-key
  method: POST
  name: createproviderkey
  path: /v1/api-keys/provider-key
- description: GET /v1/api-keys/provider-keys
  method: GET
  name: getproviderkeys
  path: /v1/api-keys/provider-keys
- description: GET /v1/api-keys
  method: GET
  name: getapikeys
  path: /v1/api-keys
- description: POST /v1/api-keys
  method: POST
  name: createapikey
  path: /v1/api-keys
- description: POST /v1/api-keys/proxy-key
  method: POST
  name: createproxykey
  path: /v1/api-keys/proxy-key
- description: DELETE /v1/api-keys/{apiKeyId}
  method: DELETE
  name: deleteapikey
  path: /v1/api-keys/{apiKeyId}
- description: PATCH /v1/api-keys/{apiKeyId}
  method: PATCH
  name: updateapikey
  path: /v1/api-keys/{apiKeyId}
- description: POST /v1/evaluator
  method: POST
  name: createevaluator
  path: /v1/evaluator
- description: GET /v1/evaluator/{evaluatorId}
  method: GET
  name: getevaluator
  path: /v1/evaluator/{evaluatorId}
- description: PUT /v1/evaluator/{evaluatorId}
  method: PUT
  name: updateevaluator
  path: /v1/evaluator/{evaluatorId}
- description: DELETE /v1/evaluator/{evaluatorId}
  method: DELETE
  name: deleteevaluator
  path: /v1/evaluator/{evaluatorId}
- description: POST /v1/evaluator/query
  method: POST
  name: queryevaluators
  path: /v1/evaluator/query
- description: GET /v1/evaluator/{evaluatorId}/experiments
  method: GET
  name: getexperimentsforevaluator
  path: /v1/evaluator/{evaluatorId}/experiments
- description: GET /v1/evaluator/{evaluatorId}/onlineEvaluators
  method: GET
  name: getonlineevaluators
  path: /v1/evaluator/{evaluatorId}/onlineEvaluators
- description: POST /v1/evaluator/{evaluatorId}/onlineEvaluators
  method: POST
  name: createonlineevaluator
  path: /v1/evaluator/{evaluatorId}/onlineEvaluators
- description: DELETE /v1/evaluator/{evaluatorId}/onlineEvaluators/{onlineEvaluatorId}
  method: DELETE
  name: deleteonlineevaluator
  path: /v1/evaluator/{evaluatorId}/onlineEvaluators/{onlineEvaluatorId}
- description: POST /v1/evaluator/python/test
  method: POST
  name: testpythonevaluator
  path: /v1/evaluator/python/test
- description: POST /v1/evaluator/llm/test
  method: POST
  name: testllmevaluator
  path: /v1/evaluator/llm/test
- description: POST /v1/evaluator/lastmile/test
  method: POST
  name: testlastmileevaluator
  path: /v1/evaluator/lastmile/test
- description: GET /v1/evaluator/{evaluatorId}/stats
  method: GET
  name: getevaluatorstats
  path: /v1/evaluator/{evaluatorId}/stats
- description: GET /v1/prompt-2025/id/{promptId}
  method: GET
  name: getprompt2025
  path: /v1/prompt-2025/id/{promptId}
- description: POST /v1/prompt-2025/id/{promptId}/rename
  method: POST
  name: renameprompt2025
  path: /v1/prompt-2025/id/{promptId}/rename
- description: PATCH /v1/prompt-2025/id/{promptId}/tags
  method: PATCH
  name: updateprompt2025tags
  path: /v1/prompt-2025/id/{promptId}/tags
- description: DELETE /v1/prompt-2025/{promptId}
  method: DELETE
  name: deleteprompt2025
  path: /v1/prompt-2025/{promptId}
- description: DELETE /v1/prompt-2025/{promptId}/{versionId}
  method: DELETE
  name: deleteprompt2025version
  path: /v1/prompt-2025/{promptId}/{versionId}
- description: GET /v1/prompt-2025/id/{promptId}/{versionId}/inputs
  method: GET
  name: getprompt2025inputs
  path: /v1/prompt-2025/id/{promptId}/{versionId}/inputs
- description: GET /v1/prompt-2025/tags
  method: GET
  name: getprompt2025tags
  path: /v1/prompt-2025/tags
- description: GET /v1/prompt-2025/environments
  method: GET
  name: getprompt2025environments
  path: /v1/prompt-2025/environments
- description: POST /v1/prompt-2025
  method: POST
  name: createprompt2025
  path: /v1/prompt-2025
- description: POST /v1/prompt-2025/update
  method: POST
  name: updateprompt2025
  path: /v1/prompt-2025/update
- description: POST /v1/prompt-2025/update/environment
  method: POST
  name: setpromptversionenvironment
  path: /v1/prompt-2025/update/environment
- description: POST /v1/prompt-2025/remove/environment
  method: POST
  name: removeenvironmentfromversion
  path: /v1/prompt-2025/remove/environment
- description: GET /v1/prompt-2025/count
  method: GET
  name: getprompt2025count
  path: /v1/prompt-2025/count
- description: POST /v1/prompt-2025/query
  method: POST
  name: getprompts2025
  path: /v1/prompt-2025/query
- description: POST /v1/prompt-2025/query/version
  method: POST
  name: getprompt2025version
  path: /v1/prompt-2025/query/version
- description: POST /v1/prompt-2025/query/environment-version
  method: POST
  name: getprompt2025environmentversion
  path: /v1/prompt-2025/query/environment-version
- description: POST /v1/prompt-2025/query/versions
  method: POST
  name: getprompt2025versions
  path: /v1/prompt-2025/query/versions
- description: POST /v1/prompt-2025/query/production-version
  method: POST
  name: getprompt2025productionversion
  path: /v1/prompt-2025/query/production-version
- description: POST /v1/prompt-2025/query/total-versions
  method: POST
  name: getprompt2025totalversions
  path: /v1/prompt-2025/query/total-versions
- description: Get the full prompt body (messages, tools, etc.) for a specific prompt version.
  method: GET
  name: getprompt2025versionbody
  path: /v1/prompt-2025/{promptVersionId}/prompt-body
- description: POST /v2/prompt-2025/query/version
  method: POST
  name: getprompt2025version
  path: /v2/prompt-2025/query/version
- description: POST /v2/prompt-2025/query/environment-version
  method: POST
  name: getprompt2025environmentversion
  path: /v2/prompt-2025/query/environment-version
- description: POST /v2/prompt-2025/query/production-version
  method: POST
  name: getprompt2025productionversion
  path: /v2/prompt-2025/query/production-version
- description: GET /v1/prompt/has-prompts
  method: GET
  name: hasprompts
  path: /v1/prompt/has-prompts
- description: POST /v1/prompt/query
  method: POST
  name: getprompts
  path: /v1/prompt/query
- description: POST /v1/prompt/{promptId}/query
  method: POST
  name: getprompt
  path: /v1/prompt/{promptId}/query
- description: DELETE /v1/prompt/{promptId}
  method: DELETE
  name: deleteprompt
  path: /v1/prompt/{promptId}
- description: POST /v1/prompt/create
  method: POST
  name: createprompt
  path: /v1/prompt/create
- description: PATCH /v1/prompt/{promptId}/user-defined-id
  method: PATCH
  name: updatepromptuserdefinedid
  path: /v1/prompt/{promptId}/user-defined-id
- description: POST /v1/prompt/version/{promptVersionId}/edit-label
  method: POST
  name: editpromptversionlabel
  path: /v1/prompt/version/{promptVersionId}/edit-label
- description: POST /v1/prompt/version/{promptVersionId}/edit-template
  method: POST
  name: editpromptversiontemplate
  path: /v1/prompt/version/{promptVersionId}/edit-template
- description: POST /v1/prompt/version/{promptVersionId}/subversion-from-ui
  method: POST
  name: createsubversionfromui
  path: /v1/prompt/version/{promptVersionId}/subversion-from-ui
- description: POST /v1/prompt/version/{promptVersionId}/subversion
  method: POST
  name: createsubversion
  path: /v1/prompt/version/{promptVersionId}/subversion
- description: POST /v1/prompt/version/{promptVersionId}/promote
  method: POST
  name: promotepromptversiontoproduction
  path: /v1/prompt/version/{promptVersionId}/promote
- description: POST /v1/prompt/version/{promptVersionId}/inputs/query
  method: POST
  name: getinputs
  path: /v1/prompt/version/{promptVersionId}/inputs/query
- description: GET /v1/prompt/{promptId}/experiments
  method: GET
  name: getpromptexperiments
  path: /v1/prompt/{promptId}/experiments
- description: POST /v1/prompt/{promptId}/versions/query
  method: POST
  name: getpromptversions
  path: /v1/prompt/{promptId}/versions/query
personas: []
provider_name: Helicone
provider_slug: helicone
search_terms:
- deleteevaluator
- patch /v1/prompt-2025/id/{promptid}/tags
- post /v1/prompt-2025/query/versions
- post /v1/prompt-2025/query/version
- updatepromptuserdefinedid
- delete /v1/prompt-2025/{promptid}/{versionid}
- get /v1/evaluator/{evaluatorid}/experiments
- getexperimentsforevaluator
- getonlineevaluators
- get /v1/evaluator/{evaluatorid}/onlineevaluators
- api
- deleteproviderkey
- post /v1/prompt/version/{promptversionid}/subversion
- getprompt2025inputs
- llm routing
- createproviderkey
- deleteprompt2025version
- getprompt2025version
- post /v1/api-keys/provider-key
- get /v1/prompt-2025/id/{promptid}
- post /v1/evaluator/query
- createsubversionfromui
- get /v1/prompt/has-prompts
- getprompt2025environmentversion
- post /v1/prompt/version/{promptversionid}/edit-template
- getpromptexperiments
- deleteprompt
- get /v1/evaluator/{evaluatorid}
- post /v1/prompt/query
- editpromptversionlabel
- delete /v1/evaluator/{evaluatorid}
- post /v1/api-keys
- getprompt2025
- get /v1/api-keys/provider-key/{providerkeyid}
- post /v1/prompt-2025/query/total-versions
- get /v1/prompt/{promptid}/experiments
- getpromptversions
- createevaluator
- editpromptversiontemplate
- getprompt2025environments
- setpromptversionenvironment
- post /v1/evaluator/llm/test
- getprompt2025versions
- post /v1/prompt-2025/remove/environment
- queryevaluators
- getevaluatorstats
- post /v2/prompt-2025/query/environment-version
- deleteprompt2025
- post /v1/prompt/create
- get /v1/api-keys
- delete /v1/prompt/{promptid}
- post /v2/prompt-2025/query/production-version
- prompt management
- post /v1/prompt-2025/id/{promptid}/rename
- updateapikey
- createproxykey
- patch /v1/prompt/{promptid}/user-defined-id
- post /v2/prompt-2025/query/version
- get /v1/prompt-2025/count
- createprompt
- getproviderkey
- renameprompt2025
- get /v1/prompt-2025/environments
- updateevaluator
- createsubversion
- getproviderkeys
- removeenvironmentfromversion
- getprompt2025versionbody
- delete /v1/prompt-2025/{promptid}
- getinputs
- delete /v1/api-keys/{apikeyid}
- getprompt2025productionversion
- post /v1/evaluator/lastmile/test
- post /v1/evaluator
- get the full prompt body (messages, tools, etc.) for a specific prompt version.
- ai monitoring
- getprompts2025
- testllmevaluator
- getprompts
- patch /v1/api-keys/provider-key/{providerkeyid}
- post /v1/prompt/version/{promptversionid}/inputs/query
- deleteapikey
- post /v1/prompt-2025
- post /v1/prompt-2025/query/production-version
- getevaluator
- post /v1/api-keys/proxy-key
- createonlineevaluator
- post /v1/prompt-2025/update
- updateprompt2025
- getprompt
- get /v1/prompt-2025/tags
- post /v1/prompt-2025/query/environment-version
- getprompt2025tags
- post /v1/evaluator/{evaluatorid}/onlineevaluators
- get /v1/prompt-2025/id/{promptid}/{versionid}/inputs
- post /v1/prompt-2025/query
- post /v1/prompt/version/{promptversionid}/promote
- testpythonevaluator
- deleteonlineevaluator
- put /v1/evaluator/{evaluatorid}
- createapikey
- post /v1/prompt/version/{promptversionid}/subversion-from-ui
- getprompt2025count
- helicone
- promotepromptversiontoproduction
- patch /v1/api-keys/{apikeyid}
- testlastmileevaluator
- delete /v1/evaluator/{evaluatorid}/onlineevaluators/{onlineevaluatorid}
- updateprompt2025tags
- post /v1/prompt/{promptid}/versions/query
- hasprompts
- post /v1/evaluator/python/test
- getprompt2025totalversions
- gateways
- llm observability
- createprompt2025
- get /v1/api-keys/provider-keys
- post /v1/prompt/version/{promptversionid}/edit-label
- get /v1/evaluator/{evaluatorid}/stats
- post /v1/prompt-2025/update/environment
- ai gateways
- delete /v1/api-keys/provider-key/{providerkeyid}
- getapikeys
- post /v1/prompt/{promptid}/query
- updateproviderkey
slug: helicone-capability
source_filename: helicone-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: helicone-api\n  description: helicone-api API capability.\n  tags:\n  - Helicone\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: helicone\n    baseUri: https://api.helicone.ai\n    description: helicone-api HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{HELICONE_TOKEN}}'\n    resources:\n    - name: v1-api-keys-provider-key-providerkeyid\n      path: /v1/api-keys/provider-key/{providerKeyId}\n      operations:\n      - name: deleteproviderkey\n        method: DELETE\n        description: DELETE /v1/api-keys/provider-key/{providerKeyId}\n        inputParameters:\n        - name: providerKeyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getproviderkey\n\
  \        method: GET\n        description: GET /v1/api-keys/provider-key/{providerKeyId}\n        inputParameters:\n        - name: providerKeyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproviderkey\n        method: PATCH\n        description: PATCH /v1/api-keys/provider-key/{providerKeyId}\n        inputParameters:\n        - name: providerKeyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-api-keys-provider-key\n      path: /v1/api-keys/provider-key\n      operations:\n      - name: createproviderkey\n        method: POST\n        description: POST /v1/api-keys/provider-key\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: v1-api-keys-provider-keys\n      path: /v1/api-keys/provider-keys\n      operations:\n      - name: getproviderkeys\n        method: GET\n        description: GET /v1/api-keys/provider-keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-api-keys\n      path: /v1/api-keys\n      operations:\n      - name: getapikeys\n        method: GET\n        description: GET /v1/api-keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapikey\n        method: POST\n        description: POST /v1/api-keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-api-keys-proxy-key\n      path: /v1/api-keys/proxy-key\n      operations:\n      - name: createproxykey\n\
  \        method: POST\n        description: POST /v1/api-keys/proxy-key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-api-keys-apikeyid\n      path: /v1/api-keys/{apiKeyId}\n      operations:\n      - name: deleteapikey\n        method: DELETE\n        description: DELETE /v1/api-keys/{apiKeyId}\n        inputParameters:\n        - name: apiKeyId\n          in: path\n          type: number\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapikey\n        method: PATCH\n        description: PATCH /v1/api-keys/{apiKeyId}\n        inputParameters:\n        - name: apiKeyId\n          in: path\n          type: number\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: v1-evaluator\n      path: /v1/evaluator\n      operations:\n      - name: createevaluator\n        method: POST\n        description: POST /v1/evaluator\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-evaluator-evaluatorid\n      path: /v1/evaluator/{evaluatorId}\n      operations:\n      - name: getevaluator\n        method: GET\n        description: GET /v1/evaluator/{evaluatorId}\n        inputParameters:\n        - name: evaluatorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateevaluator\n        method: PUT\n        description: PUT /v1/evaluator/{evaluatorId}\n        inputParameters:\n        - name: evaluatorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteevaluator\n        method: DELETE\n        description: DELETE /v1/evaluator/{evaluatorId}\n        inputParameters:\n        - name: evaluatorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-evaluator-query\n      path: /v1/evaluator/query\n      operations:\n      - name: queryevaluators\n        method: POST\n        description: POST /v1/evaluator/query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-evaluator-evaluatorid-experiments\n      path: /v1/evaluator/{evaluatorId}/experiments\n      operations:\n      - name: getexperimentsforevaluator\n        method: GET\n        description: GET /v1/evaluator/{evaluatorId}/experiments\n\
  \        inputParameters:\n        - name: evaluatorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-evaluator-evaluatorid-onlineevaluators\n      path: /v1/evaluator/{evaluatorId}/onlineEvaluators\n      operations:\n      - name: getonlineevaluators\n        method: GET\n        description: GET /v1/evaluator/{evaluatorId}/onlineEvaluators\n        inputParameters:\n        - name: evaluatorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createonlineevaluator\n        method: POST\n        description: POST /v1/evaluator/{evaluatorId}/onlineEvaluators\n        inputParameters:\n        - name: evaluatorId\n          in: path\n          type: string\n     \
  \     required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-evaluator-evaluatorid-onlineevaluators-online\n      path: /v1/evaluator/{evaluatorId}/onlineEvaluators/{onlineEvaluatorId}\n      operations:\n      - name: deleteonlineevaluator\n        method: DELETE\n        description: DELETE /v1/evaluator/{evaluatorId}/onlineEvaluators/{onlineEvaluatorId}\n        inputParameters:\n        - name: evaluatorId\n          in: path\n          type: string\n          required: true\n        - name: onlineEvaluatorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-evaluator-python-test\n      path: /v1/evaluator/python/test\n      operations:\n      - name: testpythonevaluator\n        method: POST\n        description: POST /v1/evaluator/python/test\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-evaluator-llm-test\n      path: /v1/evaluator/llm/test\n      operations:\n      - name: testllmevaluator\n        method: POST\n        description: POST /v1/evaluator/llm/test\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-evaluator-lastmile-test\n      path: /v1/evaluator/lastmile/test\n      operations:\n      - name: testlastmileevaluator\n        method: POST\n        description: POST /v1/evaluator/lastmile/test\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-evaluator-evaluatorid-stats\n      path: /v1/evaluator/{evaluatorId}/stats\n      operations:\n      - name: getevaluatorstats\n        method: GET\n        description: GET /v1/evaluator/{evaluatorId}/stats\n\
  \        inputParameters:\n        - name: evaluatorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-id-promptid\n      path: /v1/prompt-2025/id/{promptId}\n      operations:\n      - name: getprompt2025\n        method: GET\n        description: GET /v1/prompt-2025/id/{promptId}\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-id-promptid-rename\n      path: /v1/prompt-2025/id/{promptId}/rename\n      operations:\n      - name: renameprompt2025\n        method: POST\n        description: POST /v1/prompt-2025/id/{promptId}/rename\n        inputParameters:\n        - name: promptId\n   \
  \       in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-id-promptid-tags\n      path: /v1/prompt-2025/id/{promptId}/tags\n      operations:\n      - name: updateprompt2025tags\n        method: PATCH\n        description: PATCH /v1/prompt-2025/id/{promptId}/tags\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-promptid\n      path: /v1/prompt-2025/{promptId}\n      operations:\n      - name: deleteprompt2025\n        method: DELETE\n        description: DELETE /v1/prompt-2025/{promptId}\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-promptid-versionid\n      path: /v1/prompt-2025/{promptId}/{versionId}\n      operations:\n      - name: deleteprompt2025version\n        method: DELETE\n        description: DELETE /v1/prompt-2025/{promptId}/{versionId}\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        - name: versionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-id-promptid-versionid-inputs\n      path: /v1/prompt-2025/id/{promptId}/{versionId}/inputs\n      operations:\n      - name: getprompt2025inputs\n        method: GET\n        description: GET /v1/prompt-2025/id/{promptId}/{versionId}/inputs\n\
  \        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        - name: versionId\n          in: path\n          type: string\n          required: true\n        - name: requestId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-tags\n      path: /v1/prompt-2025/tags\n      operations:\n      - name: getprompt2025tags\n        method: GET\n        description: GET /v1/prompt-2025/tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-environments\n      path: /v1/prompt-2025/environments\n      operations:\n      - name: getprompt2025environments\n        method: GET\n        description: GET /v1/prompt-2025/environments\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025\n      path: /v1/prompt-2025\n      operations:\n      - name: createprompt2025\n        method: POST\n        description: POST /v1/prompt-2025\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-update\n      path: /v1/prompt-2025/update\n      operations:\n      - name: updateprompt2025\n        method: POST\n        description: POST /v1/prompt-2025/update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-update-environment\n      path: /v1/prompt-2025/update/environment\n      operations:\n      - name: setpromptversionenvironment\n        method: POST\n        description: POST /v1/prompt-2025/update/environment\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-remove-environment\n      path: /v1/prompt-2025/remove/environment\n      operations:\n      - name: removeenvironmentfromversion\n        method: POST\n        description: POST /v1/prompt-2025/remove/environment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-count\n      path: /v1/prompt-2025/count\n      operations:\n      - name: getprompt2025count\n        method: GET\n        description: GET /v1/prompt-2025/count\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-query\n      path: /v1/prompt-2025/query\n      operations:\n      - name: getprompts2025\n        method: POST\n        description: POST /v1/prompt-2025/query\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-query-version\n      path: /v1/prompt-2025/query/version\n      operations:\n      - name: getprompt2025version\n        method: POST\n        description: POST /v1/prompt-2025/query/version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-query-environment-version\n      path: /v1/prompt-2025/query/environment-version\n      operations:\n      - name: getprompt2025environmentversion\n        method: POST\n        description: POST /v1/prompt-2025/query/environment-version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-query-versions\n      path: /v1/prompt-2025/query/versions\n      operations:\n      - name: getprompt2025versions\n        method: POST\n\
  \        description: POST /v1/prompt-2025/query/versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-query-production-version\n      path: /v1/prompt-2025/query/production-version\n      operations:\n      - name: getprompt2025productionversion\n        method: POST\n        description: POST /v1/prompt-2025/query/production-version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-query-total-versions\n      path: /v1/prompt-2025/query/total-versions\n      operations:\n      - name: getprompt2025totalversions\n        method: POST\n        description: POST /v1/prompt-2025/query/total-versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-2025-promptversionid-prompt-body\n\
  \      path: /v1/prompt-2025/{promptVersionId}/prompt-body\n      operations:\n      - name: getprompt2025versionbody\n        method: GET\n        description: Get the full prompt body (messages, tools, etc.) for a specific prompt version.\n        inputParameters:\n        - name: promptVersionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-prompt-2025-query-version\n      path: /v2/prompt-2025/query/version\n      operations:\n      - name: getprompt2025version\n        method: POST\n        description: POST /v2/prompt-2025/query/version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-prompt-2025-query-environment-version\n      path: /v2/prompt-2025/query/environment-version\n      operations:\n      - name: getprompt2025environmentversion\n\
  \        method: POST\n        description: POST /v2/prompt-2025/query/environment-version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-prompt-2025-query-production-version\n      path: /v2/prompt-2025/query/production-version\n      operations:\n      - name: getprompt2025productionversion\n        method: POST\n        description: POST /v2/prompt-2025/query/production-version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-has-prompts\n      path: /v1/prompt/has-prompts\n      operations:\n      - name: hasprompts\n        method: GET\n        description: GET /v1/prompt/has-prompts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-query\n      path: /v1/prompt/query\n      operations:\n\
  \      - name: getprompts\n        method: POST\n        description: POST /v1/prompt/query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-promptid-query\n      path: /v1/prompt/{promptId}/query\n      operations:\n      - name: getprompt\n        method: POST\n        description: POST /v1/prompt/{promptId}/query\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-promptid\n      path: /v1/prompt/{promptId}\n      operations:\n      - name: deleteprompt\n        method: DELETE\n        description: DELETE /v1/prompt/{promptId}\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-create\n      path: /v1/prompt/create\n      operations:\n      - name: createprompt\n        method: POST\n        description: POST /v1/prompt/create\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-promptid-user-defined-id\n      path: /v1/prompt/{promptId}/user-defined-id\n      operations:\n      - name: updatepromptuserdefinedid\n        method: PATCH\n        description: PATCH /v1/prompt/{promptId}/user-defined-id\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-version-promptversionid-edit-label\n      path: /v1/prompt/version/{promptVersionId}/edit-label\n\
  \      operations:\n      - name: editpromptversionlabel\n        method: POST\n        description: POST /v1/prompt/version/{promptVersionId}/edit-label\n        inputParameters:\n        - name: promptVersionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-version-promptversionid-edit-template\n      path: /v1/prompt/version/{promptVersionId}/edit-template\n      operations:\n      - name: editpromptversiontemplate\n        method: POST\n        description: POST /v1/prompt/version/{promptVersionId}/edit-template\n        inputParameters:\n        - name: promptVersionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-version-promptversionid-subversion-fro\n\
  \      path: /v1/prompt/version/{promptVersionId}/subversion-from-ui\n      operations:\n      - name: createsubversionfromui\n        method: POST\n        description: POST /v1/prompt/version/{promptVersionId}/subversion-from-ui\n        inputParameters:\n        - name: promptVersionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-version-promptversionid-subversion\n      path: /v1/prompt/version/{promptVersionId}/subversion\n      operations:\n      - name: createsubversion\n        method: POST\n        description: POST /v1/prompt/version/{promptVersionId}/subversion\n        inputParameters:\n        - name: promptVersionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: v1-prompt-version-promptversionid-promote\n      path: /v1/prompt/version/{promptVersionId}/promote\n      operations:\n      - name: promotepromptversiontoproduction\n        method: POST\n        description: POST /v1/prompt/version/{promptVersionId}/promote\n        inputParameters:\n        - name: promptVersionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-version-promptversionid-inputs-query\n      path: /v1/prompt/version/{promptVersionId}/inputs/query\n      operations:\n      - name: getinputs\n        method: POST\n        description: POST /v1/prompt/version/{promptVersionId}/inputs/query\n        inputParameters:\n        - name: promptVersionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-promptid-experiments\n      path: /v1/prompt/{promptId}/experiments\n      operations:\n      - name: getpromptexperiments\n        method: GET\n        description: GET /v1/prompt/{promptId}/experiments\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-prompt-promptid-versions-query\n      path: /v1/prompt/{promptId}/versions/query\n      operations:\n      - name: getpromptversions\n        method: POST\n        description: POST /v1/prompt/{promptId}/versions/query\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: helicone-rest\n    description: REST adapter for helicone-api.\n    resources:\n    - path: /v1/api-keys/provider-key/{providerKeyId}\n      name: deleteproviderkey\n      operations:\n      - method: DELETE\n        name: deleteproviderkey\n        description: DELETE /v1/api-keys/provider-key/{providerKeyId}\n        call: helicone.deleteproviderkey\n        with:\n          providerKeyId: rest.providerKeyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys/provider-key/{providerKeyId}\n      name: getproviderkey\n      operations:\n      - method: GET\n        name: getproviderkey\n        description: GET /v1/api-keys/provider-key/{providerKeyId}\n        call: helicone.getproviderkey\n        with:\n          providerKeyId: rest.providerKeyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys/provider-key/{providerKeyId}\n\
  \      name: updateproviderkey\n      operations:\n      - method: PATCH\n        name: updateproviderkey\n        description: PATCH /v1/api-keys/provider-key/{providerKeyId}\n        call: helicone.updateproviderkey\n        with:\n          providerKeyId: rest.providerKeyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys/provider-key\n      name: createproviderkey\n      operations:\n      - method: POST\n        name: createproviderkey\n        description: POST /v1/api-keys/provider-key\n        call: helicone.createproviderkey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys/provider-keys\n      name: getproviderkeys\n      operations:\n      - method: GET\n        name: getproviderkeys\n        description: GET /v1/api-keys/provider-keys\n        call: helicone.getproviderkeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys\n\
  \      name: getapikeys\n      operations:\n      - method: GET\n        name: getapikeys\n        description: GET /v1/api-keys\n        call: helicone.getapikeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys\n      name: createapikey\n      operations:\n      - method: POST\n        name: createapikey\n        description: POST /v1/api-keys\n        call: helicone.createapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys/proxy-key\n      name: createproxykey\n      operations:\n      - method: POST\n        name: createproxykey\n        description: POST /v1/api-keys/proxy-key\n        call: helicone.createproxykey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys/{apiKeyId}\n      name: deleteapikey\n      operations:\n      - method: DELETE\n        name: deleteapikey\n        description: DELETE /v1/api-keys/{apiKeyId}\n   \
  \     call: helicone.deleteapikey\n        with:\n          apiKeyId: rest.apiKeyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys/{apiKeyId}\n      name: updateapikey\n      operations:\n      - method: PATCH\n        name: updateapikey\n        description: PATCH /v1/api-keys/{apiKeyId}\n        call: helicone.updateapikey\n        with:\n          apiKeyId: rest.apiKeyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluator\n      name: createevaluator\n      operations:\n      - method: POST\n        name: createevaluator\n        description: POST /v1/evaluator\n        call: helicone.createevaluator\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluator/{evaluatorId}\n      name: getevaluator\n      operations:\n      - method: GET\n        name: getevaluator\n        description: GET /v1/evaluator/{evaluatorId}\n        call: helicone.getevaluator\n\
  \        with:\n          evaluatorId: rest.evaluatorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluator/{evaluatorId}\n      name: updateevaluator\n      operations:\n      - method: PUT\n        name: updateevaluator\n        description: PUT /v1/evaluator/{evaluatorId}\n        call: helicone.updateevaluator\n        with:\n          evaluatorId: rest.evaluatorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluator/{evaluatorId}\n      name: deleteevaluator\n      operations:\n      - method: DELETE\n        name: deleteevaluator\n        description: DELETE /v1/evaluator/{evaluatorId}\n        call: helicone.deleteevaluator\n        with:\n          evaluatorId: rest.evaluatorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluator/query\n      name: queryevaluators\n      operations:\n      - method: POST\n        name: queryevaluators\n\
  \        description: POST /v1/evaluator/query\n        call: helicone.queryevaluators\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluator/{evaluatorId}/experiments\n      name: getexperimentsforevaluator\n      operations:\n      - method: GET\n        name: getexperimentsforevaluator\n        description: GET /v1/evaluator/{evaluatorId}/experiments\n        call: helicone.getexperimentsforevaluator\n        with:\n          evaluatorId: rest.evaluatorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluator/{evaluatorId}/onlineEvaluators\n      name: getonlineevaluators\n      operations:\n      - method: GET\n        name: getonlineevaluators\n        description: GET /v1/evaluator/{evaluatorId}/onlineEvaluators\n        call: helicone.getonlineevaluators\n        with:\n          evaluatorId: rest.evaluatorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/evaluator/{evaluatorId}/onlineEvaluators\n      name: createonlineevaluator\n      operations:\n      - method: POST\n        name: createonlineevaluator\n        description: POST /v1/evaluator/{evaluatorId}/onlineEvaluators\n        call: helicone.createonlineevaluator\n        with:\n          evaluatorId: rest.evaluatorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluator/{evaluatorId}/onlineEvaluators/{onlineEvaluatorId}\n      name: deleteonlineevaluator\n      operations:\n      - method: DELETE\n        name: deleteonlineevaluator\n        description: DELETE /v1/evaluator/{evaluatorId}/onlineEvaluators/{onlineEvaluatorId}\n        call: helicone.deleteonlineevaluator\n        with:\n          evaluatorId: rest.evaluatorId\n          onlineEvaluatorId: rest.onlineEvaluatorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluator/python/test\n      name: testpythonevaluator\n\
  \      operations:\n      - method: POST\n        name: testpythonevaluator\n        description: POST /v1/evaluator/python/test\n        call: helicone.testpythonevaluator\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluator/llm/test\n      name: testllmevaluator\n      operations:\n      - method: POST\n        name: testllmevaluator\n        description: POST /v1/evaluator/llm/test\n        call: helicone.testllmevaluator\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluator/lastmile/test\n      name: testlastmileevaluator\n      operations:\n      - method: POST\n        name: testlastmileevaluator\n        description: POST /v1/evaluator/lastmile/test\n        call: helicone.testlastmileevaluator\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluator/{evaluatorId}/stats\n      name: getevaluatorstats\n      operations:\n      - method: GET\n\
  \        name: getevaluatorstats\n        description: GET /v1/evaluator/{evaluatorId}/stats\n        call: helicone.getevaluatorstats\n        with:\n          evaluatorId: rest.evaluatorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/prompt-2025/id/{promptId}\n      name: getprompt2025\n      operations:\n      - method: GET\n        name: getprompt2025\n        description: GET /v1/prompt-2025/id/{promptId}\n        call: helicone.getprompt2025\n        with:\n          promptId: rest.promptId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/prompt-2025/id/{promptId}/rename\n      name: renameprompt2025\n      operations:\n      - me\n\n# --- truncated at 32 KB (67 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/helicone/refs/heads/main/capabilities/helicone-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/helicone/refs/heads/main/capabilities/helicone-capability.yaml
tags:
- Helicone
- API
tools:
- description: DELETE /v1/api-keys/provider-key/{providerKeyId}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproviderkey
- description: GET /v1/api-keys/provider-key/{providerKeyId}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproviderkey
- description: PATCH /v1/api-keys/provider-key/{providerKeyId}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateproviderkey
- description: POST /v1/api-keys/provider-key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproviderkey
- description: GET /v1/api-keys/provider-keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproviderkeys
- description: GET /v1/api-keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapikeys
- description: POST /v1/api-keys
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapikey
- description: POST /v1/api-keys/proxy-key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproxykey
- description: DELETE /v1/api-keys/{apiKeyId}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapikey
- description: PATCH /v1/api-keys/{apiKeyId}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapikey
- description: POST /v1/evaluator
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createevaluator
- description: GET /v1/evaluator/{evaluatorId}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevaluator
- description: PUT /v1/evaluator/{evaluatorId}
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateevaluator
- description: DELETE /v1/evaluator/{evaluatorId}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteevaluator
- description: POST /v1/evaluator/query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: queryevaluators
- description: GET /v1/evaluator/{evaluatorId}/experiments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexperimentsforevaluator
- description: GET /v1/evaluator/{evaluatorId}/onlineEvaluators
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getonlineevaluators
- description: POST /v1/evaluator/{evaluatorId}/onlineEvaluators
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createonlineevaluator
- description: DELETE /v1/evaluator/{evaluatorId}/onlineEvaluators/{onlineEvaluatorId}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteonlineevaluator
- description: POST /v1/evaluator/python/test
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: testpythonevaluator
- description: POST /v1/evaluator/llm/test
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: testllmevaluator
- description: POST /v1/evaluator/lastmile/test
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: testlastmileevaluator
- description: GET /v1/evaluator/{evaluatorId}/stats
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevaluatorstats
- description: GET /v1/prompt-2025/id/{promptId}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprompt2025
- description: POST /v1/prompt-2025/id/{promptId}/rename
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renameprompt2025
- description: PATCH /v1/prompt-2025/id/{promptId}/tags
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateprompt2025tags
- description: DELETE /v1/prompt-2025/{promptId}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprompt2025
- description: DELETE /v1/prompt-2025/{promptId}/{versionId}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprompt2025version
- description: GET /v1/prompt-2025/id/{promptId}/{versionId}/inputs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprompt2025inputs
- description: GET /v1/prompt-2025/tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprompt2025tags
- description: GET /v1/prompt-2025/environments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprompt2025environments
- description: POST /v1/prompt-2025
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprompt2025
- description: POST /v1/prompt-2025/update
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateprompt2025
- description: POST /v1/prompt-2025/update/environment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setpromptversionenvironment
- description: POST /v1/prompt-2025/remove/environment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: removeenvironmentfromversion
- description: GET /v1/prompt-2025/count
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprompt2025count
- description: POST /v1/prompt-2025/query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getprompts2025
- description: POST /v1/prompt-2025/query/version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getprompt2025version
- description: POST /v1/prompt-2025/query/environment-version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getprompt2025environmentversion
- description: POST /v1/prompt-2025/query/versions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getprompt2025versions
- description: POST /v1/prompt-2025/query/production-version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getprompt2025productionversion
- description: POST /v1/prompt-2025/query/total-versions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getprompt2025totalversions
- description: Get the full prompt body (messages, tools, etc.) for a specific prompt version.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprompt2025versionbody
- description: POST /v2/prompt-2025/query/version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getprompt2025version
- description: POST /v2/prompt-2025/query/environment-version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getprompt2025environmentversion
- description: POST /v2/prompt-2025/query/production-version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getprompt2025productionversion
- description: GET /v1/prompt/has-prompts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: hasprompts
- description: POST /v1/prompt/query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getprompts
- description: POST /v1/prompt/{promptId}/query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getprompt
- description: DELETE /v1/prompt/{promptId}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprompt
- description: POST /v1/prompt/create
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprompt
- description: PATCH /v1/prompt/{promptId}/user-defined-id
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatepromptuserdefinedid
- description: POST /v1/prompt/version/{promptVersionId}/edit-label
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editpromptversionlabel
- description: POST /v1/prompt/version/{promptVersionId}/edit-template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editpromptversiontemplate
- description: POST /v1/prompt/version/{promptVersionId}/subversion-from-ui
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubversionfromui
- description: POST /v1/prompt/version/{promptVersionId}/subversion
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubversion
- description: POST /v1/prompt/version/{promptVersionId}/promote
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: promotepromptversiontoproduction
- description: POST /v1/prompt/version/{promptVersionId}/inputs/query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getinputs
- description: GET /v1/prompt/{promptId}/experiments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpromptexperiments
- description: POST /v1/prompt/{promptId}/versions/query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getpromptversions
---
