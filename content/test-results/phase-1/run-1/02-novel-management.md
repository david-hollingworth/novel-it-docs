---
title: "02 Novel Management"
description: "Test execution records for all novel structural functionality"
draft: false
revision: "1.0"
revision_date: "18-Apr-2026"
---

## R-FUNC-0201.01 Create a novel

**Scenario:** Successfully create a novel

{{< test-results id="T-FUNC-0201.01.01" file="02-novel-management" >}}

**Scenario:** Attempt to create a novel without a title

{{< test-results id="T-FUNC-0201.01.02" file="02-novel-management" >}}

## R-UI-0201.01 Add novel form presents all required fields

**Scenario:** Add novel form presents all required fields

{{< test-results id="T-UI-0201.01.01" file="02-novel-management" >}}

## R-FUNC-0201.02 Parts enabled flag defaults to No

**Scenario:** Parts enabled defaults to No on a new novel

{{< test-results id="T-FUNC-0201.02.01" file="02-novel-management" >}}

## R-FUNC-0202.01 Novel hierarchy — parts disabled

**Scenario:** Novel structure without parts

{{< test-results id="T-FUNC-0202.01.01" file="02-novel-management" >}}

## R-FUNC-0202.02 Novel hierarchy — parts enabled

**Scenario:** Novel structure with parts

{{< test-results id="T-FUNC-0202.02.01" file="02-novel-management" >}}

## R-UI-0203.01 Edit novel form presents all required fields

**Scenario:** Edit novel form presents all editable fields

{{< test-results id="T-UI-0203.01.01" file="02-novel-management" >}}

**Scenario:** Edit novel form displays actual word count as read-only

{{< test-results id="T-UI-0203.01.02" file="02-novel-management" >}}

## R-FUNC-0203.01 Edit novel properties

**Scenario:** Successfully edit a novel's properties

{{< test-results id="T-FUNC-0203.01.01" file="02-novel-management" >}}

**Scenario:** Cancel editing a novel

{{< test-results id="T-FUNC-0203.01.02" file="02-novel-management" >}}

## R-FUNC-0203.02 Enable and disable parts

**Scenario:** Enable parts on an existing novel

{{< test-results id="T-FUNC-0203.02.01" file="02-novel-management" >}}

**Scenario:** Disable parts on an existing novel

{{< test-results id="T-FUNC-0203.02.02" file="02-novel-management" >}}

## R-FUNC-0204.01 Archive a novel

**Scenario:** Successfully archive a novel

{{< test-results id="T-FUNC-0204.01.01" file="02-novel-management" >}}

**Scenario:** Cancel archiving a novel

{{< test-results id="T-FUNC-0204.01.02" file="02-novel-management" >}}

## R-FUNC-0205.01 Unarchive a novel

**Scenario:** Successfully unarchive a novel

{{< test-results id="T-FUNC-0205.01.01" file="02-novel-management" >}}

**Scenario:** Cancel unarchiving a novel

{{< test-results id="T-FUNC-0205.01.02" file="02-novel-management" >}}

## R-FUNC-0206.01 Delete a novel

**Scenario:** Successfully delete a novel

{{< test-results id="T-FUNC-0206.01.01" file="02-novel-management" >}}

**Scenario:** Cancel deleting a novel

{{< test-results id="T-FUNC-0206.01.02" file="02-novel-management" >}}

## R-DATA-0206.01 Novel deletion cascades to all child entities

**Scenario:** Child entities are deleted with the novel

{{< test-results id="T-DATA-0206.01.01" file="02-novel-management" >}}

## R-FUNC-0209.01 Novels displayed as cards on login

**Scenario:** Novels board displayed after login

{{< test-results id="T-FUNC-0209.01.01" file="02-novel-management" >}}

**Scenario:** Archived novels do not appear on the novels board

{{< test-results id="T-FUNC-0209.01.02" file="02-novel-management" >}}

## R-FUNC-0210.01 Navigate to novel structure display

**Scenario:** Navigate into a novel without parts

{{< test-results id="T-FUNC-0210.01.01" file="02-novel-management" >}}

**Scenario:** Navigate into a novel with parts

{{< test-results id="T-FUNC-0210.01.02" file="02-novel-management" >}}

## R-FUNC-0211.01 Create a part

**Scenario:** Successfully create a part

{{< test-results id="T-FUNC-0211.01.01" file="02-novel-management" >}}

**Scenario:** Successfully create a part and assign existing chapters

{{< test-results id="T-FUNC-0211.01.02" file="02-novel-management" >}}

**Scenario:** Add Part button is not available when parts are disabled

{{< test-results id="T-FUNC-0211.01.03" file="02-novel-management" >}}

## R-UI-0211.01 Add part form presents all required fields

**Scenario:** Add part form presents all required fields

{{< test-results id="T-UI-0211.01.01" file="02-novel-management" >}}

## R-FUNC-0212.01 Edit a part

**Scenario:** Successfully edit a part

{{< test-results id="T-FUNC-0212.01.01" file="02-novel-management" >}}

**Scenario:** Cancel editing a part

{{< test-results id="T-FUNC-0212.01.02" file="02-novel-management" >}}

## R-UI-0212.01 Edit part form presents all required fields

**Scenario:** Edit part form presents all editable fields

{{< test-results id="T-UI-0212.01.01" file="02-novel-management" >}}

**Scenario:** Edit part form displays word count as read-only

{{< test-results id="T-UI-0212.01.02" file="02-novel-management" >}}

## R-FUNC-0213.01 Archive a novel part

**Scenario:** Successfully archive a part with chapters when there are more than 1 active Parts

{{< test-results id="T-FUNC-0213.01.01" file="02-novel-management" >}}

**Scenario:** Successfully archive a Part, moving the Chapters to another Part

{{< test-results id="T-FUNC-0213.01.02" file="02-novel-management" >}}

**Scenario:** Successfully archive a Part and its Chapters

{{< test-results id="T-FUNC-0213.01.03" file="02-novel-management" >}}

**Scenario:** Cancel archiving a part

{{< test-results id="T-FUNC-0213.01.04" file="02-novel-management" >}}

**Scenario:** Successfully archive a part with chapters when there is only 1 active Part

{{< test-results id="T-FUNC-0213.01.05" file="02-novel-management" >}}

**Scenario:** Successfully archive the final active part, moving the chapters to the novel

{{< test-results id="T-FUNC-0213.01.06" file="02-novel-management" >}}

**Scenario:** Successfully archive a part that has no chapters

{{< test-results id="T-FUNC-0213.01.07" file="02-novel-management" >}}

## R-FUNC-0214.01 Unarchive a part

**Scenario:** Successfully unarchive a part

{{< test-results id="T-FUNC-0214.01.01" file="02-novel-management" >}}

**Scenario:** Cancel unarchiving a part

{{< test-results id="T-FUNC-0214.01.02" file="02-novel-management" >}}

## R-FUNC-0215.01 Delete a part

**Scenario:** Successfully delete a part

{{< test-results id="T-FUNC-0215.01.01" file="02-novel-management" >}}

**Scenario:** Cancel deleting a part

{{< test-results id="T-FUNC-0215.01.02" file="02-novel-management" >}}

## R-DATA-0215.01 Part deletion cascades to chapters and scenes

**Scenario:** Chapters and scenes are deleted with the part

{{< test-results id="T-DATA-0215.01.01" file="02-novel-management" >}}

## R-FUNC-0217.01 Create a chapter

**Scenario:** Successfully create a chapter in a novel without parts

{{< test-results id="T-FUNC-0217.01.01" file="02-novel-management" >}}

**Scenario:** Successfully create a chapter in a novel with parts

{{< test-results id="T-FUNC-0217.01.02" file="02-novel-management" >}}

## R-UI-0217.01 Add chapter form presents all required fields

**Scenario:** Add chapter form presents all required fields

{{< test-results id="T-UI-0217.01.01" file="02-novel-management" >}}

## R-FUNC-0218.01 Edit a chapter

**Scenario:** Successfully edit a chapter

{{< test-results id="T-FUNC-0218.01.01" file="02-novel-management" >}}

**Scenario:** Cancel editing a chapter

{{< test-results id="T-FUNC-0218.01.02" file="02-novel-management" >}}

## R-UI-0218.01 Edit chapter form presents all required fields

**Scenario:** Edit chapter form presents all editable fields

{{< test-results id="T-UI-0218.01.01" file="02-novel-management" >}}

**Scenario:** Edit chapter form displays word count as read-only

{{< test-results id="T-UI-0218.01.02" file="02-novel-management" >}}

## R-FUNC-0219.01 Archive a chapter

**Scenario:** Successfully archive a chapter

{{< test-results id="T-FUNC-0219.01.01" file="02-novel-management" >}}

**Scenario:** Cancel archiving a chapter

{{< test-results id="T-FUNC-0219.01.02" file="02-novel-management" >}}

## R-FUNC-0220.01 Unarchive a chapter

**Scenario:** Successfully unarchive a chapter

{{< test-results id="T-FUNC-0220.01.01" file="02-novel-management" >}}

**Scenario:** Cancel unarchiving a chapter

{{< test-results id="T-FUNC-0220.01.02" file="02-novel-management" >}}

## R-FUNC-0221.01 Delete a chapter

**Scenario:** Successfully delete a chapter

{{< test-results id="T-FUNC-0221.01.01" file="02-novel-management" >}}

**Scenario:** Cancel deleting a chapter

{{< test-results id="T-FUNC-0221.01.02" file="02-novel-management" >}}

## R-DATA-0221.01 Chapter deletion cascades to scenes

**Scenario:** Scenes are deleted with the chapter

{{< test-results id="T-DATA-0221.01.01" file="02-novel-management" >}}

## R-FUNC-0223.01 Create a scene

**Scenario:** Successfully create a scene

{{< test-results id="T-FUNC-0223.01.01" file="02-novel-management" >}}

## R-UI-0223.01 Add scene form presents all required fields

**Scenario:** Add scene form presents all required fields

{{< test-results id="T-UI-0223.01.01" file="02-novel-management" >}}

## R-FUNC-0224.01 Edit a scene

**Scenario:** Successfully edit a scene

{{< test-results id="T-FUNC-0224.01.01" file="02-novel-management" >}}

**Scenario:** Cancel editing a scene

{{< test-results id="T-FUNC-0224.01.02" file="02-novel-management" >}}

## R-UI-0224.01 Edit scene form presents all required fields

**Scenario:** Edit scene form presents all editable fields

{{< test-results id="T-UI-0224.01.01" file="02-novel-management" >}}

**Scenario:** Edit scene form displays word count as read-only

{{< test-results id="T-UI-0224.01.02" file="02-novel-management" >}}

## R-FUNC-0224.02 Write button opens the editor

**Scenario:** Write button navigates to the editor

{{< test-results id="T-FUNC-0224.02.01" file="02-novel-management" >}}

## R-FUNC-0225.01 Archive a scene

**Scenario:** Successfully archive a scene

{{< test-results id="T-FUNC-0225.01.01" file="02-novel-management" >}}

**Scenario:** Cancel archiving a scene

{{< test-results id="T-FUNC-0225.01.02" file="02-novel-management" >}}

## R-FUNC-0226.01 Unarchive a scene

**Scenario:** Successfully unarchive a scene

{{< test-results id="T-FUNC-0226.01.01" file="02-novel-management" >}}

**Scenario:** Cancel unarchiving a scene

{{< test-results id="T-FUNC-0226.01.02" file="02-novel-management" >}}

## R-FUNC-0227.01 Delete a scene

**Scenario:** Successfully delete a scene

{{< test-results id="T-FUNC-0227.01.01" file="02-novel-management" >}}

**Scenario:** Cancel deleting a scene

{{< test-results id="T-FUNC-0227.01.02" file="02-novel-management" >}}

## R-FUNC-0228.01 Relocate a scene to a different chapter

**Scenario:** Successfully relocate a scene to another chapter

{{< test-results id="T-FUNC-0228.01.01" file="02-novel-management" >}}

## R-FUNC-0229.01 Status property values

**Scenario:** Status values are available on a novel

{{< test-results id="T-FUNC-0229.01.01" file="02-novel-management" >}}

**Scenario:** Status values are available on a part

{{< test-results id="T-FUNC-0229.01.02" file="02-novel-management" >}}

**Scenario:** Status values are available on a chapter

{{< test-results id="T-FUNC-0229.01.03" file="02-novel-management" >}}

**Scenario:** Status values are available on a scene

{{< test-results id="T-FUNC-0229.01.04" file="02-novel-management" >}}

## R-FUNC-0229.02 Status defaults to Not started

**Scenario:** Status defaults to Not started on a new novel

{{< test-results id="T-FUNC-0229.02.01" file="02-novel-management" >}}

**Scenario:** Status defaults to Not started on a new part

{{< test-results id="T-FUNC-0229.02.02" file="02-novel-management" >}}

**Scenario:** Status defaults to Not started on a new chapter

{{< test-results id="T-FUNC-0229.02.03" file="02-novel-management" >}}

**Scenario:** Status defaults to Not started on a new scene

{{< test-results id="T-FUNC-0229.02.04" file="02-novel-management" >}}
