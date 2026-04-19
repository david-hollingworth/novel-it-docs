---
title: "07 World Building"
description: "Test execution records for world building item profiles and relationships"
draft: false
---

## R-FUNC-0701.01 World building list board displays all world building items

**Scenario:** World building items are displayed as cards on the board

{{< test-results id="T-FUNC-0701.01.01" file="07-world-building" >}}

**Scenario:** Archived world building items do not appear on the world building list board

{{< test-results id="T-FUNC-0701.01.02" file="07-world-building" >}}

## R-UI-0701.01 World building list board has no parent summary section

**Scenario:** No parent summary section is shown on the world building list board

{{< test-results id="T-UI-0701.01.01" file="07-world-building" >}}

## R-UI-0701.02 World building item card displays the item image

**Scenario:** Image is displayed on the card when one has been uploaded

{{< test-results id="T-UI-0701.02.01" file="07-world-building" >}}

**Scenario:** Card displays no image when none has been uploaded

{{< test-results id="T-UI-0701.02.02" file="07-world-building" >}}

## R-FUNC-0702.01 Create a world building item

**Scenario:** Successfully create a world building item

{{< test-results id="T-FUNC-0702.01.01" file="07-world-building" >}}

**Scenario:** Attempt to create a world building item without a name

{{< test-results id="T-FUNC-0702.01.02" file="07-world-building" >}}

## R-UI-0702.01 Add world building item form presents all required fields

**Scenario:** Add world building item form presents all required fields

{{< test-results id="T-UI-0702.01.01" file="07-world-building" >}}

## R-FUNC-0702.02 Upload a world building item image

**Scenario:** Successfully upload an image on the add world building item page

{{< test-results id="T-FUNC-0702.02.01" file="07-world-building" >}}

**Scenario:** Successfully upload an image on the edit world building item page

{{< test-results id="T-FUNC-0702.02.02" file="07-world-building" >}}

**Scenario:** Successfully replace an existing world building item image

{{< test-results id="T-FUNC-0702.02.03" file="07-world-building" >}}

## R-FUNC-0702.03 Add a world building type value

**Scenario:** Successfully add a new world building type value

{{< test-results id="T-FUNC-0702.03.01" file="07-world-building" >}}

**Scenario:** Type values are scoped to the current novel

{{< test-results id="T-FUNC-0702.03.02" file="07-world-building" >}}

## R-FUNC-0702.04 Rename a world building type value

**Scenario:** Successfully rename a world building type value

{{< test-results id="T-FUNC-0702.04.01" file="07-world-building" >}}

## R-FUNC-0702.05 Delete a world building type value

**Scenario:** Successfully delete a world building type value

{{< test-results id="T-FUNC-0702.05.01" file="07-world-building" >}}

**Scenario:** Deleting a type value does not delete assigned world building items

{{< test-results id="T-FUNC-0702.05.02" file="07-world-building" >}}

## R-SEC-0702.01 World building item image upload restricted to PNG and JPEG formats

**Scenario:** PNG file is accepted for world building item image upload

{{< test-results id="T-SEC-0702.01.01" file="07-world-building" >}}

**Scenario:** JPG file is accepted for world building item image upload

{{< test-results id="T-SEC-0702.01.02" file="07-world-building" >}}

**Scenario:** JPEG file is accepted for world building item image upload

{{< test-results id="T-SEC-0702.01.03" file="07-world-building" >}}

**Scenario:** File with unsupported extension is rejected

{{< test-results id="T-SEC-0702.01.04" file="07-world-building" >}}

## R-FUNC-0703.01 Save and cancel when editing a world building item

**Scenario:** Successfully save changes to a world building item

{{< test-results id="T-FUNC-0703.01.01" file="07-world-building" >}}

**Scenario:** Cancel editing a world building item

{{< test-results id="T-FUNC-0703.01.02" file="07-world-building" >}}

## R-UI-0703.01 Edit world building item form displays appears in scenes as read-only

**Scenario:** Appears in scenes is displayed as read-only on the edit world building item page

{{< test-results id="T-UI-0703.01.01" file="07-world-building" >}}

## R-FUNC-0710.01 Define a relationship between a world building item and any planning entity

**Scenario:** Successfully define a relationship between a world building item and a character

{{< test-results id="T-FUNC-0710.01.01" file="07-world-building" >}}

**Scenario:** Successfully define a relationship between two world building items

{{< test-results id="T-FUNC-0710.01.02" file="07-world-building" >}}

## R-FUNC-0710.02 Relationships are displayed on both participating entities

**Scenario:** Relationship appears on both participating entities' pages with correct labels

{{< test-results id="T-FUNC-0710.02.01" file="07-world-building" >}}

## R-FUNC-0710.03 Edit a relationship from either participating entity's page

**Scenario:** Successfully edit a relationship from the world building item's page

{{< test-results id="T-FUNC-0710.03.01" file="07-world-building" >}}

## R-FUNC-0710.04 Delete a relationship from either participating entity's page

**Scenario:** Successfully delete a relationship from the world building item's page

{{< test-results id="T-FUNC-0710.04.01" file="07-world-building" >}}

## R-DATA-0710.01 Deleting a world building item removes all its relationships

**Scenario:** Relationships are removed when a world building item is deleted

{{< test-results id="T-DATA-0710.01.01" file="07-world-building" >}}
