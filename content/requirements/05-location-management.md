---
title: "05 Location Management"
description: "Requirements for location profiles and relationships"
draft: false
revision: "2.0"
revision_date: "20-Apr-2026"
---

*Phase 2 and 4 features (FEAT-0504 Archive location, FEAT-0505 Unarchive location, FEAT-0506 Delete location, FEAT-0507 Duplicate location, FEAT-0508 Location relocation, FEAT-0509 Location sharing) are out of scope for this pass and have no requirements entries here.*

## R-FUNC-0501.01 Location list board displays all locations

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0501](/novel-it-docs/features/05-location-management/#feat-0501-location-list-board) |

### Statement

The system SHALL display all non-archived locations belonging to the current novel as cards on the location list board.

### Rationale

The location list board is the primary navigation view for location management. All active locations must be viewable and accessible from this board.

### Acceptance Criteria

```gherkin
@T-FUNC-0501.01.01
Scenario: Locations are displayed as cards on the board
  Given I have a novel with three locations
  When I navigate to the location list board
  Then I see three location cards displayed

@T-FUNC-0501.01.02
Scenario: Archived locations do not appear on the location list board
  Given I have a novel with one active location and one archived location
  When I navigate to the location list board
  Then I see only the active location
  And I do not see the archived location
```

### Verification Method

Manual Test

## R-UI-0501.01 Location list board has no parent summary section

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0501](/features/05-location-management/#feat-0501-location-list-board) |

### Statement

The location list board SHALL NOT display a parent summary section.

### Rationale

Locations have no subordinate entities of their own and are not children of a named parent entity. A parent summary section would be meaningless on this board.

### Acceptance Criteria

```gherkin
@T-UI-0501.01.01
Scenario: No parent summary section is shown on the location list board
  Given I have a novel with at least one location
  When I navigate to the location list board
  Then I do not see a parent summary section
  And I see only the location cards
```

### Verification Method

Manual Test

## R-FUNC-0502.01 Create a location

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0502](/novel-it-docs/features/05-location-management/#feat-0502-add-location) |

### Statement

The system SHALL allow the user to create a location belonging to the current novel.

### Rationale

Locations are a core planning entity for narrative fiction. Authors need to be able to create and store location profiles within the context of a specific novel.

### Acceptance Criteria

```gherkin
@T-FUNC-0502.01.01
Scenario: Successfully create a location
  Given I have an existing novel
  And I am on the location list board
  When I click the Add Location button
  And I enter a location name
  And I click the Save button
  Then the location is created
  And it appears on the location list board

@T-FUNC-0502.01.02
Scenario: Attempt to create a location without a name
  Given I am on the add location page
  When I click the Save button without entering a location name
  Then the location is not created
  And I see an error message indicating that a location name is required
```

### Verification Method

Manual Test

## R-UI-0502.01 Add location form presents all required fields

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0502](/features/05-location-management/#feat-0502-add-location) |

### Statement

The add location form SHALL present the following fields: location name, location type, description, notes, and image.

### Rationale

All specified location properties must be available for input when a location is created.

### Acceptance Criteria

```gherkin
@T-UI-0502.01.01
Scenario: Add location form presents all required fields
  Given I have an existing novel
  When I click the Add Location button
  Then the add location form displays fields for: location name, location type, description, notes, and image
```

### Verification Method

Manual Test

## R-UI-0501.02 Location card displays the location image

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0501](/features/05-location-management/#feat-0501-location-list-board) |

### Statement

Where a location image has been uploaded, the location's card on the list board SHALL display that image.

### Rationale

A visual representation of a location on the list board helps the author quickly identify locations, particularly in novels with large numbers of settings.

### Acceptance Criteria

```gherkin
@T-UI-0501.02.01
Scenario: Location image is displayed on the card when one has been uploaded
  Given I have a location with an uploaded image
  When I view the location list board
  Then the location's card displays the uploaded image

@T-UI-0501.02.02
Scenario: Location card displays no image when none has been uploaded
  Given I have a location with no uploaded image
  When I view the location list board
  Then the location's card does not display an image
```

### Verification Method

Manual Test

## R-FUNC-0502.02 Upload a location image

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0502](/features/05-location-management/#feat-0502-add-location) |

### Statement

The system SHALL allow the user to upload an image for a location from both the add location and edit location pages. The uploaded image SHALL be stored and associated with the location.

### Rationale

A location image provides a visual reference that helps the author maintain consistency when writing descriptions and setting scenes.

### Acceptance Criteria

```gherkin
@T-FUNC-0502.02.01
Scenario: Successfully upload a location image on the add location page
  Given I am on the add location page
  When I upload an image file using the image field
  And I click the Save button
  Then the location is created with the uploaded image associated
  And the image is displayed on the location's edit page

@T-FUNC-0502.02.02
Scenario: Successfully upload a location image on the edit location page
  Given I have an existing location with no image
  And I am on the edit location page
  When I upload an image file using the image field
  And I click the Save button
  Then the uploaded image is associated with the location
  And the image is displayed on the location's edit page

@T-FUNC-0502.02.03
Scenario: Successfully replace an existing location image
  Given I have an existing location with an uploaded image
  And I am on the edit location page
  When I upload a new image file using the image field
  And I click the Save button
  Then the new image replaces the previous image
```

### Verification Method

Manual Test

## R-SEC-0502.01 Location image upload restricted to PNG and JPEG formats

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0502](/features/05-location-management/#feat-0502-add-location) |

### Statement

The system SHALL only accept image files with the extensions `.png`, `.jpg`, or `.jpeg` for location image upload. Any other file type SHALL be rejected and the user SHALL be shown an informative error message.

### Rationale

Restricting accepted formats to PNG and JPEG limits the attack surface for malicious file uploads and avoids server-side complexity in handling varied image formats. Both formats are natively supported in all target browsers without additional processing.

### Acceptance Criteria

```gherkin
@T-SEC-0502.01.01
Scenario: PNG file is accepted for location image upload
  Given I am on the add location page
  When I upload a file with the extension .png
  Then the file is accepted

@T-SEC-0502.01.02
Scenario: JPG file is accepted for location image upload
  Given I am on the add location page
  When I upload a file with the extension .jpg
  Then the file is accepted

@T-SEC-0502.01.03
Scenario: JPEG file is accepted for location image upload
  Given I am on the add location page
  When I upload a file with the extension .jpeg
  Then the file is accepted

@T-SEC-0502.01.04
Scenario: File with unsupported extension is rejected
  Given I am on the add location page
  When I attempt to upload a file with an extension other than .png, .jpg, or .jpeg
  Then the file is rejected
  And I see an error message indicating that only PNG and JPEG files are accepted
```

### Verification Method

Manual Test

## R-FUNC-0502.03 Add a location type value

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0502](/features/05-location-management/#feat-0502-add-location) |

### Statement

The system SHALL allow the user to add new location type values from within the location form. New type values SHALL be scoped to the current novel and SHALL become immediately available for selection.

### Rationale

Location types are novel-specific and cannot be defined in advance by the application. The author must be able to define types that are meaningful to their particular world without leaving the location form.

### Acceptance Criteria

```gherkin
@T-FUNC-0502.03.01
Scenario: Successfully add a new location type value
  Given I am on the location form for a novel
  When I open the type manager
  And I enter a new type name
  And I click the Add button
  Then the new type value is saved
  And it is immediately available for selection in the type field

@T-FUNC-0502.03.02
Scenario: Type values are scoped to the current novel
  Given I have added a type value to Novel A
  When I open the location form for Novel B
  Then the type value from Novel A is not available in Novel B's type field
```

### Verification Method

Manual Test

## R-FUNC-0502.04 Rename a location type value

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0502](/features/05-location-management/#feat-0502-add-location) |

### Statement

The system SHALL allow the user to rename an existing location type value from within the location form. The renamed value SHALL be reflected immediately wherever it is displayed.

### Rationale

Type names may need to evolve as the author develops their world. Renaming must be possible without losing the association between the type and any locations already assigned to it.

### Acceptance Criteria

```gherkin
@T-FUNC-0502.04.01
Scenario: Successfully rename a location type value
  Given a location type value exists
  And I am on the location form
  When I open the type manager
  And I rename the type value
  And I click the Save button
  Then the type value is updated
  And any locations assigned to that type display the new name
```

### Verification Method

Manual Test

## R-FUNC-0502.05 Delete a location type value

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0502](/features/05-location-management/#feat-0502-add-location) |

### Statement

The system SHALL allow the user to delete an existing location type value from within the location form. Deleting a type value SHALL NOT delete any locations assigned to that type; those locations SHALL have their type field set to empty.

### Rationale

Type values that are no longer relevant should be removable without data loss. The relationship between a location and a type is optional, so removing the type value simply clears the field on affected locations.

### Acceptance Criteria

```gherkin
@T-FUNC-0502.05.01
Scenario: Successfully delete a location type value
  Given a location type value exists
  And I am on the location form
  When I open the type manager
  And I delete the type value
  Then the type value is removed from the available options

@T-FUNC-0502.05.02
Scenario: Deleting a type value does not delete assigned locations
  Given a location type value exists
  And one or more locations are assigned to that type
  When I delete the type value
  Then the locations assigned to that type are not deleted
  And those locations have no type assigned
```

### Verification Method

Manual Test

## R-FUNC-0503.01 Save and cancel when editing a location

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0503](/novel-it-docs/features/05-location-management/#feat-0503-edit-location) |

### Statement

The system SHALL allow the user to save changes to a location's properties and SHALL allow the user to cancel without saving, discarding any changes made.

### Rationale

Location properties need to be updatable as the author develops their world. The cancel function protects the user from inadvertently overwriting existing values.

### Acceptance Criteria

```gherkin
@T-FUNC-0503.01.01
Scenario: Successfully save changes to a location
  Given I have an existing location
  And I am on the edit location page
  When I change the location name
  And I click the Save button
  Then the location is updated
  And the new name is displayed on the location list board

@T-FUNC-0503.01.02
Scenario: Cancel editing a location
  Given I have an existing location
  And I am on the edit location page
  When I change the location name
  And I click the Cancel button
  Then the location is not updated
  And the original name is retained
```

### Verification Method

Manual Test

## R-UI-0503.01 Edit location form displays appears in scenes as read-only

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0503](/features/05-location-management/#feat-0503-edit-location) |

### Statement

The edit location form SHALL display the appears in scenes field as a read-only calculated value that cannot be edited directly by the user.

### Rationale

The appears in scenes field is populated automatically by the cross-referencing feature when scenes are saved. It must be visible to the author as useful reference information, but must not be editable as it would then diverge from the actual scene content.

### Acceptance Criteria

```gherkin
@T-UI-0503.01.01
Scenario: Appears in scenes is displayed as read-only on the edit location page
  Given I have an existing location
  When I navigate to the edit location page
  Then the appears in scenes field is displayed
  And it is not editable
```

### Verification Method

Manual Test

## R-FUNC-0510.01 Define a relationship between a location and any planning entity

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0510](/novel-it-docs/features/05-location-management/#feat-0510-location-relationships) |

### Statement

The system SHALL allow the user to define a relationship between a location and any other planning entity within the same novel. Each relationship SHALL have a forward label, a reverse label, and an optional notes field.

### Rationale

Locations in fiction have meaningful connections to characters, items, and other locations — a location may be inhabited by a character, contain an item, or border another location. The labels are free-form text entered by the author with no predefined set of relationship types.

### Acceptance Criteria

```gherkin
@T-FUNC-0510.01.01
Scenario: Successfully define a relationship between a location and a character
  Given I have a novel with a location and a character
  And I am on the details page of the location
  When I add a relationship to the character
  And I enter a forward label of "inhabited by"
  And I enter a reverse label of "inhabits"
  And I click the Save button
  Then the relationship is created
  And it is displayed on the location's details page with the label "inhabited by"
  And it is displayed on the character's details page with the label "inhabits"

@T-FUNC-0510.01.02
Scenario: Successfully define a relationship between two locations
  Given I have a novel with two locations
  And I am on the details page of the first location
  When I add a relationship to the second location
  And I enter a forward label of "borders"
  And I enter a reverse label of "bordered by"
  And I click the Save button
  Then the relationship is created
  And it is displayed on the first location's details page with the label "borders"
  And it is displayed on the second location's details page with the label "bordered by"
```

### Verification Method

Manual Test

## R-FUNC-0510.02 Relationships are displayed on both participating entities

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0510](/features/05-location-management/#feat-0510-location-relationships) |

### Statement

The system SHALL display all relationships in which a location participates on that location's details page, showing the appropriate directional label for each relationship from that location's perspective. The relationship SHALL also be displayed on the other participating entity's details page with the reverse label.

### Rationale

An author viewing a location's profile needs to see all of that location's connections in one place, labelled from that location's point of view. Both ends of the relationship must be discoverable from either entity's page.

### Acceptance Criteria

```gherkin
@T-FUNC-0510.02.01
Scenario: Relationship appears on both participating entities' pages with correct labels
  Given a relationship exists between a location and a character
  And the forward label is "inhabited by" and the reverse label is "inhabits"
  When I view the location's details page
  Then I see the relationship to the character labelled "inhabited by"
  When I view the character's details page
  Then I see the relationship to the location labelled "inhabits"
```

### Verification Method

Manual Test

## R-FUNC-0510.03 Edit a relationship from either participating entity's page

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0510](/features/05-location-management/#feat-0510-location-relationships) |

### Statement

The system SHALL allow the user to edit a relationship from either participating entity's details page, including the forward label, reverse label, and notes.

### Rationale

Relationship descriptions may evolve as the author develops the story. Edits must be possible from either entity's page to avoid unnecessary navigation.

### Acceptance Criteria

```gherkin
@T-FUNC-0510.03.01
Scenario: Successfully edit a relationship from the location's page
  Given a relationship exists between a location and an item
  And I am on the details page of the location
  When I edit the relationship and change the forward label
  And I click the Save button
  Then the updated label is displayed on both the location's and the item's details pages
```

### Verification Method

Manual Test

## R-FUNC-0510.04 Delete a relationship from either participating entity's page

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0510](/features/05-location-management/#feat-0510-location-relationships) |

### Statement

The system SHALL allow the user to delete a relationship from either participating entity's details page.

### Rationale

Relationships that are no longer relevant to the story should be removable without deleting either of the participating entities.

### Acceptance Criteria

```gherkin
@T-FUNC-0510.04.01
Scenario: Successfully delete a relationship from the location's page
  Given a relationship exists between a location and a character
  And I am on the details page of the location
  When I delete the relationship
  Then the relationship no longer appears on the location's details page
  And the relationship no longer appears on the character's details page
  And both the location and the character still exist
```

### Verification Method

Manual Test

## R-DATA-0510.01 Deleting a location removes all its relationships

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0510](/features/05-location-management/#feat-0510-location-relationships) |

### Statement

When a location is deleted the system SHALL also delete all relationships in which that location participates.

### Rationale

A relationship cannot exist without both of its participants. Leaving orphaned relationship records when a location is deleted would create data inconsistencies and confusing displays on the remaining entity's page.

### Acceptance Criteria

```gherkin
@T-DATA-0510.01.01
Scenario: Relationships are removed when a location is deleted
  Given a relationship exists between a location and a character
  When the location is deleted
  Then the relationship no longer appears on the character's details page
```

### Verification Method

Manual Test
