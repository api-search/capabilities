---
categories: []
consumed_apis: []
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
- compare faces
- face liveness
- get the results of a face liveness session
- asynchronous analysis of stored and streaming video
- detect faces and analyze facial attributes
- create session
- text detection
- detect labels
- asynchronous label detection in stored videos
- detect explicit, inappropriate, or violent content in an image for content moderation
- detect labels and objects in images
- identify celebrities in an image
- synchronous analysis of images for labels, faces, text, and moderation
- machine learning
- detect image labels
- list face collections
- search faces by image
- detect objects, scenes, and concepts in an image
- moderate image content
- retrieve face liveness session results
- create a face liveness verification session to confirm a user is physically present
- detect text
- detect objects, scenes, and concepts in an image using amazon rekognition
- start
- get liveness results
- create a new face collection for storing and indexing face data
- manage faces in a collection
- get the results of an asynchronous video label detection job
- detect and extract text from an image
- detect and extract printed and handwritten text from an image
- index faces into a collection
- create face collection
- custom labels
- unified computer vision, identity verification, and content moderation workflows
- face comparison, collection search, and liveness detection for user identity
- Content Moderator
- get the results of a video label detection job
- detect faces
- search for matching faces in a collection using an image
- content moderation for inappropriate imagery
- detect custom labels
- Security Engineer
- celebrity recognition in images
- face liveness verification for fraud prevention
- image analysis
- manage face collections
- start asynchronous detection of labels in a video stored in amazon s3
- search by image
- detect inappropriate content
- create a new face collection
- video analysis
- content moderation
- identity verification
- list all face collections
- detect unsafe or explicit content in an image
- get results
- deep learning
- search a face collection for faces matching a provided image
- facial recognition
- create a face liveness verification session
- object detection
- trust and safety teams moderating user-generated content for inappropriate or explicit imagery.
- security teams using facial recognition and liveness detection for identity verification and fraud prevention.
- compare faces for identity verification
- identify celebrities in an image and return names and reference urls
- computer vision
- detect faces in an image and return facial attributes including age range, emotions, and smile
- recognize celebrities
- extract text from images
- search face collections for matching identities
- celebrity recognition
- get video label detection results
- amazon rekognition
- start asynchronous label detection in a video
- compare a face in a source image with faces in a target image for identity verification
- list
- recognize
- Application Developer
- create
- start video label detection
- developers building apps with computer vision features such as image search, face login, and text extraction.
- create liveness session
- detect custom labels in an image using a trained amazon rekognition custom labels model
- list all face collections in the aws account
- detect and analyze facial attributes
- compare a face in a source image with a target image
- index faces in collection
- get the confidence score and status from a face liveness verification session
- index
- detect text in image
- index faces from an image into a face collection for future searching
slug: computer-vision-workflows
source_filename: computer-vision-workflows.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Rekognition Computer Vision Workflows\n  description: Unified computer vision workflows combining image analysis, facial recognition, content moderation, and identity\n    verification capabilities for developers and security teams.\n  tags:\n  - Amazon Rekognition\n  - Computer Vision\n  - Identity Verification\n  - Content Moderation\n  - Facial Recognition\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: rekognition\n    baseUri: https://rekognition.amazonaws.com\n    description: Amazon Rekognition image and video analysis API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: image-analysis\n      path: /\n\
  \      description: Image analysis operations\n      operations:\n      - name: detect-labels\n        method: POST\n        description: Detect labels in an image\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: AWS target operation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: detect-faces\n        method: POST\n        description: Detect faces in an image\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: AWS target operation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: compare-faces\n        method: POST\n        description: Compare faces across images\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: detect-text\n        method: POST\n        description: Detect text in an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: detect-moderation-labels\n        method: POST\n        description: Detect inappropriate content in an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: recognize-celebrities\n        method: POST\n        description: Recognize celebrities in an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: detect-custom-labels\n        method: POST\n        description: Detect custom labels using a trained model\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: face-collections\n      path: /\n      description: Face collection management\n      operations:\n      - name: create-collection\n        method: POST\n        description: Create a face collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-collections\n        method: POST\n        description: List face collections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: index-faces\n        method: POST\n        description: Index faces into a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-faces-by-image\n        method: POST\n        description: Search for matching faces using an image\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: video-analysis\n      path: /\n      description: Stored video analysis operations\n      operations:\n      - name: start-label-detection\n        method: POST\n        description: Start asynchronous label detection in video\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-label-detection\n        method: POST\n        description: Get label detection results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: face-liveness\n      path: /\n      description: Face liveness detection operations\n      operations:\n      - name: create-face-liveness-session\n        method: POST\n        description: Create a face liveness verification session\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-face-liveness-session-results\n        method: POST\n        description: Get face liveness session results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: computer-vision-api\n    description: Unified REST API for computer vision analysis, identity verification, and content moderation.\n    resources:\n    - path: /v1/analyze/labels\n      name: label-detection\n      description: Detect labels and objects in images\n      operations:\n      - method: POST\n        name: detect-labels\n        description: Detect objects, scenes, and concepts in an image\n        call: rekognition.detect-labels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analyze/faces\n      name: face-analysis\n      description: Detect and analyze\
  \ facial attributes\n      operations:\n      - method: POST\n        name: detect-faces\n        description: Detect faces and analyze facial attributes\n        call: rekognition.detect-faces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analyze/text\n      name: text-detection\n      description: Extract text from images\n      operations:\n      - method: POST\n        name: detect-text\n        description: Detect and extract text from an image\n        call: rekognition.detect-text\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/moderation/labels\n      name: content-moderation\n      description: Content moderation for inappropriate imagery\n      operations:\n      - method: POST\n        name: detect-inappropriate-content\n        description: Detect unsafe or explicit content in an image\n        call: rekognition.detect-moderation-labels\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/identity/compare\n      name: face-comparison\n      description: Compare faces for identity verification\n      operations:\n      - method: POST\n        name: compare-faces\n        description: Compare a face in a source image with a target image\n        call: rekognition.compare-faces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/identity/search\n      name: face-search\n      description: Search face collections for matching identities\n      operations:\n      - method: POST\n        name: search-by-image\n        description: Search for matching faces in a collection using an image\n        call: rekognition.search-faces-by-image\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/liveness/sessions\n      name: liveness-verification\n      description: Face liveness verification for fraud prevention\n      operations:\n      - method: POST\n        name:\
  \ create-session\n        description: Create a face liveness verification session\n        call: rekognition.create-face-liveness-session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/liveness/sessions/{session_id}/results\n      name: liveness-results\n      description: Retrieve face liveness session results\n      operations:\n      - method: GET\n        name: get-results\n        description: Get the results of a face liveness session\n        call: rekognition.get-face-liveness-session-results\n        with:\n          SessionId: rest.session_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/celebrities\n      name: celebrity-recognition\n      description: Celebrity recognition in images\n      operations:\n      - method: POST\n        name: recognize\n        description: Identify celebrities in an image\n        call: rekognition.recognize-celebrities\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /v1/collections\n      name: face-collections\n      description: Manage face collections\n      operations:\n      - method: GET\n        name: list\n        description: List all face collections\n        call: rekognition.list-collections\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create\n        description: Create a new face collection\n        call: rekognition.create-collection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/collections/{collection_id}/faces\n      name: collection-faces\n      description: Manage faces in a collection\n      operations:\n      - method: POST\n        name: index\n        description: Index faces into a collection\n        call: rekognition.index-faces\n        with:\n          CollectionId: rest.collection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/videos/labels\n      name: video-label-detection\n      description: Asynchronous label detection in stored videos\n      operations:\n      - method: POST\n        name: start\n        description: Start asynchronous label detection in a video\n        call: rekognition.start-label-detection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/videos/labels/{job_id}\n      name: video-label-results\n      description: Get video label detection results\n      operations:\n      - method: GET\n        name: get-results\n        description: Get the results of a video label detection job\n        call: rekognition.get-label-detection\n        with:\n          JobId: rest.job_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: computer-vision-mcp\n    transport: http\n    description: MCP server for AI-assisted computer vision, identity verification, and content moderation\
  \ workflows.\n    tools:\n    - name: detect-image-labels\n      description: Detect objects, scenes, and concepts in an image using Amazon Rekognition\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rekognition.detect-labels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: detect-faces\n      description: Detect faces in an image and return facial attributes including age range, emotions, and smile\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rekognition.detect-faces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: compare-faces\n      description: Compare a face in a source image with faces in a target image for identity verification\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rekognition.compare-faces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: detect-text-in-image\n      description: Detect and\
  \ extract printed and handwritten text from an image\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rekognition.detect-text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: moderate-image-content\n      description: Detect explicit, inappropriate, or violent content in an image for content moderation\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rekognition.detect-moderation-labels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recognize-celebrities\n      description: Identify celebrities in an image and return names and reference URLs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rekognition.recognize-celebrities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: detect-custom-labels\n      description: Detect custom labels in an image using a trained Amazon Rekognition Custom Labels model\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: rekognition.detect-custom-labels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-face-collection\n      description: Create a new face collection for storing and indexing face data\n      hints:\n        readOnly: false\n        openWorld: false\n      call: rekognition.create-collection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-face-collections\n      description: List all face collections in the AWS account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rekognition.list-collections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: index-faces-in-collection\n      description: Index faces from an image into a face collection for future searching\n      hints:\n        readOnly: false\n        openWorld: false\n      call: rekognition.index-faces\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: search-faces-by-image\n      description: Search a face collection for faces matching a provided image\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rekognition.search-faces-by-image\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-liveness-session\n      description: Create a face liveness verification session to confirm a user is physically present\n      hints:\n        readOnly: false\n        openWorld: false\n      call: rekognition.create-face-liveness-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-liveness-results\n      description: Get the confidence score and status from a face liveness verification session\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rekognition.get-face-liveness-session-results\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-video-label-detection\n\
  \      description: Start asynchronous detection of labels in a video stored in Amazon S3\n      hints:\n        readOnly: false\n        openWorld: false\n      call: rekognition.start-label-detection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-video-label-detection-results\n      description: Get the results of an asynchronous video label detection job\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rekognition.get-label-detection\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
