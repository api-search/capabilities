---
api_specs:
- filename: the-color-api-openapi.yml
  format: yaml
  label: colorapi
  slug: colorapi
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/the-color-api/refs/heads/main/openapi/the-color-api-openapi.yml
categories: []
consumed_apis:
- colorapi
description: Workflow capability for color lookup, format conversion, and palette generation using The Color API. Supports designers, developers building color pickers, design system maintainers, and AI assistants needing color information.
layout: capability
name: Color Design Tools
operations:
- description: Get comprehensive color data including all format conversions, named color, and contrast.
  method: GET
  name: get-color-info
  path: /v1/colors
- description: Generate a color scheme using a specified color-wheel mode.
  method: GET
  name: get-color-scheme
  path: /v1/schemes
personas: []
provider_name: The Color API
provider_slug: the-color-api
search_terms:
- generate color scheme
- colors
- utilities
- identify a color and get all format conversions and naming information.
- generate a color scheme using a specified color-wheel mode.
- identify any color by hex, rgb, hsl, or cmyk input and receive full format conversions, nearest color name, contrast recommendation, and image swatch urls.
- get color info
- generate harmonious color palettes from a seed color.
- identify color
- design tokens
- design
- generate a harmonious color palette from a seed color using color-wheel theory. supports monochrome, monochrome-dark, monochrome-light, analogic, complement, analogic-complement, triad, and quad modes.
- get comprehensive color data including all format conversions, named color, and contrast.
- get color scheme
slug: color-design-tools
source_filename: color-design-tools.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Color Design Tools\"\n  description: >-\n    Workflow capability for color lookup, format conversion, and palette generation\n    using The Color API. Supports designers, developers building color pickers,\n    design system maintainers, and AI assistants needing color information.\n  tags:\n    - Colors\n    - Design\n    - Design Tokens\n    - Utilities\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\ncapability:\n  consumes:\n    - import: colorapi\n      location: ./shared/the-color-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: color-design-api\n      description: \"Unified REST API for color identification, conversion, and scheme generation.\"\n      resources:\n        - path: /v1/colors\n          name: colors\n          description: Identify a color and get all format conversions and naming information.\n          operations:\n            - method: GET\n              name: get-color-info\n\
  \              description: Get comprehensive color data including all format conversions, named color, and contrast.\n              call: \"colorapi.get-color-info\"\n              with:\n                hex: \"rest.hex\"\n                rgb: \"rest.rgb\"\n                hsl: \"rest.hsl\"\n                cmyk: \"rest.cmyk\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/schemes\n          name: schemes\n          description: Generate harmonious color palettes from a seed color.\n          operations:\n            - method: GET\n              name: get-color-scheme\n              description: Generate a color scheme using a specified color-wheel mode.\n              call: \"colorapi.get-color-scheme\"\n              with:\n                hex: \"rest.hex\"\n                rgb: \"rest.rgb\"\n                mode: \"rest.mode\"\n                count: \"rest.count\"\n              outputParameters:\n         \
  \       - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: color-design-mcp\n      transport: http\n      description: \"MCP server for AI-assisted color lookup, conversion, and design palette generation.\"\n      tools:\n        - name: identify-color\n          description: >-\n            Identify any color by hex, RGB, HSL, or CMYK input and receive full format conversions,\n            nearest color name, contrast recommendation, and image swatch URLs.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"colorapi.get-color-info\"\n          with:\n            hex: \"tools.hex\"\n            rgb: \"tools.rgb\"\n            hsl: \"tools.hsl\"\n            cmyk: \"tools.cmyk\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: generate-color-scheme\n          description: >-\n            Generate a harmonious color palette from a seed color\
  \ using color-wheel theory.\n            Supports monochrome, monochrome-dark, monochrome-light, analogic, complement,\n            analogic-complement, triad, and quad modes.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"colorapi.get-color-scheme\"\n          with:\n            hex: \"tools.hex\"\n            rgb: \"tools.rgb\"\n            hsl: \"tools.hsl\"\n            mode: \"tools.mode\"\n            count: \"tools.count\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/the-color-api/refs/heads/main/capabilities/color-design-tools.yaml
tags:
- Colors
- Design
- Design Tokens
- Utilities
tools:
- description: Identify any color by hex, RGB, HSL, or CMYK input and receive full format conversions, nearest color name, contrast recommendation, and image swatch URLs.
  hints:
    openWorld: true
    readOnly: true
  name: identify-color
- description: Generate a harmonious color palette from a seed color using color-wheel theory. Supports monochrome, monochrome-dark, monochrome-light, analogic, complement, analogic-complement, triad, and quad modes.
  hints:
    openWorld: true
    readOnly: true
  name: generate-color-scheme
---
