---
layout: page
title: Cloud Security Statement
permalink: /security-statement.html
---

Last updated: August 25, 2026

## Overview

Resource Planner & Gantt for Jira is built on Atlassian Forge and runs within
Atlassian Cloud infrastructure. The App does not use a separate Product Radar
application server or external runtime database for normal product operation.

## Architecture and Data Flow

The App reads Jira issue and user data through Atlassian APIs to display resource
and Gantt timelines. It stores planning records and configuration in Forge
hosted storage. User-requested Jira changes are sent through Forge to Jira Cloud.
The App has no configured remote runtime egress for Jira or planning data.

Stored data can include issue keys, planned dates and durations, assignee order
and visibility, day offs, Gantt preferences, retention settings, and limited
Atlassian account identifiers needed for functionality and privacy reporting.

## Security Controls

- **Authentication:** Atlassian authenticates users and invokes the App within
  their Jira Cloud session.
- **Authorization:** User-initiated Jira changes use user-context requests so
  Jira permissions remain authoritative. App-context operations are limited to
  platform, storage, and compliance functions that require them.
- **Data in transit:** Connections use TLS through Atlassian Cloud services.
- **Data at rest:** App data uses Atlassian Forge hosted storage protections.
- **Least privilege:** Forge scopes are limited to Jira work, Jira users, App
  storage, and personal-data reporting needed by App features.
- **Licensing:** Mutation operations are checked on the backend. An inactive
  subscription leaves planning data visible in read-only mode.
- **Dependency review:** Production dependencies are reviewed for known
  vulnerabilities before release, and security-relevant updates are evaluated.
- **Logging:** The App is designed not to intentionally log Jira issue content,
  credentials, tokens, or other end-user payloads.

## Data Residency and Retention

The App uses Forge hosted storage and inherits the data-residency capabilities
provided by Atlassian for Forge. Project administrators can configure automatic
retention for certain planning data and clear project planning data through the
App. Forge retains hosted storage for 28 days after uninstall before permanent
deletion under Atlassian's current platform process.

## Vulnerability Management

Security reports are reviewed according to severity and the supported version
is the latest production release available on Atlassian Marketplace. We target
acknowledgement of a security report within two business days and follow
applicable Atlassian Marketplace security remediation requirements.

Do not open a public GitHub issue for a suspected vulnerability. Follow the
private reporting instructions in the [Support Policy](./support.html).

## Incident Response

For a confirmed incident within the App, we will investigate, contain,
remediate, preserve relevant evidence, and coordinate with Atlassian where its
platform is involved. Affected customers or authorities will be notified where
legally or contractually required.

## Business Continuity

The App depends on Atlassian Jira Cloud and Forge availability. Product code and
release configuration are maintained in a private source repository. Recovery
of Forge-hosted data is subject to Atlassian platform capabilities and the
retention limits described above.

## Customer Responsibilities

Customers should maintain appropriate Jira permissions, promptly remove access
for departed users, avoid placing secrets in issue fields, review App changes,
and report suspected security issues privately.

## Subprocessors

See the current [Subprocessors page](./subprocessors.html). No unrelated external
processor receives Jira data during the App's standard runtime operation.

## Contact

Security reports: [security@product-radar.com](mailto:security@product-radar.com)<br>
Recommended subject: `Security report: Resource Planner & Gantt for Jira`
