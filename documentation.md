---
layout: page
title: Documentation
permalink: /documentation.html
---

Last updated: August 21, 2026

## Overview

Resource Planner & Gantt for Jira provides two connected views for planning Jira
Cloud work. The Resource Planner organizes work by assignee and working day. The
Gantt chart shows epics and their descendants as a delivery hierarchy.

## Requirements

- Jira Cloud with the App installed by an authorized administrator.
- Permission to view the relevant project and issues.
- Jira permission to edit an issue for changes to status, assignee, priority,
  estimates, or schedule fields.
- An active Marketplace subscription or trial for editing. An inactive license
  keeps the views available in read-only mode.

## Resource Planner

Open a Jira project and select **Resource Planner** from the project navigation.
The planner groups work by assignee and displays working days across the
timeline.

### Plan an issue

1. Select **Add ticket** after an assignee's latest planned issue, or select an
   empty working-day cell.
2. Search for an issue by key or summary.
3. Drag the issue onto the target day.
4. Review the planned duration. Jira estimates are converted using the
   project's working-hours-per-day setting.

Select an existing card to reveal insertion controls on its left and right.
Adding an issue between planned cards shifts later work by the inserted issue's
estimated working time. Saturdays, Sundays, and configured day offs are skipped.

### Manage an assignee timeline

- Select **Refresh** on an assignee row to reload only that timeline.
- Select **Manage assignees** to reorder assignees or hide rows.
- Use project settings in the management dialog to configure day offs and
  planning-data retention.
- Use **Remove from timeline** on a planned card to remove its planning record.
  This does not delete the Jira issue.
- Use **Today** to return the visible timeline to the current date.

### How dates and estimates work

- Planned duration uses Jira's original estimate when available.
- Working-day calculations skip weekends and configured assignee day offs.
- An in-progress issue can use status history when no explicit plan exists.
- Planning changes update relevant Jira schedule fields when those fields are
  available and the current user has permission.

## Gantt Chart

Open **Gantt chart** from Jira's Apps navigation. When opened from a Jira
project, the current project loads automatically. You can also enter a complete
epic key and select **Add epic**.

- Expand epics and issues to review their hierarchy.
- Review supported Jira issue types, including epics, stories, tasks, bugs, and
  subtasks, according to the hierarchy configured in Jira.
- Drag a planned bar to move work and use its end handle to change duration.
- Update status, priority, or assignee from an issue row when permissions allow.
- Select **Refresh** on an epic to reload only that epic and its descendants.
- Reorder sibling rows by dragging them within the same hierarchy level.
- Use **Load earlier** when older scheduled work is outside the visible range.

## Permissions and Errors

The App follows the current Jira user's permissions. If Jira rejects an update,
the App displays the returned error and leaves the Jira issue unchanged. A Jira
administrator should verify project permissions, field availability, and
workflow transitions when one user can view an issue but cannot edit it.

## Project Settings and Data

The **Manage assignees** dialog provides project-level controls for assignee
visibility and order, day offs, automatic retention, and clearing stored
planning data. These settings affect users of the App in that Jira project.

For details about stored records and deletion behavior, see
[Data Handling and Retention](./data-handling.html).

## Getting Help

See the [Support Policy](./support.html) for contact details, response targets,
and the information to include in a request.
