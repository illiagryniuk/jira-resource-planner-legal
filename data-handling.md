---
layout: page
title: Data Handling and Retention
permalink: /data-handling.html
---

Last updated: August 21, 2026

## Data Flow Summary

Resource Planner & Gantt for Jira runs on Atlassian Forge. Jira data is read from
Jira Cloud through Atlassian APIs, processed within the Forge application and
the user's browser, and displayed in the planning views. Planning records and
App settings are stored in Forge hosted storage.

The App has no separate Product Radar application server or external runtime
database and does not intentionally send Jira data to unrelated third parties
during standard operation.

## Data Categories

| Category | Examples | Purpose | Stored by the App |
| --- | --- | --- | --- |
| Jira issues | Key, summary, status, type, priority, parent, estimate, assignee, dates, relevant changelog entries | Build timelines and apply user-requested updates | Planning records store issue keys, dates, and durations; other issue details are normally read from Jira as needed |
| Jira users | Atlassian account ID, display name, avatar URL | Show assignees and apply per-assignee settings | Account IDs and related settings may be stored; profile details are normally read from Jira |
| Project planning | Planned start, duration, issue order, selected epics, expanded state | Preserve Resource Planner and Gantt plans | Yes, in Forge hosted storage |
| Project settings | Assignee order and visibility, day offs, working-day and retention settings | Apply project planning rules | Yes, in Forge hosted storage |
| Privacy metadata | Account identifiers and reporting state | Meet Atlassian personal-data reporting and erasure obligations | Yes, where required |
| Credentials and payment data | Passwords, API tokens, card or bank details | Not required by the App | No |

## Jira Updates

When an authorized user changes an issue from the App, the App may update Jira
fields such as assignee, status, priority, original estimate, start date, or due
date. Jira permissions and workflow rules remain authoritative.

## Retention Controls

- Project administrators can configure automatic retention for certain stored
  planning data.
- Project administrators can clear planning data through App settings.
- Removing an issue from the Resource Planner removes its planning record but
  does not delete the Jira issue.
- Some limited privacy-reporting metadata may be retained where required to
  process Atlassian privacy events or legal obligations.

## Uninstall

When the App is uninstalled, Atlassian soft-deletes Forge hosted storage. Under
Atlassian's current Forge process, that storage is retained for 28 days and then
permanently deleted. Atlassian controls this platform-level period.

## Data Residency

Stored App data uses Forge hosted storage and inherits the data-residency
capabilities made available by Atlassian for Forge apps. Jira source data remains
subject to the customer's Jira Cloud residency configuration and Atlassian's
policies.

## Exports and Requests

Jira administrators can use Jira's own export and administration features for
Jira issue data. For questions or verified requests concerning App planning
records, contact [illia.gryniuk@product-radar.com](mailto:illia.gryniuk@product-radar.com).
