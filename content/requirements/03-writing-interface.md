---
title: "03 Writing Interface"
description: "Requirements for the markdown editor and writing features"
draft: false
revision: "2.0"
revision_date: "20-Apr-2026"
---

## R-FUNC-0301.01 Markdown editor element support

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0301](/novel-it-docs/features/03-writing-interface/#feat-0301-editor) |

### Statement

The editor SHALL support the following markdown elements: headings H1 to H6, bold, italic, strikethrough, blockquotes, unordered lists, ordered lists, horizontal rules, links, image links, and inline and fenced code blocks.

### Rationale

Authors writing in markdown need access to standard formatting elements to structure and style their prose. The listed elements cover the full range of common narrative formatting requirements.

### Acceptance Criteria

```gherkin
@T-FUNC-0301.01.01
Scenario: Editor renders heading elements
  Given I am in the scene editor
  When I enter markdown heading syntax from H1 to H6
  Then each heading is rendered at the correct level in preview mode

@T-FUNC-0301.01.02
Scenario: Editor renders typography elements
  Given I am in the scene editor
  When I enter bold, italic, and strikethrough markdown syntax
  Then each element is rendered correctly in preview mode

@T-FUNC-0301.01.03
Scenario: Editor renders list elements
  Given I am in the scene editor
  When I enter unordered and ordered list markdown syntax
  Then each list is rendered correctly in preview mode

@T-FUNC-0301.01.04
Scenario: Editor renders remaining supported elements
  Given I am in the scene editor
  When I enter blockquote, horizontal rule, link, image link, and code block markdown syntax
  Then each element is rendered correctly in preview mode
```

### Verification Method

Manual Test

## R-UI-0301.01 Editor toolbar provides shortcuts for common elements

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0301](/features/03-writing-interface/#feat-0301-editor) |

### Statement

The editor toolbar SHALL provide shortcut buttons for H1, H2, and H3 headings. Headings H4 to H6 SHALL be available via direct markdown input only.

### Rationale

H1 to H3 are the headings most commonly needed during prose writing. Providing toolbar shortcuts for these reduces friction. H4–H6 are available for completeness but are rarely needed in narrative writing and do not warrant toolbar space.

### Acceptance Criteria

```gherkin
@T-UI-0301.01.01
Scenario: Toolbar provides H1, H2, and H3 shortcut buttons
  Given I am in the scene editor
  Then the toolbar displays shortcut buttons for H1, H2, and H3

@T-UI-0301.01.02
Scenario: H4 to H6 are not available as toolbar shortcuts
  Given I am in the scene editor
  Then the toolbar does not display shortcut buttons for H4, H5, or H6
```

### Verification Method

Manual Test

> **Note:** Tables are not fully supported in preview mode.

## R-FUNC-0302.01 Editor autosaves content automatically

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0302](/novel-it-docs/features/03-writing-interface/#feat-0302-autosave) |

### Statement

The editor SHALL automatically save scene content at a regular interval when changes have been made since the last save.

### Rationale

Autosave protects the author's work against accidental data loss from browser crashes, connectivity issues, or inadvertent navigation away from the editor.

### Acceptance Criteria

```gherkin
@T-FUNC-0302.01.01
Scenario: Editor autosaves after changes are made
  Given I am in the scene editor
  And I have made changes to the scene content
  When the autosave interval elapses
  Then the changes are saved automatically
  And I see an indication that the content has been saved

@T-FUNC-0302.01.02
Scenario: Editor does not autosave when no changes have been made
  Given I am in the scene editor
  And I have not made any changes since the last save
  When the autosave interval elapses
  Then no save operation is performed
```

### Verification Method

Manual Test

## R-PERF-0302.01 Default autosave interval is 30 seconds

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0302](/features/03-writing-interface/#feat-0302-autosave) |

### Statement

The default autosave interval SHALL be 30 seconds.

### Rationale

30 seconds balances protection against data loss with the overhead of frequent save operations. It is short enough that an author is unlikely to lose more than a few sentences if something goes wrong.

### Acceptance Criteria

```gherkin
@T-PERF-0302.01.01
Scenario: Default autosave interval is 30 seconds
  Given I am in the scene editor with default settings
  And I have made changes to the scene content
  When 30 seconds have elapsed since the last save
  Then the content is saved automatically
```

### Verification Method

Manual Test

## R-USER-0303.01 Unsaved changes trigger a confirmation dialog on in-application navigation

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0303](/novel-it-docs/features/03-writing-interface/#feat-0303-lossless-navigation) |

### Statement

When the user attempts to navigate away from the editor using in-application navigation and there are unsaved changes, the system SHALL display a confirmation dialog offering the option to continue navigation or cancel and return to the editor.

### Rationale

Unsaved changes could be lost if the user navigates away unintentionally. A confirmation dialog gives the author the opportunity to reconsider before any content is lost.

### Acceptance Criteria

```gherkin
@T-USER-0303.01.01
Scenario: Confirmation dialog is shown when navigating away with unsaved changes
  Given I am in the scene editor
  And I have made changes that have not been saved
  When I click an in-application navigation element such as a link, breadcrumb, or previous/next scene button
  Then a confirmation dialog is displayed
  And I am offered the option to continue navigation or cancel

@T-USER-0303.01.02
Scenario: Navigation proceeds when the user confirms
  Given a confirmation dialog is displayed due to unsaved changes
  When I click the Continue button
  Then navigation proceeds
  And I am taken to the destination page

@T-USER-0303.01.03
Scenario: Navigation is cancelled when the user declines
  Given a confirmation dialog is displayed due to unsaved changes
  When I click the Cancel button
  Then navigation is cancelled
  And I remain in the scene editor with my changes intact

@T-USER-0303.01.04
Scenario: No confirmation dialog when there are no unsaved changes
  Given I am in the scene editor
  And there are no unsaved changes
  When I click an in-application navigation element
  Then navigation proceeds immediately without a confirmation dialog
```

### Verification Method

Manual Test

> **Note:** Browser-level navigation such as the back button or closing the tab is outside the application's control. In these cases the browser's own native dialog will be displayed.

## R-FUNC-0304.01 Word count updates as the user types

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0304](/novel-it-docs/features/03-writing-interface/#feat-0304-word-count) |

### Statement

The editor SHALL display a running word count for the current scene that updates in real time as the user types.

### Rationale

An up-to-date word count helps the author track their progress within a scene without having to save or navigate away.

### Acceptance Criteria

```gherkin
@T-FUNC-0304.01.01
Scenario: Word count updates as text is added
  Given I am in the scene editor
  When I type additional words
  Then the displayed word count increases accordingly

@T-FUNC-0304.01.02
Scenario: Word count updates as text is deleted
  Given I am in the scene editor
  When I delete words from the scene
  Then the displayed word count decreases accordingly
```

### Verification Method

Manual Test

## R-FUNC-0304.02 Word counts roll up on save

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0304](/features/03-writing-interface/#feat-0304-word-count) |

### Statement

When a scene is saved the system SHALL update the word counts for the parent chapter, part (if applicable), and novel to reflect the current scene word count.

### Rationale

Accurate word counts at chapter, part, and novel level are needed for progress tracking and goal monitoring. These must be kept in sync with scene content whenever a save occurs.

### Acceptance Criteria

```gherkin
@T-FUNC-0304.02.01
Scenario: Chapter word count updates on scene save
  Given I have a scene in a chapter
  And I have added words to the scene
  When the scene is saved
  Then the chapter word count reflects the updated scene word count

@T-FUNC-0304.02.02
Scenario: Novel word count updates on scene save
  Given I have a scene in a novel
  And I have added words to the scene
  When the scene is saved
  Then the novel word count reflects the updated scene word count

@T-FUNC-0304.02.03
Scenario: Part word count updates on scene save when parts are enabled
  Given I have a scene in a chapter that belongs to a part
  And I have added words to the scene
  When the scene is saved
  Then the part word count reflects the updated scene word count
```

### Verification Method

Manual Test

## R-FUNC-0304.03 Word counts update when a manuscript entity is archived

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0304](/features/03-writing-interface/#feat-0304-word-count) |

### Statement

When a scene, chapter, or part is archived the system SHALL subtract its word count contribution from all ancestor totals. Archived entities SHALL NOT contribute to word counts at any level.

### Rationale

An archived entity is removed from the active manuscript. Including its word count in parent totals would give the author a misleading picture of how much active content exists.

### Acceptance Criteria

```gherkin
@T-FUNC-0304.03.01
Scenario: Archiving a scene reduces the parent chapter word count
  Given I have a chapter containing two scenes each with a word count greater than zero
  When I archive one of the scenes
  Then the chapter word count decreases by the archived scene's word count

@T-FUNC-0304.03.02
Scenario: Archiving a scene reduces the novel word count
  Given I have a novel containing a scene with a word count greater than zero
  When I archive the scene
  Then the novel word count decreases by the archived scene's word count

@T-FUNC-0304.03.03
Scenario: Archiving a scene reduces the part word count when parts are enabled
  Given I have a novel with parts enabled containing a scene with a word count greater than zero
  When I archive the scene
  Then the part word count decreases by the archived scene's word count

@T-FUNC-0304.03.04
Scenario: Archiving a chapter reduces the novel word count
  Given I have a novel containing a chapter with a word count greater than zero
  When I archive the chapter
  Then the novel word count decreases by the archived chapter's word count

@T-FUNC-0304.03.05
Scenario: Archiving a chapter reduces the part word count when parts are enabled
  Given I have a novel with parts enabled containing a chapter with a word count greater than zero
  When I archive the chapter
  Then the part word count decreases by the archived chapter's word count

@T-FUNC-0304.03.06
Scenario: Archiving a part reduces the novel word count
  Given I have a novel with parts enabled containing a part with a word count greater than zero
  When I archive the part
  Then the novel word count decreases by the archived part's word count
```

### Verification Method

Manual Test

## R-FUNC-0304.04 Word counts update when a manuscript entity is unarchived

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0304](/features/03-writing-interface/#feat-0304-word-count) |

### Statement

When a scene, chapter, or part is unarchived the system SHALL add its word count contribution back to all ancestor totals.

### Rationale

Unarchiving restores an entity to the active manuscript. Its content must be reflected in parent word count totals to give the author an accurate picture of the active manuscript size.

### Acceptance Criteria

```gherkin
@T-FUNC-0304.04.01
Scenario: Unarchiving a scene increases the parent chapter word count
  Given I have an archived scene with a word count greater than zero
  When I unarchive the scene
  Then the chapter word count increases by the unarchived scene's word count

@T-FUNC-0304.04.02
Scenario: Unarchiving a scene increases the novel word count
  Given I have an archived scene with a word count greater than zero
  When I unarchive the scene
  Then the novel word count increases by the unarchived scene's word count

@T-FUNC-0304.04.03
Scenario: Unarchiving a scene increases the part word count when parts are enabled
  Given I have a novel with parts enabled containing an archived scene with a word count greater than zero
  When I unarchive the scene
  Then the part word count increases by the unarchived scene's word count

@T-FUNC-0304.04.04
Scenario: Unarchiving a chapter increases the novel word count
  Given I have an archived chapter with a word count greater than zero
  When I unarchive the chapter
  Then the novel word count increases by the unarchived chapter's word count

@T-FUNC-0304.04.05
Scenario: Unarchiving a chapter increases the part word count when parts are enabled
  Given I have a novel with parts enabled containing an archived chapter with a word count greater than zero
  When I unarchive the chapter
  Then the part word count increases by the unarchived chapter's word count

@T-FUNC-0304.04.06
Scenario: Unarchiving a part increases the novel word count
  Given I have a novel with parts enabled containing an archived part with a word count greater than zero
  When I unarchive the part
  Then the novel word count increases by the unarchived part's word count
```

### Verification Method

Manual Test

## R-FUNC-0304.05 Word counts update when a manuscript entity is deleted

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0304](/features/03-writing-interface/#feat-0304-word-count) |

### Statement

When a scene, chapter, or part is deleted the system SHALL subtract its word count contribution from all ancestor totals.

### Rationale

Deleting an entity permanently removes its content from the manuscript. Its word count must be removed from parent totals to keep them accurate.

### Acceptance Criteria

```gherkin
@T-FUNC-0304.05.01
Scenario: Deleting a scene reduces the parent chapter word count
  Given I have a chapter containing a scene with a word count greater than zero
  When I delete the scene
  Then the chapter word count decreases by the deleted scene's word count

@T-FUNC-0304.05.02
Scenario: Deleting a scene reduces the novel word count
  Given I have a novel containing a scene with a word count greater than zero
  When I delete the scene
  Then the novel word count decreases by the deleted scene's word count

@T-FUNC-0304.05.03
Scenario: Deleting a scene reduces the part word count when parts are enabled
  Given I have a novel with parts enabled containing a scene with a word count greater than zero
  When I delete the scene
  Then the part word count decreases by the deleted scene's word count

@T-FUNC-0304.05.04
Scenario: Deleting a chapter reduces the novel word count
  Given I have a novel containing a chapter with a word count greater than zero
  When I delete the chapter
  Then the novel word count decreases by the deleted chapter's word count

@T-FUNC-0304.05.05
Scenario: Deleting a chapter reduces the part word count when parts are enabled
  Given I have a novel with parts enabled containing a chapter with a word count greater than zero
  When I delete the chapter
  Then the part word count decreases by the deleted chapter's word count

@T-FUNC-0304.05.06
Scenario: Deleting a part reduces the novel word count
  Given I have a novel with parts enabled containing a part with a word count greater than zero
  When I delete the part
  Then the novel word count decreases by the deleted part's word count
```

### Verification Method

Manual Test

## R-FUNC-0305.01 Toggle between edit and preview mode

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0305](/novel-it-docs/features/03-writing-interface/#feat-0305-preview-mode) |

### Statement

The editor SHALL allow the user to toggle between edit mode and preview mode.

### Rationale

Preview mode allows the author to review their writing as it will appear in an exported document without leaving the editor.

### Acceptance Criteria

```gherkin
@T-FUNC-0305.01.01
Scenario: Switch from edit mode to preview mode
  Given I am in the scene editor in edit mode
  When I click the preview toggle
  Then the editor switches to preview mode
  And the markdown is rendered as formatted text
  And the raw markdown syntax is not visible

@T-FUNC-0305.01.02
Scenario: Switch from preview mode back to edit mode
  Given I am in the scene editor in preview mode
  When I click the preview toggle
  Then the editor switches back to edit mode
  And the raw markdown is editable again
```

### Verification Method

Manual Test

## R-FUNC-0306.01 Distraction free mode

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0306](/novel-it-docs/features/03-writing-interface/#feat-0306-distraction-free-mode) |

### Statement

The editor SHALL provide a distraction free mode in which all interface elements other than the editor itself are hidden from view.

### Rationale

Some authors find that navigation bars, sidebars, and other interface chrome reduce their ability to focus on writing. Distraction free mode removes these elements to provide a clean writing environment.

### Acceptance Criteria

```gherkin
@T-FUNC-0306.01.01
Scenario: Enter distraction free mode
  Given I am in the scene editor
  When I activate distraction free mode
  Then all interface elements other than the editor are hidden
  And only the editor is displayed

@T-FUNC-0306.01.02
Scenario: Exit distraction free mode
  Given I am in distraction free mode
  When I deactivate distraction free mode
  Then the full interface is restored
```

### Verification Method

Manual Test

> **Note:** Distraction free mode is displayed within the browser viewport and is not true fullscreen.

## R-FUNC-0307.01 Automatic cross-referencing on save

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0307](/novel-it-docs/features/03-writing-interface/#feat-0307-automatic-cross-referencing) |

### Statement

When a scene is saved the system SHALL scan the scene content for the names of characters, locations, and items belonging to the current novel and SHALL record each occurrence against the matching entity.

### Rationale

Automatic cross-referencing allows the author to see at a glance which scenes a character, location, or item appears in, without having to tag occurrences manually. This is only useful if it is kept current, which requires it to run on every save.

### Acceptance Criteria

```gherkin
@T-FUNC-0307.01.01
Scenario: Character name occurrence is recorded on scene save
  Given I have a novel with a character named "Elara"
  And I have written a scene that mentions "Elara" by name
  When the scene is saved
  Then the scene is listed under Elara's appearances

@T-FUNC-0307.01.02
Scenario: Location name occurrence is recorded on scene save
  Given I have a novel with a location named "The Crossroads Inn"
  And I have written a scene that mentions "The Crossroads Inn" by name
  When the scene is saved
  Then the scene is listed under The Crossroads Inn's appearances

@T-FUNC-0307.01.03
Scenario: Item name occurrence is recorded on scene save
  Given I have a novel with an item named "the silver compass"
  And I have written a scene that mentions "the silver compass" by name
  When the scene is saved
  Then the scene is listed under the silver compass's appearances

@T-FUNC-0307.01.04
Scenario: No occurrence recorded when name is not present in scene
  Given I have a novel with a character named "Marcus"
  And I have written a scene that does not mention "Marcus"
  When the scene is saved
  Then the scene is not listed under Marcus's appearances
```

### Verification Method

Manual Test
