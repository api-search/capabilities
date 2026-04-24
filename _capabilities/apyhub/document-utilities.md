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
- api platform
- generating pdfs from html templates with dynamic data
- data processing
- extract document text
- integrates apyhub document utilities into web and mobile applications
- document conversion
- extracting structured data from documents like pdfs
- document processing
- apyhub
- converting documents between formats (html to pdf, word to pdf)
- utility apis
- get exchange rate
- generates a pdf invoice from an html template with dynamic order data
- extracts text content from a pdf document for processing
- data extraction
- convert webpage to pdf
- pdf generation
- generate invoice pdf
- developer utilities
- uses apyhub to generate pdfs and process documents at scale
- gets the current exchange rate and converts a currency amount
- convert, generate, and extract data from documents using apyhub
- converts a webpage or html document to pdf format
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
