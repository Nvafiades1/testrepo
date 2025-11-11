# CTH Hunt Plan: [Hunt Name] - Purple Team

**Status:** `Draft` | `Not Started` | `Active` | `Complete`
**Analyst:** `[Your Name]`
**Date:** `[Date]`


## 1. Hypothesis
*What is the specific, testable statement for this hunt?*

> [e.g., "When the Red Team executes scenario #PT-004 (Atomic Red Team T1003.001), our EDR analytic 'Analytic-123' will fire and we will see the logs."]

## 2. Hunt Overview
* **Goal:** [e.g., "Validate that our documented detection logic works as expected during a live-fire test."]
* **Related Hunt (if any):** [Link to previous `CTH Hunt Tracker` item]

### 2a. Emulation Details
* **Emulation Scenario #:** [Link or ID to the formal test case, e.g., "PT-004"]
* **Red Team Tool:** [e.g., "Atomic Red Team", "Custom C2"]
* **Expected Analytic (from `CTH Analytics Tracker`):** [e.g., "This hunt *should* trigger 'Analytic-123: LSASS Access via Procdump'"]

## 3. MITRE ATT&CK TTPs
* **Tactic:** [e.g., "Credential Access"]
* **Technique/Sub-technique:** [e.g., "T1003.001: OS Credential Dumping: LSASS Memory"]

## 4. Data Sources Required
- [ ] EDR (Process Events)
- [ ] SIEM (Alerts)
- [ ] Other: `[Specify]`

## 5. Analytic Queries

```kql
// Query 1: Look for the specific alert
AlertInfo
| where Title == "Analytic-1Joy_LSASS_Access_via_Procdump"
| where TimeGenerated > (Red Team Test Start Time)

// Query 2: Look for the raw telemetry
DeviceProcessEvents
| where FileName =~ "procdump.exe" and ProcessCommandLine has "lsass"
| where TimeGenerated > (Red Team Test Start Time)
```

## 6. Success Criteria
- [ ] The expected alert fired (Analytic Validated).
- [ ] The alert did NOT fire, but we found the raw telemetry (Analytic Failed, Gap Identified).
- [ ] We found neither the alert nor the telemetry (Data Gap Identified).
