---
title: "04 Character Management"
description: "Requirements for character profiles and relationships"
draft: false
revision: "2.0"
revision_date: "20-Apr-2026"
---

*Phase 2 and 4 features (FEAT-0404 Archive character, FEAT-0405 Unarchive character, FEAT-0406 Delete character, FEAT-0407 Duplicate character, FEAT-0408 Character relocation, FEAT-0409 Character sharing) are out of scope for this pass and have no requirements entries here.*

## R-FUNC-0401.01 Character list board displays all characters

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0401](/novel-it-docs/features/04-character-management/#feat-0401-character-list-board) |

### Statement

The system SHALL display all non-archived characters belonging to the current novel as cards on the character list board.

### Rationale

The character list board is the primary navigation view for character management. All active characters must be viewable and accessible from this board.

### Acceptance Criteria

```gherkin
@T-FUNC-0401.01.01
Scenario: Characters are displayed as cards on the board
  Given I have a novel with three characters
  When I navigate to the character list board
  Then I see three character cards displayed

@T-FUNC-0401.01.02
Scenario: Archived characters do not appear on the character list board
  Given I have a novel with one active character and one archived character
  When I navigate to the character list board
  Then I see only the active character
  And I do not see the archived character
```

### Verification Method

Manual Test

## R-UI-0401.02 Character card displays the character image

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0401](/features/04-character-management/#feat-0401-character-list-board) |

### Statement

Where a character image has been uploaded, the character's card on the list board SHALL display that image.

### Rationale

A visual representation of a character on the list board helps the author quickly identify characters, particularly in novels with large casts.

### Acceptance Criteria

```gherkin
@T-UI-0401.02.01
Scenario: Character image is displayed on the card when one has been uploaded
  Given I have a character with an uploaded image
  When I view the character list board
  Then the character's card displays the uploaded image

@T-UI-0401.02.02
Scenario: Character card displays no image when none has been uploaded
  Given I have a character with no uploaded image
  When I view the character list board
  Then the character's card does not display an image
```

### Verification Method

Manual Test

## R-UI-0401.01 Character list board has no parent summary section

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0401](/features/04-character-management/#feat-0401-character-list-board) |

### Statement

The character list board SHALL NOT display a parent summary section.

### Rationale

Characters have no subordinate entities of their own and are not children of a named parent entity in the way that chapters are children of parts. A parent summary section would be meaningless on this board.

### Acceptance Criteria

```gherkin
@T-UI-0401.01.01
Scenario: No parent summary section is shown on the character list board
  Given I have a novel with at least one character
  When I navigate to the character list board
  Then I do not see a parent summary section
  And I see only the character cards
```

### Verification Method

Manual Test

## R-FUNC-0402.01 Save and cancel when editing a character

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0402](/novel-it-docs/features/04-character-management/#feat-0402-edit-character) |

### Statement

The system SHALL allow the user to save changes to a character's properties and SHALL allow the user to cancel without saving, discarding any changes made.

### Rationale

Character properties need to be updatable as the author develops their characters. The cancel function protects the user from inadvertently overwriting existing values.

### Acceptance Criteria

```gherkin
@T-FUNC-0402.01.01
Scenario: Successfully save changes to a character
  Given I have an existing character
  And I am on the edit character page
  When I change the full name
  And I click the Save button
  Then the character is updated
  And the new name is displayed on the character list board

@T-FUNC-0402.01.02
Scenario: Cancel editing a character
  Given I have an existing character
  And I am on the edit character page
  When I change the full name
  And I click the Cancel button
  Then the character is not updated
  And the original name is retained
```

### Verification Method

Manual Test

## R-UI-0402.01 Edit character form displays appears in scenes as read-only

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0402](/features/04-character-management/#feat-0402-edit-character) |

### Statement

The edit character form SHALL display the appears in scenes field as a read-only calculated value that cannot be edited directly by the user.

### Rationale

The appears in scenes field is populated automatically by the cross-referencing feature when scenes are saved. It must be visible to the author as useful reference information, but must not be editable as it would then diverge from the actual scene content.

### Acceptance Criteria

```gherkin
@T-UI-0402.01.01
Scenario: Appears in scenes is displayed as read-only on the edit character page
  Given I have an existing character
  When I navigate to the edit character page
  Then the appears in scenes field is displayed
  And it is not editable
```

### Verification Method

Manual Test

## R-FUNC-0403.01 Create a character

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0403](/novel-it-docs/features/04-character-management/#feat-0403-add-character) |

### Statement

The system SHALL allow the user to create a character belonging to the current novel.

### Rationale

Characters are the core planning entity for narrative fiction. Authors need to be able to create and store character profiles within the context of a specific novel.

### Acceptance Criteria

```gherkin
@T-FUNC-0403.01.01
Scenario: Successfully create a character
  Given I have an existing novel
  And I am on the character list board
  When I click the Add Character button
  And I enter a full name
  And I click the Save button
  Then the character is created
  And it appears on the character list board

@T-FUNC-0403.01.02
Scenario: Attempt to create a character without a full name
  Given I am on the add character page
  When I click the Save button without entering a full name
  Then the character is not created
  And I see an error message indicating that a full name is required
```

### Verification Method

Manual Test

## R-UI-0403.01 Add character form presents all required fields

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0403](/features/04-character-management/#feat-0403-add-character) |

### Statement

The add character form SHALL present the following fields: full name, first name, middle name, last name, nickname, aliases, gender, age, role in story, physical description, interview, the lie they believe, goals and motivations, fears and weaknesses, arc in story, character image, description, and notes.

### Rationale

All specified character properties must be available for input when a character is created.

### Acceptance Criteria

```gherkin
@T-UI-0403.01.01
Scenario: Add character form presents all required fields
  Given I have an existing novel
  When I click the Add Character button
  Then the add character form displays fields for: full name, first name, middle name, last name, nickname, aliases, gender, age, role in story, physical description, interview, the lie they believe, goals and motivations, fears and weaknesses, arc in story, character image, description, and notes
```

### Verification Method

Manual Test

## R-FUNC-0403.03 Add a character role value

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0403](/features/04-character-management/#feat-0403-add-character) |

### Statement

The system SHALL allow the user to add new character role values from within the character form. New role values SHALL be scoped to the current novel and SHALL become immediately available for selection.

### Rationale

Character roles are novel-specific and cannot be defined in advance by the application. The author must be able to define roles that are meaningful to their particular story without leaving the character form.

### Acceptance Criteria

```gherkin
@T-FUNC-0403.03.01
Scenario: Successfully add a new character role value
  Given I am on the character form for a novel
  When I open the role manager
  And I enter a new role name
  And I click the Add button
  Then the new role value is saved
  And it is immediately available for selection in the role field

@T-FUNC-0403.03.02
Scenario: Role values are scoped to the current novel
  Given I have added a role value to Novel A
  When I open the character form for Novel B
  Then the role value from Novel A is not available in Novel B's role field
```

### Verification Method

Manual Test

## R-FUNC-0403.04 Rename a character role value

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0403](/features/04-character-management/#feat-0403-add-character) |

### Statement

The system SHALL allow the user to rename an existing character role value from within the character form. The renamed value SHALL be reflected immediately wherever it is displayed.

### Rationale

Role names may need to evolve as the author develops their story structure. Renaming must be possible without losing the association between the role and any characters already assigned to it.

### Acceptance Criteria

```gherkin
@T-FUNC-0403.04.01
Scenario: Successfully rename a character role value
  Given a character role value exists
  And I am on the character form
  When I open the role manager
  And I rename the role value
  And I click the Save button
  Then the role value is updated
  And any characters assigned to that role display the new name
```

### Verification Method

Manual Test

## R-FUNC-0403.05 Delete a character role value

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0403](/features/04-character-management/#feat-0403-add-character) |

### Statement

The system SHALL allow the user to delete an existing character role value from within the character form. Deleting a role value SHALL NOT delete any characters assigned to that role; those characters SHALL have their role field set to empty.

### Rationale

Role values that are no longer relevant should be removable without data loss. The relationship between a character and a role is optional, so removing the role value simply clears the field on affected characters.

### Acceptance Criteria

```gherkin
@T-FUNC-0403.05.01
Scenario: Successfully delete a character role value
  Given a character role value exists
  And I am on the character form
  When I open the role manager
  And I delete the role value
  Then the role value is removed from the available options

@T-FUNC-0403.05.02
Scenario: Deleting a role value does not delete assigned characters
  Given a character role value exists
  And one or more characters are assigned to that role
  When I delete the role value
  Then the characters assigned to that role are not deleted
  And those characters have no role assigned
```

### Verification Method

Manual Test

## R-FUNC-0403.02 Upload a character image

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0403](/features/04-character-management/#feat-0403-add-character) |

### Statement

The system SHALL allow the user to upload an image for a character from both the add character and edit character pages. The uploaded image SHALL be stored and associated with the character.

### Rationale

A character image provides a visual reference that aids the author in maintaining consistency when writing character descriptions and appearances.

### Acceptance Criteria

```gherkin
@T-FUNC-0403.02.01
Scenario: Successfully upload a character image on the add character page
  Given I am on the add character page
  When I upload an image file using the character image field
  And I click the Save button
  Then the character is created with the uploaded image associated
  And the image is displayed on the character's edit page

@T-FUNC-0403.02.02
Scenario: Successfully upload a character image on the edit character page
  Given I have an existing character with no image
  And I am on the edit character page
  When I upload an image file using the character image field
  And I click the Save button
  Then the uploaded image is associated with the character
  And the image is displayed on the character's edit page

@T-FUNC-0403.02.03
Scenario: Successfully replace an existing character image
  Given I have an existing character with an uploaded image
  And I am on the edit character page
  When I upload a new image file using the character image field
  And I click the Save button
  Then the new image replaces the previous image
```

### Verification Method

Manual Test

## R-SEC-0403.01 Character image upload restricted to PNG and JPEG formats

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0403](/features/04-character-management/#feat-0403-add-character) |

### Statement

The system SHALL only accept image files with the extensions `.png`, `.jpg`, or `.jpeg` for character image upload. Any other file type SHALL be rejected and the user SHALL be shown an informative error message.

### Rationale

Restricting accepted formats to PNG and JPEG limits the attack surface for malicious file uploads and avoids server-side complexity in handling varied image formats. PNG covers illustrated character portraits; JPEG covers photographic references. Both are natively supported in all target browsers without additional processing.

### Acceptance Criteria

```gherkin
@T-SEC-0403.01.01
Scenario: PNG file is accepted for character image upload
  Given I am on the add character page
  When I upload a file with the extension .png
  Then the file is accepted

@T-SEC-0403.01.02
Scenario: JPG file is accepted for character image upload
  Given I am on the add character page
  When I upload a file with the extension .jpg
  Then the file is accepted

@T-SEC-0403.01.03
Scenario: JPEG file is accepted for character image upload
  Given I am on the add character page
  When I upload a file with the extension .jpeg
  Then the file is accepted

@T-SEC-0403.01.04
Scenario: File with unsupported extension is rejected
  Given I am on the add character page
  When I attempt to upload a file with an extension other than .png, .jpg, or .jpeg
  Then the file is rejected
  And I see an error message indicating that only PNG and JPEG files are accepted
```

### Verification Method

Manual Test

## R-FUNC-0410.01 Define a relationship between a character and any planning entity

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0410](/novel-it-docs/features/04-character-management/#feat-0410-character-relationships) |

### Statement

The system SHALL allow the user to define a relationship between a character and any other planning entity within the same novel. Each relationship SHALL have a forward label, a reverse label, and an optional notes field.

### Rationale

Characters in fiction have relationships not only with other characters but with locations and items — a character may own an object, inhabit a place, or be associated with a setting in a meaningful way. The labels are free-form text entered by the author with no predefined set of relationship types.

### Acceptance Criteria

```gherkin
@T-FUNC-0410.01.01
Scenario: Successfully define a relationship between two characters
  Given I have a novel with two characters
  And I am on the details page of the first character
  When I add a relationship to the second character
  And I enter a forward label of "mentor of"
  And I enter a reverse label of "mentored by"
  And I click the Save button
  Then the relationship is created
  And it is displayed on the first character's details page with the forward label
  And it is displayed on the second character's details page with the reverse label

@T-FUNC-0410.01.02
Scenario: Successfully define a relationship between a character and an item
  Given I have a novel with a character and an item
  And I am on the details page of the character
  When I add a relationship to the item
  And I enter a forward label of "owns"
  And I enter a reverse label of "owned by"
  And I click the Save button
  Then the relationship is created
  And it is displayed on the character's details page with the label "owns"
  And it is displayed on the item's details page with the label "owned by"
```

### Verification Method

Manual Test

## R-FUNC-0410.02 Relationships are displayed on both participating entities

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0410](/features/04-character-management/#feat-0410-character-relationships) |

### Statement

The system SHALL display all relationships in which a character participates on that character's details page, showing the appropriate directional label for each relationship from that character's perspective. The relationship SHALL also be displayed on the other participating entity's details page with the reverse label.

### Rationale

An author viewing a character's profile needs to see all of that character's connections in one place, labelled from that character's point of view. The same applies to the other participant — both ends of the relationship must be discoverable from either entity's page.

### Acceptance Criteria

```gherkin
@T-FUNC-0410.02.01
Scenario: Relationship appears on both participating entities' pages with correct labels
  Given a relationship exists between a character and an item
  And the forward label is "owns" and the reverse label is "owned by"
  When I view the character's details page
  Then I see the relationship to the item labelled "owns"
  When I view the item's details page
  Then I see the relationship to the character labelled "owned by"
```

### Verification Method

Manual Test

## R-FUNC-0410.03 Edit a relationship from either participating entity's page

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0410](/features/04-character-management/#feat-0410-character-relationships) |

### Statement

The system SHALL allow the user to edit a relationship from either participating entity's details page, including the forward label, reverse label, and notes.

### Rationale

Relationship descriptions may evolve as the author develops the story. Edits must be possible from either entity's page to avoid unnecessary navigation.

### Acceptance Criteria

```gherkin
@T-FUNC-0410.03.01
Scenario: Successfully edit a relationship from one entity's page
  Given a relationship exists between a character and a location
  And I am on the details page of the character
  When I edit the relationship and change the forward label
  And I click the Save button
  Then the updated label is displayed on both the character's and the location's details pages
```

### Verification Method

Manual Test

## R-FUNC-0410.04 Delete a relationship from either participating entity's page

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0410](/features/04-character-management/#feat-0410-character-relationships) |

### Statement

The system SHALL allow the user to delete a relationship from either participating entity's details page.

### Rationale

Relationships that are no longer relevant to the story should be removable without deleting either of the participating entities.

### Acceptance Criteria

```gherkin
@T-FUNC-0410.04.01
Scenario: Successfully delete a relationship
  Given a relationship exists between a character and an item
  And I am on the details page of the character
  When I delete the relationship
  Then the relationship no longer appears on the character's details page
  And the relationship no longer appears on the item's details page
  And both the character and the item still exist
```

### Verification Method

Manual Test

## R-DATA-0410.01 Deleting a character removes all its relationships

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0410](/features/04-character-management/#feat-0410-character-relationships) |

### Statement

When a character is deleted the system SHALL also delete all relationships in which that character participates.

### Rationale

A relationship cannot exist without both of its participants. Leaving orphaned relationship records when a character is deleted would create data inconsistencies and confusing displays on the remaining character's page.

### Acceptance Criteria

```gherkin
@T-DATA-0410.01.01
Scenario: Relationships are removed when a character is deleted
  Given a relationship exists between Character A and Character B
  When Character A is deleted
  Then the relationship no longer appears on Character B's details page
```

### Verification Method

Manual Test
