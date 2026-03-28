---
title: "07 World Building Management"
description: "World building database and notes"
draft: false
---

The world building feature forms an addon function to locations and items. Not every genre of novel will require it.

## FEAT-0701 World building list board

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0001 - Entity list board](/features/00-base-entity-features#feat-0001-entity-list-board) |

### Description

The world building list board displays all world building items belonging to the current novel. As world building items have no subordinate entities of their own, the board displays world building item cards only, with no parent summary section.

## FEAT-0702 Add world building item

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0004 - Add entity](/features/00-base-entity-features#feat-0004-add-entity) |

### Description

In addition to the properties inherited from the base entity, world building items have the following properties:

- Type (e.g. Religion, Culture, Technology Level, Rules and Laws, Historical Timeline)

## FEAT-0703 Edit world building item

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0002 - Edit entity](/features/00-base-entity-features#feat-0002-edit-entity) |

### Description

The following properties are read-only in edit mode:

- Appears in scenes (calculated — populated by [FEAT-0307 Automatic cross referencing](/features/03-writing-interface#feat-0307-automatic-cross-referencing))

## FEAT-0704 Archive world building item

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0005 - Archive entity](/features/00-base-entity-features#feat-0005-archive-entity) |

### Description

No world building-specific extensions to the base behaviour.

## FEAT-0705 Unarchive world building item

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0003 - Archived entity list board](/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

### Description

No world building-specific extensions to the base behaviour.

## FEAT-0706 Delete world building item

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0006 - Delete entity](/features/00-base-entity-features#feat-0006-delete-entity) |

### Description

When a world building item is deleted, any manuscript text that refers to it by name remains unchanged.

## FEAT-0707 Duplicate world building item

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0007 - Duplicate entity](/features/00-base-entity-features#feat-0007-duplicate-entity) |

### Description

No world building-specific extensions to the base behaviour.

## FEAT-0708 World building item relocation

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0011 - Cross-novel relocation](/features/00-base-entity-features#feat-0011-cross-novel-relocation) |

### Description

No world building-specific extensions to the base behaviour.

## FEAT-0709 World building item sharing

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0009 - Entity sharing](/features/00-base-entity-features#feat-0009-entity-sharing) |

### Description

No world building-specific extensions to the base behaviour.

## FEAT-0710 World building item relationships

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0010 - Entity relationships](/features/00-base-entity-features#feat-0010-entity-relationships) |

### Description

No world building-specific extensions to the base behaviour.
