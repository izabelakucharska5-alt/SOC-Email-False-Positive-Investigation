# Email Security Alert Investigation — SOC L1

**Project type:** Simulated Blue Team investigation  
**Status:** In progress  
**Dataset:** [`data/onboarding_email_logs.csv`](data/onboarding_email_logs.csv)  
**Environment:** Splunk Enterprise


## 1. Initial Event Overview

**Objective:** Review the available security events and establish the scope of the email security investigation.

**Executed SPL:**

```spl
index=main source="onboarding_email_logs.csv"
| stats count by event_type
| sort - count
```

![Initial Event Overview — Splunk search and results](screenshots/01-event-overview.png)

**Results:**

The search returned 8 events, with one event recorded for each of the following event types:

| Event type | Count |
|---|---:|
| email_received | 1 |
| email_security_alert | 1 |
| hr_confirmation | 1 |
| hr_onboarding_record | 1 |
| portal_access | 1 |
| sender_validation | 1 |
| url_analysis | 1 |
| url_click | 1 |

**Analysis:**

The dataset contains a complete sequence of events related to one email security alert.

The message was received, an automated security alert was generated, and further events were recorded for sender validation, URL analysis, recipient interaction and HR confirmation.

These events provide several investigation paths that can help determine whether the alert represents a genuine phishing threat or a legitimate business communication.

**Preliminary assessment:** Further investigation required. No final classification has been made.
