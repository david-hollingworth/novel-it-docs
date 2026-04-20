---
title: "07 World Building Management"
description: "Requirements for world building item profiles and relationships"
draft: false
revision: "2.0"
revision_date: "20-Apr-2026"
---

*Phase 2 and 4 features (FEAT-0704 Archive world building item, FEAT-0705 Unarchive world building item, FEAT-0706 Delete world building item, FEAT-0707 Duplicate world building item, FEAT-0708 World building item relocation, FEAT-0709 World building item sharing) are out of scope for this pass and have no requirements entries here.*

## R-FUNC-0701.01 World building list board displays all world building items

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0701](/novel-it-docs/features/07-world-building/#feat-0701-world-building-list-board) |

### Statement

The system SHALL display all non-archived world building items belonging to the current novel as cards on the world building list board.

### Rationale

The world building list board is the primary navigation view for world building management. All active world building items must be viewable and accessible from this board.

### Acceptance Criteria

```gherkin
@T-FUNC-0701.01.01
Scenario: World building items are displayed as cards on the board
  Given I have a novel with three world building items
  When I navigate to the world building list board
  Then I see three world building item cards displayed

@T-FUNC-0701.01.02
Scenario: Archived world building items do not appear on the world building list board
  Given I have a novel with one active world building item and one archived world building item
  When I navigate to the world building list board
  Then I see only the active world building item
  And I do not see the archived world building item
```

### Verification Method

Manual Test

## R-UI-0701.01 World building list board has no parent summary section

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0701](/features/07-world-building/#feat-0701-world-building-list-board) |

### Statement

The world building list board SHALL NOT display a parent summary section.

### Rationale

World building items have no subordinate entities of their own and are not children of a named parent entity. A parent summary section would be meaningless on this board.

### Acceptance Criteria

```gherkin
@T-UI-0701.01.01
Scenario: No parent summary section is shown on the world building list board
  Given I have a novel with at least one world building item
  When I navigate to the world building list board
  Then I do not see a parent summary section
  And I see only the world building item cards
```

### Verification Method

Manual Test

## R-UI-0701.02 World building item card displays the item image

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0701](/features/07-world-building/#feat-0701-world-building-list-board) |

### Statement

Where an image has been uploaded for a world building item, the item's card on the list board SHALL display that image.

### Rationale

A visual reference on the world building list board helps the author quickly identify items, particularly in richly detailed fictional worlds with many entries.

### Acceptance Criteria

```gherkin
@T-UI-0701.02.01
Scenario: Image is displayed on the card when one has been uploaded
  Given I have a world building item with an uploaded image
  When I view the world building list board
  Then the item's card displays the uploaded image

@T-UI-0701.02.02
Scenario: Card displays no image when none has been uploaded
  Given I have a world building item with no uploaded image
  When I view the world building list board
  Then the item's card does not display an image
```

### Verification Method

Manual Test

## R-FUNC-0702.01 Create a world building item

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0702](/novel-it-docs/features/07-world-building/#feat-0702-add-world-building-item) |

### Statement

The system SHALL allow the user to create a world building item belonging to the current novel.

### Rationale

World building is a planning entity that allows the author to capture and organise the rules, history, and cultural fabric of their fictional world within the context of a specific novel.

### Acceptance Criteria

```gherkin
@T-FUNC-0702.01.01
Scenario: Successfully create a world building item
  Given I have an existing novel
  And I am on the world building list board
  When I click the Add World Building Item button
  And I enter a name
  And I click the Save button
  Then the world building item is created
  And it appears on the world building list board

@T-FUNC-0702.01.02
Scenario: Attempt to create a world building item without a name
  Given I am on the add world building item page
  When I click the Save button without entering a name
  Then the world building item is not created
  And I see an error message indicating that a name is required
```

### Verification Method

Manual Test

## R-UI-0702.01 Add world building item form presents all required fields

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0702](/features/07-world-building/#feat-0702-add-world-building-item) |

### Statement

The add world building item form SHALL present the following fields: name, type, description, notes, and image.

### Rationale

All specified world building item properties must be available for input when a world building item is created.

### Acceptance Criteria

```gherkin
@T-UI-0702.01.01
Scenario: Add world building item form presents all required fields
  Given I have an existing novel
  When I click the Add World Building Item button
  Then the add world building item form displays fields for: name, type, description, notes, and image
```

### Verification Method

Manual Test

## R-FUNC-0702.02 Upload a world building item image

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0702](/features/07-world-building/#feat-0702-add-world-building-item) |

### Statement

The system SHALL allow the user to upload an image for a world building item from both the add and edit pages. The uploaded image SHALL be stored and associated with the world building item.

### Rationale

An image provides a visual reference that helps the author illustrate aspects of their fictional world such as maps, cultural artefacts, or historical timelines.

### Acceptance Criteria

```gherkin
@T-FUNC-0702.02.01
Scenario: Successfully upload an image on the add world building item page
  Given I am on the add world building item page
  When I upload an image file using the image field
  And I click the Save button
  Then the world building item is created with the uploaded image associated
  And the image is displayed on the item's edit page

@T-FUNC-0702.02.02
Scenario: Successfully upload an image on the edit world building item page
  Given I have an existing world building item with no image
  And I am on the edit world building item page
  When I upload an image file using the image field
  And I click the Save button
  Then the uploaded image is associated with the world building item
  And the image is displayed on the item's edit page

@T-FUNC-0702.02.03
Scenario: Successfully replace an existing world building item image
  Given I have an existing world building item with an uploaded image
  And I am on the edit world building item page
  When I upload a new image file using the image field
  And I click the Save button
  Then the new image replaces the previous image
```

### Verification Method

Manual Test

## R-SEC-0702.01 World building item image upload restricted to PNG and JPEG formats

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0702](/features/07-world-building/#feat-0702-add-world-building-item) |

### Statement

The system SHALL only accept image files with the extensions `.png`, `.jpg`, or `.jpeg` for world building item image upload. Any other file type SHALL be rejected and the user SHALL be shown an informative error message.

### Rationale

Restricting accepted formats to PNG and JPEG limits the attack surface for malicious file uploads and avoids server-side complexity in handling varied image formats. Both formats are natively supported in all target browsers without additional processing.

### Acceptance Criteria

```gherkin
@T-SEC-0702.01.01
Scenario: PNG file is accepted for world building item image upload
  Given I am on the add world building item page
  When I upload a file with the extension .png
  Then the file is accepted

@T-SEC-0702.01.02
Scenario: JPG file is accepted for world building item image upload
  Given I am on the add world building item page
  When I upload a file with the extension .jpg
  Then the file is accepted

@T-SEC-0702.01.03
Scenario: JPEG file is accepted for world building item image upload
  Given I am on the add world building item page
  When I upload a file with the extension .jpeg
  Then the file is accepted

@T-SEC-0702.01.04
Scenario: File with unsupported extension is rejected
  Given I am on the add world building item page
  When I attempt to upload a file with an extension other than .png, .jpg, or .jpeg
  Then the file is rejected
  And I see an error message indicating that only PNG and JPEG files are accepted
```

### Verification Method

Manual Test

## R-FUNC-0702.03 Add a world building type value

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0702](/features/07-world-building/#feat-0702-add-world-building-item) |

### Statement

The system SHALL allow the user to add new world building type values from within the world building item form. New type values SHALL be scoped to the current novel and SHALL become immediately available for selection.

### Rationale

World building types are novel-specific and cannot be defined in advance by the application. The author must be able to define types that are meaningful to their particular world without leaving the form.

### Acceptance Criteria

```gherkin
@T-FUNC-0702.03.01
Scenario: Successfully add a new world building type value
  Given I am on the world building item form for a novel
  When I open the type manager
  And I enter a new type name
  And I click the Add button
  Then the new type value is saved
  And it is immediately available for selection in the type field

@T-FUNC-0702.03.02
Scenario: Type values are scoped to the current novel
  Given I have added a type value to Novel A
  When I open the world building item form for Novel B
  Then the type value from Novel A is not available in Novel B's type field
```

### Verification Method

Manual Test

## R-FUNC-0702.04 Rename a world building type value

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0702](/features/07-world-building/#feat-0702-add-world-building-item) |

### Statement

The system SHALL allow the user to rename an existing world building type value from within the world building item form. The renamed value SHALL be reflected immediately wherever it is displayed.

### Rationale

Type names may need to evolve as the author develops their world. Renaming must be possible without losing the association between the type and any world building items already assigned to it.

### Acceptance Criteria

```gherkin
@T-FUNC-0702.04.01
Scenario: Successfully rename a world building type value
  Given a world building type value exists
  And I am on the world building item form
  When I open the type manager
  And I rename the type value
  And I click the Save button
  Then the type value is updated
  And any world building items assigned to that type display the new name
```

### Verification Method

Manual Test

## R-FUNC-0702.05 Delete a world building type value

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0702](/features/07-world-building/#feat-0702-add-world-building-item) |

### Statement

The system SHALL allow the user to delete an existing world building type value from within the world building item form. Deleting a type value SHALL NOT delete any world building items assigned to that type; those items SHALL have their type field set to empty.

### Rationale

Type values that are no longer relevant should be removable without data loss. The relationship between a world building item and a type is optional, so removing the type value simply clears the field on affected items.

### Acceptance Criteria

```gherkin
@T-FUNC-0702.05.01
Scenario: Successfully delete a world building type value
  Given a world building type value exists
  And I am on the world building item form
  When I open the type manager
  And I delete the type value
  Then the type value is removed from the available options

@T-FUNC-0702.05.02
Scenario: Deleting a type value does not delete assigned world building items
  Given a world building type value exists
  And one or more world building items are assigned to that type
  When I delete the type value
  Then the world building items assigned to that type are not deleted
  And those items have no type assigned
```

### Verification Method

Manual Test

## R-FUNC-0703.01 Save and cancel when editing a world building item

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0703](/novel-it-docs/features/07-world-building/#feat-0703-edit-world-building-item) |

### Statement

The system SHALL allow the user to save changes to a world building item's properties and SHALL allow the user to cancel without saving, discarding any changes made.

### Rationale

World building item properties need to be updatable as the author develops their world. The cancel function protects the user from inadvertently overwriting existing values.

### Acceptance Criteria

```gherkin
@T-FUNC-0703.01.01
Scenario: Successfully save changes to a world building item
  Given I have an existing world building item
  And I am on the edit world building item page
  When I change the name
  And I click the Save button
  Then the world building item is updated
  And the new name is displayed on the world building list board

@T-FUNC-0703.01.02
Scenario: Cancel editing a world building item
  Given I have an existing world building item
  And I am on the edit world building item page
  When I change the name
  And I click the Cancel button
  Then the world building item is not updated
  And the original name is retained
```

### Verification Method

Manual Test

## R-UI-0703.01 Edit world building item form displays appears in scenes as read-only

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0703](/features/07-world-building/#feat-0703-edit-world-building-item) |

### Statement

The edit world building item form SHALL display the appears in scenes field as a read-only calculated value that cannot be edited directly by the user.

### Rationale

The appears in scenes field is populated automatically by the cross-referencing feature when scenes are saved. It must be visible to the author as useful reference information, but must not be editable as it would then diverge from the actual scene content.

### Acceptance Criteria

```gherkin
@T-UI-0703.01.01
Scenario: Appears in scenes is displayed as read-only on the edit world building item page
  Given I have an existing world building item
  When I navigate to the edit world building item page
  Then the appears in scenes field is displayed
  And it is not editable
```

### Verification Method

Manual Test

## R-FUNC-0710.01 Define a relationship between a world building item and any planning entity

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0710](/novel-it-docs/features/07-world-building/#feat-0710-world-building-item-relationships) |

### Statement

The system SHALL allow the user to define a relationship between a world building item and any other planning entity within the same novel. Each relationship SHALL have a forward label, a reverse label, and an optional notes field.

### Rationale

World building items have meaningful connections to characters, locations, items, and other world building entries — a religion may be practised by a character, a law may govern a location, a technology may affect an item. The labels are free-form text entered by the author with no predefined set of relationship types.

### Acceptance Criteria

```gherkin
@T-FUNC-0710.01.01
Scenario: Successfully define a relationship between a world building item and a character
  Given I have a novel with a world building item and a character
  And I am on the details page of the world building item
  When I add a relationship to the character
  And I enter a forward label of "practised by"
  And I enter a reverse label of "follows"
  And I click the Save button
  Then the relationship is created
  And it is displayed on the world building item's details page with the label "practised by"
  And it is displayed on the character's details page with the label "follows"

@T-FUNC-0710.01.02
Scenario: Successfully define a relationship between two world building items
  Given I have a novel with two world building items
  And I am on the details page of the first world building item
  When I add a relationship to the second world building item
  And I enter a forward label of "influences"
  And I enter a reverse label of "influenced by"
  And I click the Save button
  Then the relationship is created
  And it is displayed on the first item's details page with the label "influences"
  And it is displayed on the second item's details page with the label "influenced by"
```

### Verification Method

Manual Test

## R-FUNC-0710.02 Relationships are displayed on both participating entities

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0710](/features/07-world-building/#feat-0710-world-building-item-relationships) |

### Statement

The system SHALL display all relationships in which a world building item participates on that item's details page, showing the appropriate directional label for each relationship from that item's perspective. The relationship SHALL also be displayed on the other participating entity's details page with the reverse label.

### Rationale

An author viewing a world building item's profile needs to see all of that item's connections in one place, labelled from that item's point of view. Both ends of the relationship must be discoverable from either entity's page.

### Acceptance Criteria

```gherkin
@T-FUNC-0710.02.01
Scenario: Relationship appears on both participating entities' pages with correct labels
  Given a relationship exists between a world building item and a location
  And the forward label is "governs" and the reverse label is "governed by"
  When I view the world building item's details page
  Then I see the relationship to the location labelled "governs"
  When I view the location's details page
  Then I see the relationship to the world building item labelled "governed by"
```

### Verification Method

Manual Test

## R-FUNC-0710.03 Edit a relationship from either participating entity's page

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0710](/features/07-world-building/#feat-0710-world-building-item-relationships) |

### Statement

The system SHALL allow the user to edit a relationship from either participating entity's details page, including the forward label, reverse label, and notes.

### Rationale

Relationship descriptions may evolve as the author develops their world. Edits must be possible from either entity's page to avoid unnecessary navigation.

### Acceptance Criteria

```gherkin
@T-FUNC-0710.03.01
Scenario: Successfully edit a relationship from the world building item's page
  Given a relationship exists between a world building item and a character
  And I am on the details page of the world building item
  When I edit the relationship and change the forward label
  And I click the Save button
  Then the updated label is displayed on both the world building item's and the character's details pages
```

### Verification Method

Manual Test

## R-FUNC-0710.04 Delete a relationship from either participating entity's page

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0710](/features/07-world-building/#feat-0710-world-building-item-relationships) |

### Statement

The system SHALL allow the user to delete a relationship from either participating entity's details page.

### Rationale

Relationships that are no longer relevant to the story should be removable without deleting either of the participating entities.

### Acceptance Criteria

```gherkin
@T-FUNC-0710.04.01
Scenario: Successfully delete a relationship from the world building item's page
  Given a relationship exists between a world building item and a location
  And I am on the details page of the world building item
  When I delete the relationship
  Then the relationship no longer appears on the world building item's details page
  And the relationship no longer appears on the location's details page
  And both the world building item and the location still exist
```

### Verification Method

Manual Test

## R-DATA-0710.01 Deleting a world building item removes all its relationships

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0710](/features/07-world-building/#feat-0710-world-building-item-relationships) |

### Statement

When a world building item is deleted the system SHALL also delete all relationships in which that world building item participates.

### Rationale

A relationship cannot exist without both of its participants. Leaving orphaned relationship records when a world building item is deleted would create data inconsistencies and confusing displays on the remaining entity's page.

### Acceptance Criteria

```gherkin
@T-DATA-0710.01.01
Scenario: Relationships are removed when a world building item is deleted
  Given a relationship exists between a world building item and a character
  When the world building item is deleted
  Then the relationship no longer appears on the character's details page
```

### Verification Method

Manual Test
