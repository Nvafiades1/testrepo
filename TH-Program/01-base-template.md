# CTH Hunt Plan: [Hunt Name]

**Status:** `Draft` | `Not Started` | `Active` | `Complete`
**Hunter:** `[Your Name]`
**Date:** `[Date]`



## 1. Hypothesis
*What is the specific, testable statement for this hunt?*

> [e.g., "An adversary is dumping LSASS memory using `procdump.exe` from a non-standard directory to steal credentials."]

## 2. Hunt Overview
* **Goal:** [e.g., "Detect unauthorized dumping of LSASS memory."]
* **Related Hunt (if any):** [Link to previous `CTH Hunt Tracker` item]

## 3. MITRE ATT&CK TTPs
* **Tactic:** [e.g., "Credential Access"]
* **Technique/Sub-technique:** [e.g., "T1003.001: OS Credential Dumping: LSASS Memory"]

## 4. Data Sources Required
- [ ] EDR (Process Events)
- [ ] EDR (File Events)
- [ ] Windows Event Logs (Security, System, PowerShell)
- [ ] Firewall Logs
- [ ] Proxy Logs
- [ ] DNS Logs
- [ ] Other: `[Specify]`

## 5. Analytic Queries
*Paste the KQL or SPL etc., queries you plan to run.*

```kql
// Query 1: Find procdump.exe process creation
DeviceProcessEvents
| where FileName =~ "procdump.exe" and ProcessCommandLine has "lsass"
```

## 6. Success Criteria
*How do you know this hunt is successful?*
- [ ] Successfully find known-bad activity (True Positive).
- [ ] Validate our EDR query can find the activity (Purple Team).
- [ ] Conclude with high confidence that no such activity occurred (True Negative).
