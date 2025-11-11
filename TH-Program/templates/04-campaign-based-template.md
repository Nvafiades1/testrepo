# CTH Hunt Plan: [Hunt Name] - Campaign-Based

**Status:** `Draft` | `Not Started` | `Active` | `Complete`
**Analyst:** `[Your Name]`
**Date:** `[Date]`



## 1. Hypothesis
*What is the specific, testable statement for this hunt?*

> [e.g., "Our organization has unpatched, public-facing VMware servers that are actively being exploited by threat actors using Log4Shell."]

## 2. Hunt Overview
* **Goal:** [e.g., "Proactively hunt for Log4Shell exploitation attempts against our perimeter."]
* **Related Hunt (if any):** [Link to previous `CTH Hunt Tracker` item]

### 2a. Campaign Details
* **Campaign Name:** [e.g., "Log4Shell", "SolarWinds"]
* **Key Malware/Tools:** [e.g., "Cobalt Strike", "Mirai"]
* **Vulnerability/Targeting:** [e.g., "Public-facing VMware Horizon", "Unpatched Exchange Servers"]

## 3. MITRE ATT&CK TTPs
* **Tactic:** [e.g., "Initial Access"]
* **Technique/Sub-technique:** [e.g., "T1190: Exploit Public-Facing Application"]

## 4. Data Sources Required
- [ ] Firewall Logs
- [ ] Proxy Logs / WAF Logs
- [ ] EDR (Process Events on web servers)
- [ ] Other: `[Specify]`

## 5. Analytic Queries

```kql
// Query 1: Look for Log4j exploit patterns in proxy logs
DeviceNetworkEvents
| where RemoteUrl has "jndi:ldap"
```

## 6. Success Criteria
- [ ] Successfully find evidence of exploitation (True Positive).
- [ ] Conclude with high confidence that no such activity occurred (True Negative).
