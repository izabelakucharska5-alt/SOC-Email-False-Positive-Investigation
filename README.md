# SOC-Email-False-Positive-Investigation

**Email Security Alert Triage & False Positive Analysis**

![Status](https://img.shields.io/badge/Status-In%20Progress-orange) ![Project](https://img.shields.io/badge/Type-Blue%20Team-blue) ![SIEM](https://img.shields.io/badge/SIEM-Splunk-black) ![Level](https://img.shields.io/badge/Level-Junior-blue)

A simulated **SOC L1 email security investigation** involving a medium-risk alert generated for a welcome email sent to a new employee. The objective is to determine whether the message is malicious or a legitimate onboarding communication incorrectly flagged by an automated detection rule.

## Scenario

An employee receives a welcome email containing a link to an onboarding checklist. The email security system generates a medium-risk alert because the URL has not previously been observed for that recipient. The investigation uses email authentication results, sender validation, URL ownership, onboarding records and observed user activity to assess the alert.

## Focus Areas

- Email security alert triage.
- Sender and domain validation.
- SPF, DKIM and DMARC review.
- URL and domain validation.
- Correlation with internal onboarding records.
- Distinguishing suspicious indicators from legitimate business activity.
- False positive assessment and alert closure rationale.

## Technologies

- **Splunk Enterprise** — SIEM platform used to search and review the synthetic event dataset.
- **SPL** — Splunk Search Processing Language.
- **CSV** — Synthetic email gateway, validation, HR workflow and user activity events.

## Repository Contents

| File / Directory | Description |
|---|---|
| `investigation.md` | Investigation steps, executed SPL, screenshots, results and conclusion |
| `data/onboarding_email_logs.csv` | Synthetic event dataset for Splunk |
| `Screenshots/` | Screenshots documenting the investigation |

## Disclaimer

This is an educational project based on a fictional organization and synthetic data. No real employees, email accounts, internal systems or security incidents are involved. All domains and IP addresses are illustrative.
