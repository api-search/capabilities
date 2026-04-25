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
- create pdf document
- get metadata
- create a new pdf document
- text extraction
- list pages
- merge multiple pdf documents into one
- split document
- integrates pdf processing into applications
- java
- list pages and their dimensions in a pdf
- split a pdf document at specified page boundaries
- sign document
- create document
- get interactive form fields from a pdf document
- extract text from pdf
- creates and manages pdf documents with metadata and signatures
- apache pdfbox
- apply a digital signature to a pdf document
- get pdf document metadata (title, author, dates)
- document processing
- get form fields
- pdf
- digital signatures
- apache
- merge documents
- Application Developer
- extract text
- open source
- extract text content from a pdf document
- Document Manager
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
