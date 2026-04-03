---
title: "08 Plot and Structure"
description: "Plot lines, acts, sequences, beats, and plot scenes"
draft: false
---

The plotting module allows the user to plan the narrative structure of their novel to whatever depth they choose. It is independent of the manuscript module but intersects with it at the scene level, where plot scenes can be associated with manuscript scenes.

A novel may have one or more named plot lines — for example a main plot and one or more subplots. Each plot line has its own independent hierarchy of acts, beats, and plot scenes.

All entities in this module extend the base entity features defined in [00 Base Entity Features](/novel-it-docs/features/00-base-entity-features).

## Navigation

The plotting module is accessed via a **Plotting** tab displayed at the top of all entity boards within a novel, alongside a **Manuscript** tab. The tab pair is available on all boards except the Novels board and the scene editor.

## Plot

A plot is the top-level entity in the plotting module. It represents a single narrative thread within the novel — a main plot, a subplot, a character arc, or any other story strand the author wishes to track separately.

### FEAT-0801 Plot list board

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0001 - Entity list board](/novel-it-docs/features/00-base-entity-features#feat-0001-entity-list-board) |

#### Description

The plot list board is displayed when the user selects the Plotting tab. It displays all plot lines belonging to the current novel.

As plots have no parent entity within the plotting module, the parent summary section is not displayed. The board displays plot cards only.

### FEAT-0802 Add plot

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0004 - Add entity](/novel-it-docs/features/00-base-entity-features#feat-0004-add-entity) |

#### Description

In addition to the properties inherited from the base entity, plots have the following properties:

- Plot name (overrides base entity Name)
- Sequences enabled? Yes / No
- Template — one of:
  - Freeform (no template)
  - Three-Act Structure
  - Five-Act Structure
  - Hero's Journey
  - Save the Cat
  - Eight-Sequence Structure

When a template is selected the application shall automatically create the appropriate acts, sequences (if applicable), and beats for that template. The author then populates the content of each element.

When Freeform is selected the plot is created empty and the author adds acts, sequences, beats, and plot scenes manually.

### FEAT-0803 Edit plot

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0002 - Edit entity](/novel-it-docs/features/00-base-entity-features#feat-0002-edit-entity) |

#### Description

In addition to the functions inherited from the base entity, the plot edit page provides the following function:

- Enable / disable sequences

When sequences are disabled any existing child beats are reparented directly onto their parent act.

### FEAT-0804 Archive plot

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0005 - Archive entity](/novel-it-docs/features/00-base-entity-features#feat-0005-archive-entity) |

#### Description

No plot-specific extensions to the base behaviour.

### FEAT-0805 Unarchive plot

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0003 - Archived entity list board](/novel-it-docs/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

#### Description

No plot-specific extensions to the base behaviour.

### FEAT-0806 Delete plot

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0006 - Delete entity](/novel-it-docs/features/00-base-entity-features#feat-0006-delete-entity) |

#### Description

When a plot is deleted all associated acts, sequences, beats, and plot scenes are also deleted. Any associations between deleted plot scenes and manuscript scenes are also removed.

### FEAT-0807 Duplicate plot

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0007 - Duplicate entity](/novel-it-docs/features/00-base-entity-features#feat-0007-duplicate-entity) |

#### Description

When a plot is duplicated all associated acts, sequences, beats, and plot scenes are duplicated. Associations between plot scenes and manuscript scenes are not duplicated.

---

## Act

Acts are the major structural divisions of a plot. They are the direct children of a plot.

### FEAT-0808 Plot structure display

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0001 - Entity list board](/novel-it-docs/features/00-base-entity-features#feat-0001-entity-list-board) |

#### Description

When the user clicks on a plot name on the plot list board the view changes to the plot structure display for that plot. This board displays the acts belonging to the plot.

### FEAT-0809 Add act

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0004 - Add entity](/novel-it-docs/features/00-base-entity-features#feat-0004-add-entity) |

#### Description

No act-specific extensions to the base behaviour.

### FEAT-0810 Edit act

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0002 - Edit entity](/novel-it-docs/features/00-base-entity-features#feat-0002-edit-entity) |

#### Description

No act-specific extensions to the base behaviour.

### FEAT-0811 Archive act

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0005 - Archive entity](/novel-it-docs/features/00-base-entity-features#feat-0005-archive-entity) |

#### Description

No act-specific extensions to the base behaviour.

### FEAT-0812 Unarchive act

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0003 - Archived entity list board](/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

#### Description

No act-specific extensions to the base behaviour.

### FEAT-0813 Reparent act

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0008 - Entity reparenting](/novel-it-docs/features/00-base-entity-features#feat-0008-entity-reparenting) |

#### Description

An act may be moved to a different plot line within the same novel.

### FEAT-0814 Cross-novel act relocation

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0011 - Cross-novel relocation](/novel-it-docs/features/00-base-entity-features#feat-0011-cross-novel-relocation) |

#### Description

No act-specific extensions to the base behaviour.

### FEAT-0815 Delete act

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0006 - Delete entity](/novel-it-docs/features/00-base-entity-features#feat-0006-delete-entity) |

#### Description

When an act is deleted all associated sequences, beats, and plot scenes are also deleted. Any associations between deleted plot scenes and manuscript scenes are also removed.

---

## Sequence

Sequences are an optional level of the plot hierarchy, sitting between acts and beats. They are enabled or disabled at the plot level via [FEAT-0803](#feat-0803-edit-plot).

When sequences are disabled, beats are parented directly off acts.

### FEAT-0816 Add sequence

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0004 - Add entity](/novel-it-docs/features/00-base-entity-features#feat-0004-add-entity) |

#### Description

No sequence-specific extensions to the base behaviour.

### FEAT-0817 Edit sequence

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0002 - Edit entity](/novel-it-docs/features/00-base-entity-features#feat-0002-edit-entity) |

#### Description

No sequence-specific extensions to the base behaviour.

### FEAT-0818 Archive sequence

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0005 - Archive entity](/novel-it-docs/features/00-base-entity-features#feat-0005-archive-entity) |

#### Description

No sequence-specific extensions to the base behaviour.

### FEAT-0819 Unarchive sequence

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0003 - Archived entity list board](/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

#### Description

No sequence-specific extensions to the base behaviour.

### FEAT-0820 Reparent sequence

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0008 - Entity reparenting](/novel-it-docs/features/00-base-entity-features#feat-0008-entity-reparenting) |

#### Description

A sequence may be moved to a different act within the same plot line.

### FEAT-0821 Delete sequence

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0006 - Delete entity](/novel-it-docs/features/00-base-entity-features#feat-0006-delete-entity) |

#### Description

When a sequence is deleted all associated beats and plot scenes are also deleted. Any associations between deleted plot scenes and manuscript scenes are also removed.

---

## Beat

Beats are the named dramatic units within an act or sequence. A beat describes a section of the story with a specific dramatic purpose — for example "Fun and Games" or "Dark Night of the Soul". A beat may span multiple manuscript scenes.

### FEAT-0822 Add beat

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0004 - Add entity](/novel-it-docs/features/00-base-entity-features#feat-0004-add-entity) |

#### Description

In addition to the properties inherited from the base entity, beats have the following properties:

- Action overview
- Characters — freeform text prompt identifying characters needed in this beat
- Locations — freeform text prompt identifying locations needed in this beat
- Items — freeform text prompt identifying items needed in this beat

#### Note:
The characters, locations, and items fields are planning prompts only. They have no formal association with planning entities in the manuscript module.

### FEAT-0823 Edit beat

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0002 - Edit entity](/novel-it-docs/features/00-base-entity-features#feat-0002-edit-entity) |

#### Description

No beat-specific extensions to the base behaviour.

### FEAT-0824 Archive beat

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0005 - Archive entity](/novel-it-docs/features/00-base-entity-features#feat-0005-archive-entity) |

#### Description

No beat-specific extensions to the base behaviour.

### FEAT-0825 Unarchive beat

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0003 - Archived entity list board](/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

#### Description

No beat-specific extensions to the base behaviour.

### FEAT-0826 Reparent beat

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0008 - Entity reparenting](/novel-it-docs/features/00-base-entity-features#feat-0008-entity-reparenting) |

#### Description

A beat may be moved to a different act or sequence within the same plot line.

### FEAT-0827 Delete beat

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0006 - Delete entity](/novel-it-docs/features/00-base-entity-features#feat-0006-delete-entity) |

#### Description

When a beat is deleted all associated plot scenes are also deleted. Any associations between deleted plot scenes and manuscript scenes are also removed.

---

## Plot Scene

Plot scenes are the leaf nodes of the plot hierarchy. They represent a discrete unit of dramatic action within a beat. A beat may contain one or more plot scenes.

Plot scenes have an optional many-to-many association with manuscript scenes. A plot scene may be associated with zero, one, or many manuscript scenes. A manuscript scene may be associated with zero, one, or many plot scenes, across any number of plot lines.

### FEAT-0828 Add plot scene

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0004 - Add entity](/novel-it-docs/features/00-base-entity-features#feat-0004-add-entity) |

#### Description

No plot scene-specific extensions to the base behaviour.

### FEAT-0829 Edit plot scene

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0002 - Edit entity](/novel-it-docs/features/00-base-entity-features#feat-0002-edit-entity) |

#### Description

No plot scene-specific extensions to the base behaviour.

### FEAT-0830 Archive plot scene

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0005 - Archive entity](/novel-it-docs/features/00-base-entity-features#feat-0005-archive-entity) |

#### Description

No plot scene-specific extensions to the base behaviour.

### FEAT-0831 Unarchive plot scene

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0003 - Archived entity list board](/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

#### Description

No plot scene-specific extensions to the base behaviour.

### FEAT-0832 Reparent plot scene

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0008 - Entity reparenting](/novel-it-docs/features/00-base-entity-features#feat-0008-entity-reparenting) |

#### Description

A plot scene may be moved to a different beat within the same plot line. All associations with manuscript scenes are preserved.

### FEAT-0833 Delete plot scene

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0006 - Delete entity](/novel-it-docs/features/00-base-entity-features#feat-0006-delete-entity) |

#### Description

When a plot scene is deleted any associations with manuscript scenes are also removed.

---

## Manuscript Association

The manuscript association features define how plot scenes connect to the manuscript. Associations are optional and many-to-many — a plot scene may be linked to any number of manuscript scenes, and a manuscript scene may be linked to plot scenes from any number of plot lines. This flexibility supports both detailed plotters and pantsers who wish to map their plot retrospectively.

### FEAT-0834 Associate plot scene with manuscript scene

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

#### Description

The user shall be able to associate a plot scene with one or more manuscript scenes.

- From the plot scene details page the user shall be able to search for and select manuscript scenes to associate with the plot scene
- The association is optional — a plot scene may exist with no manuscript scene associations
- A plot scene may be associated with manuscript scenes from any chapter within the novel
- The user shall be able to remove an association between a plot scene and a manuscript scene without deleting either entity

### FEAT-0835 Plot scene sidebar in editor

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

#### Description

When writing a manuscript scene in the editor, any plot scenes associated with that manuscript scene shall be displayed as cards in the right-hand sidebar.

- Each card shall display the plot scene name, its parent beat name, and its parent plot name
- The cards provide the author with dramatic context without leaving the writing interface
- If the manuscript scene has no plot scene associations the sidebar shall display no plot cards

### FEAT-0836 Plot coverage reporting

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

#### Description

The system shall provide reporting to identify gaps between the plot and the manuscript.

- **Unwritten plot scenes** — plot scenes that have no associated manuscript scenes, indicating planned story content that has not yet been written
- **Unplotted manuscript scenes** — manuscript scenes that have no associated plot scenes across any plot line, indicating written content that falls outside the current plot structure

Reports shall be available from the plot list board and shall be filterable by plot line.
