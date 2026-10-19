# Recorded-call QA — scores, evidence and alerts

**Type:** Independent training project using five supplied sample recordings.

## Why I built it

A transcript alone does not provide a consistent quality review. I wanted to apply the same service criteria to every recording and make low-scoring calls visible to a reviewer.

## What I built

An n8n workflow retrieves recordings from Google Drive, checks supported audio formats, transcribes the audio, filters voicemail or unusable inputs, and scores eight service-quality criteria. Structured results go to Google Sheets. A score below 3/5 triggers a Telegram alert.

**Flow:** Drive recording → format checks → transcription → conversation filter → structured QA → Sheets → conditional alert.

## Why this approach

A fixed rubric makes reviews comparable. A comment alongside every score gives the reviewer evidence to inspect. Source IDs and recorded delivery state protect finished work from duplicate rows and repeated alerts on replay.

## Test results

- Five out of five sample recordings completed.
- 40 criterion scores and 40 supporting comments recorded.
- Two calls rated Good and three Poor; the sample average was 3.3/5.
- All three required alerts had confirmed delivery.
- Replaying completed recordings produced no new QA rows or repeated alerts.
- Separate synthetic validation covered three classification cases and 11 deterministic checks.

## Current limits

This processes existing recordings; it is not a live voice agent or telephony service. The five-call corpus is small. The results do not establish model accuracy across other call types, time savings or changes in customer satisfaction.

## What I learned

Model output needs structural validation and explicit threshold tests. Checking alert delivery and replay behavior makes the end-to-end result more useful than a successful transcription alone.

**Tools:** n8n, Google Drive, Google Sheets, OpenRouter, transcription and QA models, JavaScript, Telegram Bot API.

[Portfolio, demo and execution evidence](https://nova-slice-e68.notion.site/Vadym-Dudka-3b7f35dfa98a80d485cfdf6ecab41b67)
