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

## FEAT-002 Novel structure

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

Novels shall follow this hierachical structure

1. Parts - these are optional. If a novel is to have more than 1 part then this option can be selected when the novel is created.
2. Chapters. The novel shall consist of one or more chapters. If parts are in use then the chapters are parented off a part, rather than a novel.
3. Scenes. A chapter shall have one or more scenes

#### Note:
Parts are a phase 4 feature. Phase 1 shall consist only of Novels, Chapters and Scenes.

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
- A dashboard of chapters showing a brief summary of the chapter's details.

## FEAT-0210 Duplicate Novel

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |

### Description

- The user shall be able to duplicate an entire novel
- When a Novel is duplicated all associated chapters, characters, locations and items are also duplicated and associated with the new novel.

## FEAT-0211 Chapter Management

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

When the novel details are displayed the user shall be able to:
- Add new chapters
- Reorder chapters on the dashboard
- Edit chapters details
- Add scenes directly to a chapter
- Display the chapter details page



