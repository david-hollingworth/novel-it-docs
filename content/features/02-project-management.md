---
title: "02 Novel Management"
description: "Novel creation, metadata, archiving, and organisation"
draft: false
---

## FEAT-0201 Create Novel

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

Users shall be able to create any number of novels.

Novels shall have the following attributes:

- Title
- Sub-title
- Log-line
- Synopsis
- Premise
- Genre
- Status - one of:
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
- Parts required? Yes / No

## FEAT-002 Novel structure

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

Novels shall follow this hierachical structure

1. Parts - these are optional. If a novel is to have more than 1 part then this option can be enabled when the novel is created, or at a later stage when editing the novel's details.
2. Chapters. The novel shall consist of one or more chapters. If parts are in use then the chapters are parented off a part, rather than a novel.
3. Scenes. A chapter shall have one or more scenes

## FEAT-0203 Edit Novel

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

The user shall be able to edit all aspects of a novel's structure.

## FEAT-0204 Archive Novel

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

The system shall support a soft-delete feature that allows the user to archive a novel instead of deleting it. 

When a novel has been archived it is no longer displayed on the novel list page.

## FEAT-0205 Unarchive Novel

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

- The user shall be able to display the archived novels
- The user shall be able to select an archived novel and unarchive it.
- A novel that has been unarchived shall be displayed on the novel list page

## FEAT-0206 Delete Novel

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

- The user shall be able to permenantly delete an entire novel.
- When the user opts to delete a novel a warning message is displayed
- When a novel is deleted all chapters, scenes, characters, locations and items associated with that novel are deleted.

## FEAT-0207 Export Novel

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 3 |

### Description

The user shall be able to export a novel in one of the following formats:

- Markdown
- HTML
- PDF
- ePub

## FEAT-0208 Novel List Display

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

WHen the user logs into the application their novels shall be displayed as cards on a dashboard. Each card shall display:

- The novel's title
- Three lines from the novel's premise
- The number of words in the novel
- The time since the novel details were last updated.

## FEAT-0209 Novel Details Display

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

The user can open the novel's details by clicking on the novel's title on the novel card.

The novel details page shall display:

- The novel's title
- The novel's premise
- Buttons to edit the novel's details, archive the novel, add a chapter, view archived chapters.
- Chapter, scene and word counts.
- If parts are enabled then a dashboard of parts is displayed showing a brief summary of the part's details.
- If parts are disabled then dashboard of chapters showing a brief summary of the chapter's details is displayed.

## FEAT-0210 Duplicate Novel

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |

### Description

- The user shall be able to duplicate an entire novel
- When a Novel is duplicated all associated chapters, characters, locations and items are also duplicated and associated with the new novel.

## FEAT-0211 Part Management

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

Parts are an optional top level of the organizational hierachy within the novel.

When the novel details are displayed the user shall be able to:
- Enable parts if they are disabled
- Add new parts
- Drag and drop parts on the dashboard to reorder them
- Edit part details
- Add chapters directly to a part
- Display the part details page

#### Note: Phase 2 Features - extended part management

- If parts are enabled then the user shall be able to move parts from one novel to another.
- If a part is moved to another novel then all child chapters and scenes shall move to the new novel.

## FEAT-0212 Chapter Management

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

Chapters can be the children of a Novel, if parts are disabled. However, if paarts are enabled for the novel then chapters are the children of a part.

When the novel details are displayed (or part details, if parts are enabled) the user shall be able to:
- Add new chapters
- Drag and drop chapters on the dashboard to reorder them
- Edit chapters details
- Add scenes directly to a chapter
- Display the chapter details page

#### Note: Phase 2 Features - extended chapter management

- Chapters can be moved from one novel to another
- If the destination novel has parts enabled then the a destination part must be selected for the chapter
- When a chapter is moved to a new novel or part, then any child scenes are moved along with the chapter;

## FEAT-0213 Scene Management

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

When The chapter details are displayed the user shall be able to:
- Edit the chapter details
- Delete a chapter. Any scenes attached to the chapter are also deleted.
- Archive a chapter. Archived chapters no longer appear as part of the novel
- Unarchive a chapter
- Add new scenes
- Drag and drop scenes on the dashboard to reorder them
- Edit scene details
- Delete a scene
- Archive a scene
- Unarchive a scene
- Set the scene's status
- Move scenes between chapters
- Click on a scene's title to open the editor

