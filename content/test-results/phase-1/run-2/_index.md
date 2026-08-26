---
title: "Test Report - Phase 1 - Run 2"
description: "Report summarising the test results for development phase 1 - run 2"
draft: false
---

## Introduction

This test report summarises the test protocol executed as run-2 for development phase 1. The application under test was Novel-It v0.5.2.

Unlike Run 1, which was executed manually, Run 2 was executed as an automated test suite (pytest for backend/state scenarios, Playwright for browser-dependent scenarios), converted from the same Gherkin scenarios documented in the requirements. Each test is tagged with its requirement's test ID, and results are recorded automatically against that ID.

The following test protocols made up this test run:

- 01-user-management
- 02-novel-management
- 03-writing-interface
- 04-character-management
- 05-location-management
- 06-item-management
- 07-world-building

All seven test protocols were executed in full, with the exception of specific scenarios that were declared in the addendum to the run 1 test report. This run also included 07-world-building, which could not be executed in Run 1 as the feature did not yet exist.

23 scenarios across five protocols were excluded from this run's scope, as declared in Run 1's addendum. All relate to archive/delete functionality not yet implemented for any planning entity (Character, Location, Item, World Building) or for Scene. These remain excluded pending that functionality being built (see below).

## Test Summary

| Protocol | Tests Run | Passed | Genuine Fails | Untestable |
| -------- | --------- | ------ | -------------- | ---------- |
| 01-user-management | 16 | 16 | 0 | 0 |
| 02-novel-management | 68 | 68 | 0 | 0 |
| 03-writing-interface | 35 | 35 | 0 | 0 |
| 04-character-management | 27 | 27 | 0 | 0 |
| 05-location-management | 27 | 27 | 0 | 0 |
| 06-item-management | 27 | 27 | 0 | 0 |
| 07-world-building | 27 | 27 | 0 | 0 |
| **Total** | **227** | **227** | **0** | **0** |

## Conclusion

All 227 in-scope scenarios passed. No genuine failures were recorded during this run.

One further defect was found and corrected during preparation for this run, rather than surfacing as a recorded failure here: `part_delete_view` was not updating the novel's word count after deleting a part (issue #138). This was caught by the new automated test for that scenario before Run 2 was executed, and fixed prior to running it.

## Exclusions From This Run

The following 23 scenarios, declared in Run 1's addendum, remain excluded — all relate to archive/delete functionality not yet implemented for any planning entity or for Scene:

### 02-novel-management

| Test ID | Reason |
| --- | --- |
| T-FUNC-0225.01.01 | Scene archive not yet implemented |
| T-FUNC-0225.01.02 | Scene archive not yet implemented |
| T-FUNC-0226.01.01 | Scene restore not yet implemented |
| T-FUNC-0226.01.02 | Scene restore not yet implemented |
| T-FUNC-0227.01.01 | Scene delete not yet implemented |
| T-FUNC-0227.01.02 | Scene delete not yet implemented |

### 03-writing-interface

| Test ID | Reason |
| --- | --- |
| T-FUNC-0304.03.01 | Scene archive not yet implemented |
| T-FUNC-0304.03.02 | Scene archive not yet implemented |
| T-FUNC-0304.03.03 | Scene archive not yet implemented |
| T-FUNC-0304.04.01 | Scene restore not yet implemented |
| T-FUNC-0304.04.02 | Scene restore not yet implemented |
| T-FUNC-0304.04.03 | Scene restore not yet implemented |
| T-FUNC-0304.05.01 | Scene delete not yet implemented |
| T-FUNC-0304.05.02 | Scene delete not yet implemented |
| T-FUNC-0304.05.03 | Scene delete not yet implemented |

### 04-character-management

| Test ID | Reason |
| --- | --- |
| T-FUNC-0401.01.02 | Character archive not yet implemented |
| T-DATA-0410.01.01 | Character delete not yet implemented |

### 05-location-management

| Test ID | Reason |
| --- | --- |
| T-FUNC-0501.01.02 | Location archive not yet implemented |
| T-DATA-0510.01.01 | Location delete not yet implemented |

### 06-item-management

| Test ID | Reason |
| --- | --- |
| T-FUNC-0601.01.02 | Item archive not yet implemented |
| T-DATA-0610.01.01 | Item delete not yet implemented |

### 07-world-building

| Test ID | Reason |
| --- | --- |
| T-FUNC-0701.01.02 | World building archive not yet implemented |
| T-DATA-0710.01.01 | World building delete not yet implemented |

## Individual Test Reports

