---
title: "05 Location Management"
description: "Location database and tracking"
draft: false
---

## FEAT-0501 Location list board

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0001 - Entity list board](/features/00-base-entity-features#feat-0001-entity-list-board) |

### Description

The location list board displays all locations belonging to the current novel. As locations have no subordinate entities of their own, the board displays location cards only, with no parent summary section.

## FEAT-0502 Add location

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0004 - Add entity](/features/00-base-entity-features#feat-0004-add-entity) |

### Description

In addition to the properties inherited from the base entity, locations have the following properties:

- Location name (overrides base entity Name)
- Location type

## FEAT-0503 Edit location

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0002 - Edit entity](/features/00-base-entity-features#feat-0002-edit-entity) |

### Description

The following properties are read-only in edit mode:

- Appears in scenes (calculated — populated by [FEAT-0307 Automatic cross referencing](/features/03-writing-interface#feat-0307-automatic-cross-referencing))

## FEAT-0504 Archive location

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0005 - Archive entity](/features/00-base-entity-features#feat-0005-archive-entity) |

### Description

No location-specific extensions to the base behaviour.

## FEAT-0505 Unarchive location

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0003 - Archived entity list board](/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

### Description

No location-specific extensions to the base behaviour.

## FEAT-0506 Delete location

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0006 - Delete entity](/features/00-base-entity-features#feat-0006-delete-entity) |

### Description

When a location is deleted, any manuscript text that refers to the location by name remains unchanged.

## FEAT-0507 Duplicate location

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0007 - Duplicate entity](/features/00-base-entity-features#feat-0007-duplicate-entity) |

### Description

No location-specific extensions to the base behaviour.

## FEAT-0508 Location relocation

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0011 - Cross-novel relocation](/features/00-base-entity-features#feat-0011-cross-novel-relocation) |

### Description

No location-specific extensions to the base behaviour.

## FEAT-0509 Location sharing

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0009 - Entity sharing](/features/00-base-entity-features#feat-0009-entity-sharing) |

### Description

No location-specific extensions to the base behaviour.

## FEAT-0510 Location relationships

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0010 - Entity relationships](/features/00-base-entity-features#feat-0010-entity-relationships) |

### Description

No location-specific extensions to the base behaviour.
