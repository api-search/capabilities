---
categories:
- automation
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
- lists all available keynote themes and templates for new presentations
- presentation export to different formats
- marketing team member creating brand presentations, pitch decks, and sales materials
- automation
- slides
- lists all keynote presentations stored in the user's icloud account
- presentations
- available themes and templates
- apple
- export a presentation to pdf, pptx, or images
- add slide to presentation
- creates a new keynote presentation with a specified title and optional theme
- list all keynote presentations in icloud
- list slides
- converting and sharing presentations in different formats
- create a new presentation with title and theme
- exports a keynote presentation to pdf format with optional presenter notes
- list themes
- end-to-end keynote presentation creation and management via icloud
- Marketing Professional
- creating, organizing, and managing keynote presentation documents
- create keynote presentation
- list slides in a presentation
- presentation lifecycle management
- create presentation
- list keynote themes
- adds a new slide to a keynote presentation at a specified position with a chosen layout
- icloud
- slide management within presentations
- lists all slides in a keynote presentation with their titles and layouts
- individual creating presentations for training, education, or personal use
- productivity
- export keynote to pdf
- design
- export presentation
- Content Creator
- themes, layouts, and visual styling of presentations
- list available keynote themes
- list keynote presentations
- list presentations
- list presentation slides
- keynote
- iwork
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
