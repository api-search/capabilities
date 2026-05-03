---
categories: []
consumed_apis:
- cranlogs
- crandb
- rversions
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
- get daily downloads
- get download totals
- package download totals
- get most-downloaded cran packages
- get daily cran download breakdown for r packages over a period. useful for trend analysis and identifying download spikes.
- downloads
- get the previous stable r release (oldrel) version for backward compatibility testing.
- open source
- get the most-downloaded r packages from cran for last-day, last-week, or last-month. returns up to 100 packages ranked by download count.
- list all cran packages
- get top downloaded packages
- all r release versions
- top downloaded packages
- list r versions
- versions
- list all r packages available on cran with their current version numbers.
- package analytics
- get top packages
- data science
- list all r versions
- daily package download counts
- current r release version
- get detailed metadata for a cran r package including description, version, author, maintainer, dependencies (imports, depends, suggests), license, and urls.
- get total cran download counts for r packages for a given period (last-day, last-week, last-month, grand-total, or custom date range like 2023-01-01:2023-12-31).
- get package download totals
- get cran package metadata
- get current r version
- get daily download counts for packages
- get current stable r release version and date
- statistics
- cran
- get package
- get the current stable r release version number and date. use to verify ci/cd pipelines target the latest r.
- get package daily downloads
- get previous r version
- r package metadata
- list all historical r releases
- get r release
- programming language
- get total download counts for packages
- list all historical r releases with version numbers, release dates, and nicknames.
slug: r-package-analytics
source_filename: r-package-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"R Package Analytics\"\n  description: \"R package ecosystem analytics workflow combining METACRAN CranLogs download statistics, CranDB package metadata, and R version information. Used by R package maintainers, data scientists, CI/CD engineers, and ecosystem researchers to analyze package adoption, trends, R version compatibility, and ecosystem health.\"\n  tags:\n    - R\n    - CRAN\n    - Package Analytics\n    - Downloads\n    - Open Source\n    - Statistics\n    - Versions\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds: []\n\ncapability:\n  consumes:\n    - import: cranlogs\n      location: ./shared/metacran-cranlogs.yaml\n    - import: crandb\n      location: ./shared/metacran-crandb.yaml\n    - import: rversions\n      location: ./shared/rversions.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: r-package-analytics-api\n      description: \"Unified REST API for R package analytics\
  \ combining metadata and download statistics.\"\n      resources:\n        - path: /v1/packages/{package}\n          name: packages\n          description: \"R package metadata\"\n          operations:\n            - method: GET\n              name: get-package\n              description: \"Get CRAN package metadata\"\n              call: \"crandb.get-package\"\n              with:\n                package: \"rest.package\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/downloads/total/{period}/{packages}\n          name: download-totals\n          description: \"Package download totals\"\n          operations:\n            - method: GET\n              name: get-download-totals\n              description: \"Get total download counts for packages\"\n              call: \"cranlogs.get-package-download-totals\"\n              with:\n                period: \"rest.period\"\n                packages: \"rest.packages\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/downloads/daily/{period}/{packages}\n          name: daily-downloads\n          description: \"Daily package download counts\"\n          operations:\n            - method: GET\n              name: get-daily-downloads\n              description: \"Get daily download counts for packages\"\n              call: \"cranlogs.get-package-download-daily\"\n              with:\n                period: \"rest.period\"\n                packages: \"rest.packages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/top/{period}/{count}\n          name: top-packages\n          description: \"Top downloaded packages\"\n          operations:\n            - method: GET\n              name: get-top-packages\n              description: \"Get most-downloaded CRAN packages\"\n              call: \"cranlogs.get-top-packages\"\
  \n              with:\n                period: \"rest.period\"\n                count: \"rest.count\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/r/release\n          name: r-release\n          description: \"Current R release version\"\n          operations:\n            - method: GET\n              name: get-r-release\n              description: \"Get current stable R release version and date\"\n              call: \"rversions.get-r-release\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/r/versions\n          name: r-versions\n          description: \"All R release versions\"\n          operations:\n            - method: GET\n              name: list-r-versions\n              description: \"List all historical R releases\"\n              call: \"rversions.list-r-versions\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: r-package-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted R package ecosystem analysis.\"\n      tools:\n        - name: get-cran-package-metadata\n          description: \"Get detailed metadata for a CRAN R package including description, version, author, maintainer, dependencies (Imports, Depends, Suggests), license, and URLs.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"crandb.get-package\"\n          with:\n            package: \"tools.package\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-package-download-totals\n          description: \"Get total CRAN download counts for R packages for a given period (last-day, last-week, last-month, grand-total, or custom date range like 2023-01-01:2023-12-31).\"\n          hints:\n            readOnly: true\n\
  \            openWorld: false\n          call: \"cranlogs.get-package-download-totals\"\n          with:\n            period: \"tools.period\"\n            packages: \"tools.packages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-package-daily-downloads\n          description: \"Get daily CRAN download breakdown for R packages over a period. Useful for trend analysis and identifying download spikes.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"cranlogs.get-package-download-daily\"\n          with:\n            period: \"tools.period\"\n            packages: \"tools.packages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-top-downloaded-packages\n          description: \"Get the most-downloaded R packages from CRAN for last-day, last-week, or last-month. Returns up to 100 packages ranked by download count.\"\n\
  \          hints:\n            readOnly: true\n            openWorld: false\n          call: \"cranlogs.get-top-packages\"\n          with:\n            period: \"tools.period\"\n            count: \"tools.count\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-all-cran-packages\n          description: \"List all R packages available on CRAN with their current version numbers.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"crandb.list-all-packages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-current-r-version\n          description: \"Get the current stable R release version number and date. Use to verify CI/CD pipelines target the latest R.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rversions.get-r-release\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: get-previous-r-version\n          description: \"Get the previous stable R release (oldrel) version for backward compatibility testing.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rversions.get-r-oldrel\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-all-r-versions\n          description: \"List all historical R releases with version numbers, release dates, and nicknames.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rversions.list-r-versions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
