---
title: "03 Writing Interface"
description: "Test execution records for the markdown editor and writing features"
draft: false
revision: "1.0"
revision_date: "18-Apr-2026"
---

## R-FUNC-0301.01 Markdown editor element support

**Scenario:** Editor renders heading elements

{{< test-results id="T-FUNC-0301.01.01" file="03-writing-interface" >}}

**Scenario:** Editor renders typography elements

{{< test-results id="T-FUNC-0301.01.02" file="03-writing-interface" >}}

**Scenario:** Editor renders list elements

{{< test-results id="T-FUNC-0301.01.03" file="03-writing-interface" >}}

**Scenario:** Editor renders remaining supported elements

{{< test-results id="T-FUNC-0301.01.04" file="03-writing-interface" >}}

## R-UI-0301.01 Editor toolbar provides shortcuts for common elements

**Scenario:** Toolbar provides H1, H2, and H3 shortcut buttons

{{< test-results id="T-UI-0301.01.01" file="03-writing-interface" >}}

**Scenario:** H4 to H6 are not available as toolbar shortcuts

{{< test-results id="T-UI-0301.01.02" file="03-writing-interface" >}}

## R-FUNC-0302.01 Editor autosaves content automatically

**Scenario:** Editor autosaves after changes are made

{{< test-results id="T-FUNC-0302.01.01" file="03-writing-interface" >}}

**Scenario:** Editor does not autosave when no changes have been made

{{< test-results id="T-FUNC-0302.01.02" file="03-writing-interface" >}}

## R-PERF-0302.01 Default autosave interval is 30 seconds

**Scenario:** Default autosave interval is 30 seconds

{{< test-results id="T-PERF-0302.01.01" file="03-writing-interface" >}}

## R-USER-0303.01 Unsaved changes trigger a confirmation dialog on in-application navigation

**Scenario:** Confirmation dialog is shown when navigating away with unsaved changes

{{< test-results id="T-USER-0303.01.01" file="03-writing-interface" >}}

**Scenario:** Navigation proceeds when the user confirms

{{< test-results id="T-USER-0303.01.02" file="03-writing-interface" >}}

**Scenario:** Navigation is cancelled when the user declines

{{< test-results id="T-USER-0303.01.03" file="03-writing-interface" >}}

**Scenario:** No confirmation dialog when there are no unsaved changes

{{< test-results id="T-USER-0303.01.04" file="03-writing-interface" >}}

## R-FUNC-0304.01 Word count updates as the user types

**Scenario:** Word count updates as text is added

{{< test-results id="T-FUNC-0304.01.01" file="03-writing-interface" >}}

**Scenario:** Word count updates as text is deleted

{{< test-results id="T-FUNC-0304.01.02" file="03-writing-interface" >}}

## R-FUNC-0304.02 Word counts roll up on save

**Scenario:** Chapter word count updates on scene save

{{< test-results id="T-FUNC-0304.02.01" file="03-writing-interface" >}}

**Scenario:** Novel word count updates on scene save

{{< test-results id="T-FUNC-0304.02.02" file="03-writing-interface" >}}

**Scenario:** Part word count updates on scene save when parts are enabled

{{< test-results id="T-FUNC-0304.02.03" file="03-writing-interface" >}}

## R-FUNC-0304.03 Word counts update when a manuscript entity is archived

**Scenario:** Archiving a scene reduces the parent chapter word count

{{< test-results id="T-FUNC-0304.03.01" file="03-writing-interface" >}}

**Scenario:** Archiving a scene reduces the novel word count

{{< test-results id="T-FUNC-0304.03.02" file="03-writing-interface" >}}

**Scenario:** Archiving a scene reduces the part word count when parts are enabled

{{< test-results id="T-FUNC-0304.03.03" file="03-writing-interface" >}}

**Scenario:** Archiving a chapter reduces the novel word count

{{< test-results id="T-FUNC-0304.03.04" file="03-writing-interface" >}}

**Scenario:** Archiving a chapter reduces the part word count when parts are enabled

{{< test-results id="T-FUNC-0304.03.05" file="03-writing-interface" >}}

**Scenario:** Archiving a part reduces the novel word count

{{< test-results id="T-FUNC-0304.03.06" file="03-writing-interface" >}}

## R-FUNC-0304.04 Word counts update when a manuscript entity is unarchived

**Scenario:** Unarchiving a scene increases the parent chapter word count

{{< test-results id="T-FUNC-0304.04.01" file="03-writing-interface" >}}

**Scenario:** Unarchiving a scene increases the novel word count

{{< test-results id="T-FUNC-0304.04.02" file="03-writing-interface" >}}

**Scenario:** Unarchiving a scene increases the part word count when parts are enabled

{{< test-results id="T-FUNC-0304.04.03" file="03-writing-interface" >}}

**Scenario:** Unarchiving a chapter increases the novel word count

{{< test-results id="T-FUNC-0304.04.04" file="03-writing-interface" >}}

**Scenario:** Unarchiving a chapter increases the part word count when parts are enabled

{{< test-results id="T-FUNC-0304.04.05" file="03-writing-interface" >}}

**Scenario:** Unarchiving a part increases the novel word count

{{< test-results id="T-FUNC-0304.04.06" file="03-writing-interface" >}}

## R-FUNC-0304.05 Word counts update when a manuscript entity is deleted

**Scenario:** Deleting a scene reduces the parent chapter word count

{{< test-results id="T-FUNC-0304.05.01" file="03-writing-interface" >}}

**Scenario:** Deleting a scene reduces the novel word count

{{< test-results id="T-FUNC-0304.05.02" file="03-writing-interface" >}}

**Scenario:** Deleting a scene reduces the part word count when parts are enabled

{{< test-results id="T-FUNC-0304.05.03" file="03-writing-interface" >}}

**Scenario:** Deleting a chapter reduces the novel word count

{{< test-results id="T-FUNC-0304.05.04" file="03-writing-interface" >}}

**Scenario:** Deleting a chapter reduces the part word count when parts are enabled

{{< test-results id="T-FUNC-0304.05.05" file="03-writing-interface" >}}

**Scenario:** Deleting a part reduces the novel word count

{{< test-results id="T-FUNC-0304.05.06" file="03-writing-interface" >}}

## R-FUNC-0305.01 Toggle between edit and preview mode

**Scenario:** Switch from edit mode to preview mode

{{< test-results id="T-FUNC-0305.01.01" file="03-writing-interface" >}}

**Scenario:** Switch from preview mode back to edit mode

{{< test-results id="T-FUNC-0305.01.02" file="03-writing-interface" >}}

## R-FUNC-0306.01 Distraction free mode

**Scenario:** Enter distraction free mode

{{< test-results id="T-FUNC-0306.01.01" file="03-writing-interface" >}}

**Scenario:** Exit distraction free mode

{{< test-results id="T-FUNC-0306.01.02" file="03-writing-interface" >}}

## R-FUNC-0307.01 Automatic cross-referencing on save

**Scenario:** Character name occurrence is recorded on scene save

{{< test-results id="T-FUNC-0307.01.01" file="03-writing-interface" >}}

**Scenario:** Location name occurrence is recorded on scene save

{{< test-results id="T-FUNC-0307.01.02" file="03-writing-interface" >}}

**Scenario:** Item name occurrence is recorded on scene save

{{< test-results id="T-FUNC-0307.01.03" file="03-writing-interface" >}}

**Scenario:** No occurrence recorded when name is not present in scene

{{< test-results id="T-FUNC-0307.01.04" file="03-writing-interface" >}}
