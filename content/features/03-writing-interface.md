---
title: "03 Writing Interface"
description: "Editor features"
draft: false
revision: "1.0"
revision_date: "20-Apr-2026"
---

## FEAT-0301 Editor

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

Novel-It shall provide the user with a markdown editor that supports the following markdown elements:

- Headings H1 to H6 (toolbar shortcuts provided for H1–H3; H4–H6 available via direct markdown input)
- Typography. E.g. Bold, italic, srikethrough
- Blockquotes
- Unordered (bullet point) lists
- Ordered (numbered) lists
- Horizontal rule
- Links
- Image links
- Code blocks (inline and fenced)

####  Note:
Tables are not fully supported by the preview mode

## FEAT-0302 Autosave

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

The editor shall automatically save the content if the text has been updaated. The default is every 30 seconds, which can be overridden in the user's profile.

## FEAT-0303 Lossless navigation

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

If there are unsaved changes and the user attempts to navigate away from the editor using in-application navigation (links, breadcrumbs, previous/next scene buttons), the system shall display an in-application confirmation dialog giving the user the option to continue or cancel the navigation.

#### Note:

Browser-level navigation (back button, closing the tab) is outside the application's control. The browser's own native dialog will be displayed in these cases.

## FEAT-0304 Word count

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

- The system shall keep a count of the number of words in the scene. 
- The word count for the scene is updated as the user types.
- Word counts are rolled up to chapter, part and novel levels when the scene is saaved.

## FEAT-0305 Preview mode

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

The user shall be able to toggle between edit mode and preview mode. In preview mode the markdown is renderd as it would appear in an exported document.

## FEAT-0306 Distraction free mode

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

The editor shall provide a distraction free mode in which only the editor is displayed.

#### Note:
The editor is still displayed within the browser viewport and so is not truely fullscreen. 

## FEAT-0307 Automatic cross referencing

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

When a scene is saved the application will automatically search for characters, locations and items mentioned by name in that scene and will records their occurance against the appropriate character, location or item.
