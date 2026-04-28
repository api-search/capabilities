---
categories:
- document-processing
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
- apache pdfbox
- get form fields
- pdf
- list pages
- get interactive form fields from a pdf document
- apply a digital signature to a pdf document
- digital signatures
- create document
- get metadata
- document processing
- split a pdf document at specified page boundaries
- extract text content from a pdf document
- apache
- java
- merge documents
- open source
- split document
- Document Manager
- create a new pdf document
- sign document
- get pdf document metadata (title, author, dates)
- Application Developer
- list pages and their dimensions in a pdf
- integrates pdf processing into applications
- creates and manages pdf documents with metadata and signatures
- merge multiple pdf documents into one
- extract text
- text extraction
- extract text from pdf
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
