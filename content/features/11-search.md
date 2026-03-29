---
title: "11 Search"
description: "Global search across novel content and planning entities"
draft: false
---

The search feature allows the user to search across all content within a novel, or across all novels they own. Search results are grouped by entity type and ranked by relevance within each group.

## FEAT-1101 Global search

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

### Description

The user shall be able to search across all content in the application from a persistent search interface.

The following fields are included in the search index:

- Manuscript — scene content, chapter titles, part titles
- Characters — name, description, notes, and all other text fields
- Locations — name, description, notes, and all other text fields
- Items — name, description, notes, and all other text fields
- World building — name, description, notes, and all other text fields
- Research notes — title, description, notes
- Plot — plot name, act name, sequence name, beat name, plot scene name, and all associated text fields

Archived entities are not included in search results.

## FEAT-1102 Search filters

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

### Description

The user shall be able to filter search results by any combination of the following dimensions. All filters default to their broadest setting and persist for the duration of the search session.

**Novel scope**
- This novel (default)
- All my novels

**Entity type**
- Manuscript (parts, chapters, scenes)
- Characters
- Locations
- Items
- World building
- Research notes
- Plot

Filters may be combined freely. By default all entity types are included in results.

## FEAT-1103 Search results display

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

### Description

Search results shall be grouped by entity type. Within each group, results shall be ranked by relevance using the following priority:

1. Exact match on entity name or title
2. Partial match on entity name or title
3. Match within body text fields (description, notes, content)

Each result shall display:

- The entity name or title
- The entity type
- The novel the entity belongs to (when searching across all novels)
- A brief excerpt showing the matched text in context

Clicking a result shall navigate directly to that entity's details page.

## FEAT-1104 Search highlighting

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

### Description

The search term shall be highlighted wherever it appears within the result excerpts, allowing the user to quickly identify why a result was returned.
