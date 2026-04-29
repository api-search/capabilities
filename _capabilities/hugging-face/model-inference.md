---
categories:
- machine-learning
consumed_apis:
- hf-inference
- hf-providers
- hf-tgi
description: Unified workflow for running AI/ML inference across Hugging Face APIs, combining the Inference API, Inference Providers, and Text Generation Inference for NLP, vision, audio, and multimodal tasks. Used by ML engineers and AI application developers.
layout: capability
name: Hugging Face Model Inference
operations:
- description: Run inference on a model via the Inference API
  method: POST
  name: run-inference
  path: /v1/inference/{model_id}
- description: Generate text using the Inference API
  method: POST
  name: text-generation
  path: /v1/text-generation/{model_id}
- description: Create chat completion via providers
  method: POST
  name: chat-completion
  path: /v1/chat/completions
- description: Create text completion via providers
  method: POST
  name: text-completion
  path: /v1/completions
- description: Create text embeddings
  method: POST
  name: create-embeddings
  path: /v1/embeddings
- description: Generate images from text
  method: POST
  name: generate-image
  path: /v1/images/generations
- description: Classify text into categories
  method: POST
  name: classify-text
  path: /v1/classification/{model_id}
- description: Summarize text content
  method: POST
  name: summarize
  path: /v1/summarization/{model_id}
- description: Translate text between languages
  method: POST
  name: translate
  path: /v1/translation/{model_id}
personas: []
provider_name: Hugging Face
provider_slug: hugging-face
search_terms:
- transcribe speech
- translate
- create text completion via multi-provider api.
- tokenize input text and return token ids.
- generate text with a specific model
- create text embeddings
- text translation
- list models available across all inference providers.
- list provider models
- summarize text content
- fill in masked tokens in text.
- convert text to speech via multi-provider api.
- run inference on a model via the inference api
- extract features
- ai
- classify text into predefined categories.
- tgi server info
- hugging face
- providers create embeddings
- create chat completions using tgi openai-compatible messages api.
- create chat completion via openai-compatible multi-provider api.
- run inference on any hugging face model by model id.
- text completion
- classify text
- providers transcribe
- text completions
- providers text completion
- get tgi server information and deployed model details.
- summarize text
- classify image
- extract feature vectors from text for embeddings.
- create text embeddings via multi-provider api.
- compute similarity
- chat completion
- machine learning
- fill mask
- answer question
- text classification
- translate text
- run inference on any model
- image generation
- text summarization
- transcribe audio via multi-provider api.
- tgi generate
- generate images from text prompts.
- text generation
- generate text using the inference api
- create embeddings
- classify text into categories
- detect objects
- generate image
- tgi chat completions
- compute similarity between sentences.
- translate text between languages
- providers chat completion
- generate text
- summarize
- classify images into categories.
- tgi tokenize
- inference
- providers generate image
- generate text using the tgi native endpoint.
- generate images from text
- run inference
- text embeddings
- classify text without predefined training labels.
- generate images via multi-provider api.
- summarize text content.
- create text completion via providers
- translate text between languages.
- transcribe audio to text using automatic speech recognition.
- answer questions based on provided context.
- detect objects in images.
- generate text using a language model via the inference api.
- openai-compatible chat completions
- create chat completion via providers
- providers text to speech
- zero shot classify
slug: model-inference
source_filename: model-inference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Hugging Face Model Inference\"\n  description: \"Unified workflow for running AI/ML inference across Hugging Face APIs, combining the Inference API, Inference Providers, and Text Generation Inference for NLP, vision, audio, and multimodal tasks. Used by ML engineers and AI application developers.\"\n  tags:\n    - Hugging Face\n    - Machine Learning\n    - Inference\n    - AI\n    - Text Generation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      HF_API_TOKEN: HF_API_TOKEN\n\ncapability:\n  consumes:\n    - import: hf-inference\n      location: ./shared/inference.yaml\n    - import: hf-providers\n      location: ./shared/inference-providers.yaml\n    - import: hf-tgi\n      location: ./shared/text-generation-inference.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: hf-model-inference-api\n      description: \"Unified REST API for running ML inference\
  \ across Hugging Face services.\"\n      resources:\n        - path: /v1/inference/{model_id}\n          name: inference\n          description: \"Run inference on any model\"\n          operations:\n            - method: POST\n              name: run-inference\n              description: \"Run inference on a model via the Inference API\"\n              call: \"hf-inference.run-inference\"\n              with:\n                model_id: \"rest.model_id\"\n                inputs: \"rest.inputs\"\n                parameters: \"rest.parameters\"\n                options: \"rest.options\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/text-generation/{model_id}\n          name: text-generation\n          description: \"Generate text with a specific model\"\n          operations:\n            - method: POST\n              name: text-generation\n              description: \"Generate text using the Inference API\"\n   \
  \           call: \"hf-inference.text-generation\"\n              with:\n                model_id: \"rest.model_id\"\n                inputs: \"rest.inputs\"\n                parameters: \"rest.parameters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/chat/completions\n          name: chat-completions\n          description: \"OpenAI-compatible chat completions\"\n          operations:\n            - method: POST\n              name: chat-completion\n              description: \"Create chat completion via providers\"\n              call: \"hf-providers.create-chat-completion\"\n              with:\n                model: \"rest.model\"\n                messages: \"rest.messages\"\n                max_tokens: \"rest.max_tokens\"\n                temperature: \"rest.temperature\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/completions\n\
  \          name: completions\n          description: \"Text completions\"\n          operations:\n            - method: POST\n              name: text-completion\n              description: \"Create text completion via providers\"\n              call: \"hf-providers.create-completion\"\n              with:\n                model: \"rest.model\"\n                prompt: \"rest.prompt\"\n                max_tokens: \"rest.max_tokens\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/embeddings\n          name: embeddings\n          description: \"Text embeddings\"\n          operations:\n            - method: POST\n              name: create-embeddings\n              description: \"Create text embeddings\"\n              call: \"hf-providers.create-embeddings\"\n              with:\n                model: \"rest.model\"\n                input: \"rest.input\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/images/generations\n          name: image-generation\n          description: \"Image generation\"\n          operations:\n            - method: POST\n              name: generate-image\n              description: \"Generate images from text\"\n              call: \"hf-providers.create-image-generation\"\n              with:\n                model: \"rest.model\"\n                prompt: \"rest.prompt\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/classification/{model_id}\n          name: classification\n          description: \"Text classification\"\n          operations:\n            - method: POST\n              name: classify-text\n              description: \"Classify text into categories\"\n              call: \"hf-inference.text-classification\"\n              with:\n                model_id: \"rest.model_id\"\n                inputs: \"rest.inputs\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/summarization/{model_id}\n          name: summarization\n          description: \"Text summarization\"\n          operations:\n            - method: POST\n              name: summarize\n              description: \"Summarize text content\"\n              call: \"hf-inference.summarization\"\n              with:\n                model_id: \"rest.model_id\"\n                inputs: \"rest.inputs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/translation/{model_id}\n          name: translation\n          description: \"Text translation\"\n          operations:\n            - method: POST\n              name: translate\n              description: \"Translate text between languages\"\n              call: \"hf-inference.translation\"\n              with:\n                model_id: \"rest.model_id\"\
  \n                inputs: \"rest.inputs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: hf-model-inference-mcp\n      transport: http\n      description: \"MCP server for AI-assisted ML model inference across Hugging Face services.\"\n      tools:\n        - name: run-inference\n          description: \"Run inference on any Hugging Face model by model ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-inference.run-inference\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n            parameters: \"tools.parameters\"\n            options: \"tools.options\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: generate-text\n          description: \"Generate text using a language model via the Inference API.\"\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"hf-inference.text-generation\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n            parameters: \"tools.parameters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: classify-text\n          description: \"Classify text into predefined categories.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-inference.text-classification\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: answer-question\n          description: \"Answer questions based on provided context.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-inference.question-answering\"\n          with:\n\
  \            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: summarize-text\n          description: \"Summarize text content.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-inference.summarization\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n            parameters: \"tools.parameters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: translate-text\n          description: \"Translate text between languages.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-inference.translation\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: fill-mask\n          description: \"Fill in masked tokens in text.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-inference.fill-mask\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: extract-features\n          description: \"Extract feature vectors from text for embeddings.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-inference.feature-extraction\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: classify-image\n          description: \"Classify images into categories.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"hf-inference.image-classification\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: detect-objects\n          description: \"Detect objects in images.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-inference.object-detection\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: transcribe-speech\n          description: \"Transcribe audio to text using automatic speech recognition.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-inference.automatic-speech-recognition\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: generate-image\n          description: \"Generate images from text prompts.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-inference.text-to-image\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n            parameters: \"tools.parameters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: zero-shot-classify\n          description: \"Classify text without predefined training labels.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-inference.zero-shot-classification\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n            parameters: \"tools.parameters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ compute-similarity\n          description: \"Compute similarity between sentences.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-inference.sentence-similarity\"\n          with:\n            model_id: \"tools.model_id\"\n            inputs: \"tools.inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: providers-chat-completion\n          description: \"Create chat completion via OpenAI-compatible multi-provider API.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-providers.create-chat-completion\"\n          with:\n            model: \"tools.model\"\n            messages: \"tools.messages\"\n            max_tokens: \"tools.max_tokens\"\n            temperature: \"tools.temperature\"\n            stream: \"tools.stream\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ providers-text-completion\n          description: \"Create text completion via multi-provider API.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-providers.create-completion\"\n          with:\n            model: \"tools.model\"\n            prompt: \"tools.prompt\"\n            max_tokens: \"tools.max_tokens\"\n            temperature: \"tools.temperature\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: providers-create-embeddings\n          description: \"Create text embeddings via multi-provider API.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-providers.create-embeddings\"\n          with:\n            model: \"tools.model\"\n            input: \"tools.input\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: providers-generate-image\n          description: \"Generate\
  \ images via multi-provider API.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-providers.create-image-generation\"\n          with:\n            model: \"tools.model\"\n            prompt: \"tools.prompt\"\n            n: \"tools.n\"\n            size: \"tools.size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: providers-transcribe\n          description: \"Transcribe audio via multi-provider API.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-providers.create-transcription\"\n          with:\n            model: \"tools.model\"\n            file: \"tools.file\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: providers-text-to-speech\n          description: \"Convert text to speech via multi-provider API.\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"hf-providers.create-speech\"\n          with:\n            model: \"tools.model\"\n            input: \"tools.input\"\n            voice: \"tools.voice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: tgi-generate\n          description: \"Generate text using the TGI native endpoint.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-tgi.generate\"\n          with:\n            inputs: \"tools.inputs\"\n            parameters: \"tools.parameters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: tgi-chat-completions\n          description: \"Create chat completions using TGI OpenAI-compatible Messages API.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-tgi.chat-completions\"\n          with:\n            model: \"tools.model\"\n            messages:\
  \ \"tools.messages\"\n            max_tokens: \"tools.max_tokens\"\n            temperature: \"tools.temperature\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: tgi-tokenize\n          description: \"Tokenize input text and return token IDs.\"\n          hints:\n            readOnly: true\n          call: \"hf-tgi.tokenize\"\n          with:\n            inputs: \"tools.inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: tgi-server-info\n          description: \"Get TGI server information and deployed model details.\"\n          hints:\n            readOnly: true\n          call: \"hf-tgi.get-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-provider-models\n          description: \"List models available across all inference providers.\"\n          hints:\n            readOnly: true\n          call: \"\
  hf-providers.list-models\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hugging-face/refs/heads/main/capabilities/model-inference.yaml
tags:
- Hugging Face
- Machine Learning
- Inference
- AI
- Text Generation
tools:
- description: Run inference on any Hugging Face model by model ID.
  hints:
    openWorld: true
    readOnly: true
  name: run-inference
- description: Generate text using a language model via the Inference API.
  hints:
    openWorld: true
    readOnly: true
  name: generate-text
- description: Classify text into predefined categories.
  hints:
    openWorld: true
    readOnly: true
  name: classify-text
- description: Answer questions based on provided context.
  hints:
    openWorld: true
    readOnly: true
  name: answer-question
- description: Summarize text content.
  hints:
    openWorld: true
    readOnly: true
  name: summarize-text
- description: Translate text between languages.
  hints:
    openWorld: true
    readOnly: true
  name: translate-text
- description: Fill in masked tokens in text.
  hints:
    openWorld: true
    readOnly: true
  name: fill-mask
- description: Extract feature vectors from text for embeddings.
  hints:
    openWorld: true
    readOnly: true
  name: extract-features
- description: Classify images into categories.
  hints:
    openWorld: true
    readOnly: true
  name: classify-image
- description: Detect objects in images.
  hints:
    openWorld: true
    readOnly: true
  name: detect-objects
- description: Transcribe audio to text using automatic speech recognition.
  hints:
    openWorld: true
    readOnly: true
  name: transcribe-speech
- description: Generate images from text prompts.
  hints:
    openWorld: true
    readOnly: true
  name: generate-image
- description: Classify text without predefined training labels.
  hints:
    openWorld: true
    readOnly: true
  name: zero-shot-classify
- description: Compute similarity between sentences.
  hints:
    openWorld: true
    readOnly: true
  name: compute-similarity
- description: Create chat completion via OpenAI-compatible multi-provider API.
  hints:
    openWorld: true
    readOnly: true
  name: providers-chat-completion
- description: Create text completion via multi-provider API.
  hints:
    openWorld: true
    readOnly: true
  name: providers-text-completion
- description: Create text embeddings via multi-provider API.
  hints:
    openWorld: true
    readOnly: true
  name: providers-create-embeddings
- description: Generate images via multi-provider API.
  hints:
    openWorld: true
    readOnly: true
  name: providers-generate-image
- description: Transcribe audio via multi-provider API.
  hints:
    openWorld: true
    readOnly: true
  name: providers-transcribe
- description: Convert text to speech via multi-provider API.
  hints:
    openWorld: true
    readOnly: true
  name: providers-text-to-speech
- description: Generate text using the TGI native endpoint.
  hints:
    openWorld: true
    readOnly: true
  name: tgi-generate
- description: Create chat completions using TGI OpenAI-compatible Messages API.
  hints:
    openWorld: true
    readOnly: true
  name: tgi-chat-completions
- description: Tokenize input text and return token IDs.
  hints:
    readOnly: true
  name: tgi-tokenize
- description: Get TGI server information and deployed model details.
  hints:
    readOnly: true
  name: tgi-server-info
- description: List models available across all inference providers.
  hints:
    readOnly: true
  name: list-provider-models
---
