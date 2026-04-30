---
title: "Test Report - Phase 1 - Run 1"
description: "Report summarising the test results for development phase 1 - run 1"
draft: false
revision: "2.0"
revision_date: "20-Apr-2026"
---

## Introduction

This test report summarises the test protocol executed as run-1 for development phase 1. The application under test was Novel-It v0.3.0.

The following test protocols made up this test run:

- 01-user-management
- 02-novel-management
- 03-writing-interface
- 04-character-management
- 05-location-management
- 06-item-management
- 07-world-building

All test protocols were completed with the exception of 07-world-building, which was not executed (see below).

A number of failures were recorded during the execution. Some of these were genuine failure of the application to perform to requirements. However some of the tests relied on functionality that's not due to be implemented until phase 2 or later. Because these tests were included in the run they were marked as failures for this run. The report sections below differentiate between the two types of test failure. The columns labeled "Untestable" in the tables below relate to these tests that couldn't be performed due to missing functionality. 

## Test Summary

| Protocol | Tests Run | Passed | Genuine Fails | Untestable |
| -------- | --------- | ------ | ------------- | ---------- |
| 01-user-management | 16 | 15 | 1 | 0 |
| 02-novel-management | 79 | 60 | 19 | 0 |
| 03-writing-interface | 44 | 25 | 19 | 0 |
| 04-character-management | 29 | 24 | 3 | 2 |
| 05-location-management | 29 | 23 | 4 | 2 |
| 06-item-management | 29 | 23 | 4 | 2 |
| 07-world-building | 29 | 0 | 0 | 29 |

## Conclusion

- The 07-world-building feature is a phase 1 feature that has not been implemented. This will be corrected and the test protocol will be submitted for phase-1 run-2.
- The genuine failures will be fixed as patch releases and will be re-submitted for phase-1 run-2.
- The untestable tests that rely on functionality that is not part of phase-1 will be identified and excluded from run-2.

## Addendum - Test Exclusions From Run 2

These tests will not be included in phase-1 run-2 testing:

### 04-character-management

| Test ID | Scenario |
| --- | --- |
| T-FUNC-0401.01.02 | Archived characters do not appear on the character list board |
| T-DATA-0410.01.01 | Relationships are removed when a character is deleted |

### 05-location-management

| Test ID | Scenario |
| --- | --- |
| T-FUNC-0501.01.02 | Archived locations do not appear on the location list board |
| T-DATA-0510.01.01 | Relationships are removed when a location is deleted |

### 06-item-management

| Test ID | Scenario |
| --- | --- |
| T-FUNC-0601.01.02 | Archived items do not appear on the item list board |
| T-DATA-0610.01.01 | Relationships are removed when an item is deleted |

### 07-world-building

| Test ID | Scenario |
| --- | --- |
| T-FUNC-0701.01.02 | Archived world building items do not appear on the world building list board |
| T-DATA-0710.01.01 | Relationships are removed when a world building item is deleted |

## Revision History

| Revision | Date | Changes |
| --- | ------------ | --- |
| 1.0 | 18 Apr 2026 | Initial version |
| 2.0 | 20 Apr 2026 | Moved untestable failures to genuine failures for 02-novel-management and 03-writing-interface. Removed sections for 02-novel-management and 03-writing-interface from the addendum |


## Individual Test Reports
