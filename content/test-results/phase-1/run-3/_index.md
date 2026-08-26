---
title: "Test Report - Phase 1 - Run 3"
description: "Report summarising the test results for development phase 1 - run 3 (scene archive/restore/delete correction)"
draft: false
---

## Introduction

Run 3 is a small, targeted correction to Run 2, not a full re-execution of
Phase 1. It covers 15 scenarios that Run 2 excluded on the assumption that
scene archive/restore/delete weren't implemented -- an exclusion first
declared in Run 1's addendum and carried forward into Run 2's scope.

That assumption was wrong. The backend views (`scene_archive_view`,
`scene_restore_view`, `scene_delete_view`) existed all along -- what was
actually missing was the UI buttons to reach them, which appeared once the
card design was standardised across the application. Confirmed by reading
the view implementations directly: all three correctly trigger the same
word-count cascade mechanism already proven correct for chapter and part.

See `data/requirements/phase-1-run-3-scope.yaml` for the full reasoning
behind each test's inclusion.

Run 2's own scope file and recorded results are not edited retroactively --
this run's results are recorded as new executions alongside Run 2's, not as
amendments to it.

## Test Summary

| Area | Tests Run | Passed | Genuine Fails |
| ---- | --------- | ------ | -------------- |
| Scene archive/restore/delete | 6 | 6 | 0 |
| Word-count cascade effects | 9 | 9 | 0 |
| **Total** | **15** | **15** | **0** |

## Conclusion

All 15 scenarios passed. The exclusion declared in Run 1's addendum and
carried into Run 2 was based on an incorrect assumption about what had been
implemented, now corrected.

## Scene Archive, Restore, and Delete

### R-FUNC-0225.01 Archive a scene

**Scenario:** Successfully archive a scene

{{< test-results id="T-FUNC-0225.01.01" file="02-novel-management" >}}

**Scenario:** Cancel archiving a scene

{{< test-results id="T-FUNC-0225.01.02" file="02-novel-management" >}}

### R-FUNC-0226.01 Unarchive a scene

**Scenario:** Successfully unarchive a scene

{{< test-results id="T-FUNC-0226.01.01" file="02-novel-management" >}}

**Scenario:** Cancel unarchiving a scene

{{< test-results id="T-FUNC-0226.01.02" file="02-novel-management" >}}

### R-FUNC-0227.01 Delete a scene

**Scenario:** Successfully delete a scene

{{< test-results id="T-FUNC-0227.01.01" file="02-novel-management" >}}

**Scenario:** Cancel deleting a scene

{{< test-results id="T-FUNC-0227.01.02" file="02-novel-management" >}}

## Word-Count Cascade Effects

### R-FUNC-0304.03 Word counts update when a manuscript entity is archived

**Scenario:** Archiving a scene reduces the parent chapter word count

{{< test-results id="T-FUNC-0304.03.01" file="03-writing-interface" >}}

**Scenario:** Archiving a scene reduces the novel word count

{{< test-results id="T-FUNC-0304.03.02" file="03-writing-interface" >}}

**Scenario:** Archiving a scene reduces the part word count when parts are enabled

{{< test-results id="T-FUNC-0304.03.03" file="03-writing-interface" >}}

### R-FUNC-0304.04 Word counts update when a manuscript entity is unarchived

**Scenario:** Unarchiving a scene increases the parent chapter word count

{{< test-results id="T-FUNC-0304.04.01" file="03-writing-interface" >}}

**Scenario:** Unarchiving a scene increases the novel word count

{{< test-results id="T-FUNC-0304.04.02" file="03-writing-interface" >}}

**Scenario:** Unarchiving a scene increases the part word count when parts are enabled

{{< test-results id="T-FUNC-0304.04.03" file="03-writing-interface" >}}

### R-FUNC-0304.05 Word counts update when a manuscript entity is deleted

**Scenario:** Deleting a scene reduces the parent chapter word count

{{< test-results id="T-FUNC-0304.05.01" file="03-writing-interface" >}}

**Scenario:** Deleting a scene reduces the novel word count

{{< test-results id="T-FUNC-0304.05.02" file="03-writing-interface" >}}

**Scenario:** Deleting a scene reduces the part word count when parts are enabled

{{< test-results id="T-FUNC-0304.05.03" file="03-writing-interface" >}}
