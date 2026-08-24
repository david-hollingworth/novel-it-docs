---
title: "Phase 1 - Run 2 Risk Assessment"
description: "Risk assessment determining which Phase 1 Run 1 tests must be re-executed in Run 2 and which can be safely skipped"
draft: true
date: "2026-06-24"
superseded: true
superseded_date: "2026-08-24"
---

> **Superseded 24-Aug-2026.** This assessment's regression-risk skip strategy (136 must-re-run / 80 skip) is no longer the basis for Run 2 scope. With execution moving to automated CI, the manual-effort rationale for skipping unchanged areas no longer applies — every in-scope test now runs on every execution. Current Run 2 scope (227 included / 23 excluded, the 23 being functionality genuinely not yet implemented) is defined in `data/requirements/phase-1-run-2-scope.yaml`. This document is retained as a historical record of the Run 1 -> Run 2 risk analysis and is excluded from the built site (`draft: true`).

## Introduction

This risk assessment was produced to inform the scope of Phase 1 Run 2 testing for Novel-It. Its purpose is to identify which tests that passed in Run 1 must be re-executed in Run 2 due to the risk of regression introduced by fixes and new features implemented since Run 1, and which tests can be safely skipped on the basis that no changes were made to the areas of the application they cover.

The assessment draws on three sources of data:

- **Phase 1 Run 1 test results** — the execution records held in `data/test-results/` for each of the six protocols completed during Run 1, covering 196 tests across protocols 01 through 06. Protocol 07 (World Building) was not executed in Run 1 as the feature was not yet implemented.
- **GitHub issue list** — the closed issues on the `david-hollingworth/novel-it` repository, used to identify which defects raised during Run 1 have been fixed, and which new features have been implemented, since Run 1 concluded in April 2026.
- **Run 1 test report addendum** — the list of 17 tests formally excluded from Run 2, covering functionality deferred to Phase 2 (archive/delete for characters, locations, items, and world building).

For each test that passed in Run 1, the recommendation is either **Must re-run** (the fix set or new feature work touches the area under test, creating regression risk) or **Skip** (no changes were made to the relevant area). All tests that failed in Run 1 and have a corresponding fix are automatically categorised as **Must re-run**. Tests in the excluded list are omitted from this assessment entirely.

The following GitHub issues were closed between Run 1 (April 2026) and the preparation of Run 2, and inform the risk ratings below:

| Issue | Title |
| --- | --- |
| #62 | fix: User not redirected to the login page after registration |
| #63 | fix: Edit novel form does not display actual word count |
| #64 | doc: Incorrect field name in test description (part form) |
| #65 | fix: Word count not displayed on edit part page |
| #66 | fix: Incorrect fields displayed on add/edit chapter form |
| #67 | fix: Actual word count not displayed on edit chapter form |
| #68 | fix: Scene form fields do not match the required fields |
| #69 | fix: Actual word count not displayed on edit scene form |
| #70 | fix: Write button not available on the edit scene page |
| #71 | fix: No facility to archive scenes |
| #73 | fix: No option to delete a scene |
| #74 | fix: Status drop down not available for the chapter |
| #75 | fix: In-application notification not displayed for all navigations |
| #76 | fix: Archiving a chapter did not reduce the novel/part word count |
| #77 | fix: Archiving a part did not reduce the novel word count |
| #78 | fix: Unarchiving a chapter/part did not increase word counts |
| #79 | fix: Deleting a chapter/part did not reduce word counts |
| #81 | fix: Not all data fields appear on the character form |
| #83 | fix: Application accepts image formats other than PNG and JPG |
| #84 | fix: Incorrect behaviour when editing a relationship |
| #88 | fix: No facility to delete locations |
| #90 | fix: Add item form did not display all required fields |
| #95 | feat: FEAT-0225 Archive scene |
| #96 | feat: FEAT-0227 Delete scene |
| #97 | feat: FEAT-0226 Unarchive scene |
| #98 | enh: Align card designs and features across entities |
| #114 | feat: FEAT-07 World Building Management |
| #122 | fix: Single line breaks in the markdown editor render as a continuous line in the preview |

---

## 01 — User Management

| Test ID | Scenario | Run 1 | Recommendation | Rationale |
| --- | --- | --- | --- | --- |
| T-FUNC-0101.01.01 | User not redirected to login after registration | FAIL | Must re-run | #62 fixed this defect directly |
| T-SEC-0101.01.01 | Duplicate username rejected | PASS | Skip | Authentication and registration validation logic was not touched by any fix |
| T-SEC-0101.02.01 | Password complexity enforced | PASS | Skip | Password validation logic was not touched by any fix |
| T-DATA-0101.01.01 | User data stored correctly | PASS | Skip | User data persistence was not touched by any fix |
| T-FUNC-0101.02.01 | Single password field rejected | PASS | Skip | Registration form validation was not touched by any fix |
| T-FUNC-0101.02.02 | Mismatched passwords rejected | PASS | Skip | Registration form validation was not touched by any fix |
| T-FUNC-0102.01.01 | Successful login | PASS | Skip | Login logic was not touched by any fix |
| T-FUNC-0102.01.02 | Incorrect password rejected | PASS | Skip | Login validation was not touched by any fix |
| T-FUNC-0102.02.01 | Logout successful | PASS | Skip | Logout logic was not touched by any fix |
| T-FUNC-0102.02.02 | Session terminated after logout | PASS | Skip | Session handling was not touched by any fix |
| T-SEC-0102.01.01 | Redirect to login when unauthenticated | PASS | Skip | Authentication guards were not touched by any fix |
| T-USER-0102.01.01 | Generic error on bad login (username) | PASS | Skip | Login error messaging was not touched by any fix |
| T-USER-0102.01.02 | Generic error on bad login (password) | PASS | Skip | Login error messaging was not touched by any fix |
| T-FUNC-0103.01.01 | Password change successful | PASS | Skip | Password change logic was not touched by any fix |
| T-FUNC-0103.01.02 | Password change rejected with wrong current password | PASS | Skip | Password change validation was not touched by any fix |
| T-FUNC-0103.02.01 | Password change rejected when new passwords don't match | PASS | Skip | Password change validation was not touched by any fix |

---

## 02 — Novel Management

*Excluded from Run 2 (per Run 1 Addendum):* T-FUNC-0225.01.01, T-FUNC-0225.01.02, T-FUNC-0226.01.01, T-FUNC-0226.01.02, T-FUNC-0227.01.01, T-FUNC-0227.01.02

| Test ID | Scenario | Run 1 | Recommendation | Rationale |
| --- | --- | --- | --- | --- |
| T-FUNC-0201.01.01 | Create novel | PASS | Skip | Novel creation logic was not touched by any fix |
| T-FUNC-0201.01.02 | Novel not created without title | PASS | Skip | Novel creation validation was not touched by any fix |
| T-UI-0201.01.01 | Novel creation form fields | PASS | Must re-run | #98 aligned card designs and features across all entities; the novel creation UI may have been affected |
| T-FUNC-0201.02.01 | Parts Enabled defaults to No | PASS | Skip | Parts default logic was not touched by any fix |
| T-FUNC-0202.01.01 | Parts not displayed when disabled | PASS | Skip | Parts display logic was not touched by any fix |
| T-FUNC-0202.02.01 | Parts displayed when enabled | PASS | Skip | Parts display logic was not touched by any fix |
| T-FUNC-0203.01.01 | Edit novel title | PASS | Skip | Novel edit logic was not touched by any fix |
| T-FUNC-0203.01.02 | Edit novel rejected without title | PASS | Skip | Novel edit validation was not touched by any fix |
| T-FUNC-0203.02.01 | Enable parts via edit | PASS | Skip | Parts toggle logic was not touched by any fix |
| T-FUNC-0203.02.02 | Disable parts via edit | PASS | Skip | Parts toggle logic was not touched by any fix |
| T-UI-0203.01.01 | Edit novel form fields displayed | PASS | Skip | The edit novel form structure was not changed by any fix |
| T-UI-0203.01.02 | Edit novel word count displayed | FAIL | Must re-run | #63 fixed this defect directly |
| T-FUNC-0204.01.01 | Archive novel | PASS | Skip | Novel archive logic was not touched by any fix |
| T-FUNC-0204.01.02 | Cancel archive novel | PASS | Skip | Novel archive cancel path was not touched by any fix |
| T-FUNC-0205.01.01 | Unarchive novel | PASS | Skip | Novel unarchive logic was not touched by any fix |
| T-FUNC-0205.01.02 | Cancel unarchive novel | PASS | Skip | Novel unarchive cancel path was not touched by any fix |
| T-FUNC-0206.01.01 | Delete novel | PASS | Skip | Novel delete logic was not touched by any fix |
| T-FUNC-0206.01.02 | Cancel delete novel | PASS | Skip | Novel delete cancel path was not touched by any fix |
| T-DATA-0206.01.01 | Delete novel cascades to all children | PASS | Skip | Novel cascade delete logic was not touched by any fix |
| T-FUNC-0209.01.01 | Novel list shows active novels | PASS | Must re-run | #98 aligned card designs and features across all entities; the novel list card UI may have been affected |
| T-FUNC-0209.01.02 | Novel list excludes archived | PASS | Skip | Novel list filtering logic was not touched by any fix |
| T-FUNC-0210.01.01 | Novel structure displayed (no parts) | PASS | Skip | Novel structure display was not touched by any fix |
| T-FUNC-0210.01.02 | Novel structure displayed (with parts) | PASS | Skip | Novel structure display with parts was not touched by any fix |
| T-FUNC-0211.01.01 | Add part | PASS | Skip | Part creation logic was not touched by any fix |
| T-FUNC-0211.01.02 | Add part with chapters | PASS | Skip | Part creation with chapter assignment was not touched by any fix |
| T-FUNC-0211.01.03 | Add part button hidden when parts disabled | PASS | Skip | Part button visibility logic was not touched by any fix |
| T-UI-0211.01.01 | Add part form fields | FAIL | Must re-run | #64 corrected the requirement wording rather than the code; must verify the form matches the corrected requirement |
| T-FUNC-0212.01.01 | Edit part name | PASS | Skip | Part edit logic was not touched by any fix |
| T-FUNC-0212.01.02 | Edit part rejected without name | PASS | Skip | Part edit validation was not touched by any fix |
| T-UI-0212.01.01 | Edit part form fields | FAIL | Must re-run | #64 corrected the requirement wording rather than the code; must verify the edit part form matches the corrected requirement |
| T-UI-0212.01.02 | Edit part word count displayed | FAIL | Must re-run | #65 fixed this defect directly |
| T-FUNC-0213.01.01 | Archive part — options displayed with chapters present | PASS | Must re-run | #76 and #77 fixed word count cascade logic for archiving parts and chapters; the archive part code path was modified |
| T-FUNC-0213.01.02 | Archive part — chapters moved to another part | PASS | Must re-run | #76 and #77 fixed word count cascade logic for archiving parts and chapters; the archive part code path was modified |
| T-FUNC-0213.01.03 | Archive part — chapters archived with part | PASS | Must re-run | #76 and #77 fixed word count cascade logic for archiving parts and chapters; the archive part code path was modified |
| T-FUNC-0213.01.04 | Archive part — cancel | PASS | Skip | The cancel path does not execute the cascade logic modified by #76 and #77 |
| T-FUNC-0213.01.05 | Archive part — options displayed (parts-disabled novel) | PASS | Must re-run | #76 and #77 fixed word count cascade logic for archiving parts and chapters; the archive part code path was modified |
| T-FUNC-0213.01.06 | Archive part — chapters moved to novel level | PASS | Must re-run | #76 and #77 fixed word count cascade logic for archiving parts and chapters; the archive part code path was modified |
| T-FUNC-0213.01.07 | Archive part — confirmed | PASS | Must re-run | #76 and #77 fixed word count cascade logic for archiving parts and chapters; the archive part code path was modified |
| T-FUNC-0214.01.01 | Unarchive part | PASS | Must re-run | #78 fixed word count cascade logic for unarchiving chapters and parts; the unarchive part code path was modified |
| T-FUNC-0214.01.02 | Cancel unarchive part | PASS | Skip | The cancel path does not execute the cascade logic modified by #78 |
| T-FUNC-0215.01.01 | Delete part | PASS | Must re-run | #79 fixed word count cascade logic for deleting chapters and parts; the delete part code path was modified |
| T-FUNC-0215.01.02 | Cancel delete part | PASS | Skip | The cancel path does not execute the cascade logic modified by #79 |
| T-DATA-0215.01.01 | Delete part cascades to chapters and scenes | PASS | Must re-run | #79 fixed word count cascade logic for deleting chapters and parts; the delete part code path was modified and cascade behaviour should be re-verified |
| T-FUNC-0217.01.01 | Add chapter (no parts) | PASS | Skip | Chapter creation logic was not touched by any fix |
| T-FUNC-0217.01.02 | Add chapter (with parts) | PASS | Skip | Chapter creation logic for part-enabled novels was not touched by any fix |
| T-UI-0217.01.01 | Add chapter form fields | FAIL | Must re-run | #66 fixed this defect directly |
| T-FUNC-0218.01.01 | Edit chapter name | PASS | Skip | Chapter edit logic was not touched by any fix |
| T-FUNC-0218.01.02 | Edit chapter rejected without name | PASS | Skip | Chapter edit validation was not touched by any fix |
| T-UI-0218.01.01 | Edit chapter form fields | FAIL | Must re-run | #66 fixed this defect directly |
| T-UI-0218.01.02 | Edit chapter word count displayed | FAIL | Must re-run | #67 fixed this defect directly |
| T-FUNC-0219.01.01 | Archive chapter | PASS | Must re-run | #76 fixed word count cascade logic when archiving a chapter; the archive chapter code path was modified |
| T-FUNC-0219.01.02 | Cancel archive chapter | PASS | Skip | The cancel path does not execute the cascade logic modified by #76 |
| T-FUNC-0220.01.01 | Unarchive chapter | PASS | Must re-run | #78 fixed word count cascade logic when unarchiving a chapter; the unarchive chapter code path was modified |
| T-FUNC-0220.01.02 | Cancel unarchive chapter | PASS | Skip | The cancel path does not execute the cascade logic modified by #78 |
| T-FUNC-0221.01.01 | Delete chapter | PASS | Must re-run | #79 fixed word count cascade logic when deleting a chapter; the delete chapter code path was modified |
| T-FUNC-0221.01.02 | Cancel delete chapter | PASS | Skip | The cancel path does not execute the cascade logic modified by #79 |
| T-DATA-0221.01.01 | Delete chapter cascades to scenes | PASS | Must re-run | #79 fixed word count cascade logic when deleting a chapter; the delete chapter code path was modified and cascade behaviour should be re-verified |
| T-FUNC-0223.01.01 | Add scene | PASS | Must re-run | #95, #96, and #97 implemented archive, delete, and unarchive for scenes; the scene model and views were modified as part of this work |
| T-UI-0223.01.01 | Add scene form fields | FAIL | Must re-run | #68 fixed this defect directly |
| T-FUNC-0224.01.01 | Edit scene title | PASS | Must re-run | #70 added the Write button to the edit scene form; the edit scene form was modified as part of this fix |
| T-FUNC-0224.01.02 | Edit scene rejected without title | PASS | Skip | Scene edit validation logic was not touched by any fix |
| T-UI-0224.01.01 | Edit scene form fields | FAIL | Must re-run | #68 fixed this defect directly |
| T-UI-0224.01.02 | Edit scene word count displayed | FAIL | Must re-run | #69 fixed this defect directly |
| T-FUNC-0224.02.01 | Write button on edit scene | FAIL | Must re-run | #70 fixed this defect directly |
| T-FUNC-0228.01.01 | Relocate scenes | PASS | Must re-run | #72 fixed a page-not-found error after relocating a scene; the scene relocation code path was modified |
| T-FUNC-0229.01.01 | Status options on novel | PASS | Skip | Novel status logic was not touched by any fix |
| T-FUNC-0229.01.02 | Status options on part | PASS | Skip | Part status logic was not touched by any fix |
| T-FUNC-0229.01.03 | Status field on chapter | FAIL | Must re-run | #74 fixed this defect directly |
| T-FUNC-0229.01.04 | Status field on scene | PASS | Skip | Scene status display was not touched by any fix |
| T-FUNC-0229.02.01 | Status defaults to Not Started (novel) | PASS | Skip | Novel status default logic was not touched by any fix |
| T-FUNC-0229.02.02 | Status defaults to Not Started (part) | PASS | Skip | Part status default logic was not touched by any fix |
| T-FUNC-0229.02.03 | Status defaults to Not Started (chapter) | FAIL | Must re-run | #74 fixed this defect directly |
| T-FUNC-0229.02.04 | Status defaults to Not Started (scene) | PASS | Skip | Scene status default logic was not touched by any fix |

---

## 03 — Writing Interface

*Excluded from Run 2 (per Run 1 Addendum):* T-FUNC-0304.03.01, T-FUNC-0304.03.02, T-FUNC-0304.03.03, T-FUNC-0304.04.01, T-FUNC-0304.04.02, T-FUNC-0304.04.03, T-FUNC-0304.05.01, T-FUNC-0304.05.02, T-FUNC-0304.05.03

| Test ID | Scenario | Run 1 | Recommendation | Rationale |
| --- | --- | --- | --- | --- |
| T-FUNC-0301.01.01 | Markdown heading elements rendered correctly | PASS | Must re-run | #122 fixed markdown preview rendering of line breaks; the preview rendering code was modified and all markdown element rendering should be re-verified |
| T-FUNC-0301.01.02 | Markdown typography elements rendered correctly | PASS | Must re-run | #122 fixed markdown preview rendering of line breaks; the preview rendering code was modified and all markdown element rendering should be re-verified |
| T-FUNC-0301.01.03 | Markdown list elements rendered correctly | PASS | Must re-run | #122 fixed markdown preview rendering of line breaks; the preview rendering code was modified and all markdown element rendering should be re-verified |
| T-FUNC-0301.01.04 | Remaining markdown elements rendered correctly | PASS | Must re-run | #122 fixed markdown preview rendering of line breaks; the preview rendering code was modified and all markdown element rendering should be re-verified |
| T-UI-0301.01.01 | Shortcut buttons H1–H3 displayed | PASS | Skip | Editor toolbar UI was not touched by any fix |
| T-UI-0301.01.02 | Shortcut buttons H4–H6 not displayed | PASS | Skip | Editor toolbar UI was not touched by any fix |
| T-FUNC-0302.01.01 | Autosave on change | PASS | Skip | Autosave logic was not touched by any fix |
| T-FUNC-0302.01.02 | No save when no changes | PASS | Skip | Autosave trigger logic was not touched by any fix |
| T-PERF-0302.01.01 | Autosave interval 30 seconds | PASS | Skip | Autosave interval configuration was not touched by any fix |
| T-USER-0303.01.01 | In-app notification on navigation with unsaved changes | FAIL | Must re-run | #75 fixed this defect directly |
| T-USER-0303.01.02 | Navigation confirmed | PASS | Must re-run | This test exercises the confirmation path of the same notification and navigation flow fixed by #75; the code path was modified |
| T-USER-0303.01.03 | Navigation cancelled | PASS | Must re-run | This test exercises the cancel path of the same notification and navigation flow fixed by #75; the code path was modified |
| T-USER-0303.01.04 | Navigation with no unsaved changes | PASS | Skip | This test exercises the no-notification path, which does not involve the dialog code modified by #75 |
| T-FUNC-0304.01.01 | Word count increments as words are added | PASS | Skip | Live in-editor word count logic was not touched by any fix |
| T-FUNC-0304.01.02 | Word count decrements as words are deleted | PASS | Skip | Live in-editor word count logic was not touched by any fix |
| T-FUNC-0304.02.01 | Novel word count updates when scene is saved | PASS | Must re-run | #76, #77, #78, and #79 all modified word count cascade logic; the positive (writing) word count update path shares code with the cascade and should be re-verified |
| T-FUNC-0304.02.02 | Novel word count updates (variant) | PASS | Must re-run | #76, #77, #78, and #79 all modified word count cascade logic; the positive word count update path shares code with the cascade and should be re-verified |
| T-FUNC-0304.02.03 | Part word count updates when scene is saved | PASS | Must re-run | #76, #77, #78, and #79 all modified word count cascade logic; the part-level word count update path shares code with the cascade and should be re-verified |
| T-FUNC-0304.03.04 | Archiving chapter reduces novel word count | FAIL | Must re-run | #76 fixed this defect directly |
| T-FUNC-0304.03.05 | Archiving chapter reduces part word count | FAIL | Must re-run | #76 fixed this defect directly |
| T-FUNC-0304.03.06 | Archiving part reduces novel word count | FAIL | Must re-run | #77 fixed this defect directly |
| T-FUNC-0304.04.04 | Unarchiving chapter increases novel word count | FAIL | Must re-run | #78 fixed this defect directly |
| T-FUNC-0304.04.05 | Unarchiving chapter increases part word count | FAIL | Must re-run | #78 fixed this defect directly |
| T-FUNC-0304.04.06 | Unarchiving part increases novel word count | FAIL | Must re-run | #78 fixed this defect directly |
| T-FUNC-0304.05.04 | Deleting chapter reduces novel word count | FAIL | Must re-run | #79 fixed this defect directly |
| T-FUNC-0304.05.05 | Deleting chapter reduces part word count | FAIL | Must re-run | #79 fixed this defect directly |
| T-FUNC-0304.05.06 | Deleting part reduces novel word count | FAIL | Must re-run | #79 fixed this defect directly |
| T-FUNC-0305.01.01 | Preview renders text without markdown syntax | PASS | Must re-run | #122 modified the preview rendering code; all preview behaviour should be re-verified |
| T-FUNC-0305.01.02 | Toggle back to edit mode shows markdown | PASS | Must re-run | #122 modified the preview rendering code; the toggle back to edit mode should be re-verified to confirm the fix did not affect it |
| T-FUNC-0306.01.01 | Distraction free mode hides UI | PASS | Skip | Distraction free mode logic was not touched by any fix |
| T-FUNC-0306.01.02 | Toggle off distraction free restores UI | PASS | Skip | Distraction free mode toggle logic was not touched by any fix |
| T-FUNC-0307.01.01 | Character cross-referencing in scene | PASS | Skip | Cross-referencing logic for characters was not touched by any fix |
| T-FUNC-0307.01.02 | Location cross-referencing in scene | PASS | Skip | Cross-referencing logic for locations was not touched by any fix |
| T-FUNC-0307.01.03 | Item cross-referencing in scene | PASS | Skip | Cross-referencing logic for items was not touched by any fix |
| T-FUNC-0307.01.04 | Characters not mentioned not cross-referenced | PASS | Skip | Cross-referencing exclusion logic was not touched by any fix |

---

## 04 — Character Management

*Excluded from Run 2 (per Run 1 Addendum):* T-FUNC-0401.01.02, T-DATA-0410.01.01

| Test ID | Scenario | Run 1 | Recommendation | Rationale |
| --- | --- | --- | --- | --- |
| T-FUNC-0401.01.01 | Character list displayed | PASS | Must re-run | #98 aligned card designs and features across all entities; the character list card UI was directly affected |
| T-UI-0401.01.01 | Character card UI | PASS | Must re-run | #98 directly modified card UI across entities including the character card |
| T-UI-0401.02.01 | Image displayed on character card when uploaded | PASS | Must re-run | #98 modified card UI across entities; the image display on the character card should be re-verified |
| T-UI-0401.02.02 | No image shown on character card when not uploaded | PASS | Must re-run | #98 modified card UI across entities; the no-image fallback on the character card should be re-verified |
| T-FUNC-0402.01.01 | Edit character name | PASS | Skip | Character edit logic was not touched by any fix |
| T-FUNC-0402.01.02 | Edit character rejected without name | PASS | Skip | Character edit validation was not touched by any fix |
| T-UI-0402.01.01 | Appears In field read-only on edit page | PASS | Skip | Appears In field behaviour was not touched by any fix |
| T-FUNC-0403.01.01 | Add character | PASS | Must re-run | #81 added missing fields to the character form; the add character code path was modified |
| T-FUNC-0403.01.02 | Add character rejected without name | PASS | Must re-run | #81 modified the character form; validation behaviour on the modified form should be re-verified |
| T-UI-0403.01.01 | Add character form fields | FAIL | Must re-run | #81 fixed this defect directly |
| T-FUNC-0403.02.01 | Upload character image (new) | PASS | Must re-run | #83 modified image upload validation across all entities; the upload code path was changed and should be re-verified |
| T-FUNC-0403.02.02 | Upload character image (no existing image) | PASS | Must re-run | #83 modified image upload validation across all entities; the upload code path was changed and should be re-verified |
| T-FUNC-0403.02.03 | Upload character image (replace existing) | PASS | Must re-run | #83 modified image upload validation across all entities; the upload code path was changed and should be re-verified |
| T-SEC-0403.01.01 | PNG image accepted | PASS | Must re-run | #83 modified image type validation; the allowed types must be re-verified to confirm they still pass |
| T-SEC-0403.01.02 | JPG image accepted | PASS | Must re-run | #83 modified image type validation; the allowed types must be re-verified to confirm they still pass |
| T-SEC-0403.01.03 | JPEG image accepted | PASS | Must re-run | #83 modified image type validation; the allowed types must be re-verified to confirm they still pass |
| T-SEC-0403.01.04 | BMP image rejected | FAIL | Must re-run | #83 fixed this defect directly |
| T-FUNC-0403.03.01 | Add character role | PASS | Skip | Character role logic was not touched by any fix |
| T-FUNC-0403.03.02 | Roles scoped to novel | PASS | Skip | Role scoping logic was not touched by any fix |
| T-FUNC-0403.04.01 | Rename character role | PASS | Skip | Role rename logic was not touched by any fix |
| T-FUNC-0403.05.01 | Delete character role | PASS | Skip | Role delete logic was not touched by any fix |
| T-FUNC-0403.05.02 | Deleting role does not delete characters | PASS | Skip | Role cascade logic was not touched by any fix |
| T-FUNC-0410.01.01 | Add character relationship | PASS | Must re-run | #84 fixed relationship edit logic across entities; the relationship creation code is adjacent and should be re-verified |
| T-FUNC-0410.01.02 | Add character relationship (variant) | PASS | Must re-run | #84 fixed relationship edit logic across entities; the relationship creation code is adjacent and should be re-verified |
| T-FUNC-0410.02.01 | Relationship shown on both characters | PASS | Must re-run | #84 fixed relationship edit logic across entities; the relationship display code is adjacent and should be re-verified |
| T-FUNC-0410.03.01 | Edit relationship labels | FAIL | Must re-run | #84 fixed this defect directly |
| T-FUNC-0410.04.01 | Delete character relationship | PASS | Skip | Relationship delete logic was not modified by #84, which addressed the edit path only |

---

## 05 — Location Management

*Excluded from Run 2 (per Run 1 Addendum):* T-FUNC-0501.01.02, T-DATA-0510.01.01

| Test ID | Scenario | Run 1 | Recommendation | Rationale |
| --- | --- | --- | --- | --- |
| T-FUNC-0501.01.01 | Location list displayed | PASS | Must re-run | #98 aligned card designs and features across all entities; the location list card UI was directly affected |
| T-UI-0501.01.01 | No parent summary on location list board | PASS | Skip | The parent summary behaviour was not touched by any fix |
| T-UI-0501.02.01 | Image displayed on location card when uploaded | PASS | Must re-run | #98 modified card UI across entities; the image display on the location card should be re-verified |
| T-UI-0501.02.02 | No image shown on location card when not uploaded | PASS | Must re-run | #98 modified card UI across entities; the no-image fallback on the location card should be re-verified |
| T-FUNC-0502.01.01 | Add location | PASS | Skip | Location creation logic was not touched by any fix |
| T-FUNC-0502.01.02 | Add location rejected without name | PASS | Skip | Location creation validation was not touched by any fix |
| T-UI-0502.01.01 | Add location form fields | PASS | Skip | The add location form was not changed by any fix |
| T-FUNC-0502.02.01 | Upload location image (new) | PASS | Must re-run | #83 modified image upload validation across all entities; the upload code path was changed and should be re-verified |
| T-FUNC-0502.02.02 | Upload location image (no existing image) | PASS | Must re-run | #83 modified image upload validation across all entities; the upload code path was changed and should be re-verified |
| T-FUNC-0502.02.03 | Upload location image (replace existing) | PASS | Must re-run | #83 modified image upload validation across all entities; the upload code path was changed and should be re-verified |
| T-SEC-0502.01.01 | PNG image accepted | PASS | Must re-run | #83 modified image type validation; the allowed types must be re-verified to confirm they still pass |
| T-SEC-0502.01.02 | JPG image accepted | PASS | Must re-run | #83 modified image type validation; the allowed types must be re-verified to confirm they still pass |
| T-SEC-0502.01.03 | JPEG image accepted | PASS | Must re-run | #83 modified image type validation; the allowed types must be re-verified to confirm they still pass |
| T-SEC-0502.01.04 | BMP image rejected | FAIL | Must re-run | #83 fixed this defect directly |
| T-FUNC-0502.03.01 | Add location type | PASS | Skip | Location type logic was not touched by any fix |
| T-FUNC-0502.03.02 | Location types scoped to novel | PASS | Skip | Location type scoping logic was not touched by any fix |
| T-FUNC-0502.04.01 | Rename location type | PASS | Skip | Location type rename logic was not touched by any fix |
| T-FUNC-0502.05.01 | Delete location type with assigned locations | FAIL | Must re-run | #88 added delete capability for locations; the location type delete logic is adjacent to the new delete location code and should be re-verified |
| T-FUNC-0502.05.02 | Delete location type with reassignment | FAIL | Must re-run | #88 added delete capability for locations; the location type delete logic is adjacent to the new delete location code and should be re-verified |
| T-FUNC-0503.01.01 | Edit location name | PASS | Skip | Location edit logic was not touched by any fix |
| T-FUNC-0503.01.02 | Edit location rejected without name | PASS | Skip | Location edit validation was not touched by any fix |
| T-UI-0503.01.01 | Appears In field read-only on edit page | PASS | Skip | Appears In field behaviour was not touched by any fix |
| T-FUNC-0510.01.01 | Add location relationship | PASS | Must re-run | #84 fixed relationship edit logic across entities; the relationship creation code is adjacent and should be re-verified |
| T-FUNC-0510.01.02 | Add location relationship (variant) | PASS | Must re-run | #84 fixed relationship edit logic across entities; the relationship creation code is adjacent and should be re-verified |
| T-FUNC-0510.02.01 | Relationship shown on both locations | PASS | Must re-run | #84 fixed relationship edit logic across entities; the relationship display code is adjacent and should be re-verified |
| T-FUNC-0510.03.01 | Edit location relationship labels | FAIL | Must re-run | #84 fixed this defect directly |
| T-FUNC-0510.04.01 | Delete location relationship | PASS | Skip | Relationship delete logic was not modified by #84, which addressed the edit path only |

---

## 06 — Item Management

*Excluded from Run 2 (per Run 1 Addendum):* T-FUNC-0601.01.02, T-DATA-0610.01.01

| Test ID | Scenario | Run 1 | Recommendation | Rationale |
| --- | --- | --- | --- | --- |
| T-FUNC-0601.01.01 | Item list displayed | PASS | Must re-run | #98 aligned card designs and features across all entities; the item list card UI was directly affected |
| T-UI-0601.01.01 | No parent summary on item list board | PASS | Skip | The parent summary behaviour was not touched by any fix |
| T-UI-0601.02.01 | Image displayed on item card when uploaded | PASS | Must re-run | #98 modified card UI across entities; the image display on the item card should be re-verified |
| T-UI-0601.02.02 | No image shown on item card when not uploaded | PASS | Must re-run | #98 modified card UI across entities; the no-image fallback on the item card should be re-verified |
| T-FUNC-0602.01.01 | Add item | PASS | Must re-run | #90 added missing fields to the item form; the add item code path was modified |
| T-FUNC-0602.01.02 | Add item rejected without name | PASS | Must re-run | #90 modified the item form; validation behaviour on the modified form should be re-verified |
| T-UI-0602.01.01 | Add item form fields | FAIL | Must re-run | #90 fixed this defect directly |
| T-FUNC-0602.02.01 | Upload item image (new) | PASS | Must re-run | #83 modified image upload validation across all entities; the upload code path was changed and should be re-verified |
| T-FUNC-0602.02.02 | Upload item image (no existing image) | PASS | Must re-run | #83 modified image upload validation across all entities; the upload code path was changed and should be re-verified |
| T-FUNC-0602.02.03 | Upload item image (replace existing) | PASS | Must re-run | #83 modified image upload validation across all entities; the upload code path was changed and should be re-verified |
| T-SEC-0602.01.01 | PNG image accepted | PASS | Must re-run | #83 modified image type validation; the allowed types must be re-verified to confirm they still pass |
| T-SEC-0602.01.02 | JPG image accepted | PASS | Must re-run | #83 modified image type validation; the allowed types must be re-verified to confirm they still pass |
| T-SEC-0602.01.03 | JPEG image accepted | PASS | Must re-run | #83 modified image type validation; the allowed types must be re-verified to confirm they still pass |
| T-SEC-0602.01.04 | BMP image rejected | FAIL | Must re-run | #83 fixed this defect directly |
| T-FUNC-0602.03.01 | Add item type | PASS | Skip | Item type logic was not touched by any fix |
| T-FUNC-0602.03.02 | Item types scoped to novel | PASS | Skip | Item type scoping logic was not touched by any fix |
| T-FUNC-0602.04.01 | Rename item type | PASS | Skip | Item type rename logic was not touched by any fix |
| T-FUNC-0602.05.01 | Delete item type with assigned items | FAIL | Must re-run | #91 added delete capability for items; the item type delete logic is adjacent to the new delete item code and should be re-verified |
| T-FUNC-0602.05.02 | Delete item type with reassignment | FAIL | Must re-run | #91 added delete capability for items; the item type delete logic is adjacent to the new delete item code and should be re-verified |
| T-FUNC-0603.01.01 | Edit item name | PASS | Skip | Item edit logic was not touched by any fix |
| T-FUNC-0603.01.02 | Edit item rejected without name | PASS | Skip | Item edit validation was not touched by any fix |
| T-UI-0603.01.01 | Appears In field read-only on edit page | PASS | Skip | Appears In field behaviour was not touched by any fix |
| T-FUNC-0610.01.01 | Add item relationship | PASS | Must re-run | #84 fixed relationship edit logic across entities; the relationship creation code is adjacent and should be re-verified |
| T-FUNC-0610.01.02 | Add item relationship (variant) | PASS | Must re-run | #84 fixed relationship edit logic across entities; the relationship creation code is adjacent and should be re-verified |
| T-FUNC-0610.02.01 | Relationship shown on both items | PASS | Must re-run | #84 fixed relationship edit logic across entities; the relationship display code is adjacent and should be re-verified |
| T-FUNC-0610.03.01 | Edit item relationship labels | PASS | Must re-run | #84 fixed relationship edit logic across entities; the item relationship edit path shares the same fix and should be re-verified |
| T-FUNC-0610.04.01 | Delete item relationship | PASS | Skip | Relationship delete logic was not modified by #84, which addressed the edit path only |

---

## 07 — World Building

Protocol 07 was not executed in Run 1 as the World Building feature (FEAT-07) was not yet implemented. Issue #114 closed the full implementation in June 2026. All 27 active tests in this protocol (29 minus the 2 excluded per the Run 1 Addendum) are new and must be executed in full.

*Excluded from Run 2 (per Run 1 Addendum):* T-FUNC-0701.01.02, T-DATA-0710.01.01

---

## Summary

| Protocol | Tests in scope | Must re-run | Skip |
| --- | --- | --- | --- |
| 01-user-management | 16 | 1 | 15 |
| 02-novel-management | 57 | 31 | 26 |
| 03-writing-interface | 35 | 22 | 13 |
| 04-character-management | 27 | 19 | 8 |
| 05-location-management | 27 | 17 | 10 |
| 06-item-management | 27 | 19 | 8 |
| 07-world-building | 27 | 27 | 0 |
| **Total** | **216** | **136** | **80** |

The 80 skippable tests represent approximately 37% of the Run 2 scope and are concentrated in the stable, untouched areas of the application: user authentication, core novel/part/chapter CRUD paths (create, edit, archive/delete cancel paths), role and type management, relationship deletion, and distraction-free and cross-referencing editor features.
