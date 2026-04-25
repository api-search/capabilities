---
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
- generate invoice pdf
- generates a pdf invoice from an html template with dynamic order data
- extracting structured data from documents like pdfs
- pdf generation
- data processing
- integrates apyhub document utilities into web and mobile applications
- converts a webpage or html document to pdf format
- developer utilities
- gets the current exchange rate and converts a currency amount
- converting documents between formats (html to pdf, word to pdf)
- generating pdfs from html templates with dynamic data
- document processing
- data extraction
- api platform
- get exchange rate
- document conversion
- apyhub
- extract document text
- convert webpage to pdf
- convert, generate, and extract data from documents using apyhub
- extracts text content from a pdf document for processing
- uses apyhub to generate pdfs and process documents at scale
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
