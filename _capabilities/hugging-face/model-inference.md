---
categories:
- machine-learning
consumed_apis: []
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
- create text completion via multi-provider api.
- run inference
- inference
- providers transcribe
- extract feature vectors from text for embeddings.
- generate text using the inference api
- fill in masked tokens in text.
- run inference on any model
- text generation
- list models available across all inference providers.
- create chat completion via providers
- text translation
- chat completion
- generate text using the tgi native endpoint.
- generate images from text prompts.
- tgi server info
- compute similarity
- generate text
- hugging face
- classify text
- text completion
- translate text between languages.
- classify images into categories.
- ai
- summarize
- generate text using a language model via the inference api.
- detect objects
- transcribe speech
- classify image
- transcribe audio via multi-provider api.
- generate images via multi-provider api.
- providers generate image
- providers chat completion
- classify text without predefined training labels.
- classify text into predefined categories.
- convert text to speech via multi-provider api.
- extract features
- generate image
- generate images from text
- translate text between languages
- create embeddings
- providers create embeddings
- run inference on a model via the inference api
- run inference on any hugging face model by model id.
- create text completion via providers
- fill mask
- translate
- tgi tokenize
- machine learning
- text summarization
- generate text with a specific model
- create text embeddings
- image generation
- classify text into categories
- answer questions based on provided context.
- translate text
- summarize text content
- get tgi server information and deployed model details.
- zero shot classify
- transcribe audio to text using automatic speech recognition.
- compute similarity between sentences.
- create text embeddings via multi-provider api.
- tokenize input text and return token ids.
- openai-compatible chat completions
- tgi chat completions
- list provider models
- providers text completion
- summarize text content.
- summarize text
- answer question
- tgi generate
- create chat completion via openai-compatible multi-provider api.
- text classification
- create chat completions using tgi openai-compatible messages api.
- text completions
- providers text to speech
- text embeddings
- detect objects in images.
slug: model-inference
source_filename: model-inference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hugging Face Model Inference\n  description: Unified workflow for running AI/ML inference across Hugging Face APIs, combining the Inference API, Inference\n    Providers, and Text Generation Inference for NLP, vision, audio, and multimodal tasks. Used by ML engineers and AI application\n    developers.\n  tags:\n  - Hugging Face\n  - Machine Learning\n  - Inference\n  - AI\n  - Text Generation\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HF_API_TOKEN: HF_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: hf-inference\n    baseUri: https://api-inference.huggingface.co\n    description: Run inference on ML models hosted on the Hugging Face Hub.\n    authentication:\n      type: bearer\n      token: '{{HF_API_TOKEN}}'\n    resources:\n    - name: model-inference\n      path: /models/{model_id}\n      description: Run inference on a specific model\n      operations:\n      - name:\
  \ run-inference\n        method: POST\n        description: Run inference on any model hosted on the Hugging Face Hub.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID on the Hugging Face Hub\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            parameters: '{{tools.parameters}}'\n            options: '{{tools.options}}'\n    - name: pipeline-inference\n      path: /pipeline/{task}\n      description: Run inference by pipeline task\n      operations:\n      - name: run-pipeline-inference\n        method: POST\n        description: Run inference using a specific pipeline task.\n        inputParameters:\n        - name: task\n          in: path\n          type: string\n          required: true\n       \
  \   description: The pipeline task name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            parameters: '{{tools.parameters}}'\n    - name: text-generation\n      path: /models/{model_id}/text-generation\n      description: Text generation inference\n      operations:\n      - name: text-generation\n        method: POST\n        description: Generate text using a language model.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            parameters: '{{tools.parameters}}'\n    - name:\
  \ text-classification\n      path: /models/{model_id}/text-classification\n      description: Text classification inference\n      operations:\n      - name: text-classification\n        method: POST\n        description: Classify text into predefined categories.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: question-answering\n      path: /models/{model_id}/question-answering\n      description: Question answering inference\n      operations:\n      - name: question-answering\n        method: POST\n        description: Answer questions based on provided context.\n        inputParameters:\n        - name: model_id\n          in: path\n         \
  \ type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: summarization\n      path: /models/{model_id}/summarization\n      description: Text summarization inference\n      operations:\n      - name: summarization\n        method: POST\n        description: Summarize text content.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            parameters: '{{tools.parameters}}'\n    - name: translation\n      path:\
  \ /models/{model_id}/translation\n      description: Text translation inference\n      operations:\n      - name: translation\n        method: POST\n        description: Translate text between languages.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: fill-mask\n      path: /models/{model_id}/fill-mask\n      description: Fill mask inference\n      operations:\n      - name: fill-mask\n        method: POST\n        description: Fill in masked tokens in text.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: feature-extraction\n      path: /models/{model_id}/feature-extraction\n      description: Feature extraction inference\n      operations:\n      - name: feature-extraction\n        method: POST\n        description: Extract feature vectors from text.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: image-classification\n      path: /models/{model_id}/image-classification\n      description: Image classification inference\n      operations:\n      -\
  \ name: image-classification\n        method: POST\n        description: Classify images into categories.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: object-detection\n      path: /models/{model_id}/object-detection\n      description: Object detection inference\n      operations:\n      - name: object-detection\n        method: POST\n        description: Detect objects in images.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: speech-recognition\n      path: /models/{model_id}/automatic-speech-recognition\n      description: Automatic speech recognition\n      operations:\n      - name: automatic-speech-recognition\n        method: POST\n        description: Transcribe audio to text.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: text-to-image\n      path: /models/{model_id}/text-to-image\n      description: Text to image generation\n      operations:\n      - name: text-to-image\n        method: POST\n        description: Generate images from\
  \ text prompts.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            parameters: '{{tools.parameters}}'\n    - name: zero-shot-classification\n      path: /models/{model_id}/zero-shot-classification\n      description: Zero-shot classification\n      operations:\n      - name: zero-shot-classification\n        method: POST\n        description: Classify text without predefined training labels.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            parameters: '{{tools.parameters}}'\n    - name: sentence-similarity\n      path: /models/{model_id}/sentence-similarity\n      description: Sentence similarity\n      operations:\n      - name: sentence-similarity\n        method: POST\n        description: Compute similarity between sentences.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n  - type: http\n    namespace: hf-providers\n    baseUri: https://router.huggingface.co\n    description: Unified inference proxy routing to 15+ providers via OpenAI-compatible endpoints.\n    authentication:\n\
  \      type: bearer\n      token: '{{HF_API_TOKEN}}'\n    resources:\n    - name: chat-completions\n      path: /v1/chat/completions\n      description: Chat completion endpoint\n      operations:\n      - name: create-chat-completion\n        method: POST\n        description: Create a chat completion using an OpenAI-compatible API.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            messages: '{{tools.messages}}'\n            max_tokens: '{{tools.max_tokens}}'\n            temperature: '{{tools.temperature}}'\n            stream: '{{tools.stream}}'\n    - name: completions\n      path: /v1/completions\n      description: Text completion endpoint\n      operations:\n      - name: create-completion\n        method: POST\n        description: Create a text completion.\n        inputParameters:\
  \ []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            prompt: '{{tools.prompt}}'\n            max_tokens: '{{tools.max_tokens}}'\n            temperature: '{{tools.temperature}}'\n    - name: embeddings\n      path: /v1/embeddings\n      description: Text embedding endpoint\n      operations:\n      - name: create-embeddings\n        method: POST\n        description: Create text embeddings.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            input: '{{tools.input}}'\n    - name: image-generation\n      path: /v1/images/generations\n      description: Image generation endpoint\n      operations:\n   \
  \   - name: create-image-generation\n        method: POST\n        description: Generate images from text prompts.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            prompt: '{{tools.prompt}}'\n            n: '{{tools.n}}'\n            size: '{{tools.size}}'\n    - name: transcription\n      path: /v1/audio/transcriptions\n      description: Audio transcription endpoint\n      operations:\n      - name: create-transcription\n        method: POST\n        description: Transcribe audio to text.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            file: '{{tools.file}}'\n    - name:\
  \ speech\n      path: /v1/audio/speech\n      description: Text-to-speech endpoint\n      operations:\n      - name: create-speech\n        method: POST\n        description: Convert text to speech audio.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            input: '{{tools.input}}'\n            voice: '{{tools.voice}}'\n    - name: models\n      path: /v1/models\n      description: List available models\n      operations:\n      - name: list-models\n        method: GET\n        description: List available models from all providers.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-by-id\n      path: /v1/models/{model_id}\n      description: Get model details\n\
  \      operations:\n      - name: get-model\n        method: GET\n        description: Get details about a specific model.\n        inputParameters:\n        - name: model_id\n          in: path\n          type: string\n          required: true\n          description: The model ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: hf-tgi\n    baseUri: https://api-inference.huggingface.co\n    description: High-performance LLM serving with streaming, tool calling, and structured output.\n    authentication:\n      type: bearer\n      token: '{{HF_API_TOKEN}}'\n    resources:\n    - name: generate\n      path: /generate\n      description: Generate text\n      operations:\n      - name: generate\n        method: POST\n        description: Generate text using the TGI native endpoint.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            parameters: '{{tools.parameters}}'\n    - name: generate-stream\n      path: /generate_stream\n      description: Generate text with streaming\n      operations:\n      - name: generate-stream\n        method: POST\n        description: Generate text with server-sent events streaming.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            parameters: '{{tools.parameters}}'\n    - name: chat-completions\n      path: /v1/chat/completions\n      description: OpenAI-compatible chat completions\n      operations:\n      - name: chat-completions\n        method: POST\n        description: Create chat completions using OpenAI-compatible\
  \ Messages API.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            messages: '{{tools.messages}}'\n            max_tokens: '{{tools.max_tokens}}'\n            temperature: '{{tools.temperature}}'\n            stream: '{{tools.stream}}'\n    - name: completions\n      path: /v1/completions\n      description: OpenAI-compatible completions\n      operations:\n      - name: completions\n        method: POST\n        description: Create text completions.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n            prompt: '{{tools.prompt}}'\n            max_tokens: '{{tools.max_tokens}}'\n\
  \    - name: models\n      path: /v1/models\n      description: List available models\n      operations:\n      - name: list-models\n        method: GET\n        description: List available models on the TGI server.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: info\n      path: /info\n      description: Server information\n      operations:\n      - name: get-info\n        method: GET\n        description: Get information about the deployed model and server.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /health\n      description: Health check\n      operations:\n      - name: health-check\n        method: GET\n        description: Check if the TGI server is healthy.\n        inputParameters: []\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n      description: Server metrics\n      operations:\n      - name: get-metrics\n        method: GET\n        description: Get Prometheus metrics from the TGI server.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokenize\n      path: /tokenize\n      description: Tokenize text\n      operations:\n      - name: tokenize\n        method: POST\n        description: Tokenize input text and return token IDs.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hf-model-inference-api\n\
  \    description: Unified REST API for running ML inference across Hugging Face services.\n    resources:\n    - path: /v1/inference/{model_id}\n      name: inference\n      description: Run inference on any model\n      operations:\n      - method: POST\n        name: run-inference\n        description: Run inference on a model via the Inference API\n        call: hf-inference.run-inference\n        with:\n          model_id: rest.model_id\n          inputs: rest.inputs\n          parameters: rest.parameters\n          options: rest.options\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/text-generation/{model_id}\n      name: text-generation\n      description: Generate text with a specific model\n      operations:\n      - method: POST\n        name: text-generation\n        description: Generate text using the Inference API\n        call: hf-inference.text-generation\n        with:\n          model_id: rest.model_id\n          inputs: rest.inputs\n\
  \          parameters: rest.parameters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/chat/completions\n      name: chat-completions\n      description: OpenAI-compatible chat completions\n      operations:\n      - method: POST\n        name: chat-completion\n        description: Create chat completion via providers\n        call: hf-providers.create-chat-completion\n        with:\n          model: rest.model\n          messages: rest.messages\n          max_tokens: rest.max_tokens\n          temperature: rest.temperature\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/completions\n      name: completions\n      description: Text completions\n      operations:\n      - method: POST\n        name: text-completion\n        description: Create text completion via providers\n        call: hf-providers.create-completion\n        with:\n          model: rest.model\n          prompt: rest.prompt\n        \
  \  max_tokens: rest.max_tokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/embeddings\n      name: embeddings\n      description: Text embeddings\n      operations:\n      - method: POST\n        name: create-embeddings\n        description: Create text embeddings\n        call: hf-providers.create-embeddings\n        with:\n          model: rest.model\n          input: rest.input\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images/generations\n      name: image-generation\n      description: Image generation\n      operations:\n      - method: POST\n        name: generate-image\n        description: Generate images from text\n        call: hf-providers.create-image-generation\n        with:\n          model: rest.model\n          prompt: rest.prompt\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/classification/{model_id}\n      name: classification\n\
  \      description: Text classification\n      operations:\n      - method: POST\n        name: classify-text\n        description: Classify text into categories\n        call: hf-inference.text-classification\n        with:\n          model_id: rest.model_id\n          inputs: rest.inputs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/summarization/{model_id}\n      name: summarization\n      description: Text summarization\n      operations:\n      - method: POST\n        name: summarize\n        description: Summarize text content\n        call: hf-inference.summarization\n        with:\n          model_id: rest.model_id\n          inputs: rest.inputs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/translation/{model_id}\n      name: translation\n      description: Text translation\n      operations:\n      - method: POST\n        name: translate\n        description: Translate text between languages\n\
  \        call: hf-inference.translation\n        with:\n          model_id: rest.model_id\n          inputs: rest.inputs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hf-model-inference-mcp\n    transport: http\n    description: MCP server for AI-assisted ML model inference across Hugging Face services.\n    tools:\n    - name: run-inference\n      description: Run inference on any Hugging Face model by model ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-inference.run-inference\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n        parameters: tools.parameters\n        options: tools.options\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-text\n      description: Generate text using a language model via the Inference API.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-inference.text-generation\n\
  \      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n        parameters: tools.parameters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: classify-text\n      description: Classify text into predefined categories.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-inference.text-classification\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: answer-question\n      description: Answer questions based on provided context.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-inference.question-answering\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: summarize-text\n      description: Summarize text content.\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: hf-inference.summarization\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n        parameters: tools.parameters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: translate-text\n      description: Translate text between languages.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-inference.translation\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fill-mask\n      description: Fill in masked tokens in text.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-inference.fill-mask\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: extract-features\n      description: Extract feature vectors from text for embeddings.\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: hf-inference.feature-extraction\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: classify-image\n      description: Classify images into categories.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-inference.image-classification\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: detect-objects\n      description: Detect objects in images.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-inference.object-detection\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: transcribe-speech\n      description: Transcribe audio to text using automatic speech recognition.\n   \
  \   hints:\n        readOnly: true\n        openWorld: true\n      call: hf-inference.automatic-speech-recognition\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-image\n      description: Generate images from text prompts.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-inference.text-to-image\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n        parameters: tools.parameters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: zero-shot-classify\n      description: Classify text without predefined training labels.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-inference.zero-shot-classification\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n        parameters: tools.parameters\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: compute-similarity\n      description: Compute similarity between sentences.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-inference.sentence-similarity\n      with:\n        model_id: tools.model_id\n        inputs: tools.inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: providers-chat-completion\n      description: Create chat completion via OpenAI-compatible multi-provider API.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-providers.create-chat-completion\n      with:\n        model: tools.model\n        messages: tools.messages\n        max_tokens: tools.max_tokens\n        temperature: tools.temperature\n        stream: tools.stream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: providers-text-completion\n      description: Create text completion via multi-provider API.\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: hf-providers.create-completion\n      with:\n        model: tools.model\n        prompt: tools.prompt\n        max_tokens: tools.max_tokens\n        temperature: tools.temperature\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: providers-create-embeddings\n      description: Create text embeddings via multi-provider API.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-providers.create-embeddings\n      with:\n        model: tools.model\n        input: tools.input\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: providers-generate-image\n      description: Generate images via multi-provider API.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-providers.create-image-generation\n      with:\n        model: tools.model\n        prompt: tools.prompt\n        n: tools.n\n        size: tools.size\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: providers-transcribe\n      description: Transcribe audio via multi-provider API.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-providers.create-transcription\n      with:\n        model: tools.model\n        file: tools.file\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: providers-text-to-speech\n      description: Convert text to speech via multi-provider API.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-providers.create-speech\n      with:\n        model: tools.model\n        input: tools.input\n        voice: tools.voice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tgi-generate\n      description: Generate text using the TGI native endpoint.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-tgi.generate\n      with:\n        inputs: tools.inputs\n        parameters:\
  \ tools.parameters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tgi-chat-completions\n      description: Create chat completions using TGI OpenAI-compatible Messages API.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-tgi.chat-completions\n      with:\n        model: tools.model\n        messages: tools.messages\n        max_tokens: tools.max_tokens\n        temperature: tools.temperature\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tgi-tokenize\n      description: Tokenize input text and return token IDs.\n      hints:\n        readOnly: true\n      call: hf-tgi.tokenize\n      with:\n        inputs: tools.inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tgi-server-info\n      description: Get TGI server information and deployed model details.\n      hints:\n        readOnly: true\n      call: hf-tgi.get-info\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: list-provider-models\n      description: List models available across all inference providers.\n      hints:\n        readOnly: true\n      call: hf-providers.list-models\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
