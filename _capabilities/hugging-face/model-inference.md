---
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
- detect objects in images.
- create text embeddings
- summarize
- run inference on any model
- text completion
- compute similarity
- translate text
- create chat completion via openai-compatible multi-provider api.
- inference
- convert text to speech via multi-provider api.
- create text completion via providers
- tgi generate
- text classification
- classify text
- translate text between languages.
- create text completion via multi-provider api.
- text generation
- create text embeddings via multi-provider api.
- chat completion
- summarize text content.
- text completions
- transcribe speech
- tokenize input text and return token ids.
- hugging face
- run inference
- create chat completion via providers
- ai
- providers chat completion
- transcribe audio via multi-provider api.
- generate text using the tgi native endpoint.
- generate image
- classify text into categories
- compute similarity between sentences.
- summarize text content
- transcribe audio to text using automatic speech recognition.
- classify text into predefined categories.
- generate text using the inference api
- text embeddings
- generate images from text prompts.
- providers transcribe
- create chat completions using tgi openai-compatible messages api.
- classify image
- providers text to speech
- image generation
- generate images from text
- translate text between languages
- run inference on any hugging face model by model id.
- extract feature vectors from text for embeddings.
- create embeddings
- providers generate image
- summarize text
- fill in masked tokens in text.
- answer questions based on provided context.
- openai-compatible chat completions
- detect objects
- tgi server info
- generate text
- machine learning
- text summarization
- classify text without predefined training labels.
- tgi tokenize
- list models available across all inference providers.
- providers create embeddings
- extract features
- generate text with a specific model
- translate
- run inference on a model via the inference api
- fill mask
- generate images via multi-provider api.
- classify images into categories.
- providers text completion
- text translation
- answer question
- list provider models
- get tgi server information and deployed model details.
- zero shot classify
- tgi chat completions
- generate text using a language model via the inference api.
slug: model-inference
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
