---
layout: default
title: Data and security
permalink: /security/
description: How PulseDB handles Confluence data, and why it qualifies for Runs on Atlassian.
---

# Data and security

<p class="lede">PulseDB is built so that your data never leaves Atlassian.</p>

<p class="meta">Last updated: November 17, 2026</p>

## Summary

| Question | Answer |
|---|---|
| Where does PulseDB run? | Entirely on Atlassian Forge, Atlassian's own cloud platform. |
| Does it send data outside Atlassian? | No. PulseDB declares no outside network access, so the platform blocks any connection to an outside server. |
| Does it store my data? | No. PulseDB keeps no copy of database rows. Nothing is saved in app storage. |
| Where are chart settings kept? | Confluence saves them with the page, like any other macro's settings. |
| Whose permissions are used? | The person viewing the page. Data is always read on their behalf. |
| Analytics or tracking? | None. |
| Does Sentire Labs see my data? | No. Sentire Labs has no access to your site or your data. |

## How a chart is built

1. A person opens a Confluence page that contains a PulseDB chart.
2. PulseDB asks Confluence for the database's columns and rows, **as that person**. Confluence only returns what they are allowed to see.
3. PulseDB calculates the chart's numbers in memory, on Atlassian's platform, and draws the chart.
4. When the page closes, nothing is kept.

PulseDB reads up to 2,000 rows per chart, and reads them again on each view or Refresh.

## Permissions PulseDB requests

| Permission | Why |
|---|---|
| `read:database:confluence` | Read a database's columns and rows to draw the chart |
| `search:confluence` | List databases in the settings panel |
| `read:content-details:confluence` | Read basic details such as a database's title and link |
| `read:space:confluence` | Show which space a database belongs to |
| `read:confluence-user` | Show people's names in person columns, instead of account codes |

PulseDB asks for **read** permissions only. It cannot change, create, or delete anything in Confluence.

## Logs

If a chart fails to load for an unexpected reason, PulseDB writes a one-line technical error message to the app's logs on Atlassian's platform. These messages never include database contents. Atlassian keeps these logs for a limited time under its own retention rules.

## Runs on Atlassian

PulseDB is designed to meet Atlassian's **Runs on Atlassian** program: it runs only on Atlassian's infrastructure, makes no outside connections, and keeps data within Atlassian's data residency and security controls.

## Reporting a security issue

Please email **support@sentire-labs.com** with the subject "Security". We will acknowledge reports within 2 business days and keep you updated until the issue is resolved.
