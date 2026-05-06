---
categories: []
consumed_apis: []
description: End-to-end creative asset production workflow combining AI content generation (Firefly), image editing and manipulation (Photoshop), and stock asset sourcing and licensing (Stock). Used by creative directors, production designers, and marketing teams to find, generate, edit, and finalize visual assets.
layout: capability
name: Adobe Creative Production
operations:
- description: Generate images from a text prompt using Firefly
  method: POST
  name: generate-images
  path: /v1/generations
- description: Generate images similar to a reference image
  method: POST
  name: generate-similar-images
  path: /v1/generations/similar
- description: Expand an image beyond its boundaries using Firefly
  method: POST
  name: expand-image
  path: /v1/expansions
- description: Fill a masked region with AI-generated content
  method: POST
  name: fill-image
  path: /v1/fills
- description: Generate and composite an AI object into a scene
  method: POST
  name: generate-composite
  path: /v1/composites
- description: Generate a video from a text prompt using Firefly
  method: POST
  name: generate-video
  path: /v1/videos
- description: Remove background from an image using Photoshop
  method: POST
  name: remove-background
  path: /v1/cutouts
- description: Create an alpha mask for an image
  method: POST
  name: create-mask
  path: /v1/masks
- description: Auto-crop an image to the primary product
  method: POST
  name: product-crop
  path: /v1/product-crops
- description: Create renditions from a PSD or image
  method: POST
  name: create-rendition
  path: /v1/renditions
- description: Manage layers in a PSD document
  method: POST
  name: manage-layers
  path: /v1/layers
- description: Edit text layers in a PSD document
  method: POST
  name: edit-text-layers
  path: /v1/text-edits
- description: Replace smart object content in a PSD
  method: POST
  name: edit-smart-object
  path: /v1/smart-objects
- description: Apply resize, flatten, or trim operations to a PSD
  method: POST
  name: apply-document-operations
  path: /v1/document-operations
- description: Create artboards in a PSD document
  method: POST
  name: create-artboard
  path: /v1/artboards
- description: Automatically straighten a rotated image
  method: POST
  name: straighten-image
  path: /v1/straighten-jobs
- description: Search the Adobe Stock library
  method: GET
  name: search-stock-files
  path: /v1/stock-files
- description: Get metadata for a specific stock file
  method: GET
  name: get-stock-file-metadata
  path: /v1/stock-files/{content_id}
- description: License a stock photo
  method: POST
  name: license-image
  path: /v1/licenses/images
- description: License a vector or illustration
  method: POST
  name: license-vector
  path: /v1/licenses/vectors
- description: License a stock video clip
  method: POST
  name: license-video
  path: /v1/licenses/videos
- description: Get the status of an async Firefly generation job
  method: GET
  name: get-firefly-job-status
  path: /v1/firefly-jobs/{jobId}
- description: Get the status of an async Photoshop job
  method: GET
  name: get-photoshop-job-status
  path: /v1/photoshop-jobs/{jobId}
personas: []
provider_name: Adobe Creative Suite
provider_slug: adobe-creative-suite
search_terms:
- create an alpha mask for an image
- generate and composite an ai object into a scene
- get the adobe stock content category tree
- psd text layer editing
- firefly generate similar images
- generate a video from a text prompt using firefly
- create renditions from a psd or image in jpeg, png, or tiff
- photography
- apply document operations
- license image
- photoshop create rendition
- ai image generation from text prompts
- ai-powered image expansion
- license vector
- license a stock photo
- stock asset search
- product crop
- fill image
- get metadata for a specific stock file
- apply resize, flatten, or trim operations to a psd document
- photoshop product crop
- image editing
- smart object replacement
- generate images from a text prompt using adobe firefly
- generate similar images
- ai video generation
- auto-crop an image to focus on the primary product
- generate images similar to a reference image using firefly
- remove background from an image using photoshop
- fill a masked region of an image with ai-generated content using firefly
- firefly get job status
- license a stock photo for use in a project
- create renditions from a psd or image
- photoshop edit smart object
- create artboards in a psd document
- remove the background from an image using photoshop sensei ai
- firefly generate video
- stock license vector
- remove background
- stock assets
- edit smart object
- create mask
- get the status of an async firefly generation job
- auto-crop an image to the primary product
- replace smart object content in a psd document
- psd document operations
- create artboards within a psd document
- get stock file metadata
- stock license video
- firefly fill image
- video
- psd layer management
- stock license image
- generate images
- photoshop apply document operations
- photoshop manage layers
- get the status of an async photoshop job
- generate images from a text prompt using firefly
- read, add, modify, or delete layers in a psd document
- search the adobe stock library for photos, illustrations, vectors, and videos
- automatically straighten a rotated image
- photoshop straighten image
- create rendition
- photoshop edit text layers
- search stock files
- generate images similar to a reference image
- expand an image beyond its boundaries using firefly
- edit text layers in a psd document
- license a vector or illustration for use in a project
- stock search files
- design
- expand an image beyond its boundaries using firefly generative ai
- generative ai
- manage layers
- license a vector or illustration
- get photoshop job status
- photoshop remove background
- expand image
- manage layers in a psd document
- stock get file metadata
- stock file metadata
- image rendition creation
- replace smart object content in a psd
- stock vector licensing
- straighten image
- generate similar image variations
- generate composite
- photoshop create artboard
- get detailed metadata for a specific stock file
- adobe
- generate video
- product cropping
- ai-powered generative fill
- stock get categories
- creative production
- license a stock video clip
- ai object compositing
- create an alpha mask for an image using photoshop sensei ai
- graphics
- background removal
- generate an ai object and composite it into a scene using firefly
- edit text content and styling in psd text layers
- image straightening
- psd artboard creation
- photoshop operation job status
- license video
- creative
- license a stock video clip for use in a project
- stock image licensing
- firefly generate composite
- apply resize, flatten, or trim operations to a psd
- photoshop get job status
- firefly expand image
- fill a masked region with ai-generated content
- search the adobe stock library
- create artboard
- firefly generate images
- firefly generation job status
- edit text layers
- photoshop create mask
- stock video licensing
- alpha mask creation
- get firefly job status
slug: creative-production
source_filename: creative-production.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adobe Creative Production\n  description: End-to-end creative asset production workflow combining AI content generation (Firefly), image editing and\n    manipulation (Photoshop), and stock asset sourcing and licensing (Stock). Used by creative directors, production designers,\n    and marketing teams to find, generate, edit, and finalize visual assets.\n  tags:\n  - Adobe\n  - Creative Production\n  - Generative AI\n  - Image Editing\n  - Stock Assets\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADOBE_FIREFLY_TOKEN: ADOBE_FIREFLY_TOKEN\n    ADOBE_PHOTOSHOP_TOKEN: ADOBE_PHOTOSHOP_TOKEN\n    ADOBE_STOCK_TOKEN: ADOBE_STOCK_TOKEN\n    ADOBE_STOCK_API_KEY: ADOBE_STOCK_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: firefly\n    baseUri: https://firefly-api.adobe.io/v3\n    description: Adobe Firefly API for generative AI image and video creation\n    authentication:\n      type:\
  \ bearer\n      token: '{{ADOBE_FIREFLY_TOKEN}}'\n    resources:\n    - name: image-generation\n      path: /images\n      description: Text-to-image and image variation generation operations\n      operations:\n      - name: generate-images-async\n        method: POST\n        path: /generate-async\n        description: Generates one or more images from a text prompt using the Adobe Firefly generative AI model\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            negativePrompt: '{{tools.negative_prompt}}'\n            contentClass: '{{tools.content_class}}'\n            numVariations: '{{tools.num_variations}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: generate-similar-images-async\n        method: POST\n        path: /generate-similar-async\n        description: Generates images visually similar to a provided reference image\n     \
  \   body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            image: '{{tools.image}}'\n            numVariations: '{{tools.num_variations}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: generative-expand\n      path: /images\n      description: Expand images beyond their original boundaries\n      operations:\n      - name: expand-image-async\n        method: POST\n        path: /expand-async\n        description: Expands an existing image beyond its original boundaries using generative AI\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            negativePrompt: '{{tools.negative_prompt}}'\n            image: '{{tools.image}}'\n            numVariations: '{{tools.num_variations}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: generative-fill\n      path: /images\n      description: Fill selected regions of images with AI-generated content\n      operations:\n      - name: fill-image-async\n        method: POST\n        path: /fill-async\n        description: Fills a masked region of an existing image with AI-generated content based on a text prompt\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            negativePrompt: '{{tools.negative_prompt}}'\n            image: '{{tools.image}}'\n            mask: '{{tools.mask}}'\n            numVariations: '{{tools.num_variations}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: object-composite\n      path: /images\n      description: Composite AI-generated objects into existing images\n      operations:\n      - name: generate-object-composite-async\n        method: POST\n        path: /generate-object-composite-async\n\
  \        description: Generates an AI-rendered object and composites it into an existing scene image\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            negativePrompt: '{{tools.negative_prompt}}'\n            contentClass: '{{tools.content_class}}'\n            image: '{{tools.image}}'\n            mask: '{{tools.mask}}'\n            numVariations: '{{tools.num_variations}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: video-generation\n      path: /videos\n      description: Generate video from text prompts\n      operations:\n      - name: generate-video-async\n        method: POST\n        path: /generate-async\n        description: Generates a short video clip from a text prompt using the Adobe Firefly video generation model\n        body:\n          type: json\n          data:\n            prompt: '{{tools.prompt}}'\n            negativePrompt:\
  \ '{{tools.negative_prompt}}'\n            duration: '{{tools.duration}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status\n      path: /status\n      description: Asynchronous job status polling\n      operations:\n      - name: get-generation-status\n        method: GET\n        path: /{jobId}\n        description: Retrieves the current status of an asynchronous Firefly generation job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the generation job to check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: photoshop\n    baseUri: https://image.adobe.io\n    description: Adobe Photoshop API for programmatic image manipulation\n    authentication:\n      type: bearer\n\
  \      token: '{{ADOBE_PHOTOSHOP_TOKEN}}'\n    resources:\n    - name: cutout\n      path: /sensei\n      description: Background removal and masking operations\n      operations:\n      - name: remove-background\n        method: POST\n        path: /cutout\n        description: Removes the background from an image using Adobe Sensei AI\n        body:\n          type: json\n          data:\n            input: '{{tools.input}}'\n            output: '{{tools.output}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: product-crop\n        method: POST\n        path: /product_crop\n        description: Automatically crops an image to focus on the primary product subject\n        body:\n          type: json\n          data:\n            input: '{{tools.input}}'\n            output: '{{tools.output}}'\n            options: '{{tools.options}}'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: straighten-image\n        method: POST\n        path: /straighten\n        description: Automatically detects and corrects the rotation of an image\n        body:\n          type: json\n          data:\n            input: '{{tools.input}}'\n            output: '{{tools.output}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mask\n      path: /sensei\n      description: Alpha mask creation operations\n      operations:\n      - name: create-mask\n        method: POST\n        path: /mask\n        description: Creates an alpha mask for an image using Adobe Sensei AI\n        body:\n          type: json\n          data:\n            input: '{{tools.input}}'\n            output: '{{tools.output}}'\n            options: '{{tools.options}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: text\n      path: /pie/psdService\n      description: Text layer editing operations\n      operations:\n      - name: edit-text-layers\n        method: POST\n        path: /text\n        description: Edits text content, font properties, and styling of text layers within a PSD document\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            outputs: '{{tools.outputs}}'\n            options: '{{tools.options}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: layers\n      path: /pie/psdService\n      description: PSD layer management operations\n      operations:\n      - name: manage-layers\n        method: POST\n        path: /layers\n        description: Reads, adds, modifies, or deletes layers within a PSD document\n        body:\n          type: json\n          data:\n            inputs:\
  \ '{{tools.inputs}}'\n            outputs: '{{tools.outputs}}'\n            options: '{{tools.options}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: document\n      path: /pie/psdService\n      description: Document-level operations\n      operations:\n      - name: apply-document-operations\n        method: POST\n        path: /documentOperations\n        description: Applies operations to a PSD document such as resizing, flattening, and color mode conversions\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            outputs: '{{tools.outputs}}'\n            options: '{{tools.options}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rendition\n      path: /pie/psdService\n      description: Rendition and export operations\n      operations:\n      - name:\
  \ create-rendition\n        method: POST\n        path: /renditionCreate\n        description: Generates one or more renditions from a PSD or image in JPEG, PNG, or TIFF\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            outputs: '{{tools.outputs}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: smart-object\n      path: /pie/psdService\n      description: Smart object editing operations\n      operations:\n      - name: edit-smart-object\n        method: POST\n        path: /smartObject\n        description: Replaces the content of a smart object layer within a PSD document\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            outputs: '{{tools.outputs}}'\n            options: '{{tools.options}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: artboard\n      path: /pie/psdService\n      description: Artboard creation and management\n      operations:\n      - name: create-artboard\n        method: POST\n        path: /artboard\n        description: Creates one or more artboards within a PSD document\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            outputs: '{{tools.outputs}}'\n            options: '{{tools.options}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status\n      path: /pie/psdService/status\n      description: Asynchronous job status operations\n      operations:\n      - name: get-job-status\n        method: GET\n        path: /{jobId}\n        description: Retrieves the current status of an asynchronous Photoshop API job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n\
  \          required: true\n          description: The unique identifier of the job to check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: stock\n    baseUri: https://stock.adobe.io/Rest\n    description: Adobe Stock API for searching and licensing stock content\n    authentication:\n      type: bearer\n      token: '{{ADOBE_STOCK_TOKEN}}'\n    resources:\n    - name: search\n      path: /Media/1/Search\n      description: Search and discover stock content\n      operations:\n      - name: search-stock-files\n        method: GET\n        path: /Files\n        description: Searches the Adobe Stock library for files matching specified criteria\n        inputParameters:\n        - name: locale\n          in: query\n          type: string\n          required: false\n          description: BCP 47 locale code for localized search results\n        - name: search_parameters[words]\n\
  \          in: query\n          type: string\n          required: false\n          description: Keywords to search for in the stock library\n        - name: search_parameters[limit]\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return per page (1-64)\n        - name: search_parameters[offset]\n          in: query\n          type: integer\n          required: false\n          description: Number of results to skip for pagination\n        - name: search_parameters[filters][content_type:photo]\n          in: query\n          type: integer\n          required: false\n          description: Include photos in results (1 = include, 0 = exclude)\n        - name: search_parameters[filters][content_type:illustration]\n          in: query\n          type: integer\n          required: false\n          description: Include illustrations in results (1 = include, 0 = exclude)\n        - name: search_parameters[filters][content_type:vector]\n\
  \          in: query\n          type: integer\n          required: false\n          description: Include vector files in results (1 = include, 0 = exclude)\n        - name: search_parameters[filters][content_type:video]\n          in: query\n          type: integer\n          required: false\n          description: Include video files in results (1 = include, 0 = exclude)\n        - name: search_parameters[filters][orientation]\n          in: query\n          type: string\n          required: false\n          description: Filter by image orientation\n        - name: search_parameters[filters][premium]\n          in: query\n          type: string\n          required: false\n          description: Filter by premium status\n        - name: result_columns[]\n          in: query\n          type: array\n          required: false\n          description: Fields to include in the response\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n      \
  \    description: Adobe Stock API key (client ID)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-stock-file-metadata\n        method: GET\n        path: /Files/{content_id}\n        description: Retrieves detailed metadata for a specific stock file by its content ID\n        inputParameters:\n        - name: content_id\n          in: path\n          type: integer\n          required: true\n          description: Adobe Stock unique content identifier\n        - name: locale\n          in: query\n          type: string\n          required: false\n          description: BCP 47 locale for localized response data\n        - name: result_columns[]\n          in: query\n          type: array\n          required: false\n          description: Fields to include in the response\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description:\
  \ Adobe Stock API key (client ID)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-category-tree\n        method: GET\n        path: /CategoryTree\n        description: Retrieves the hierarchical category tree used to organize Adobe Stock content\n        inputParameters:\n        - name: locale\n          in: query\n          type: string\n          required: false\n          description: BCP 47 locale for localized category names\n        - name: category_id\n          in: query\n          type: integer\n          required: false\n          description: Root category ID to retrieve subtree from\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: member\n\
  \      path: /Member/1\n      description: Member profile and licensing operations\n      operations:\n      - name: get-member-profile\n        method: GET\n        path: /Profile\n        description: Retrieves the profile of the authenticated Adobe Stock member including quota information\n        inputParameters:\n        - name: locale\n          in: query\n          type: string\n          required: false\n          description: BCP 47 locale for localized profile data\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: license\n      path: /Member/1\n      description: License stock assets for use in projects\n      operations:\n      - name: get-license-history\n        method: GET\n        path: /License\n        description: Retrieves the\
  \ license history for the authenticated member\n        inputParameters:\n        - name: locale\n          in: query\n          type: string\n          required: false\n          description: BCP 47 locale for localized response data\n        - name: search_parameters[limit]\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return\n        - name: search_parameters[offset]\n          in: query\n          type: integer\n          required: false\n          description: Number of results to skip for pagination\n        - name: result_columns[]\n          in: query\n          type: array\n          required: false\n          description: Fields to include in the license history response\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: license-image\n        method: POST\n        path: /LicenseImage\n        description: Licenses a stock photo for use in a project\n        inputParameters:\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        body:\n          type: json\n          data:\n            content_id: '{{tools.content_id}}'\n            license: '{{tools.license}}'\n            locale: '{{tools.locale}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: license-vector\n        method: POST\n        path: /LicenseVectorOrIllustration\n        description: Licenses a vector or illustration stock file for use in a project\n        inputParameters:\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n\
  \          description: Adobe Stock API key (client ID)\n        body:\n          type: json\n          data:\n            content_id: '{{tools.content_id}}'\n            license: '{{tools.license}}'\n            locale: '{{tools.locale}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: license-video\n        method: POST\n        path: /LicenseVideo\n        description: Licenses a stock video clip for use in a project\n        inputParameters:\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        body:\n          type: json\n          data:\n            content_id: '{{tools.content_id}}'\n            license: '{{tools.license}}'\n            locale: '{{tools.locale}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n      - name: get-license-stats\n        method: POST\n        path: /LicenseStats\n        description: Retrieves licensing statistics for the authenticated member\n        inputParameters:\n        - name: x-api-key\n          in: header\n          type: string\n          required: true\n          description: Adobe Stock API key (client ID)\n        body:\n          type: json\n          data:\n            locale: '{{tools.locale}}'\n            result_columns: '{{tools.result_columns}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: creative-production-api\n    description: Unified REST API for end-to-end creative asset production combining AI generation, image editing, and stock\n      sourcing.\n    resources:\n    - path: /v1/generations\n      name: generations\n      description: AI image generation from text prompts\n      operations:\n\
  \      - method: POST\n        name: generate-images\n        description: Generate images from a text prompt using Firefly\n        call: firefly.generate-images-async\n        with:\n          prompt: rest.prompt\n          negative_prompt: rest.negative_prompt\n          content_class: rest.content_class\n          num_variations: rest.num_variations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/generations/similar\n      name: similar-generations\n      description: Generate similar image variations\n      operations:\n      - method: POST\n        name: generate-similar-images\n        description: Generate images similar to a reference image\n        call: firefly.generate-similar-images-async\n        with:\n          prompt: rest.prompt\n          image: rest.image\n          num_variations: rest.num_variations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/expansions\n      name: expansions\n\
  \      description: AI-powered image expansion\n      operations:\n      - method: POST\n        name: expand-image\n        description: Expand an image beyond its boundaries using Firefly\n        call: firefly.expand-image-async\n        with:\n          prompt: rest.prompt\n          image: rest.image\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fills\n      name: fills\n      description: AI-powered generative fill\n      operations:\n      - method: POST\n        name: fill-image\n        description: Fill a masked region with AI-generated content\n        call: firefly.fill-image-async\n        with:\n          prompt: rest.prompt\n          image: rest.image\n          mask: rest.mask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/composites\n      name: composites\n      description: AI object compositing\n      operations:\n      - method: POST\n        name: generate-composite\n       \
  \ description: Generate and composite an AI object into a scene\n        call: firefly.generate-object-composite-async\n        with:\n          prompt: rest.prompt\n          image: rest.image\n          mask: rest.mask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/videos\n      name: videos\n      description: AI video generation\n      operations:\n      - method: POST\n        name: generate-video\n        description: Generate a video from a text prompt using Firefly\n        call: firefly.generate-video-async\n        with:\n          prompt: rest.prompt\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cutouts\n      name: cutouts\n      description: Background removal\n      operations:\n      - method: POST\n        name: remove-background\n        description: Remove background from an image using Photoshop\n        call: photoshop.remove-background\n        with:\n          input: rest.input\n\
  \          output: rest.output\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/masks\n      name: masks\n      description: Alpha mask creation\n      operations:\n      - method: POST\n        name: create-mask\n        description: Create an alpha mask for an image\n        call: photoshop.create-mask\n        with:\n          input: rest.input\n          output: rest.output\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/product-crops\n      name: product-crops\n      description: Product cropping\n      operations:\n      - method: POST\n        name: product-crop\n        description: Auto-crop an image to the primary product\n        call: photoshop.product-crop\n        with:\n          input: rest.input\n          output: rest.output\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/renditions\n      name: renditions\n      description: Image rendition\
  \ creation\n      operations:\n      - method: POST\n        name: create-rendition\n        description: Create renditions from a PSD or image\n        call: photoshop.create-rendition\n        with:\n          inputs: rest.inputs\n          outputs: rest.outputs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/layers\n      name: layers\n      description: PSD layer management\n      operations:\n      - method: POST\n        name: manage-layers\n        description: Manage layers in a PSD document\n        call: photoshop.manage-layers\n        with:\n          inputs: rest.inputs\n          outputs: rest.outputs\n          options: rest.options\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/text-edits\n      name: text-edits\n      description: PSD text layer editing\n      operations:\n      - method: POST\n        name: edit-text-layers\n        description: Edit text layers in a PSD document\n\
  \        call: photoshop.edit-text-layers\n        with:\n          inputs: rest.inputs\n          outputs: rest.outputs\n          options: rest.options\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/smart-objects\n      name: smart-objects\n      description: Smart object replacement\n      operations:\n      - method: POST\n        name: edit-smart-object\n        description: Replace smart object content in a PSD\n        call: photoshop.edit-smart-object\n        with:\n          inputs: rest.inputs\n          outputs: rest.outputs\n          options: rest.options\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/document-operations\n      name: document-operations\n      description: PSD document operations\n      operations:\n      - method: POST\n        name: apply-document-operations\n        description: Apply resize, flatten, or trim operations to a PSD\n        call: photoshop.apply-document-operations\n\
  \        with:\n          inputs: rest.inputs\n          outputs: rest.outputs\n          options: rest.options\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/artboards\n      name: artboards\n      description: PSD artboard creation\n      operations:\n      - method: POST\n        name: create-artboard\n        description: Create artboards in a PSD document\n        call: photoshop.create-artboard\n        with:\n          inputs: rest.inputs\n          outputs: rest.outputs\n          options: rest.options\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/straighten-jobs\n      name: straighten-jobs\n      description: Image straightening\n      operations:\n      - method: POST\n        name: straighten-image\n        description: Automatically straighten a rotated image\n        call: photoshop.straighten-image\n        with:\n          input: rest.input\n          output: rest.output\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/stock-files\n      name: stock-files\n      description: Stock asset search\n      operations:\n      - method: GET\n        name: search-stock-files\n        description: Search the Adobe Stock library\n        call: stock.search-stock-files\n        with:\n          search_parameters[words]: rest.keywords\n          search_parameters[limit]: rest.limit\n          search_parameters[offset]: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stock-files/{content_id}\n      name: stock-file-detail\n      description: Stock file metadata\n      operations:\n      - method: GET\n        name: get-stock-file-metadata\n        description: Get metadata for a specific stock file\n        call: stock.get-stock-file-metadata\n        with:\n          content_id: rest.content_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/licenses/images\n\
  \      name: license-images\n      description: Stock image licensing\n      operations:\n      - method: POST\n        name: license-image\n        description: License a stock photo\n        call: stock.license-image\n        with:\n          content_id: rest.content_id\n          license: rest.license\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/licenses/vectors\n      name: license-vectors\n      description: Stock vector licensing\n      operations:\n      - method: POST\n        name: license-vector\n        description: License a vector or illustration\n        call: stock.license-vector\n        with:\n          content_id: rest.content_id\n          license: rest.license\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/licenses/videos\n      name: license-videos\n      description: Stock video licensing\n      operations:\n      - method: POST\n        name: license-video\n        description:\
  \ License a stock video clip\n        call: stock.license-video\n        with:\n          content_id: rest.content_id\n          license: rest.license\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/firefly-jobs/{jobId}\n      name: firefly-jobs\n      description: Firefly generation job status\n      operations:\n      - method: GET\n        name: get-firefly-job-status\n        description: Get the status of an async Firefly generation job\n        call: firefly.get-generation-status\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/photoshop-jobs/{jobId}\n      name: photoshop-jobs\n      description: Photoshop operation job status\n      operations:\n      - method: GET\n        name: get-photoshop-job-status\n        description: Get the status of an async Photoshop job\n        call: photoshop.get-job-status\n        with:\n          jobId: rest.jobId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: creative-production-mcp\n    transport: http\n    description: MCP server for AI-assisted creative asset production combining generation, editing, and stock sourcing.\n    tools:\n    - name: firefly-generate-images\n      description: Generate images from a text prompt using Adobe Firefly\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: firefly.generate-images-async\n      with:\n        prompt: tools.prompt\n        negative_prompt: tools.negative_prompt\n        content_class: tools.content_class\n        num_variations: tools.num_variations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: firefly-generate-similar-images\n      description: Generate images similar to a reference image using Firefly\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: firefly.generate-similar-images-async\n      with:\n        prompt: tools.prompt\n        image: tools.image\n        num_variations: tools.num_variations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: firefly-expand-image\n      description: Expand an image beyond its boundaries using Firefly generative AI\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: firefly.expand-image-async\n      with:\n        prompt: tools.prompt\n        image: tools.image\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: firefly-fill-image\n      description: Fill a masked region of an image wit\n\n# --- truncated at 32 KB (39 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/adobe-creative-suite/refs/heads/main/capabilities/creative-production.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adobe-creative-suite/refs/heads/main/capabilities/creative-production.yaml
tags:
- Adobe
- Creative Production
- Generative AI
- Image Editing
- Stock Assets
tools:
- description: Generate images from a text prompt using Adobe Firefly
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: firefly-generate-images
- description: Generate images similar to a reference image using Firefly
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: firefly-generate-similar-images
- description: Expand an image beyond its boundaries using Firefly generative AI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: firefly-expand-image
- description: Fill a masked region of an image with AI-generated content using Firefly
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: firefly-fill-image
- description: Generate an AI object and composite it into a scene using Firefly
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: firefly-generate-composite
- description: Generate a video from a text prompt using Firefly
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: firefly-generate-video
- description: Get the status of an async Firefly generation job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: firefly-get-job-status
- description: Remove the background from an image using Photoshop Sensei AI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-remove-background
- description: Create an alpha mask for an image using Photoshop Sensei AI
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-create-mask
- description: Auto-crop an image to focus on the primary product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-product-crop
- description: Automatically straighten a rotated image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-straighten-image
- description: Edit text content and styling in PSD text layers
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-edit-text-layers
- description: Read, add, modify, or delete layers in a PSD document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-manage-layers
- description: Apply resize, flatten, or trim operations to a PSD document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-apply-document-operations
- description: Create renditions from a PSD or image in JPEG, PNG, or TIFF
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-create-rendition
- description: Replace smart object content in a PSD document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-edit-smart-object
- description: Create artboards within a PSD document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: photoshop-create-artboard
- description: Get the status of an async Photoshop job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: photoshop-get-job-status
- description: Search the Adobe Stock library for photos, illustrations, vectors, and videos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: stock-search-files
- description: Get detailed metadata for a specific stock file
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: stock-get-file-metadata
- description: License a stock photo for use in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stock-license-image
- description: License a vector or illustration for use in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stock-license-vector
- description: License a stock video clip for use in a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stock-license-video
- description: Get the Adobe Stock content category tree
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: stock-get-categories
---
