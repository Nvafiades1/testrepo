# CTH Hunt Plan: [Hunt Name] - TTP-Based

**Status:** `Draft` | `Not Started` | `Active` | `Complete`
**Analyst:** `[Your Name]`
**Date:** `[Date]`



## 1. Hypothesis
*What is the specific, testable statement for this hunt?*

> [e.g., "An adversary can use the `comsvcs.dll` minidump feature to dump LSASS memory, and our current analytics will not detect it."]

## 2. Hunt Overview
* **Goal:** [e.g., "Develop and test a new detection for a specific variant of T1003.001."]
* **Related Hunt (if any):** [Link to previous `CTH Hunt Tracker` item]

## 3. MITRE ATT&CK TTPs
* **Tactic:** [e.g., "Credential Access"]
* **Technique/Sub-technique:** [e.g., "T1003.001: OS Credential Dumping: LSASS Memory"]

### 3a. TTP Deep Dive
* **Detection Gaps (Hypothesized):** [e.g., "We believe we have good detection for `procdump.exe` but are blind to `comsvcs.dll` minidumps."]
* **Analytic Goal:** [e.G., "Develop a new query to specifically cover the `comsvcs.dll` variation."]

## 4. Data Sources Required
- [ ] EDR (Process Events)
- [ ] EDR (File Events)
- [ ] Windows Event Logs
- [ ] Other: `[Specify]`

## 5. Analytic Queries

```kql
// Query 1: Hunt for comsvcs.dll minidump artifact
DeviceProcessEvents
| where ProcessCommandLine has "comsvcs.dll" and ProcessCommandLine has "minidump"
```

## 6. Success Criteria
- [ ] A new, high-fidelity query is developed and validated.
- [ ] A detection gap is confirmed and formally documented.
