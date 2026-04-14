---
title: "06 Item Management"
description: "Test execution records for item profiles and relationships"
draft: false
---

## R-FUNC-0601.01 Item list board displays all items

**Scenario:** Items are displayed as cards on the board

{{< test-results id="T-FUNC-0601.01.01" file="06-item-management" >}}

**Scenario:** Archived items do not appear on the item list board

{{< test-results id="T-FUNC-0601.01.02" file="06-item-management" >}}

## R-UI-0601.01 Item list board has no parent summary section

**Scenario:** No parent summary section is shown on the item list board

{{< test-results id="T-UI-0601.01.01" file="06-item-management" >}}

## R-UI-0601.02 Item card displays the item image

**Scenario:** Item image is displayed on the card when one has been uploaded

{{< test-results id="T-UI-0601.02.01" file="06-item-management" >}}

**Scenario:** Item card displays no image when none has been uploaded

{{< test-results id="T-UI-0601.02.02" file="06-item-management" >}}

## R-FUNC-0602.01 Create an item

**Scenario:** Successfully create an item

{{< test-results id="T-FUNC-0602.01.01" file="06-item-management" >}}

**Scenario:** Attempt to create an item without a name

{{< test-results id="T-FUNC-0602.01.02" file="06-item-management" >}}

## R-UI-0602.01 Add item form presents all required fields

**Scenario:** Add item form presents all required fields

{{< test-results id="T-UI-0602.01.01" file="06-item-management" >}}

## R-FUNC-0602.02 Upload an item image

**Scenario:** Successfully upload an item image on the add item page

{{< test-results id="T-FUNC-0602.02.01" file="06-item-management" >}}

**Scenario:** Successfully upload an item image on the edit item page

{{< test-results id="T-FUNC-0602.02.02" file="06-item-management" >}}

**Scenario:** Successfully replace an existing item image

{{< test-results id="T-FUNC-0602.02.03" file="06-item-management" >}}

## R-FUNC-0602.03 Add an item type value

**Scenario:** Successfully add a new item type value

{{< test-results id="T-FUNC-0602.03.01" file="06-item-management" >}}

**Scenario:** Type values are scoped to the current novel

{{< test-results id="T-FUNC-0602.03.02" file="06-item-management" >}}

## R-FUNC-0602.04 Rename an item type value

**Scenario:** Successfully rename an item type value

{{< test-results id="T-FUNC-0602.04.01" file="06-item-management" >}}

## R-FUNC-0602.05 Delete an item type value

**Scenario:** Successfully delete an item type value

{{< test-results id="T-FUNC-0602.05.01" file="06-item-management" >}}

**Scenario:** Deleting a type value does not delete assigned items

{{< test-results id="T-FUNC-0602.05.02" file="06-item-management" >}}

## R-SEC-0602.01 Item image upload restricted to PNG and JPEG formats

**Scenario:** PNG file is accepted for item image upload

{{< test-results id="T-SEC-0602.01.01" file="06-item-management" >}}

**Scenario:** JPG file is accepted for item image upload

{{< test-results id="T-SEC-0602.01.02" file="06-item-management" >}}

**Scenario:** JPEG file is accepted for item image upload

{{< test-results id="T-SEC-0602.01.03" file="06-item-management" >}}

**Scenario:** File with unsupported extension is rejected

{{< test-results id="T-SEC-0602.01.04" file="06-item-management" >}}

## R-FUNC-0603.01 Save and cancel when editing an item

**Scenario:** Successfully save changes to an item

{{< test-results id="T-FUNC-0603.01.01" file="06-item-management" >}}

**Scenario:** Cancel editing an item

{{< test-results id="T-FUNC-0603.01.02" file="06-item-management" >}}

## R-UI-0603.01 Edit item form displays appears in scenes as read-only

**Scenario:** Appears in scenes is displayed as read-only on the edit item page

{{< test-results id="T-UI-0603.01.01" file="06-item-management" >}}

## R-FUNC-0610.01 Define a relationship between an item and any planning entity

**Scenario:** Successfully define a relationship between an item and a character

{{< test-results id="T-FUNC-0610.01.01" file="06-item-management" >}}

**Scenario:** Successfully define a relationship between two items

{{< test-results id="T-FUNC-0610.01.02" file="06-item-management" >}}

## R-FUNC-0610.02 Relationships are displayed on both participating entities

**Scenario:** Relationship appears on both participating entities' pages with correct labels

{{< test-results id="T-FUNC-0610.02.01" file="06-item-management" >}}

## R-FUNC-0610.03 Edit a relationship from either participating entity's page

**Scenario:** Successfully edit a relationship from the item's page

{{< test-results id="T-FUNC-0610.03.01" file="06-item-management" >}}

## R-FUNC-0610.04 Delete a relationship from either participating entity's page

**Scenario:** Successfully delete a relationship from the item's page

{{< test-results id="T-FUNC-0610.04.01" file="06-item-management" >}}

## R-DATA-0610.01 Deleting an item removes all its relationships

**Scenario:** Relationships are removed when an item is deleted

{{< test-results id="T-DATA-0610.01.01" file="06-item-management" >}}
