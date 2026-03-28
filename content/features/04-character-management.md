---
title: "04 Character Management"
description: "Character profiles, relationships, and scene appearances"
draft: false
---

## FEAT-0401 Character list board

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0001 - Entity list board](/features/00-base-entity-features#feat-0001-entity-list-board) |

### Description

The character list board displays all characters belonging to the current novel. As characters have no subordinate entities of their own, the board displays character cards only, with no parent summary section.

## FEAT-0402 Edit character

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0002 - Edit entity](/features/00-base-entity-features#feat-0002-edit-entity) |

### Description

The following properties are read-only in edit mode:

- Appears in scenes (calculated — populated by [FEAT-0307 Automatic cross referencing](/features/03-writing-interface#feat-0307-automatic-cross-referencing))

## FEAT-0403 Add character

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0004 - Add entity](/features/00-base-entity-features#feat-0004-add-entity) |

### Description

In addition to the properties inherited from the base entity, characters have the following properties:

- Full name (overrides base entity Name)
- First name
- Middle name
- Last name
- Nickname
- Aliases
- Gender
- Age
- Role in story
- Physical description
- Interview
- The lie they believe
- Goals / motivations
- Fears / weaknesses
- Arc in story
- Character image

## FEAT-0404 Archive character

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0005 - Archive entity](/features/00-base-entity-features#feat-0005-archive-entity) |

### Description

No character-specific extensions to the base behaviour.

## FEAT-0405 Unarchive character

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0003 - Archived entity list board](/features/00-base-entity-features#feat-0003-archived-entity-list-board) |

### Description

No character-specific extensions to the base behaviour.

## FEAT-0406 Delete character

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0006 - Delete entity](/features/00-base-entity-features#feat-0006-delete-entity) |

### Description

When a character is deleted, any manuscript text that refers to the character by name remains unchanged.

## FEAT-0407 Duplicate character

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |
| **Extends** | [FEAT-0007 - Duplicate entity](/features/00-base-entity-features#feat-0007-duplicate-entity) |

### Description

No character-specific extensions to the base behaviour.

## FEAT-0408 Character relocation

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0011 - Cross-novel relocation](/features/00-base-entity-features#feat-0011-cross-novel-relocation) |

### Description

No character-specific extensions to the base behaviour.

## FEAT-0409 Character sharing

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |
| **Extends** | [FEAT-0009 - Entity sharing](/features/00-base-entity-features#feat-0009-entity-sharing) |

### Description

No character-specific extensions to the base behaviour.

## FEAT-0410 Character relationships

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |
| **Extends** | [FEAT-0010 - Entity relationships](/features/00-base-entity-features#feat-0010-entity-relationships) |

### Description

No character-specific extensions to the base behaviour.
