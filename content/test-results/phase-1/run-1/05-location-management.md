---
title: "05 Location Management"
description: "Test execution records for location profiles and relationships"
draft: false
revision: "1.0"
revision_date: "18-Apr-2026"
---

## R-FUNC-0501.01 Location list board displays all locations

**Scenario:** Locations are displayed as cards on the board

{{< test-results id="T-FUNC-0501.01.01" file="05-location-management" >}}

**Scenario:** Archived locations do not appear on the location list board

{{< test-results id="T-FUNC-0501.01.02" file="05-location-management" >}}

## R-UI-0501.01 Location list board has no parent summary section

**Scenario:** No parent summary section is shown on the location list board

{{< test-results id="T-UI-0501.01.01" file="05-location-management" >}}

## R-UI-0501.02 Location card displays the location image

**Scenario:** Location image is displayed on the card when one has been uploaded

{{< test-results id="T-UI-0501.02.01" file="05-location-management" >}}

**Scenario:** Location card displays no image when none has been uploaded

{{< test-results id="T-UI-0501.02.02" file="05-location-management" >}}

## R-FUNC-0502.01 Create a location

**Scenario:** Successfully create a location

{{< test-results id="T-FUNC-0502.01.01" file="05-location-management" >}}

**Scenario:** Attempt to create a location without a name

{{< test-results id="T-FUNC-0502.01.02" file="05-location-management" >}}

## R-UI-0502.01 Add location form presents all required fields

**Scenario:** Add location form presents all required fields

{{< test-results id="T-UI-0502.01.01" file="05-location-management" >}}

## R-FUNC-0502.02 Upload a location image

**Scenario:** Successfully upload a location image on the add location page

{{< test-results id="T-FUNC-0502.02.01" file="05-location-management" >}}

**Scenario:** Successfully upload a location image on the edit location page

{{< test-results id="T-FUNC-0502.02.02" file="05-location-management" >}}

**Scenario:** Successfully replace an existing location image

{{< test-results id="T-FUNC-0502.02.03" file="05-location-management" >}}

## R-FUNC-0502.03 Add a location type value

**Scenario:** Successfully add a new location type value

{{< test-results id="T-FUNC-0502.03.01" file="05-location-management" >}}

**Scenario:** Type values are scoped to the current novel

{{< test-results id="T-FUNC-0502.03.02" file="05-location-management" >}}

## R-FUNC-0502.04 Rename a location type value

**Scenario:** Successfully rename a location type value

{{< test-results id="T-FUNC-0502.04.01" file="05-location-management" >}}

## R-FUNC-0502.05 Delete a location type value

**Scenario:** Successfully delete a location type value

{{< test-results id="T-FUNC-0502.05.01" file="05-location-management" >}}

**Scenario:** Deleting a type value does not delete assigned locations

{{< test-results id="T-FUNC-0502.05.02" file="05-location-management" >}}

## R-SEC-0502.01 Location image upload restricted to PNG and JPEG formats

**Scenario:** PNG file is accepted for location image upload

{{< test-results id="T-SEC-0502.01.01" file="05-location-management" >}}

**Scenario:** JPG file is accepted for location image upload

{{< test-results id="T-SEC-0502.01.02" file="05-location-management" >}}

**Scenario:** JPEG file is accepted for location image upload

{{< test-results id="T-SEC-0502.01.03" file="05-location-management" >}}

**Scenario:** File with unsupported extension is rejected

{{< test-results id="T-SEC-0502.01.04" file="05-location-management" >}}

## R-FUNC-0503.01 Save and cancel when editing a location

**Scenario:** Successfully save changes to a location

{{< test-results id="T-FUNC-0503.01.01" file="05-location-management" >}}

**Scenario:** Cancel editing a location

{{< test-results id="T-FUNC-0503.01.02" file="05-location-management" >}}

## R-UI-0503.01 Edit location form displays appears in scenes as read-only

**Scenario:** Appears in scenes is displayed as read-only on the edit location page

{{< test-results id="T-UI-0503.01.01" file="05-location-management" >}}

## R-FUNC-0510.01 Define a relationship between a location and any planning entity

**Scenario:** Successfully define a relationship between a location and a character

{{< test-results id="T-FUNC-0510.01.01" file="05-location-management" >}}

**Scenario:** Successfully define a relationship between two locations

{{< test-results id="T-FUNC-0510.01.02" file="05-location-management" >}}

## R-FUNC-0510.02 Relationships are displayed on both participating entities

**Scenario:** Relationship appears on both participating entities' pages with correct labels

{{< test-results id="T-FUNC-0510.02.01" file="05-location-management" >}}

## R-FUNC-0510.03 Edit a relationship from either participating entity's page

**Scenario:** Successfully edit a relationship from the location's page

{{< test-results id="T-FUNC-0510.03.01" file="05-location-management" >}}

## R-FUNC-0510.04 Delete a relationship from either participating entity's page

**Scenario:** Successfully delete a relationship from the location's page

{{< test-results id="T-FUNC-0510.04.01" file="05-location-management" >}}

## R-DATA-0510.01 Deleting a location removes all its relationships

**Scenario:** Relationships are removed when a location is deleted

{{< test-results id="T-DATA-0510.01.01" file="05-location-management" >}}
