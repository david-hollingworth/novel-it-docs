---
title: "10 Export"
description: "Export novel manuscript and planning entities to multiple formats"
draft: false
---

The export feature allows the user to export novel content to a variety of formats for sharing, printing, or use in other applications. Export is available at multiple levels of the manuscript hierarchy and for individual planning entity types. Archived content is never included in an export.

Export is delivered as a browser download. Users running Novel-It over HTTP rather than HTTPS may be prompted by their browser to approve the download before it is saved.

Email delivery of exports is not supported in this phase but is a candidate for a future phase when email integration is available.

## FEAT-1001 Include in compile

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 3 |

### Description

Before exporting, the user controls which manuscript content is included using the Include in compile feature. This is independent of the export format and applies whenever manuscript content is exported.

Each part, chapter, and scene card on its respective board shall display a checkbox labelled "Include in compile".

- By default all entities have Include in compile set to true
- Checking or unchecking the checkbox on a part or chapter cascades the change to all its child entities
- Individual child entities can be deselected independently after a cascade
- The Include in compile state is persisted and retained between sessions
- Excluded entities are visually indicated on the board so the author can see at a glance what will and will not be exported

## FEAT-1002 Export manuscript

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 3 |

### Description

Manuscript export is triggered from the board of the entity being exported. The export button appears alongside the other action buttons in the parent summary section of the board. Export is available at the following levels:

- **Novel board** — exports the entire novel (subject to Include in compile selections)
- **Part board** — exports that part and its included chapters and scenes
- **Chapter board** — exports that chapter and its included scenes

Clicking the Export button opens an export dialog. The user shall be able to select the export format from the following options:

- Plain text
- Markdown
- HTML
- PDF
- ePub

The user shall be able to confirm or cancel the export from the dialog. On confirmation the export is generated and delivered as a browser download. Only content with Include in compile set to true is included in the export. Archived parts, chapters, and scenes are never included.

## FEAT-1003 Export planning entities

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 3 |

### Description

Planning entity export is triggered from the entity list board of each planning entity type. The export button appears alongside the other action buttons on the board. Export is available for the following planning entity types:

- Characters
- Locations
- Items
- World building
- Research notes

Clicking the Export button opens an export dialog. The user shall be able to select the export format from the following options:

- Plain text
- Markdown
- HTML
- PDF

ePub is not available for planning entity exports. The user shall be able to confirm or cancel the export from the dialog. On confirmation the export is generated and delivered as a browser download. Archived entities are never included in the export.

## FEAT-1004 PDF and ePub formatting options

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 3 |

### Description

PDF and ePub exports support additional formatting options beyond the basic export. These options are available in the export dialog when PDF or ePub is selected as the format. The export dialog shall provide the following formatting options:

- Font family
- Font size
- Line spacing
- Page size (PDF only — e.g. A4, US Letter)
- Margins (PDF only)
- Include table of contents — Yes / No
- Front matter — title page, author name, date

#### Note:
The full set of formatting options for PDF and ePub is subject to detailed design during Phase 3. The options listed above are indicative and may be extended or revised at that stage.
