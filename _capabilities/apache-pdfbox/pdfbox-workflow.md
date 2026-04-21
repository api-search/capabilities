---
consumed_apis: []
description: Workflow for creating, manipulating, extracting text from, and digitally signing PDF documents using Apache PDFBox.
layout: capability
name: Apache PDFBox Document Processing Workflow
operations:
- description: Create PDF document
  method: POST
  name: create-document
  path: /v1/documents
- description: Extract text from PDF
  method: GET
  name: extract-text
  path: /v1/documents/{documentId}/text
personas: []
provider_name: Apache PDFBox
provider_slug: apache-pdfbox
search_terms:
- creates and manages pdf documents with metadata and signatures
- apache
- create pdf document
- pdf
- document processing
- split a pdf document at specified page boundaries
- get form fields
- java
- extract text from pdf
- text extraction
- get interactive form fields from a pdf document
- extract text content from a pdf document
- create a new pdf document
- apache pdfbox
- Application Developer
- get metadata
- list pages and their dimensions in a pdf
- list pages
- merge multiple pdf documents into one
- integrates pdf processing into applications
- digital signatures
- sign document
- extract text
- merge documents
- get pdf document metadata (title, author, dates)
- split document
- create document
- apply a digital signature to a pdf document
- Document Manager
- open source
slug: pdfbox-workflow
tags:
- Apache PDFBox
- PDF
- Document Processing
- Digital Signatures
tools:
- description: Create a new PDF document
  hints:
    readOnly: false
  name: create-document
- description: Extract text content from a PDF document
  hints:
    readOnly: true
  name: extract-text
- description: Get PDF document metadata (title, author, dates)
  hints:
    readOnly: true
  name: get-metadata
- description: List pages and their dimensions in a PDF
  hints:
    readOnly: true
  name: list-pages
- description: Merge multiple PDF documents into one
  hints:
    readOnly: false
  name: merge-documents
- description: Split a PDF document at specified page boundaries
  hints:
    readOnly: false
  name: split-document
- description: Apply a digital signature to a PDF document
  hints:
    readOnly: false
  name: sign-document
- description: Get interactive form fields from a PDF document
  hints:
    readOnly: true
  name: get-form-fields
---
