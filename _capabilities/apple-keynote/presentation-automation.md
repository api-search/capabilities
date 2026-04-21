---
consumed_apis:
- keynote-icloud
description: Workflow capability for automating Keynote presentation creation and management via iCloud. Combines presentation lifecycle management, slide operations, theme selection, and multi-format export into a unified workflow for content creators, marketing teams, and business presenters.
layout: capability
name: Apple Keynote Presentation Automation
operations:
- description: List all Keynote presentations in iCloud
  method: GET
  name: list-presentations
  path: /v1/presentations
- description: Create a new presentation with title and theme
  method: POST
  name: create-presentation
  path: /v1/presentations
- description: List slides in a presentation
  method: GET
  name: list-slides
  path: /v1/slides
- description: Export a presentation to PDF, PPTX, or images
  method: POST
  name: export-presentation
  path: /v1/export
- description: List available Keynote themes
  method: GET
  name: list-themes
  path: /v1/themes
personas: []
provider_name: Apple Keynote
provider_slug: apple-keynote
search_terms:
- creates a new keynote presentation with a specified title and optional theme
- export a presentation to pdf, pptx, or images
- apple
- Marketing Professional
- exports a keynote presentation to pdf format with optional presenter notes
- icloud
- list presentations
- adds a new slide to a keynote presentation at a specified position with a chosen layout
- export keynote to pdf
- presentations
- list keynote themes
- presentation export to different formats
- add slide to presentation
- iwork
- list keynote presentations
- end-to-end keynote presentation creation and management via icloud
- lists all keynote presentations stored in the user's icloud account
- list slides in a presentation
- export presentation
- design
- list presentation slides
- list slides
- automation
- keynote
- productivity
- presentation lifecycle management
- slide management within presentations
- lists all slides in a keynote presentation with their titles and layouts
- Content Creator
- creating, organizing, and managing keynote presentation documents
- converting and sharing presentations in different formats
- individual creating presentations for training, education, or personal use
- create a new presentation with title and theme
- list themes
- list all keynote presentations in icloud
- marketing team member creating brand presentations, pitch decks, and sales materials
- list available keynote themes
- themes, layouts, and visual styling of presentations
- slides
- create presentation
- create keynote presentation
- available themes and templates
- lists all available keynote themes and templates for new presentations
slug: presentation-automation
tags:
- Apple
- Keynote
- Presentations
- Automation
- Productivity
- iCloud
tools:
- description: Lists all Keynote presentations stored in the user's iCloud account
  hints:
    idempotent: true
    readOnly: true
  name: list-keynote-presentations
- description: Creates a new Keynote presentation with a specified title and optional theme
  hints:
    destructive: false
    readOnly: false
  name: create-keynote-presentation
- description: Lists all slides in a Keynote presentation with their titles and layouts
  hints:
    idempotent: true
    readOnly: true
  name: list-presentation-slides
- description: Adds a new slide to a Keynote presentation at a specified position with a chosen layout
  hints:
    destructive: false
    readOnly: false
  name: add-slide-to-presentation
- description: Exports a Keynote presentation to PDF format with optional presenter notes
  hints:
    idempotent: true
    readOnly: true
  name: export-keynote-to-pdf
- description: Lists all available Keynote themes and templates for new presentations
  hints:
    idempotent: true
    readOnly: true
  name: list-keynote-themes
---
