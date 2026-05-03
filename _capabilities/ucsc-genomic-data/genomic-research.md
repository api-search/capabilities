---
categories: []
consumed_apis:
- ucsc-genome-browser
description: Workflow capability for computational biology research using the UCSC Genome Browser API. Supports genome assembly discovery, DNA sequence retrieval, annotation track analysis, and track hub management. Designed for bioinformaticians, genomics researchers, and computational biologists.
layout: capability
name: UCSC Genomic Research Workflow
operations:
- description: List all UCSC Genome Browser assemblies.
  method: GET
  name: list-ucsc-genomes
  path: /v1/genomes
- description: Search for genome assemblies by name or accession.
  method: GET
  name: find-genome
  path: /v1/genomes/search
- description: List all annotation tracks for a genome.
  method: GET
  name: list-tracks
  path: /v1/genomes/{genome}/tracks
- description: List chromosomes and their sizes for a genome.
  method: GET
  name: list-chromosomes
  path: /v1/genomes/{genome}/chromosomes
- description: Retrieve DNA sequence for a genomic region.
  method: GET
  name: get-dna-sequence
  path: /v1/sequence
- description: Retrieve annotation data from a specific track for a region.
  method: GET
  name: get-track-data
  path: /v1/track-data
- description: List all publicly available track hubs.
  method: GET
  name: list-public-hubs
  path: /v1/hubs
- description: Search track data, names, and descriptions in the Genome Browser.
  method: GET
  name: search-genome-browser
  path: /v1/search
personas: []
provider_name: UCSC Genomic Data
provider_slug: ucsc-genomic-data
search_terms:
- biology
- find genome
- get track data
- annotation
- research
- chromosome listings for a genome assembly.
- list all publicly available ucsc track hubs.
- list genome assemblies
- get chromosomes and their sizes for a genome assembly.
- search genome browser
- bioinformatics
- genome assembly search.
- get track annotations
- search for genome assemblies by name or accession.
- list all publicly available track hubs.
- list all annotation tracks available for a specific genome assembly.
- search track data, names, and descriptions in the genome browser.
- genome browser search.
- list public track hubs
- get annotation data from a specific track for a genomic region.
- public track hubs.
- list annotation tracks
- retrieve annotation data from a specific track for a region.
- dna sequence retrieval.
- genomics
- annotation tracks for a genome assembly.
- get dna sequence
- list tracks
- list chromosomes and their sizes for a genome.
- open science
- search for genome assemblies by organism name, accession, or keywords.
- get chromosomes
- search genomes
- retrieve dna sequence from a genome for a specified chromosomal region.
- list all annotation tracks for a genome.
- list ucsc genomes
- list all ucsc genome browser assemblies.
- search track data, names, and descriptions in the ucsc genome browser.
- list all genome assemblies available in the ucsc genome browser.
- ucsc genome assembly listings.
- annotation track data retrieval.
- ucsc
- dna
- list chromosomes
- list public hubs
- dna sequences
- retrieve dna sequence for a genomic region.
slug: genomic-research
source_filename: genomic-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"UCSC Genomic Research Workflow\"\n  description: >-\n    Workflow capability for computational biology research using the UCSC Genome Browser API.\n    Supports genome assembly discovery, DNA sequence retrieval, annotation track analysis,\n    and track hub management. Designed for bioinformaticians, genomics researchers,\n    and computational biologists.\n  tags:\n    - Genomics\n    - Bioinformatics\n    - DNA Sequences\n    - Annotation\n    - UCSC\n    - Research\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys: {}\n\ncapability:\n  consumes:\n    - import: ucsc-genome-browser\n      location: ./shared/genome-browser.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ucsc-genomic-research-api\n      description: \"Unified REST API for UCSC Genome Browser genomic data access.\"\n      resources:\n        - path: /v1/genomes\n          name: genomes\n      \
  \    description: \"UCSC genome assembly listings.\"\n          operations:\n            - method: GET\n              name: list-ucsc-genomes\n              description: \"List all UCSC Genome Browser assemblies.\"\n              call: \"ucsc-genome-browser.list-ucsc-genomes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/genomes/search\n          name: genome-search\n          description: \"Genome assembly search.\"\n          operations:\n            - method: GET\n              name: find-genome\n              description: \"Search for genome assemblies by name or accession.\"\n              call: \"ucsc-genome-browser.find-genome\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/genomes/{genome}/tracks\n          name: tracks\n          description: \"Annotation tracks for a genome\
  \ assembly.\"\n          operations:\n            - method: GET\n              name: list-tracks\n              description: \"List all annotation tracks for a genome.\"\n              call: \"ucsc-genome-browser.list-tracks\"\n              with:\n                genome: \"rest.genome\"\n                trackLeavesOnly: \"rest.trackLeavesOnly\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/genomes/{genome}/chromosomes\n          name: chromosomes\n          description: \"Chromosome listings for a genome assembly.\"\n          operations:\n            - method: GET\n              name: list-chromosomes\n              description: \"List chromosomes and their sizes for a genome.\"\n              call: \"ucsc-genome-browser.list-chromosomes\"\n              with:\n                genome: \"rest.genome\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n     \
  \   - path: /v1/sequence\n          name: sequence\n          description: \"DNA sequence retrieval.\"\n          operations:\n            - method: GET\n              name: get-dna-sequence\n              description: \"Retrieve DNA sequence for a genomic region.\"\n              call: \"ucsc-genome-browser.get-dna-sequence\"\n              with:\n                genome: \"rest.genome\"\n                chrom: \"rest.chrom\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n                revComp: \"rest.revComp\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/track-data\n          name: track-data\n          description: \"Annotation track data retrieval.\"\n          operations:\n            - method: GET\n              name: get-track-data\n              description: \"Retrieve annotation data from a specific track for a region.\"\n              call: \"ucsc-genome-browser.get-track-data\"\
  \n              with:\n                genome: \"rest.genome\"\n                track: \"rest.track\"\n                chrom: \"rest.chrom\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n                maxItemsOutput: \"rest.maxItemsOutput\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/hubs\n          name: hubs\n          description: \"Public track hubs.\"\n          operations:\n            - method: GET\n              name: list-public-hubs\n              description: \"List all publicly available track hubs.\"\n              call: \"ucsc-genome-browser.list-public-hubs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search\n          name: search\n          description: \"Genome Browser search.\"\n          operations:\n            - method: GET\n              name: search-genome-browser\n         \
  \     description: \"Search track data, names, and descriptions in the Genome Browser.\"\n              call: \"ucsc-genome-browser.search-genome-browser\"\n              with:\n                search: \"rest.search\"\n                genome: \"rest.genome\"\n                categories: \"rest.categories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ucsc-genomic-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted genomic research using the UCSC Genome Browser.\"\n      tools:\n        - name: list-genome-assemblies\n          description: \"List all genome assemblies available in the UCSC Genome Browser.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ucsc-genome-browser.list-ucsc-genomes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-genomes\n\
  \          description: \"Search for genome assemblies by organism name, accession, or keywords.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ucsc-genome-browser.find-genome\"\n          with:\n            q: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-annotation-tracks\n          description: \"List all annotation tracks available for a specific genome assembly.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ucsc-genome-browser.list-tracks\"\n          with:\n            genome: \"tools.genome\"\n            trackLeavesOnly: \"tools.trackLeavesOnly\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-chromosomes\n          description: \"Get chromosomes and their sizes for a genome assembly.\"\n          hints:\n            readOnly: true\n    \
  \        openWorld: true\n          call: \"ucsc-genome-browser.list-chromosomes\"\n          with:\n            genome: \"tools.genome\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-dna-sequence\n          description: \"Retrieve DNA sequence from a genome for a specified chromosomal region.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ucsc-genome-browser.get-dna-sequence\"\n          with:\n            genome: \"tools.genome\"\n            chrom: \"tools.chrom\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n            revComp: \"tools.revComp\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-track-annotations\n          description: \"Get annotation data from a specific track for a genomic region.\"\n          hints:\n            readOnly: true\n            openWorld: true\n        \
  \  call: \"ucsc-genome-browser.get-track-data\"\n          with:\n            genome: \"tools.genome\"\n            track: \"tools.track\"\n            chrom: \"tools.chrom\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-public-track-hubs\n          description: \"List all publicly available UCSC track hubs.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ucsc-genome-browser.list-public-hubs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-genome-browser\n          description: \"Search track data, names, and descriptions in the UCSC Genome Browser.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ucsc-genome-browser.search-genome-browser\"\n          with:\n            search: \"tools.query\"\n\
  \            genome: \"tools.genome\"\n            categories: \"tools.categories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ucsc-genomic-data/refs/heads/main/capabilities/genomic-research.yaml
tags:
- Genomics
- Bioinformatics
- DNA Sequences
- Annotation
- UCSC
- Research
tools:
- description: List all genome assemblies available in the UCSC Genome Browser.
  hints:
    openWorld: true
    readOnly: true
  name: list-genome-assemblies
- description: Search for genome assemblies by organism name, accession, or keywords.
  hints:
    openWorld: true
    readOnly: true
  name: search-genomes
- description: List all annotation tracks available for a specific genome assembly.
  hints:
    openWorld: true
    readOnly: true
  name: list-annotation-tracks
- description: Get chromosomes and their sizes for a genome assembly.
  hints:
    openWorld: true
    readOnly: true
  name: get-chromosomes
- description: Retrieve DNA sequence from a genome for a specified chromosomal region.
  hints:
    openWorld: true
    readOnly: true
  name: get-dna-sequence
- description: Get annotation data from a specific track for a genomic region.
  hints:
    openWorld: true
    readOnly: true
  name: get-track-annotations
- description: List all publicly available UCSC track hubs.
  hints:
    openWorld: true
    readOnly: true
  name: list-public-track-hubs
- description: Search track data, names, and descriptions in the UCSC Genome Browser.
  hints:
    openWorld: true
    readOnly: true
  name: search-genome-browser
---
