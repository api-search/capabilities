---
api_specs:
- filename: shutterstock-openapi.yml
  format: yaml
  label: shutterstock
  slug: shutterstock
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/shutterstock/refs/heads/main/openapi/shutterstock-openapi.yml
categories: []
consumed_apis:
- shutterstock
description: Workflow capability for discovering, evaluating, and licensing stock media from Shutterstock's library of 350M+ assets. Combines image search, video search, audio search, editorial content, computer vision similarity matching, collection management, and licensing operations into a unified creative asset workflow for content teams, designers, marketers, and developers.
layout: capability
name: Shutterstock Media Search And Licensing
operations:
- description: Search Shutterstock stock photos, illustrations, and vectors
  method: GET
  name: search-images
  path: /v1/images
- description: Get detailed metadata for a specific stock image
  method: GET
  name: get-image
  path: /v1/images/{id}
- description: Find stock images visually similar to a reference image
  method: GET
  name: get-similar-images
  path: /v1/images/{id}/similar
- description: Get keyword suggestions for image searches
  method: GET
  name: get-suggestions
  path: /v1/images/suggestions
- description: List all available Shutterstock image categories
  method: GET
  name: list-categories
  path: /v1/images/categories
- description: License one or more stock images for download
  method: POST
  name: license-images
  path: /v1/images/licenses
- description: List previously licensed images
  method: GET
  name: list-image-licenses
  path: /v1/images/licenses
- description: Search Shutterstock stock video clips
  method: GET
  name: search-videos
  path: /v1/videos
- description: Get detailed metadata for a specific stock video
  method: GET
  name: get-video
  path: /v1/videos/{id}
- description: License one or more stock videos for download
  method: POST
  name: license-videos
  path: /v1/videos/licenses
- description: Search Shutterstock music tracks and audio content
  method: GET
  name: search-audio
  path: /v1/audio
- description: License one or more music tracks
  method: POST
  name: license-audio
  path: /v1/audio/licenses
- description: Search editorial images for news and documentary use
  method: GET
  name: search-editorial
  path: /v1/editorial/images
- description: Find images visually similar to an uploaded reference image
  method: GET
  name: find-similar-images
  path: /v1/cv/similar
- description: Get AI-suggested keywords for an uploaded image
  method: GET
  name: get-keywords
  path: /v1/cv/keywords
- description: List user image collections
  method: GET
  name: list-collections
  path: /v1/collections
- description: Create a new image collection
  method: POST
  name: create-collection
  path: /v1/collections
- description: Get authenticated user account details
  method: GET
  name: get-user
  path: /v1/user
- description: List active user subscriptions and allotments
  method: GET
  name: get-subscriptions
  path: /v1/user/subscriptions
personas: []
provider_name: Shutterstock
provider_slug: shutterstock
search_terms:
- stock video search and discovery
- get detailed metadata for a specific stock image
- search shutterstock stock video clips
- get video
- license one or more shutterstock video clips for download.
- license one or more shutterstock music tracks for download.
- get similar images
- license audio
- videos
- get user
- search editorial images for news and documentary use
- stock images
- search images
- get subscriptions
- search shutterstock stock photos, illustrations, and vectors
- get detailed metadata for a specific shutterstock image by id.
- get image
- list all available shutterstock image categories
- list previously licensed images in the user's account history.
- collections
- search shutterstock's editorial image library for news, sports, entertainment, and documentary photography. requires country code.
- license one or more shutterstock stock images for download using a subscription allotment or on-demand purchase. returns download urls.
- list image categories
- audio licensing operations
- creative content
- create a new image collection to organize saved assets.
- license images
- music and audio track search
- create a new image collection
- search keyword suggestions for images
- license one or more stock images for download
- editorial news and event photography
- get search keyword suggestions for image discovery based on a partial query string.
- get image suggestions
- list active user subscriptions and allotments
- search shutterstock's library of royalty-free music tracks and audio content by keyword, genre, mood, and duration.
- ai-generated keyword suggestions from uploaded images
- get detailed metadata for a specific shutterstock video clip by id.
- search videos
- search shutterstock's library of 350m+ stock photos, illustrations, and vectors by keyword, color, orientation, category, and more. returns image metadata including preview urls and asset details.
- visually similar image recommendations
- list categories
- get authenticated user account details
- get ai-suggested keywords for an uploaded image
- get detailed metadata for a specific stock video
- image licensing operations
- list user image collections
- license one or more stock videos for download
- stock media
- audio
- get details about the authenticated shutterstock user account.
- list all available shutterstock image content categories for filtering.
- list collections
- available image content categories
- computer vision
- photos
- find shutterstock stock images that are visually similar to a specified image id. useful for finding alternative options or creating visual consistency.
- stock image search and discovery
- get keyword suggestions for image searches
- search editorial images
- user account details
- license videos
- find similar images by upload
- use computer vision to find shutterstock images visually similar to an uploaded reference image. requires an asset_id from the cv image upload endpoint.
- individual video details
- find images visually similar to an uploaded reference image
- create collection
- video licensing operations
- editorial
- licensing
- search audio
- user media collection management
- use shutterstock's ai to extract relevant keywords from an uploaded image, useful for finding related stock content.
- get ai keywords
- images
- individual image details
- list the authenticated user's image collections.
- media
- list previously licensed images
- find stock images visually similar to a reference image
- license one or more music tracks
- search shutterstock music tracks and audio content
- list image licenses
- search editorial
- get keywords
- get suggestions
- search shutterstock's library of stock video clips by keyword, resolution, duration, and category.
- list active shutterstock subscriptions and remaining download allotments.
- find similar images
- computer vision visual similarity search
- user subscription information
slug: media-search-and-licensing
source_filename: media-search-and-licensing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Shutterstock Media Search And Licensing\"\n  description: >-\n    Workflow capability for discovering, evaluating, and licensing stock media\n    from Shutterstock's library of 350M+ assets. Combines image search, video\n    search, audio search, editorial content, computer vision similarity matching,\n    collection management, and licensing operations into a unified creative asset\n    workflow for content teams, designers, marketers, and developers.\n  tags:\n    - Images\n    - Videos\n    - Audio\n    - Stock Media\n    - Licensing\n    - Creative Content\n    - Computer Vision\n    - Editorial\n    - Collections\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SHUTTERSTOCK_ACCESS_TOKEN: SHUTTERSTOCK_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: shutterstock\n      location: ./shared/shutterstock.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace:\
  \ shutterstock-media-licensing-api\n      description: \"Unified REST API for Shutterstock media discovery and licensing.\"\n      resources:\n        - path: /v1/images\n          name: images\n          description: Stock image search and discovery\n          operations:\n            - method: GET\n              name: search-images\n              description: Search Shutterstock stock photos, illustrations, and vectors\n              call: \"shutterstock.search-images\"\n              with:\n                query: \"rest.query\"\n                image_type: \"rest.image_type\"\n                orientation: \"rest.orientation\"\n                color: \"rest.color\"\n                category: \"rest.category\"\n                per_page: \"rest.per_page\"\n                page: \"rest.page\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/images/{id}\n          name: image-detail\n\
  \          description: Individual image details\n          operations:\n            - method: GET\n              name: get-image\n              description: Get detailed metadata for a specific stock image\n              call: \"shutterstock.get-image\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/images/{id}/similar\n          name: similar-images\n          description: Visually similar image recommendations\n          operations:\n            - method: GET\n              name: get-similar-images\n              description: Find stock images visually similar to a reference image\n              call: \"shutterstock.get-similar-images\"\n              with:\n                id: \"rest.id\"\n                per_page: \"rest.per_page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/images/suggestions\n\
  \          name: image-suggestions\n          description: Search keyword suggestions for images\n          operations:\n            - method: GET\n              name: get-suggestions\n              description: Get keyword suggestions for image searches\n              call: \"shutterstock.get-image-search-suggestions\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/images/categories\n          name: image-categories\n          description: Available image content categories\n          operations:\n            - method: GET\n              name: list-categories\n              description: List all available Shutterstock image categories\n              call: \"shutterstock.list-image-categories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/images/licenses\n          name: image-licenses\n\
  \          description: Image licensing operations\n          operations:\n            - method: POST\n              name: license-images\n              description: License one or more stock images for download\n              call: \"shutterstock.license-images\"\n              with:\n                images: \"rest.images\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-image-licenses\n              description: List previously licensed images\n              call: \"shutterstock.list-image-licenses\"\n              with:\n                image_id: \"rest.image_id\"\n                per_page: \"rest.per_page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/videos\n          name: videos\n          description: Stock video search and discovery\n          operations:\n            - method: GET\n             \
  \ name: search-videos\n              description: Search Shutterstock stock video clips\n              call: \"shutterstock.search-videos\"\n              with:\n                query: \"rest.query\"\n                resolution: \"rest.resolution\"\n                duration_from: \"rest.duration_from\"\n                per_page: \"rest.per_page\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/videos/{id}\n          name: video-detail\n          description: Individual video details\n          operations:\n            - method: GET\n              name: get-video\n              description: Get detailed metadata for a specific stock video\n              call: \"shutterstock.get-video\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/videos/licenses\n\
  \          name: video-licenses\n          description: Video licensing operations\n          operations:\n            - method: POST\n              name: license-videos\n              description: License one or more stock videos for download\n              call: \"shutterstock.license-videos\"\n              with:\n                videos: \"rest.videos\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/audio\n          name: audio\n          description: Music and audio track search\n          operations:\n            - method: GET\n              name: search-audio\n              description: Search Shutterstock music tracks and audio content\n              call: \"shutterstock.search-audio\"\n              with:\n                query: \"rest.query\"\n                genre: \"rest.genre\"\n                moods: \"rest.moods\"\n                duration_from: \"rest.duration_from\"\n                per_page: \"\
  rest.per_page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/audio/licenses\n          name: audio-licenses\n          description: Audio licensing operations\n          operations:\n            - method: POST\n              name: license-audio\n              description: License one or more music tracks\n              call: \"shutterstock.license-audio\"\n              with:\n                audio: \"rest.audio\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/editorial/images\n          name: editorial-images\n          description: Editorial news and event photography\n          operations:\n            - method: GET\n              name: search-editorial\n              description: Search editorial images for news and documentary use\n              call: \"shutterstock.search-editorial-images\"\n              with:\n               \
  \ query: \"rest.query\"\n                country: \"rest.country\"\n                per_page: \"rest.per_page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cv/similar\n          name: visual-similarity\n          description: Computer vision visual similarity search\n          operations:\n            - method: GET\n              name: find-similar-images\n              description: Find images visually similar to an uploaded reference image\n              call: \"shutterstock.find-similar-images\"\n              with:\n                asset_id: \"rest.asset_id\"\n                per_page: \"rest.per_page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cv/keywords\n          name: ai-keywords\n          description: AI-generated keyword suggestions from uploaded images\n          operations:\n            - method: GET\n            \
  \  name: get-keywords\n              description: Get AI-suggested keywords for an uploaded image\n              call: \"shutterstock.get-keywords\"\n              with:\n                asset_id: \"rest.asset_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/collections\n          name: collections\n          description: User media collection management\n          operations:\n            - method: GET\n              name: list-collections\n              description: List user image collections\n              call: \"shutterstock.list-image-collections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-collection\n              description: Create a new image collection\n              call: \"shutterstock.create-image-collection\"\n              with:\n                name: \"rest.name\"\n            \
  \  outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/user\n          name: user-account\n          description: User account details\n          operations:\n            - method: GET\n              name: get-user\n              description: Get authenticated user account details\n              call: \"shutterstock.get-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/user/subscriptions\n          name: user-subscriptions\n          description: User subscription information\n          operations:\n            - method: GET\n              name: get-subscriptions\n              description: List active user subscriptions and allotments\n              call: \"shutterstock.get-subscriptions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: shutterstock-media-licensing-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted stock media discovery, evaluation, and licensing.\"\n      tools:\n        - name: search-images\n          description: >-\n            Search Shutterstock's library of 350M+ stock photos, illustrations,\n            and vectors by keyword, color, orientation, category, and more.\n            Returns image metadata including preview URLs and asset details.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shutterstock.search-images\"\n          with:\n            query: \"tools.query\"\n            image_type: \"tools.image_type\"\n            orientation: \"tools.orientation\"\n            color: \"tools.color\"\n            category: \"tools.category\"\n            per_page: \"tools.per_page\"\n            page: \"tools.page\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-image\n\
  \          description: Get detailed metadata for a specific Shutterstock image by ID.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shutterstock.get-image\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-similar-images\n          description: >-\n            Find Shutterstock stock images that are visually similar to a\n            specified image ID. Useful for finding alternative options or\n            creating visual consistency.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shutterstock.get-similar-images\"\n          with:\n            id: \"tools.id\"\n            per_page: \"tools.per_page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-image-suggestions\n          description: >-\n            Get search keyword\
  \ suggestions for image discovery based on a\n            partial query string.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shutterstock.get-image-search-suggestions\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-image-categories\n          description: List all available Shutterstock image content categories for filtering.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shutterstock.list-image-categories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: license-images\n          description: >-\n            License one or more Shutterstock stock images for download using\n            a subscription allotment or on-demand purchase. Returns download URLs.\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n            idempotent: false\n          call: \"shutterstock.license-images\"\n          with:\n            images: \"tools.images\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-image-licenses\n          description: List previously licensed images in the user's account history.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shutterstock.list-image-licenses\"\n          with:\n            image_id: \"tools.image_id\"\n            per_page: \"tools.per_page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-videos\n          description: >-\n            Search Shutterstock's library of stock video clips by keyword,\n            resolution, duration, and category.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shutterstock.search-videos\"\n          with:\n\
  \            query: \"tools.query\"\n            resolution: \"tools.resolution\"\n            duration_from: \"tools.duration_from\"\n            per_page: \"tools.per_page\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-video\n          description: Get detailed metadata for a specific Shutterstock video clip by ID.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shutterstock.get-video\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: license-videos\n          description: License one or more Shutterstock video clips for download.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"shutterstock.license-videos\"\n          with:\n            videos: \"tools.videos\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-audio\n          description: >-\n            Search Shutterstock's library of royalty-free music tracks and\n            audio content by keyword, genre, mood, and duration.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shutterstock.search-audio\"\n          with:\n            query: \"tools.query\"\n            genre: \"tools.genre\"\n            moods: \"tools.moods\"\n            duration_from: \"tools.duration_from\"\n            per_page: \"tools.per_page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: license-audio\n          description: License one or more Shutterstock music tracks for download.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"shutterstock.license-audio\"\n    \
  \      with:\n            audio: \"tools.audio\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-editorial-images\n          description: >-\n            Search Shutterstock's editorial image library for news, sports,\n            entertainment, and documentary photography. Requires country code.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shutterstock.search-editorial-images\"\n          with:\n            query: \"tools.query\"\n            country: \"tools.country\"\n            per_page: \"tools.per_page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-similar-images-by-upload\n          description: >-\n            Use computer vision to find Shutterstock images visually similar\n            to an uploaded reference image. Requires an asset_id from the\n            CV image upload endpoint.\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"shutterstock.find-similar-images\"\n          with:\n            asset_id: \"tools.asset_id\"\n            per_page: \"tools.per_page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-ai-keywords\n          description: >-\n            Use Shutterstock's AI to extract relevant keywords from an uploaded\n            image, useful for finding related stock content.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shutterstock.get-keywords\"\n          with:\n            asset_id: \"tools.asset_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-collections\n          description: List the authenticated user's image collections.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shutterstock.list-image-collections\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-collection\n          description: Create a new image collection to organize saved assets.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"shutterstock.create-image-collection\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user\n          description: Get details about the authenticated Shutterstock user account.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shutterstock.get-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-subscriptions\n          description: List active Shutterstock subscriptions and remaining download allotments.\n          hints:\n          \
  \  readOnly: true\n            openWorld: false\n          call: \"shutterstock.get-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shutterstock/refs/heads/main/capabilities/media-search-and-licensing.yaml
tags:
- Images
- Videos
- Audio
- Stock Media
- Licensing
- Creative Content
- Computer Vision
- Editorial
- Collections
tools:
- description: Search Shutterstock's library of 350M+ stock photos, illustrations, and vectors by keyword, color, orientation, category, and more. Returns image metadata including preview URLs and asset details.
  hints:
    openWorld: true
    readOnly: true
  name: search-images
- description: Get detailed metadata for a specific Shutterstock image by ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-image
- description: Find Shutterstock stock images that are visually similar to a specified image ID. Useful for finding alternative options or creating visual consistency.
  hints:
    openWorld: true
    readOnly: true
  name: get-similar-images
- description: Get search keyword suggestions for image discovery based on a partial query string.
  hints:
    openWorld: true
    readOnly: true
  name: get-image-suggestions
- description: List all available Shutterstock image content categories for filtering.
  hints:
    openWorld: false
    readOnly: true
  name: list-image-categories
- description: License one or more Shutterstock stock images for download using a subscription allotment or on-demand purchase. Returns download URLs.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: license-images
- description: List previously licensed images in the user's account history.
  hints:
    openWorld: false
    readOnly: true
  name: list-image-licenses
- description: Search Shutterstock's library of stock video clips by keyword, resolution, duration, and category.
  hints:
    openWorld: true
    readOnly: true
  name: search-videos
- description: Get detailed metadata for a specific Shutterstock video clip by ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-video
- description: License one or more Shutterstock video clips for download.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: license-videos
- description: Search Shutterstock's library of royalty-free music tracks and audio content by keyword, genre, mood, and duration.
  hints:
    openWorld: true
    readOnly: true
  name: search-audio
- description: License one or more Shutterstock music tracks for download.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: license-audio
- description: Search Shutterstock's editorial image library for news, sports, entertainment, and documentary photography. Requires country code.
  hints:
    openWorld: true
    readOnly: true
  name: search-editorial-images
- description: Use computer vision to find Shutterstock images visually similar to an uploaded reference image. Requires an asset_id from the CV image upload endpoint.
  hints:
    openWorld: true
    readOnly: true
  name: find-similar-images-by-upload
- description: Use Shutterstock's AI to extract relevant keywords from an uploaded image, useful for finding related stock content.
  hints:
    openWorld: false
    readOnly: true
  name: get-ai-keywords
- description: List the authenticated user's image collections.
  hints:
    openWorld: false
    readOnly: true
  name: list-collections
- description: Create a new image collection to organize saved assets.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-collection
- description: Get details about the authenticated Shutterstock user account.
  hints:
    openWorld: false
    readOnly: true
  name: get-user
- description: List active Shutterstock subscriptions and remaining download allotments.
  hints:
    openWorld: false
    readOnly: true
  name: get-subscriptions
---
