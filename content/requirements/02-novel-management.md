---
title: "02 Novel Management"
description: "Requirements for novel, part, chapter, and scene management"
draft: false
revision: "2.0"
revision_date: "20-Apr-2026"
---

*Phase 3 and 4 features (FEAT-0207 Duplicate novel, FEAT-0208 Export novel, FEAT-0216 Part relocation, FEAT-0222 Chapter relocation) are out of scope for this pass and have no requirements entries here.*

## R-FUNC-0201.01 Create a novel

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0201](/novel-it-docs/features/02-novel-management/#feat-0201-add-novel) |

### Statement

The system SHALL allow the user to create a novel with the following properties: title, subtitle, author name, genre, target word count, status, synopsis, premise, pitch, and parts enabled.

### Rationale

Novel creation is the primary entry point for all writing activity. All manuscript and planning content belongs to a novel.

### Acceptance Criteria

```gherkin
@T-FUNC-0201.01.01
Scenario: Successfully create a novel
  Given I am logged in
  And I am on the novels board
  When I click the Add Novel button
  And I enter a title
  And I click the Save button
  Then the novel is created
  And it appears on my novels board

@T-FUNC-0201.01.02
Scenario: Attempt to create a novel without a title
  Given I am logged in
  And I am on the add novel page
  When I click the Save button without entering a title
  Then the novel is not created
  And I see an error message indicating that a title is required
```

### Verification Method

Manual Test

## R-UI-0201.01 Add novel form presents all required fields

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0201](/features/02-novel-management/#feat-0201-add-novel) |

### Statement

The add novel form SHALL present the following fields: title, subtitle, author name, genre, target word count, status, synopsis, premise, pitch, and parts enabled.

### Rationale

All specified novel properties must be available for input when a novel is created. Omitting a field from the form would make that property inaccessible at creation time.

### Acceptance Criteria

```gherkin
@T-UI-0201.01.01
Scenario: Add novel form presents all required fields
  Given I am logged in
  When I click the Add Novel button on the novels board
  Then the add novel form displays fields for: title, subtitle, author name, genre, target word count, status, synopsis, premise, pitch, and parts enabled
```

### Verification Method

Manual Test

## R-FUNC-0201.02 Parts enabled flag defaults to No

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0201](/features/02-novel-management/#feat-0201-add-novel) |

### Statement

The system SHALL default the parts enabled flag to No when a new novel is created.

### Rationale

Most novels do not use parts. Defaulting to No reduces friction for the common case while keeping the option available.

### Acceptance Criteria

```gherkin
@T-FUNC-0201.02.01
Scenario: Parts enabled defaults to No on a new novel
  Given I am on the add novel page
  Then the parts enabled field displays No by default
```

### Verification Method

Manual Test

## R-UI-0203.01 Edit novel form presents all required fields

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0203](/novel-it-docs/features/02-novel-management/#feat-0203-edit-novel) |

### Statement

The edit novel form SHALL present the following editable fields: title, subtitle, author name, genre, target word count, status, synopsis, premise, pitch, and parts enabled. The actual word count SHALL be displayed as a read-only field.

### Rationale

All specified novel properties must be available for editing. The actual word count must be visible but protected from direct editing as it is a calculated value.

### Acceptance Criteria

```gherkin
@T-UI-0203.01.01
Scenario: Edit novel form presents all editable fields
  Given I have an existing novel
  When I navigate to the edit novel page
  Then the form displays editable fields for: title, subtitle, author name, genre, target word count, status, synopsis, premise, pitch, and parts enabled

@T-UI-0203.01.02
Scenario: Edit novel form displays actual word count as read-only
  Given I have an existing novel
  When I navigate to the edit novel page
  Then the actual word count is displayed
  And it is not editable
```

### Verification Method

Manual Test

## R-FUNC-0202.01 Novel hierarchy — parts disabled

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0202](/novel-it-docs/features/02-novel-management/#feat-0202-novel-structure) |

### Statement

When parts are disabled, the system SHALL organise the novel as a two-level hierarchy of chapters containing scenes, with chapters parented directly off the novel.

### Rationale

The chapter-scene structure is the minimum viable hierarchy for writing. It must be available without requiring parts to be enabled.

### Acceptance Criteria

```gherkin
@T-FUNC-0202.01.01
Scenario: Novel structure without parts
  Given I have a novel with parts disabled
  When I view the novel structure display
  Then I see chapters listed directly under the novel
  And I do not see a parts level in the hierarchy
```

### Verification Method

Manual Test

## R-FUNC-0202.02 Novel hierarchy — parts enabled

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0202](/features/02-novel-management/#feat-0202-novel-structure) |

### Statement

When parts are enabled, the system SHALL organise the novel as a three-level hierarchy of parts containing chapters containing scenes, with chapters parented off parts rather than the novel directly. When Parts are disabled Chapters SHALL be displayed directly under the Novel structure display.

### Rationale

Multi-part novels require a structural level above chapters to organise the manuscript into distinct sections.

### Acceptance Criteria

```gherkin
@T-FUNC-0202.02.01
Scenario: Novel structure with parts
  Given I have a novel with parts enabled
  When I view the novel structure display
  Then I see parts listed under the novel
  And chapters are listed under their respective parts
  And chapters are not displayed directly under the novel
```

### Verification Method

Manual Test

## R-FUNC-0203.01 Edit novel properties

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0203](/features/02-novel-management/#feat-0203-edit-novel) |

### Statement

The system SHALL allow the user to save changes to a novel's properties and SHALL allow the user to cancel without saving, discarding any changes made.

### Rationale

Novel properties need to be updatable throughout the writing process as the author's vision develops. The cancel function protects the user from inadvertently overwriting existing values.

### Acceptance Criteria

```gherkin
@T-FUNC-0203.01.01
Scenario: Successfully edit a novel's properties
  Given I have an existing novel
  And I am on the edit novel page
  When I change the title
  And I click the Save button
  Then the novel is updated
  And the new title is displayed on the novels board

@T-FUNC-0203.01.02
Scenario: Cancel editing a novel
  Given I have an existing novel
  And I am on the edit novel page
  When I change the title
  And I click the Cancel button
  Then the novel is not updated
  And the original title is retained
```

### Verification Method

Manual Test

## R-FUNC-0203.02 Enable and disable parts

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0203](/features/02-novel-management/#feat-0203-edit-novel) |

### Statement

The system SHALL allow the user to enable or disable parts for a novel from the edit novel page.

When parts are enabled and there are existing active chapters in the novel structure then the system SHALL move those chapters to the first part in the novel structure display.

### Rationale

An author may decide to restructure their novel into parts after initial creation, or remove the parts level if it is no longer needed.

### Acceptance Criteria

```gherkin
@T-FUNC-0203.02.01
Scenario: Enable parts on an existing novel
  Given I have a novel with parts disabled
  And I am on the edit novel page
  When I enable parts
  And I click the Save button
  Then parts are enabled for the novel
  And the novel structure display shows a parts level

@T-FUNC-0203.02.02
Scenario: Disable parts on an existing novel
  Given I have a novel with parts enabled
  And I am on the edit novel page
  When I disable parts
  And I click the Save button
  Then parts are disabled for the novel
  And any existing chapters are displayed directly under the novel structure display
```

### Verification Method

Manual Test

## R-FUNC-0204.01 Archive a novel

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0204](/novel-it-docs/features/02-novel-management/#feat-0204-archive-novel) |

### Statement

The system SHALL allow the user to archive a novel, and SHALL require confirmation before doing so.

### Rationale

Archiving is a recoverable action but should not be triggered accidentally. A confirmation step protects the user from unintended archiving.

### Acceptance Criteria

```gherkin
@T-FUNC-0204.01.01
Scenario: Successfully archive a novel
  Given I have an existing novel on my novels board
  When I click the Archive button for that novel
  And I am shown a confirmation dialog
  And I click the Continue button
  Then the novel is archived
  And it no longer appears on my novels board

@T-FUNC-0204.01.02
Scenario: Cancel archiving a novel
  Given I have an existing novel on my novels board
  When I click the Archive button for that novel
  And I am shown a confirmation dialog
  And I click the Cancel button
  Then the novel is not archived
  And it remains on my novels board
```

### Verification Method

Manual Test

## R-FUNC-0205.01 Unarchive a novel

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0205](/novel-it-docs/features/02-novel-management/#feat-0205-unarchive-novel) |

### Statement

The system SHALL display archived novels on a separate archived novels board and SHALL allow the user to unarchive a novel from that board, requiring confirmation before doing so.

### Rationale

Archived novels must be recoverable. A dedicated board and confirmation step ensure the user can find and restore them without accidentally triggering the action.

### Acceptance Criteria

```gherkin
@T-FUNC-0205.01.01
Scenario: Successfully unarchive a novel
  Given I have an archived novel
  And I am on the archived novels board
  When I click the Unarchive button for that novel
  And I am shown a confirmation dialog
  And I click the Continue button
  Then the novel is unarchived
  And it appears on my novels board
  And it no longer appears on the archived novels board

@T-FUNC-0205.01.02
Scenario: Cancel unarchiving a novel
  Given I have an archived novel
  And I am on the archived novels board
  When I click the Unarchive button for that novel
  And I am shown a confirmation dialog
  And I click the Cancel button
  Then the novel is not unarchived
  And it remains on the archived novels board
```

### Verification Method

Manual Test

## R-FUNC-0206.01 Delete a novel

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0206](/novel-it-docs/features/02-novel-management/#feat-0206-delete-novel) |

### Statement

The system SHALL allow the user to permanently delete a novel and SHALL require confirmation before doing so.

### Rationale

Deletion is irreversible. A confirmation step is essential to protect the user from accidental data loss.

### Acceptance Criteria

```gherkin
@T-FUNC-0206.01.01
Scenario: Successfully delete a novel
  Given I have an existing novel
  When I click the Delete button for that novel
  And I am shown a confirmation dialog warning that the deletion is permanent
  And I click the Continue button
  Then the novel is permanently deleted
  And it no longer appears on my novels board

@T-FUNC-0206.01.02
Scenario: Cancel deleting a novel
  Given I have an existing novel
  When I click the Delete button for that novel
  And I am shown a confirmation dialog
  And I click the Cancel button
  Then the novel is not deleted
  And it remains on my novels board
```

### Verification Method

Manual Test

## R-DATA-0206.01 Novel deletion cascades to all child entities

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0206](/features/02-novel-management/#feat-0206-delete-novel) |

### Statement

When a novel is deleted the system SHALL also permanently delete all associated parts, chapters, scenes, characters, locations, and items belonging to that novel.

### Rationale

Orphaned child entities with no parent novel would be inaccessible and would consume storage indefinitely. Cascade deletion ensures the database remains consistent.

### Acceptance Criteria

```gherkin
@T-DATA-0206.01.01
Scenario: Child entities are deleted with the novel
  Given I have a novel containing parts, chapters, scenes, characters, locations, and items
  When I delete the novel
  Then all parts, chapters, scenes, characters, locations, and items belonging to that novel are also deleted
  And none of those entities are accessible in the application
```

### Verification Method

Manual Test

## R-FUNC-0209.01 Novels displayed as cards on login

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0209](/novel-it-docs/features/02-novel-management/#feat-0209-novel-list-display) |

### Statement

The system SHALL display all of the user's non-archived novels as cards on a board immediately after login.

### Rationale

The novels board is the user's home view and the starting point for all writing activity.

### Acceptance Criteria

```gherkin
@T-FUNC-0209.01.01
Scenario: Novels board displayed after login
  Given I am a registered user with two novels
  When I log in
  Then I see my two novels displayed as cards on the novels board

@T-FUNC-0209.01.02
Scenario: Archived novels do not appear on the novels board
  Given I have one active novel and one archived novel
  When I log in
  Then I see only the active novel on the novels board
  And I do not see the archived novel
```

### Verification Method

Manual Test

## R-FUNC-0210.01 Navigate to novel structure display

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0210](/novel-it-docs/features/02-novel-management/#feat-0210-novel-structure-display) |

### Statement

The system SHALL navigate the user to the novel structure display when they click on a novel card on the novels board, showing the parts or chapters belonging to that novel.

### Rationale

The novel structure display is the primary navigation view for manuscript content and the entry point for all chapter and scene management.

### Acceptance Criteria

```gherkin
@T-FUNC-0210.01.01
Scenario: Navigate into a novel without parts
  Given I have a novel with parts disabled and two chapters
  And I am on the novels board
  When I click on that novel's title
  Then I am taken to the novel structure display
  And I see the two chapters displayed

@T-FUNC-0210.01.02
Scenario: Navigate into a novel with parts
  Given I have a novel with parts enabled and two parts
  And I am on the novels board
  When I click on that novel's title
  Then I am taken to the novel structure display
  And I see the two parts displayed
```

### Verification Method

Manual Test

## R-FUNC-0211.01 Create a part

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0211](/novel-it-docs/features/02-novel-management/#feat-0211-add-part) |

### Statement

The system SHALL allow the user to create a part with the following properties: name, description, notes, and status. The Add Part action SHALL only be available when parts are enabled for the novel.

If there are Chapters present at the Novel level (from before Parts were enabled), when the Add Part dialogue is open the user shall be able to select any Chapters they want to appear under that Part. When the Part is saved those chapters will appear on the Part structure display.

### Rationale

Parts are the top-level structural division of a multi-part novel. Each part groups related chapters under a named section.

### Acceptance Criteria

```gherkin
@T-FUNC-0211.01.01
Scenario: Successfully create a part
  Given I have a novel with parts enabled
  And I am on the novel structure display
  When I click the Add Part button
  And I enter a name
  And I click the Save button
  Then the part is created
  And it appears on the novel structure display

@T-FUNC-0211.01.02
Scenario: Successfully create a part and assign existing Chapters
  Given I have a novel with parts enabled
  And I have Chapters present at the Novel level
  And I am on the novel structure display
  When I click the Add Part button
  And I enter a name
  And I select the Chapters I want attached to this Part
  And I click the Save button
  Then the part is created
  And it appears on the novel structure display
  And the Chapters are shown on the Part structure display.  

@T-FUNC-0211.01.03
Scenario: Add Part button is not available when parts are disabled
  Given I have a novel with parts disabled
  And I am on the novel structure display
  Then I do not see an Add Part button
```

### Verification Method

Manual Test

## R-UI-0211.01 Add part form presents all required fields

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0211](/features/02-novel-management/#feat-0211-add-part) |

### Statement

The add part form SHALL present the following fields: name, description, notes, and status.

### Rationale

All specified part properties must be available for input when a part is created.

### Acceptance Criteria

```gherkin
@T-UI-0211.01.01
Scenario: Add part form presents all required fields
  Given I have a novel with parts enabled
  When I click the Add Part button
  Then the add part form displays fields for: name, description, notes, and status
```

### Verification Method

Manual Test

## R-FUNC-0212.01 Edit a part

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0212](/novel-it-docs/features/02-novel-management/#feat-0212-edit-part) |

### Statement

The system SHALL allow the user to save changes to a part's properties and SHALL allow the user to cancel without saving, discarding any changes made.

### Rationale

Part properties need to be updatable as the author restructures and revises their manuscript. The cancel function protects the user from inadvertently overwriting existing values.

### Acceptance Criteria

```gherkin
@T-FUNC-0212.01.01
Scenario: Successfully edit a part
  Given I have an existing part
  And I am on the edit part page
  When I change the name
  And I click the Save button
  Then the part is updated
  And the new name is displayed on the novel structure display

@T-FUNC-0212.01.02
Scenario: Cancel editing a part
  Given I have an existing part
  And I am on the edit part page
  When I change the name
  And I click the Cancel button
  Then the part is not updated
  And the original name is retained
```

### Verification Method

Manual Test

## R-UI-0212.01 Edit part form presents all required fields

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0212](/features/02-novel-management/#feat-0212-edit-part) |

### Statement

The edit part form SHALL present the following editable fields: name, description, notes, and status. The word count SHALL be displayed as a read-only field.

### Rationale

All specified part properties must be available for editing. The word count must be visible but protected from direct editing as it is a calculated value.

### Acceptance Criteria

```gherkin
@T-UI-0212.01.01
Scenario: Edit part form presents all editable fields
  Given I have an existing part
  When I navigate to the edit part page
  Then the form displays editable fields for: name, description, notes, and status

@T-UI-0212.01.02
Scenario: Edit part form displays word count as read-only
  Given I have an existing part containing chapters with scenes
  When I navigate to the edit part page
  Then the word count is displayed
  And it is not editable
```

### Verification Method

Manual Test

## R-FUNC-0213.01 Archive a novel part

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0213](/novel-it-docs/features/02-novel-management/#feat-0213-archive-part) |

### Note:

The behvaiour of the system is slightly different depending on whether the user is archiving the final active part or whether there are more than one active part.

### Statement

The system SHALL allow the user to archive a novel part and SHALL require confirmation before doing so. 

If there are existing active chapters for the part and there is more than one active part then the user shall be prompted:

1. Move Chapters to another Part?
2. Archive the Chapters with the Part?
3. Cancel

If there are existing active chapters for the part and this is the final active part then the user shall be prompted:

1. Move Chapters to the Novel?
2. Archive the Chapters with the Part?
3. Cancel

If there are no active Chapters for this part then the user shall be prompted:

1. Continue
2. Cancel

#### Note:

Archived Chapters are ignored in all cases.

### Rationale

The user may wish to retain access to the chapters after the part has been archived, or they may wish to archive everything.

### Acceptance Criteria

```gherkin
@T-FUNC-0213.01.01
Scenario: Successfully archive a part with chapters when there are more than 1 active Parts
  Given I have more then one Part on the novel structure display
  And a Part has Chapters
  When I click the Archive button for that Part
  Then I am prompted "Move Chapters to another Part?, Archive the Chapters with the Part?, Cancel"
  
@T-FUNC-0213.01.02
Scenario: Successfully archive a Part, moving the Chapters to another Part
  Given I have more then one Part on the novel structure display
  And a Part has Chapters
  When I click the Archive button for that Part
  And I click the button to move the chapters to another part
  And I select another part to move the chapters to
  Then the part is archived and no longer appears on the novel structure display
  And the chapters are moved to the other part and are displayed on that part's structure display

@T-FUNC-0213.01.03
Scenario: Successfully archive a Part and its Chapters
  Given I have an existing part on the novel structure display
  And the Part has Chapters
  When I click the Archive button for that Part
  And I click the button to archive the Chapters with the Part
  Then the Part is archived
  And the Part no longer appears on the Novel structure display 
  And the Chapters do not appear on any part's structure display

@T-FUNC-0213.01.04
Scenario: Cancel archiving a part
  Given I have an existing part on the novel structure display
  And I have clicked the Archive button for that part
  And I am shown a confirmation dialog
  When I click the Cancel button
  Then the part is not archived
  And it remains on the novel structure display

@T-FUNC-0213.01.05
Scenario: Successfully archive a part with chapters when there is only 1 active Part
  Given I have only one Part on the novel structure display
  And the Part has Chapters
  When I click the Archive button for that Part
  Then I am prompted "Move Chapters to the Novel?, Archive the Chapters with the Part?, Cancel"

@T-FUNC-0213.01.06
Scenario: Successfully archive the final active part, moving the chapters to the novel
  Given I have only one part on the novel structure display
  And the Part has Chapters
  When I click the Archive button for that Part
  And I click the button to move the Chapters to the Novel
  Then the Part is archived
  And the Part no longer appears on the Novel structure display 
  And the Chapters are now displayed on the Novel structure display.
  And Parts Enabled is set to "No"  

@T-FUNC-0213.01.07
Scenario: Successfully archive a part that has no chapters
  Given I have an existing Part on the Novel structure display
  And the Part has no Chapters
  When I click the button to archive the Part
  Then I am prompted "Continue?, Cancel"
  And I click the Continue button
  And the Part is archived
  And the Part no longer appears on the Novel structure display 
```

### Verification Method

Manual Test

## R-FUNC-0214.01 Unarchive a part

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0214](/novel-it-docs/features/02-novel-management/#feat-0214-unarchive-part) |

### Statement

The system SHALL display archived parts on a separate archived parts board and SHALL allow the user to unarchive a part from that board, requiring confirmation before doing so.

### Rationale

Archived parts must be recoverable. A dedicated board ensures the user can find and restore them.

### Acceptance Criteria

```gherkin
@T-FUNC-0214.01.01
Scenario: Successfully unarchive a part
  Given I have an archived part
  And I am on the archived parts board for that novel
  When I click the Unarchive button for that part
  And I am shown a confirmation dialog
  And I click the Continue button
  Then the part is unarchived
  And it appears on the novel structure display
  And it no longer appears on the archived parts board

@T-FUNC-0214.01.02
Scenario: Cancel unarchiving a part
  Given I have an archived part
  And I am on the archived parts board for that novel
  When I click the Unarchive button for that part
  And I am shown a confirmation dialog
  And I click the Cancel button
  Then the part is not unarchived
  And it remains on the archived parts board
```

### Verification Method

Manual Test

## R-FUNC-0215.01 Delete a part

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0215](/novel-it-docs/features/02-novel-management/#feat-0215-delete-part) |

### Statement

The system SHALL allow the user to permanently delete a part and SHALL require confirmation before doing so.

### Rationale

Deletion is irreversible and a confirmation step protects the user from accidental data loss.

### Acceptance Criteria

```gherkin
@T-FUNC-0215.01.01
Scenario: Successfully delete a part
  Given I have an existing part
  When I click the Delete button for that part
  And I am shown a confirmation dialog warning that the deletion is permanent
  And I click the Continue button
  Then the part is permanently deleted
  And it no longer appears on the novel structure display

@T-FUNC-0215.01.02
Scenario: Cancel deleting a part
  Given I have an existing part
  When I click the Delete button for that part
  And I am shown a confirmation dialog
  And I click the Cancel button
  Then the part is not deleted
  And it remains on the novel structure display
```

### Verification Method

Manual Test

## R-DATA-0215.01 Part deletion cascades to chapters and scenes

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0215](/features/02-novel-management/#feat-0215-delete-part) |

### Statement

When a part is deleted the system SHALL also permanently delete all chapters and scenes belonging to that part.

### Rationale

Orphaned chapters and scenes with no parent part would be inaccessible. Cascade deletion ensures the database remains consistent.

### Acceptance Criteria

```gherkin
@T-DATA-0215.01.01
Scenario: Chapters and scenes are deleted with the part
  Given I have a part containing two chapters each with two scenes
  When I delete the part
  Then all chapters and scenes belonging to that part are also deleted
  And none of those entities are accessible in the application
```

### Verification Method

Manual Test

## R-FUNC-0217.01 Create a chapter

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0217](/novel-it-docs/features/02-novel-management/#feat-0217-add-chapter) |

### Statement

The system SHALL allow the user to create a chapter with the following properties: name, description, notes, and status. When parts are enabled the chapter SHALL be parented off a part; when parts are disabled the chapter SHALL be parented directly off the novel.

### Rationale

Chapters are the primary structural unit of the manuscript and the container for scenes.

### Acceptance Criteria

```gherkin
@T-FUNC-0217.01.01
Scenario: Successfully create a chapter in a novel without parts
  Given I have a novel with parts disabled
  And I am on the novel structure display
  When I click the Add Chapter button
  And I enter a name
  And I click the Save button
  Then the chapter is created
  And it appears directly under the novel on the structure display

@T-FUNC-0217.01.02
Scenario: Successfully create a chapter in a novel with parts
  Given I have a novel with parts enabled and at least one part
  And I am on the part structure display
  When I click the Add Chapter button
  And I enter a name
  And I click the Save button
  Then the chapter is created
  And it appears under the part on the structure display
```

### Verification Method

Manual Test

## R-UI-0217.01 Add chapter form presents all required fields

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0217](/features/02-novel-management/#feat-0217-add-chapter) |

### Statement

The add chapter form SHALL present the following fields: name, description, notes, and status.

### Rationale

All specified chapter properties must be available for input when a chapter is created.

### Acceptance Criteria

```gherkin
@T-UI-0217.01.01
Scenario: Add chapter form presents all required fields
  Given I have an existing novel
  When I click the Add Chapter button
  Then the add chapter form displays fields for: name, description, notes, and status
```

### Verification Method

Manual Test

## R-FUNC-0218.01 Edit a chapter

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0218](/novel-it-docs/features/02-novel-management/#feat-0218-edit-chapter) |

### Statement

The system SHALL allow the user to save changes to a chapter's properties and SHALL allow the user to cancel without saving, discarding any changes made.

### Rationale

Chapter properties need to be updatable as the author revises their manuscript structure. The cancel function protects the user from inadvertently overwriting existing values.

### Acceptance Criteria

```gherkin
@T-FUNC-0218.01.01
Scenario: Successfully edit a chapter
  Given I have an existing chapter
  And I am on the edit chapter page
  When I change the name
  And I click the Save button
  Then the chapter is updated
  And the new name is displayed on the structure display

@T-FUNC-0218.01.02
Scenario: Cancel editing a chapter
  Given I have an existing chapter
  And I am on the edit chapter page
  When I change the name
  And I click the Cancel button
  Then the chapter is not updated
  And the original name is retained
```

### Verification Method

Manual Test

## R-UI-0218.01 Edit chapter form presents all required fields

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0218](/features/02-novel-management/#feat-0218-edit-chapter) |

### Statement

The edit chapter form SHALL present the following editable fields: name, description, notes, and status. The word count SHALL be displayed as a read-only field.

### Rationale

All specified chapter properties must be available for editing. The word count must be visible but protected from direct editing as it is a calculated value.

### Acceptance Criteria

```gherkin
@T-UI-0218.01.01
Scenario: Edit chapter form presents all editable fields
  Given I have an existing chapter
  When I navigate to the edit chapter page
  Then the form displays editable fields for: name, description, notes, and status

@T-UI-0218.01.02
Scenario: Edit chapter form displays word count as read-only
  Given I have an existing chapter containing scenes with text
  When I navigate to the edit chapter page
  Then the word count is displayed
  And it is not editable
```

### Verification Method

Manual Test

## R-FUNC-0219.01 Archive a chapter

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0219](/novel-it-docs/features/02-novel-management/#feat-0219-archive-chapter) |

### Statement

The system SHALL allow the user to archive a chapter and SHALL require confirmation before doing so.

### Rationale

Archiving is a recoverable action but should not be triggered accidentally.

### Acceptance Criteria

```gherkin
@T-FUNC-0219.01.01
Scenario: Successfully archive a chapter
  Given I have an existing chapter on the structure display
  When I click the Archive button for that chapter
  And I am shown a confirmation dialog
  And I click the Continue button
  Then the chapter is archived
  And it no longer appears on the structure display

@T-FUNC-0219.01.02
Scenario: Cancel archiving a chapter
  Given I have an existing chapter on the structure display
  When I click the Archive button for that chapter
  And I am shown a confirmation dialog
  And I click the Cancel button
  Then the chapter is not archived
  And it remains on the structure display
```

### Verification Method

Manual Test

## R-FUNC-0220.01 Unarchive a chapter

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0220](/novel-it-docs/features/02-novel-management/#feat-0220-unarchive-chapter) |

### Statement

The system SHALL display archived chapters on a separate archived chapters board and SHALL allow the user to unarchive a chapter from that board, requiring confirmation before doing so.

### Rationale

Archived chapters must be recoverable.

### Acceptance Criteria

```gherkin
@T-FUNC-0220.01.01
Scenario: Successfully unarchive a chapter
  Given I have an archived chapter
  And I am on the archived chapters board for that novel
  When I click the Unarchive button for that chapter
  And I am shown a confirmation dialog
  And I click the Continue button
  Then the chapter is unarchived
  And it appears on the structure display
  And it no longer appears on the archived chapters board

@T-FUNC-0220.01.02
Scenario: Cancel unarchiving a chapter
  Given I have an archived chapter
  And I am on the archived chapters board for that novel
  When I click the Unarchive button for that chapter
  And I am shown a confirmation dialog
  And I click the Cancel button
  Then the chapter is not unarchived
  And it remains on the archived chapters board
```

### Verification Method

Manual Test

## R-FUNC-0221.01 Delete a chapter

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0221](/novel-it-docs/features/02-novel-management/#feat-0221-delete-chapter) |

### Statement

The system SHALL allow the user to permanently delete a chapter and SHALL require confirmation before doing so.

### Rationale

Deletion is irreversible and a confirmation step protects the user from accidental data loss.

### Acceptance Criteria

```gherkin
@T-FUNC-0221.01.01
Scenario: Successfully delete a chapter
  Given I have an existing chapter
  When I click the Delete button for that chapter
  And I am shown a confirmation dialog warning that the deletion is permanent
  And I click the Continue button
  Then the chapter is permanently deleted
  And it no longer appears on the structure display

@T-FUNC-0221.01.02
Scenario: Cancel deleting a chapter
  Given I have an existing chapter
  When I click the Delete button for that chapter
  And I am shown a confirmation dialog
  And I click the Cancel button
  Then the chapter is not deleted
  And it remains on the structure display
```

### Verification Method

Manual Test

## R-DATA-0221.01 Chapter deletion cascades to scenes

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0221](/features/02-novel-management/#feat-0221-delete-chapter) |

### Statement

When a chapter is deleted the system SHALL also permanently delete all scenes belonging to that chapter.

### Rationale

Orphaned scenes with no parent chapter would be inaccessible. Cascade deletion ensures the database remains consistent.

### Acceptance Criteria

```gherkin
@T-DATA-0221.01.01
Scenario: Scenes are deleted with the chapter
  Given I have a chapter containing three scenes
  When I delete the chapter
  Then all three scenes belonging to that chapter are also deleted
  And none of those scenes are accessible in the application
```

### Verification Method

Manual Test

## R-FUNC-0223.01 Create a scene

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0223](/novel-it-docs/features/02-novel-management/#feat-0223-add-scene) |

### Statement

The system SHALL allow the user to create a scene with the following properties: name, description, notes, and status. Scenes SHALL be parented off a chapter.

### Rationale

Scenes are the leaf nodes of the manuscript hierarchy and the units of writing. All manuscript text is written within scenes.

### Acceptance Criteria

```gherkin
@T-FUNC-0223.01.01
Scenario: Successfully create a scene
  Given I have an existing chapter
  And I am on the chapter structure display
  When I click the Add Scene button
  And I enter a name
  And I click the Save button
  Then the scene is created
  And it appears on the chapter structure display
```

### Verification Method

Manual Test

## R-UI-0223.01 Add scene form presents all required fields

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0223](/features/02-novel-management/#feat-0223-add-scene) |

### Statement

The add scene form SHALL present the following fields: name, description, notes, and status.

### Rationale

All specified scene properties must be available for input when a scene is created.

### Acceptance Criteria

```gherkin
@T-UI-0223.01.01
Scenario: Add scene form presents all required fields
  Given I have an existing chapter
  When I click the Add Scene button
  Then the add scene form displays fields for: name, description, notes, and status
```

### Verification Method

Manual Test

## R-FUNC-0224.01 Edit a scene

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0224](/novel-it-docs/features/02-novel-management/#feat-0224-edit-scene) |

### Statement

The system SHALL allow the user to save changes to a scene's properties and SHALL allow the user to cancel without saving, discarding any changes made.

### Rationale

Scene properties need to be updatable as the author plans and revises their work. The cancel function protects the user from inadvertently overwriting existing values.

### Acceptance Criteria

```gherkin
@T-FUNC-0224.01.01
Scenario: Successfully edit a scene
  Given I have an existing scene
  And I am on the edit scene page
  When I change the name
  And I click the Save button
  Then the scene is updated
  And the new name is displayed on the chapter structure display

@T-FUNC-0224.01.02
Scenario: Cancel editing a scene
  Given I have an existing scene
  And I am on the edit scene page
  When I change the name
  And I click the Cancel button
  Then the scene is not updated
  And the original name is retained
```

### Verification Method

Manual Test

## R-UI-0224.01 Edit scene form presents all required fields

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0224](/features/02-novel-management/#feat-0224-edit-scene) |

### Statement

The edit scene form SHALL present the following editable fields: name, description, notes, and status. The word count SHALL be displayed as a read-only field.

### Rationale

All specified scene properties must be available for editing. The word count must be visible but protected from direct editing as it is a calculated value.

### Acceptance Criteria

```gherkin
@T-UI-0224.01.01
Scenario: Edit scene form presents all editable fields
  Given I have an existing scene
  When I navigate to the edit scene page
  Then the form displays editable fields for: name, description, notes, and status

@T-UI-0224.01.02
Scenario: Edit scene form displays word count as read-only
  Given I have an existing scene containing text
  When I navigate to the edit scene page
  Then the word count is displayed
  And it is not editable
```

### Verification Method

Manual Test

## R-FUNC-0224.02 Write button opens the editor

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0224](/features/02-novel-management/#feat-0224-edit-scene) |

### Statement

The system SHALL provide a Write button on the edit scene page that navigates the user to the writing interface for that scene.

### Rationale

The Write button provides a direct path from scene management into the writing interface, reducing the number of steps required to begin writing.

### Acceptance Criteria

```gherkin
@T-FUNC-0224.02.01
Scenario: Write button navigates to the editor
  Given I have an existing scene
  And I am on the edit scene page
  When I click the Write button
  Then I am navigated to the writing interface for that scene
```

### Verification Method

Manual Test

## R-FUNC-0225.01 Archive a scene

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0225](/novel-it-docs/features/02-novel-management/#feat-0225-archive-scene) |

### Statement

The system SHALL allow the user to archive a scene and SHALL require confirmation before doing so.

### Rationale

Archiving is a recoverable action but should not be triggered accidentally.

### Acceptance Criteria

```gherkin
@T-FUNC-0225.01.01
Scenario: Successfully archive a scene
  Given I have an existing scene on the chapter structure display
  When I click the Archive button for that scene
  And I am shown a confirmation dialog
  And I click the Continue button
  Then the scene is archived
  And it no longer appears on the chapter structure display

@T-FUNC-0225.01.02
Scenario: Cancel archiving a scene
  Given I have an existing scene on the chapter structure display
  When I click the Archive button for that scene
  And I am shown a confirmation dialog
  And I click the Cancel button
  Then the scene is not archived
  And it remains on the chapter structure display
```

### Verification Method

Manual Test

## R-FUNC-0226.01 Unarchive a scene

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0226](/novel-it-docs/features/02-novel-management/#feat-0226-unarchive-scene) |

### Statement

The system SHALL display archived scenes on a separate archived scenes board and SHALL allow the user to unarchive a scene from that board, requiring confirmation before doing so.

### Rationale

Archived scenes must be recoverable.

### Acceptance Criteria

```gherkin
@T-FUNC-0226.01.01
Scenario: Successfully unarchive a scene
  Given I have an archived scene
  And I am on the archived scenes board for that chapter
  When I click the Unarchive button for that scene
  And I am shown a confirmation dialog
  And I click the Continue button
  Then the scene is unarchived
  And it appears on the chapter structure display
  And it no longer appears on the archived scenes board

@T-FUNC-0226.01.02
Scenario: Cancel unarchiving a scene
  Given I have an archived scene
  And I am on the archived scenes board for that chapter
  When I click the Unarchive button for that scene
  And I am shown a confirmation dialog
  And I click the Cancel button
  Then the scene is not unarchived
  And it remains on the archived scenes board
```

### Verification Method

Manual Test

## R-FUNC-0227.01 Delete a scene

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0227](/novel-it-docs/features/02-novel-management/#feat-0227-delete-scene) |

### Statement

The system SHALL allow the user to permanently delete a scene and SHALL require confirmation before doing so.

### Rationale

Deletion is irreversible and a confirmation step protects the user from accidental data loss.

### Acceptance Criteria

```gherkin
@T-FUNC-0227.01.01
Scenario: Successfully delete a scene
  Given I have an existing scene
  When I click the Delete button for that scene
  And I am shown a confirmation dialog warning that the deletion is permanent
  And I click the Continue button
  Then the scene is permanently deleted
  And it no longer appears on the chapter structure display

@T-FUNC-0227.01.02
Scenario: Cancel deleting a scene
  Given I have an existing scene
  When I click the Delete button for that scene
  And I am shown a confirmation dialog
  And I click the Cancel button
  Then the scene is not deleted
  And it remains on the chapter structure display
```

### Verification Method

Manual Test

## R-FUNC-0228.01 Relocate a scene to a different chapter

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0228](/novel-it-docs/features/02-novel-management/#feat-0228-scene-relocation) |

### Statement

The system SHALL allow the user to move a scene to a different chapter within the same novel.

### Rationale

Authors frequently restructure their manuscripts by moving scenes between chapters as the narrative develops.

### Acceptance Criteria

```gherkin
@T-FUNC-0228.01.01
Scenario: Successfully relocate a scene to another chapter
  Given I have a novel with two chapters each containing at least one scene
  When I move a scene from the first chapter to the second chapter
  Then the scene appears under the second chapter
  And it no longer appears under the first chapter
```

### Verification Method

Manual Test

## R-FUNC-0229.01 Status property values

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0229](/novel-it-docs/features/02-novel-management/#feat-0229-status-selection) |

### Statement

The system SHALL provide a Status property for novels, parts, chapters, and scenes with the following values: Not started, Plotting, First draft, First review, Second draft, Second review, Structural edit, Final edit, Beta reading, Publishing, Published.

### Rationale

Status values allow the author to track the progress of each manuscript entity through the writing and editing workflow.

### Acceptance Criteria

```gherkin
@T-FUNC-0229.01.01
Scenario: Status values are available on a novel
  Given I am on the add novel page
  When I open the status dropdown
  Then I see exactly the following options: Not started, Plotting, First draft, First review, Second draft, Second review, Structural edit, Final edit, Beta reading, Publishing, Published

@T-FUNC-0229.01.02
Scenario: Status values are available on a part
  Given I am on the add part page
  When I open the status dropdown
  Then I see exactly the following options: Not started, Plotting, First draft, First review, Second draft, Second review, Structural edit, Final edit, Beta reading, Publishing, Published

@T-FUNC-0229.01.03
Scenario: Status values are available on a chapter
  Given I am on the add chapter page
  When I open the status dropdown
  Then I see exactly the following options: Not started, Plotting, First draft, First review, Second draft, Second review, Structural edit, Final edit, Beta reading, Publishing, Published

@T-FUNC-0229.01.04
Scenario: Status values are available on a scene
  Given I am on the add scene page
  When I open the status dropdown
  Then I see exactly the following options: Not started, Plotting, First draft, First review, Second draft, Second review, Structural edit, Final edit, Beta reading, Publishing, Published
```

### Verification Method

Manual Test

## R-FUNC-0229.02 Status defaults to Not started

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0229](/features/02-novel-management/#feat-0229-status-selection) |

### Statement

The system SHALL default the status property to "Not started" when a new novel, part, chapter, or scene is created.

### Rationale

"Not started" is the correct initial state for any newly created manuscript entity. It accurately reflects that no writing has yet taken place.

### Acceptance Criteria

```gherkin
@T-FUNC-0229.02.01
Scenario: Status defaults to Not started on a new novel
  Given I am on the add novel page
  Then the status field displays "Not started" by default

@T-FUNC-0229.02.02
Scenario: Status defaults to Not started on a new part
  Given I am on the add part page
  Then the status field displays "Not started" by default

@T-FUNC-0229.02.03
Scenario: Status defaults to Not started on a new chapter
  Given I am on the add chapter page
  Then the status field displays "Not started" by default

@T-FUNC-0229.02.04
Scenario: Status defaults to Not started on a new scene
  Given I am on the add scene page
  Then the status field displays "Not started" by default
```

### Verification Method

Manual Test
