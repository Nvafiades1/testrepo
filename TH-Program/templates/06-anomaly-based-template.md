# CTH Hunt Plan: [Hunt Name] - Anomaly-Based

**Status:** `Draft` | `Not Started` | `Active` | `Complete`
**Analyst:** `[Your Name]`
**Date:** `[Date]`



## 1. Hypothesis
*What is the specific, testable statement for this hunt?*

> [e.g., "The 'rarest 1%' of user agents seen in our environment represent either test/dev systems or a malicious C2 beacon, and this activity warrants investigation."]

## 2. Hunt Overview
* **Goal:** [e.g., "Investigate a statistical anomaly to determine if it is malicious, benign, or misconfigured."]
* **Related Hunt (if any):** [Link to previous `CTH Hunt Tracker` item]

### 2a. Anomaly Details
* **Source Alert/Dashboard:** [Link to the SIEM/UBA alert that triggered this]
* **Anomaly Type:** [e.g., "Rarest 1%", "New Process", "High-Frequency Beacon", "New User Agent"]
* **Baseline Query (What is "Normal"?):**
    ```kql
    // Query used to find "normal" user agents
    DeviceNetworkEvents
    | summarize count() by UserAgent
    | top 100 by count_
    ```

## 3. MITRE ATT&CK TTPs
* **Tactic:** [e.g., "Command and Control"]
* **Technique/Sub-technique:** [e.g., "T1071.001: Application Layer Protocol: Web Protocols"]

## 4. Data Sources Required
- [ ] Proxy Logs
- [ ] EDR (Process Events)
- [ ] DNS Logs
- [ ] Other: `[Specify]`

## 5. Analytic Queries

```kql
// Query 1: Find all devices using the anomalous User Agent
DeviceNetworkEvents
| where UserAgent == "AnomalousUserAgentString"
| summarize by DeviceName, RemoteIP, RemoteUrl
```

## 6. Success Criteria
- [ ] The anomaly is identified and confirmed as malicious (True Positive).
- [ ] The anomaly is identified and confirmed as benign (e.g., new app, test script) (True Negative).
