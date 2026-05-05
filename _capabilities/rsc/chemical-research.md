---
categories: []
consumed_apis:
- chemspider-compounds
description: Workflow capability for chemical research and cheminformatics tasks using the RSC ChemSpider database. Supports compound discovery, structure lookup, property analysis, and cross-database reference retrieval for researchers, data scientists, and pharmaceutical developers working with chemical data.
layout: capability
name: RSC Chemical Research
operations:
- description: Submit a name-based compound search
  method: POST
  name: search-compounds-by-name
  path: /v1/compounds/search/name
- description: Submit a SMILES-based compound search
  method: POST
  name: search-compounds-by-smiles
  path: /v1/compounds/search/smiles
- description: Submit a formula-based compound search
  method: POST
  name: search-compounds-by-formula
  path: /v1/compounds/search/formula
- description: Submit a mass-based compound search
  method: POST
  name: search-compounds-by-mass
  path: /v1/compounds/search/mass
- description: Poll search query status
  method: GET
  name: get-search-status
  path: /v1/compounds/search/{queryId}/status
- description: Get compound search results
  method: GET
  name: get-search-results
  path: /v1/compounds/search/{queryId}/results
- description: Retrieve compound properties
  method: GET
  name: get-compound
  path: /v1/compounds/{recordId}
- description: Retrieve external references for a compound
  method: GET
  name: get-compound-references
  path: /v1/compounds/{recordId}/references
- description: Retrieve details for multiple compounds
  method: POST
  name: get-compounds-batch
  path: /v1/compounds/batch
- description: Convert SMILES, InChI, InChIKey, or Mol format
  method: POST
  name: convert-format
  path: /v1/tools/convert
- description: Check if an InChIKey is valid
  method: POST
  name: validate-inchikey
  path: /v1/tools/validate/inchikey
- description: Get all available ChemSpider data sources
  method: GET
  name: list-data-sources
  path: /v1/data-sources
personas: []
provider_name: RSC
provider_slug: rsc
search_terms:
- get compounds batch
- get compound details by chemspider record id
- rsc
- get detailed properties for multiple compounds at once (up to 100)
- get compound references
- check the status of a chemspider compound search query
- search the rsc chemspider database for a compound by inchikey
- science
- get compound
- search the rsc chemspider database for compounds within a molecular mass range
- get details for multiple compounds
- list available data sources
- cheminformatics
- chemistry
- submit a name-based compound search
- check status of a compound search query
- validate inchikey format
- convert chemical identifier
- retrieve compound properties
- list data sources
- search compound by formula
- search compounds by smiles
- search for compounds by smiles
- convert between chemical identifier formats
- search compound by inchi
- get search results
- search compounds by name
- get external database references for a compound
- search for compounds by molecular formula
- get compound batch
- check if an inchikey is valid
- search the rsc chemspider database for compounds by chemical name
- search compound by smiles
- retrieve results from a completed compound search
- search the rsc chemspider database for compounds by molecular formula (e.g., c6h12o6)
- search for compounds by name
- submit a formula-based compound search
- convert a chemical identifier between smiles, inchi, inchikey, and mol file formats
- submit a smiles-based compound search
- validate inchikey
- search compound by inchikey
- retrieve compound record ids from a completed chemspider search query
- validate whether a string is a correctly formed inchikey
- get detailed chemical properties for a compound by chemspider record id
- get compound details
- chemical data
- get all available chemspider data sources
- get search status
- search compound by mass
- search the rsc chemspider database for compounds matching a smiles string
- search for compounds by molecular mass
- check search status
- convert format
- search compounds by formula
- get compound external references
- retrieve details for multiple compounds
- list all data sources available in chemspider for filtering searches
- search compound by name
- search the rsc chemspider database for compounds by inchi string
- get compound search results
- get external database references (pubchem, pubmed, etc.) for a compound
- retrieve external references for a compound
- chemspider
- search compounds by mass
- chemical research
- submit a mass-based compound search
- poll search query status
- convert smiles, inchi, inchikey, or mol format
slug: chemical-research
source_filename: chemical-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"RSC Chemical Research\"\n  description: >-\n    Workflow capability for chemical research and cheminformatics tasks using\n    the RSC ChemSpider database. Supports compound discovery, structure lookup,\n    property analysis, and cross-database reference retrieval for researchers,\n    data scientists, and pharmaceutical developers working with chemical data.\n  tags:\n    - Chemistry\n    - Cheminformatics\n    - Chemical Research\n    - RSC\n    - ChemSpider\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RSC_API_KEY: RSC_API_KEY\n\ncapability:\n  consumes:\n    - import: chemspider-compounds\n      location: ./shared/chemspider-compounds.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: chemical-research-api\n      description: \"Unified REST API for chemical compound research and cheminformatics workflows.\"\n      resources:\n        - path: /v1/compounds/search/name\n\
  \          name: compound-name-search\n          description: \"Search for compounds by name\"\n          operations:\n            - method: POST\n              name: search-compounds-by-name\n              description: \"Submit a name-based compound search\"\n              call: \"chemspider-compounds.filter-by-name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compounds/search/smiles\n          name: compound-smiles-search\n          description: \"Search for compounds by SMILES\"\n          operations:\n            - method: POST\n              name: search-compounds-by-smiles\n              description: \"Submit a SMILES-based compound search\"\n              call: \"chemspider-compounds.filter-by-smiles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compounds/search/formula\n          name: compound-formula-search\n          description:\
  \ \"Search for compounds by molecular formula\"\n          operations:\n            - method: POST\n              name: search-compounds-by-formula\n              description: \"Submit a formula-based compound search\"\n              call: \"chemspider-compounds.filter-by-formula\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compounds/search/mass\n          name: compound-mass-search\n          description: \"Search for compounds by molecular mass\"\n          operations:\n            - method: POST\n              name: search-compounds-by-mass\n              description: \"Submit a mass-based compound search\"\n              call: \"chemspider-compounds.filter-by-mass\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compounds/search/{queryId}/status\n          name: search-status\n          description: \"Check status of a compound search\
  \ query\"\n          operations:\n            - method: GET\n              name: get-search-status\n              description: \"Poll search query status\"\n              call: \"chemspider-compounds.get-filter-status\"\n              with:\n                queryId: \"rest.queryId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compounds/search/{queryId}/results\n          name: search-results\n          description: \"Retrieve results from a completed compound search\"\n          operations:\n            - method: GET\n              name: get-search-results\n              description: \"Get compound search results\"\n              call: \"chemspider-compounds.get-filter-results\"\n              with:\n                queryId: \"rest.queryId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compounds/{recordId}\n          name: compound-details\n\
  \          description: \"Get compound details by ChemSpider record ID\"\n          operations:\n            - method: GET\n              name: get-compound\n              description: \"Retrieve compound properties\"\n              call: \"chemspider-compounds.get-record-details\"\n              with:\n                recordId: \"rest.recordId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compounds/{recordId}/references\n          name: compound-references\n          description: \"Get external database references for a compound\"\n          operations:\n            - method: GET\n              name: get-compound-references\n              description: \"Retrieve external references for a compound\"\n              call: \"chemspider-compounds.get-external-references\"\n              with:\n                recordId: \"rest.recordId\"\n              outputParameters:\n                - type: object\n           \
  \       mapping: \"$.\"\n        - path: /v1/compounds/batch\n          name: compound-batch\n          description: \"Get details for multiple compounds\"\n          operations:\n            - method: POST\n              name: get-compounds-batch\n              description: \"Retrieve details for multiple compounds\"\n              call: \"chemspider-compounds.get-records-batch\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tools/convert\n          name: format-conversion\n          description: \"Convert between chemical identifier formats\"\n          operations:\n            - method: POST\n              name: convert-format\n              description: \"Convert SMILES, InChI, InChIKey, or Mol format\"\n              call: \"chemspider-compounds.convert-chemical-format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tools/validate/inchikey\n\
  \          name: inchikey-validation\n          description: \"Validate InChIKey format\"\n          operations:\n            - method: POST\n              name: validate-inchikey\n              description: \"Check if an InChIKey is valid\"\n              call: \"chemspider-compounds.validate-inchikey\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-sources\n          name: data-sources\n          description: \"List available data sources\"\n          operations:\n            - method: GET\n              name: list-data-sources\n              description: \"Get all available ChemSpider data sources\"\n              call: \"chemspider-compounds.get-data-sources\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: chemical-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted\
  \ chemical research using the RSC ChemSpider database.\"\n      tools:\n        - name: search-compound-by-name\n          description: \"Search the RSC ChemSpider database for compounds by chemical name\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"chemspider-compounds.filter-by-name\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-compound-by-smiles\n          description: \"Search the RSC ChemSpider database for compounds matching a SMILES string\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"chemspider-compounds.filter-by-smiles\"\n          with:\n            smiles: \"tools.smiles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-compound-by-inchi\n          description: \"Search the RSC ChemSpider database\
  \ for compounds by InChI string\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"chemspider-compounds.filter-by-inchi\"\n          with:\n            inchi: \"tools.inchi\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-compound-by-inchikey\n          description: \"Search the RSC ChemSpider database for a compound by InChIKey\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"chemspider-compounds.filter-by-inchikey\"\n          with:\n            inchikey: \"tools.inchikey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-compound-by-formula\n          description: \"Search the RSC ChemSpider database for compounds by molecular formula (e.g., C6H12O6)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"chemspider-compounds.filter-by-formula\"\
  \n          with:\n            formula: \"tools.formula\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-compound-by-mass\n          description: \"Search the RSC ChemSpider database for compounds within a molecular mass range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"chemspider-compounds.filter-by-mass\"\n          with:\n            mass: \"tools.mass\"\n            massRange: \"tools.massRange\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-search-status\n          description: \"Check the status of a ChemSpider compound search query\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"chemspider-compounds.get-filter-status\"\n          with:\n            queryId: \"tools.queryId\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: get-search-results\n          description: \"Retrieve compound record IDs from a completed ChemSpider search query\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"chemspider-compounds.get-filter-results\"\n          with:\n            queryId: \"tools.queryId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-compound-details\n          description: \"Get detailed chemical properties for a compound by ChemSpider record ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"chemspider-compounds.get-record-details\"\n          with:\n            recordId: \"tools.recordId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-compound-batch\n          description: \"Get detailed properties for multiple compounds at once (up to 100)\"\n          hints:\n  \
  \          readOnly: true\n            openWorld: false\n          call: \"chemspider-compounds.get-records-batch\"\n          with:\n            recordIds: \"tools.recordIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-compound-external-references\n          description: \"Get external database references (PubChem, PubMed, etc.) for a compound\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"chemspider-compounds.get-external-references\"\n          with:\n            recordId: \"tools.recordId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: convert-chemical-identifier\n          description: \"Convert a chemical identifier between SMILES, InChI, InChIKey, and Mol file formats\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"chemspider-compounds.convert-chemical-format\"\
  \n          with:\n            input: \"tools.input\"\n            inputFormat: \"tools.inputFormat\"\n            outputFormat: \"tools.outputFormat\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-inchikey\n          description: \"Validate whether a string is a correctly formed InChIKey\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"chemspider-compounds.validate-inchikey\"\n          with:\n            inchikey: \"tools.inchikey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-sources\n          description: \"List all data sources available in ChemSpider for filtering searches\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"chemspider-compounds.get-data-sources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rsc/refs/heads/main/capabilities/chemical-research.yaml
tags:
- Chemistry
- Cheminformatics
- Chemical Research
- RSC
- ChemSpider
tools:
- description: Search the RSC ChemSpider database for compounds by chemical name
  hints:
    openWorld: true
    readOnly: true
  name: search-compound-by-name
- description: Search the RSC ChemSpider database for compounds matching a SMILES string
  hints:
    openWorld: true
    readOnly: true
  name: search-compound-by-smiles
- description: Search the RSC ChemSpider database for compounds by InChI string
  hints:
    openWorld: true
    readOnly: true
  name: search-compound-by-inchi
- description: Search the RSC ChemSpider database for a compound by InChIKey
  hints:
    openWorld: true
    readOnly: true
  name: search-compound-by-inchikey
- description: Search the RSC ChemSpider database for compounds by molecular formula (e.g., C6H12O6)
  hints:
    openWorld: true
    readOnly: true
  name: search-compound-by-formula
- description: Search the RSC ChemSpider database for compounds within a molecular mass range
  hints:
    openWorld: true
    readOnly: true
  name: search-compound-by-mass
- description: Check the status of a ChemSpider compound search query
  hints:
    openWorld: false
    readOnly: true
  name: check-search-status
- description: Retrieve compound record IDs from a completed ChemSpider search query
  hints:
    openWorld: false
    readOnly: true
  name: get-search-results
- description: Get detailed chemical properties for a compound by ChemSpider record ID
  hints:
    openWorld: false
    readOnly: true
  name: get-compound-details
- description: Get detailed properties for multiple compounds at once (up to 100)
  hints:
    openWorld: false
    readOnly: true
  name: get-compound-batch
- description: Get external database references (PubChem, PubMed, etc.) for a compound
  hints:
    openWorld: true
    readOnly: true
  name: get-compound-external-references
- description: Convert a chemical identifier between SMILES, InChI, InChIKey, and Mol file formats
  hints:
    openWorld: false
    readOnly: true
  name: convert-chemical-identifier
- description: Validate whether a string is a correctly formed InChIKey
  hints:
    openWorld: false
    readOnly: true
  name: validate-inchikey
- description: List all data sources available in ChemSpider for filtering searches
  hints:
    openWorld: false
    readOnly: true
  name: list-data-sources
---
