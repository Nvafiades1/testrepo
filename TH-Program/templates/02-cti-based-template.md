# CTH Hunt Plan: [Hunt Name] - CTI-Based

**Status:** `Draft` | `Not Started` | `Active` | `Complete`
**Analyst:** `[Your Name]`
**Date:** `[Date]`



## 1. Hypothesis
*What is the specific, testable statement for this hunt?*

> [e.g., "APT29 has compromised a supplier and is using their infrastructure (IP: 1.2.3.4) to access our environment."]

## 2. Hunt Overview
* **Goal:** [e.g., "Hunt for specific indicators and TTPs from CTI report #XYZ."]
* **Related Hunt (if any):** [Link to previous `CTH Hunt Tracker` item]

### 2a. Threat Intelligence
* **Threat Actor Group:** [e.g., "APT29", "FIN7"]
* **CTI Report Link:** [Link to the report]
* **Key Indicators (IOCs):**
    * **Hashes:** `[hash]`
    * **IPs/Domains:** `[ip/domain]`

## 3. MITRE ATT&CK TTPs
* **Tactic:** [e.g., "Initial Access"]
* **Technique/Sub-technique:** [e.g., "T1195.002: Compromise Software Supply Chain"]

## 4. Data Sources Required
- [ ] EDR (Process Events)
- [ ] Firewall Logs
- [ ] Proxy Logs
- [ ] DNS Logs
- [ ] Other: `[Specify]`

## 5. Analytic Queries

```kql
// Query 1: Hunt for known-bad IP
DeviceNetworkEvents
| where RemoteIP == "1.2.3.4"
```

## 6. Success Criteria
- [ ] Successfully find known-bad activity (True Positive).
- [ ] Conclude with high confidence that no such activity occurred (True Negative).
