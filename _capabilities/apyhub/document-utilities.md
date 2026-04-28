---
categories:
- document-processing
consumed_apis:
- apyhub
description: Workflow capability for document processing utilities using ApyHub. Supports developers and content teams generating PDFs, converting documents, extracting text, and processing data without building custom infrastructure.
layout: capability
name: ApyHub Document Utilities
operations: []
personas: []
provider_name: ApyHub
provider_slug: apyhub
search_terms:
- apyhub
- data processing
- convert, generate, and extract data from documents using apyhub
- converts a webpage or html document to pdf format
- pdf generation
- document conversion
- extracts text content from a pdf document for processing
- developer utilities
- generate invoice pdf
- get exchange rate
- document processing
- integrates apyhub document utilities into web and mobile applications
- extracting structured data from documents like pdfs
- data extraction
- gets the current exchange rate and converts a currency amount
- api platform
- convert webpage to pdf
- uses apyhub to generate pdfs and process documents at scale
- converting documents between formats (html to pdf, word to pdf)
- extract document text
- generating pdfs from html templates with dynamic data
- generates a pdf invoice from an html template with dynamic order data
- utility apis
slug: document-utilities
tags:
- ApyHub
- Document Processing
- PDF Generation
- Data Extraction
- Developer Utilities
tools:
- description: Generates a PDF invoice from an HTML template with dynamic order data
  hints:
    destructive: false
    readOnly: false
  name: generate-invoice-pdf
- description: Converts a webpage or HTML document to PDF format
  hints:
    destructive: false
    readOnly: false
  name: convert-webpage-to-pdf
- description: Extracts text content from a PDF document for processing
  hints:
    idempotent: true
    readOnly: false
  name: extract-document-text
- description: Gets the current exchange rate and converts a currency amount
  hints:
    idempotent: true
    readOnly: false
  name: get-exchange-rate
---
