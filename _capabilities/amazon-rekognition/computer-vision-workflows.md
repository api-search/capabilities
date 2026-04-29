---
categories: []
consumed_apis:
- rekognition
description: Unified computer vision workflows combining image analysis, facial recognition, content moderation, and identity verification capabilities for developers and security teams.
layout: capability
name: Amazon Rekognition Computer Vision Workflows
operations:
- description: Detect objects, scenes, and concepts in an image
  method: POST
  name: detect-labels
  path: /v1/analyze/labels
- description: Detect faces and analyze facial attributes
  method: POST
  name: detect-faces
  path: /v1/analyze/faces
- description: Detect and extract text from an image
  method: POST
  name: detect-text
  path: /v1/analyze/text
- description: Detect unsafe or explicit content in an image
  method: POST
  name: detect-inappropriate-content
  path: /v1/moderation/labels
- description: Compare a face in a source image with a target image
  method: POST
  name: compare-faces
  path: /v1/identity/compare
- description: Search for matching faces in a collection using an image
  method: POST
  name: search-by-image
  path: /v1/identity/search
- description: Create a face liveness verification session
  method: POST
  name: create-session
  path: /v1/liveness/sessions
- description: Get the results of a face liveness session
  method: GET
  name: get-results
  path: /v1/liveness/sessions/{session_id}/results
- description: Identify celebrities in an image
  method: POST
  name: recognize
  path: /v1/celebrities
- description: List all face collections
  method: GET
  name: list
  path: /v1/collections
- description: Create a new face collection
  method: POST
  name: create
  path: /v1/collections
- description: Index faces into a collection
  method: POST
  name: index
  path: /v1/collections/{collection_id}/faces
- description: Start asynchronous label detection in a video
  method: POST
  name: start
  path: /v1/videos/labels
- description: Get the results of a video label detection job
  method: GET
  name: get-results
  path: /v1/videos/labels/{job_id}
personas: []
provider_name: Amazon Rekognition
provider_slug: amazon-rekognition
search_terms:
- manage face collections
- start
- synchronous analysis of images for labels, faces, text, and moderation
- detect image labels
- asynchronous label detection in stored videos
- Security Engineer
- start asynchronous detection of labels in a video stored in amazon s3
- unified computer vision, identity verification, and content moderation workflows
- compare faces
- detect faces
- get the results of a video label detection job
- detect faces in an image and return facial attributes including age range, emotions, and smile
- identify celebrities in an image
- detect custom labels in an image using a trained amazon rekognition custom labels model
- create a new face collection for storing and indexing face data
- detect custom labels
- trust and safety teams moderating user-generated content for inappropriate or explicit imagery.
- compare a face in a source image with faces in a target image for identity verification
- search for matching faces in a collection using an image
- index faces into a collection
- detect and analyze facial attributes
- create session
- detect faces and analyze facial attributes
- identity verification
- search face collections for matching identities
- identify celebrities in an image and return names and reference urls
- content moderation
- moderate image content
- machine learning
- detect text
- create a face liveness verification session to confirm a user is physically present
- create face collection
- get the results of a face liveness session
- extract text from images
- amazon rekognition
- computer vision
- search by image
- recognize
- content moderation for inappropriate imagery
- facial recognition
- create
- detect labels and objects in images
- index faces in collection
- retrieve face liveness session results
- detect objects, scenes, and concepts in an image
- developers building apps with computer vision features such as image search, face login, and text extraction.
- asynchronous analysis of stored and streaming video
- deep learning
- Content Moderator
- start video label detection
- face liveness verification for fraud prevention
- image analysis
- video analysis
- manage faces in a collection
- index faces from an image into a face collection for future searching
- search faces by image
- detect explicit, inappropriate, or violent content in an image for content moderation
- face liveness
- list all face collections
- create a new face collection
- index
- Application Developer
- list all face collections in the aws account
- search a face collection for faces matching a provided image
- detect unsafe or explicit content in an image
- recognize celebrities
- compare faces for identity verification
- get results
- get the results of an asynchronous video label detection job
- detect objects, scenes, and concepts in an image using amazon rekognition
- list
- celebrity recognition in images
- get video label detection results
- detect text in image
- celebrity recognition
- custom labels
- get the confidence score and status from a face liveness verification session
- create liveness session
- aws
- start asynchronous label detection in a video
- detect and extract text from an image
- object detection
- security teams using facial recognition and liveness detection for identity verification and fraud prevention.
- text detection
- detect and extract printed and handwritten text from an image
- list face collections
- detect inappropriate content
- compare a face in a source image with a target image
- detect labels
- get liveness results
- face comparison, collection search, and liveness detection for user identity
- create a face liveness verification session
slug: computer-vision-workflows
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon Rekognition Computer Vision Workflows\n  description: Unified computer vision workflows combining image analysis, facial recognition, content moderation, and identity verification capabilities for developers and security teams.\n  tags:\n    - Amazon Rekognition\n    - Computer Vision\n    - Identity Verification\n    - Content Moderation\n    - Facial Recognition\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: rekognition\n      location: ./shared/rekognition.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: computer-vision-api\n      description: Unified REST API for computer vision analysis, identity verification, and content moderation.\n      resources:\n        - path: /v1/analyze/labels\n\
  \          name: label-detection\n          description: Detect labels and objects in images\n          operations:\n            - method: POST\n              name: detect-labels\n              description: Detect objects, scenes, and concepts in an image\n              call: \"rekognition.detect-labels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/analyze/faces\n          name: face-analysis\n          description: Detect and analyze facial attributes\n          operations:\n            - method: POST\n              name: detect-faces\n              description: Detect faces and analyze facial attributes\n              call: \"rekognition.detect-faces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/analyze/text\n          name: text-detection\n          description: Extract text from images\n          operations:\n            - method:\
  \ POST\n              name: detect-text\n              description: Detect and extract text from an image\n              call: \"rekognition.detect-text\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/moderation/labels\n          name: content-moderation\n          description: Content moderation for inappropriate imagery\n          operations:\n            - method: POST\n              name: detect-inappropriate-content\n              description: Detect unsafe or explicit content in an image\n              call: \"rekognition.detect-moderation-labels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/identity/compare\n          name: face-comparison\n          description: Compare faces for identity verification\n          operations:\n            - method: POST\n              name: compare-faces\n              description: Compare a face\
  \ in a source image with a target image\n              call: \"rekognition.compare-faces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/identity/search\n          name: face-search\n          description: Search face collections for matching identities\n          operations:\n            - method: POST\n              name: search-by-image\n              description: Search for matching faces in a collection using an image\n              call: \"rekognition.search-faces-by-image\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/liveness/sessions\n          name: liveness-verification\n          description: Face liveness verification for fraud prevention\n          operations:\n            - method: POST\n              name: create-session\n              description: Create a face liveness verification session\n              call: \"rekognition.create-face-liveness-session\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/liveness/sessions/{session_id}/results\n          name: liveness-results\n          description: Retrieve face liveness session results\n          operations:\n            - method: GET\n              name: get-results\n              description: Get the results of a face liveness session\n              call: \"rekognition.get-face-liveness-session-results\"\n              with:\n                SessionId: \"rest.session_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/celebrities\n          name: celebrity-recognition\n          description: Celebrity recognition in images\n          operations:\n            - method: POST\n              name: recognize\n              description: Identify celebrities in an image\n              call: \"rekognition.recognize-celebrities\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/collections\n          name: face-collections\n          description: Manage face collections\n          operations:\n            - method: GET\n              name: list\n              description: List all face collections\n              call: \"rekognition.list-collections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create\n              description: Create a new face collection\n              call: \"rekognition.create-collection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/collections/{collection_id}/faces\n          name: collection-faces\n          description: Manage faces in a collection\n          operations:\n            - method: POST\n              name: index\n              description: Index faces into a\
  \ collection\n              call: \"rekognition.index-faces\"\n              with:\n                CollectionId: \"rest.collection_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/videos/labels\n          name: video-label-detection\n          description: Asynchronous label detection in stored videos\n          operations:\n            - method: POST\n              name: start\n              description: Start asynchronous label detection in a video\n              call: \"rekognition.start-label-detection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/videos/labels/{job_id}\n          name: video-label-results\n          description: Get video label detection results\n          operations:\n            - method: GET\n              name: get-results\n              description: Get the results of a video label detection job\n         \
  \     call: \"rekognition.get-label-detection\"\n              with:\n                JobId: \"rest.job_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: computer-vision-mcp\n      transport: http\n      description: MCP server for AI-assisted computer vision, identity verification, and content moderation workflows.\n      tools:\n        - name: detect-image-labels\n          description: Detect objects, scenes, and concepts in an image using Amazon Rekognition\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rekognition.detect-labels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: detect-faces\n          description: Detect faces in an image and return facial attributes including age range, emotions, and smile\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"rekognition.detect-faces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: compare-faces\n          description: Compare a face in a source image with faces in a target image for identity verification\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rekognition.compare-faces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: detect-text-in-image\n          description: Detect and extract printed and handwritten text from an image\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rekognition.detect-text\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: moderate-image-content\n          description: Detect explicit, inappropriate, or violent content in an image for content moderation\n          hints:\n    \
  \        readOnly: true\n            openWorld: true\n          call: \"rekognition.detect-moderation-labels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: recognize-celebrities\n          description: Identify celebrities in an image and return names and reference URLs\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rekognition.recognize-celebrities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: detect-custom-labels\n          description: Detect custom labels in an image using a trained Amazon Rekognition Custom Labels model\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rekognition.detect-custom-labels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-face-collection\n          description: Create a new face collection\
  \ for storing and indexing face data\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"rekognition.create-collection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-face-collections\n          description: List all face collections in the AWS account\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rekognition.list-collections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: index-faces-in-collection\n          description: Index faces from an image into a face collection for future searching\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"rekognition.index-faces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-faces-by-image\n          description: Search a face collection\
  \ for faces matching a provided image\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rekognition.search-faces-by-image\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-liveness-session\n          description: Create a face liveness verification session to confirm a user is physically present\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"rekognition.create-face-liveness-session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-liveness-results\n          description: Get the confidence score and status from a face liveness verification session\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rekognition.get-face-liveness-session-results\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: start-video-label-detection\n          description: Start asynchronous detection of labels in a video stored in Amazon S3\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"rekognition.start-label-detection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-video-label-detection-results\n          description: Get the results of an asynchronous video label detection job\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rekognition.get-label-detection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-rekognition/refs/heads/main/capabilities/computer-vision-workflows.yaml
tags:
- Amazon Rekognition
- Computer Vision
- Identity Verification
- Content Moderation
- Facial Recognition
tools:
- description: Detect objects, scenes, and concepts in an image using Amazon Rekognition
  hints:
    openWorld: true
    readOnly: true
  name: detect-image-labels
- description: Detect faces in an image and return facial attributes including age range, emotions, and smile
  hints:
    openWorld: true
    readOnly: true
  name: detect-faces
- description: Compare a face in a source image with faces in a target image for identity verification
  hints:
    openWorld: true
    readOnly: true
  name: compare-faces
- description: Detect and extract printed and handwritten text from an image
  hints:
    openWorld: true
    readOnly: true
  name: detect-text-in-image
- description: Detect explicit, inappropriate, or violent content in an image for content moderation
  hints:
    openWorld: true
    readOnly: true
  name: moderate-image-content
- description: Identify celebrities in an image and return names and reference URLs
  hints:
    openWorld: true
    readOnly: true
  name: recognize-celebrities
- description: Detect custom labels in an image using a trained Amazon Rekognition Custom Labels model
  hints:
    openWorld: true
    readOnly: true
  name: detect-custom-labels
- description: Create a new face collection for storing and indexing face data
  hints:
    openWorld: false
    readOnly: false
  name: create-face-collection
- description: List all face collections in the AWS account
  hints:
    openWorld: false
    readOnly: true
  name: list-face-collections
- description: Index faces from an image into a face collection for future searching
  hints:
    openWorld: false
    readOnly: false
  name: index-faces-in-collection
- description: Search a face collection for faces matching a provided image
  hints:
    openWorld: false
    readOnly: true
  name: search-faces-by-image
- description: Create a face liveness verification session to confirm a user is physically present
  hints:
    openWorld: false
    readOnly: false
  name: create-liveness-session
- description: Get the confidence score and status from a face liveness verification session
  hints:
    openWorld: false
    readOnly: true
  name: get-liveness-results
- description: Start asynchronous detection of labels in a video stored in Amazon S3
  hints:
    openWorld: false
    readOnly: false
  name: start-video-label-detection
- description: Get the results of an asynchronous video label detection job
  hints:
    openWorld: false
    readOnly: true
  name: get-video-label-detection-results
---
