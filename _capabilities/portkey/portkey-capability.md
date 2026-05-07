---
categories: []
consumed_apis: []
description: The Portkey REST API. Please see https://portkey.ai/docs/api-reference for more details.
layout: capability
name: Portkey API
operations:
- description: Chat
  method: POST
  name: createchatcompletion
  path: /chat/completions
- description: Realtime
  method: GET
  name: connectrealtime
  path: /realtime
- description: Completions
  method: POST
  name: createcompletion
  path: /completions
- description: Create a new collection
  method: POST
  name: post-collections
  path: /collections
- description: List collections
  method: GET
  name: get-collections
  path: /collections
- description: Get collection details
  method: GET
  name: get-collections-collectionid
  path: /collections/{collectionId}
- description: Update collection
  method: PUT
  name: put-collections-collectionid
  path: /collections/{collectionId}
- description: Delete collection
  method: DELETE
  name: delete-collections-collectionid
  path: /collections/{collectionId}
- description: Create a new label
  method: POST
  name: createlabel
  path: /labels
- description: List labels
  method: GET
  name: listlabels
  path: /labels
- description: Get a label by ID
  method: GET
  name: getlabel
  path: /labels/{labelId}
- description: Update a label
  method: PUT
  name: updatelabel
  path: /labels/{labelId}
- description: Delete a label
  method: DELETE
  name: deletelabel
  path: /labels/{labelId}
- description: Create a new prompt
  method: POST
  name: createprompt
  path: /prompts
- description: List prompts
  method: GET
  name: listprompts
  path: /prompts
- description: Get a prompt by ID or slug
  method: GET
  name: getprompt
  path: /prompts/{promptId}
- description: Update a prompt
  method: PUT
  name: updateprompt
  path: /prompts/{promptId}
- description: Delete a prompt
  method: DELETE
  name: deleteprompt
  path: /prompts/{promptId}
- description: Get all versions of a prompt
  method: GET
  name: getpromptversions
  path: /prompts/{promptId}/versions
- description: Get a specific version of a prompt
  method: GET
  name: getpromptbyversion
  path: /prompts/{promptId}/versions/{versionId}
- description: Update a specific version of a prompt
  method: PUT
  name: updatepromptversion
  path: /prompts/{promptId}/versions/{versionId}
- description: Set a version as the default for a prompt
  method: PUT
  name: updatepromptdefault
  path: /prompts/{promptId}/makeDefault
- description: Create a new prompt partial
  method: POST
  name: createpromptpartial
  path: /prompts/partials
- description: List prompt partials
  method: GET
  name: listpromptpartials
  path: /prompts/partials
- description: Get a prompt partial by ID or slug
  method: GET
  name: getpromptpartial
  path: /prompts/partials/{promptPartialId}
- description: Update a prompt partial
  method: PUT
  name: updatepromptpartial
  path: /prompts/partials/{promptPartialId}
- description: Delete a prompt partial
  method: DELETE
  name: deletepromptpartial
  path: /prompts/partials/{promptPartialId}
- description: Get all versions of a prompt partial
  method: GET
  name: getpromptpartialversions
  path: /prompts/partials/{promptPartialId}/versions
- description: Set a version as the default for a prompt partial
  method: PUT
  name: updatepromptpartialdefault
  path: /prompts/partials/{promptPartialId}/makeDefault
- description: Prompts Completions
  method: POST
  name: createpromptcompletion
  path: /prompts/{promptId}/completions
- description: Prompts Render
  method: POST
  name: createpromptrender
  path: /prompts/{promptId}/render
- description: Create a new guardrail
  method: POST
  name: createguardrail
  path: /guardrails
- description: List guardrails
  method: GET
  name: listguardrails
  path: /guardrails
- description: Get a specific guardrail
  method: GET
  name: getguardrail
  path: /guardrails/{guardrailId}
- description: Update a guardrail
  method: PUT
  name: updateguardrail
  path: /guardrails/{guardrailId}
- description: Delete a guardrail
  method: DELETE
  name: deleteguardrail
  path: /guardrails/{guardrailId}
- description: Create Image
  method: POST
  name: createimage
  path: /images/generations
- description: Create Image Edit
  method: POST
  name: createimageedit
  path: /images/edits
- description: Creates Image Variation
  method: POST
  name: createimagevariation
  path: /images/variations
- description: Embeddings
  method: POST
  name: createembedding
  path: /embeddings
- description: Rerank
  method: POST
  name: creatererank
  path: /rerank
- description: Create Speech
  method: POST
  name: createspeech
  path: /audio/speech
- description: Create Transcription
  method: POST
  name: createtranscription
  path: /audio/transcriptions
- description: Create Translation
  method: POST
  name: createtranslation
  path: /audio/translations
- description: List Files
  method: GET
  name: listfiles
  path: /files
- description: Upload a file to be used across various endpoints, such as Assistant (<2M tokens), Fine-Tuning, and Batch (<100 MB). Total size of your bucket is 100 GB.
  method: POST
  name: createfile
  path: /files
- description: Delete File
  method: DELETE
  name: deletefile
  path: /files/{file_id}
- description: Returns information about a specific file.
  method: GET
  name: retrievefile
  path: /files/{file_id}
- description: Returns the contents of the specified file.
  method: GET
  name: downloadfile
  path: /files/{file_id}/content
- description: Create a Finetune Job
  method: POST
  name: createfinetuningjob
  path: /fine_tuning/jobs
- description: List your organization's fine-tuning jobs
  method: GET
  name: listpaginatedfinetuningjobs
  path: /fine_tuning/jobs
- description: Get info about a fine-tuning job. [Learn more about fine-tuning](https://platform.openai.com/docs/guides/fine-tuning)
  method: GET
  name: retrievefinetuningjob
  path: /fine_tuning/jobs/{fine_tuning_job_id}
- description: Get status updates for a fine-tuning job.
  method: GET
  name: listfinetuningevents
  path: /fine_tuning/jobs/{fine_tuning_job_id}/events
- description: Immediately cancel a fine-tune job.
  method: POST
  name: cancelfinetuningjob
  path: /fine_tuning/jobs/{fine_tuning_job_id}/cancel
- description: List checkpoints for a fine-tuning job.
  method: GET
  name: listfinetuningjobcheckpoints
  path: /fine_tuning/jobs/{fine_tuning_job_id}/checkpoints
- description: List Available Models
  method: GET
  name: listmodels
  path: /models
- description: Retrieves a model instance, providing basic information about the model such as the owner and permissioning.
  method: GET
  name: retrievemodel
  path: /models/{model}
- description: Delete a fine-tuned model. You must have the Owner role in your organization to delete a model.
  method: DELETE
  name: deletemodel
  path: /models/{model}
- description: Identify potentially harmful content in text and images. **Only** works with [OpenAI's Moderations endpoint](https://platform.openai.com/docs/guides/moderation) currently.
  method: POST
  name: createmoderation
  path: /moderations
- description: Returns a list of assistants.
  method: GET
  name: listassistants
  path: /assistants
personas: []
provider_name: Portkey
provider_slug: portkey
search_terms:
- portkey
- updateguardrail
- delete collections collectionid
- get a prompt by id or slug
- get a specific guardrail
- api
- returns the contents of the specified file.
- get collections collectionid
- getpromptpartial
- createimage
- get info about a fine-tuning job. [learn more about fine-tuning](https://platform.openai.com/docs/guides/fine-tuning)
- get all versions of a prompt
- rerank
- deletemodel
- connectrealtime
- get collection details
- deletelabel
- create transcription
- deletepromptpartial
- retrievemodel
- getlabel
- creates image variation
- list checkpoints for a fine-tuning job.
- retrievefinetuningjob
- list collections
- deleteprompt
- updatelabel
- createfile
- set a version as the default for a prompt
- set a version as the default for a prompt partial
- delete a label
- get status updates for a fine-tuning job.
- listfiles
- get a specific version of a prompt
- getpromptversions
- list your organization's fine-tuning jobs
- delete a prompt partial
- updatepromptdefault
- updatepromptpartial
- delete collection
- createpromptpartial
- createspeech
- get collections
- create a new guardrail
- prompt management
- completions
- createchatcompletion
- create translation
- upload a file to be used across various endpoints, such as assistant (<2m tokens), fine-tuning, and batch (<100 mb). total size of your bucket is 100 gb.
- returns a list of assistants.
- retrieves a model instance, providing basic information about the model such as the owner and permissioning.
- createprompt
- create a new prompt
- creatererank
- createtranslation
- getpromptbyversion
- get a label by id
- createimagevariation
- listassistants
- listguardrails
- immediately cancel a fine-tune job.
- post collections
- listprompts
- update a prompt
- realtime
- create image
- delete file
- getguardrail
- createtranscription
- createpromptcompletion
- createpromptrender
- createcompletion
- update a guardrail
- returns information about a specific file.
- listpromptpartials
- listmodels
- observability
- embeddings
- createimageedit
- list labels
- getprompt
- cancelfinetuningjob
- createguardrail
- delete a fine-tuned model. you must have the owner role in your organization to delete a model.
- deletefile
- create a finetune job
- create a new label
- update collection
- listfinetuningjobcheckpoints
- deleteguardrail
- createlabel
- createmoderation
- prompts render
- createfinetuningjob
- list available models
- delete a prompt
- governance
- updatepromptversion
- list prompt partials
- update a prompt partial
- list guardrails
- create a new prompt partial
- get all versions of a prompt partial
- listfinetuningevents
- create a new collection
- updatepromptpartialdefault
- gateways
- createembedding
- identify potentially harmful content in text and images. **only** works with [openai's moderations endpoint](https://platform.openai.com/docs/guides/moderation) currently.
- guardrails
- prompts completions
- getpromptpartialversions
- create speech
- ai gateways
- update a specific version of a prompt
- chat
- list files
- create image edit
- update a label
- updateprompt
- delete a guardrail
- downloadfile
- retrievefile
- listpaginatedfinetuningjobs
- put collections collectionid
- listlabels
- list prompts
- get a prompt partial by id or slug
slug: portkey-capability
source_filename: portkey-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Portkey API\n  description: The Portkey REST API. Please see https://portkey.ai/docs/api-reference for more details.\n  tags:\n  - Portkey\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: portkey\n    baseUri: https://api.portkey.ai/v1\n    description: Portkey API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-portkey-api-key\n      value: '{{PORTKEY_TOKEN}}'\n    resources:\n    - name: chat-completions\n      path: /chat/completions\n      operations:\n      - name: createchatcompletion\n        method: POST\n        description: Chat\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: realtime\n      path: /realtime\n      operations:\n      - name: connectrealtime\n        method: GET\n        description: Realtime\n        inputParameters:\n\
  \        - name: model\n          in: query\n          type: string\n          description: Often required for OpenAI-style realtime; other query params pass through unchanged.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: completions\n      path: /completions\n      operations:\n      - name: createcompletion\n        method: POST\n        description: Completions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: collections\n      path: /collections\n      operations:\n      - name: post-collections\n        method: POST\n        description: Create a new collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-collections\n        method: GET\n        description: List collections\n        inputParameters:\n\
  \        - name: workspace_id\n          in: query\n          type: string\n          required: true\n          description: ID or slug of the workspace\n        - name: current_page\n          in: query\n          type: integer\n          description: Page number for pagination (0-indexed)\n        - name: page_size\n          in: query\n          type: integer\n          description: Number of items per page\n        - name: search\n          in: query\n          type: string\n          description: Search query to filter collections by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: collections-collectionid\n      path: /collections/{collectionId}\n      operations:\n      - name: get-collections-collectionid\n        method: GET\n        description: Get collection details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n      - name: put-collections-collectionid\n        method: PUT\n        description: Update collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-collections-collectionid\n        method: DELETE\n        description: Delete collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: labels\n      path: /labels\n      operations:\n      - name: createlabel\n        method: POST\n        description: Create a new label\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listlabels\n        method: GET\n        description: List labels\n        inputParameters:\n        - name: organisation_id\n          in: query\n          type: string\n          description: ID of the organisation\n     \
  \   - name: workspace_id\n          in: query\n          type: string\n          description: ID or slug of the workspace\n        - name: search\n          in: query\n          type: string\n          description: Search query to filter labels by name\n        - name: current_page\n          in: query\n          type: integer\n          description: Page number for pagination\n        - name: page_size\n          in: query\n          type: integer\n          description: Number of items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: labels-labelid\n      path: /labels/{labelId}\n      operations:\n      - name: getlabel\n        method: GET\n        description: Get a label by ID\n        inputParameters:\n        - name: labelId\n          in: path\n          type: string\n          required: true\n          description: ID of the label to retrieve\n        - name: organisation_id\n\
  \          in: query\n          type: string\n          description: ID of the organisation\n        - name: workspace_id\n          in: query\n          type: string\n          description: ID or slug of the workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelabel\n        method: PUT\n        description: Update a label\n        inputParameters:\n        - name: labelId\n          in: path\n          type: string\n          required: true\n          description: ID of the label to update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelabel\n        method: DELETE\n        description: Delete a label\n        inputParameters:\n        - name: labelId\n          in: path\n          type: string\n          required: true\n          description: ID of the label to delete\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prompts\n      path: /prompts\n      operations:\n      - name: createprompt\n        method: POST\n        description: Create a new prompt\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listprompts\n        method: GET\n        description: List prompts\n        inputParameters:\n        - name: collection_id\n          in: query\n          type: string\n        - name: workspace_id\n          in: query\n          type: string\n        - name: current_page\n          in: query\n          type: integer\n        - name: page_size\n          in: query\n          type: integer\n        - name: search\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ prompts-promptid\n      path: /prompts/{promptId}\n      operations:\n      - name: getprompt\n        method: GET\n        description: Get a prompt by ID or slug\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateprompt\n        method: PUT\n        description: Update a prompt\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteprompt\n        method: DELETE\n        description: Delete a prompt\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prompts-promptid-versions\n      path: /prompts/{promptId}/versions\n      operations:\n      - name: getpromptversions\n        method: GET\n        description: Get all versions of a prompt\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prompts-promptid-versions-versionid\n      path: /prompts/{promptId}/versions/{versionId}\n      operations:\n      - name: getpromptbyversion\n        method: GET\n        description: Get a specific version of a prompt\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        - name: versionId\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepromptversion\n        method: PUT\n        description: Update a specific version of a prompt\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        - name: versionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prompts-promptid-makedefault\n      path: /prompts/{promptId}/makeDefault\n      operations:\n      - name: updatepromptdefault\n        method: PUT\n        description: Set a version as the default for a prompt\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n    - name: prompts-partials\n      path: /prompts/partials\n      operations:\n      - name: createpromptpartial\n        method: POST\n        description: Create a new prompt partial\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listpromptpartials\n        method: GET\n        description: List prompt partials\n        inputParameters:\n        - name: collection_id\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prompts-partials-promptpartialid\n      path: /prompts/partials/{promptPartialId}\n      operations:\n      - name: getpromptpartial\n        method: GET\n        description: Get a prompt partial by ID or slug\n        inputParameters:\n        - name: promptPartialId\n        \
  \  in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepromptpartial\n        method: PUT\n        description: Update a prompt partial\n        inputParameters:\n        - name: promptPartialId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepromptpartial\n        method: DELETE\n        description: Delete a prompt partial\n        inputParameters:\n        - name: promptPartialId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prompts-partials-promptpartialid-versions\n      path: /prompts/partials/{promptPartialId}/versions\n\
  \      operations:\n      - name: getpromptpartialversions\n        method: GET\n        description: Get all versions of a prompt partial\n        inputParameters:\n        - name: promptPartialId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prompts-partials-promptpartialid-makedefault\n      path: /prompts/partials/{promptPartialId}/makeDefault\n      operations:\n      - name: updatepromptpartialdefault\n        method: PUT\n        description: Set a version as the default for a prompt partial\n        inputParameters:\n        - name: promptPartialId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prompts-promptid-completions\n      path: /prompts/{promptId}/completions\n\
  \      operations:\n      - name: createpromptcompletion\n        method: POST\n        description: Prompts Completions\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the prompt template to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prompts-promptid-render\n      path: /prompts/{promptId}/render\n      operations:\n      - name: createpromptrender\n        method: POST\n        description: Prompts Render\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the prompt template to render\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: guardrails\n      path:\
  \ /guardrails\n      operations:\n      - name: createguardrail\n        method: POST\n        description: Create a new guardrail\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listguardrails\n        method: GET\n        description: List guardrails\n        inputParameters:\n        - name: workspace_id\n          in: query\n          type: string\n          description: Workspace UUID to filter guardrails\n        - name: organisation_id\n          in: query\n          type: string\n          description: Organisation UUID to filter guardrails\n        - name: page_size\n          in: query\n          type: integer\n          description: Number of items per page\n        - name: current_page\n          in: query\n          type: integer\n          description: Current page number (0-indexed)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: guardrails-guardrailid\n      path: /guardrails/{guardrailId}\n      operations:\n      - name: getguardrail\n        method: GET\n        description: Get a specific guardrail\n        inputParameters:\n        - name: guardrailId\n          in: path\n          type: string\n          required: true\n          description: Guardrail UUID or slug (with guard_ prefix)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateguardrail\n        method: PUT\n        description: Update a guardrail\n        inputParameters:\n        - name: guardrailId\n          in: path\n          type: string\n          required: true\n          description: Guardrail UUID or slug to update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteguardrail\n        method: DELETE\n \
  \       description: Delete a guardrail\n        inputParameters:\n        - name: guardrailId\n          in: path\n          type: string\n          required: true\n          description: Guardrail UUID or slug to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-generations\n      path: /images/generations\n      operations:\n      - name: createimage\n        method: POST\n        description: Create Image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-edits\n      path: /images/edits\n      operations:\n      - name: createimageedit\n        method: POST\n        description: Create Image Edit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-variations\n      path: /images/variations\n\
  \      operations:\n      - name: createimagevariation\n        method: POST\n        description: Creates Image Variation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: embeddings\n      path: /embeddings\n      operations:\n      - name: createembedding\n        method: POST\n        description: Embeddings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rerank\n      path: /rerank\n      operations:\n      - name: creatererank\n        method: POST\n        description: Rerank\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audio-speech\n      path: /audio/speech\n      operations:\n      - name: createspeech\n        method: POST\n        description: Create Speech\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: audio-transcriptions\n      path: /audio/transcriptions\n      operations:\n      - name: createtranscription\n        method: POST\n        description: Create Transcription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audio-translations\n      path: /audio/translations\n      operations:\n      - name: createtranslation\n        method: POST\n        description: Create Translation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files\n      path: /files\n      operations:\n      - name: listfiles\n        method: GET\n        description: List Files\n        inputParameters:\n        - name: purpose\n          in: query\n          type: string\n          description: Only return files with the given purpose.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfile\n        method: POST\n        description: Upload a file to be used across various endpoints, such as Assistant (<2M tokens), Fine-Tuning, and Batch\n          (<100 MB). Total size of your bucket is 100 GB.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-file-id\n      path: /files/{file_id}\n      operations:\n      - name: deletefile\n        method: DELETE\n        description: Delete File\n        inputParameters:\n        - name: file_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the file to use for this request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: retrievefile\n        method: GET\n        description:\
  \ Returns information about a specific file.\n        inputParameters:\n        - name: file_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the file to use for this request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-file-id-content\n      path: /files/{file_id}/content\n      operations:\n      - name: downloadfile\n        method: GET\n        description: Returns the contents of the specified file.\n        inputParameters:\n        - name: file_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the file to use for this request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fine-tuning-jobs\n      path: /fine_tuning/jobs\n      operations:\n      - name: createfinetuningjob\n\
  \        method: POST\n        description: Create a Finetune Job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listpaginatedfinetuningjobs\n        method: GET\n        description: List your organization's fine-tuning jobs\n        inputParameters:\n        - name: after\n          in: query\n          type: string\n          description: Identifier for the last job from the previous pagination request.\n        - name: limit\n          in: query\n          type: integer\n          description: Number of fine-tuning jobs to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fine-tuning-jobs-fine-tuning-job-id\n      path: /fine_tuning/jobs/{fine_tuning_job_id}\n      operations:\n      - name: retrievefinetuningjob\n        method: GET\n        description: Get info about a fine-tuning job. [Learn\
  \ more about fine-tuning](https://platform.openai.com/docs/guides/fine-tuning)\n        inputParameters:\n        - name: fine_tuning_job_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the fine-tuning job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fine-tuning-jobs-fine-tuning-job-id-events\n      path: /fine_tuning/jobs/{fine_tuning_job_id}/events\n      operations:\n      - name: listfinetuningevents\n        method: GET\n        description: Get status updates for a fine-tuning job.\n        inputParameters:\n        - name: fine_tuning_job_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the fine-tuning job to get events for.\n        - name: after\n          in: query\n          type: string\n          description: Identifier for the last event from the previous pagination\
  \ request.\n        - name: limit\n          in: query\n          type: integer\n          description: Number of events to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fine-tuning-jobs-fine-tuning-job-id-cancel\n      path: /fine_tuning/jobs/{fine_tuning_job_id}/cancel\n      operations:\n      - name: cancelfinetuningjob\n        method: POST\n        description: Immediately cancel a fine-tune job.\n        inputParameters:\n        - name: fine_tuning_job_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the fine-tuning job to cancel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fine-tuning-jobs-fine-tuning-job-id-checkpoints\n      path: /fine_tuning/jobs/{fine_tuning_job_id}/checkpoints\n      operations:\n      - name: listfinetuningjobcheckpoints\n\
  \        method: GET\n        description: List checkpoints for a fine-tuning job.\n        inputParameters:\n        - name: fine_tuning_job_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the fine-tuning job to get checkpoints for.\n        - name: after\n          in: query\n          type: string\n          description: Identifier for the last checkpoint ID from the previous pagination request.\n        - name: limit\n          in: query\n          type: integer\n          description: Number of checkpoints to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models\n      path: /models\n      operations:\n      - name: listmodels\n        method: GET\n        description: List Available Models\n        inputParameters:\n        - name: ai_service\n          in: query\n          type: string\n          description: Filter models\
  \ by the AI service (e.g., 'openai', 'anthropic').\n        - name: provider\n          in: query\n          type: string\n          description: Filter models by the provider.\n        - name: limit\n          in: query\n          type: integer\n          description: The maximum number of models to return.\n        - name: offset\n          in: query\n          type: integer\n          description: The number of models to skip before starting to collect the result set.\n        - name: sort\n          in: query\n          type: string\n          description: The field to sort the results by.\n        - name: order\n          in: query\n          type: string\n          description: The order to sort the results in.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models-model\n      path: /models/{model}\n      operations:\n      - name: retrievemodel\n        method: GET\n        description:\
  \ Retrieves a model instance, providing basic information about the model such as the owner and permissioning.\n        inputParameters:\n        - name: model\n          in: path\n          type: string\n          required: true\n          description: The ID of the model to use for this request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemodel\n        method: DELETE\n        description: Delete a fine-tuned model. You must have the Owner role in your organization to delete a model.\n        inputParameters:\n        - name: model\n          in: path\n          type: string\n          required: true\n          description: The model to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: moderations\n      path: /moderations\n      operations:\n      - name: createmoderation\n        method:\
  \ POST\n        description: Identify potentially harmful content in text and images. **Only** works with [OpenAI's Moderations endpoint](https://platform.openai.com/docs/guides/moderation)\n          currently.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assistants\n      path: /assistants\n      operations:\n      - name: listassistants\n        method: GET\n        description: Returns a list of assistants.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description: A limit on the number of objects to be returned. Limit can range between 1 and 100, and the default\n            is 20.\n        - name: order\n          in: query\n          type: string\n          description: Sort order by the `created_at` timestamp of the objects. `asc` for ascending order and `desc` for descending\n            order.\n        - name: after\n     \
  \     in: query\n          type: string\n          description: A cursor for use in pagination. `after` is an object ID that defines your place in the list. For instance,\n            if you make a list request and receive 100 objects, e\n        - name: before\n          in: query\n          type: string\n          description: 'A cursor for use in pagination. `before` is an object ID that defines your place in the list. For\n            instance, if you make a list request and receive 100 objects, '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: portkey-rest\n    description: REST adapter for Portkey API.\n    resources:\n    - path: /chat/completions\n      name: createchatcompletion\n      operations:\n      - method: POST\n        name: createchatcompletion\n        description: Chat\n        call: portkey.createchatcompletion\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /realtime\n      name: connectrealtime\n      operations:\n      - method: GET\n        name: connectrealtime\n        description: Realtime\n        call: portkey.connectrealtime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /completions\n      name: createcompletion\n      operations:\n      - method: POST\n        name: createcompletion\n        description: Completions\n        call: portkey.createcompletion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collections\n      name: post-collections\n      operations:\n      - method: POST\n        name: post-collections\n        description: Create a new collection\n        call: portkey.post-collections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collections\n      name: get-collections\n      operations:\n      - method: GET\n        name: get-collections\n\
  \        description: List collections\n        call: portkey.get-collections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collections/{collectionId}\n      name: get-collections-collectionid\n      operations:\n      - method: GET\n        name: get-collections-collectionid\n        description: Get collection details\n        call: portkey.get-collections-collectionid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collections/{collectionId}\n      name: put-collections-collectionid\n      operations:\n      - method: PUT\n        name: put-collections-collectionid\n        description: Update collection\n        call: portkey.put-collections-collectionid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /collections/{collectionId}\n      name: delete-collections-collectionid\n      operations:\n      - method: DELETE\n        name: delete-collections-collectionid\n\
  \        description: Delete collection\n        call: portkey.delete-collections-collectionid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /labels\n      name: createlabel\n      operations:\n      - method: POST\n        name: createlabel\n        description: Create a new label\n        call: portkey.createlabel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /labels\n      name: listlabels\n      operations:\n      - method: GET\n        name: listlabels\n        description: List labels\n        call: portkey.listlabels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /labels/{labelId}\n      name: getlabel\n      operations:\n      - method: GET\n        name: getlabel\n        description: Get a label by ID\n        call: portkey.getlabel\n        with:\n          labelId: rest.labelId\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /labels/{labelId}\n      name: updatelabel\n      operations:\n      - method: PUT\n        name: updatelabel\n        description: Update a label\n        call: portkey.updatelabel\n        with:\n          labelId: rest.labelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /labels/{labelId}\n      name: deletelabel\n      operations:\n      - method: DELETE\n        name: deletelabel\n        description: Delete a label\n        call: portkey.deletelabel\n        with:\n          labelId: rest.labelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /prompts\n      name: createprompt\n      operations:\n      - method: POST\n        name: createprompt\n        description: Create a new prompt\n        call: portkey.createprompt\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /prompts\n      name: listprompts\n      operations:\n      - method: GET\n      \
  \  name: listprompts\n        description: List prompts\n        call: portkey.listprompts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /prompts/{promptId}\n      name: getprompt\n      operations:\n      - method: GET\n        name: getprompt\n        description: Get a prompt by ID or slug\n        call: portkey.getprompt\n        with:\n          promptId: rest.promptId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /prompts/{promptId}\n      name: updateprompt\n      operations:\n      - method: PUT\n        name: updateprompt\n        description: Update a prompt\n        call: portkey.updateprompt\n        with:\n          promptId: rest.promptId\n        outputParameters:\n        - type: object\n          mapping: $.\n \n\n# --- truncated at 32 KB (73 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/portkey/refs/heads/main/capabilities/portkey-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/portkey/refs/heads/main/capabilities/portkey-capability.yaml
tags:
- Portkey
- API
tools:
- description: Chat
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchatcompletion
- description: Realtime
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: connectrealtime
- description: Completions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcompletion
- description: Create a new collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-collections
- description: List collections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-collections
- description: Get collection details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-collections-collectionid
- description: Update collection
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-collections-collectionid
- description: Delete collection
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-collections-collectionid
- description: Create a new label
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlabel
- description: List labels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlabels
- description: Get a label by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlabel
- description: Update a label
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelabel
- description: Delete a label
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletelabel
- description: Create a new prompt
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprompt
- description: List prompts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprompts
- description: Get a prompt by ID or slug
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprompt
- description: Update a prompt
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateprompt
- description: Delete a prompt
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprompt
- description: Get all versions of a prompt
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpromptversions
- description: Get a specific version of a prompt
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpromptbyversion
- description: Update a specific version of a prompt
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepromptversion
- description: Set a version as the default for a prompt
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepromptdefault
- description: Create a new prompt partial
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpromptpartial
- description: List prompt partials
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpromptpartials
- description: Get a prompt partial by ID or slug
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpromptpartial
- description: Update a prompt partial
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepromptpartial
- description: Delete a prompt partial
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepromptpartial
- description: Get all versions of a prompt partial
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpromptpartialversions
- description: Set a version as the default for a prompt partial
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepromptpartialdefault
- description: Prompts Completions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpromptcompletion
- description: Prompts Render
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpromptrender
- description: Create a new guardrail
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createguardrail
- description: List guardrails
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listguardrails
- description: Get a specific guardrail
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getguardrail
- description: Update a guardrail
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateguardrail
- description: Delete a guardrail
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteguardrail
- description: Create Image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createimage
- description: Create Image Edit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createimageedit
- description: Creates Image Variation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createimagevariation
- description: Embeddings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createembedding
- description: Rerank
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creatererank
- description: Create Speech
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createspeech
- description: Create Transcription
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtranscription
- description: Create Translation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtranslation
- description: List Files
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfiles
- description: Upload a file to be used across various endpoints, such as Assistant (<2M tokens), Fine-Tuning, and Batch (<100 MB). Total size of your bucket is 100 GB.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfile
- description: Delete File
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefile
- description: Returns information about a specific file.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievefile
- description: Returns the contents of the specified file.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadfile
- description: Create a Finetune Job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfinetuningjob
- description: List your organization's fine-tuning jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpaginatedfinetuningjobs
- description: Get info about a fine-tuning job. [Learn more about fine-tuning](https://platform.openai.com/docs/guides/fine-tuning)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievefinetuningjob
- description: Get status updates for a fine-tuning job.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfinetuningevents
- description: Immediately cancel a fine-tune job.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelfinetuningjob
- description: List checkpoints for a fine-tuning job.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfinetuningjobcheckpoints
- description: List Available Models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmodels
- description: Retrieves a model instance, providing basic information about the model such as the owner and permissioning.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievemodel
- description: Delete a fine-tuned model. You must have the Owner role in your organization to delete a model.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemodel
- description: Identify potentially harmful content in text and images. **Only** works with [OpenAI's Moderations endpoint](https://platform.openai.com/docs/guides/moderation) currently.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmoderation
- description: Returns a list of assistants.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listassistants
---
