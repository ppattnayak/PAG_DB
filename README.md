# Automated-Postmortem-Action-Generation-PAG-using-LLM
Synthetic, anonymized dataset of 950 IT incidents with structured Corrective and Preventive Measures (CAPMs) — companion to “Automated Postmortem Action Generation (PAG) using LLM”


## Overview

This repository provides a **synthetic, anonymized dataset of 950 IT incidents**, created to support research on **Postmortem Action Generation (PAG)** — an NLP task for generating **Corrective and Preventive Measures (CAPMs)** from IT incident postmortems.

Unlike root-cause analysis datasets that identify *what went wrong*, this dataset focuses on *what to do next* — providing structured action recommendations (CAPMs) derived from incident metadata, severity, and narrative.

All entries are **synthetic**, **non-confidential**, and **fully anonymized** — designed to mirror realistic incident management data while preserving research reproducibility and ethical use.

---

## Dataset Schema


| Field | Type | Description |
|-------|------|-------------|
| **Incident_ID** | String | Unique identifier for the incident |
| **Summary** | String | Short summary describing the main issue or outage |
| **Description** | String | Detailed narrative of what occurred during the incident |
| **Severity** | String | Severity level of the incident (`Sev-1` for critical, `Sev-2` for major) |
| **Detection_Method** | String | How the incident was first detected (e.g., Monitoring Alert, Customer Report) |
| **Impact_Type** | String | Type of customer impact (e.g., Outage, Degraded Throughput, Latency Spike) |
| **Impacted_Customer_Count** | Integer | Approximate number of impacted customers or tenants |
| **Region** | String | Affected cloud region (e.g., `us-east-1`, `eu-central-1`) |
| **Root_Cause_Team** | String | Team or service area responsible for the impacted system |
| **Root_Cause_Type** | String | Category of the root cause (e.g., Monitoring Gaps, Config Errors, Dependency Failure) |
| **Root_Cause_Description** | String | Textual explanation of what caused the issue |
| **Impact_Start_Time** | DateTime (UTC) | When the customer impact began |
| **Detected_Time** | DateTime (UTC) | When the issue was detected or reported |
| **Mitigation_Time** | DateTime (UTC) | When mitigation or full recovery was achieved |
| **Repeat_Outage** | Boolean | Indicates whether a similar incident occurred previously (`true` / `false`) |
| **CAPM_Ticket_Link** | String | Synthetic link or reference ID for the associated incident ticket |
| **CAPM** | Object | Container object holding all corrective and preventive measures |
| **CAPM.Corrective_Actions** | Array[String] | Immediate steps taken to mitigate and resolve the incident |
| **CAPM.Preventive_Actions** | Array[String] | Long-term measures proposed to prevent recurrence of similar incidents |

