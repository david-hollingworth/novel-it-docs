---
title: "05 Location Management"
description: "Location database and tracking"
draft: false
---

## FEAT-0501 Create location

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

The user shall be able to create new locations. Locations shall have the following attributes:
- Location name
- Location type
- Description
- Notes
- Related To list
- Appears In scenes list

## FEAT-0502 Edit location

| | |
|---|---|
| **Status** | In Progress |
| **Phase** | 1 |

### Description

The user shall be able to click on a location's card on the location dashboard and edit the location's details.

## FEAT-0503 Archive location

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

### Description

From the location's details page the user shall be able to archive a location.

Archived locations do not appear on the location dashboard

## FEAT-0504 Unarchive location

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

### Description

From the location dashboard the user shall be able to display a list of archived locations and select locations to unarchive.

Once unarchived, the location shall appear on the location dashboard again.

## FEAT-0505 Delete location

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

### Description

- From the location's details page the user shall be able to delete a location.
- A warning shall be displayed that this is permanent
- When a location is deleted any manuscript that refers to the location remains unchanged

## FEAT-0506 location sharing

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 4 |

### Description

- The user can share a location amongst more than one novel
- From the location details page the user can add the additional novels that the location will appear in
- When the user opens the additional novels and navigates to locations then the location shall be displayed.
- If a shared location is edited then the edits appear in all novels where the location exists
- If a shared location is archived then it is archived for all novels
- If a shared location is deleted then it is deleted for all novels
