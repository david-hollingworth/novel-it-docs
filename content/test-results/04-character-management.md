---
title: "04 Character Management"
description: "Test execution records for character profiles and relationships"
draft: false
---

## R-FUNC-0401.01 Character list board displays all characters

**Scenario:** Characters are displayed as cards on the board

{{< test-results id="T-FUNC-0401.01.01" file="04-character-management" >}}

**Scenario:** Archived characters do not appear on the character list board

{{< test-results id="T-FUNC-0401.01.02" file="04-character-management" >}}

## R-UI-0401.01 Character list board has no parent summary section

**Scenario:** No parent summary section is shown on the character list board

{{< test-results id="T-UI-0401.01.01" file="04-character-management" >}}

## R-UI-0401.02 Character card displays the character image

**Scenario:** Character image is displayed on the card when one has been uploaded

{{< test-results id="T-UI-0401.02.01" file="04-character-management" >}}

**Scenario:** Character card displays no image when none has been uploaded

{{< test-results id="T-UI-0401.02.02" file="04-character-management" >}}

## R-FUNC-0402.01 Save and cancel when editing a character

**Scenario:** Successfully save changes to a character

{{< test-results id="T-FUNC-0402.01.01" file="04-character-management" >}}

**Scenario:** Cancel editing a character

{{< test-results id="T-FUNC-0402.01.02" file="04-character-management" >}}

## R-UI-0402.01 Edit character form displays appears in scenes as read-only

**Scenario:** Appears in scenes is displayed as read-only on the edit character page

{{< test-results id="T-UI-0402.01.01" file="04-character-management" >}}

## R-FUNC-0403.01 Create a character

**Scenario:** Successfully create a character

{{< test-results id="T-FUNC-0403.01.01" file="04-character-management" >}}

**Scenario:** Attempt to create a character without a full name

{{< test-results id="T-FUNC-0403.01.02" file="04-character-management" >}}

## R-UI-0403.01 Add character form presents all required fields

**Scenario:** Add character form presents all required fields

{{< test-results id="T-UI-0403.01.01" file="04-character-management" >}}

## R-FUNC-0403.02 Upload a character image

**Scenario:** Successfully upload a character image on the add character page

{{< test-results id="T-FUNC-0403.02.01" file="04-character-management" >}}

**Scenario:** Successfully upload a character image on the edit character page

{{< test-results id="T-FUNC-0403.02.02" file="04-character-management" >}}

**Scenario:** Successfully replace an existing character image

{{< test-results id="T-FUNC-0403.02.03" file="04-character-management" >}}

## R-FUNC-0403.03 Add a character role value

**Scenario:** Successfully add a new character role value

{{< test-results id="T-FUNC-0403.03.01" file="04-character-management" >}}

**Scenario:** Role values are scoped to the current novel

{{< test-results id="T-FUNC-0403.03.02" file="04-character-management" >}}

## R-FUNC-0403.04 Rename a character role value

**Scenario:** Successfully rename a character role value

{{< test-results id="T-FUNC-0403.04.01" file="04-character-management" >}}

## R-FUNC-0403.05 Delete a character role value

**Scenario:** Successfully delete a character role value

{{< test-results id="T-FUNC-0403.05.01" file="04-character-management" >}}

**Scenario:** Deleting a role value does not delete assigned characters

{{< test-results id="T-FUNC-0403.05.02" file="04-character-management" >}}

## R-SEC-0403.01 Character image upload restricted to PNG and JPEG formats

**Scenario:** PNG file is accepted for character image upload

{{< test-results id="T-SEC-0403.01.01" file="04-character-management" >}}

**Scenario:** JPG file is accepted for character image upload

{{< test-results id="T-SEC-0403.01.02" file="04-character-management" >}}

**Scenario:** JPEG file is accepted for character image upload

{{< test-results id="T-SEC-0403.01.03" file="04-character-management" >}}

**Scenario:** File with unsupported extension is rejected

{{< test-results id="T-SEC-0403.01.04" file="04-character-management" >}}

## R-FUNC-0410.01 Define a relationship between a character and any planning entity

**Scenario:** Successfully define a relationship between two characters

{{< test-results id="T-FUNC-0410.01.01" file="04-character-management" >}}

**Scenario:** Successfully define a relationship between a character and an item

{{< test-results id="T-FUNC-0410.01.02" file="04-character-management" >}}

## R-FUNC-0410.02 Relationships are displayed on both participating entities

**Scenario:** Relationship appears on both participating entities' pages with correct labels

{{< test-results id="T-FUNC-0410.02.01" file="04-character-management" >}}

## R-FUNC-0410.03 Edit a relationship from either participating entity's page

**Scenario:** Successfully edit a relationship from one entity's page

{{< test-results id="T-FUNC-0410.03.01" file="04-character-management" >}}

## R-FUNC-0410.04 Delete a relationship from either participating entity's page

**Scenario:** Successfully delete a relationship

{{< test-results id="T-FUNC-0410.04.01" file="04-character-management" >}}

## R-DATA-0410.01 Deleting a character removes all its relationships

**Scenario:** Relationships are removed when a character is deleted

{{< test-results id="T-DATA-0410.01.01" file="04-character-management" >}}
