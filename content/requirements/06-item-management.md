---
title: "06 Item Management"
description: "Requirements for item profiles and relationships"
draft: false
revision: "2.0"
revision_date: "20-Apr-2026"
---

*Phase 2 and 4 features (FEAT-0604 Archive item, FEAT-0605 Unarchive item, FEAT-0606 Delete item, FEAT-0607 Duplicate item, FEAT-0608 Item relocation, FEAT-0609 Item sharing) are out of scope for this pass and have no requirements entries here.*

## R-FUNC-0601.01 Item list board displays all items

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0601](/novel-it-docs/features/06-item-management/#feat-0601-item-list-board) |

### Statement

The system SHALL display all non-archived items belonging to the current novel as cards on the item list board.

### Rationale

The item list board is the primary navigation view for item management. All active items must be viewable and accessible from this board.

### Acceptance Criteria

```gherkin
@T-FUNC-0601.01.01
Scenario: Items are displayed as cards on the board
  Given I have a novel with three items
  When I navigate to the item list board
  Then I see three item cards displayed

@T-FUNC-0601.01.02
Scenario: Archived items do not appear on the item list board
  Given I have a novel with one active item and one archived item
  When I navigate to the item list board
  Then I see only the active item
  And I do not see the archived item
```

### Verification Method

Manual Test

## R-UI-0601.01 Item list board has no parent summary section

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0601](/features/06-item-management/#feat-0601-item-list-board) |

### Statement

The item list board SHALL NOT display a parent summary section.

### Rationale

Items have no subordinate entities of their own and are not children of a named parent entity. A parent summary section would be meaningless on this board.

### Acceptance Criteria

```gherkin
@T-UI-0601.01.01
Scenario: No parent summary section is shown on the item list board
  Given I have a novel with at least one item
  When I navigate to the item list board
  Then I do not see a parent summary section
  And I see only the item cards
```

### Verification Method

Manual Test

## R-UI-0601.02 Item card displays the item image

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0601](/features/06-item-management/#feat-0601-item-list-board) |

### Statement

Where an item image has been uploaded, the item's card on the list board SHALL display that image.

### Rationale

A visual representation of an item on the list board helps the author quickly identify items, particularly in novels with large numbers of objects and artefacts.

### Acceptance Criteria

```gherkin
@T-UI-0601.02.01
Scenario: Item image is displayed on the card when one has been uploaded
  Given I have an item with an uploaded image
  When I view the item list board
  Then the item's card displays the uploaded image

@T-UI-0601.02.02
Scenario: Item card displays no image when none has been uploaded
  Given I have an item with no uploaded image
  When I view the item list board
  Then the item's card does not display an image
```

### Verification Method

Manual Test

## R-FUNC-0602.01 Create an item

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0602](/novel-it-docs/features/06-item-management/#feat-0602-add-item) |

### Statement

The system SHALL allow the user to create an item belonging to the current novel.

### Rationale

Items are a core planning entity for narrative fiction. Authors need to be able to create and store item profiles within the context of a specific novel.

### Acceptance Criteria

```gherkin
@T-FUNC-0602.01.01
Scenario: Successfully create an item
  Given I have an existing novel
  And I am on the item list board
  When I click the Add Item button
  And I enter an item name
  And I click the Save button
  Then the item is created
  And it appears on the item list board

@T-FUNC-0602.01.02
Scenario: Attempt to create an item without a name
  Given I am on the add item page
  When I click the Save button without entering an item name
  Then the item is not created
  And I see an error message indicating that an item name is required
```

### Verification Method

Manual Test

## R-UI-0602.01 Add item form presents all required fields

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0602](/features/06-item-management/#feat-0602-add-item) |

### Statement

The add item form SHALL present the following fields: item name, item type, history, properties and abilities, description, notes, and image.

### Rationale

All specified item properties must be available for input when an item is created.

### Acceptance Criteria

```gherkin
@T-UI-0602.01.01
Scenario: Add item form presents all required fields
  Given I have an existing novel
  When I click the Add Item button
  Then the add item form displays fields for: item name, item type, history, properties and abilities, description, notes, and image
```

### Verification Method

Manual Test

## R-FUNC-0602.02 Upload an item image

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0602](/features/06-item-management/#feat-0602-add-item) |

### Statement

The system SHALL allow the user to upload an image for an item from both the add item and edit item pages. The uploaded image SHALL be stored and associated with the item.

### Rationale

An item image provides a visual reference that helps the author maintain consistency when writing descriptions and references to the item.

### Acceptance Criteria

```gherkin
@T-FUNC-0602.02.01
Scenario: Successfully upload an item image on the add item page
  Given I am on the add item page
  When I upload an image file using the image field
  And I click the Save button
  Then the item is created with the uploaded image associated
  And the image is displayed on the item's edit page

@T-FUNC-0602.02.02
Scenario: Successfully upload an item image on the edit item page
  Given I have an existing item with no image
  And I am on the edit item page
  When I upload an image file using the image field
  And I click the Save button
  Then the uploaded image is associated with the item
  And the image is displayed on the item's edit page

@T-FUNC-0602.02.03
Scenario: Successfully replace an existing item image
  Given I have an existing item with an uploaded image
  And I am on the edit item page
  When I upload a new image file using the image field
  And I click the Save button
  Then the new image replaces the previous image
```

### Verification Method

Manual Test

## R-SEC-0602.01 Item image upload restricted to PNG and JPEG formats

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0602](/features/06-item-management/#feat-0602-add-item) |

### Statement

The system SHALL only accept image files with the extensions `.png`, `.jpg`, or `.jpeg` for item image upload. Any other file type SHALL be rejected and the user SHALL be shown an informative error message.

### Rationale

Restricting accepted formats to PNG and JPEG limits the attack surface for malicious file uploads and avoids server-side complexity in handling varied image formats. Both formats are natively supported in all target browsers without additional processing.

### Acceptance Criteria

```gherkin
@T-SEC-0602.01.01
Scenario: PNG file is accepted for item image upload
  Given I am on the add item page
  When I upload a file with the extension .png
  Then the file is accepted

@T-SEC-0602.01.02
Scenario: JPG file is accepted for item image upload
  Given I am on the add item page
  When I upload a file with the extension .jpg
  Then the file is accepted

@T-SEC-0602.01.03
Scenario: JPEG file is accepted for item image upload
  Given I am on the add item page
  When I upload a file with the extension .jpeg
  Then the file is accepted

@T-SEC-0602.01.04
Scenario: File with unsupported extension is rejected
  Given I am on the add item page
  When I attempt to upload a file with an extension other than .png, .jpg, or .jpeg
  Then the file is rejected
  And I see an error message indicating that only PNG and JPEG files are accepted
```

### Verification Method

Manual Test

## R-FUNC-0602.03 Add an item type value

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0602](/features/06-item-management/#feat-0602-add-item) |

### Statement

The system SHALL allow the user to add new item type values from within the item form. New type values SHALL be scoped to the current novel and SHALL become immediately available for selection.

### Rationale

Item types are novel-specific and cannot be defined in advance by the application. The author must be able to define types that are meaningful to their particular story without leaving the item form.

### Acceptance Criteria

```gherkin
@T-FUNC-0602.03.01
Scenario: Successfully add a new item type value
  Given I am on the item form for a novel
  When I open the type manager
  And I enter a new type name
  And I click the Add button
  Then the new type value is saved
  And it is immediately available for selection in the type field

@T-FUNC-0602.03.02
Scenario: Type values are scoped to the current novel
  Given I have added a type value to Novel A
  When I open the item form for Novel B
  Then the type value from Novel A is not available in Novel B's type field
```

### Verification Method

Manual Test

## R-FUNC-0602.04 Rename an item type value

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0602](/features/06-item-management/#feat-0602-add-item) |

### Statement

The system SHALL allow the user to rename an existing item type value from within the item form. The renamed value SHALL be reflected immediately wherever it is displayed.

### Rationale

Type names may need to evolve as the author develops their story. Renaming must be possible without losing the association between the type and any items already assigned to it.

### Acceptance Criteria

```gherkin
@T-FUNC-0602.04.01
Scenario: Successfully rename an item type value
  Given an item type value exists
  And I am on the item form
  When I open the type manager
  And I rename the type value
  And I click the Save button
  Then the type value is updated
  And any items assigned to that type display the new name
```

### Verification Method

Manual Test

## R-FUNC-0602.05 Delete an item type value

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0602](/features/06-item-management/#feat-0602-add-item) |

### Statement

The system SHALL allow the user to delete an existing item type value from within the item form. Deleting a type value SHALL NOT delete any items assigned to that type; those items SHALL have their type field set to empty.

### Rationale

Type values that are no longer relevant should be removable without data loss. The relationship between an item and a type is optional, so removing the type value simply clears the field on affected items.

### Acceptance Criteria

```gherkin
@T-FUNC-0602.05.01
Scenario: Successfully delete an item type value
  Given an item type value exists
  And I am on the item form
  When I open the type manager
  And I delete the type value
  Then the type value is removed from the available options

@T-FUNC-0602.05.02
Scenario: Deleting a type value does not delete assigned items
  Given an item type value exists
  And one or more items are assigned to that type
  When I delete the type value
  Then the items assigned to that type are not deleted
  And those items have no type assigned
```

### Verification Method

Manual Test

## R-FUNC-0603.01 Save and cancel when editing an item

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0603](/novel-it-docs/features/06-item-management/#feat-0603-edit-item) |

### Statement

The system SHALL allow the user to save changes to an item's properties and SHALL allow the user to cancel without saving, discarding any changes made.

### Rationale

Item properties need to be updatable as the author develops their story. The cancel function protects the user from inadvertently overwriting existing values.

### Acceptance Criteria

```gherkin
@T-FUNC-0603.01.01
Scenario: Successfully save changes to an item
  Given I have an existing item
  And I am on the edit item page
  When I change the item name
  And I click the Save button
  Then the item is updated
  And the new name is displayed on the item list board

@T-FUNC-0603.01.02
Scenario: Cancel editing an item
  Given I have an existing item
  And I am on the edit item page
  When I change the item name
  And I click the Cancel button
  Then the item is not updated
  And the original name is retained
```

### Verification Method

Manual Test

## R-UI-0603.01 Edit item form displays appears in scenes as read-only

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0603](/features/06-item-management/#feat-0603-edit-item) |

### Statement

The edit item form SHALL display the appears in scenes field as a read-only calculated value that cannot be edited directly by the user.

### Rationale

The appears in scenes field is populated automatically by the cross-referencing feature when scenes are saved. It must be visible to the author as useful reference information, but must not be editable as it would then diverge from the actual scene content.

### Acceptance Criteria

```gherkin
@T-UI-0603.01.01
Scenario: Appears in scenes is displayed as read-only on the edit item page
  Given I have an existing item
  When I navigate to the edit item page
  Then the appears in scenes field is displayed
  And it is not editable
```

### Verification Method

Manual Test

## R-FUNC-0610.01 Define a relationship between an item and any planning entity

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0610](/novel-it-docs/features/06-item-management/#feat-0610-item-relationships) |

### Statement

The system SHALL allow the user to define a relationship between an item and any other planning entity within the same novel. Each relationship SHALL have a forward label, a reverse label, and an optional notes field.

### Rationale

Items in fiction have meaningful connections to characters, locations, and other items — an item may be owned by a character, found in a location, or related to another object. The labels are free-form text entered by the author with no predefined set of relationship types.

### Acceptance Criteria

```gherkin
@T-FUNC-0610.01.01
Scenario: Successfully define a relationship between an item and a character
  Given I have a novel with an item and a character
  And I am on the details page of the item
  When I add a relationship to the character
  And I enter a forward label of "owned by"
  And I enter a reverse label of "owns"
  And I click the Save button
  Then the relationship is created
  And it is displayed on the item's details page with the label "owned by"
  And it is displayed on the character's details page with the label "owns"

@T-FUNC-0610.01.02
Scenario: Successfully define a relationship between two items
  Given I have a novel with two items
  And I am on the details page of the first item
  When I add a relationship to the second item
  And I enter a forward label of "part of"
  And I enter a reverse label of "contains"
  And I click the Save button
  Then the relationship is created
  And it is displayed on the first item's details page with the label "part of"
  And it is displayed on the second item's details page with the label "contains"
```

### Verification Method

Manual Test

## R-FUNC-0610.02 Relationships are displayed on both participating entities

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0610](/features/06-item-management/#feat-0610-item-relationships) |

### Statement

The system SHALL display all relationships in which an item participates on that item's details page, showing the appropriate directional label for each relationship from that item's perspective. The relationship SHALL also be displayed on the other participating entity's details page with the reverse label.

### Rationale

An author viewing an item's profile needs to see all of that item's connections in one place, labelled from that item's point of view. Both ends of the relationship must be discoverable from either entity's page.

### Acceptance Criteria

```gherkin
@T-FUNC-0610.02.01
Scenario: Relationship appears on both participating entities' pages with correct labels
  Given a relationship exists between an item and a location
  And the forward label is "found in" and the reverse label is "contains"
  When I view the item's details page
  Then I see the relationship to the location labelled "found in"
  When I view the location's details page
  Then I see the relationship to the item labelled "contains"
```

### Verification Method

Manual Test

## R-FUNC-0610.03 Edit a relationship from either participating entity's page

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0610](/features/06-item-management/#feat-0610-item-relationships) |

### Statement

The system SHALL allow the user to edit a relationship from either participating entity's details page, including the forward label, reverse label, and notes.

### Rationale

Relationship descriptions may evolve as the author develops the story. Edits must be possible from either entity's page to avoid unnecessary navigation.

### Acceptance Criteria

```gherkin
@T-FUNC-0610.03.01
Scenario: Successfully edit a relationship from the item's page
  Given a relationship exists between an item and a character
  And I am on the details page of the item
  When I edit the relationship and change the forward label
  And I click the Save button
  Then the updated label is displayed on both the item's and the character's details pages
```

### Verification Method

Manual Test

## R-FUNC-0610.04 Delete a relationship from either participating entity's page

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0610](/features/06-item-management/#feat-0610-item-relationships) |

### Statement

The system SHALL allow the user to delete a relationship from either participating entity's details page.

### Rationale

Relationships that are no longer relevant to the story should be removable without deleting either of the participating entities.

### Acceptance Criteria

```gherkin
@T-FUNC-0610.04.01
Scenario: Successfully delete a relationship from the item's page
  Given a relationship exists between an item and a location
  And I am on the details page of the item
  When I delete the relationship
  Then the relationship no longer appears on the item's details page
  And the relationship no longer appears on the location's details page
  And both the item and the location still exist
```

### Verification Method

Manual Test

## R-DATA-0610.01 Deleting an item removes all its relationships

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0610](/features/06-item-management/#feat-0610-item-relationships) |

### Statement

When an item is deleted the system SHALL also delete all relationships in which that item participates.

### Rationale

A relationship cannot exist without both of its participants. Leaving orphaned relationship records when an item is deleted would create data inconsistencies and confusing displays on the remaining entity's page.

### Acceptance Criteria

```gherkin
@T-DATA-0610.01.01
Scenario: Relationships are removed when an item is deleted
  Given a relationship exists between an item and a character
  When the item is deleted
  Then the relationship no longer appears on the character's details page
```

### Verification Method

Manual Test
