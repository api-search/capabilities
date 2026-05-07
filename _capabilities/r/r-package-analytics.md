---
categories: []
consumed_apis: []
description: R package ecosystem analytics workflow combining METACRAN CranLogs download statistics, CranDB package metadata, and R version information. Used by R package maintainers, data scientists, CI/CD engineers, and ecosystem researchers to analyze package adoption, trends, R version compatibility, and ecosystem health.
layout: capability
name: R Package Analytics
operations:
- description: Get CRAN package metadata
  method: GET
  name: get-package
  path: /v1/packages/{package}
- description: Get total download counts for packages
  method: GET
  name: get-download-totals
  path: /v1/downloads/total/{period}/{packages}
- description: Get daily download counts for packages
  method: GET
  name: get-daily-downloads
  path: /v1/downloads/daily/{period}/{packages}
- description: Get most-downloaded CRAN packages
  method: GET
  name: get-top-packages
  path: /v1/top/{period}/{count}
- description: Get current stable R release version and date
  method: GET
  name: get-r-release
  path: /v1/r/release
- description: List all historical R releases
  method: GET
  name: list-r-versions
  path: /v1/r/versions
personas: []
provider_name: R
provider_slug: r
search_terms:
- get r release
- get previous r version
- get top packages
- get cran package metadata
- get total download counts for packages
- get current stable r release version and date
- list all cran packages
- get most-downloaded cran packages
- top downloaded packages
- daily package download counts
- r package metadata
- get daily downloads
- get top downloaded packages
- get the current stable r release version number and date. use to verify ci/cd pipelines target the latest r.
- open source
- all r release versions
- list all r versions
- get package
- downloads
- versions
- package analytics
- data science
- get current r version
- programming language
- list all r packages available on cran with their current version numbers.
- list r versions
- get the most-downloaded r packages from cran for last-day, last-week, or last-month. returns up to 100 packages ranked by download count.
- cran
- get package daily downloads
- package download totals
- get the previous stable r release (oldrel) version for backward compatibility testing.
- list all historical r releases with version numbers, release dates, and nicknames.
- get daily download counts for packages
- statistics
- get package download totals
- get total cran download counts for r packages for a given period (last-day, last-week, last-month, grand-total, or custom date range like 2023-01-01:2023-12-31).
- list all historical r releases
- get detailed metadata for a cran r package including description, version, author, maintainer, dependencies (imports, depends, suggests), license, and urls.
- get download totals
- current r release version
- get daily cran download breakdown for r packages over a period. useful for trend analysis and identifying download spikes.
slug: r-package-analytics
source_filename: r-package-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: R Package Analytics\n  description: R package ecosystem analytics workflow combining METACRAN CranLogs download statistics, CranDB package metadata,\n    and R version information. Used by R package maintainers, data scientists, CI/CD engineers, and ecosystem researchers\n    to analyze package adoption, trends, R version compatibility, and ecosystem health.\n  tags:\n  - R\n  - CRAN\n  - Package Analytics\n  - Downloads\n  - Open Source\n  - Statistics\n  - Versions\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds: []\ncapability:\n  consumes:\n  - type: http\n    namespace: cranlogs\n    baseUri: https://cranlogs.r-pkg.org\n    description: METACRAN CranLogs public API — no authentication required\n    resources:\n    - name: download-totals\n      path: /downloads/total\n      description: Total download counts for R packages\n      operations:\n      - name: get-package-download-totals\n        method: GET\n        description:\
  \ Get total download counts for packages over a period\n        inputParameters:\n        - name: period\n          in: path\n          type: string\n          required: true\n          description: 'Period: last-day, last-week, last-month, grand-total, or date range'\n        - name: packages\n          in: path\n          type: string\n          required: true\n          description: Package name or comma-separated list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: download-daily\n      path: /downloads/daily\n      description: Daily download counts for R packages\n      operations:\n      - name: get-package-download-daily\n        method: GET\n        description: Get daily download breakdown for packages over a period\n        inputParameters:\n        - name: period\n          in: path\n          type: string\n          required: true\n          description: Period or date range\n     \
  \   - name: packages\n          in: path\n          type: string\n          required: true\n          description: Package name or comma-separated list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: top-packages\n      path: /top\n      description: Most-downloaded CRAN packages\n      operations:\n      - name: get-top-packages\n        method: GET\n        description: Get the most-downloaded CRAN packages for a period\n        inputParameters:\n        - name: period\n          in: path\n          type: string\n          required: true\n          description: 'Period: last-day, last-week, last-month'\n        - name: count\n          in: path\n          type: integer\n          required: true\n          description: Number of top packages (max 100)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n\
  \    namespace: crandb\n    baseUri: https://crandb.r-pkg.org\n    description: METACRAN CranDB public API — no authentication required\n    resources:\n    - name: packages\n      path: /\n      description: CRAN package metadata\n      operations:\n      - name: get-package\n        method: GET\n        description: Get metadata for the latest version of a CRAN package\n        inputParameters:\n        - name: package\n          in: path\n          type: string\n          required: true\n          description: CRAN package name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-package-version\n        method: GET\n        description: Get metadata for a specific version of a CRAN package\n        inputParameters:\n        - name: package\n          in: path\n          type: string\n          required: true\n          description: CRAN package name\n        - name: version\n          in: path\n\
  \          type: string\n          required: true\n          description: Version string or 'all'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: all-packages\n      path: /-/pkgs\n      description: All CRAN package names and versions\n      operations:\n      - name: list-all-packages\n        method: GET\n        description: List all CRAN packages with latest versions\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: rversions\n    baseUri: https://rversions.r-pkg.org\n    description: R Versions public API — no authentication required\n    resources:\n    - name: current-release\n      path: /r-release\n      description: Current stable R release\n      operations:\n      - name: get-r-release\n        method: GET\n        description: Get the current stable\
  \ R release version and date\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: previous-release\n      path: /r-oldrel\n      description: Previous (old-rel) R release\n      operations:\n      - name: get-r-oldrel\n        method: GET\n        description: Get the previous stable R release for backward compatibility testing\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: all-versions\n      path: /r-versions\n      description: All historical R releases\n      operations:\n      - name: list-r-versions\n        method: GET\n        description: List all historical R release versions with dates and nicknames\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: r-package-analytics-api\n    description: Unified REST API for R package analytics combining metadata and download statistics.\n    resources:\n    - path: /v1/packages/{package}\n      name: packages\n      description: R package metadata\n      operations:\n      - method: GET\n        name: get-package\n        description: Get CRAN package metadata\n        call: crandb.get-package\n        with:\n          package: rest.package\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/downloads/total/{period}/{packages}\n      name: download-totals\n      description: Package download totals\n      operations:\n      - method: GET\n        name: get-download-totals\n        description: Get total download counts for packages\n        call: cranlogs.get-package-download-totals\n        with:\n          period: rest.period\n          packages: rest.packages\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/downloads/daily/{period}/{packages}\n      name: daily-downloads\n      description: Daily package download counts\n      operations:\n      - method: GET\n        name: get-daily-downloads\n        description: Get daily download counts for packages\n        call: cranlogs.get-package-download-daily\n        with:\n          period: rest.period\n          packages: rest.packages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/top/{period}/{count}\n      name: top-packages\n      description: Top downloaded packages\n      operations:\n      - method: GET\n        name: get-top-packages\n        description: Get most-downloaded CRAN packages\n        call: cranlogs.get-top-packages\n        with:\n          period: rest.period\n          count: rest.count\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/r/release\n      name: r-release\n \
  \     description: Current R release version\n      operations:\n      - method: GET\n        name: get-r-release\n        description: Get current stable R release version and date\n        call: rversions.get-r-release\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/r/versions\n      name: r-versions\n      description: All R release versions\n      operations:\n      - method: GET\n        name: list-r-versions\n        description: List all historical R releases\n        call: rversions.list-r-versions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: r-package-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted R package ecosystem analysis.\n    tools:\n    - name: get-cran-package-metadata\n      description: Get detailed metadata for a CRAN R package including description, version, author, maintainer, dependencies\n        (Imports, Depends,\
  \ Suggests), license, and URLs.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: crandb.get-package\n      with:\n        package: tools.package\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-package-download-totals\n      description: Get total CRAN download counts for R packages for a given period (last-day, last-week, last-month, grand-total,\n        or custom date range like 2023-01-01:2023-12-31).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: cranlogs.get-package-download-totals\n      with:\n        period: tools.period\n        packages: tools.packages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-package-daily-downloads\n      description: Get daily CRAN download breakdown for R packages over a period. Useful for trend analysis and identifying\n        download spikes.\n      hints:\n        readOnly: true\n        openWorld: false\n      call:\
  \ cranlogs.get-package-download-daily\n      with:\n        period: tools.period\n        packages: tools.packages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-downloaded-packages\n      description: Get the most-downloaded R packages from CRAN for last-day, last-week, or last-month. Returns up to 100\n        packages ranked by download count.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: cranlogs.get-top-packages\n      with:\n        period: tools.period\n        count: tools.count\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-all-cran-packages\n      description: List all R packages available on CRAN with their current version numbers.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: crandb.list-all-packages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-current-r-version\n      description: Get the current\
  \ stable R release version number and date. Use to verify CI/CD pipelines target the latest\n        R.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rversions.get-r-release\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-previous-r-version\n      description: Get the previous stable R release (oldrel) version for backward compatibility testing.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rversions.get-r-oldrel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-all-r-versions\n      description: List all historical R releases with version numbers, release dates, and nicknames.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rversions.list-r-versions\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/r/refs/heads/main/capabilities/r-package-analytics.yaml
tags:
- R
- CRAN
- Package Analytics
- Downloads
- Open Source
- Statistics
- Versions
tools:
- description: Get detailed metadata for a CRAN R package including description, version, author, maintainer, dependencies (Imports, Depends, Suggests), license, and URLs.
  hints:
    openWorld: false
    readOnly: true
  name: get-cran-package-metadata
- description: Get total CRAN download counts for R packages for a given period (last-day, last-week, last-month, grand-total, or custom date range like 2023-01-01:2023-12-31).
  hints:
    openWorld: false
    readOnly: true
  name: get-package-download-totals
- description: Get daily CRAN download breakdown for R packages over a period. Useful for trend analysis and identifying download spikes.
  hints:
    openWorld: false
    readOnly: true
  name: get-package-daily-downloads
- description: Get the most-downloaded R packages from CRAN for last-day, last-week, or last-month. Returns up to 100 packages ranked by download count.
  hints:
    openWorld: false
    readOnly: true
  name: get-top-downloaded-packages
- description: List all R packages available on CRAN with their current version numbers.
  hints:
    openWorld: false
    readOnly: true
  name: list-all-cran-packages
- description: Get the current stable R release version number and date. Use to verify CI/CD pipelines target the latest R.
  hints:
    openWorld: false
    readOnly: true
  name: get-current-r-version
- description: Get the previous stable R release (oldrel) version for backward compatibility testing.
  hints:
    openWorld: false
    readOnly: true
  name: get-previous-r-version
- description: List all historical R releases with version numbers, release dates, and nicknames.
  hints:
    openWorld: false
    readOnly: true
  name: list-all-r-versions
---
