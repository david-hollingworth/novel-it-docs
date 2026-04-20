---
title: "06 Item Management"
description: "Item database and tracking"
draft: false
revision: "1.0"
revision_date: "20-Apr-2026"
---

## FEAT-0601 Item list board

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0001 - Entity list board](/novel-it-docs/features/00-base-entity-features#feat-0001-entity-list-board) |

### Description

The item list board displays all items belonging to the current novel. As items have no subordinate entities of their own, the board displays item cards only, with no parent summary section.

## FEAT-0602 Add item

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0004 - Add entity](/novel-it-docs/features/00-base-entity-features#feat-0004-add-entity) |

### Description

In addition to the properties inherited from the base entity, items have the following properties:

- Item name (overrides base entity Name)
- Item type
- History
- Properties / abilities

## FEAT-0603 Edit item

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0002 - Edit entity](/novel-it-docs/features/00-base-entity-features#feat-0002-edit-entity) |

### Description

The following properties are read-only in edit mode:

- Appears in scenes (calculated — populated by [FEAT-0307 Automatic cross referencing](/novel-it-docs/features/03-writing-interface#feat-0307-automatic-cross-referencing))

## FEAT-0604 Archive item

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0005 - Archive entity](/novel-it-docs/features/00-base-entity-features#feat-0005-archive-entity) |

### Description

No item-specific extensions to the base behaviour.

## FEAT-0605 Unarchive item

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0003 - Archived entity list board](/novel-it-docs/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

### Description

No item-specific extensions to the base behaviour.

## FEAT-0606 Delete item

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0006 - Delete entity](/novel-it-docs/features/00-base-entity-features#feat-0006-delete-entity) |

### Description

When an item is deleted, any manuscript text that refers to the item by name remains unchanged.

## FEAT-0607 Duplicate item

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0007 - Duplicate entity](/novel-it-docs/features/00-base-entity-features#feat-0007-duplicate-entity) |

### Description

No item-specific extensions to the base behaviour.

## FEAT-0608 Item relocation

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0011 - Cross-novel relocation](/novel-it-docs/features/00-base-entity-features#feat-0011-cross-novel-relocation) |

### Description

No item-specific extensions to the base behaviour.

## FEAT-0609 Item sharing

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0009 - Entity sharing](/novel-it-docs/features/00-base-entity-features#feat-0009-entity-sharing) |

### Description

No item-specific extensions to the base behaviour.

## FEAT-0610 Item relationships

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0010 - Entity relationships](/novel-it-docs/features/00-base-entity-features#feat-0010-entity-relationships) |

### Description

No item-specific extensions to the base behaviour.
