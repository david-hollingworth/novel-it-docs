---
title: "13 Visualisation"
description: "Graph and visual representations of novel data"
draft: false
revision: "1.0"
revision_date: "20-Apr-2026"
---

The visualisation module provides graphical views of novel data that complement the board-based navigation. Rather than presenting a global view of all entities at once, the graph is always focused on a specific entity and expands outward to show its connections. This keeps the view manageable and meaningful regardless of the size of the novel.

## FEAT-1301 Entity relationship graph

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |

### Description

Every entity in the application shall display a graph icon alongside its other action buttons (Edit, Archive, Delete etc.). Clicking the graph icon opens the relationship graph focused on that entity.

The focused entity is displayed as the central node. Connected entities are displayed as surrounding nodes, with edges representing the relationships between them. The types of connections displayed depend on the active filters.

#### Graph filters

The user shall be able to filter the graph by entity family. The following filters shall be available and may be selected in any combination:

- **Manuscript** — novels, parts, chapters, and scenes connected to the focused entity via the manuscript hierarchy or via plot scene associations. Where a planning entity is shared across novels, connections to all associated novels are shown.
- **Planning** — characters, locations, items, and world building connected to the focused entity via FEAT-0010 relationships or via FEAT-0307 automatic cross-referencing. Shared entities show connections to all novels they appear in.
- **Plotting** — plots, acts, sequences, beats, and plot scenes connected to the focused entity via the plot hierarchy or via plot scene to manuscript scene associations

By default all three filters are active. Deselecting a filter removes that family of nodes and their edges from the graph.

#### Node display

- Each entity type shall be represented by a distinct node style (shape or colour) to allow visual differentiation
- The focused entity shall be visually distinguished from connected entities
- Hovering over a node shall display a brief summary popup showing the entity name, type, and a short excerpt of its description
- Clicking on a node shall open that entity's details page

#### Graph navigation

- The user shall be able to navigate the graph by dragging the canvas
- The user shall be able to zoom in and out of the graph
- The user shall be able to re-centre the graph on the focused entity at any time
- The user shall be able to search within the graph to locate a specific connected entity by name
