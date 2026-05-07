---
api_specs:
- filename: api-snap-openapi.yml
  format: yaml
  label: api-snap
  slug: api-snap
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/api-snap/refs/heads/main/openapi/api-snap-openapi.yml
categories: []
consumed_apis:
- api-snap
description: Workflow that combines API Snap's visual and document generation endpoints (QR code, screenshot, image resize, PDF, Markdown, placeholder, URL metadata) for marketing, content management, and document automation pipelines. Used by content engineers, growth teams, and CMS platforms to produce link previews, visual assets, PDFs, and rendered HTML on demand.
layout: capability
name: API Snap Content Generation
operations:
- description: Generate a QR code
  method: POST
  name: createQrCode
  path: /v1/qr-codes
- description: Capture a webpage screenshot
  method: POST
  name: createScreenshot
  path: /v1/screenshots
- description: Resize and convert an image
  method: POST
  name: resizeImage
  path: /v1/images
- description: Generate an SVG placeholder image
  method: POST
  name: createPlaceholder
  path: /v1/images
- description: Render HTML as PDF
  method: POST
  name: createPdf
  path: /v1/documents
- description: Convert Markdown to HTML
  method: POST
  name: renderMarkdown
  path: /v1/documents
- description: Extract URL metadata
  method: GET
  name: getUrlMetadata
  path: /v1/url-metadata
personas:
- description: Engineer building content publishing, link previews, and visual assets
  id: content-engineer
  name: Content Engineer
- description: Engineer building marketing assets, QR campaigns, and landing-page automation
  id: growth-engineer
  name: Growth Engineer
- description: Developer integrating Markdown rendering, PDF generation, and screenshots into a CMS
  id: cms-integrator
  name: CMS Integrator
provider_name: API Snap
provider_slug: api-snap
search_terms:
- generation of uuids and unique ids
- capture screenshot
- visual and document generation workflow combining qr code, screenshot, image resize, pdf, markdown, placeholder, and url metadata endpoints.
- platform engineer
- generation of visual assets including qr codes, screenshots, resized images, and placeholders
- engineer building application services that need ids, hashing, and encoding utilities
- render html content as a pdf document.
- image processing
- createPlaceholder
- generate an svg placeholder image
- resize image
- render html as pdf
- qr code generation
- html to pdf
- base64
- resizeImage
- convert markdown content into html.
- generate a qr code encoding the supplied text or url.
- api snap
- engineer building content publishing, link previews, and visual assets
- engineer building marketing assets, qr campaigns, and landing-page automation
- content generation
- generation and conversion of structured documents
- pdf and markdown rendering
- webpage screenshot capture
- uuid
- screenshots
- color conversion
- createScreenshot
- engineer integrating utility primitives into ide, cli, or admin tooling
- lorem ipsum
- markdown
- color conversion and placeholder text for design and prototyping
- qr codes
- developer tools
- generate placeholder
- generate an svg placeholder image.
- growth engineer
- content engineer
- pdf generation
- generate qr code
- createQrCode
- extract open graph and metadata for a url.
- capture a screenshot of a webpage.
- get url metadata
- api utilities
- generate a qr code
- extract url metadata
- cms integrator
- markdown to html
- backend developer primitive workflow combining hashing, jwt decode, base64, uuid generation, color conversion, and lorem ipsum endpoints.
- image resize and placeholder generation
- renderMarkdown
- resize and reformat an image.
- backend engineer
- capture a webpage screenshot
- resize and convert an image
- engineer centralizing developer primitives across services
- url metadata and open graph extraction
- developer tools builder
- inspection and extraction of metadata from web urls
- cryptographic hashing, jwt inspection, and base64 encoding
- url metadata
- createPdf
- developer integrating markdown rendering, pdf generation, and screenshots into a cms
- jwt
- convert markdown to html
- hashing
- placeholder images
- getUrlMetadata
slug: content-generation
source_filename: content-generation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: API Snap Content Generation\n  description: >-\n    Workflow that combines API Snap's visual and document generation endpoints\n    (QR code, screenshot, image resize, PDF, Markdown, placeholder, URL\n    metadata) for marketing, content management, and document automation\n    pipelines. Used by content engineers, growth teams, and CMS platforms to\n    produce link previews, visual assets, PDFs, and rendered HTML on demand.\n  tags:\n    - API Snap\n    - Content Generation\n    - QR Codes\n    - Screenshots\n    - Image Processing\n    - PDF Generation\n    - Markdown\n    - URL Metadata\n  created: '2026-05-06'\n  modified: '2026-05-06'\nbinds:\n  - namespace: env\n    keys:\n      API_SNAP_API_KEY: API_SNAP_API_KEY\ncapability:\n  consumes:\n    - import: api-snap\n      location: ./shared/api-snap.yaml\n  exposes:\n    - type: rest\n      port: 7081\n      namespace: content-generation-api\n      description: Unified REST API for\
  \ visual and document content generation.\n      resources:\n        - path: /v1/qr-codes\n          name: qr-codes\n          description: QR code generation\n          operations:\n            - method: POST\n              name: createQrCode\n              description: Generate a QR code\n              call: api-snap.generateQrCode\n              with:\n                data: rest.data\n                size: rest.size\n                format: rest.format\n                dark: rest.dark\n                light: rest.light\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n        - path: /v1/screenshots\n          name: screenshots\n          description: Webpage screenshot capture\n          operations:\n            - method: POST\n              name: createScreenshot\n              description: Capture a webpage screenshot\n              call: api-snap.captureScreenshot\n              with:\n                url: rest.url\n             \
  \   width: rest.width\n                height: rest.height\n                format: rest.format\n                full_page: rest.full_page\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n        - path: /v1/images\n          name: images\n          description: Image resize and placeholder generation\n          operations:\n            - method: POST\n              name: resizeImage\n              description: Resize and convert an image\n              call: api-snap.resizeImage\n              with:\n                image: rest.image\n                url: rest.url\n                width: rest.width\n                height: rest.height\n                format: rest.format\n                quality: rest.quality\n                fit: rest.fit\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n            - method: POST\n              name: createPlaceholder\n              description: Generate\
  \ an SVG placeholder image\n              call: api-snap.generatePlaceholderImage\n              with:\n                w: rest.w\n                h: rest.h\n                bg: rest.bg\n                fg: rest.fg\n                text: rest.text\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n        - path: /v1/documents\n          name: documents\n          description: PDF and Markdown rendering\n          operations:\n            - method: POST\n              name: createPdf\n              description: Render HTML as PDF\n              call: api-snap.htmlToPdf\n              with:\n                html: rest.html\n                title: rest.title\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n            - method: POST\n              name: renderMarkdown\n              description: Convert Markdown to HTML\n              call: api-snap.markdownToHtml\n              with:\n    \
  \            markdown: rest.markdown\n                styled: rest.styled\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n        - path: /v1/url-metadata\n          name: url-metadata\n          description: URL metadata and Open Graph extraction\n          operations:\n            - method: GET\n              name: getUrlMetadata\n              description: Extract URL metadata\n              call: api-snap.extractUrlMetadata\n              with:\n                url: rest.url\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n    - type: mcp\n      port: 7082\n      namespace: content-generation-mcp\n      transport: http\n      description: MCP server for AI-assisted visual and document content generation.\n      tools:\n        - name: generate-qr-code\n          description: Generate a QR code encoding the supplied text or URL.\n          hints:\n            readOnly: true\n       \
  \     openWorld: false\n          call: api-snap.generateQrCode\n          with:\n            data: tools.data\n            size: tools.size\n            format: tools.format\n            dark: tools.dark\n            light: tools.light\n          outputParameters:\n            - type: object\n              mapping: '$.'\n        - name: capture-screenshot\n          description: Capture a screenshot of a webpage.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api-snap.captureScreenshot\n          with:\n            url: tools.url\n            width: tools.width\n            height: tools.height\n            format: tools.format\n            full_page: tools.full_page\n          outputParameters:\n            - type: object\n              mapping: '$.'\n        - name: resize-image\n          description: Resize and reformat an image.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: api-snap.resizeImage\n\
  \          with:\n            image: tools.image\n            url: tools.url\n            width: tools.width\n            height: tools.height\n            format: tools.format\n            quality: tools.quality\n            fit: tools.fit\n          outputParameters:\n            - type: object\n              mapping: '$.'\n        - name: generate-placeholder\n          description: Generate an SVG placeholder image.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: api-snap.generatePlaceholderImage\n          with:\n            w: tools.w\n            h: tools.h\n            bg: tools.bg\n            fg: tools.fg\n            text: tools.text\n          outputParameters:\n            - type: object\n              mapping: '$.'\n        - name: html-to-pdf\n          description: Render HTML content as a PDF document.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: api-snap.htmlToPdf\n         \
  \ with:\n            html: tools.html\n            title: tools.title\n          outputParameters:\n            - type: object\n              mapping: '$.'\n        - name: markdown-to-html\n          description: Convert Markdown content into HTML.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: api-snap.markdownToHtml\n          with:\n            markdown: tools.markdown\n            styled: tools.styled\n          outputParameters:\n            - type: object\n              mapping: '$.'\n        - name: get-url-metadata\n          description: Extract Open Graph and metadata for a URL.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api-snap.extractUrlMetadata\n          with:\n            url: tools.url\n          outputParameters:\n            - type: object\n              mapping: '$.'\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/api-snap/refs/heads/main/capabilities/content-generation.yaml
tags:
- API Snap
- Content Generation
- QR Codes
- Screenshots
- Image Processing
- PDF Generation
- Markdown
- URL Metadata
tools:
- description: Generate a QR code encoding the supplied text or URL.
  hints:
    openWorld: false
    readOnly: true
  name: generate-qr-code
- description: Capture a screenshot of a webpage.
  hints:
    openWorld: true
    readOnly: true
  name: capture-screenshot
- description: Resize and reformat an image.
  hints:
    openWorld: false
    readOnly: false
  name: resize-image
- description: Generate an SVG placeholder image.
  hints:
    openWorld: false
    readOnly: true
  name: generate-placeholder
- description: Render HTML content as a PDF document.
  hints:
    openWorld: false
    readOnly: false
  name: html-to-pdf
- description: Convert Markdown content into HTML.
  hints:
    openWorld: false
    readOnly: true
  name: markdown-to-html
- description: Extract Open Graph and metadata for a URL.
  hints:
    openWorld: true
    readOnly: true
  name: get-url-metadata
---
