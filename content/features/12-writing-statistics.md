---
title: "12 Writing Statistics and Goals"
description: "Session tracking, word count statistics, and writing goals"
draft: false
---

The writing statistics module tracks the author's writing activity and progress against self-defined goals. Statistics are recorded at the session level and aggregated to day, week, month, and year. Goals are set independently at each level and are not derived from one another.

## FEAT-1201 Session tracking

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

### Description

The system shall automatically record writing sessions to provide the data underlying all statistics.

- A session begins when the user opens the scene editor
- A session ends when the user closes the scene editor or navigates away from it
- The system shall record the number of words written during each session
- Words written is calculated as the difference between the word count at the start and end of the session
- If the word count decreases during a session (e.g. the author deletes content) the session contribution may be negative
- Sessions are associated with the novel being written

## FEAT-1202 Writing statistics dashboard

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

### Description

The user shall be able to view a statistics dashboard showing their writing activity. The dashboard shall display words written for the following periods:

- Today
- This week
- This month
- This year
- All time

Statistics shall be displayed per novel and as a total across all novels. The dashboard shall be accessible from the novel board.

## FEAT-1203 Writing goals

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

### Description

The user shall be able to set writing goals independently at each of the following levels:

- Daily goal — target words per writing day
- Weekly goal — target words per week
- Monthly goal — target words per month
- Yearly goal — target words per year

Goals are set independently of each other and are not calculated from or constrained by other goal levels. The author is free to set goals that reflect their own writing schedule, including irregular patterns such as weeks off or variable writing days.

Goals are stored per novel. An author working on multiple novels may set different goals for each.

## FEAT-1204 Novel word count goal

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

### Description

The user shall be able to set a target word count for the novel. This is defined as a property of the novel — see [FEAT-0201 Add novel](/novel-it-docs/features/02-novel-management#feat-0201-add-novel).

The statistics dashboard shall display progress towards the novel word count goal alongside the time-based goals.

## FEAT-1205 Words required

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 2 |

### Description

Where a goal has been set, the system shall display the number of words still required to meet that goal in the current period.

- **Words required today** — daily goal minus words written today
- **Words required this week** — weekly goal minus words written this week
- **Words required this month** — monthly goal minus words written this month
- **Words required this year** — yearly goal minus words written this year
- **Words required for novel** — novel target word count minus current novel word count

Where words required is zero or negative the goal for that period has been met and the system shall indicate this to the user.
