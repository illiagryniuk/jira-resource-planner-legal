# Cloud Security Statement

Last updated: June 24, 2026

## Overview
Resource Planner is a Forge app for Jira Cloud. The App is hosted on Atlassian's
Forge platform and runs within Atlassian Cloud infrastructure. We do not operate
separate external application servers for the normal operation of this App.

## Data Handling
The App processes Jira issue data and limited user data made available by Jira,
including accountId, displayName, and avatar URL where needed for the user
experience.

The App stores data in Atlassian Forge hosted storage, including:
- Planning data such as issue keys, planned start dates, and planned durations
- Assignee ordering and visibility settings
- Day-off settings
- Gantt preferences and expanded state
- Retention settings
- GDPR reporting metadata and related account identifiers

## Data Protection
- Data at rest: protected by Atlassian Forge hosted storage controls
- Data in transit: protected through TLS via Atlassian Cloud
- Infrastructure hosting: provided by Atlassian Cloud and Forge

## Authentication and Authorization
The App uses Atlassian Forge authentication and permission controls.

Where user actions modify Jira data, the App uses user-context requests through
Forge `asUser()` to rely on Jira's permission model. Platform and compliance
operations may use app-context access where required.

## Data Residency and Egress
The App is designed to operate within Atlassian-hosted services. We do not
intentionally transmit App data to unrelated third-party processors for standard
product functionality.

## Privacy and GDPR
The App stores personal data elements such as Atlassian account IDs when needed
for features and compliance. The App supports Atlassian's personal data
reporting obligations and provides administrative controls for deleting planning
data.

## Vulnerability Management
We review dependencies and app behavior for security issues and aim to respond
to reported vulnerabilities promptly. Where applicable, we follow Atlassian
security expectations for Forge and Marketplace partners.

## Incident Response
If a confirmed security incident affects the App, we will investigate, contain,
and remediate it as reasonably possible. We will coordinate with Atlassian where
platform involvement is required and notify affected parties when legally or
contractually required.

## Retention and Deletion
Data is retained only as needed for App functionality or compliance and may be
deleted through App controls, administrative action, uninstall, or verified
request. Some project-level data can also be governed by retention settings.

## Sub-processors
This App uses Atlassian Cloud services, including Jira Cloud APIs and Forge
hosted infrastructure. No additional routine operational sub-processors are
intentionally used at this time.

## Contact
Security and support contact:
[productt.radarr@gmail.com](mailto:productt.radarr@gmail.com)
