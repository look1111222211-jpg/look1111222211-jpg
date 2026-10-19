# HouseBox — support ticket routing and SLA checks

**Type:** Independent training project for an e-commerce support scenario.

## Why I built it

Support emails need a consistent place to record ownership, priority and follow-up status. I wanted to practise a complete intake-to-reporting process rather than an isolated AI classification step.

## What I built

Six connected n8n workflows cover Gmail intake, AI classification, owner assignment, priority rules, SLA escalation, error logging and on-demand reports. Google Sheets stores tickets and message logs, Telegram delivers notifications, and Google Docs holds reports.

**Flow:** Gmail message → classify and route → save ticket/message state → notify the owner → check SLA status → escalate or report.

## Why this approach

Separate workflows keep intake, escalation and reporting easier to inspect. Stored ticket/message state makes repeated processing testable. Escalation levels give an explicit next action when a request remains unresolved.

## Test results

- 17 synthetic emails: 15 customer requests and two spam messages.
- Replay checks found no duplicate ticket IDs.
- Manual checks exercised three escalation levels.

## Current limits

These are test results from a demo environment. The SLA schedule is paused in the demo. Unattended production scheduling and business response-time improvements were not measured.

## What I learned

A useful automation needs persistent state and visible failure paths, as well as the main successful route. Escalation rules also need clear boundaries and repeat tests.

**Tools:** n8n, Gmail, Google Sheets, Google Docs, AI classification, Telegram.

[Portfolio and execution evidence](https://nova-slice-e68.notion.site/Vadym-Dudka-3b7f35dfa98a80d485cfdf6ecab41b67)
