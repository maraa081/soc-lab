```markdown
# Wazuh Detection Rules

This document covers the Wazuh rules used and written for this lab.  
It includes both native rules triggered during attack simulations and custom rules developed for this project.

---

## Native Rules Triggered

### SSH Brute Force Scenario

| Rule ID | Level | Description | Triggered By |
|---------|-------|-------------|--------------|
| 5760 | 10 | SSH brute force attack detected | Multiple failed auth attempts |
| 5710 | 5 | Attempt to login using a non-existent user | Invalid username in SSH |
| 5715 | 3 | SSH authentication success | Successful login after failures |
| 2502 | 5 | User successfully logged in | PAM login event |

Rule levels in Wazuh go from 0 to 15 :
- **0–3** : Informational
- **4–7** : Low / Medium
- **8–11** : High
- **12–15** : Critical

---

## Custom Rules

### Rule – Brute Force Followed by Success

**Goal** : detect a successful SSH login from an IP that previously triggered brute force alerts.  
**Status** : In development

```xml
<group name="custom,ssh,bruteforce">
  <rule id="100001" level="12" frequency="5" timeframe="120">
    <if_matched_sid>5760</if_matched_sid>
    <same_source_ip/>
    <description>SSH brute force followed by successful login from same IP</description>
    <mitre>
      <id>T1110</id>
      <id>T1078</id>
    </mitre>
    <group>authentication_success,attack</group>
  </rule>
</group>
```

**Where to deploy** : `/var/ossec/etc/rules/local_rules.xml`

---

## How Rules Work in Wazuh

```
Log collected by agent
        ↓
Sent to Wazuh Manager
        ↓
Decoded (decoders extract fields)
        ↓
Matched against rules
        ↓
Alert generated if rule fires
        ↓
Alert visible in Wazuh Dashboard
```

---

## References

- [Wazuh ruleset documentation](https://documentation.wazuh.com/current/user-manual/ruleset/index.html)
- [Custom rules guide](https://documentation.wazuh.com/current/user-manual/ruleset/custom.html)
- [Wazuh rule syntax](https://documentation.wazuh.com/current/user-manual/ruleset/rules-classification.html)
```
