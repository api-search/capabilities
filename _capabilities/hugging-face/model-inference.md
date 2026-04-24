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
- providers text completion
- ai
- fill mask
- tgi tokenize
- list provider models
- providers generate image
- tokenize input text and return token ids.
- translate text between languages.
- create text embeddings via multi-provider api.
- detect objects
- text generation
- image generation
- create chat completion via providers
- fill in masked tokens in text.
- text completion
- get tgi server information and deployed model details.
- generate text
- providers text to speech
- inference
- run inference
- transcribe audio to text using automatic speech recognition.
- answer questions based on provided context.
- summarize text content
- hugging face
- tgi chat completions
- detect objects in images.
- providers create embeddings
- translate text between languages
- generate text using the inference api
- create chat completions using tgi openai-compatible messages api.
- openai-compatible chat completions
- generate images via multi-provider api.
- summarize text
- generate images from text
- classify text
- chat completion
- text embeddings
- list models available across all inference providers.
- classify images into categories.
- convert text to speech via multi-provider api.
- generate image
- run inference on any model
- classify image
- generate text using a language model via the inference api.
- answer question
- summarize text content.
- tgi server info
- compute similarity
- tgi generate
- transcribe audio via multi-provider api.
- run inference on a model via the inference api
- machine learning
- create embeddings
- extract features
- create text embeddings
- text completions
- create text completion via providers
- translate text
- classify text into predefined categories.
- compute similarity between sentences.
- generate text with a specific model
- run inference on any hugging face model by model id.
- generate text using the tgi native endpoint.
- classify text without predefined training labels.
- providers chat completion
- classify text into categories
- zero shot classify
- translate
- extract feature vectors from text for embeddings.
- summarize
- create text completion via multi-provider api.
- generate images from text prompts.
- text summarization
- text classification
- providers transcribe
- create chat completion via openai-compatible multi-provider api.
- text translation
- transcribe speech
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
