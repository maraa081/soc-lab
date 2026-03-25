# MITRE ATT&CK Mapping

This document maps all attack scenarios simulated in this lab to the MITRE ATT&CK framework.  
The goal is to track coverage and identify detection gaps.

---

## Coverage Map

| Scenario | Tactic | Technique | Technique ID | Detection | Wazuh Rule |
|----------|--------|-----------|--------------|-----------|------------|
| SSH Brute Force | Credential Access | Brute Force | T1110 | Detected | 5760 |
| SSH Brute Force | Credential Access | Password Guessing | T1110.001 | Detected | 5760 |
| SSH Brute Force | Defense Evasion | Valid Accounts | T1078 | Detected | 5715 |
| SSH Brute Force | Lateral Movement | Remote Services – SSH | T1021.004 | Detected | 2502 |
| Web Attack | Initial Access | Exploit Public-Facing Application | T1190 | Planned | - |
| Lateral Movement | Lateral Movement | Remote Services | T1021 | Planned | - |
| Persistence | Persistence | Scheduled Task/Job – Cron | T1053.003 | Planned | - |
| Persistence | Persistence | Create Account | T1136 | Planned | - |

---

## Tactic Coverage

| Tactic | Covered | Planned | Total |
|--------|---------|---------|-------|
| Credential Access | 2 | 0 | 2 |
| Defense Evasion | 1 | 0 | 1 |
| Lateral Movement | 1 | 1 | 2 |
| Initial Access | 0 | 1 | 1 |
| Persistence | 0 | 2 | 2 |

---

## Notes

- Detection is validated when a Wazuh alert fires during attack simulation
- Each technique is linked to its corresponding attack scenario README
- Coverage will expand as new scenarios are added

---

## References

- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [Wazuh MITRE integration](https://documentation.wazuh.com/current/user-manual/ruleset/mitre.html)
