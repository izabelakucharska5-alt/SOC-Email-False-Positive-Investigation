# SOC-Email-False-Positive-Investigation

**Email Security Alert Triage & False Positive Investigation**

![Status](https://img.shields.io/badge/Status-Completed-brightgreen) ![Project](https://img.shields.io/badge/Type-Blue%20Team-blue) ![SIEM](https://img.shields.io/badge/SIEM-Splunk-black) ![Level](https://img.shields.io/badge/Level-Junior-blue)

A simulated **SOC L1 email security investigation** focused on determining whether an automated phishing alert represents a genuine security threat or a false positive.

The scenario involves a welcome email sent to a new employee by the company's People Operations department. The email contains a link to an internal onboarding portal and triggers a medium-risk security alert because the URL has not previously been observed for the recipient.

The investigation uses Splunk and multiple sources of synthetic evidence to validate the sender, URL, recipient activity and HR onboarding process.

## Investigation Summary

An email security system generated a medium-risk alert for a welcome email sent to a new employee.

The investigation identified the following indicators supporting the legitimacy of the message:

- SPF, DKIM and DMARC authentication checks all passed.
- The sender was verified as an active internal company account belonging to People Operations.
- The URL was registered in the corporate application inventory.
- The destination was identified as the internal New Starter Portal.
- The recipient accessed the portal using a known corporate device and internal IP address.
- People Operations confirmed that the email was part of an approved onboarding process.

**Final classification: FALSE POSITIVE**

The alert was triggered by a first-seen URL detection rule. The investigation found no evidence of phishing or malicious intent in the supplied dataset.

## Focus Areas

- Email security alert triage.
- Email authentication analysis (SPF, DKIM, DMARC).
- Sender identity verification.
- URL reputation and corporate application validation.
- Internal versus external URL assessment.
- Recipient activity investigation.
- Event correlation across multiple data sources.
- HR process verification.
- False positive identification and classification.
- Alert closure documentation and detection rule tuning recommendations.

## Technologies & Frameworks

- **Splunk Enterprise** — SIEM platform used to ingest and investigate synthetic email security events.
- **SPL** — Splunk Search Processing Language used to filter, display and analyze events.
- **CSV** — Structured dataset containing simulated email, security alert, sender validation, URL analysis, portal access and HR confirmation events.
- **Blue Team / SOC L1** — Security alert triage and evidence-based incident investigation.

## Repository Contents

| File / Directory | Description |
|---|---|
| [`investigation.md`](investigation.md) | Full investigation report, executed SPL searches, screenshots, findings and final classification |
| [`data/`](data/) | Synthetic email security log dataset |
| [`screenshots/`](screenshots/) | Screenshots documenting the Splunk investigation process |

## Investigation Workflow

1. Reviewed the available email security events and established the investigation scope.
2. Examined the original email and identified the reason behind the medium-risk alert.
3. Verified the sender against internal company account information.
4. Checked the URL against the corporate application inventory.
5. Reviewed the recipient's URL click and internal portal access activity.
6. Correlated the email with the approved HR onboarding record and confirmation.
7. Classified the alert and documented the recommended SOC response.

The full investigation includes the executed SPL searches, corresponding Splunk screenshots, textual results and analysis.

See [`investigation.md`](investigation.md).

## Key Findings

The automated detection rule identified a URL that was new for the recipient and generated a medium-risk alert.

Further investigation established that:

- The message originated from a verified internal sender.
- The URL pointed to a registered corporate application.
- The recipient accessed the internal onboarding portal from a known device.
- People Operations confirmed the onboarding process and the legitimacy of the email.
- The HR confirmation was associated with onboarding case `ONB-2026-118` and alert `MAIL-ALERT-2041`.

**Conclusion:** The alert was a false positive caused by a legitimate onboarding URL that had not previously been observed for the recipient.

## Recommended SOC Actions

The investigation recommends closing the alert as False Positive, documenting the supporting evidence and considering whether approved internal onboarding URLs should receive different treatment by the first-seen URL detection rule.

Any detection rule changes should follow the organization's approval process.

## Disclaimer

This is an educational Blue Team project based on a fictional scenario and synthetic security logs.

**All SPL searches were executed in Splunk Enterprise** against the supplied synthetic dataset.

No production infrastructure, real employee accounts or real security incidents were involved.

All names, domains, IP addresses and events are fictional. The findings demonstrate an investigation workflow and should not be interpreted as evidence from a real production environment.
