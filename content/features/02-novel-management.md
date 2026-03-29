---
title: "02 Novel Management"
description: "Novel creation, metadata, archiving, and organisation"
draft: false
---

## FEAT-0201 Add novel

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0004 - Add entity](/features/00-base-entity-features#feat-0004-add-entity) |

### Description

Users shall be able to create any number of novels.

In addition to the properties inherited from the base entity, novels have the following properties:

- Title (overrides base entity Name)
- Subtitle
- Author name
- Genre
- Target word count
- Status - [FEAT-0229](#feat-0229-status-selection)
- Synopsis (overrides base entity Description)
- Premise (overrides base entity Notes)
- Pitch
- Parts enabled? Yes / No

## FEAT-0202 Novel structure

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

Novels shall follow this hierarchical structure:

1. Parts — these are optional. If a novel is to have more than one part then this option can be enabled when the novel is created, or at a later stage when editing the novel's details.
2. Chapters — the novel shall consist of one or more chapters. If parts are in use then chapters are parented off a part, rather than the novel.
3. Scenes — a chapter shall have one or more scenes.

## FEAT-0203 Edit novel

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0002 - Edit entity](/features/00-base-entity-features#feat-0002-edit-entity) |

### Description

The following properties are read-only in edit mode:

- Actual word count (calculated)

In addition to the functions inherited from the base entity, the novel edit page provides the following function:

- Enable / disable parts

## FEAT-0204 Archive novel

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0005 - Archive entity](/features/00-base-entity-features#feat-0005-archive-entity) |

### Description

No novel-specific extensions to the base behaviour.

## FEAT-0205 Unarchive novel

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0003 - Archived entity list board](/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

### Description

No novel-specific extensions to the base behaviour.

## FEAT-0206 Delete novel

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0006 - Delete entity](/features/00-base-entity-features#feat-0006-delete-entity) |

### Description

When a novel is deleted all associated parts, chapters, scenes, characters, locations and items are also deleted.

## FEAT-0207 Duplicate novel

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0007 - Duplicate entity](/features/00-base-entity-features#feat-0007-duplicate-entity) |

### Description

When a novel is duplicated all associated parts, chapters, scenes, characters, locations and items are also duplicated and associated with the new novel.

## FEAT-0208 Export novel

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 3 |

### Description

Novel export is fully described in [10 Export](/features/10-export). See [FEAT-1002 Export manuscript](/features/10-export#feat-1002-export-manuscript) for manuscript export and [FEAT-1001 Include in compile](/features/10-export#feat-1001-include-in-compile) for controlling which content is included.

## FEAT-0209 Novel list display

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0001 - Entity list board](/features/00-base-entity-features#feat-0001-entity-list-board) |

### Description

When the user logs into the application their novels shall be displayed as cards on a board.

#### Note:
The novel list display is an exception to the Entity list board. As novels have no parent entity, the parent summary section is not displayed.

## FEAT-0210 Novel structure display

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0001 - Entity list board](/features/00-base-entity-features#feat-0001-entity-list-board) |

### Description

When the user clicks on a novel title on the novel list display the view changes to the entity list board for that novel, displaying its parts or chapters.

## FEAT-0211 Add part

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0004 - Add entity](/features/00-base-entity-features#feat-0004-add-entity) |

### Description

Parts are an optional level of the novel structure. Parts can be enabled or disabled through the edit novel feature.

In addition to the properties inherited from the base entity, parts have the following properties:

- Status - [FEAT-0229](#feat-0229-status-selection)

## FEAT-0212 Edit part

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0002 - Edit entity](/features/00-base-entity-features#feat-0002-edit-entity) |

### Description

The following properties are read-only in edit mode:

- Word count (calculated)

## FEAT-0213 Archive part

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0005 - Archive entity](/features/00-base-entity-features#feat-0005-archive-entity) |

### Description

No part-specific extensions to the base behaviour.

## FEAT-0214 Unarchive part

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0003 - Archived entity list board](/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

### Description

No part-specific extensions to the base behaviour.

## FEAT-0215 Delete part

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0006 - Delete entity](/features/00-base-entity-features#feat-0006-delete-entity) |

### Description

When a part is deleted all associated chapters and scenes are also deleted.

## FEAT-0216 Part relocation

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0011 - Cross-novel relocation](/features/00-base-entity-features#feat-0011-cross-novel-relocation) |

### Description

If a part is relocated to a novel where parts are not enabled, the system shall automatically enable parts for the destination novel.

When parts are disabled on a novel, any existing child chapters are reparented directly onto the novel.

## FEAT-0217 Add chapter

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0004 - Add entity](/features/00-base-entity-features#feat-0004-add-entity) |

### Description

Chapters are parented off a novel part if parts are enabled, otherwise their parent is the novel itself.

In addition to the properties inherited from the base entity, chapters have the following properties:

- Status - [FEAT-0229](#feat-0229-status-selection)

## FEAT-0218 Edit chapter

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0002 - Edit entity](/features/00-base-entity-features#feat-0002-edit-entity) |

### Description

The following properties are read-only in edit mode:

- Word count (calculated)

## FEAT-0219 Archive chapter

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0005 - Archive entity](/features/00-base-entity-features#feat-0005-archive-entity) |

### Description

No chapter-specific extensions to the base behaviour.

## FEAT-0220 Unarchive chapter

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0003 - Archived entity list board](/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

### Description

No chapter-specific extensions to the base behaviour.

## FEAT-0221 Delete chapter

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0006 - Delete entity](/features/00-base-entity-features#feat-0006-delete-entity) |

### Description

When a chapter is deleted all associated scenes are also deleted.

## FEAT-0222 Chapter relocation

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0011 - Cross-novel relocation](/features/00-base-entity-features#feat-0011-cross-novel-relocation) |

### Description

If the destination novel has parts enabled, a destination part must be selected for the chapter.

## FEAT-0223 Add scene

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0004 - Add entity](/features/00-base-entity-features#feat-0004-add-entity) |

### Description

Scenes are the children of chapters.

In addition to the properties inherited from the base entity, scenes have the following properties:

- Status - [FEAT-0229](#feat-0229-status-selection)

## FEAT-0224 Edit scene

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0002 - Edit entity](/features/00-base-entity-features#feat-0002-edit-entity) |

### Description

The following properties are read-only in edit mode:

- Word count (calculated)

In addition to the functions inherited from the base entity, the scene edit page provides the following function:

- Write — opens the writing interface

## FEAT-0225 Archive scene

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0005 - Archive entity](/features/00-base-entity-features#feat-0005-archive-entity) |

### Description

No scene-specific extensions to the base behaviour.

## FEAT-0226 Unarchive scene

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0003 - Archived entity list board](/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

### Description

No scene-specific extensions to the base behaviour.

## FEAT-0227 Delete scene

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0006 - Delete entity](/features/00-base-entity-features#feat-0006-delete-entity) |

### Description

No scene-specific extensions to the base behaviour.

## FEAT-0228 Scene relocation

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0008 - Entity reparenting](/features/00-base-entity-features#feat-0008-entity-reparenting) |

### Description

Scene relocation is limited to moving a scene between chapters within the same novel. Cross-novel relocation is not supported for scenes.

## FEAT-0229 Status selection

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

Where indicated, manuscript entities include a Status property with the following values:

- Not started (default)
- Plotting
- First draft
- First review
- Second draft
- Second review
- Structural edit
- Final edit
- Beta reading
- Publishing
- Published
