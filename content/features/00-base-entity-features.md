---
title: "00 Base Entity Features"
description: "Defines a base set of features that other features can inherit from."
draft: false
---

## Overview

The Novel-It features fall into a number of distinct sets, all having common features that behave in the same way. These feature sets are:

- Manuscript management features. Covers novels, parts, chapters and scenes.
- Element management features. Covers characters, locations, items, world-building and research
- Plot management features. Covers acts, beats and scenes

The feature definitions below are intended to be generic. Each individual feature set will define which features it inherits and how it extends the base feature.

## FEAT-0001 Entity list board

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

The entity board is the primary navigation view for an entity and its children. It consists of two sections:

#### Parent summary section (top)
The top section displays a summary of the parent entity and provides action buttons for operating on the parent. The following actions shall be available:

- Edit Details
- Archive
- Delete
- Add [child entity]
- Archived [child entities]

#### Child entity board (below)
Below the parent summary, the children of the parent entity are displayed as cards. Each card shall display the child entity's name. Additional card content is defined in each concrete entity specification.

Child entity cards can be dragged on the board to reorder them.

## FEAT-0002 Edit entity

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

- The Edit Entity page shall allow the user to edit all properties of the entity
- The following properties are read-only in edit mode:
  - Date and time created
- Every entity edit page shall support these functions:
  - Save Changes
  - Cancel

## FEAT-0003 Archived entity list board

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

- Archived entities shall be displayed as cards on a "board"
- Each card shall display the entity's name property
- Each card shall have an Unarchive button
- Clicking Unarchive shall display a warning that the entity will be unarchived
- Clicking the continue button will unarchive the entity
- Clicking the cancel button shall return the user to the archived entities board

#### Note:

This board is filtered to show only entities with the "archived" property set to true

## FEAT-0004 Add entity

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

- Clicking the Add entity button opens an empty entity details page to allow the user to create a new entity
- Every entity shall have the following properties:
  - Name
  - Description
  - Notes
- The following properties are set automatically by the system and are not user-editable:
  - Date and time created
  - Date and time last modified
- The Add Entity page supports the following functions:
  - Save new Entity
  - Cancel

## FEAT-0005 Archive entity

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

- Clicking Archive entity displays a warning that the entity will be archived
- Clicking the continue button archives the entity
- Clicking the cancel button returns the user to the previous board

## FEAT-0006 Delete entity

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

- Clicking Delete entity displays a warning that the entity will be permanently deleted
- Clicking the continue button deletes the entity and all its child entities
- Clicking the cancel button returns the user to the previous board

## FEAT-0007 Duplicate entity

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 2 |

### Description

- Clicking on the Duplicate button creates a copy of the entity
- The user is prompted that they are making a copy of the entity and asked if they want to proceed.
- The user is warned that any unsaved changes in the entity will be lost when the duplicate is made
- The new duplicate entity is displayed for editing.

## FEAT-0008 Entity relocation

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |

### Description

- With the exception of novel entities, all other entities can be moved to a different novel.
- All child entities are moved along with the entity being relocated
- The user is asked to confirm the relocation

## FEAT-0009 Entity sharing

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |

### Description

An entity can be shared across more than one novel. Sharing differs from relocation in that the entity remains associated with the original novel and is also visible in the additional novels.

- The user can add additional novels to the entity's sharing list from the entity details page
- Edits to a shared entity are reflected in all novels where it appears
- Archiving a shared entity archives it across all associated novels
- Deleting a shared entity deletes it across all associated novels

## FEAT-0010 Entity relationships

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

The user shall be able to define named relationships between any two planning entities (characters, locations, and items) within a novel.

- Each relationship has a forward label and a reverse label (e.g. "owns" / "owned by")
- Relationship types are user-definable and scoped to the novel
- The user can add notes to a relationship to provide additional context
- Relationships are displayed on the details page of both participating entities
- The user can add, edit, and delete relationships from either entity's details page
- Deleting an entity also deletes all relationships in which it participates
