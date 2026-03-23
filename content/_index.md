---
title: "Novel-It Documentation"
description: "Feature specifications, requirements, and traceability for Novel-It"
---

**Please note. This site is a work in progress and doesn't yet contain a full list of Novel-It features 
and requirements. Please refer to [The Novel-It Blog](https://david-hollingworth.github.io/novel-it-site/posts/) for 
more information.**

[Novel-It](https://github.com/david-hollingworth/novel-it) is a self-hosted, open-source novel writing application. This site contains
the formal specifications and validation documentation that underpin its development.

## Release phases

Novel-It will be developed in the following phases:

| Phase | Description | Status |
| ----- | ----------- | ------ |
| 1 | Minimum Viable Product to allow the user to login, create novels and chapters and to write scenes. Includes basic character, location and item management. | In Progress |
| 2 | Plotting. Functionality to allow the user to plot a novel | Planned |
| 3 | Statistics and goals. Enhancements to manuscript features | Planning |
| 4 | Multi-user features. Collaboration. | To Plan |

## How this documentation is structured

Features describe what the application does from the user's perspective. Each feature
is supported by one or more formal requirements that define precisely how the system
behaves. Those requirements in turn drive the acceptance criteria used to validate
the implementation — ensuring that what was intended, what was built, and what was
tested are all traceable to each other.

The [Traceability Matrix](traceability/) maps features to requirements to test
coverage, giving a clear picture of where the application stands at any point in time.
